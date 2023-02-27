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

Make sure you have submit issue for tracking PR: [https://github.com/apache/inlong/issues](https://github.com/apache/inlong/issues)

1. Do not use `git add .` to commit all the changes.
2. Just push your changed files, such as:
    * `*.md`
	* blog.js or docs.js or site.js
3. Send a PR to **master** branch.


## Guide for adding new document

### Add a new article for docs

1. Add new .md file under `docs` or `i18n`.
2. Run dev server locally to verify the article can be displayed correctly.
3. Send the pull request contains the *.md and development.js only.


### Add a new version for documents

1. Modify the document in `docs`, then run `npm run docusaurus docs:version replace_by_target_version` locally to copy a document.
2. Add a label to DOC's item in `docusaurus.config.js` file.
3. Modify the last table version in `/src/pages/version/index.js`.
