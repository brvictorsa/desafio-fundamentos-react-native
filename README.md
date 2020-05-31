## :rocket: DESAFIO GOMARKETPLACE REACT NATIVE E TYPESCRIPT
Aplicação GoMarketplace utilizando React Native, junto com TypeScript, utilizando rotas, Async Storage e a Context API.

![AppMobile](https://github.com/brvictorsa/desafio-gomarketplace-react-native/blob/master/src/assets/gomarketplace.png)

### Utilizando uma fake API

Antes de tudo, para que você tenha os dados para exibir em tela, criamos um arquivo que você poderá utilizar como fake API para te prover esses dados.

Para isso, deixamos instalado no seu package.json uma dependência chamada `json-server`, e um arquivo chamado `server.json` que contém os dados para uma rota `/products`. Para executar esse servidor você pode executar o seguinte comando:

```js
yarn json-server server.json -p 3333
yarn json-server server.json --host IP -p 3333 //onde 'IP' é o endereço da sua máquina (e.g 192.168.1.1)
```

### Funcionalidades da aplicação

- **`Listar os produtos da fake API`**: a página `Dashboard` deve ser capaz de exibir uma listagem através de uma tabela, com o campo `title`, `image_url` e `price`.

- **`Adicionar itens ao carrinho`**: a aplicação deve utilizar o Contexto chamado `cart` que deixamos disponível. As funcionalidades se encontram dentro de `hooks/cart.tsx`.

- **`Exibir itens do carrinho`**: a página `Cart` deve exibir todos os itens do carrinho, junto com a quantidade, valor único, valor subtotal dos itens e total de todos os items.

- **`Aumentar quantidade de itens do carrinho`**: a página `Cart` você deve permitir que o usuário aumente a quantidade de itens do mesmo produto, para isso você pode utilizar a função `increment` dentro do seu contexto em `/src/hooks/cart.tsx`.

- **`Diminuir quantidade de um item do carrinho`**: a página `Cart` deve permitir que o usuário decremente a quantidade de itens do mesmo produto, para isso você pode utilizar a função `decrement` dentro do seu contexto em `/src/hooks/cart.tsx`.

- **`Exibir valor total dos itens no carrinho`**: Tanto na página `Dashboard`, tanto na página `Cart` você deve exibir o valor total de todos os itens que estão no seu carrinho.


### Específicação dos testes

A aplicação conta com os seguintes testes:

- **should be able to list the products**: para que esse teste passe, sua aplicação deve permitir que sejam listados na sua tela `Dashboard`, toda os produtos que são retornadas do Fake API. Essa listagem deve exibir o `title` e o `price` que deve ser formatado utilizando a função `Intl`.

- **should be able to add a product to the cart**: para que esse teste passe, deve-se permitir que seja possível adicionar produtos da sua `Dashboard` ao carrinho, utilizando o contexto de `cart` disponibilizado.

- **should be able to list the products on the cart**: para que esse teste passe, deve-se permitir que seja possível listar os produtos que estão salvos no contexto do seu carrinho na página `Cart`, nessa página exiba o nome do produto, o subtotal total de cada produto (price * quantity)..

- **should be able to calculate the cart total**: para que esse teste passe, tanto na página `Dashboard`, tanto na página `Cart` você deve exibir o valor total de todos os itens que estão no seu carrinho.

- **should be able to show the total quantity of itens in the cart**: para que esse teste passe, tanto na página `Dashboard`, tanto na página `Cart` você deve exibir o número total de itens que estão no seu carrinho.

- **should be able to increment product quantity on the cart**: para que esse teste passe, deve-se permitir que seja possível incrementar a quantidade de um produto do seu carrinho, utilizando o contexto de `cart` disponibilizado.

- **should be able to decrement product quantity on the cart**: para que esse teste passe, deve-se permitir que seja possível decrementar a quantidade de um produto do seu carrinho, utilizando o contexto de `cart` disponibilizado.

- **should be able to navigate to the cart**: para que esse teste passe, no seu componente `FloatingCart` na Dashboard, você deve permitir que ao clicar no botão de carrinho com o testID de `navigate-to-cart-button`, o usuário seja redirecionado para a página `Cart`.

- **should be able to add products to the cart**: para que esse teste passe, no seu arquivo onde contém o contexto do carrinho, você deve permitir que a função `addToCart` adicione um novo item ao carrinho.

- **should be able to increment quantity**: para que esse teste passe, no seu arquivo onde contém o contexto do carrinho, você deve permitir que a função `increment` altere incremente em `1 unidade` a quantidade de um item que está armazenado no contexto.

- **should be able to decrement quantity**: para que esse teste passe, no seu arquivo onde contém o contexto do carrinho, você deve permitir que a função `decrement` altere decremente em `1 unidade` a quantidade de um item que está armazenado no contexto.

- **should store products in AsyncStorage while adding, incrementing and decrementing**: para que esse teste passe, no seu arquivo onde contém o contexto do carrinho você deve permitir que `todas as atualizações que você fizer no carrinho, sejam salvas no AsyncStorage`. Por exemplo, ao adicionar um item ao carrinho, adicione-o também no AsyncStorage. Lembre de também atualizar o valor do AsyncStorage quando você incrementar ou decrementar a quantidade de um item.

- **should load products from AsyncStorage**: para que esse teste passe, no seu arquivo onde contém o contexto do carrinho, deve-se permitir que `todos os produtos que foram adicionados sejam buscados do AsyncStorage`.

### Instalar e executar o projeto:

**Mobile**

1. Clonar o projeto frontend para seu local de trabalho (via HTTPS).

2. Executar o comando *yarn* no terminal para baixar as dependências do projeto.
```js
yarn //or npm install
```
3. Executar o metro bundler pelo comando.
```js
yarn start //or npm run start
```

4. Com o dispositivo conectado na USB, instalar o app pelo comando.
```js
yarn android //or npm run android
```

5. Executar a fake API conforme explicado no item acima *Utilizando uma fake API*.

6. Executar os testes da aplicação com o comando.
```js
yarn test  //or npm run test
```

## :memo: Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

---
