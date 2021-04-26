
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





