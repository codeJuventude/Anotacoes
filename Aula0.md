# Bem-vindos(as) à aula 0!

![cat](https://user-images.githubusercontent.com/98218660/190912063-634fd535-7490-476c-9993-470b7c46699f.gif)

# O Editor de código

* Para fazermos nossos programas precisamos de um editor de código. Poderiamos usar aqueles conhecidos, como o Word, mas como queremos fazer programas e não documentos, vamos utilizar um editor feito para isso! O Visual Studio Code, um compilador!

* O Visual Studio Code (ou VS Code) é disponibilizado gratuitamente pela Microsoft e é um dos editores de texto mais famoso para programação, já que ele é muito customizável e aceita praticamente todas as linguagens de programação!

* Para instalar o VS Code, basta ir até [VSCODE](https://code.visualstudio.com/Download) e baixar o arquivo.

# Criando programas com Python

* Na parte de baixo do VS Code, você pode ver um terminal. Execute o comando **code ola.py** para começar a programar.

* No arquivo que foi aberto, você pode digitar **print("Olá, mundo!")**. Esse é um programa muito famoso, que praticamente todo programador já fez quando começam a aprender!

* Após isso, clique de novo no terminal e digite o comando **python ola.py**. Isso vai __interpretar__ e __executar__ seu programa. Vamos entender mais sobre isso nas aulas!

* O resultado do seu programa deve ser que a frase **Olá, mundo!** aparece escrita na tela.

* Parabéns! Você criou seu primeiro programa.

# Funções

* Funções são ações que o computador sabe fazer.

* No seu programa **ola.py**, a função **print** sabe como imprimir (escrever) coisas na tela.

* A função **print** aceita argumentos. Nesse caso **"Olá, mundo!"** é o argumento que ela aceita.

# Bugs

* Bugs são erros no código e uma parte natural de programar. Erros fazem parte do processso de aprendizagem. Lembrem-se: quantos mais erros vocês cometerem agora, menos erros irão cometer no futuro!

* Por exemplo, se em **ola.py** vocÊ digitar **print("Olá, mundo!"**, note que você esqueceu do **)** no fim. Assim, o computador não vai conseguir entender o que você quer dizer e o programa vai dar erro!

* Muitas vezes, os erros são mostrados por meio de mensagens que dão dicas de como resolver o problema!

# Melhorando sseu primeiro programa

* Podemos personalizar seu primeiro programa em Python.

* Em nosso editor de texto em **hello.py** podemos adicionar outra função. **input** é uma função que recebe um pedido como argumento. Podemos editar nosso código para dizer.

    **input("Qual seu nome? ")**
**print("Olá, mundo!")**

* Esta edição por si só, no entanto, não permitirá que seu programa produza o que seu usuário insere. Para isso, precisaremos apresentar as variáveis

# Variáveis

* Uma variável é um contâiner para alguma informação no seu programa. Da mesma forma que uma gaveta guarda uma meia, uma variável guarda uma informação.

* Em seu programa, você pode introduzir sua própria variável em seu programa editando-a para ler um nome, por exemplo!

    **nome = input("Qual seu nome? ")**
**print("Olá, mundo!")**

    Observe que este sinal de igual **=** no meio de **nome = input("Qual seu nome?")** tem um papel especial na programação. Este sinal de igual literalmente atribui o que está à direita ao que está à esquerda. Portanto, o valor retornado por **input("Qual seu nome?")** é atribuído a **nome**.

* Se você editar seu código da seguinte forma, você notará um erro

    **nome = input("Qual seu nome? ")**
**print("Olá, nome!")**

* O programa retornará **Olá, nome!** na janela do terminal, independentemente do que o usuário digitar.

* Editando ainda mais nosso código, você pode digitar

    **nome = input("Qual seu nome? ")**
    
    **print("Olá,")**

    **print(nome)**

* O resultado no terminal deve ser

    **Qual seu nome? Daniel**
**Olá,**
**Daniel**

* Estamos chegando mais perto do resultado que queremos

* Você pode saber mais vendo a documentação do Python sobre [tipos de dados](https://docs.python.org/pt-br/3/library/datatypes.html)

# Comentários

* Os comentários são uma maneira de os programadores rastrearem o que estão fazendo em seus programas e até mesmo informar outras pessoas sobre suas intenções em relação a um bloco de código. Resumindo, são anotações para você e outras pessoas que verão seu código!

* Você pode adicionar comentários ao seu programa para poder ver o que seu programa está fazendo. Você pode editar seu código da seguinte forma:

    **# Ask the user for their name**

    **nome = input("Qual seu nome? ")**

    **print("Ola,")**

    **print(nome)**

* Os comentários também podem servir como lista de tarefas para você.

# Pseudocódigo

* O pseudocódigo é um tipo importante de comentário que se torna um tipo especial de lista de tarefas, especialmente quando você não entende como realizar uma tarefa de codificação. Por exemplo, em seu código, você pode editar seu código para dizer:

    **# Perguntar o nome do usuário**
    **nome = input("Qual seu nome? ")**

    **# Imprimir olá**
    **print("Olá,")**

    **# Imprimir nome de entrada**
    **print(nome)**

# Melhorando ainda mais seu programa

* Podemos editar mais nosso código:

    **# Perguntar o nome do usuário**
    **nome = input("Qual seu nome? ")**

    **# Imprimir olá + nome**
    **print("hello, " + nome)**

* Acontece que algumas funções podem receber mais de um argumento

* Podemos usar uma vírgula **,**

    **# Perguntar nome do usuário**
    **nome = input("Qual seu nome? ")**

    **# Imprimir olá e o nome**
    **print("Olá,", nome)**

# Strings e parâmetros

 * Uma string é uma sequência de caracteres, uma sequência de texto, abreviada como **str**

 * Voltando um pouco em nosso código, houve um efeito colateral visual de ter o resultado aparecendo em várias linhas:

    **# Perguntar o nome do usuário**
    **nome = input("Qual seu nome? ")**

    **# Imprimir olá**
    **print("Olá,")**

    **# Imprimir nome de entrada**
    **print(nome)**

* As funções recebem argumentos que influenciam seu comportamento. Se examinarmos a documentação para impressão, você notará que podemos aprender muito sobre os argumentos que a função de impressão usa.

* Observando esta documentação, você aprenderá que a função de impressão inclui automaticamente um parâmetro código end='\n'. Este \n indica que a função de impressão criará automaticamente uma quebra de linha quando executada. A função print recebe um argumento chamado end` e o padrão é criar uma nova linha.

* No entanto, podemos tecnicamente fornecer um argumento para nós mesmos, de modo que uma nova linha não seja criada!

* Podemos modificar nosso código da seguinte forma:

    **# Perguntar nome**
    **nome = input("Qual seu nome? ")**
    **print("Olá,", end="")**
    **print(nome)**

    Ao fornecer end="" estamos modificando o valor padrão de **end** de forma que ele nunca crie uma nova linha após esta primeira instrução de impressão. Fornecendo o nome como “Daniel”, a saída na janela do terminal será "Olá, Daniel".

* Você pode aprender mais na documentação do Python sobre [print](https://docs.python.org/pt-br/3/library/functions.html#print).

# Formatando strings

* A maneira mais elegante de usar strings é a seguinte:

    **# Perguntar nome**
    **nome = input("Qual seu nome? ")**
    **print(f"hello, {name}")**

    Observe o **f** em **print(f"hello, {name}")**. Este **f** é um indicador especial para o Python tratar essa string de uma maneira especial, diferente das abordagens anteriores que ilustramos nesta aula. Espere que você usará esse estilo de strings com bastante frequência neste curso.

# Mais sobre strings

* Nunca espere que o usuário do seu prgrama vai ultilizá-lo como você espera. Então, é importante verificar os valores de entrada!

* Acontece que temos a habilidade de remover espaços extra em strings

* Utilizamos o *método* **strip** em **nome**, assim: **nome = nome.strip()**. Isso vai remover qualquer espaço em branco antes e depois de nossa string:

    **# Perguntar nome**
    **nome = input("Qual seu nome?? ")**

    **# Remover espaços da str**
    **nome = nome.strip()**

    **# Imprimir**
    **print(f"Olá, {nome}")**

* Se utilizarmos o método **title**, o nosso nome será capitalizado, ou seja, a primeira letra será transformada em maiúscula

    **# Perguntar nome**
    **nome = input("Qual seu nome?? ")**

    **# Remover espaços da str**
    **nome = nome.strip()**

    **# Capitalizar a primeira letra de cada palavra**
    **name = name.title()**

    **# Imprimir**
    **print(f"Olá, {nome}")**

* Podemos fazer o mesmo assim:

    **# Perguntar nome**
    **nome = input("Qual seu nome? ")**

    **# Remover espaços da str e Capitalizar a primeira letra de cada palavra**
    **nome = nome.strip().title()**

    **# Imprimir**
    **print(f"Olá, {nome}")**

* E podemos fazer mais ainda!

    **# Remover espaços da str e Capitalizar a primeira letra de cada palavra**
    **nome = intput(nome).strip().title()**

    **# Imprimir**
    **print(f"Olá, {nome}")**

* Visite a documetação do Python em [str](https://docs.python.org/3/library/stdtypes.html#str)

# Inteiros (int)

* Os números inteiros (todos os números exatos, sem vírgula) são chamados de **int** no mundo da programação

* No mundo da matemática, estamos familiarizados com os operadores +, -, *, / e %. Esse último operador **%** ou operador de módulo pode não ser muito familiar para você.

* Você não precisa usar a janela do editor de texto em seu compilador para executar o código Python. No seu terminal, você pode executar o python sozinho. Você será presenteado com >>> na janela do terminal. Você pode então executar código interativo ao vivo. Você pode digitar 1 + 1 e ele executará esse cálculo. Este modo não será comumente usado durante este curso.

* Agora, vamos digitar no terminal **code calculator.py** para criar um novo arquivo python.

* Agora vamos fazer uma caluladora simples

    **x = 1**
    **y = 2**

    **z = x + y**

    **print(z)**

    Naturalmente, o resultado será 3 quando executarmos **python calculator.py**

* Podemos tornar nosso programa mais interessante usando a função **input**

    **x = input("x? ")**
    **y = input("y? ")**

    **z = x + y**

    **print(z)**

    Note que agora o resultado é 12! Por que será?

 * Nós já sabemos que **+** junta duas strings e porque sua entrada chega para o programa como texto, o python acha que nós queremos juntar dois textos e não somar dois números!

 * Precisamos indicar que o valor que queremos guardar não é texto, mas sim um inteiro!!

    **x = input("x? ")**
    **y = input("y? ")**

    **z = int(x) + int(y)**

    **print(z)**

* Podemos melhorar nosso programa com:

    **x = int(input("x? "))**
    **y = int(input("y? "))**

    **print(x + y)**

# Legibilidade importa!

* Ao decidir sobre sua abordagem para uma tarefa de programação, lembre-se de que pode-se fazer um argumento razoável para muitas abordagens para o mesmo problema.

* Independentemente de qual abordagem você adota para uma tarefa de programação, lembre-se de que seu código deve ser legível. Você deve usar comentários para dar a si mesmo e aos outros pistas sobre o que seu código está fazendo. Além disso, você deve criar código de forma legível.

# Float

* Um valor de ponto flutuante é um número que contém um ponto (equivalente à vírgula em português), tal como **0.52**

* Podemos mudar nosso código para o seguinte

    **x = float(input("x? "))**
    **y = float(input("y? "))**

    **print(x + y)**

* Podemos arredondar nosso valor assim:

    **x = float(input("x? "))**
    **y = float(input("y? "))**

    **# Arredondar**

    **z = round(x + y)**

    **print(z)**

* Em português, gostamos de usar vírgulas ao invés de pontos, podemos fazer isso assim:

    **x = float(input("x? "))**
    **y = float(input("y? "))**

    **# Arredondar**

    **z = round(x + y)**

    **print(f"{z:,}")**

* Podemos arredondar números float de outra forma!

    **x = float(input("x? "))**
    **y = float(input("y? "))**

    **# Arredondar**

    **z = round(x / y , 2)**

    **print(z)**

    Ou então, usando a **fstring**:
    **x = float(input("x? "))**
    **y = float(input("y? "))**

    **# Arredondar**

    **z = round(x / y)**

    **print(f"{z:.2f}")**

* Saiba mais em [float](https://docs.python.org/3/library/functions.html?highlight=float#float)

# Def

* Nós aprendemos que podemos usar funções em python, mas podemos também criar funções!! Legal, né?

* Vamos voltar em **hello.py**, apagar todo o código e começar do início:

    **nome = input("Qual seu nome? ")**
    **ola()**
    **print(nome)**

    Esse código não funciona, afinal não existe função **ola** em python

* Vamos criar nossa própria função!
    **def ola():**
        **print("Olá, ")**
    **nome = input("Qual seu nome? ")**
    **ola()**
    **print(nome)**

    Observe que tudo em **def hello()** é indentado. Python é uma linguagem indentada. Ele usa recuo para entender o que faz parte da função acima. Portanto, tudo na função hello deve ser recuado. Quando algo não é recuado, ele o trata como se não estivesse dentro da função hello. Executando python hello.py na janela do terminal, você verá que sua saída não é exatamente como você deseja.

* Podemos melhorar nosso código!

    **def ola(para):**
        **print("para,", para)**


    **# Imprimir usando nossa função**
    **nome = input("Qual seu nome? ")**
    **ola(nome)**

* Podemos dar um valor padrão para nossa função
    **def ola(para="mundo"):**
        **print("Olá,", para)**


    **# Imprimir usando nossa função**
    **nome = input("Qual seu nome? ")**
    **ola(nome)**

    **Imprimir com valor padrão**
    **ola()**

* Geralmente é melhor colocarmos nossas funções na parte debaixo do nosso código, para melhorar a organização, mas isso só é possível se criarmos uma função **main** com a parte principal do nosso programa

    **def main():**
        **# Imprimir usando nossa função**
        **nome = input("Qual seu nome? ")**
        **ola(nome)**
        **Imprimir com valor padrão**
        **ola()**

    **def ola(para="mundo"):**
        **print("Olá,", para)**

* Note que só isso não é o sufuciente, para nosso programa funcionar precisamos executar a função main além de definí-la. Fazemos isso assim:

    **def main():**
        **# Imprimir usando nossa função**
        **nome = input("Qual seu nome? ")**
        **ola(nome)**
        **Imprimir com valor padrão**
        **ola()**

    **def ola(para="mundo"):**
        **print("Olá,", para)**
    
    **main()**

# Retornando valores

* Podemos imaginar que nós queremos que uma função não só realize uma ação, mas **retorne** um valor

* Vamos imaginar um programa que calcula um número **n** elevado ao quadrado:

    **def main():**
        **x = int(input("x? "))**
        **print("x ao quadrado é", quadrado(x))**


    **def quadrado(n):**
        **return n * n**


    **main()**

    Em essência, o valor de **x** é passado para **quadrado** como argumento, então **quadrado** calcula o valor de x elevado ao quadrado e retorna esse valor!

![cat](https://user-images.githubusercontent.com/98218660/190912063-634fd535-7490-476c-9993-470b7c46699f.gif)


