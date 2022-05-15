# 概要

Linuxでdockerを扱うときとの違いを記載

## マウント

```
$ docker run -v c/dev/playground/docker_practice/root/WebContents/:/usr/local/apache2/htdocs/ -p 80:80 -d httpd
```

ホスト側のパスは絶対パス。また、ドライブも設定しないといけない。
Docker Desktopが「Share it」と表示したらマウント成功。