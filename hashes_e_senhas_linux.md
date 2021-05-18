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

Hashes com Python

Exemplo via terminal:

python

import haslib
texto = "brasil"
hashlib.md5(texto).hexdigest()






