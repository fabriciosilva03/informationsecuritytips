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





