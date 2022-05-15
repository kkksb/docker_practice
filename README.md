# 概要

Dockerの練習
一通りのLAMP環境を作れるようにする。

## 環境

Windows
Docker Desktop for Windows

## 教科書

Docker入門

## Dockerfileからapache tomcatをbuildする練習

rootディレクトリの中身を使ってbuildする。

```
$ docker build -t apache-image .
```

### ボリュームの作り方

```
$ docker run -v apachelog-volume:/usr/local/apache2/logs --name=apachelog-container busybox
```

### コンテナbuild

```
$ docker run --volumes-from apachelog-container -p 80:80 -d --name=apache-container apache-image
```

### log出力を確認する一時コンテナの起動

```
$ docker run --rm --volumes-from apachelog-container -it ubuntu /bin/bash
```