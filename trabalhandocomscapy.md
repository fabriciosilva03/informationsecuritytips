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







