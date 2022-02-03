# Questões práticas
### 3 - Crie nesse repositório um arquivo que vai se chamar calculadora.js, abra esse arquivo em seu editor de códigos favoritos e adicione o seguinte código:

```js
const args = process.argv.slice(2);
console.log(parseInt(args[0]) + parseInt(args[1]));
```

### Descubra o que esse código faz através de pesquisas na internet, também descubra como executar um código em javascript e dado que o nome do nosso arquivo é calculadora.js e você entendeu o que o código faz, escreva abaixo como executar esse código em seu terminal:

R: `process.argv` é uma matriz que contém os argumentos da linha de comando. O primeiro argumento na `process.argv` matriz é sempre o diretório do Node.js, que está executando o programa. O segundo argumento é sempre o local do arquivo que está sendo executado. Os próximos elementos serão quaisquer argumentos adicionais da linha de comando. Por `argv` ser uma matriz, você pode usar o `slice` interno do JavaScript que retorna uma seleção de elementos. Quando você fornece a função slice(2), obtém todos os elementos argv que vêm após o segundo elemento, ou seja, os argumentos que o usuário inseriu. Inserindo numeros no terminal pós `node calculadora.js`, `console.log(parseInt(args[0]) + parseInt(args[1]));` irá soma-los e devolver o valor da soma. Caso os valores informados sejam diferentes de números, o retorno será `NaN`.

### 4 - Agora que você já tem um código feito e a resposta aqui, você precisa subir isso para seu repositório. Sem usar git add . descubra como adicionar apenas um arquivo ao seu histórico de commit e adicione calculadora.js a ele. Que tipo de commit esse código deve ter de acordo ao conventional commit. Que tipo de commit o seu README.md deve contar de acordo ao conventional commit. Por fim, faça um push desse commit.

R: O comando git add . adiciona todos os untrackeds da working directory para a stage area, porem com o comando git add "nome do file" é possível adiciona-los de forma individual, por exemplo: `git add "calculadora.js"`. No caso do commit da calculadora por tratar-se de adições de novas funcionalidades ou de quaisquer outras novas implantações ao código, usa-se o tipo `feat`. E no caso do README, por referir-se a uma inclusão ou alteração somente de arquivos de documentação, usa-se o tipo `docs`

### 5. Copie e cole o código abaixo em sua calculadora.js:

```js
const soma = () => {
    console.log(parseInt(args[0]) + parseInt(args[1]));
};

const args = process.argv.slice(2);

soma();
```

### Descubra o que essa mudança representa em relação ao conventional commit e faça o devido commit dessa mudança.

R: Em relação aos padrões de commit, considerando que houveram alterações no código, mas manteve-se a função, deve-se usar o tipo `refactor`


