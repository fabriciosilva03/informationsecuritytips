## Introdução ao Scapy

Manual do scapy

`man scapy`

Executando o scapy

`scapy`

Liscatar comando 

`lsc()`

Entendendo como o comando funciona

`help(sr)`

Listando todos os protocolos que são suportados

`ls()`

Detalhes de um protocolo

`ls(IP)`

## Manipulando pacotes de rede

Criando pacote:

`pIP = IP(dst="192.168.0.1")`

Checando como esta ficando o pacote:

`pIP.show()`

ou

`pIP.summary()`

Montando TCP

`pTCP = TCP(dport=80,flags="S")`

Listando dados

`pTCP`

ou

`pTCP.show()`

Altenrando a porta de origem

`pTCP.sport=43778`

Encapsulando pacote TCP no IP

`pacote = pIP/pTCP`

Listando:

`pacote`

ou 

`pacote.show()`

Enviando pacote

`sr1(pacote)`

Armazendo dados de reposta

`resposta=sr1(pacote)`

Listado dados da resposta

`resposta.show()`

ou 

`resposta.summary()`

Armazendo em reposta somente detalhes especificos

`reposta[IP].dst`

Criando pacote com varias portas de destino:

`pTCP=TCP(dport=[80,443,8080])`

Encapsulando pacaote

`pacote=pIP/pTCP`

Enviando e recebendo resposta

`sr(pacote)`

Criando variaveis para armazenar resposta diferentes:

`resp, noresp = sr(pacote)`

Listando detalhes da reposta

`resp.summary`

ou

`resp.show`

## Criando pacotes ICMP e payloads

Enviando pacote ICMP

`pacote = pIP/ICMP()`

Enviando pacote

`resposta = sr1(pacote)`

Enviando payload com ICMP

`pacote = pIP/ICMP()/"PAYLOAD"`

Enviando pacote

`resposta = sr1(pacote)`

Enviando payload com TCP

`pacote = pIP/TCP()/"PAYLOAD"`


## Criando um portscan com Scapy com python

Scan Simples

`nano scanscapy.py`

```
#!/usr/bin/python
import sys
from scapy.all import *

conf.verb =  0

portas = [21,22,23,25,80,443,110]

pIP = IP(dst=sys.argv[1])
pTCP = TCP(dport=portas,flags="S")
pacote = pIP/pTCP
resp, noresp = sr(pacote)
resp.show()
```

Scan mais detalho

```
#!/usr/bin/python
import sys
from scapy.all import *

conf.verb =  0

portas = [21,22,23,25,80,443,110]

pIP = IP(dst=sys.argv[1])
pTCP = TCP(dport=portas,flags="S")
pacote = pIP/pTCP
resp, noresp = sr(pacote)
#resp.show()

#Lendo todas as respostas

for resposta in resp:
	porta = resposta[1][TCP].sport
	flag = resposta[1][TCP].flags
	print ("%d %s"  %(porta,flag))


#Analisando um unico pacote de envio
#print resp[0][0].show

#Analisando pacote de resposta
#print resp[0][1].show

#Porta de orgigem
#print resp[0][1][TCP].sport

#Flags
#print resp[0][1][TCP].flags
```

Escan mais detalhado e filtrado

```
#!/usr/bin/python
import sys
from scapy.all import *

conf.verb =  0

portas = [21,22,23,25,80,443,110]

pIP = IP(dst=sys.argv[1])
pTCP = TCP(dport=portas,flags="S")
pacote = pIP/pTCP
resp, noresp = sr(pacote)
#resp.show()

#Lendo todas as respostas

for resposta in resp:
	porta = resposta[1][TCP].sport
	flag = resposta[1][TCP].flags
#	print ("%d %s"  %(porta,flag))
	if (flag == "SA"):
		print ("Porta %d ABERTA" %(porta))


#Analisando um unico pacote de envio
#print resp[0][0].show

#Analisando pacote de resposta
#print resp[0][1].show

#Porta de orgigem
#print resp[0][1][TCP].sport

#Flags
#print resp[0][1][TCP].flags
```









