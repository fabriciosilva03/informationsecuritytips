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









