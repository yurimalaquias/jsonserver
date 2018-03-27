# JSON SERVER
JSON Server criado para estudos.
> Esse documento esta disponível para estudos, qualquer sugestão é bem vinda. :)

## Instalar NodeJS (LTS)
> https://nodejs.org/en/download/
`$ node -v | $ npm -v`

## Instalar JSON-Server
`$ npm i -g json-server`

## Criar DB
`$ mkdir jsonserver`
`$ cd jsonserver`

## Criar arquivo db.json
> http://localhost:3000/people/ 

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

* [JSONServer](https://github.com/typicode/json-server) - Get a full fake REST API with zero coding in less than 30 seconds (seriously)
* [Faker](https://github.com/Marak/Faker.js) - generate massive amounts of fake data in Node.js and the browser
* [Lodash](https://github.com/lodash/lodash) - A modern JavaScript utility library delivering modularity, performance, & extras. https://lodash.com/
