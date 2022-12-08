# O Projeto final

Estamos perto do fim de nosso curso! Por isso, está na hora de produzir o seu projeto final. Lembrando que esse projeto é necessário para que você receba seu certificado!

É possível que você já tenha começado seu projeto, já tenha terminado ou até mesmo nem pensou ainda nele! De qualquer forma, abaixo estão algumas características que seu projeto deve apresentar para que seja aceito.

## Os arquivos do projeto

O seu programa em si vai tomar a forma de um (ou mais) arquivos de código fonte Python. No entanto, um projeto deve apresentar alguns outros arquivos e pastas.

### A pasta principal do projeto

Seu programa não deve ser um arquivo Python solto, ele deve estar dentro de uma pasta! Tal pasta deve ter um nome descritivo que indique do que se trata seu projeto e esse nome não deve conter espaços em branco e nem conter acentos por **exemplo**, um projeto que implemente uma calculadora básica não deve ter sua pasta nomeada `calculadora básica`, mas sim `calculadora_basica` ou alguma variação disso.

### O(s) arquivo(s) fonte

O projeto final deve ser composto por (pelo menos) um arquivo de código em Python. O nome do arquivo principal (ou do arquivo único) deve ser `main.py` e qualquer outro arquivo subsequente deve ter nomes descritivos de sua funcionalidade. Por exemplo, um arquivo que defina funções pode ser chamado de `funcoes.py`. *Veja abaixo sobre os requisitos que seu programa em Python deve seguir*.

### O(s) arquivo(s) de teste

O projeto final deve ser composto por (pelo menos) um arquivo de teste que, quando executado, irá testar se seu projeto de fato funciona como esperado. Os testes devem ser escritos com o framework de testes PyTest, como demontrado durante o curso, ou com outro framework de sua escolha (se este for seu caso, atente-se para a seção de documentação). Você pode ler mais sobre como usar o pytest em sua [documentação](https://docs.pytest.org/en/7.2.x/contents.html).

### O arquivo ReadMe

A pasta principal de seu projeto também deve conter um arquivo chamado `Readme.md` que será onde a documentação do seu projeto será escrita. Mais abaixo, atente-se para um breve guia de o que sua documentação deve conter e de como ela será escrita.

### O arquivo requirements

Esse é importante! Seu projeto precisa de conter um arquivo de texto chamado `requirements.txt` no qual deverão ser listadas TODAS as bibliotecas externas, ou seja, que não sejam nativas ao Python, que você usou, uma em cada linha. Abaixo, estará um exemplo de um arquivo de requisitos.

## Os requisitos!

Existem alguns requisitos para o código de seu projeto estar completo e de acordo com certas convenções importantes no mundo do Python e da programação em geral, segue abaixo:

### A função main

A existência de uma função main não é requisitada pelo Python para que se programa funcione, mas ela é considerada importante para a clareza de qualquer programa mais complexo que um simples "Hello, world". Por isso, seu projeto deve ter em sua estrutura uma função main, tal qual o exemplo abaixo:

```
def main():
    # Funcionalidade da sua função main

def f1():
    # Você pode declarar outras funções, caso queira

# Para que seu programa funcione, essas duas linhas de código são necessárias
if __name__ == "__main__":
    main()
```

Note as duas últimas linhas de código. Quando criamos uma função main com a expressão `def main():` nós estamos apenas `definindo` ela, ou seja, estamos "dizendo" para nosso computador o que ela deve fazer. Mas, para que ela realmente faça o que nos queremos precisamos de `chamá-la`, o que é feito no comando `main()`e dizemos também que ela deve ser chamada apenas se o arquivo em que ela está definida esteja sendo executado, o que é feito pela condicional `if __name__ == "__main__":`.

### Comentários

Cada funcionalidade do seu projeto deve ser comentada, para que um leitor qualquer do seu código consiga perceber, de forma fácil e rápida, o que cada parte do seu código faz! Segue um exemplo:

```
async def join(self, ctx):
    """
    Entra no canal de voz do autor do comando
    """

    # Se o bot já está em um canal de voz, mova-o para o canal do autor
    if ctx.voice_client:
        return await ctx.voice_client.move_to(ctx.author.voice.channel)
        
    # Caso contrário, conecte o bot no canal de voz do autor, conectando-o ao serviço de voz
    await ctx.author.voice.channel.connect()
```

### Condicionais e repetições

Seu projeto deve incluir estruturas condicionais e laços de repetição. Ele não deve ser puramente sequencial.

## Documentação

A documentação do seu projeto não precisa ser muito complexa, mas precisa ser completa, ou seja, toda funcionalidade deve estar explicada na documentação.

### Descrição básica

Sua documentação deve iniciar com uma breve descrição de o que é seu projeto e qual o objetivo dele.

### Como usar 

A próxima seção deve desmonstrar como usar seu programa. Que informações o usuário vai precisar fornecer? Quais argumentos de linha de comando o usuário irá fornecer, se houver?

### Funções

Cada função deverar ser explicitada na documentação e deve incluir nome, descrição da funcionalidade, quais argumentos de argumentos ela recebe e quais os tipos de dados desses argumentos, além dos valores de retorno de cada um

## Markdown

Markdown é uma linguagem de hypertexto muita usada para documentar programas. Apesar de ser um pouco diferente de escrever textos "puros", ela apresenta uma sintaxe simples.

### Criando arquivos markdown
Todo arquivo markdown deve terminar em .md para que ele funcione corretamente. O nome deste arquivo, por exemplo, é "ProjetoFinal.md"

### Títulos

Em markdown, títulos são escritos utilizando uma "#" sem as aspas seguido do título que você deseja, por exemplo: "# Título 1" quando o arquivo pronto é visualizado, se transforma em 
# Título 1

Você pode tornar seus títulos menores da seguinte forma:<br>
"## Título 2" se torna
## Título 2

"### Título 3" se torna
### Título 3

e assim por diante.

### Listas

Você pode criar listas em markdown utilizando uma * no início da linha, da seguinte maneira:

* Isso é um item de lista

### Saiba mais!!!

Caso queira (ou precise) saber mais sobre markdown, visite a [documentação](https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown#open)

# Revisão!!

## Variáveis
Variáveis são como caixinhas que guardam algum tipo de informação e tornam fácil acessar essa informação em qualquer parte do seu programa, pois com elas o seu computador "lembra" onde essa informação está guardada. Toda variável deve ter um nome que descreva qual informação está guardada. Por exemplo, uma variável que guarda um dia de número 21 pode ser chamada de `dia` e podemos guardar o valor 21 dentro dela da seguinte forma:
```
dia = 21
```
A expressão acima é lida como "a variável dia recebe o valor 21".

## Listas

Em Python, listas são uma forma prática de guardarmos mais de um valor, preferencialmente relacionados entre si, em uma única variável, colocando todos os valores dentro de colchetes e separados por vírgula, da seguinte maneira:

```
carro = ["Toyota", 2016]
```

## Dicionários

No exemplo anterior, temos o que podemos supor ser uma variável guardando informações sobre um carro (marca e ano, respectivamente). Nossa suposição estaria correta, mas isso nem sempre será verdade. Existem muitos casos em que não é tão claro supor o que é cada informação. Por esse e outros motivos, dicionários podem ser alternativas atraentes às listas.<br><br>
Dicionários em Python associam certas chaves aos seus respectivos valores, assim como dicionários de português associam palavras aos seus significados. Ao invés de colchetes, usamos chaves para declararmos dicionários e, assim como nas listas, utilizamos vírgulas para separar nossos pares chave-valor, da seguinte forma:

```
carro = {"marca": "Toyota, "ano": 2016}
``` 
## Condicionais
Existem vários momentos em nossas vidas de programadores que nos deparamos com situações em que queremos que certa funcionalidade do nosso código só seja executada se alguma coisa acontecer ou deixar de acontecer, ou seja, se alguma condição for satisfeita.<br>

Em Python, estas condições são declaradas pela palavra "if", que significa "se" em inglês, da seguinte forma:

```
x = 21

if x > 20:
    print("x é maior que 20")
```
Nesse caso, x é 21 e, portanto, maior que 20. Então, o bloco de código dentro da condicional é executado, mas e se x não fosse maior que 20? Podemos usar a palavra "else", que significa "senão em inglês", da seguinte forma:

```
x = 19

if x > 20:
    print("x é maior que 20")
else:
    print("x é menor que 20")
```

Mas e se, em último caso, x seja EXATAMENTE 20? No código acima, o resultado seria "x é menor que 20", o que obviamente não é verdadeiro. Então podemos usar outro artifício, que é a expressão "elif" que é uma redução das palavras "else if", que em inglês significa "senão, se", da seguinte forma:

```
x = 20

if x > 20:
    print("x é maior que 20")

else if x < 20:
    print("x é menor que 20")

else:
    print("x é 20")
```

## Repetições

Outras várias vezes nós precisamos que uma mesma funcionalidade se repita várias vezes. Nos poderíamos escrever o mesmo código várias vezes, mas isso não é bom design. Por isso, usamos o que chamados de estruturas de repetição.

### While

Uma estrutura de repetição se chama while. Ela se assemelha a uma condicional, mas se diferencia pelo fato de que ao invés de o código executar uma única vez que a condição especificada seja `verdadeira`, ele será executado várias vezes até que a condição seja `falsa`, da seguinte maneira:

```
x = 0

while x < 10:
    print(x)
    x += 1
```

Aqui, x começa com um valor 0, o que não satizfaz a condição, o que significa que o código será executado, resultando na impressão do valor de x e no incremento de x por 1. Isso se repete até que x seja igual a 10

### For

A estrutura for também repete um código até que uma condição deixe de ser satisfeita, mas permite um controle mas fino das repetições, por exemplo, digamos que queremos repetir um código EXATAMENTE cingo vezez, faremos o seguinte:

```
for i in range(5):
    print(i)
```
Declaramos uma variável i dentro da estrutura for, que automaticamente terá o valor 0 atribuido a ela, a cada vez que o código é executado, a variável tem seu valor incrementado por 1 até que i = 5, o que é determinado por range(5). Range, em inglês, significa distância.
