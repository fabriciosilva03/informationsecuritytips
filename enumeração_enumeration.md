##

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumera%C3%A7%C3%A3o-enumeration">Enumeração - Enuumeration </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-http"> Enumerando HTTP </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#como-fazer"> Como fazer </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-https"> Enumerando HTTPs  </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#identificando-web-application-firewalls"> Identificando web application firewalls </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-ftp"> Enumerando FTP </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#interagindo-com-ftp-python">Interagindo com FTP python  </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#introdu%C3%A7%C3%A3o-netbiossmb">Introdução Netbios e SMB  </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/enumera%C3%A7%C3%A3o_enumeration.md#enumerando-netbiossmb-no-windows"> Enumerando-netbios smb no windows </a>

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

## Introdução: NetBIOS/SMB

*Serviço que permite compartilhamento de arquivos e diretorios*

- NetBIOS - 139 (TCP)
- SMB - 445 (TCP)
- Null Session - Sessão criada sem autenticação de usuário e senha (nulos)
- IPC$ - Permite que usuários anônimos executem determinadas atividades

## Enumerando NetBIOS/SMB no Windows

NMAP

`nmap -v -sV -p139,445 -Pn --open 192.168.0.1/24`

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
















