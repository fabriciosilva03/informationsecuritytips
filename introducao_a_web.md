## DNS (O que é o protocolo)

**List of Servers**

Referência: https://www.iana.org/domains/root/servers

**Tools && Comands**

Ferramenta que acopla diversas ferramentas relacionadas a DNS

`dnsutils`

Listando todos os root servers

`dig`
 
Listando servers que são responsaveis por DNS relacionados ao .br.
 
`dig NS br`

Utilizando root server para consultar sobre os responsaveis pelo .br.

`dig NS @a.root-server.net br`

Consultando sobre os servers responsaveis por determinado dominio.

`dig NS @a.dns.br site.com.br`

- Exemplo com globo.com

Primeiro indenfique os server responsaveis .br

`dig NS @a.root-server.net .br`

Depois use um dos servers encontrados para fazer a resolução

`dig NS @a.dns.br globo.com.br`

Apos indentificar os hosts responsaveis, utilize um para identificar o IP do site globo.com

`dig A @ns.oghost.com.br wwww.globo.com.br`

Identificando sua resolução de DNS local

`cat /etc/resolv.conf`

## Entradas DNS (CNAME, A, AAAA, MX, SOA)

@  A IP

A - IPv4

AAAA - IPv6

CNAME - Dominio

TXT - Anotações e Validações

MX - aponta os servidores de email do dominio.

SOA - Validações do dominio

NS - Servidores autoritativos

Comando para verificar o TXT registrado sobre algum dominio.

`ig TXT site.com`

Listando servidores de email

`dig MX site.com`



## Métodos HTTP

- Get: Ler dados do servidor
- Post: enviar dados para o servidor
- Put: Enviar dados para o servidor (criar/atualizar)
- Delete: Deleta dados do servidor
- Patch: Atualiza dados do servidor.

## Servidores Web (Apache, Nginx, IIS)

**NGNIX**

instalando interpretador PHP 

`sudo apt-get install php-fpm`

Inicializando PHP

`sudo systemctl start php-fpm`

Configurando PHP no ngix

Acesse o arquivo default

`nano /etc/nginx/sites-enable/default`

e remova algumas na região 

location ~ \.php$ {

Comando para acompanhar os registros de log do nginx

`sudo tail -f /var/log/nginx/access.log`

**APACHE2**

Instalando PHP e Apache2 

`sudo apt-get install php apache2`

Comando para acompanhar os registros de log do nginx

`sudo tail -f /var/log/apache2/access.log`

Modulo de securança para evitar ataques em servidores apache

**ModSecurity **

https://github.com/SpiderLabs/ModSecurity




## Cookies

- Cookie de sessão
- Cookie persistente
- Cookies de terceiros

**Propriedades **

- name
- value
- path
- domain
- expires
- http-only
- secure
- samesite

## API (REST, SOAP, Graphql

**Tipos de API Relevantes**

- REST
- GRAPHQL
- SOAP





