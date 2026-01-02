# Jupyter Singularity Template

Singularity イメージを作成するための Cookiecutter テンプレートです。
Python、Jupyter Notebook、および最新の Python パッケージマネージャーである `uv` を含んだ環境を構築します。
始まりがあって、終わりがあるジョブにはSingularityの方がDockerよりも適すると考えます。

## 特徴

- **Base Image**: Alpine latest
- **Package Manager**: [uv](https://github.com/astral-sh/uv)
- **Jupyter**: Jupyter Notebook がプリインストールされています。
- **Optional**: Starship (Rich Console) の導入が可能です。

## 必要要件

- [Singularity](https://apptainer.org/) (または Apptainer)
- [Cookiecutter](https://github.com/cookiecutter/cookiecutter)

## 使い方

### プロジェクトの作成

以下のコマンドを実行して、テンプレートからプロジェクトを作成してください。

```bash
cookiecutter .
```

### 設定項目

プロンプトに従って以下の設定を入力します。

- `package_name`: プロジェクトのディレクトリ名 (デフォルト: `jupyter-latest`)
- `rich_console`: Starship プロンプトをインストールし、リッチなコンソールを使用するか (`y` or `n` / デフォルト: `N`)

## 生成されるプロジェクト構成

```text
<package_name>/
├── apps/          # アプリケーションコード (uv init済み)
├── notebooks/     # Jupyter Notebook 保存用ディレクトリ
├── image.def      # Singularity 定義ファイル
├── makefile       # ビルド・実行用 Makefile
├── readme.md      # プロジェクトドキュメント
└── ...
```

## ビルドと実行

生成されたプロジェクト内で `make` コマンドを使用できます。

```bash
cd <package_name>
make build  # Singularity イメージのビルド
make run    # コンテナシェルの起動
```
