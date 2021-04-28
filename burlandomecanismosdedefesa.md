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

Instalando Ferramenta:

`apt install snort`

Listando as regras que o SNORT possui:

`cd /etc/snort/rules`

`ls`

*Obs: É possivel alimentar as regras disponiveis, baixar novas regras ou criar suas proprias regras.*

Exemplo de uso:

Implementando regra:

`snort -A fast -q -h 192.168.0.0/24 -c snort.conf`

Monitorando:

`tail -f alert`

Localização dos logs salvos:

`cd /var/log/snort`

Comando para acompanhar de forma direta tudo que esta acontencendo na maquina que possui o IDS instaldo:

`snort -A console -q -h 192.168.0/24 -c snort.conf`

## Entendendo e criando regras de IDS

Exemplo de regra simples:

Criando o arquivo

`nano novasregras.rules`

*Obs: O arquivo criado deve ser armazenado ou criado de forma direta dentro do diretorio /etc/snort/rules.*

Implementando regras

*Regra 01:*

`alert tcp any any -> 192.168.0.1 any (msg: "Port Scannning"; sid:1000001; rev:001;)`

*Regra 02:*

`alert tcp any any -> 192.168.0.1 22 (msg: "Pacote SYN enviado ao SSH"; flags:S;sid:1000002; rev:001;)`

*Regra 03:*

`alert tcp any any -> 192.168.0.1 80 (msg: "Acesso ao arquivo robots.txt";content:"robots.txt";sid:1000003; rev:001;)`

*Regra 04:*

`alert tcp any any -> 192.168.0.1 80 (msg: "Possivel ataque SqlInjection";content:"%27";sid:1000004; rev:001;)`

*Obs: Apos criar sua regra personalizada, vocẽ deve incluir a mesma no snort.conf.*

Atulizando listas de regras

` nano /etc/snort/snort.conf`

Incluindo a nova regra criada

` include $RULE_PATH/novasregras.rules `

























