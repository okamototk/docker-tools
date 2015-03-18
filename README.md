Docker Tools
------------

Dockerを利用する上でなくても困らないけどあると便利かもしれない個人的なスクリプト置き場です。

ライセンスは適当に使っていただいて構いませんが無保証です。

## docker-expose-port

Dockerコンテナのポート設定はコンテナ起動時にしか行えません。
docker-expose-portはコンテナ起動後にポート設定を行うツールです。
下記のコマンドで実行します。

  # docker-expose-port [-d] <コンテナID> <ホストポート>:<コンテナポート>

-dオプションは公開したポートを削除するオプションです。例えば、sshポートの
公開は、次のように実行することができます。

  # docker-expose-port mycontainer  2022:22

ポートを閉じたいときは、上記のコマンドに-dを付けて実行します。

  # docker-expose-port -d mycontainer  2022:22

## docker-cd

ホスト上にあるDockerコンテナのルートディレクトリに移動するコマンドです。多分、Ubuntuでしか動きません。
 

  # docker-cd <コンテナ名>

で実行することができます。実行すると、次のようになります。

  root@docker:~# docker-cd mycontainer
  root@docker:/var/lib/docker/aufs/mnt/a7b2c8b54355b7236540c8e58b6ca6606f0a1cf26ecc6dd7ce3fcf2f4726cca9#
