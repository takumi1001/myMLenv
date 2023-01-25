# myMLenv
ぼくのかんがえたさいきょうの機械学習環境(poetry)

自分用です。

# Pytorch
環境によって固定せざる負えない。自分のデスクトップ環境向けは以下のようになる。
```
poetry install --with torch1131-cu117-cp38-win
```
必要に応じてOptinal Groupを作ること。

# 備忘録
`python = ">=3.8.1,<3.10"`にしている理由
 - Google Colabは`Python 3.8`
   - pyenvで`3.8.10`を明示的に指定している
 - `<3.10`にしないと`llvmlite`周りがおかしくなり、`poetry install`不可能になる

TensorFlowのネイティブWindowsのGPUサポートは`2.10.x`が最後
  - `2.11`以降ではWSLやDrirectMLPluginが必要
  - まだプレビュー機能っぽいので`2.10`で様子見
  - ちなみに、`2.11`を入れると`ModuleNotFoundError: No module named 'tensorflow'`になる（おい）

Jupyter Labの日本語化
  - `jupyterlab-language-pack-ja-jp` で可能だが・・・
  - 導入したら設定がバグったのでやめたほうがいいです。

Windowsにおける`CUDA`バージョンの切り替え
  - `CUDA_PATH`環境変数を適宜切り替える
    - `%CUDA_PATH_V11_2%`: Tenosrflow
    - `%CUDA_PATH_V11_7%`: Pytorch
  - cf. https://blog.kintarou.com/2021/06/25/post-1591/
  - 切り替え用のスクリプト書いた
    - https://gist.github.com/takumi1001/2affa546b58d74224e32938fefac6b02 
