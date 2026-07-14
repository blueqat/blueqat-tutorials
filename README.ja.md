Blueqat チュートリアル
====================

このチュートリアルは、最新の[blueqatSDK](https://github.com/blueqat/blueqatSDK)(PyTorchネイティブ版)に対応しています。以下でインストールできます。
```
pip install git+https://github.com/blueqat/blueqatSDK
```

English version is available at [README.md](README.md).

破壊的変更や新着情報は [CHANGELOG.ja.md](CHANGELOG.ja.md) をご覧ください。

0-1. 量子コンピュータの基本操作
--------------------

|No.|タイトル|
|:---|:---|
|001.|<a href="tutorial/ja/001_qubit.ipynb">量子ビットの操作と量子アルゴリズム</a>|
|002.|<a href="tutorial/ja/002_logicgate.ipynb">量子論理ゲート</a>|
|003.|<a href="tutorial/ja/003_cloud.ipynb">クラウドへの接続</a>|
|004.|<a href="tutorial/ja/004_backend.ipynb">バックエンド</a>|

1-1. 変分アルゴリズムと機械学習アルゴリズム
--------------------

|No.|タイトル|
|:---|:---|
|100.|<a href="tutorial/ja/100_vqe.ipynb">変分量子固有値ソルバー VQE</a>|
|101.|<a href="tutorial/ja/101_qaoa.ipynb">量子近似最適化アルゴリズム QAOA</a>|
|102.|<a href="tutorial/ja/102_quantum_classical_hybrid.ipynb">量子・古典ハイブリッド機械学習</a>|
|103.|<a href="tutorial/ja/103_qcbm.ipynb">量子回路ボルンマシン</a>|
|104.|<a href="tutorial/ja/104_ttn_mps.ipynb">木構造テンソルネットワークと行列積状態</a>|
|105.|<a href="tutorial/ja/105_clustering.ipynb">QAOAによるクラスタリング</a>|
|106.|<a href="tutorial/ja/106_linear_regression.ipynb">QAOAによる線形回帰</a>|
|107.|<a href="tutorial/ja/107_matrix_factorization.ipynb">行列分解</a>|
|108.|<a href="tutorial/ja/108_trafficflow.ipynb">QAOAによる交通流最適化</a>|
|109.|<a href="tutorial/ja/109_maxcut.ipynb">QAOAによるMaxcut、Exact Cover、グラフ彩色</a>|
|313.|<a href="tutorial/ja/313_setpacking.ipynb">集合パッキング問題</a>|
|315.|<a href="tutorial/ja/315_vertexcover.ipynb">頂点被覆問題</a>|
|316.|<a href="tutorial/ja/316_grover_adaptive_qubo.ipynb">QUBOに対するグローバー適応探索</a>|
|400.|<a href="tutorial/ja/400_chemistry.ipynb">量子化学とVQE</a>|
|401.|<a href="tutorial/ja/401_homemadeansatz.ipynb">自作Ansatzを用いたVQE</a>|
|402.|<a href="tutorial/ja/402_excitedstate.ipynb">励起状態の計算</a>|

3-1. FTQCアルゴリズム
--------------------

|No.|タイトル|
|:---|:---|
|300.|<a href="tutorial/ja/300_qft.ipynb">量子フーリエ変換</a>|
|301.|<a href="tutorial/ja/301_pea.ipynb">量子位相推定</a>|
|302.|<a href="tutorial/ja/302_pea2.ipynb">2×2エルミート行列の量子位相推定</a>|
|303.|<a href="tutorial/ja/303_pea3.ipynb">4×4エルミート行列の量子位相推定</a>|
|304.|<a href="tutorial/ja/304_qaa_qae_grover_gas.ipynb">量子振幅増幅と量子振幅推定とその応用</a>|
|305.|<a href="tutorial/ja/305_phase_kick_back.ipynb">位相キックバック</a>|
|306.|<a href="tutorial/ja/306_deutsch.ipynb">ドイチのアルゴリズム</a>|
|307.|<a href="tutorial/ja/307_deutsch-jozsa.ipynb">ドイチ・ジョザのアルゴリズム</a>|
|308.|<a href="tutorial/ja/308_bernstein-vazirani.ipynb">バーンスタイン・ヴァジラニのアルゴリズム</a>|
|309.|<a href="tutorial/ja/309_simon.ipynb">サイモンのアルゴリズム</a>|
|310.|<a href="tutorial/ja/310_shor.ipynb">ショアのアルゴリズム</a>|
|311.|<a href="tutorial/ja/311_four.ipynb">四則演算と剰余</a>|

3-2. ゼロから作るショアのアルゴリズム(本格実装)
--------------------

上記310の関連シリーズです。ショアのアルゴリズムの実際に動く実装を、算術演算の部品から少しずつ積み上げ、最後まで実行します。

|No.|タイトル|
|:---|:---|
|320.|<a href="tutorial/ja/320_shor_scratch_adder.ipynb">第1回: 量子加算器</a>|
|321.|<a href="tutorial/ja/321_shor_scratch_modulo_adder.ipynb">第2回: 剰余加算器</a>|
|322.|<a href="tutorial/ja/322_shor_scratch_controlled_multiplier.ipynb">第3回: 制御剰余乗算</a>|
|323.|<a href="tutorial/ja/323_shor_scratch_modular_exponentiation.ipynb">第4回: べき剰余</a>|
|324.|<a href="tutorial/ja/324_shor_full_algorithm.ipynb">第5回: 完全なアルゴリズム(位相推定・逆QFT・連分数展開)</a>|

Licence
----------
<a href="https://github.com/Blueqat/blueqat-tutorials/blob/main/LICENSE">Apache Licence 2.0</a>
