# Bem-vindos(as) à aula 3!!!

![cat](https://imgur.com/a/dT3gAqY)

## Exceções (exceptions)

* Exceções são coisas que dão errado no nosso código.

* Em nosso terminal, digitamos code ola.py para criar um novo arquivo. Escreva o que está embaixo (includindo erros).

```
    print("Ola, mundo)
```
* Note que deixamos as aspas abertas

* Ao executarmos **python ola.py** no terminal, um erro vai ocorrer. O compilador afirma que é um “syntax error”, que traduz para "erro de sintaxe". Erros de sintaxe são aqueles que exigem que você verifique novamente se digitou seu código corretamente.

* Aprenda mais na documentação do python sobre [erros e exceções](https://docs.python.org/pt-br/3/tutorial/errors.html).

## Runtime errors

* Erros de tempo de execução referem-se àqueles criados por comportamento inesperado em seu código. Por exemplo, talvez você pretenda que um usuário insira um número, mas ele insere um caractere. Seu programa pode gerar um erro devido a essa entrada inesperada do usuário.

* No terminal, execute **code numero.py**. Digite o seguinte no arquivo:

```
    x = int(input("O que é x? "))
    print(f"x é {x}")
```

* Como programadores, devemos ser defensivos para garantir que nossos usuários estejam inserindo o que esperávamos. Podemos considerar “casos de limite” como -1, 0 ou gato.

* Se executarmos este programa e digitarmos “gato”, veremos de repente **ValueError: literal invalid for int() com base 10: 'gato'** Essencialmente, o interpretador Python não gosta que passamos “gato” para a função print.

* Uma estratégia eficaz para corrigir esse erro potencial seria criar um “tratamento de erros” para garantir que o usuário se comporte como pretendemos.

* Aprenda mais na documentação do python sobre [erros e exceções](https://docs.python.org/pt-br/3/tutorial/errors.html).

# **try**

* Em Python **try** e **except** são formas de testar a entrada do usuário antes que algo dê errado. Modifique seu código da seguinte forma:

```
    try:
        x = int(input("O que é x?"))
        print(f"x é {x}")
    except ValueError:
        print("x não é inteiro")
```

* Observe como, executando este código, a entrada de 50 será aceita. No entanto, digitar gato produzirá um erro visível para o usuário, e o irá informar que a entrada não foi aceita e por que.

* Esta ainda não é a melhor maneira de implementar este código. Observe que estamos tentando fazer duas linhas de código. Para melhor prática, devemos tentar apenas o menor número possível de linhas de código que nos preocupem que possam falhar. Ajuste seu código da seguinte forma:

```
    try:
        x = int(input("O que é x?"))
    except ValueError:
        print("x não é inteiro")
    
    print(f"x é {x}")
```

* Observe que, embora isso atinja nosso objetivo de tentar o menor número de linhas possível, agora enfrentamos um novo erro! Enfrentamos **um NameError** onde **x is not defined**. Observe este código e considere: Por que x não é definido em alguns casos?

* De fato, se você examinar a ordem das operações em **x = int(input("O que é x?"))**, trabalhando da direita para a esquerda, poderia pegar um caractere inserido incorretamente e tentar atribuí-lo como um inteiro. Se isso falhar, a atribuição do valor de x nunca ocorre. Portanto, não há x para imprimir em nossa linha final de código.

## **Else**

* Acontece que existe outra maneira de implementar o **try** que pode capturar erros dessa natureza.

* Ajuste seu código da seguinte forma:

```
    try:
        x = int(input("O que é x?"))
    except ValueError:
        print("x não é inteiro")
    else:
        print(f"x é {x}")
```

* Observe que, se nenhuma exceção ocorrer, ele executará o bloco de código dentro de else. Executando python number.py e fornecendo 50, você notará que o resultado será impresso. Tentando novamente, desta vez fornecendo cat, você notará que o programa agora detecta o erro.

* Pensando em melhorar nosso código, observe que estamos sendo um pouco rudes com nosso usuário. Se nosso usuário não cooperar, atualmente simplesmente encerramos nosso programa. Considere como podemos usar um loop para solicitar ao usuário x e se ele não solicitar novamente! Melhore seu código da seguinte forma:

```
    while True:
        try:
            x = int(input("What's x?"))
        except ValueError:
            print("x is not an integer")
        else:
            break

    print(f"x is {x}")
```

* Observe que while True fará um loop para sempre. Se o usuário conseguir fornecer a entrada correta, podemos sair do loop e imprimir a saída. Agora, um usuário que insere algo incorretamente será solicitado a inserir novamente.

# Criando uma função para ler um inteiro

* Certamente, muitas vezes gostaríamos de obter um inteiro do nosso usuário. Modifique seu código da seguinte forma:

```
    def main():
        x = ler_int()
        print(f"x é {x}")


    def ler_int()
        while True:
            try:
                x = int(input("O que é x?"))
            except ValueError:
                print("x não é inteiro")
            else:
                break
        return x


    main()
```

* Observe que estamos manifestando muitas grandes propriedades. Primeiro, abstraímos a capacidade de obter um número inteiro. Agora, todo este programa se resume às três primeiras linhas do programa.

* Mesmo assim, podemos melhorar este programa. Considere o que mais você poderia fazer para melhorar este programa. Modifique seu código da seguinte forma:

```
    def main():
        x = ler_int()
        print(f"x é {x}")


    def ler_int()
        while True:
            try:
                x = int(input("O que é x? "))
            except ValueError:
                print("x não é inteiro")
            else:
                return x


    main()
```

* Observe que return não apenas o tirará de um loop, mas também retornará um valor.

* Algumas pessoas podem argumentar que você poderia fazer o seguinte:

```
    def main():
        x = ler_int()
        print(f"x é {x}")


    def ler_int()
        while True:
            try:
                return int(input("O que é x? "))
            except ValueError:
                print("x não é inteiro")

    main()
```

* Observe que isso faz a mesma coisa que a iteração anterior do nosso código, simplesmente com menos linhas.

## **pass**

* Podemos fazer com que nosso código não avise nosso usuário, mas simplesmente faça novamente nossa pergunta de solicitação modificando nosso código da seguinte maneira:

```
    def main():
        x = ler_int()
        print(f"x é {x}")


    def ler_int()
        while True:
            try:
                return int(input("O que é x? "))
            except ValueError:
                pass

    main()
```

* Observe que nosso código ainda funcionará, mas não informará repetidamente ao usuário sobre seu erro. Em alguns casos, você desejará deixar bem claro para o usuário qual erro está sendo produzido. Outras vezes, você pode decidir que simplesmente quer pedir a opinião deles novamente.

* Um refinamento final que poderia melhorar a implementação dessa função **ler_int**. No momento, observe que estamos confiando no sistema de honra que x está nas funções main e **ler_int**. Provavelmente, queremos passar um prompt que o usuário veja quando solicitado. Modifique seu código da seguinte maneira.

```
    def main():
        x = ler_int("O que é x?" )
        print(f"x é {x}")


    def ler_int(prompt)
        while True:
            try:
                return int(input(prompt))
            except ValueError:
                pass

    main()
```

* Aprenda mais na documentação do python sobre [**pass**](https://docs.python.org/pt-br/3/tutorial/controlflow.html#pass-statements)