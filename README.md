# jsonserver
JSON Server criado para estudos.
> Esse documento esta disponível para estudos, qualquer sugestão é bem vinda. :)

## Instalar NodeJS (LTS) - HTTPS://NODEJS.ORG/EN/DOWNLOAD/
`$ node -v | $ npm -v`

## Instalar JSON-Server
`$ npm i -g json-server`

## Criar DB
`$ mkdir jsonserver`
`$ cd jsonserver`

## Criar arquivo db.json
`$ touch db.json`
```
{
  "people": [
    {
      "id": 0,
      "name": "Jhon"
    }
  ]
}
```

## Utilizando generate.js
> Para utilizar o generate.js você deve baixar as dependencias `Faker` e `Lodash`.

### Criar o arquivo generate.js
```
module.exports = function() {
    var faker = require("faker");
    var _ = require("lodash");
    return {
        people: _.times(100, function(n) {
            return {
                id: n,
                name: faker.name.findName(),
                avatar: faker.internet.avatar()
            }
        })
    }
}
```
### Rodar o comando de start do JSONServer apontando para o novo arquivo.
`$ json-server generate.js`



## Dependencias

* [JSONServer](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Faker](https://maven.apache.org/) - Dependency Management
* [Lodash](https://rometools.github.io/rome/) - Used to generate RSS Feeds