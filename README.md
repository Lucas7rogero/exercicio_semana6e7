# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

✅ **<ins>A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.</ins>**

**<ins>JUSTIFICATIVA: A expressão booleana é true porque (p % q === 1) é true, (r * 2 > p) é true, e o "||" mantém o resultado como true. O produto dos valores é calculado corretamente como 29160.</ins>**

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.


______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

✅ **<ins>A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'</ins>**

**<ins>JUSTIFICATIVA: O analisarCredito1() soma os valores até ultrapassar o limite, resultando em saldo de -600 devido ao do...while. analisarCredito2() para antes de ultrapassar o limite, resultando em saldo de -200.</ins>**

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

✅ **<ins>B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".</ins>**

**<ins>JUSTIFICATIVA: A condição verifica corretamente se a idade está entre 18 e 60 anos, imprimindo "Você é um adulto!", e cobre os outros casos de maneira lógica.</ins>**

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:


A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200


B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.


C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.


✅ **<ins>D)
Dispositivo 1 ligado. Energia restante: 900</ins>**

**<ins>Dispositivo 2 ligado. Energia restante: 300</ins>**

**<ins>Dispositivo 3 ligado com bateria extra. Energia restante: 200</ins>**

**<ins>Dispositivo 4 não pode ser ligado. Energia insuficiente.</ins>**

**<ins>Dispositivo 5 não pode ser ligado. Energia insuficiente.</ins>**

**<ins>JUSTIFICATIVA: Os dispositivos 1, 2 e 3 são ligados corretamente usando energia e bateria extra, mas os dispositivos 4 e 5 não podem ser ligados por falta de energia.</ins>**

______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

✅ **<ins>B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.</ins>**

**<ins>JUSTIFICATIVA: O método update() é chamado continuamente a cada quadro para atualizar lógica, movimentação e interações no jogo.</ins>**

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

✅ **<ins>A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.</ins>**

**<ins>JUSTIFICATIVA: O módulo Matter.js é usado para simular física avançada, como colisões, gravidade e forças em jogos.</ins>**

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```
//EX07
constante frete = 800

se (frete maior ou igual 0.0 e frete menor 50.0) então
    escreva("Frete não disponível")
senão se (frete maior 50.0 e frete menor 199.0) então
    escreva("Frete com custo adicional")
senão
    escreva("Frete grátis")
fim
```
**<ins>EXPLICAÇÃO: É verificado o valor do frete e é exibida uma mensagem com base em faixas de valor. Se o frete for entre 0 e 50, informa que o frete não está disponível. Se for entre 50 e 199, diz que há um custo adicional. Se for 199 ou mais, o frete é grátis.</ins>**

______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
    Atributos:
        modelo
        ano
    
    Método Construtor(modelo, ano):
        self.modelo ← modelo
        self.ano ← ano
    
    Método CalcularConsumo():
        Retornar "Método a ser implementado pelas subclasses"

Classe Carro herda de Veiculo:
    Atributos:
        eficiencia
    
    Método Construtor(modelo, ano, eficiencia):
        Chamar Construtor de Veiculo(modelo, ano)
        self.eficiencia ← eficiencia
    
    Método CalcularConsumo(km):
        consumo ← km / self.eficiencia
        Retornar consumo

Classe Moto herda de Veiculo:
    Atributos:
        eficiencia
    
    Método Construtor(modelo, ano, eficiencia):
        Chamar Construtor de Veiculo(modelo, ano)
        self.eficiencia ← eficiencia
    
    Método CalcularConsumo(km):
        consumo ← km / self.eficiencia
        Retornar consumo

carro ← Novo Carro("Sedan", 2022, 12) 
moto ← Nova Moto("Esportiva", 2021, 25)

Escrever "Consumo do carro em 100 km: " + carro.CalcularConsumo(100) + " litros"
Escrever "Consumo da moto em 100 km: " + moto.CalcularConsumo(100) + " litros"

```
**<ins>EXPLICAÇÃO:</ins>**

**<ins>A classe Veiculo define os atributos modelo e ano, e um método genérico CalcularConsumo() para ser sobrescrito pelas subclasses.
A classe Carro herda de Veiculo e implementa CalcularConsumo(km) usando a fórmula:</ins>**

**<ins>consumo = Km / eficiência(km/L)</ins>**

**<ins>A classe Moto herda de Veiculo e implementa o mesmo método com o mesmo cálculo.</ins>**

______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```

```
INÍCIO  
    velocidadeInicial ← Entrada("Informe a velocidade inicial da sonda (m/s): ")  
    velocidadeSegura ← Entrada("Informe a velocidade segura para pouso (m/s): ")  
    desaceleracao ← Entrada("Informe a taxa de desaceleração (m/s²): ")  
    tempoMaximo ← Entrada("Informe o tempo máximo permitido para pouso (s): ")  
    limiteMinimoDesaceleracao ← Entrada("Informe o limite mínimo de desaceleração (m/s²): ")  

    SE desaceleracao < limiteMinimoDesaceleracao ENTAO  
        ESCREVER "Erro: Desaceleração abaixo do limite mínimo permitido."  
        TERMINAR  

    tempo ← 0  

    ENQUANTO velocidadeInicial > velocidadeSegura E tempo < tempoMaximo FAÇA  
        velocidadeInicial ← velocidadeInicial - desaceleracao  
        tempo ← tempo + 1  

    SE velocidadeInicial <= velocidadeSegura ENTAO  
        ESCREVER "Sonda atingiu velocidade segura em " + tempo + " segundos."  
    SENÃO SE tempo >= tempoMaximo ENTAO  
        ESCREVER "Pouso instável!"  
    FIM SE  
FIM
```
**<ins>EXPLICAÇÃO: O código simula a desaceleração de uma sonda em Marte para atingir uma velocidade segura de pouso. Ele reduz a velocidade a cada segundo com base na taxa de desaceleração até atingir a velocidade segura ou ultrapassar o tempo máximo. Se a sonda atingir a velocidade segura dentro do limite de tempo, o pouso é bem-sucedido; caso contrário, é instável.</ins>**
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função MultiplicarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se o número de colunas de matrizA é igual ao número de linhas de matrizB  
    Se tamanho(matrizA[0]) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser multiplicadas. Dimensões incompatíveis."  
    Senão:  
        linhas ← tamanho(matrizA)  
        colunas ← tamanho(matrizB[0])  
        matrizResultado ← novaMatriz(linhas, colunas)  

        # Loop para percorrer e multiplicar os elementos das matrizes  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] ← 0  
                Para k de 0 até tamanho(matrizA[0])-1 faça:  
                    matrizResultado[i][j] ← matrizResultado[i][j] + (matrizA[i][k] * matrizB[k][j])  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 ← [[1000, 2000], [1500, 2500]]  
fatoresCrescimento ← [[1.1, 0.9], [1.2, 1.3]]  

resultadoInvestimentos ← MultiplicarMatrizesInvestimento(investimentosAno1, fatoresCrescimento)  
Escrever("Resultado dos investimentos após fatores de crescimento:")  
ImprimirMatriz(resultadoInvestimentos)  

```
**<ins>EXPLICAÇÃO: É verificado se as matrizes podem ser multiplicadas e confere se o número de colunas da primeira matriz é igual ao número de linhas da segunda. Se puderem ser multiplicadas, ele faz o cálculo multiplicando os valores de cada posição e somando os resultados para formar uma nova matriz. Se não puderem ser multiplicadas, retorna uma mensagem de erro.
