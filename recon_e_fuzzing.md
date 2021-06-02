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

**Content Discovery**

- github.com/projectdiscovery/httpx
- github.com/michenriksen/aquatone
- github.com/m4ll0k/SecretFinder

*Obs: Para executar binarios de qualquer parte do seu sistema, basta mover a sua aplicação baixada para pasta bin.*

Ex:

`sudo mv httpx /bin/`

Caso o binario gau esteja dando problema ao executar apos ser exportado para /bin siga os passos abaixo.

Acesse o .zshrc

`nano /home/john/.zshrc`

E coloque # ao lado do pluguin do git

#plugins=(git)





