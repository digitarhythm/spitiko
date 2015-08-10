#シェルスクリプトをインストールするためのスクリプト

**spitiko**を使うためには、  

0. PHP5
0. GnuPG
0. SQLite3
0. json_decode

が必要です。
GnuPGと、SQLite3をPHPから使えるようになっている必要があります。
事前準備として、私のGnuPG公開鍵「AF8C0606」をインストールする必要があります。

**\# gpg --keyserver pgp.nic.ad.jp --recv AF8C0606**

で、インストール出来ます。
とりあえずは、GnuPGのセットアップが必要です。

今のところ、バージョンチェックなどはしていないので、すでにインストールしてあるスクリプトを再インストールすると、上書きされます。

#インストールされるスクリプト

コマンドの初回実行時に、

**~/.spitiko**  
**~/.spitiko/script.d**

のディレクトリと、

**~/.spitiko/spitikopackage.db**

が作成されます。 SQLite3を使って、このDBファイルにインストールすることが出来るスクリプトの情報を保存します。

「**~/.spitiko/script.d**」にパスを通しておくと、インストールしたスクリプトをすぐに使うことが出来ます。

#使い方

**$ spitiko update**  
インストールする事が出来るスクリプトのデータベースを更新します。

**$ spitiko search [string]**  
指定した文字列で、スクリプト名と説明を検索して、ヒットしたものを表示します。  
環境変数「SPITIKO_SH」に、検索対象のシェルの名前を入れておくと、そのシェル用のスクリプトがフィルタリングされます。  
例）export SPITIKO_SH="zsh"  
なにも指定が無い場合は「bash」が使用されます。

**$ spitiko install [script name]**  
指定したスクリプトをインストールします。

