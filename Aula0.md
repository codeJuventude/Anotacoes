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

* Você pode saber mais vendo a documentação do Python sobre [tipos de dados](https://docs.python.org/3/library/datatypes.html)

# Comentários

* Os comentários são uma maneira de os programadores rastrearem o que estão fazendo em seus programas e até mesmo informar outras pessoas sobre suas intenções em relação a um bloco de código. Resumindo, são anotações para você e outras pessoas que verão seu código!

* Você pode adicionar comentários ao seu programa para poder ver o que seu programa está fazendo. Você pode editar seu código da seguinte forma:

    **# Ask the user for their name**

    **nome = input("Qual seu nome? ")**

    **print("Ola,")**

    **print(nome)**

* Os comentários também podem servir como lista de tarefas para você.