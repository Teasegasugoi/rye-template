# rye-template

Rye + VSCode での開発環境テンプレート

2023/09現在,以下の記事を参考にした
- https://zenn.dev/nowa0402/articles/85833db7ff2e13

## Linter
- [mypy](https://github.com/python/mypy)
  - 型チェック
  - [Mypy Type Checker](https://marketplace.visualstudio.com/items?itemName=ms-python.mypy-type-checker)
  - VSCode上での利用は, 拡張機能経由が推奨
    - https://qiita.com/siruku6/items/6a8412c41616b558df66
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

## Formatter