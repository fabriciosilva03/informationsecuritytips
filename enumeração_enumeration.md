## MENU

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumera%C3%A7%C3%A3o-enumeration">Enumeração - Enumeration </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-http"> Enumerando HTTP </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#como-fazer"> Como fazer </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-https"> Enumerando HTTPs  </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#identificando-web-application-firewalls"> Identificando web application firewalls </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-ftp"> Enumerando FTP </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#interagindo-com-ftp-python">Interagindo com FTP python  </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#introdu%C3%A7%C3%A3o-netbiossmb">Introdução Netbios e SMB  </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-netbiossmb-no-windows"> Enumerando-netbios smb no windows </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#trick-brute-force-via-prompt-do-windows">Trick brute force via prompt do windows</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-netbiossmb-via-linux">Enumerando netbiossmb via linux</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-com-rpc">Enumerando com RPC </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#automatizando-a-enumera%C3%A7%C3%A3o-netbiossmb"> Automatizando a enumeração Netbios SMB </a> 

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#scripts-para-enumera%C3%A7%C3%A3o-netbiossmb">Scripts para enumeração Netbios SMB</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-pop3">enumerando pop3</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-smtp">Enumerando smtp</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#criando-um-script-para-enumerar-smtp">Criando um script para enumerar smtp</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#criando-um-script-para-brute-force-smtp">Criando um script para brute force smtp</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-dispositivos-de-rede">Enumerando dispositivos de rede</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#protocolos-seguros-x-inseguros">Protocolos seguros x inseguros</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-ssh">Enumerando ssh</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#autentica%C3%A7%C3%A3o-com-chave-p%C3%BAblica">Autenticação com chave publica</a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-network-file-system"> Enumerando network file system </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-snmp"> Enumerando snmp </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#alterando-informa%C3%A7%C3%B5es-via-snmp"> Alterando informações via snmp </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-mysql"> Enumerando mysql </a>



## 

## Enumeração (Enumeration)

- Identificar detalhes do serviço em execução.
- Coletar mais informações do host.
- As informações complementares podem ajudar nas fases de exploração.
- A versão indentificada pode ter uma vulnerabilidade conhecida (Exploits Público).
- Alguns serviços podem ser vulneráveis a ataques de força bruta.

1. Identificar detalhes do serviço em execução
2. Estudar o serviço/protocolo para enteder o funcionamento
3. Tentar interagir com o serviço/protocolo afim obter mais informações do host
4. Indentificar possíveis vulnerabilidades/vetores de ataque.


## Enumerando HTTP

**O que buscamos:**

- Versões do Web Server(IIS, Apache, Nginx, etc.)
- Tecnologias utilizadas(PHP, ASP, JSP, etc.)
- Métodos aceitos(PUT,POST,DELETE, etc.)


## Como Fazer?

- Portas comuns: 80,8080,81,8081
- Versões do protocolo: HTTP/1.0 | HTTP/1.1
- Requisição: GET | HEAD | OTPTIONS
- Utilitários: nc | curl | telnet

Exemplo 01:

`nc -v site.com.br 80
HEAD / HTTP/1.0
`

Exemplo 02:

`nc -v site.com.br 80
GET / HTTP/1.1
Host: site.com.br
`
Exemplo 03 - Indenticiando a versão da liguagem utilizada:

`nc -v site.com.br 80
GET /index.aspx HTTP/1.0
`

## Enumerando HTTPs

Exemplo 01:

`openssl s_client -connet site.com:443
HEAD / HTTP/1.1
Host: site.com.br
`
*Obs: Ao setar a porta que há cripritográfia na comunicação utilize HTTP/1.1 e defina o Host.*

Exemplo 02:

`openssl s_client -quiet -connet www.site.com:443
HEAD / HTTP/1.1
Host: www.site.com.br
`
*Obs: -quiet oculta mensagens de respostas de toda a execução inicial.*


## Identificando Web Application Firewalls

Exemplo 01

`wafw00f site.com`

*Obs: **wafw00f** - ferramenta utilizada para identificar qual WAF esta sendo utilizado em uma aplicação web.*


## Enumerando FTP

Exemplo 01

`nmap -v -sV -p21,2121 -Pn --open 192.168.0.1 -oG ftp`

Exemplo 02

`nc -vn 192.168.0.1 21`   |   `nc -vn 192.168.0.1 2121`

*Obs: Tente entender como interagir com o protocolo.*

*Usuarios e senhas defaults:*

- anonymous,anonymous
- ftp,ftp

*Obs: Se alguns comandos não estiverem respondendo ao acessar o servidor via ftp, ative o modo **passive**, após fazer o login.*


## Interagindo com FTP (Python)

```
#!/usr/bin/python

import socket

tcp=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
tcp.connect(("192.168.0.1",21))

print ("Connectando ao Servidor...")
banner = tcp.recv(1024)
print (banner)

print ("Enviando usuario...")
tcp.send("USER ftp\r\n")
user = tcp.recv(1024)
print (user)

print ("Enviando senha...")
tcp.send("PASS ftp\r\n")
pw = tcp.recv(1024)
print (pw)

print ("Enviando comando HELP...")
tcp.send("help \r\n")
cmd = tcp.recv(2048)
print (cmd)
```
*Obs: Para executar o script acima utilize o python e não o python3*

## Introdução: NetBIOS/SMB

*Serviço que permite compartilhamento de arquivos e diretorios*

- NetBIOS - 139 (TCP)
- SMB - 445 (TCP)
- Null Session - Sessão criada sem autenticação de usuário e senha (nulos)
- IPC$ - Permite que usuários anônimos executem determinadas atividades

## Enumerando NetBIOS/SMB no Windows

NMAP

`nmap -v -sV -p139,445 -Pn --open 192.168.0.0/24`

WINDOWS - CMD

Helpe

`nbtstat`

Obtendo informações do host, como nome e qual grupo ele pertence

`nbtstat -A 192.168.0.1`

Tentando visualizar informações da maquina

`net view \\192.168.0.1`

Estabelecendo sessão nula (Null Session)

`net use \\192.168.0.1 "" /u:""`

Estabelecendo sessão com usuario e senha, caso você tenha uma credencial

`net use \\192.168.0.1 "senha" /u:"usuario"`

Obtendo informações do cahe apos ja ter tido exito ao acessar algum host

`nbtstat -c`

Se conectando a um diretorio disponivel 

`net use h: \\192.168.0.1\diretorio`

Listando arquivos do diretorio conectado

`net use`

Desmontando um mapeamento

`net use h: /delete`

Deletando uma conexão estabelecida

`net use \\192.168.0.1 /delete`

## Trick: Brute Force via prompt do Windows

**senhas.txt** = 
123456
rede
admin
network
password
Rede123

**nome_usuario** = rafaela

CMD

Exemplo de brute force 01:

`for /f %i in (senha.txt) do net use \\192.168.0.14 %i /u:nome_usuario`

Exemplo de brute force 02:

**users_senhas.txt** =

admin 123456

rafaela Rede123

`for /f "tokens=1,2" %i in (senha.txt) do net use \\192.168.0.14 %j /u:%i`

## Enumerando NetBIOS/SMB via Linux

Indentificando hosts que possuem tais portas abertas com NMAP

`nmap -v -sV -p139,445 -Pn --open 192.168.0.0/24`

Scanneando com o NBTSCAN

`nbtscan -r 192.168.0.0/24`

Scanneando um host especifico com o SMBCLIENT

`smbclient -L \\192.168.0.1`

Interagindo com a sessão via Session Null

`smbclient -L \\192.168.0.1 -N`

Definindo apenas o nome de usuario

`smbclient -L \\192.168.0.1 -N -U nome_usuario`

Se conectando com um diretorio localizado

`smbclient //192.168.0.1/diretorio -N`

**CASO TENHA ALGUM PROBLEMA AO EXECUTAR OS COMANDO ACIMA FIQUE ATENTO A VERSÃO DO SOFTWARE.**

*Algumas soluções, seria acresentar mais alguns parâmentros:*

` smbclient -L \\192.168.0.1 -N --option='client min protocol=NT1'`

## Enumerando com RPC

Acessando manual

`man rpcclient`

`rṕcclient --help`

Se conectando

`rpcclient -U "" -N 192.168.0.1`

Dicas de comandos

`?`

Listando usuario da maquina

`enumdomusers`

Obtendo informações de um usuário especifico

`queryuser root`

Listando compartilhamentos da maquina acessada

`netshareenum`

Conectando utilziando um usurio especifico

`rpcclient -U "nome_usuario" 192.168.0.1`

Conectando utilziando um usurio e senha

`rpcclient -U "nome_usuario" 192.168.0.1 -p "senha" ` 


## Automatizando a enumeração NetBIOS/SMB

Ferramenta de automatização de enumeração

`enum4linux`

Obtendo o maximo de informação

`enum4linux -A 192.168.0.1`

Utilizando a ferramenta para trazer informações dos usuarios

`enum4linux -U 192.168.0.1`

Obtendo informações de compartilhamento

`enum4linux -S 192.168.0.1`


## Scripts para enumeração NetBIOS/SMB

Listando scripts do NMAP especificos para SMB

`ls /usr/share/nmap/scripts/smb`

Executando script para identificar o Sistema Operacional

`nmap -v --script=smb-os-discovery 192.168.0.1`

Executando script ṕara identificar se o host possui vulnerabilidade aos scripts executados.

`nmap -v --script=smb-vuln-ms* 192.168.0.1`


## Enumerando POP3

*Porta default = 110*

NMAP

Analisando um range de IPs

`nmap --open -sS -p 110 -Pn 192.168.0.0/24`

Analisando um IP especifico

`nmap --open -sS -p 110 -Pn 192.168.0.1`

Tentando obter o banner com NETCAT

`nc -v 192.168.0.1 110`

Se conectando via TELNET

`telnet 192.168.0.1 110
USER admin
PASS admin
`


## Enumerando SMTP

*Porta default = 25*

NMAP

`nmap --open -sS -p 25 -Pn 192.168.0/24`

ou 

`nmap --open -sS -p 25 -Pn 192.168.0.1`

Tentando obter o banner com NETCAT e interagir com a porta

`nc -v 192.168.0.1 25`

Apos se conectar o serviço você pode utilizar o comando abaixo para identificar se o usuario existe:

`VRFY nome_usuario`

Enviando e-mail com o NETCAT

`
nc -v 192.168.0.1 25
mail from: nome_usuario
rcpt to: usuario_destion
DATA
mensagem...
.
`

## Criando um script para enumerar SMTP

```
#!/usr/bin/python
import socket,sys

if len(sys.argv) !=3:
	print "Modo de uso: python smtpenum.py IP usuario"
	sys.exit(0)

tcp = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
tcp.connect((sys.argv[1],25))

banner = tcp.recv(1024)
print banner

tcp.send("VRFY "+sys.argv[2]+"\r\n")
user = tcp.recv(1024)
print user
```


## Criando um script para brute force SMTP

```
#!/usr/bin/python
import socket,sys,re

file = open("lista.txt")
for linha in file:
	tcp = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
	tcp.connect((sys.argv[1],25))
	banner = tcp.recv(1024)
	tcp.send("VRFY "+linha)
	user = tcp.recv(1024)
	if re.search("252", user):
		print "Usuario encontrado: "+user.strip("252 2.0.0")
```


## Enumerando dispositivos de rede

*Obs: Para enumerar dispositivos o ideal é analisar se ha telnet habilitado.*

*Porta padrão: 23*

**Testar autenticação default:**

https://cirt.net/passwords

https://datarecovery.com/rd/default-passwords

*CONSULTAR O MANUL DO FABRICANTE.*

NMAP

Analisando um range de IPs

`nmap --open -sS -p 23 -Pn 192.168.0.0/24`


## Protocolos Seguros X Inseguros

*Obs: A principal diferença é que um protocolo que possui criptografia ele é mais seguro do que aquele que não possui.*


## Enumerando SSH

*Porta padrão: 22*

Comando para obter o banner 

`nc 192.168.0.1 22`

Metodos de autenticação 

`ssh -v 192.168.0.1`

*Apos inserir o comando acima, observer no final das informações geradas o techo **Authentications that can continue:** , neste trecho sera listada as possiveis formas de autenticação.

**Tipos de autenticação:** Password, Publickey


## Autenticação com chave pública

Local de alteração de configurações do SSH

`nano /etc/ssh/sshd_config`

*Obs: Um dos metodos mais seguros seria deixar habilitado somente autenticação por Publickey.*

Gerenado uma chave publica:

1. `ssh-keygen`
2. Defina o local de armazenamento da chave
3. Digite um senha para ser armazenada na chave
4. Listando as chaves criadas `ls id*`
5. Copie os dados da chave com extenção **.pub**
6. Adicione a copia da chave no servidor e no diretorio especifico **/.ssh/authorized_keys** 
7. `ssh-add id_rsa` - comando para autorizar o uso da chave, comando digitado em sua maquina e não no servidor.

## Enumerando Network File System
- Protocolo de compartilhamento de diretorios no linux

*Porta padrão: 2049*

Enumerando:

Range de IPs

`nmap --open -sS -p 2049 -Pn 192.168.0.0/24`

Indentificando versoes suportadas

`rpcinfo -p 192.168.0.1 | grep nfs`

Listando diretorios exportados - compartilhamentos disponíveis que possam ser montados.

`showmount -e 192.168.0.1`

Criando diretorio temporario para armazenar o diretorio que sera montado

`mkdir /tmp/nfs`

Montando diretorio

`mount -t nfs -o nfsvers=2 192.168.0.1:/ /tmp/nfs`

Desmontando diretorio

`umount nfs`


## Enumerando SNMP

*Protocolo de gerenciamento de dispositivos de rede.*

- SNMP	-	161 (UDP)

- OID - Object Identifier -	Código dutilizado para identficar os objetos

- MIB - Management Information Base	-	Base contendo informações relacionadas ao gerenciamento de redes

- Community 	-	Valor utilizado entre as partes snmp para troca de informações.

Nivel de acesso (Community)

**RO - Read Only** - Acesso de leitura

**RW - Read Write** - Acesso de leitura / escrita

Exemplos:

Valores MIBS

1.3.6.1.2.1.25.1.6.0	-	Processos do sitema

3.3.6.1.4.1.77.1.2.25	-	Contas de usuários

5.3.6.1.2.1.6.13.1.3	-	Portas TCP

Community

public 	- manager

private - access

cisco 	- secret


**Referências:**

https://www.alvestrand.no/objectid/1.3.6.1.html

http://www.oid-info.com/


Scan com NMAP

`nmap -sVU -p161 -Pn 192.168.0.1 192.168.0.247`

Scan com ONESIXTYONE

comu.txt =

public 

private

cisco

manager

juniper

`onesixtyone -c comu.txt 192.168.0/24` 

enumerando um host especifico com SNMPWALK para listar todos os usuarios

`snmpwalk -c public -v1 192.168.0.1 1.3.6.1.4.1.77.1.2.25` 

ou 

`snmpwalk -c public -v1 192.168.0.1` 

Buscando pacote para traduzir MIBs

`apt search mibs`

Instalando 

`apt install snmp-mibs-downloader`

Configurando 

`echo "" > /etc/snmp/snmp.conf`

Exemplo

`snmpwalk -c public  -v1 192.168.0.1 SNMPv2-MIB::sysUpTime`

SNMPTTRANSLATE - Contem a traduçãode diversos codigos bin

Exemplo 01:

`snmptranslate -IR sysUpTime`

Exemplo 02:

`snmptranslate -Td SNMPv2-MIB::sysUpTime`

Exemplo 03:

`snmptranslate -TB icmp`


## Alterando informações via SNMP

Enumerando

`snmp-check 192.168.0.1 -c public `

Setando configurações com SNMPSET

`snmpset -c manager -v1 192.168.0.1 SNMPv2-MIB::sysContact.0 s "Novo_valor"`


## Enumerando MySQL

*Porta padrão: 3306*

Varrendo a rede 

`nmap --open -sS -p 3306 -Pn 192.168.0.0/24`

Conectando ao host encontrado

`mysql -h 192.168.0.1 -u mysql`















