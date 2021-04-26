
**TTL (Time to Live)**

- Tempo de vida de um pacote na rede.

- A cada roteador o TTL é decrementado -1.

Exemplo de comando de manipulação de TTL via terminal:

`ping site.com.br -c 1 -t 1 `

Comando para ver toda a rota até o alvo.

`traceroute site.com.br`

Modificando o tempo de espera dos pacotes

`traceroute site.com.br -w 5`

Modificando a quantidade de TTLs

`traceroute site.com.br -m 1`

Estipulando apartir de qual salto desejo acompanhar.

`traceroute site.com.br -m 20 -f 15`

Comando para indentificar o AS de cada salto.

`traceroute site.com.br -A`

Comando que não mostra os Hosts indentificados da rota.

`traceroute site.com.br -n`

*Obs: A lançar o traceroute o mesmo utiliza o protocolo UDP como default e para saber se toda a rota foi completa observe o utilmo salto se corresponde exatamente 
ao IP que vocẽ setou, caso contrario teste o traceroute com outros protocolos para saber qual foi aceito.*

Analisando rota utilizando o protocolo ICMP:

`traceroute site.com.br -n -I`

Analisando rota utilizando o protocolo TCP:

`traceroute site.com.br -n -T`

Analisando rota utilizando o protocolo TCP e uma porta especifica:

`traceroute site.com.br -n -T -p 443`

Analisando rota utilizando o protocolo UDP e a porta 53: *Obs: Utilizando o -U ele seta de forma automatica a porta 53 do protocolo UDP.*

`traceroute site.com.br -n -U `

**Overview sobre Firewall com IPTABLES**

Comando para verificar como esta as regras de firewall

`iptables -nL`

Bloqueando todos as regras de acesso de ENTRADA:

`iptables -P INPUT DROP`

Liberando todas as regras de ENTRADA:

`iptables -P INPUT ACCEPT`

Habilitando somente uma porta especifica:

`iptables -A INPUT -p tcp --dport 80 -j ACCEPT `

Habilitando somente uma porta especifica de origem:

`iptables -A INPUT -p tcp --sport 80 -j ACCEPT `

Habilitando o protocolo ICMP:

`iptables -A INPUT -p icmp -j ACCEPT `

Habilitando somente um porta especifica para um host especifico:

`iptables -A INPUT -p tcp --dport 80 -s 192.680.0.1 -j ACCEPT `

Resetando a regra de firewall

`iptables -F`

Habilitando o protocolo ICMP com um tipo especifico:

`iptables -A INPUT -p icmp --icmp-type 8 -j ACCEPT `

Habilitando tudo que for relacionado ao protocolo UDP

`iptables -A INPUT -p udp -j ACCEPT `

Bloqueando um protocolo e uma porta especifica:

`iptables -A INPUT -p tcp --dport 80 -j DROP `


**Descobrindo hosts ativos: Ping Sweep**

Verificando quais hosts estão ativos atrves do ping:

` for ip in $(seq 1 254); do ping -c 1 172.16.1.$ip;done | grep "64 bytes" `

Verificando quais hosts estão ativos atrves do ping, tempo de espera 1 segundo:

` for ip in $(seq 1 254); do ping -c 1 192.168.0.$ip -w 1;done | grep "64 bytes" `

utilizando o FPING para descobrir hosts ativos

` fping -a -g 192.168.0.0/24 `

*Obs: Não confie segamente em uma técnica.*

Acessando o manual do ICMP

`man icmp`

Descobrindo hosts ativos: Pentest Interno

Utilizando ARPING

` arping -c 1 192.168.0.1 `

Analisnado um range de IPs com arping

` for ip in $(seq 1 14);do arping -c 1 192.168.0.$ip;done | grep "60 bytes" `

Comando utilizado em ARPING para indentificar todos os hosts da rede:

` arp-scan -l `
























