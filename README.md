# myMLenv
ぼくのかんがえたさいきょうの機械学習環境(poetry)

# 備忘録
`python = ">=3.8.1,<3.10"`にしている理由
 - Google Colabは`Python 3.8`
   - pyenvで`3.8.10`を明示的に指定している
 - `<3.10`にしないと`llvmlite`周りがおかしくなり、`poetry install`不可能になる

 TensorFlowのネイティブWindowsのGPUサポートは`2.10.x`が最後
  - `2.11`以降ではWSLやDrirectMLPluginが必要
  - まだプレビュー機能っぽいので`2.10`で様子見
  - ちなみに、`2.11`を入れると`ModuleNotFoundError: No module named 'tensorflow'`になる（おい）