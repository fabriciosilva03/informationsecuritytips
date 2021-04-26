## Recebimento via IMAP

Com o comando Telnet é possível testar o funcionamento da caixa postal para com o protocolo IMAP, listando todas as pastas criadas no webmail.

Clique em Iniciar.

Preencha o campo de pesquisa com o comando cmd e clique Ok.

telnet pop.dominio.com.br 143

Digite zzz login usuario@dominio.com.br senhadousuario

Digite aaa list “” “*”

Digite zzz select “INBOX”

Depois é só digitar um quit, para fecharmos o teste de e-mail.



Referencias:

https://electrictoolbox.com/pop3-commands/

https://ajuda.locaweb.com.br/wiki/teste-de-envio-e-recebimento-via-telnet/

https://www.my-tiny.net/L05-smtp.htm
