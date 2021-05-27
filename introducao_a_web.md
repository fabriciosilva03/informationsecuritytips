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







