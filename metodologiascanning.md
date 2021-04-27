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

Scanneando hosts:

`namp -v -sn 192.168.0.0/24 -oG`




## DESAFIOS

- Tempo de scan e consumo do tráfego na rede
- Firewall filtrando/rejeitando pacotes
- Bloqueio de PortScan
- Sistemas de detecção e prevenção de intrusos (IDS/IPS) 




