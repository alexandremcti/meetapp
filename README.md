# configuração do sucrase

Instalando

- yarn add sucrase -D (instalar em ambiente de desenvolvimento);

# configurando nodemon

Instalando

- yarn add nodemon -D (instalar em ambiente de desenvolvimento);

Configurar o package.json

- "scripts":{
  "dev": "nodemon src/server.js"
  }

Configurar o nodemon para rodar extensoes js quando usado o sucrase

- criar um arquivo nodemon.json
- configurar o arquivo

{
"execMap":{
"js": "sucrase-node"
}
}

# configuração do docker

criar um container com uma imagem.

docker run --name database -e POSTGRES_PASSWORD=docker -d postgres -p 5432:5432 -d postgres

# configuração do eslint (padronização de código)

instalação

- yarn add eslint -D

configurando um arquivo de configuração eslint

- yarn eslint --init

-- seleciona as opções

- To check syntax, find problems, and enforce code style
- javascript modules(import/export)
- which framework - none of these
- where does your code run - node
- stile guide - popular (airbnb)
- format file config - javascript

-- remover arquivo package-lock.json e comandar um yarn no terminal
-- as configurações do arquivo settings.json devem ter esses parametros

"eslint.validate": [
{
"language": "javascript",
"autoFix": true
},
{
"language": "javascriptreact",
"autoFix": true
},
{
"language": "typescript",
"autoFix": true
},
{
"language": "typescriptreact",
"autoFix": true
}
],

-- instalar o eslint e configurar arquivo eslintrc.js

rules: {
"prettier/prettier": "error",
"class-methods-use-this":"off",
"no-param-reassign": "off",
"camelcase":"off",
"no-unused-vars":[
"error", {"argsIgnorePattern": "next"}]
},

# configuração do prettier

- instalar o prettier

yarn add prettier eslint-config-prettier eslint-plugin-prettier -D

- configurar o arquivo eslintrc

  extends: ['airbnb', 'prettier'],
  plugins:['prettier'],

- criar arquivo de configuração .prettierrc para sobrescrever regras
  {
  "singleQuote": true,
  "trailingComma": "es5"
  }

- fazer fix automático

yarn eslint --fix src --ext .js

# configuração do sequelize

- criar um diretório config para conexão
- criar um diretório database para as configurações de database e migrations
- instala a dependência sequelize

yarn add sequelize

- configura o arquivo .sequelizerc
- configura o database.js
- instala a dependência pg e pg-hstore para usar o dialeto postgres

yarn add pg pg-hstore

# criação de migrations

Roda o comando sequelize migration:create

yarn sequelize migration:create --name=create-users

depois de configurado o migrate user, rodar o comando yarn sequelize db:migrate

desfazer uma migration

db:migration:undo

ou desfaz todas

db:migration:undo:all

# criação de hash

instalar o bcryptjs

# instalação do jsonwebtoken para jwt

yarn add jsonwebtoken

# validação de entradas

yarn add yup
