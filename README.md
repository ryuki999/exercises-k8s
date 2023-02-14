# Kubernetes演習
## はじめに
ソフトウェア構築特論の演習課題として、minikubeを用いたサービスの構築を行う。

## 演習環境
* Windows10 / WSL2(Ubuntu LTS 20.04)
* Docker Desktop

## 準備
* Docker Desktopの立ち上げ
* WSLの起動

### サービス構築手順
以下のコマンドは全てWSLのホームディレクトリ直下から実行する.

```
# 演習リポジトリのクローン
git clone https://github.com/ryuki999/exercises-k8s.git

minikube start
kubectl apply -f replicaset.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml

# minikubeのコンテナに対してトンネルを通して接続(NordPortを使用しても必要)
minikube service myapp --url
```

最後に、出力されたIPアドレス:ポート番号にアクセスすると、Webサイトが立ち上がる。
IPアドレス例)127.0.0.1:31406