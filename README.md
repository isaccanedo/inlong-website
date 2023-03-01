# InLong Official Website

Este projeto mantém todas as fontes usadas para construir o site oficial do InLong, que é servido em
https://inlong.apache.org/

## Pré-requisito

O site Inlong é alimentado por [Docusaurus] (https://docinaurus.io/).
Se a sua versão do docusaurus for menor que `2.0.0`, atualize para` 2.0.0`.
Verifique também que a versão do seu nó é 14.x, versões superiores a 14.x ainda não são suportadas pelo Docusaurus.

## Instrução de construção

1. Run `npm i` no diretório raiz para instalar as dependências.
2. Run `npm start` no diretório raiz para iniciar um servidor local, você verá o site em 'http://127.0.0.1:3000'.
3. Run `npm run build` para construir o código-fonte.

Se você tiver uma versão superior do node instalada, considere `nvm` para permitir que diferentes versões do `node` coexistam em sua máquina.

1. Siga as [instruções](http://nvm.sh) para instalar o nvm
2. Run `nvm install v14.13.0` to install node v14
3. Run `nvm use v14.13.0` to switch the working environment to node v14

Então você está pronto para executar e construir o site. Siga as instruções de compilação acima para os detalhes.

## Como enviar um PR

Verifique se você enviou o problema para rastrear o PR: [https://github.com/apache/inlong/issues](https://github.com/apache/inlong/issues)

1. Não use `git add .` para confirmar todas as alterações.
2. Basta enviar seus arquivos alterados, como:
    * `*.md`
	* blog.js or docs.js or site.js
3. Envie um PR para a filial **mestre**.


## Guia para adicionar um novo documento

### Adicionar um novo artigo para documentos

1. Adicione um novo arquivo .md em `docs` ou `i18n`.
2. Execute o servidor dev localmente para verificar se o artigo pode ser exibido corretamente.
3. Envie a solicitação pull contendo apenas *.md e development.js.


### Adicionar uma nova versão para documentos

1. Modifique o documento em `docs` e execute `npm run docusaurus docs:version replace_by_target_version` localmente para copiar um documento.
2. Adicione um rótulo ao item do DOC no arquivo `docusaurus.config.js`.
3. Modifique a última versão da tabela em `/src/pages/version/index.js`.
