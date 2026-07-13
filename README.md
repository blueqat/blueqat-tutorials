Blueqat Tutorial
====================

These tutorials target the current [blueqatSDK](https://github.com/blueqat/blueqatSDK) (PyTorch-native edition). Install it with:
```
pip install git+https://github.com/blueqat/blueqatSDK
```

日本語版のチュートリアルは [README.ja.md](README.ja.md) を参照してください。

See [CHANGELOG.md](CHANGELOG.md) for breaking changes and what's new.

0-1. Basic Operation on Quantum Computer
--------------------

|No.|Title|日本語|
|:---|:---|:---|
|001.|<a href="tutorial/001_qubit.ipynb">Operation on Qubits and Quantum Algorithm</a>|<a href="tutorial/ja/001_qubit.ipynb">日本語</a>|
|002.|<a href="tutorial/002_logicgate.ipynb">Quantum Logic Gate</a>|<a href="tutorial/ja/002_logicgate.ipynb">日本語</a>|
|003.|<a href="tutorial/003_cloud.ipynb">Connection to the cloud</a>|<a href="tutorial/ja/003_cloud.ipynb">日本語</a>|
|004.|<a href="tutorial/004_backend.ipynb">Backend</a>|<a href="tutorial/ja/004_backend.ipynb">日本語</a>|

1-1. Variational and Machine Learning Algorithms
--------------------

|No.|Title|日本語|
|:---|:---|:---|
|100.|<a href="tutorial/100_vqe.ipynb">Variational Quantum Eigensolver VQE</a>|<a href="tutorial/ja/100_vqe.ipynb">日本語</a>|
|101.|<a href="tutorial/101_qaoa.ipynb">Quantum Approximate Optimization Algorithm QAOA</a>|<a href="tutorial/ja/101_qaoa.ipynb">日本語</a>|
|102.|<a href="tutorial/102_quantum_classical_hybrid.ipynb">Quantum Classical Hybrid Machine Learning</a>|<a href="tutorial/ja/102_quantum_classical_hybrid.ipynb">日本語</a>|
|103.|<a href="tutorial/103_qcbm.ipynb">Quantum Circuit Born Machine</a>|<a href="tutorial/ja/103_qcbm.ipynb">日本語</a>|
|104.|<a href="tutorial/104_ttn_mps.ipynb">Tree Tensor Network and Matrix Product State</a>|<a href="tutorial/ja/104_ttn_mps.ipynb">日本語</a>|
|105.|<a href="tutorial/105_clustering.ipynb">Clustering on QAOA</a>|<a href="tutorial/ja/105_clustering.ipynb">日本語</a>|
|106.|<a href="tutorial/106_linear_regression.ipynb">Linear Regression on QAOA</a>|<a href="tutorial/ja/106_linear_regression.ipynb">日本語</a>|
|107.|<a href="tutorial/107_matrix_factorization.ipynb">Matrix Factorization</a>|<a href="tutorial/ja/107_matrix_factorization.ipynb">日本語</a>|
|108.|<a href="tutorial/108_trafficflow.ipynb">Traffic Flow Optimization on QAOA</a>|<a href="tutorial/ja/108_trafficflow.ipynb">日本語</a>|
|109.|<a href="tutorial/109_maxcut.ipynb">Maxcut, Exact Cover, Graph Coloring on QAOA</a>|<a href="tutorial/ja/109_maxcut.ipynb">日本語</a>|
|117.|<a href="tutorial/313_setpacking.ipynb">Set Packing</a>|<a href="tutorial/ja/313_setpacking.ipynb">日本語</a>|
|118.|<a href="tutorial/315_vertexcover.ipynb">Vertext Cover</a>|<a href="tutorial/ja/315_vertexcover.ipynb">日本語</a>|
|119.|<a href="tutorial/323_grover_adaptive_qubo.ipynb">Grover Adaptive Search for QUBO</a>|<a href="tutorial/ja/323_grover_adaptive_qubo.ipynb">日本語</a>|
|123.|<a href="tutorial/400_chemistry.ipynb">Quantum Chemistry and VQE</a>|<a href="tutorial/ja/400_chemistry.ipynb">日本語</a>|
|124.|<a href="tutorial/401_homemadeansatz.ipynb">VQE with homemade ansatz</a>|<a href="tutorial/ja/401_homemadeansatz.ipynb">日本語</a>|
|125.|<a href="tutorial/402_excitedstate.ipynb">Excited state calculation</a>|<a href="tutorial/ja/402_excitedstate.ipynb">日本語</a>|

3-1. FTQC Algorithms
--------------------

|No.|Title|日本語|
|:---|:---|:---|
|300.|<a href="tutorial/300_qft.ipynb">Quantum Fourier Transform</a>|<a href="tutorial/ja/300_qft.ipynb">日本語</a>|
|301.|<a href="tutorial/301_pea.ipynb">Quantum Phase Estimation</a>|<a href="tutorial/ja/301_pea.ipynb">日本語</a>|
|302.|<a href="tutorial/302_pea2.ipynb">Quantum Phase Estimation of 2x2 Hermitian Matrix</a>|<a href="tutorial/ja/302_pea2.ipynb">日本語</a>|
|303.|<a href="tutorial/303_pea3.ipynb">Quantum Phase Estimation of 4x4 Hermitian Matrix</a>|<a href="tutorial/ja/303_pea3.ipynb">日本語</a>|
|304.|<a href="tutorial/304_qaa_qae_grover_gas.ipynb">Quantum Amplitude Amplification and Quantum Amplitude Estimation with Applications</a>|<a href="tutorial/ja/304_qaa_qae_grover_gas.ipynb">日本語</a>|
|305.|<a href="tutorial/305_phase_kick_back.ipynb">Phase Kickback</a>|<a href="tutorial/ja/305_phase_kick_back.ipynb">日本語</a>|
|306.|<a href="tutorial/306_deutsch.ipynb">Deutsch's algorithm</a>|<a href="tutorial/ja/306_deutsch.ipynb">日本語</a>|
|307.|<a href="tutorial/307_deutsch-jozsa.ipynb">Deutsch-Jozsa's algorithm</a>|<a href="tutorial/ja/307_deutsch-jozsa.ipynb">日本語</a>|
|308.|<a href="tutorial/308_bernstein-vazirani.ipynb">Bernstein-Vazirani's algorithm</a>|<a href="tutorial/ja/308_bernstein-vazirani.ipynb">日本語</a>|
|309.|<a href="tutorial/309_simon.ipynb">Simon's algorithm</a>|<a href="tutorial/ja/309_simon.ipynb">日本語</a>|
|310.|<a href="tutorial/310_shor.ipynb">Shor's algorithm</a>|<a href="tutorial/ja/310_shor.ipynb">日本語</a>|
|311.|<a href="tutorial/311_four.ipynb">Four Calculations and Modulus</a>|<a href="tutorial/ja/311_four.ipynb">日本語</a>|

3-2. Shor's Algorithm from Scratch (full implementation, work in progress)
--------------------

A companion series to 310 above, building a working implementation of Shor's algorithm from the ground up, one arithmetic building block at a time. More parts will be added as they're ready.

|No.|Title|日本語|
|:---|:---|:---|
|320.|<a href="tutorial/320_shor_scratch_adder.ipynb">Part 1: Quantum Adder</a>|<a href="tutorial/ja/320_shor_scratch_adder.ipynb">日本語</a>|
|321.|<a href="tutorial/321_shor_scratch_modulo_adder.ipynb">Part 2: Modulo Adder</a>|<a href="tutorial/ja/321_shor_scratch_modulo_adder.ipynb">日本語</a>|
|322.|<a href="tutorial/322_shor_scratch_controlled_multiplier.ipynb">Part 3: Controlled Modular Multiplication</a>|<a href="tutorial/ja/322_shor_scratch_controlled_multiplier.ipynb">日本語</a>|
|324.|<a href="tutorial/324_shor_scratch_modular_exponentiation.ipynb">Part 4: Modular Exponentiation</a>|<a href="tutorial/ja/324_shor_scratch_modular_exponentiation.ipynb">日本語</a>|

Licence
----------
<a href="https://github.com/Blueqat/blueqat-tutorials/blob/master/LICENSE">Apache Licence 2.0</a>

