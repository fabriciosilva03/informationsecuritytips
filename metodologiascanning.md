## TCP HOST SCAN
- INDENTIFICAR TODOAS AS PORTAS ABERTAS (PROTOCOLO TCP)

Scan normal:

`nmap -v -sS -Pn 192.168.0.1`

Scan em todas as portas (*Mais eficiente):

`nmap -v -sS -p- -Pn 192.168.0.1`




## UDP HOST SCAN
- INDENTIFICAR TODAS AS PORTAS ABERTAS (PROTOCOLO UDP)

**Obs:**

*Porta Aberta - Sem resposta*

*Porta Fechada - Port Unreachable*

*Porta com filtro de firewall em drop - Sem resposta*

*Porta com filtro de firewall em reject - Port Unreachable*

Scanneando host

`nmap -sU -Pn 192.168.0.1`

Analisando porta especifica:

`hping3 --udp -p 69 -c 1 192.168.0.1`

`nmap -sU -p 69 -Pn 192.168.0.1`

Se conectando no serviço para saber se ele realmente esta ativo:

`nmap -sUV -p 69 192.168.0.1`

*Obs: Sempre que for fazer um scanner UDP faça essa teste de se conectar no serviço para saber se realmente a porta esta aberta.*


## NETWORK SWEEPING
- INDENTIFICAR PORTAS ABERTAS NA REDE OTIMIZANDO A BUSCA

Scanneamento para identificar hosts ativos:

`namp -v -sn 192.168.0.0/24 -oG ativos.txt`

Filtrando dados coletados:

`greep "Up" ativos.txt | cut -d " " -f 2 > hosts`

Scanneando somente os host coletados e indentificando se os mesmos possuem um porta especifica ativa.

`nmap -sS -p 80 --open -Pn -iL hosts`

Scannenado e coletando o banner:

`nmap -sSV -p 80 --open -Pn -iL hosts -oG web.txt`

Scannenado todas as portas que utilizam o HTTP:

`nmap -sS -p http* --open -Pn -iL hosts`


## Identificando Serviços

Comando verificar portas ativas e possiveis serviços que rodan nestas portas de acordo com a tabela padrão.

`nmap -v -sS -Pn 192.168.0.1`

*Obs: Mas para ter certerza sobre se estes serviços correspondem realmente as portas citadas realiza um novo scan com um comando com o NMPA utilizando -sV*

`nmap -v -sV -Pn 192.168.0.1`

*O comando -sV ira tentanr se conectar com o serviço e verificar realemnte os dados do serviço em execução.*


## Estudo técnico: Enganando o Atacante

**Exemplo altenrando o banner do serviço SSH**

Install Bless

`apt install bless`

Localizando sshd

`whereis sshd`

Analisando o binario encontrado

`strings /usr/sbin/sshd`

*Obs: Antes de alterar o banner do serviço faça uma copia de segurança do mesmo.*

`cp /usr/sbin/sshd root/Desktop`

Localizando dados do banner

`strings /usr/sbin/sshd | greep "OpenSSH" `

Abrindo o editor de Hexadeximal para alterar o banner do binario

`bless sshd`




## Listando portas e serviços padrões:

`cat /etc/services`



## DESAFIOS

- Tempo de scan e consumo do tráfego na rede
- Firewall filtrando/rejeitando pacotes
- Bloqueio de PortScan
- Sistemas de detecção e prevenção de intrusos (IDS/IPS) 




