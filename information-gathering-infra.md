**IANA**

https://www.iana.org/

**WHOIS**

Iana

https://www.iana.org/whois

Registro br

https://registro.br/tecnologia/ferramentas/whois/

Ripe

https://apps.db.ripe.net/db-web-ui/query

**RDAP**

https://rdap-web.lacnic.net/

https://registro.br/rdap/

https://client.rdap.org/

**IP**

Comando via terminal:

``` host site.com.br ```

Arin 

https://search.arin.net/rdap/

Comando via terminal, para obter o bloco de IP:

``` whois 192.168.0.1 | grep "inetnum" ```

**BGP**

https://bgpview.io/

https://bgp.he.net/

**SHODAN**

https://www.shodan.io/

Shodan no linux:

```pip install shodan```

```shodan init API```

Exemplos de busca no shodan via terminal:

``` shodan country:br port:445 ``` 

``` shodan host 192.168.0.1 ``` 

**CENSYS**

https://censys.io/

Exemplo de filtro:

```location.country_code:BR AND metadata.os:Ubunto AND ports:3306```


**DNS - Domain Name System**

Pesquisando resoluções de DNS via terminal:

```host -t A site.com.br ```

``` host -t mx site.com.br ```

``` host -t ns site.com.br ```

``` host -t hinfo site.com.br ```

``` host -t aaaa site.com.br ```

``` host -t txt site.com.br ```

``` host mail.site.com.br ```










