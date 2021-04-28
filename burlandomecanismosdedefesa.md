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

`alert tcp any any -> 192.168.0.1 80 (msg: "Possivel ataque Sql Injection";content:"%27";sid:1000004; rev:001;)`

*Obs: Apos criar sua regra personalizada, vocẽ deve incluir a mesma no snort.conf.*

Atulizando listas de regras

` nano /etc/snort/snort.conf`

Incluindo a nova regra criada

` include $RULE_PATH/novasregras.rules `

## Estudo técnico: Bypass de regras de IDS

Bypass utilizando o PING. 

*Obs: O baypass foi realizado com sucesso pois na regra era esperado um sequencia de hexadeciamal padrão e não um sequencia hexadecimal aleatória.

`ping -c1 -p "6465736563" 192.168.0.1`

Bypass utilizando o HPING. 

`hping3 --icmp -C 8 -K 1 -c 1 192.168.0.1`

*Obs: Para que cada baypass seja bem sucedido é preciso realizar testes e indentificar quais as possiveis regras é utilizada para detectar tais serviços, e com isso o ideal é que seja montado um laboratório ou analisar estudos ja desenvolvidos sobre os princiapis tipos de regras implementadas em IDS.*

## IPS / Bloqueio de Port Scanning

Ferramenta para criar portas falsas **Portsentry*

Intalando PortSentry

`apt install portsentry`

*Obs: A utilização de portas falsas é uma das formas para detectar um atacante, pois caso uma das portas falsas for feita tentativa de acesso é emitido um alerta para a equipe de defesa.*

Localizando dados de configuração do PortSentry

`cd /etc/portsentry`

Acessando arquivo de configuração do PortSentry

`nano portsentry.conf`

*Obs: Ao executar o nmpa e o retorno seja TCPWRAPPED em uma das portas listas, é possivel que esteja habilitados regras de firewall, IDS ou IPS.*

**Observando se algum ip foi bloqueado de acordo com a regra implementada**

`iptables -nL`

`cat /etc/hosts.deny`

*Obs: Quando o sistem bloquear sua tentativa de acesso via scanner ou algo do tipo no meio da execução do script é possivel observar que a mesma para e não conclui todo o processo.*

Tipo de regra que bloqueais até o SynScan

`usr/sbin/portsentry -stcp`


## Bypass IDS/IPS/FW

*Uma tecnica para dar bypass seria mascarar nosso pacote ,em varios tipos de pacotes, utilizar diversos IPs.*


## Evadindo mecanismos de defesa

Exemplo 01:

`nmap -v -sS --top-ports=10 --open -Pn 192.168.0.1`

Exemplo 02 (Utilizando a flag decoi para camuflar meu ip):

`nmap -v -D 10.12.2.34,192.168.0.23,172.16.1.32 -sS --top-ports=10 --open -Pn 192.168.0.1`

Exemplo 02 (Utilizando a flag decoi para camuflar meu ip):

*Obs: Neste exemplo estou camuflando meu IP utilizando 20 IPs falsos.

`nmap -v -D RND:20 -sS --top-ports=10 --open -Pn 192.168.0.1`

Exemplo 02 (Utilizando a flag decoi para camuflar meu ip):

*Obs: Neste exemplo estou camuflando meu IP utilizando 20 IPs falsos e utilizando -sV consigo pegar o banner dos serviços encontrados.

`nmap -v -D RND:20 -sV --top-ports=10 --open -Pn 192.168.0.1`












