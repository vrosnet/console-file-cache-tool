# console-file-cache-tool
コマンドラインからシステムファイルキャッシュサイズを操作するためのプログラムです。

About
-----
Windows Server 2008 R2 SP1よりも前のバージョンでは，[システムファイルキャッシュが物理メモリの大部分を占有](http://support.microsoft.com/kb/976618)してしまい，アプリケーションのパフォーマンスに深刻な影響を及ぼすことがあります。

特に32ビット版のWindowsでは，たとえマシンに潤沢なメモリが搭載されていたとしても，アドレス範囲に限界があるため，問題はより深刻です。

**たとえば，おおきな4Dデータベースの変換が完了できないかもしれません。**

問題を回避するためには，[SetSystemFileCacheSize](http://msdn.microsoft.com/en-us/library/aa965240(VS.85).aspx)を使用し，システムファイルキャッシュが占有できるメモリに制限を設けることが提案されています。

このコマンドラインプログラムは，システムファイルキャッシュのサイズ制限を読み書きするためのものです。

**注記**

この問題は，Windows Server 2008 R2 SP1で改善されました。また，Windows 7およびWindows 2008 R2には，[修正プログラム](http://support.microsoft.com/kb/979149)が存在します。

プログラムは，おもにWindows Server 2008 R2 SP1よりも前のバージョンでデータベースのようなおおきなファイルを使用しており，上述したような問題に遭遇している人を対象にしています。

**関連記事**
http://blogs.technet.com/b/askcorejp/archive/2009/12/29/1-64bit.aspx

Example
-------
コマンドプロンプト（windows/system32/cmd.exe）に対するショートカットをデスクトップなどに作成します。

作成したショートカットを右クリックし，『管理者として実行』します。

コマンドプロンプトより，file_cache_toolを実行します。

**オプション**
* -m 最大値を設定する（ある程度のサイズでないと87エラーが返されます。）
* -n 最小値を設定する（0はデフォルト値になります。）
* -i 現在の値を確認することができます
* -l システムファイルキャッシュのフラッシュを実行します

![](images/1.png)

