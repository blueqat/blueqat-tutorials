# 更新履歴

English version is available at [CHANGELOG.md](CHANGELOG.md).

## 2026-07-13 — 新しいblueqatSDKへの移行、日本語訳の追加

全37本のチュートリアルが、古いPyPI版の `blueqat` 0.3.xではなく、現行の[blueqatSDK](https://github.com/blueqat/blueqatSDK)(PyTorchネイティブ版)に対応しました。このリポジトリ(または他の場所)の古いコードが動かなくなった場合、原因はほぼ間違いなく以下の破壊的変更です。

### blueqatSDK自体の破壊的変更

- **`blueqat.pauli` と `blueqat.vqe` が廃止されました。** これまでそこに含まれていたもの — `X`, `Y`, `Z`, `I`, `qubo_bit`, `from_qubo`, `Vqe`, `QaoaAnsatz`, `AnsatzBase`, `VqeResult`, `expect` など — は、すべて `blueqat.utils` に移動しています。`from blueqat.pauli import ...` と `from blueqat.vqe import ...` は `from blueqat.utils import ...` に変更してください。
- **`qaoa()` 関数が廃止されました。** 代わりに `QaoaAnsatz` + `Vqe` の組み合わせを使用してください。
  ```python
  # 旧
  from blueqat.utils import qaoa
  result = qaoa(hamiltonian, step, init_circuit, mixer)

  # 新
  from blueqat.utils import Vqe, QaoaAnsatz
  result = Vqe(QaoaAnsatz(hamiltonian, step, init_circuit, mixer)).run()
  ```
- **`Vqe` は `minimizer=`(SciPy)引数を受け取らなくなりました。** 現在は常にPyTorchの自動微分と `torch.optim` オプティマイザで最適化します: `Vqe(ansatz, optimizer_cls=torch.optim.Adam, optimizer_kwargs={"lr": 0.05})`、`.run(max_iter=500, tol=1e-6)`。
- **`QaoaAnsatz` の `step` パラメータの意味が変わりました。** 以前は固定された(安価な)トロッター分割の細かさを表しており、`step=200` のような大きな値でも問題ありませんでした。現在は勾配降下法で実際に最適化される変分レイヤーの数を表すため、同じ大きな値だと非常に遅くなります。深さが本当に必要な場合を除き、小さい値(5〜10程度)を使用してください。
- **カスタムバックエンドの形が変わりました。** ゲート種別ごとのテンプレートメソッド(`_one_qubit_gate_noargs`、`_two_qubit_gate_noargs` など)は廃止されました。カスタムの `Backend` サブクラスは、単一のメソッド `run(self, gates, n_qubits, *args, **kwargs)` だけを実装するようになりました。
- **`run_with_sympy_unitary()` は廃止されました。** 代わりに `blueqat.circuit_funcs.circuit_to_unitary(circuit)` を使うと、回路のユニタリ行列をNumPy配列として取得できます。
- **ショット測定のビット列の順序が反転しました。** `Circuit.run(shots=...)` が返す `Counter` のキーは、**量子ビット0が右端の文字**になります(標準的な2進数表記の慣習)。以前は左端でした。コードが旧来の順序を前提としていても例外は発生せず、`key[0]`/`key[:n]` によるインデックス参照や `format(i, '0Nb')` 形式の比較などで、静かに間違った(しかし一見もっともらしい)答えが返ってきます。ノートブックの出力結果が、そのノートブック自身の想定と食い違う場合は、まずこれを疑ってください。
- **`Circuit.run()` は、状態ベクトルやハミルトニアン期待値の結果としてNumPy配列ではなくPyTorchテンソルを返すようになりました。** 通常は透過的です(表示、演算、`scipy.optimize.minimize` への受け渡しもそのまま機能します)が、後続の処理が `ndarray` を明示的に要求する場合は `.numpy()` を呼んでください。
- **PyPI版の `blueqat` パッケージは、依然として古い0.3.x系列のままです。** `pip install blueqat` では新しいSDKは手に入りません。代わりに `pip install git+https://github.com/blueqat/blueqatSDK` でインストールしてください。
- **`openfermionblueqat` は新SDKと非互換です。** `blueqat~=0.3.3` に固定されており、新SDKと一緒にインストールすると環境を古いSDKに静かにダウングレードしてしまいます。新SDKと併用してインストールしないでください。化学系チュートリアル(400〜402)では、`blueqat.utils` を直接使った小さな自作の代替実装(ハミルトニアン変換 + UCC Ansatz)を紹介しています。

### このリポジトリでの変更点

- 既存の全32本のチュートリアルを上記に対応させ、現行SDKの実環境でエラーなく最初から最後まで実行できることを確認しました。
- 全チュートリアルの日本語訳を `tutorial/ja/` 以下に追加し、新しい[README.ja.md](README.ja.md)からリンクしました。
- `tutorial/3_ftqc/`(唯一のサブフォルダで、内部の番号付けも不統一でした)をフラット化して `tutorial/` 直下に統合し、READMEがもともと想定していた `300`〜`311` の番号体系に統一しました。
- 「ゼロから作るショアのアルゴリズム」シリーズを追加しました(`320`〜`324`: 量子加算器、剰余加算器、制御剰余乗算、べき剰余、そして最後にアダマールによる重ね合わせ・逆QFT・連分数展開による後処理をこのシリーズ自身のべき剰余回路の上で組み合わせた完全なアルゴリズム)。既存の理論解説中心の `310_shor.ipynb` の関連編として、算術演算の部品から実際に動く実装を積み上げています。最終回では $N=6$ と、GPU上で $N=15$(教科書の定番例)の両方について実際の因数を復元しています。
- `323_grover_adaptive_qubo.ipynb` を `316_grover_adaptive_qubo.ipynb` に番号変更しました(誤ってゼロから作るショアのアルゴリズムシリーズの番号範囲の途中に入り込んでいたため)。またシリーズ第4回を `324` から `323` に変更し、シリーズ全体が `320`〜`324` の連番になるようにしました。
