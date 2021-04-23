## BASH SCRIPTING - LINUX

PortScan: 

```
#!/bin/bash

#Scaneado de portas.

if ["1$" == ""]
	then
    
    #echo "Digite o argumento conforme o exemplo:"
		#echo "Exemplo:" 
    #echo "./script 192.168.0.1"
    
	else
		for p in {1..100};do
		hping3 -S -p $p $1 -c 1 | grep "SA" | grep -v "RA" >> list_port
		clear
		cat list_port		
		
done
fi
```

Scaneamento de Subdominios:

```
#!/bin/bash
    
    #echo "Digite o argumento conforme o exemplo:"
		#echo "Exemplo:" 
    #echo "./script 192.168.0.1"

if ["1$" == ""]
	then
		echo "Digite o argumento de forma correta"
	else
		wget $1 
		clear
	cat index.html | grep "http" | cut -d "/" -f 3 | cut -d '"' -f 1 > lista
	while read line; do 
	host  "$line"; 
	done < lista	
	rm -f index.html

fi

```

Scanner files

```
if ["1$" == ""]
        then
		#Realize busca por pdf dentro de sites de forma automatizada.

                echo "Digite o argumento de forma correta:"
		echo "Exemplo:"
		echo "./script site.com"
	else
		lynx --dump "https://google.com/search?&q=site:$1+ext:pdf" | grep ".pdf" | cut -d "=" -f2 | egrep -v "site|google" | sed 's/...$//' > resbusca

		for url in $(cat resbusca);do wget -q $url;done

		exiftool *.pdf

		rm -rf *.pdf

fi
```

Script de transferência de zone

```
#!/bin/bash

#Script para transferencia de zona

# Forma de uso:
# ./script site.com.br

for server in $(host -t ns $1 | cut -d " " -f 4);
do
host -l -a $1 $server
done
```

Script para Pesquisa Reversa (DNS)
```
#!/bin/bash

#Script para pesquisa reversa de DNS

#Forma de uso
#./script 192.168.0

for ip in $(seq 224 239);do
host -t ptr $1.$ip | grep -v "$1" | cut -d " " -f 5
done
```

Script para subdomain takeover

```
#!/bin/bash

#Script para para subdomain takeover

#Forma de uso
#./script site.com.br

for palavra in $(cat lista.txt);do
host -t cname $palavra.$1 | grep "alias for"
done

```

Script para recon de websites e encotrar diretorios e extenções predefinidas.

```
#!/bin/bash

#Script para recon de websites e encotrar diretorios e extenções predefinidas.
#Exemplo de uso
#./script site.com.br ou ./script site.com.br php

echo "___________________________________________________"
echo "DIRETORIOS ENCONTRADOS:"
echo "___________________________________________________"

for palavra in $(cat lista2.txt)
do

resposta=$(curl -s -H "User-Agent: Firefox" -o /dev/null -w "%{http_code}" $1/$palavra/)

if [ $resposta == "200" ]
then

echo "$1/$palavra"

fi
done

echo "___________________________________________________"
echo "ARQUIVOS $2 ENCONTRADOS:"
echo "___________________________________________________"

for palavra in $(cat lista2.txt)
do

resposta2=$(curl -s -H "User-Agent: Firefox" -o /dev/null -w "%{http_code}" $1/$palavra.$2)

if [ $resposta2 == "200" ]
then

echo "$1/$palavra.$2"

fi
done

```


## POWER SHELL

PortScan

```
param($ip)
if(!$ip){
    echo "DESEC SECURITY - PORTSCAN"
    echo "Exemplo de uso:"
    echo "\.portscan.ps1 192.168.0.1"
} else {
$topports = 21,22,3306,80,443
try{foreach ($porta in $topports){
if (Test-NetConnection $ip -Port $porta -WarningAction SilentlyContinue -InformationLevel Quiet){
    echo "Porta $porta Aberta"
}} else {
    echo "Porta $porta Fechada"
}} catch {}
}

```
Analise Web

```
$web = Invoke-WebRequest -uri "http://www.businesscorp.com.br" -Method Options
echo " O Servidor roda: "
$web.headers.server
echo ""
echo "O servidor aceita os metodos: "
$web.headers.allow
echo ""
echo "Links econtrados: "
$web2 = Invoke-WebRequest -uri "http://www.businesscorp.com.br"
$web2.links.href | Select-String http://
```

## LINGUAGEM C

PortScan
```
#include <stdio.h>
#include <sys/socket.h>
#include <netdb.h>

int main(int argc, char *argv[]){

	int meusocket;
	int conecta;

	int porta;
	int inicio= 0;
	int final = 65535;
	char *destino;
	destino = argv[1];

	struct sockaddr_in alvo;

	for(porta=inicio;porta<final;porta++){

	meusocket = socket(AF_INET, SOCK_STREAM,0);
	alvo.sin_family = AF_INET;
	alvo.sin_port = htons(porta);
	alvo.sin_addr.s_addr = inet_addr(destino);

	conecta = connect(meusocket, (struct scokaddr *)&alvo, sizeof alvo);

	if(conecta == 0){
		printf("Porta %d - status [ABERTA] \n", porta);
		close(meusocket);
		close(conecta);
	}else{
		close(meusocket);
		close(conecta);
	}
	}
}

```

Resolver:

```
#include <stdio.h>
#include <netdb.h>
#include <arpa/inet.h>

int main(int argc, char *argv[]){

	if(argc <= 1){
		printf("Modo de uso: ./ resolver www.businescorp.com.br\n");
		return 0;
	}else{
		struct hostent *alvo = gethostbyname(argv[1]);
		if (alvo == NULL){
			printf("Ocorreu um erro :( \n");
		}else{
			printf("IP: %s\n", inet_ntoa(*((struct in_addr *)alvo->h_addr)));
		}
}
}

```


## PYTHON

PortScan:
```
#!/usr/bin/python
import socket, sys

for porta in range(1,65535):
	meusocket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
	if meusocket.connect_ex((sys.argv[1],porta)) == 0:
		print "Porta", porta, "[ABERTA]"
		meusocket.close()
```

Resolver:

```
import socket,sys

host = sys.argv[1]

print host,"--->", socket.gethostbyname(host)
```
