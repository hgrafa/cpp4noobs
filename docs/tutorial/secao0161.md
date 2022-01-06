# 16.1 - Aplicando a Big O Notation

Aplicar *big O notation* é uma tarefa razoavelmente simples, depois de entendermos seus conceitos, e esse é nosso objetivo neste módulo. Vamos ver alguns exemplos isolados para entender o seu funcionamento:

## Aprofundando nos cálculos da *Big O*

Usaremos `f` como a função que denota a quantidade de operações de cada programa em função dos `input`'s.

**exemplo 1:**

> input: `n` e `f(n) = n+15` 

> Consequentemente: `f(n)` pertence a `O(n)`.


Novamente, a *Big O* é um conjunto capaz de representar um conjunto de funções. Pra entender para onde foram as constantes do exemplo acima, **basta nos concentrarmos no estudo dos piores casos**.

Para o exemplo acima, é trivial, pois basta perceber que a medida que `n` cresce que as constantes começam a se tornarem irrelevantes.


| valor de `n` | `f(n) = n+15`| `g(n) = n` | erro cometido |
| :----------: | :----------: | :----------: |:----------: |
| 10^2 | 115 | 100 | +15% |
| 10^4 | 10015 | 10000 | +0.15% |
| 10^6 | 1000015 | 1000000 | +0.001% |

> Ficou mais fácil entender porque constantes não fazem tanta diferença?

De modo geral, seja `f(n) = ax+b`, `f` vai pertencer a `O(n)`.  

**exemplo 2:**

> input: `n` e `f(n)  = n*log(n) + n`

> `f(n)` pertence a `O(n*log(n))`



## Tabela de funções - *Big O notation*

## *Big O notation* nos códigos

### 0. Complexidade constante - `O(1)`

### 1. Complexidade linear - `O(n)`

### 2. Complexidade quadrática - `O(n^2)`

### 3. Complexidade logarítmica - `O(log(n))` e `O(n*log(n))`

### 4. Complexidade exponencial - `O(2^n)`


<br>
--------
### Notas e referências

Se você for iniciante e não entender os tópicos abaixo, não se sinta mal o objetivo é deixá-los como oportunidade aprofundamento.

 Olhar notação assintótica como estudo dos piores casos não torna inválida a [definição formal da *Big O*](https://en.wikipedia.org/wiki/Big_O_notation#:~:text=Big%20O%20notation%20is%20a,a%20particular%20value%20or%20infinity.&text=In%20computer%20science%2C%20big%20O,as%20the%20input%20size%20grows.). Na verdade, com base na definição:

> Se `f(m) <= c*g(m)` para todo `m >= n`

> então, `f(n)` pertence a `O( g(n) )`

isto é, temos que a partir de algum valor `m` a ser descoberto, a função seria limitada superiormente por `g(n)` e essa seria sua complexidade.

 Entretanto, se olharmos para os piores casos, com grandes valores de entrada, iremos ***extrapolar*** o `m` mínimo e consequentemente **também é possível utilizar este método para o cálculo de complexidade**.

