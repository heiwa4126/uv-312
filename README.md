# uv-312

uv で Python 3.12 を使うメモ。

バージョン 3.12 というのは例で、「システム標準でないバージョンの Python を使う」練習。

## プロジェクトの作り方

uv+PoeThePoet でやってます(2024-12)。

```sh
mkdir uv-312 && cd !$
uv init
uv sync
uv venv --python 3.12 # なければ自動ダウンロードされる
```

`.python-version` を編集して `3.12` に書き換え

`uv run python --version` で `Python 3.12.x` と表示されたら OK

## 便利コマンド

```sh
# このプロジェクトですでに使えるようになっているPythonのバージョン
uv python list

# このOSで使えるPython全リスト (pyenvのあれだ)
uv python list --all-versions

# .python-versionで指定されたデフォルトのPythonが、実際にどこにあるか
uv python find --system

# uv run で別のバージョンのpythonを使う例
uv run --python 3.10 python --version
## または UV_PYTHON_VERSION 環境変数で指定
## --python オプションでパスを指定してもいいらしい。
```

## .python-version が無い(または削除した)時

どの Python が使われるかよくわからない。

## 参考

- [Python versions | uv](https://docs.astral.sh/uv/concepts/python-versions/)
