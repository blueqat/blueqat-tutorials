# Changelog

日本語版は [CHANGELOG.ja.md](CHANGELOG.ja.md) を参照してください。

## 2026-07-15 — Default branch renamed, README fixes, new QCNN tutorial, full renumbering

- Renamed the default branch from `master` to `main`.
- Fixed six README rows (Set Packing, Vertex Cover, Grover Adaptive Search, and the three chemistry notebooks) whose "No." labels were stale leftovers from before those files were renumbered; every row's label now matches its filename.
- Added `110_qcnn.ipynb`: a Quantum Convolutional Neural Network tutorial, migrated from private customer material and modernized to use blueqatSDK's native PyTorch autograd support (`loss.backward()` end to end, no manual finite-difference gradients needed as the original implementation required on the old SDK). Trains a 4-qubit "quanvolution" filter as the first layer of an MNIST digit classifier (0 vs 1), reaching ~98-99% test accuracy in under two minutes.
- **Renumbered and reorganized the whole tutorial set into six clearly-scoped categories** (breaking change for any bookmarked links — every affected file moved):
  - `0` Basic Operation on Quantum Computer (`001`-`004`, unchanged)
  - `1` Machine Learning Algorithms (`100`-`103`: hybrid ML, QCBM, TTN/MPS, QCNN)
  - `2` Optimization Algorithms — QAOA, VQE, and QUBO/Grover-based methods, previously scattered across `100`s and `313`/`315`/`316` (`200`-`209`)
  - `3` FTQC Algorithms (`300`-`310`; Shor's theory notebook moved out to category 4, `311_four` shifted down to fill the gap)
  - `4` Shor's Algorithm — the theory notebook plus the from-scratch series, now contiguous and no longer split across categories (`400`-`405`)
  - `5` Quantum Chemistry (`500`-`502`, previously `400`-`402`)
  
  Section headings were also simplified (e.g. `0-1.` → `0.`) now that each top-level number maps to exactly one category.

## 2026-07-13 — Migrated to the new blueqatSDK, added Japanese translations

All 37 tutorials now target the current [blueqatSDK](https://github.com/blueqat/blueqatSDK) (PyTorch-native edition), rather than the old PyPI `blueqat` 0.3.x package. If you have old code (from this repo or elsewhere) that stopped working, the breaking changes below are almost certainly why.

### Breaking changes in blueqatSDK itself

- **`blueqat.pauli` and `blueqat.vqe` no longer exist.** Everything they used to contain — `X`, `Y`, `Z`, `I`, `qubo_bit`, `from_qubo`, `Vqe`, `QaoaAnsatz`, `AnsatzBase`, `VqeResult`, `expect`, etc. — now lives in `blueqat.utils`. Change `from blueqat.pauli import ...` and `from blueqat.vqe import ...` to `from blueqat.utils import ...`.
- **The `qaoa()` convenience function is gone.** Replace it with the `QaoaAnsatz` + `Vqe` pattern:
  ```python
  # old
  from blueqat.utils import qaoa
  result = qaoa(hamiltonian, step, init_circuit, mixer)

  # new
  from blueqat.utils import Vqe, QaoaAnsatz
  result = Vqe(QaoaAnsatz(hamiltonian, step, init_circuit, mixer)).run()
  ```
- **`Vqe` no longer takes a `minimizer=` (SciPy) argument.** It always optimizes with PyTorch autograd + a `torch.optim` optimizer now: `Vqe(ansatz, optimizer_cls=torch.optim.Adam, optimizer_kwargs={"lr": 0.05})`, `.run(max_iter=500, tol=1e-6)`.
- **`QaoaAnsatz`'s `step` parameter means something different.** It used to be a cheap, fixed Trotter-schedule granularity (large values like `step=200` were fine). It's now the number of variational layers actually optimized by gradient descent, so the same large values are extremely slow. Use small values (5-10) unless you need the extra depth.
- **Custom backends changed shape.** The old per-gate-type template methods (`_one_qubit_gate_noargs`, `_two_qubit_gate_noargs`, etc.) are gone. A custom `Backend` subclass now implements a single method: `run(self, gates, n_qubits, *args, **kwargs)`.
- **`run_with_sympy_unitary()` no longer exists.** Use `blueqat.circuit_funcs.circuit_to_unitary(circuit)` to get a circuit's unitary matrix as a NumPy array instead.
- **Shot-sampling bitstring order is reversed.** `Circuit.run(shots=...)` now returns `Counter` keys with **qubit 0 as the rightmost character** (standard binary-string convention), not the leftmost. This doesn't raise an exception if your code assumed the old order — it just silently produces wrong-but-plausible answers, e.g. from `key[0]`/`key[:n]` indexing or `format(i, '0Nb')`-style comparisons. If a notebook's printed answer doesn't match its own stated expectation, suspect this first.
- **`Circuit.run()` now returns a PyTorch tensor**, not a NumPy array, for statevector/hamiltonian-expectation results. Usually transparent (printing, arithmetic, and even `scipy.optimize.minimize` all accept it), but call `.numpy()` if something downstream specifically requires an `ndarray`.
- **PyPI's `blueqat` package is still the old 0.3.x line.** `pip install blueqat` will *not* get you the new SDK — install with `pip install git+https://github.com/blueqat/blueqatSDK` instead.
- **`openfermionblueqat` is incompatible.** It pins `blueqat~=0.3.3` and will silently downgrade your environment back to the old SDK if installed. Don't install it alongside the new SDK; the chemistry tutorials (400-402) show a small self-contained replacement (Hamiltonian conversion + UCC ansatz) built directly on `blueqat.utils`.

### What changed in this repo

- All 32 existing tutorials updated for the above and verified to execute end-to-end with zero errors against a real install of the current SDK.
- Added a full Japanese translation of every tutorial, under `tutorial/ja/`, linked from a new [README.ja.md](README.ja.md).
- Flattened `tutorial/3_ftqc/` (previously the only tutorial subfolder, with inconsistent internal numbering) into the main `tutorial/` directory, renumbered `300`-`311` to match the scheme the README already implied.
- Added a "Shor's Algorithm from Scratch" series (`320`-`324`: quantum adder, modulo adder, controlled modular multiplication, modular exponentiation, and finally the full algorithm — Hadamard superposition, inverse QFT, and continued-fraction post-processing run together on this series' own modular-exponentiation circuit), building a working implementation up from arithmetic primitives, as a companion to the existing theory-focused `310_shor.ipynb`. The final part recovers real factors for both `N=6` and, on a GPU, the classic `N=15` example.
- Renumbered `323_grover_adaptive_qubo.ipynb` to `316_grover_adaptive_qubo.ipynb` (it had been sitting in the middle of the Shor's-from-scratch series' number range by mistake) and shifted the series' Part 4 from `324` to `323` so the series occupies a contiguous `320`-`324`.
