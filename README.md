# myMLenv
ぼくのかんがえたさいきょうの機械学習環境(poetry)

# 備忘録
`python = ">=3.8.1,<3.10"`にしている理由
 - Google Colabは`Python 3.8`
   - pyenvで`3.8.10`を明示的に指定している
 - `<3.10`にしないと`llvmlite`周りがおかしくなり、`poetry install`不可能になる
