## Hashes e Senhas - Linux

## Entendendo os Hashes

*Obs:*
- Cada tipo de hash possuem tamanho especifico.
- Hash são irreversiveis

## Trabalhando com Hashes

Aplicando função de Hash

`echo -n "exemplo" | md5sum`

Tirando hash de arquivos

`md5sum arquivo`

Obtendo detalhes sobre o arquivo

`file arquivo*`

## One Way x Two Way

Decodificando um base 64

`echo "YnJhc2ls" | base64 -d ` 

Encodando uma imgem em base 64

`cat wallpaper.png | base64 > saida`

Reconstruindo o arquivo

`cat saida | base64 -d > wall.png`

## Hashes com Python

Exemplo via terminal:

```
python

import haslib
texto = "brasil"
hashlib.md5(texto).hexdigest()
```


## Base64 com Python

```
python

import base64
texto = "brasil"
base64.b64encode(texto)
```

## Identificando Hashes

Exemplo 01

`hashid .......`

Exemplo 02

`hash-identifier`

*Obs: valide em pelo menos dois programas qual o tipo de hash esta sendo utilizado, para valiadar sua identificação.*

## Estudo técnico: Atacando Hashes

*Obs: primeiro identifique qual tipo de hash esta sendo utilizado e depois efetue o ataque.*

Ataque de forma manual

`for i in $(cat wordlist.txt);do echo -n $i " " ;echo -n $i | sha1sum;done > rainbow_tables`

`greep "hash_a_ser_procurada" rainbow_tables`

Referência:

https://hashes.com/en/decrypt/hash

https://md5decrypt.net/en/

## Ataques a hashes: Ferramentas

Ferramenta 01

`john`

Exemplo 01

`john arquivo_com_hash`

Exemplo 02

`john arquivo_com_hash --format=Raw-MD5 --wordlist=/opt/aquivo.txt`

Ferramenta 02

`hashcat`

Exemplo 01

`hascat -m 100 arquivo_com_hash /usr/share/john/password.lst --force`

## Senhas em sistemas Linux

Lista de usuario linux

`cat /etc/passwd`

Lista de senhas linux

`cat /etc/shadow`

man crypt (Metodo utilizado no linux para encripitar senha).

**Referência:**

https://man7.org/linux/man-pages/man3/crypt.3.html
















