# API_pptx2movie
このレポジトリではパワーポイント資料のノートテキストとスライドの画像を抽出し、mp４の動画ファイルを作成するapiを格納します。


## プロジェクト構成

- `app/`: FastAPIのアプリケーションコードが含まれています。
- `data/`: 抽出された画像や音声ファイルが保存されるディレクトリです。
- `scripts/`: ユーティリティスクリプトが含まれています。
- `requirements.txt`: アプリケーションを実行するために必要なPythonパッケージが記載されています。
- `README.md`: このドキュメントです。
- `.gitignore`: Gitで無視するファイルやディレクトリを指定するファイルです。
- `venv/`: Python仮想環境のディレクトリです（Gitで追跡されません）。

## 前提条件

- Python 3.10 以上
- ノートテキストや画像が含まれるPowerPointファイル
- Voicevox APIキー（必要に応じて）

## セットアップ手順

### 1. リポジトリのクローン

以下のコマンドでリポジトリをクローンし、ディレクトリに移動します。

```bash
git clone https://github.com/ayumu-dev/API_pptx2movie.git
cd API_pptx2movie
```

### 2. 仮想環境の作成と有効化

`venv`を使用して仮想環境を作成します。

```bash
python -m venv venv
```

仮想環境を有効化します。

- macOS/Linuxの場合:

  ```bash
  source venv/bin/activate
  ```

- Windowsの場合:

  ```bash
  .\venv\Scripts\activate
  ```
- Windowsでの仮想環境実行時に以下のエラーが出た場合:

  ```bash
    +  .\venv\Scripts\activate
    + CategoryInfo          : セキュリティ エラー: (: ) []、PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
  ```
  
- 下記のコマンドで実行ポリシーを変更
    ```bash
  Set-ExecutionPolicy RemoteSigned -Scope Process
  ```

### 3. 必要なパッケージのインストール

`requirements.txt`を使用して必要なパッケージをインストールします。

```bash
pip install -r requirements.txt
```


### 4. アプリケーションの実行

以下のコマンドでFastAPIサーバーを起動します。

```bash
uvicorn api.main:app --reload
```

これで、開発サーバーが`http://127.0.0.1:8000`で起動します。


## 5. APIドキュメント

サーバーが起動したら、次のURLでAPIドキュメントにアクセスできます。

```
http://127.0.0.1:8000/docs
```
