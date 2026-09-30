# Kiosk Lock — canal de atualizacoes

Este repositorio nao contem codigo. Serve apenas de canal publico de
metadados de release para a aplicacao **Kiosk Lock**.

O codigo vive em `antoniocostalopes/Kiosk-Lock-APP`.

## Como funciona

A aplicacao consulta, ao arrancar e quando o operador pede, o endereco:

```
https://api.github.com/repos/antoniocostalopes/Kiosk-Lock-Releases/releases/latest
```

Le o campo `tag_name`, compara-o com a versao instalada e, sendo mais
recente, mostra um aviso discreto no canto do ecra.

A consulta tem 8 segundos de limite e **nao envia qualquer identificador
do utilizador**: sem cabecalho de autorizacao, sem cookies, sem parametros.
Falha de rede ou metadados invalidos nunca interrompem a exibicao.

## Formato das etiquetas

A comparacao e semantica e ignora prefixos. Sao aceites `v1.2.3`, `1.2.3`,
`release-1.2.3` e pre-lancamentos como `1.2.3-beta.1`, que ficam antes da
versao final correspondente.

## Publicar uma versao

1. Criar uma release com a etiqueta da nova versao
2. Anexar os instaladores assinados
3. Descrever no corpo o que mudou

Ate existir keystore de distribuicao, as releases levam apenas metadados.
