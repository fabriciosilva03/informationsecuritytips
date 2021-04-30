## Enumeração (Enumeration)

- Identificar detalhes do serviço em execução.
- Coletar mais informações do host.
- As informações complementares podem ajudar nas fases de exploração.
- A versão indentificada pode ter uma vulnerabilidade conhecida (Exploits Público).
- Alguns serviços podem ser vulneráveis a ataques de força bruta.

1. Identificar detalhes do serviço em execução
2. Estudar o serviço/protocolo para enteder o funcionamento
3. Tentar interagir com o serviço/protocolo afim obter mais informações do host
4. Indentificar possíveis vulnerabilidades/vetores de ataque.


## Enumerando HTTP

**O que buscamos:**

- Versões do Web Server(IIS, Apache, Nginx, etc.)
- Tecnologias utilizadas(PHP, ASP, JSP, etc.)
- Métodos aceitos(PUT,POST,DELETE, etc.)

## Como Fazer?

- Portas comuns: 80,8080,81,8081
- Versões do protocolo: HTTP/1.0 | HTTP/1.1
- Requisição: GET | HEAD | OTPTIONS
- Utilitários: nc | curl | telnet

Exemplo 01:

`nc -v site.com.br 80
HEAD / HTTP/1.0
`

Exemplo 02:

`nc -v site.com.br 80
GET / HTTP/1.1
Host: site.com.br
`
Exemplo 03 - Indenticiando a versão da liguagem utilizada:

`nc -v site.com.br 80
GET /index.aspx HTTP/1.0
`

## Enumerando HTTPs


Exemplo 01:

`openssl s_client -connet site.com:443
HEAD / HTTP/1.1
Host: site.com.br
`
*Obs: Ao setar a porta que há cripritográfia na comunicação utilize HTTP/1.1 e defina o Host.*

Exemplo 02:

`openssl s_client -quiet -connet www.site.com:443
HEAD / HTTP/1.1
Host: www.site.com.br
`
*Obs: -quiet oculta mensagens de respostas de toda a execução inicial.*

## Identificando Web Application Firewalls

Exemplo 01

`wafw00f site.com`

*Obs: **wafw00f** - ferramenta utilizada para identificar qual WAF esta sendo utilizado em uma aplicação web.







