# Python UV Template

このリポジトリは、[uv](https://github.com/astral-sh/uv) を使用したPythonプロジェクトのテンプレートです。
高速なパッケージ管理、Lint/Format、型チェック、タスクランナー、pre-commitフックがあらかじめ設定されています。

## 特徴

- パッケージ管理: `uv` を使用して高速に依存関係を解決・インストールします。
- Lint / Format: [Ruff](https://github.com/astral-sh/ruff) を使用して高速なコード解析とフォーマットを行います。
- 型チェック: [Mypy](https://github.com/python/mypy) (strictモード) を設定済みです。
- タスクランナー: [Poe the Poet](https://github.com/nat-n/poethepoet) を使用して、よく使うコマンドを定義しています。
- Pre-commit: コミット時に自動的にチェック（Lint, Format, Type check）を実行する設定が含まれています。

## 前提条件

- [uv](https://github.com/astral-sh/uv) がインストールされていること。
- Python 3.14以上 (`pyproject.toml`の設定に基づく)

## セットアップ

1. 依存関係のインストール

   ```bash
   uv sync --dev
   ```

2. Pre-commitフックの有効化

   ```bash
   uv run pre-commit install
   ```

## 開発コマンド

`poethepoet` を使用して以下のタスクを実行できます。

- フォーマット
   ```bash
   uv run poe format
   ```
   Ruffを使用してコードをフォーマットします。

- Lint (修正付き)
   ```bash
   uv run poe lint
   ```
   Ruffを使用してLintを実行し、自動修正可能なものは修正します。

- 型チェック
   ```bash
   uv run poe type-check
   ```
   Mypyを使用して型チェックを行います。

- 一括チェック
   ```bash
   uv run poe check
   ```
   上記の `format`, `lint`, `type-check` を順番に実行します。pre-commitフックでもこのコマンドが実行されます。

## プロジェクトの開始方法

1. このリポジトリをテンプレートとして使用するか、クローンします。
2. `pyproject.toml` の `[project]` セクション（name, description, versionなど）を自分のプロジェクトに合わせて編集してください。
