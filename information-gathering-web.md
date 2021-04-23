## Web Recon

**Robots e Sitemap**

Exemplo de busca por robots.txt utilizando o google dork - `site:.com.br ext:txt robost`

**Listagem de Diretórios**

index of  -  \css   -   \admin

**Mirror Website**

`wget -m site.com.br`

`wget -m -e robots=off site.com.br`

**Análise de erros, códigos e extensões**

**Pesquisa via requisições HTTP**

` nc -v site.com.br 80 `

01 - ` HEAD/HTTP/1.0 `   02 - ` GET /index.php HTTP/1.0`    03 - `OPTIONS /site HTTP/1.0 ` 

04 - ` HEAD/HTTP/1.0 Host:site.com.br `  Obs: Utilize este metodo quando o site possuir hospedagem compartilhada ou algum tipo de firewall.

**Brute force - Arquivos e Diretórios**

` dirb http://site.com.br `

**Conhecendo o Curl**

Pesquisa normal: `curl site.com.br`

Pesquisa detalhada: `curl -v site.com.br`

Filtrando por status code da pagina: `curl -s --head site.com.br | grep "HTTP" | cut -d " " -f 2 `

Filtrando por status code da pagina: `curl -s -o /dev/null -w "%{http_code}" site.com.br `

Mudando o user agent: `curl -v -H "User-Agent: xxxx" site.com.br`

**WhatWeb**

`whatweb site.com.br`

**Wappalyzer**

- Extensão para o browser para indentificar as tecnologias utilizadas no site.


















       
