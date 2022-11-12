### devcontainer 用のファイルを追加

1. 拡張機能をインストール

   Dev Containers - Visual Studio Marketplace  
   https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers

1. コマンドパレットを開く

1. `Dev Containers: Add Dev Container Configuration Files` を入力してクリック

1. `From 'docker-compose.yml'` をクリック

1. Select a service で `app` をクリック

1. `.devcontainer/` 以下の `docker-compose.yml` は不要なので削除

1. `devcontainer.json` を変更 f9bcf1e

### Codespaces 用に Dockerfile と docker-compose.yml を変更

Dockerfile f9bcf1e

docker-compose.yml b4dda67

### Codespaces で環境変数の設定

#### シークレットの設定をする場合

Managing encrypted secrets for your codespaces - GitHub Docs  
https://docs.github.com/ja/codespaces/managing-your-codespaces/managing-encrypted-secrets-for-your-codespaces#adding-a-secret

#### 環境変数を設定してみた

ターミナルに `printenv` と入力すると一覧を表示

URL はこんなかんじ  
`CODESPACE_NAME=yos10-legendary-chainsaw-r6qv574vvqp2x9wr`

ターミナルに以下を入力

```
export GITHUB_CLIENT_ID=
export GITHUB_CLIENT_SECRET=
export PORT=8000
export CALLBACK_URL="https://${CODESPACE_NAME}-${PORT}.${GITHUB_CODESPACES_PORT_FORWARDING_DOMAIN}/"
```

### Codespaces の中断

1. VS Code の左下の `>< Codespaces` をクリック

1. `現在の Codespaces を中断する` をクリック
