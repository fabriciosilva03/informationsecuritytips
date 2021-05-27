## DNS (O que é o protocolo)

**List of Servers**

Referência: https://www.iana.org/domains/root/servers

**Tools && Comands**

`dnsutils` - Ferramenta que acopla diversas ferramentas relacionadas a DNS

`dig` - Listando todos os root servers

`dig NS br` - Listando servers que são responsaveis por DNS relacionados ao .br.

`dig NS @a.root-server.net br` - utilizando root server para consultar sobre os responsaveis pelo .br.

`dig NS @a.dns.br site.com.br` - consultando sobre os servers responsaveis por determinado dominio.

Exemplo com globo.com

Primeiro indenfique os server responsaveis .br

`dig NS @a.root-server.net .br`

Depois use um dos servers encontrados para fazer a resolução

`dig NS @a.dns.br globo.com.br`

Apos indentificar os hosts responsaveis, utilize um para identificar o IP do site globo.com

`dig A @ns.oghost.com.br wwww.globo.com.br`

Identificando sua resolução de DNS local

`cat /etc/resolv.conf`







