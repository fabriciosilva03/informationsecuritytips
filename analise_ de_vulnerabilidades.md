##  Análise de Vulnerabilidades

## Etapa - Análise de Vulnerabilidade

Seguindo método de trabalho:

- Information Gathering
- Sacnning 
- Enumeration
- **Vulnerability Analysis**
- Exploitation
- Post Exploitation

Para realizar o processo de análise de vulnerabilidade de forma manual recomendo utiliza o seguinte processo:

1. Identificar o possível SO
2. identificar a possível versão do software / aplicação / sistema
3. Buscar por vulnerabilidades conhecidas
4. Tentar identificar vulnerabilidades ainda não conhecidas
5. Se possível outros tipos de atques (exemplo: Brute force)*

Bases de dados de vulnerabilidades e exploits:

https://www.exploit-db.com/

https://www.securityfocus.com/vulnerabilities

https://www.cvedetails.com/

https://nvd.nist.gov/vuln/search

https://www.rapid7.com/

https://packetstormsecurity.com/files/tags/exploit/

`searchsploit nome_da_aplicação_ou_SO`

## Pesquisa manual por vulnerabilidades

*Utilizando os sites acima faça a busca por vulnerabilidades de acordo com a aplicação ou sistema que vocẽ identificou, caso nao saiba a versão da aplicação você pode se basear pela versão do sistema operacional o ano e tentar filtrar qual a versão da aplicação estva disponível na quele ano.*

Google Dork

`site:exploit-db.com "webmin"`

## Scanners de Vulnerabilidades

*São ferramentas capazes de automatizar o processo de descoberta de vulnerabilidades.*

- Nessus
- Qualys
- OpenVAS

Como funciona?

*Um bom scanner de vulnerabilidades via tentar automatizar o processo da seguinte forma* 

1. Tenta identificar se o host está ativo
2. Realiza um portscan
3. Tenta identificar o sistema operacional
4. Tenta identificar os serviços encontrados
5. Faz a verificação de vulnerabilidades de acordo com sua base de vulnerabilidades

Vantagens e Desvantagens

VANTAGENS

- Analisa uma grande quantidade de vulnerabilidades conhecidasa em pouco tempo em diversos hosts simultaneamente
- Ajuda a realizar gerenciamento de patches
- Pode ser usado para ajudar em processos de auditoria e compliances

DESVANTAGENS

- Pode gerar vários falsos positivos (informar que existe uma vulnerabilidade onde não existe)
- Gera falsos negativos (não detecta uma vulnerabilidade existente)
- Cosome poder computacional
- Gera bastante ruído na rede/host

## Exemplos de uso

*O bom uso de uma ferramenta que automatiza o processo de analise de vulnerabilidade seria o saber configurar da forma correta para que mesma não seja barrada por alguma ferrametna de proteção, alem de alternar algumas tarefas entre automatico e manual.*

## Trabalhando com o Nessus

Download:

https://www.tenable.com/downloads/nessus?loginAttempted=true

Apos fazer o download faça a checagem do ckesum para ver se é compativel com a que esta no site e a que você baixou.

Exemplo:

`sha256sum nome_da_aplicação`


## Análise de um scan básico

## Análise em aplicações web

## Realizando um Patch Assessment

## Realizando testes de força bruta

## Scan avançado (Like a pro)

## Compliance PCI-DSS

Referência:

https://www.pcisecuritystandards.org/document_library

https://www.pcisecuritystandards.org/document_library?category=pcidss&subcategory=pcidss_supporting#results

https://www.pcisecuritystandards.org/documents/Penetration_Testing_Guidance_March_2015.pdf

## Exemplo: Compliance PCI-DSS

## Falsos Negativos

## Revisão e dicas

## NMAP NSE

Localizando scripts

`cd /usr/share/nmap/scripts`

Lendo 

`cat script.db`

Validando uma vulnerabilidade

`nmap -p21 --script ftp-vsftpd-backdoor.nse -Pn 192.168.0.1`

*Obs: quando o script possui o campo @args ele permite a inserção de argumentos.*

`nmap -p21 --script ftp-vsftpd-backdoor.nse --script-args cmd=pwd -Pn 192.168.0.1`

*Obs: as vezes alguns scripts para terem resultado precisa-se passar argumentos.*

*Para validar alguma vulnerabilidade faça uso do nikto ou do dirb.*

## Shadow Brokers

*The Shadow Brokers é um grupo de hackers que apareceu pela primeira vez no verão de 2016. Eles publicaram vários vazamentos contendo ferramentas de hacking, incluindo várias explorações de dia zero, do "Equation Group", amplamente suspeito de ser um ramo da Agência de Segurança Nacional dos Estados Unidos.*

*Tambem se trata de um utilitario implementado em diversas ferramentas para detectar possíveis vulnerabilidades que tem grande impacto, exemplo de ferramenta que possui este utilitário seria o *Nessus*.














