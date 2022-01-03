# 16.1 - Análise de Complexidade (Big O Notation)

Analisar a complexidade de um algoritmo é uma tarefa importante para entender as limitações associadas ao código. Podemos encontrar mais desse tema através dos nomes *análise assintótica* ou *Big O Notation*.

Não conseguimos fazer uma analise precisa do tempo, pois depende de fatores particulares da entrada. Entretanto, conseguimos medir a complexidade **em função dos parâmetros da entrada.**

## Primeiro passo: **Contando operações**

Vamos estudar particularmente a [**sequência de fibonacci**](https://pt.wikipedia.org/wiki/Sequ%C3%AAncia_de_Fibonacci#:~:text=Os%20n%C3%BAmeros%20de%20Fibonacci%20s%C3%A3o,%2C%202584%2C%20...%20.). Simplificando o problema: temos uma sequência que inicialmente {0, 1} e todo próximo número dessa sequência é definido como soma dos dois antecessores.

Ex.: {0 , 1 , 1 , 2 , 3 , 5 , 8, ... }

1ª implementação - ***botton up***: definimos os casos base e iremos escalando até chegarmos no resultado desejado.

```cpp{0}
// @he4rt developers - Hugo Rafael

#include <iostream>

int main()
{

  int n; // inteiro n
  std::cin >> n; // dou entrada em n

  // crio a sequencia e seus casos base
  int fibonacci[n+1];
  fibonacci[0] = 0; // caso base para zero
  fibonacci[1] = 1; // caso base para um

  for(int i=2; i<=n; i++)
  { // faço os calculos a partir do segundo
    fibonacci[i] = fibonacci[i-1] + fibonacci[i-2]; // escalo com as repostas
  }

  std::cout << fibonacci[n] << std::endl; // reposta

}
```

2ª implementação - ***top down:*** Utilizando funções recursivas até chegar nos casos base.

```cpp{0}
// @he4rt developers - Hugo Rafael

#include <iostream>

int fibonacci(int n)
{

  if(n==0) return 0; // caso base para o zero
  if(n==1) return 1; // caso base para o um

  return fibonacci(n-1) + fibonacci(n-2); // algoritmo recursivo
}

int main()
{

  int n; // inteiro n
  std::cin >> n; // dou entrada em n

  std::cout << fib(n) << std::endl; // resposta

}
```

Para a 1ª implementação, temos 2 operações feitas para atribuir os casos base do array e depois temos um for que faz n-1 operações, indo de 2 até n(inclusive). 

Para

> Conseguiu notar que o número de operações é uma função de n?

Se sim, agora você deu o primeiro passo para entender a **Big O Notation**.

> Consegue notar a diferença dessas implementações?
