# mirelplatform 用 MySQL Dev Container

## 説明

このプロジェクトは、VSCode の devcontainer 機能を使用して MySQL サーバーを管理するためのものです。  
開発環境を簡単にセットアップし、MySQL サーバーをコンテナ内で実行することで、環境の一貫性を保ちながら開発を進めることができます。  
このプロジェクトは、mirelplatform 用のデータベースを管理するために設計されています。  

## 必要条件

- WSL2 がインストールされていること
- WSL2 上に Docker がインストールされていること

## 環境変数の設定

1. プロジェクトのルートディレクトリに `.env` ファイルを作成します。
2. `.env.sample` ファイルを参考にして、必要な環境変数を設定します。  
    設定例：
    ```properties
    MYSQL_ROOT_PASSWORD=root
    MYSQL_DATABASE=mipla
    MYSQL_USER=mipla
    MYSQL_PASSWORD=mipla
    ```

## 起動方法

1. VSCode でこのプロジェクトを開きます。
2. コマンドパレットを開き、「Remote-Containers: Reopen in Container」を実行します。これにより、定義されたコンテナ内で開発環境が再構築されます。

## MySQL への接続

1. MySQL クライアント拡張機能をインストールします。
2. 以下の情報で MySQL サーバーに接続します。

- ホスト: localhost
- ポート: 3306
- ユーザー名: root
- パスワード: your_password

## ディレクトリ構成


### 各ファイルの説明

- `.devcontainer/devcontainer.json`: Dev Container の設定ファイルです。コンテナの構成や環境変数の設定が含まれています。
- `.devcontainer/Dockerfile`: MySQL コンテナの Dockerfile です。ベースイメージや初期設定スクリプトのコピーなどが記述されています。
- `.env`: 環境変数を定義するファイルです。MySQL の設定に使用されます。
- `.env.sample`: 環境変数のサンプルファイルです。`.env` ファイルを作成する際の参考にします。
- `docker-compose.yml`: Docker Compose の設定ファイルです。MySQL サービスの構成が記述されています。
- `setup_mysql.sh`: MySQL の初期設定スクリプトです。コンテナ起動後に実行されます。
- `.vscode/extensions.json`: 推奨する VSCode 拡張機能の設定ファイルです。

## トラブルシューティング

### コンテナが起動しない場合

1. `.env` ファイルが正しく設定されているか確認してください。
2. WSL2 が正しくインストールされているか確認してください。
3. WSL2 に Docker がインストールされているか確認してください。
4. Docker と Docker Compose が正しくインストールされているか確認してください。
5. WSL2 ターミナルから `docker-compose up --build` コマンドを手動で実行して、エラーメッセージを確認してください。

### MySQL に接続できない場合

1. 環境変数が正しく設定されているか確認してください。
2. MySQL クライアントの設定が正しいか確認してください。
3. コンテナが正しく起動しているか確認してください。
