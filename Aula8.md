# Aula 8: Programação Orientada a Objetos

![cat](https://imgur.com/XxaF5DB.gif)
<br><br>
## OOP

* Existem diferentes paradigmas de programação. Ao aprender outras linguagens, você começará a reconhecer padrões como esses.

* Até este ponto, você trabalhou processualmente passo a passo.

* A programação orientada a objetos (OOP) é ​​uma solução atraente para problemas relacionados à programação.

* Para começar, digite ```code student.py``` na janela do terminal e codifique da seguinte maneira:

```
name = input("Name: ")
house = input("House: ")
print(f"{name} from {house}")
```

Observe que este programa segue um paradigma processual, passo a passo: Muito parecido com o que você viu nas partes anteriores deste curso.

* Com base em nosso trabalho das semanas anteriores, podemos criar funções para abstrair partes deste programa.

```
def main():
    name = get_name()
    house = get_house()
    print(f"{name} from {house}")


def get_name():
    return input("Name: ")


def get_house():
    return input("House: ")


if __name__ == "__main__":
    main()
```

Observe como get_name e get_house abstraem algumas das necessidades de nossa função principal. Além disso, observe como as linhas finais do código acima informam ao compilador para executar a função principal.

* Podemos simplificar ainda mais nosso programa armazenando o aluno como uma ```tuple```. Uma ```tuple``` é uma sequência de valores. Ao contrário de uma ```list```, uma ```tuple``` não pode ser modificada. Em essência, estamos devolvendo dois valores.

```
def main():
    name, house = get_student()
    print(f"{name} from {house}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return name, house


if __name__ == "__main__":
    main()
```

Observe como ```get_student``` retorna ```nome, casa```.

* Empacotando essa ```tuple```, de forma que possamos retornar ambos os itens para uma variável chamada aluno, podemos modificar nosso código da seguinte maneira.

```
def main():
    student = get_student()
    print(f"{student[0]} from {student[1]}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return (name, house)


if __name__ == "__main__":
    main()
```

Observe que ```(nome, casa)``` diz explicitamente a qualquer um que esteja lendo nosso código que estamos retornando dois valores dentro de um. Além disso, observe como podemos indexar em ```tuple```s usando ```aluno[0]``` ou ```aluno[1]```.

* as ```tuple```s são imutáveis, o que significa que não podemos alterar esses valores. A imutabilidade é uma maneira pela qual podemos programar defensivamente.

```
def main():
    student = get_student()
    if student[0] == "Padma":
        student[1] = "Ravenclaw"
    print(f"{student[0]} from {student[1]}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return name, house


if __name__ == "__main__":
    main()
```

Observe que esse código produz um erro. Como as ```tuple```s são imutáveis, não podemos reatribuir o valor de ```aluno[1]```.

* Se quiséssemos fornecer flexibilidade aos nossos colegas programadores, poderíamos utilizar uma ```list``` como a seguir.

```
def main():
    student = get_student()
    if student[0] == "Padma":
        student[1] = "Ravenclaw"
    print(f"{student[0]} from {student[1]}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return [name, house]


if __name__ == "__main__":
    main()
```

Observe que as listas são mutáveis. Ou seja, a ordem da ```casa``` e do ```nome``` pode ser trocada por um programador. Você pode decidir utilizar isso em alguns casos em que deseja fornecer mais flexibilidade ao custo da segurança do seu código. Afinal, se a ordem desses valores for variável, os programadores que trabalham com você podem cometer erros no futuro.

* Um dicionário também pode ser utilizado nesta implementação. Lembre-se de que os dicionários fornecem um par chave-valor.

```
def main():
    student = get_student()
    print(f"{student['name']} from {student['house']}")


def get_student():
    student = {}
    student["name"] = input("Name: ")
    student["house"] = input("House: ")
    return student


if __name__ == "__main__":
    main()
```

Observe que, neste caso, dois pares de valor-chave são retornados. Uma vantagem dessa abordagem é que podemos indexar nesse dicionário usando as chaves.

* Ainda assim, nosso código pode ser melhorado ainda mais. Observe que há uma variável desnecessária. Podemos remover aluno = {} porque não precisamos criar um dicionário vazio.

```
def main():
    student = get_student()
    print(f"{student['name']} from {student['house']}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return {"name": name, "house": house}


if __name__ == "__main__":
    main()
```

Observe que podemos utilizar chaves ```{}``` na instrução return para criar o dicionário e retorná-lo na mesma linha.

* Podemos fornecer nosso caso especial com Padma em nossa versão de dicionário de nosso código.

```
def main():
    student = get_student()
    if student["name"] == "Padma":
        student["house"] = "Ravenclaw"
    print(f"{student['name']} from {student['house']}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return {"name": name, "house": house}


if __name__ == "__main__":
    main()
```

Observe como, semelhante em espírito às nossas iterações anteriores deste código, podemos utilizar os nomes das chaves para indexar em nosso dicionário do aluno.

## Classes

* As classes são uma maneira pela qual, na programação orientada a objetos, podemos criar nosso próprio tipo de dados e dar-lhes nomes.

*  Uma classe é como um molde para um tipo de dado – onde podemos inventar nosso próprio tipo de dado e dar um nome a ele.

* Podemos modificar nosso código da seguinte maneira para implementar nossa própria classe chamada ```Aluno```:

```
class Student:
    ...


def main():
    student = get_student()
    print(f"{student.name} from {student.house}")


def get_student():
    student = Student()
    student.name = input("Name: ")
    student.house = input("House: ")
    return student


if __name__ == "__main__":
    main()
```

Observe por convenção que Aluno é capitalizado. Além disso, observe que ... simplesmente significa que retornaremos mais tarde para concluir essa parte do nosso código. Além disso, observe que em get_student, podemos criar um aluno da classe Aluno usando a sintaxe aluno = Aluno(). Além disso, observe que utilizamos “notação de ponto” para acessar os atributos dessa variável aluno da classe Aluno.

* Sempre que você cria uma classe e utiliza esse projeto para criar algo, você cria o que é chamado de “objeto” ou “instância”. No caso do nosso código, aluno é um objeto.

* Além disso, podemos estabelecer algumas bases para os atributos que são esperados dentro de um objeto cuja classe é Aluno. Podemos modificar nosso código da seguinte maneira:

```
class Student:
    def __init__(self, name, house):
        self.name = name
        self.house = house


def main():
    student = get_student()
    print(f"{student.name} from {student.house}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    student = Student(name, house)
    return student


if __name__ == "__main__":
    main()
```

Notice that within Student, we standardize the attributes of this class. We can create a function within class Student, called a “method”, that determines the behavior of an object of class Student. Within this function, it takes the name and house passed to it and assigns these variables to this object. Further, notice how the constructor student = Student(name, house) calls this function within the Student class and creates a student. self refers to the current object that was just created.

* Podemos simplificar nosso código da seguinte maneira:
```
class Student:
    def __init__(self, name, house):
        self.name = name
        self.house = house


def main():
    student = get_student()
    print(f"{student.name} from {student.house}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return Student(name, house)


if __name__ == "__main__":
    main()
```

Observe como return Aluno(nome, casa) simplifica a iteração anterior de nosso código em que a instrução do construtor foi executada em sua própria linha.

## raise

* O programa orientado a objetos encoraja você a encapsular toda a funcionalidade de uma classe dentro da definição de classe. E se algo der errado? E se alguém tentar digitar algo aleatório? E se alguém tentar criar um aluno sem nome? Modifique seu código da seguinte maneira:

```
class Student:
    def __init__(self, name, house):
        if not name:
            raise ValueError("Missing name")
        if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
            raise ValueError("Invalid house")
        self.name = name
        self.house = house


def main():
    student = get_student()
    print(f"{student.name} from {student.house}")


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return Student(name, house)


if __name__ == "__main__":
    main()
```

Observe como verificamos agora que um nome é fornecido e uma casa adequada é designada. Acontece que podemos criar nossas próprias exceções que alertam o programador sobre um possível erro criado pelo usuário chamado raise. No caso acima, levantamos ValueError com uma mensagem de erro específica.

* Acontece que o Python permite que você crie uma função específica pela qual você pode imprimir os atributos de um objeto. Modifique seu código da seguinte maneira:

```
class Student:
    def __init__(self, name, house, patronus):
        if not name:
            raise ValueError("Missing name")
        if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
            raise ValueError("Invalid house")
        self.name = name
        self.house = house
        self.patronus = patronus

    def __str__(self):
        return f"{self.name} from {self.house}"


def main():
    student = get_student()
    print(student)


def get_student():
    name = input("Name: ")
    house = input("House: ")
    patronus = input("Patronus: ")
    return Student(name, house, patronus)


if __name__ == "__main__":
    main()
```

Observe como def ```__str__(self)``` fornece um meio pelo qual um aluno é retornado quando chamado. Portanto, agora você pode, como programador, imprimir um objeto, seus atributos ou quase tudo o que desejar relacionado a esse objeto.

* ```__str__``` é um método embutido que vem com as classes do Python. Acontece que podemos criar nossos próprios métodos para uma classe também! Modifique seu código da seguinte maneira:

```
class Student:
    def __init__(self, name, house, patronus=None):
        if not name:
            raise ValueError("Missing name")
        if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
            raise ValueError("Invalid house")
        if patronus and patronus not in ["Stag", "Otter", "Jack Russell terrier"]:
            raise ValueError("Invalid patronus")
        self.name = name
        self.house = house
        self.patronus = patronus

    def __str__(self):
        return f"{self.name} from {self.house}"

    def charm(self):
        match self.patronus:
            case "Stag":
                return "🐴"
            case "Otter":
                return "🦦"
            case "Jack Russell terrier":
                return "🐶"
            case _:
                return "🪄"


def main():
    student = get_student()
    print("Expecto Patronum!")
    print(student.charm())


def get_student():
    name = input("Name: ")
    house = input("House: ")
    patronus = input("Patronus: ") or None
    return Student(name, house, patronus)


if __name__ == "__main__":
    main()
```

Observe como definimos nosso próprio método charm. Ao contrário dos dicionários, as classes podem ter funções internas chamadas métodos. Neste caso, definimos nosso método charm onde casos específicos possuem resultados específicos. Além disso, observe que o Python tem a capacidade de utilizar emojis diretamente em nosso código.

* Antes de prosseguir, vamos remover nosso código de patronus. Modifique seu código da seguinte maneira:

```
class Student:
    def __init__(self, name, house):
        if not name:
            raise ValueError("Invalid name")
        if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
            raise ValueError("Invalid house")
        self.name = name
        self.house = house

    def __str__(self):
        return f"{self.name} from {self.house}"


def main():
    student = get_student()
    student.house = "Number Four, Privet Drive"
    print(student)


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return Student(name, house)


if __name__ == "__main__":
    main()
```

Observe como temos apenas dois métodos: ```__init__``` e ```__str__```.

## Decoradores

* As propriedades podem ser utilizadas para fortalecer nosso código. Em Python, definimos propriedades usando a função “decorators”, que começa com ```@```. Modifique seu código da seguinte maneira:

```
class Student:
    def __init__(self, name, house):
        if not name:
            raise ValueError("Invalid name")
        self.name = name
        self.house = house

    def __str__(self):
        return f"{self.name} from {self.house}"

    # Getter for house
    @property
    def house(self):
        return self._house

    # Setter for house
    @house.setter
    def house(self, house):
        if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
            raise ValueError("Invalid house")
        self._house = house


def main():
    student = get_student()
    print(student)


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return Student(name, house)


if __name__ == "__main__":
    main()
```

Observe como escrevemos @propriedade acima de uma função chamada casa. Isso define a casa como uma propriedade de nossa classe. Com house como propriedade, ganhamos a capacidade de definir como algum atributo de nossa classe, _house, deve ser definido e recuperado. De fato, agora podemos definir uma função chamada “setter”, via @house.setter, que será chamada sempre que a propriedade da casa for definida — por exemplo, com student.house = "Gryffindor". Aqui, fizemos nosso criador validar os valores da casa para nós. Observe como levantamos um ValueError se o valor de house não for nenhuma das casas de Harry Potter, caso contrário, usaremos house para atualizar o valor de _house. Por que _house e não house? house é uma propriedade de nossa classe, com funções por meio das quais um usuário tenta definir nosso atributo de classe. _house é o próprio atributo de classe. O sublinhado inicial, _, indica aos usuários que eles não precisam (e, na verdade, não devem!) modificar esse valor diretamente. _house só deve ser definido pelo configurador da casa. Observe como a propriedade house simplesmente retorna o valor de _house, nosso atributo de classe que presumivelmente foi validado usando nosso configurador de house. Quando um usuário liga para student.house, ele obtém o valor de _house por meio de nosso "gerador" de casa.

* In addition to the name of the house, we can protect the name of our student as well. Modify your code as follows:

```
class Student:
    def __init__(self, name, house):
        self.name = name
        self.house = house

    def __str__(self):
        return f"{self.name} from {self.house}"

    # Getter for name
    @property
    def name(self):
        return self._name

    # Setter for name
    @name.setter
    def name(self, name):
        if not name:
            raise ValueError("Invalid name")
        self._name = name

    @property
    def house(self):
        return self._house

    @house.setter
    def house(self, house):
        if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
            raise ValueError("Invalid house")
        self._house = house


def main():
    student = get_student()
    print(student)


def get_student():
    name = input("Name: ")
    house = input("House: ")
    return Student(name, house)


if __name__ == "__main__":
    main()
```

Observe como, muito parecido com o código anterior, fornecemos um getter e um setter para o nome.

## Conectando com o que vimos anteriormente

* Embora não tenha sido explicitamente declarado nas partes anteriores deste curso, você usou classes e objetos o tempo todo.

* Se você pesquisar a documentação de int, verá que é uma classe com um construtor. É um projeto para criar objetos do tipo int. Você pode aprender mais na documentação de int do Python.

* Strings também são uma classe. Se você usou str.lower(), você estava usando um método que vem dentro da classe str. Você pode aprender mais na documentação do Python sobre str.

* lista também é uma classe. Olhando para a documentação da lista, você pode ver os métodos que estão contidos nela, como list.append(). Você pode aprender mais na documentação de lista do Python.

* dict também é uma classe dentro do Python. Você pode aprender mais na documentação de dict do Python.

* Para ver como você tem usado as classes o tempo todo, vá para o console e digite o código type.py e, em seguida, codifique da seguinte forma:

```
print(type(50))
```

Observe como ao executar este código, ele exibirá que a classe de 50 é int.

* Também podemos aplicar isso a str da seguinte maneira:

```
print(type("hello, world"))
```

Observe como a execução desse código indicará que isso é da classe str.

* Também podemos aplicar isso à lista da seguinte maneira:

```
print(type([]))
```

Observe como a execução desse código indicará que isso é da lista de classes.

* Também podemos aplicar isso a uma lista usando o nome da classe de lista interna do Python da seguinte maneira:

```
print(type(list()))
```

Observe como a execução desse código indicará que isso é da lista de classes.

* Também podemos aplicar isso ao dict da seguinte maneira:

```
print(type({}))
```

Observe como a execução desse código indicará que isso é do dict da classe.

* Também podemos aplicar isso a um dict usando o nome da classe dict incorporada do Python da seguinte forma:

```
print(type(dict()))
```

Observe como a execução desse código indicará que isso é do dict da classe.

## Class Methods

* Às vezes, queremos adicionar funcionalidade a uma classe em si, não a instâncias dessa classe.

* @classmethod é uma função que podemos usar para adicionar funcionalidade a uma classe como um todo.

* Aqui está um exemplo de não usar um método de classe. Na janela do terminal, digite code hat.py e codifique da seguinte forma:

```
import random


class Hat:
    def __init__(self):
        self.houses = ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]

    def sort(self, name):
        print(name, "is in", random.choice(self.houses))


hat = Hat()
hat.sort("Harry")
```

Observe como quando passamos o nome do aluno para o chapéu seletor, ele nos dirá qual casa é atribuída ao aluno. Observe que hat = Hat() instancia um hat. A funcionalidade de classificação é sempre tratada pela instância da classe Hat. Ao executar hat.sort("Harry"), passamos o nome do aluno para o método sort da instância específica de Hat, que chamamos de hat.

* Podemos querer, porém, executar a função de classificação sem criar uma instância específica do chapéu seletor (há apenas um, afinal!). Podemos modificar nosso código da seguinte maneira:

```
import random


class Hat:

    houses = ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]

    @classmethod
    def sort(cls, name):
        print(name, "is in", random.choice(cls.houses))


Hat.sort("Harry")
```

Observe como o método ```__init__``` foi removido porque não precisamos instanciar um chapéu em nenhum lugar do nosso código. self, portanto, não é mais relevante e é removido. Especificamos essa classificação como @classmethod, substituindo self por cls. Finalmente, observe como Hat é capitalizado por convenção próximo ao final deste código, porque este é o nome de nossa classe.

* Voltando a Students.py, podemos modificar nosso código da seguinte maneira, abordando algumas oportunidades perdidas relacionadas a @classmethods:

```
class Student:
    def __init__(self, name, house):
        self.name = name
        self.house = house

    def __str__(self):
        return f"{self.name} from {self.house}"

    @classmethod
    def get(cls):
        name = input("Name: ")
        house = input("House: ")
        return cls(name, house)


def main():
    student = Student.get()
    print(student)


if __name__ == "__main__":
    main()
```

Observe que get_student foi removido e um @classmethod chamado get foi criado. Esse método agora pode ser chamado sem a necessidade de criar um aluno primeiro.

## Herança

* A herança é, talvez, o recurso mais poderoso da programação orientada a objetos.

* Acontece que você pode criar uma classe que “herda” métodos, variáveis ​​e atributos de outra classe.

* In the terminal, execute code wizard.py. Code as follows:

```
class Wizard:
    def __init__(self, name):
        if not name:
            raise ValueError("Missing name")
        self.name = name

    ...


class Student(Wizard):
    def __init__(self, name, house):
        super().__init__(name)
        self.house = house

    ...


class Professor(Wizard):
    def __init__(self, name, subject):
        super().__init__(name)
        self.subject = subject

    ...


wizard = Wizard("Albus")
student = Student("Harry", "Gryffindor")
professor = Professor("Severus", "Defense Against the Dark Arts")
...
```

Observe que existe uma classe acima chamada Wizard e uma classe chamada Student. Além disso, observe que há uma classe chamada Professor. Tanto os alunos quanto os professores têm nomes. Além disso, alunos e professores são magos. Portanto, tanto o Aluno quanto o Professor herdam as características do Wizard. Dentro da classe “filho” Student, o Student pode herdar da classe “pai” ou “super” Wizard como a linha super().__init__(name) executa o método init do Wizard. Por fim, observe que as últimas linhas desse código criam um mago chamado Albus, um aluno chamado Harry e assim por diante.

## Herança e exceções

* Embora tenhamos acabado de introduzir a herança, temos usado isso o tempo todo durante nosso uso de exceções.

* Acontece que as exceções vêm em uma hierarquia, onde existem classes filhos, pais e avós. Estes são ilustrados abaixo:

```
BaseException
 +-- KeyboardInterrupt
 +-- Exception
      +-- ArithmeticError
      |    +-- ZeroDivisionError
      +-- AssertionError
      +-- AttributeError
      +-- EOFError
      +-- ImportError
      |    +-- ModuleNotFoundError
      +-- LookupError
      |    +-- KeyError
      +-- NameError
      +-- SyntaxError
      |    +-- IndentationError
      +-- ValueError
 ...
```

## Sobrecarga de operadores

* Some operators such as + and - can be “overloaded” such that they can have more abilities beyond simple arithmetic.

* In your terminal window, type code vault.py. Then, code as follows:

```
class Vault:
    def __init__(self, galleons=0, sickles=0, knuts=0):
        self.galleons = galleons
        self.sickles = sickles
        self.knuts = knuts

    def __str__(self):
        return f"{self.galleons} Galleons, {self.sickles} Sickles, {self.knuts} Knuts"

    def __add__(self, other):
        galleons = self.galleons + other.galleons
        sickles = self.sickles + other.sickles
        knuts = self.knuts + other.knuts
        return Vault(galleons, sickles, knuts)


potter = Vault(100, 50, 25)
print(potter)

weasley = Vault(25, 50, 100)
print(weasley)

total = potter + weasley
print(total)
```

Observe como o método ```__str__``` retorna uma string formatada. Além disso, observe como o método ```__add__``` permite a adição dos valores de dois cofres. self é o que está à esquerda do operando +. outro é o que está certo do +.