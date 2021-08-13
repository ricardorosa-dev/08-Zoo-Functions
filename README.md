<h1 align="center">Zoo Functions</h1>

![GitHub repo size](https://img.shields.io/github/repo-size/ricardorosa-dev/08-Zoo-Functions?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/ricardorosa-dev/08-Zoo-Functions?style=for-the-badge)

> Projeto para o aprendizado de JavaScript, JSON e testes unitários com a biblioteca Jest

> JavaScript | Jest
---
### <strong>Proposta</strong>: Dado um arquivo JSON, criamos funções para manipulação desse arquivo. Depois criamos testes para essas funções.

### Exemplo de função
```JavaScript
function animalsByIds(...ids) {
  const result = [];
  if (ids === undefined) {
    return [];
  }

  for (let i = 0; i < ids.length; i += 1) {
    const animalsMap = animals.filter(animal => animal.id === ids[i]);
    result[i] = animalsMap[0];
  }
  return result;
}
```
### > Teste
```JavaScript
describe('Implemente a função animalsByIds', () => {
  it('Caso receba nenhum parâmetro, necessário retornar um array vazio', () => {
    const actual = zoo.animalsByIds();
    const expected = [];
    assert.deepEqual(actual, expected);
  });

  it('Ao receber como parâmetro um único id, retorna os animais com este id', () => {
    const actual = zoo.animalsByIds('0938aa23-f153-4937-9f88-4858b24d6bce');
    const expected = [{
      id: '0938aa23-f153-4937-9f88-4858b24d6bce',
      name: 'lions',
      popularity: 4,
      location: 'NE',
      residents: [
        { name: 'Zena', sex: 'female', age: 12 },
        { name: 'Maxwell', sex: 'male', age: 15 },
        { name: 'Faustino', sex: 'male', age: 7 },
        { name: 'Dee', sex: 'female', age: 14 }
      ]
    }]

    assert.deepEqual(actual, expected);
  });

  it('Ao receber mais de um id, retorna os animais que têm um desses ids', () => {
    const actual = zoo.animalsByIds('0938aa23-f153-4937-9f88-4858b24d6bce', 'e8481c1d-42ea-4610-8e11-1752cfc05a46');
    const expected = [{
      id: '0938aa23-f153-4937-9f88-4858b24d6bce',
      name: 'lions',
      popularity: 4,
      location: 'NE',
      residents: [
        { name: 'Zena', sex: 'female', age: 12 },
        { name: 'Maxwell', sex: 'male', age: 15 },
        { name: 'Faustino', sex: 'male', age: 7 },
        { name: 'Dee', sex: 'female', age: 14 }
      ]
    },
    {
      id: 'e8481c1d-42ea-4610-8e11-1752cfc05a46',
      name: 'tigers',
      popularity: 5,
      location: 'NW',
      residents: [
        { name: 'Shu', sex: 'female', age: 19 },
        { name: 'Esther', sex: 'female', age: 17 }
      ]
    }];

    assert.deepEqual(actual, expected);
  });
});
```
---
## Author

👤 **Ricardo Rosa**

* Website: http://ricardorosa-dev.github.io/
* Github: [@ricardorosa-dev](https://github.com/ricardorosa-dev)
* LinkedIn: [@https://www.linkedin.com/in/ricardorosa-dev/](https://www.linkedin.com/in/ricardorosa-dev/)

---




## Show your support

Give a ⭐️ if this project helped you!

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
