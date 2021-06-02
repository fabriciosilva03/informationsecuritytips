## Recon e Fuzzing

## Subdomain Discovery

- Histórico
- Brute Force
- Certificados e Passivos

Histórico

- securitytrails.com
- subdomainfinder.c99.nl
- web.archive.org
- dnsdumpster.com
- github.com/Screetsec/Sudomy

Brute Force

- github.com/aboul3la/Sublist3r
- github.com/TheRook/subbrute
- github.com/OWASP/Amass

Certificados e Passivos

- github.com/projectdiscovery/subfinder
- github.com/certspotter
- github.com/UnaPibaGeek/ctfr (usa o crt.sh)
- chaos.projectdiscovery.io


Consultando subdomain de forma simples

`host site.com`

Brute force simples de subdomain

`for subdominio in $(cat sub.txt); host "$subdominio.site.com" | grep -v 'NXDOMAIN';`

**ProjectDiscovery - Security Through Intelligent Automation**

https://github.com/projectdiscovery

Subfinder - Uma excelente ferramenta.

Scan de subdomain online

https://chaos.projectdiscovery.io/#/




## Application Discovery

- URL discovery
- Parameter discovery
- Content discovery

**Tools**

- github.com/lc/gau
- github.com/hakluke/hakrawler
- github.com/xmendez/wfuzz
- github.com/ffuf/ffuf
- github.com//maurosoria/dirsearch

**Parameter Discovery**

- github.com/devanshbatham/ParamSpider
- github.com/tomnomnom/gf
- github.com/s0md3v/Parth
- github.com/tomnomnom/hacks/tree/master/kxss

**Content Discovery**

- github.com/projectdiscovery/httpx
- github.com/michenriksen/aquatone
- github.com/m4ll0k/SecretFinder

*Obs: Para executar binarios de qualquer parte do seu sistema, basta mover a sua aplicação baixada para pasta bin.*

Ex:

`sudo mv httpx /bin/`

**Caso o binario gau esteja dando problema ao executar apos ser exportado para /bin siga os passos abaixo.**

Acesse o .zshrc

`nano /home/john/.zshrc`

E coloque # ao lado do pluguin do git

#plugins=(git)


1. Enumernado

subfinder -d site.com -o sub.txt

2. Possui aplicações web?

cat sub.txt | httpx

cat sub.txt | httpx -silent

cat sub.txt | httpx -status-code

cat sub.txt | httpx -status-code -path /admin/

cat sub.txt | httpx -status-code -ports 80,8080,443

3. Identificando subdomains

cat sub.txt | httpx -silent | gau

ou

subfinder -d site.com -silent | httpx -silent | gau

*Obs: -silent é um comando usado para não exibir um banner da aplicação.*




## Parameter Discovery

Buscando parametros de dominios

- github.com/devanshbatham/ParamSpider

Verificando se os parametros são refletidos

- github.com/tomnomnom/hacks/tree/master/kxss




## Content Discovery

Capturando telas e tecnologias utiliadas nos sites listados.

- github.com/michenriksen/aquatone

Exemplo:

subfinder -d site.com -silent | ./aquatone


## Fuzzing de pasta e arquivos (wfuzz, fuff)

**Automation**

- github.com/yogeshojha/rengine
- github.com/edoardottt/scilla
- github.com/kpcyrd/sn0int


**WFUZZ**

https://github.com/xmendez/wfuzz

Pesquisa de arquivos e diretorios

`wfuzz -c -z file,wordlist.txt --hc 404 http://192.168.0.1/FUZZ`

Pesquisa de arquivos e diretorios mais rapido

`wfuzz -t 100 -c -z file,wordlist.txt --hc 404 http://192.168.0.1/FUZZ`




## Fuzzing de parametros (wfuzz, fuff)

Wordlist: 

- SecList --> burp-parameter-names.txt
- SecList --> raft-large-words-lowercase.txt

Exemplo: 

`wfuzz -c -z file,burp-parameter-names.txt --hc 404 http://192.168.0.1/index.php?FUZZ=teste`

Exemplo 02: Filtrando pelo numero de caracteres

`wfuzz -c -z file,burp-parameter-names.txt --hc 404 --hh 3034 http://192.168.0.1/index.php?FUZZ=teste`

Exemplo 03: Fazendo Fuzz no paramentro encontrado

`wfuzz -c -z file,raft-large-words-lowercase.txt  --hc 404 http://192.168.0.1/index.php?search=FUZZ`

Exemplo 04: Filtrando pelo numero de linhas

`wfuzz -c -z file,raft-large-words-lowercase.txt --hc 404  --hl 45 http://192.168.0.1/index.php?search=FUZZ`




## PortScan

**NMAP**

`nmap -Pn -sV 192.168.0.1 -vv`

`nmap -Pn -p- -sV 192.168.0.1 -vv`

`nmap -Pn -p- -sV -A 192.168.0.1 -vv`















