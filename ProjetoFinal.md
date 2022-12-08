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

## Breve revisão

Segue abaixo uma breve revisão dos conceitos básicos vistos durante o curso:
