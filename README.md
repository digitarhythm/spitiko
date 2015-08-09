# spitiko

シェルスクリプトをインストールします。

・PHP5  
・GnuPG  
・SQLite3  

が必要です。  
GnuPGと、SQLite3をPHPから使えるようになっている必要があります。  
事前準備として、私のGnuPG公開鍵「AF8C0606」をインストールする必要があります。  

\# gpg --keyserver pgp.nic.ad.jp --recv AF8C0606  

で、インストール出来ます。

今のところ、バージョンチェックなどはしていないので、すでにインストールしてあるスクリプトを再インストールすると、上書きされます。

## 使い方

$ spitiko update  
インストールする事が出来るスクリプトのデータベースを更新します。

$ spitiko search [string]  
指定した文字列で、スクリプト名と説明を検索して、ヒットしたものを表示します。

$ spitiko install [script name]  
指定したスクリプトをインストールします。

## インストールされるスクリプト
コマンドの初回実行時に、

~/.spitiko
~/.spitiko/script.d

のディレクトリと、

~/.spitiko/spitikopackage.db

が作成されます。
SQLite3を使って、このDBファイルにインストールすることが出来るスクリプトの情報を保存します。

「~/.spitiko/script.d」にパスを通しておくと、インストールしたスクリプトをすぐに使うことが出来ます。

