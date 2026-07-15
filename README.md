Blueqat Tutorial
====================

These tutorials target the current [blueqatSDK](https://github.com/blueqat/blueqatSDK) (PyTorch-native edition). Install it with:
```
pip install git+https://github.com/blueqat/blueqatSDK
```

日本語版のチュートリアルは [README.ja.md](README.ja.md) を参照してください。

See [CHANGELOG.md](CHANGELOG.md) for breaking changes and what's new.

0. Basic Operation on Quantum Computer
--------------------

|No.|Title|日本語|
|:---|:---|:---|
|001.|<a href="tutorial/001_qubit.ipynb">Operation on Qubits and Quantum Algorithm</a>|<a href="tutorial/ja/001_qubit.ipynb">日本語</a>|
|002.|<a href="tutorial/002_logicgate.ipynb">Quantum Logic Gate</a>|<a href="tutorial/ja/002_logicgate.ipynb">日本語</a>|
|003.|<a href="tutorial/003_cloud.ipynb">Connection to the cloud</a>|<a href="tutorial/ja/003_cloud.ipynb">日本語</a>|
|004.|<a href="tutorial/004_backend.ipynb">Backend</a>|<a href="tutorial/ja/004_backend.ipynb">日本語</a>|

1. Machine Learning Algorithms
--------------------

|No.|Title|日本語|
|:---|:---|:---|
|100.|<a href="tutorial/100_quantum_classical_hybrid.ipynb">Quantum Classical Hybrid Machine Learning</a>|<a href="tutorial/ja/100_quantum_classical_hybrid.ipynb">日本語</a>|
|101.|<a href="tutorial/101_qcbm.ipynb">Quantum Circuit Born Machine</a>|<a href="tutorial/ja/101_qcbm.ipynb">日本語</a>|
|102.|<a href="tutorial/102_ttn_mps.ipynb">Tree Tensor Network and Matrix Product State</a>|<a href="tutorial/ja/102_ttn_mps.ipynb">日本語</a>|
|103.|<a href="tutorial/103_qcnn.ipynb">Quantum Convolutional Neural Network</a>|<a href="tutorial/ja/103_qcnn.ipynb">日本語</a>|

2. Optimization Algorithms (QAOA, etc.)
--------------------

|No.|Title|日本語|
|:---|:---|:---|
|200.|<a href="tutorial/200_vqe.ipynb">Variational Quantum Eigensolver VQE</a>|<a href="tutorial/ja/200_vqe.ipynb">日本語</a>|
|201.|<a href="tutorial/201_qaoa.ipynb">Quantum Approximate Optimization Algorithm QAOA</a>|<a href="tutorial/ja/201_qaoa.ipynb">日本語</a>|
|202.|<a href="tutorial/202_clustering.ipynb">Clustering on QAOA</a>|<a href="tutorial/ja/202_clustering.ipynb">日本語</a>|
|203.|<a href="tutorial/203_linear_regression.ipynb">Linear Regression on QAOA</a>|<a href="tutorial/ja/203_linear_regression.ipynb">日本語</a>|
|204.|<a href="tutorial/204_matrix_factorization.ipynb">Matrix Factorization</a>|<a href="tutorial/ja/204_matrix_factorization.ipynb">日本語</a>|
|205.|<a href="tutorial/205_trafficflow.ipynb">Traffic Flow Optimization on QAOA</a>|<a href="tutorial/ja/205_trafficflow.ipynb">日本語</a>|
|206.|<a href="tutorial/206_maxcut.ipynb">Maxcut, Exact Cover, Graph Coloring on QAOA</a>|<a href="tutorial/ja/206_maxcut.ipynb">日本語</a>|
|207.|<a href="tutorial/207_setpacking.ipynb">Set Packing</a>|<a href="tutorial/ja/207_setpacking.ipynb">日本語</a>|
|208.|<a href="tutorial/208_vertexcover.ipynb">Vertext Cover</a>|<a href="tutorial/ja/208_vertexcover.ipynb">日本語</a>|
|209.|<a href="tutorial/209_grover_adaptive_qubo.ipynb">Grover Adaptive Search for QUBO</a>|<a href="tutorial/ja/209_grover_adaptive_qubo.ipynb">日本語</a>|

3. FTQC Algorithms
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
|310.|<a href="tutorial/310_four.ipynb">Four Calculations and Modulus</a>|<a href="tutorial/ja/310_four.ipynb">日本語</a>|

4. Shor's Algorithm
--------------------

The theory notebook (400) plus a from-scratch series (401-405) building a working implementation of Shor's algorithm from the ground up, one arithmetic building block at a time, and running it end to end.

|No.|Title|日本語|
|:---|:---|:---|
|400.|<a href="tutorial/400_shor.ipynb">Shor's algorithm</a>|<a href="tutorial/ja/400_shor.ipynb">日本語</a>|
|401.|<a href="tutorial/401_shor_scratch_adder.ipynb">From Scratch Part 1: Quantum Adder</a>|<a href="tutorial/ja/401_shor_scratch_adder.ipynb">日本語</a>|
|402.|<a href="tutorial/402_shor_scratch_modulo_adder.ipynb">From Scratch Part 2: Modulo Adder</a>|<a href="tutorial/ja/402_shor_scratch_modulo_adder.ipynb">日本語</a>|
|403.|<a href="tutorial/403_shor_scratch_controlled_multiplier.ipynb">From Scratch Part 3: Controlled Modular Multiplication</a>|<a href="tutorial/ja/403_shor_scratch_controlled_multiplier.ipynb">日本語</a>|
|404.|<a href="tutorial/404_shor_scratch_modular_exponentiation.ipynb">From Scratch Part 4: Modular Exponentiation</a>|<a href="tutorial/ja/404_shor_scratch_modular_exponentiation.ipynb">日本語</a>|
|405.|<a href="tutorial/405_shor_full_algorithm.ipynb">From Scratch Part 5: The Full Algorithm (Phase Estimation, Inverse QFT, Continued Fractions)</a>|<a href="tutorial/ja/405_shor_full_algorithm.ipynb">日本語</a>|

5. Quantum Chemistry
--------------------

|No.|Title|日本語|
|:---|:---|:---|
|500.|<a href="tutorial/500_chemistry.ipynb">Quantum Chemistry and VQE</a>|<a href="tutorial/ja/500_chemistry.ipynb">日本語</a>|
|501.|<a href="tutorial/501_homemadeansatz.ipynb">VQE with homemade ansatz</a>|<a href="tutorial/ja/501_homemadeansatz.ipynb">日本語</a>|
|502.|<a href="tutorial/502_excitedstate.ipynb">Excited state calculation</a>|<a href="tutorial/ja/502_excitedstate.ipynb">日本語</a>|

Licence
----------
<a href="https://github.com/Blueqat/blueqat-tutorials/blob/main/LICENSE">Apache Licence 2.0</a>
