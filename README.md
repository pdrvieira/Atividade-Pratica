# Questões práticas
### 3 - Crie nesse repositório um arquivo que vai se chamar calculadora.js, abra esse arquivo em seu editor de códigos favoritos e adicione o seguinte código:

```js
const args = process.argv.slice(2);
console.log(parseInt(args[0]) + parseInt(args[1]));
```

### Descubra o que esse código faz através de pesquisas na internet, também descubra como executar um código em javascript e dado que o nome do nosso arquivo é calculadora.js e você entendeu o que o código faz, escreva abaixo como executar esse código em seu terminal:

R: `process.argv` é uma matriz que contém os argumentos da linha de comando. O primeiro argumento na `process.argv` matriz é sempre o diretório do Node.js, que está executando o programa. O segundo argumento é sempre o local do arquivo que está sendo executado. Os próximos elementos serão quaisquer argumentos adicionais da linha de comando. Por `argv` ser uma matriz, você pode usar o `slice` interno do JavaScript que retorna uma seleção de elementos. Quando você fornece a função slice(2), obtém todos os elementos argv que vêm após o segundo elemento, ou seja, os argumentos que o usuário inseriu. Inserindo numeros no terminal pós `node calculadora.js`, `console.log(parseInt(args[0]) + parseInt(args[1]));` irá soma-los e devolver o valor da soma. Caso os valores informados sejam diferentes de números, o retorno será `NaN`.

### 4 - Agora que você já tem um código feito e a resposta aqui, você precisa subir isso para seu repositório. Sem usar git add . descubra como adicionar apenas um arquivo ao seu histórico de commit e adicione calculadora.js a ele. Que tipo de commit esse código deve ter de acordo ao conventional commit. Que tipo de commit o seu README.md deve contar de acordo ao conventional commit. Por fim, faça um push desse commit.

R: O comando git add . adiciona todos os untrackeds da working directory para a stage area, porem com o comando git add "nome do file" é possível adiciona-los de forma individual, por exemplo: `git add "calculadora.js"`. No caso do commit da calculadora por tratar-se de adições de novas funcionalidades ou de quaisquer outras novas implantações ao código, usa-se o tipo `feat`. E no caso do README, por referir-se a uma inclusão ou alteração somente de arquivos de documentação, usa-se o tipo `docs`.

### 5. Copie e cole o código abaixo em sua calculadora.js:

```js
const soma = () => {
    console.log(parseInt(args[0]) + parseInt(args[1]));
};

const args = process.argv.slice(2);

soma();
```

### Descubra o que essa mudança representa em relação ao conventional commit e faça o devido commit dessa mudança.

R: Em relação aos padrões de commit, considerando que houveram alterações no código, mas manteve-se a função, deve-se usar o tipo `refactor`.

### 6 - João entrou em seu repositório e o deixou da seguinte maneira:

```js
const soma = () => {
    console.log(parseInt(args[0]) + parseInt(args[1]));
};

const sub = () => {
    console.log(parseInt(args[0]) - parseInt(args[1]));  
}

const args = process.argv.slice(2);

switch (args[0]) {
    case 'soma':
        soma();
    break;

    case 'sub':
        sub();
    break;

    default:
        console.log('does not support', arg[0]);
}
```

### Depois disso, realizou um git add . e um commit com a mensagem: "Feature: added subtraction" faça como ele e descubra como executar o seu novo código. Nesse código, temos um pequeno erro, encontre-o e corrija para que a soma e divisão funcionem. Por fim, commit sua mudança.

Existem erros comprometendo o programa, em `console.log(parseInt(args[0]) + parseInt(args[1]));` os valores do index deveriam ser 1 e 2, pois o valor 0, será assumido pelas entradas "soma" ou "sub" da estrutura Switch-Case. E também, na ultima linha `console.log('does not support', arg[0]);` deveria estar `console.log('does not support', args[0]);` para que haja concordancia entre as variáveis.

### 7. Por causa de joãozinho, você foi obrigado a fazer correções na sua branch principal! O produto foi pro saco e a empresa perdeu muito dinheiro porque não conseguiu fazer as suas contas, graças a isso o seu chefe ficou bem bravo e mandou você dar um jeito disso nunca acontecer. Aprenda a criar uma branch, e desenvolva a feature de divisão nessa branch.

R: Com o comando `git checkout -b staging` cria-se a branch staging, onde pode-se desenvolver testes e alterações paralelamente ao branch main, e com o comando "git push origin staging", empurra a nova branch para o repostiório remoto.

### 8 - Agora que a sua divisão está funcionando e você garantiu que não afetou as outras funções, você está apto a fazer um merge request Em seu gitlab, descubra como realizá-lo de acordo com o gitflow.

R: Para realizar o merge, dentro da branch master, executa-se o seguinte comando `git merge "nome-da-branch"`, após isso basta adicionar, comitar e executar o push. Caso ocorra conflitos entre os repositorios, executa-se antes o comando `git pull`, alinhando, dessa forma, ambos os arquivos locais e remotos, deixando tudo pronto para o merge entre a branch principal e secundaria.

### 9 - João quis se redimir dos pecados e fez uma melhoria em seu código, mas ainda assim, continuou fazendo um push na master, faça a seguinte alteração no código e fez o commit com a mensagem: "refactor: calculator abstraction"

```js
var x = args[0];
var y = args[2];
var operator = args[1];

function evaluate(param1, param2, operator) {
  return eval(param1 + operator + param2);
}

if ( console.log( evaluate(x, y, operator) ) ) {}
```

### Para piorar a situação, joão não te contou como executar esse novo código, enquanto você não descobre como executá-lo lendo o código, e seu chefe não descobriu que tudo está comprometido, faça um revert através do seu gitlab para que o produto volte ao normal o quanto antes!

R: Nesse caso basta utilizar o comando `git revert`. Este comando é usado para desfazer alterações ao histórico de commits do repositório, resolvendo o problema.

### 10 - Descubra como executar esse novo código e que operações ele é capaz de realizar. Deixe sua resposta aqui, e explique o que essas funções javascript fazem.

R: A função Eval avalia o expressão de cadeia de caracteres e retorna seu valor. Por exemplo, Eval("1 + 1") retorna 2. Se você passar para a função Eval uma cadeia de caracteres que contém o nome de uma função, a função Eval retornará o valor de retorno da função.

