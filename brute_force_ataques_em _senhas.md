##   Brute Force: Ataques em senhas

**Ataques de Força Bruta**

- Se o sistema não te bloqueia depois de 3 tentativas erradas ele provavelmente permite ataque de força bruta
- Se ele te bloquei mais volta a te permitir tentativas depos de certo tempo tambem é possivel setar o time para o numero de tentativas.
- Podemos analisar tbm caracteristicas do alvo e montar um wordlist com base no alvo
- Podemos tentar senhas default
- Pode ser tambem utilizado wordlists populares.

## Wordlists

**Word Lists Kali**

- usr/share/wordlists
- usr/share/seclists

Comando utilizado para buscar um termo dentro de varias wordlists

`grep -r "termo_pesquisado" *`

Buscando padrões de senha atraves do Google

site:pastebin.com "alvo_pesquisado"

Wordlist Longato

https://github.com/ricardolongatto/loncrack/blob/master/wl.txt


Gerando mutação em wordlist

- Primeiro crie um lista com possiveis senhas utilizadas pelo alvo
- Depois execute o comando abaixo para fazer a mudação usando o John
- `john --wordlist=wl.txt --rules --stdout > wl_mutacao.txt`

Caso queira acresentar algum tipo de modificação para insereir na mutação, você pode alterar algumas configurações no john

- Acesse: /etc/john/john.conf
- Localize: List Rules Wordlist
- 
