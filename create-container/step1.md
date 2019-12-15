# Dockerのインストール
まずは、コンテナを稼働させるためのコンテナエンジンとしてDockerを導入します。
Ubuntuにおけるインストール方法を以下に記しますが、学習内容としては本質的でないので、コマンドの実行さえできていれば、よく理解できなくても問題ありません。
## インストールコマンド
- aptの最新化
`sudo apt update`{{execute}}
- パッケージのインストール
```
sudo apt install -y \
     apt-transport-https \
     ca-certificates \
     curl \
     software-properties-common
```{{execute}}

- Docker公式GPGKeyの追加
`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`{{execute}}
- repositoryの追加
```
sudo add-apt-repository \
     "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) \
     stable"
```{{execute}}
- 再度aptの最新化
`sudo apt update`{{execute}}
- Dockerインストール
`sudo apt install -y docker-ce`{{execute}}

### 起動確認
`sudo systemctl status docker`{{execute}}