# rye-template

自分用の Rye + VSCode での開発環境テンプレート


## 注意
一部ツールは`pip install`をする必要がなくなり、拡張機能のインストールだけで利用可能になった。しかし、プレビュー版であるので機能が変更されるかも
- https://github.com/microsoft/vscode-python/wiki/Migration-to-Python-Tools-Extensions
  - Pylint
  - Flake8
  - Mypy Type Checker
  - Black Formatter
  - autopep8
  - isort

## Linter
- [mypy](https://github.com/python/mypy)
  - 型チェック
  - 拡張機能: [Mypy Type Checker](https://marketplace.visualstudio.com/items?itemName=ms-python.mypy-type-checker)
  - VSCode上での利用は, 拡張機能経由が推奨
    - が、自分の環境ではうまく機能してくれないので、pip install の方を利用する
  - pip install での設定
    - 詳細設定は、pyproject.toml に追加する
  - 採用しているコマンドラインオプション
    - ignore-missing-imports
      - 型情報を持つstubファイルを含まないパッケージのインポートを許可
    - disallow-untyped-defs
      - 関数の引数・戻り値に型指定必須
    - no-implicit-optional
      - デフォルト引数にNoneをセットする際に、引数のアノテーションにOptional必須
    - warn-return-any
      - 戻り値がAnyではない関数の戻り値がAnyの場合に警告
    - warn-redundant-casts
      - 冗長なキャストを警告
    - show-error-context
      - エラーメッセージを詳細表示
    - show-column-numbers
      - エラー発生箇所を行列数で明示

- [Flake8](https://github.com/PyCQA/flake8)
  - 倫理エラーやスタイルをチェック
  - 拡張機能: [Flake8](https://marketplace.visualstudio.com/items?itemName=ms-python.flake8)
  - 採用しているコマンドラインオプション
    - max-line-length
      - 行の長さの上限


## Formatter
- [Black](https://github.com/psf/black)
  - 拡張機能: [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter)
  - line-length
    - 行の長さの上限
- [isort](https://github.com/pycqa/isort/)
  - import文を綺麗に
  - 拡張機能: [isort](https://marketplace.visualstudio.com/items?itemName=ms-python.isort)
