## Bypass Firewall

Scaneando host definindo uma porta de origem, se o firewall não estiver bem configurado é possivel ver grande parte dos serviços que estão em execução.

`nmap -v -sS -Pn -g 53 192.168.0.1`

*Obs: Caso acha regra de firewal e no caso há uma possivel aplicação web em execução so será possivel acessa se você definir uma porta de origem.*

Acessando via NetCat definindo uma portade origem:

`nc -vn -p 53 192.168.0.1 8180
HEAD / HTTP/1.0
`
Capturando toda a pagina que esta com bloqeio de firewall para indentificar detalhes da aplicação web

`nc -vn -p 53 192.168.0.1 8180 > /var/www/html/recon.html
GET / HTTP/1.0
`
## IDS - Sistema de Detecção de Intrusos












