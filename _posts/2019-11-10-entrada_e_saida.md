---
layout: post
title:  "Entrada e saída de dados"
date:   2019-11-10 16:12:00 -0400
categories: estudo
---

*Entrada e saída de dados* é um termo que significa como um programa se comunica com o usuário ou outros programas. A maioria das linguagens de programação possui o conceito de entrada e saída *padrão*, onde a entrada de dados é feita pelo teclado e a saída via terminal.

Nas competições de programação, como na *Maratona de Programação* e na *Olimpíada Brasileira de Informática*, o programador deverá utilizar
a *entrada e saída padrão* para ler os dados do problema e imprimir a resposta. Entretanto, nas competições, o teste do programa é automatizado e realizado sem a intervenção humana, sendo a entrada e saída padrão são mapeadas para arquivos. Por isto, o programador deve ficar atento ao formato imposto pelo problema: qualquer vírgula ou espaço a mais na saída caracteriza um erro.

## Saída de dados

Em Java, a saída de dados pode ser realizada com o método *System.out.print* e *System.out.println*, conforme o exemplo abaixo:

{% highlight java %}
public class Saida1 {
    public static void main(String[] args) {
        System.out.println("Olá, mundo"); // imprime uma mensagem e pula a linha

        System.out.print("Eu gosto de "); // imprime, mas não pula a linha
        System.out.println("programar");

        double pi = Math.PI;
        System.out.println(pi);
    }
}
{% endhighlight %}

Para compilar e rodar na linha de comando:

    $ javac Saida1.java
    $ java Saida1

Alguns problemas pedem para que seja impresso um número com um número fixo de casas decimais. Neste caso, pode-se utilizar o método *System.out.printf*:

{% highlight java %}
public class Saida2 {
    public static void main(String[] args) {
        double pi = Math.PI;
        System.out.printf("PI: %.2f\n", pi);
    }
}
{% endhighlight %}

Neste último exemplo, o formato "PI: %.2f\n" especifica que queremos um número de ponto flutuante ("f") com duas casas após o separador decimal (".2"), tendo como final o pulo de linha ("\n").

## Entrada de dados

A entrada de dados em Java pode ser realizada utilizando a classe *Scanner*. O exemplo abaixo mostra como utilizar esta classe para realizar a leitura de diferentes tipos de dados:

{% highlight java %}
import java.util.Scanner;

public class Entrada1 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        int a = leitor.nextInt();       // int
        double b = leitor.nextDouble(); // double
        String c = leitor.next();       // String

        System.out.println("a == " + a + ", b == " + b + ", c == " + c);
    }
}
{% endhighlight %}

### Entrada controlada por contador

Existem problemas de programação onde é necessário realizar a leitura de múltiplos valores. Um dos tipos de entrada utilizados é a *entrada controlada por contador*, onde o problema fornece primeiramente a quantidade de valores e então os valores em si. Considere o seguinte problema:

    Escreva um programa que leia uma sequência de números inteiros positivos
    da entrada padrão e imprima o somatório dos números.

Na entrada por contador, o problema iria fornecer o número de inteiros e então a sequência de números, como no exemplo abaixo:

    5
    1 5 3 4 8

Um programa em Java que resolve o problema acima é mostrado abaixo:

{% highlight java %}
import java.util.Scanner;

public class Entrada2 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        int N = leitor.nextInt();
        int total = 0;

        for (int i = 0; i < N; i++) {
            total += leitor.nextInt();
        }

        System.out.println(total);
    }
}
{% endhighlight %}

### Entrada controlada por sentinela

Uma segunda forma de um problema de programação especificar a entrada de múltiplos valores é por meio da "entrada controlada por sentinela*. Um sentinela é um valor que marca o final da entrada.

Considerando o problema anterior, temos que a entrada é constituída somente por números inteiros positivos. Logo, o problema poderia utilizar o valor -1 como sentinela. Neste caso, o exemplo abaixo corresponde a uma entrada válida:

    1 5 3 4 8 -1

Segue abaixo um programa em Java que realiza a entrada de dados utilizando sentinela:

{% highlight java %}
import java.util.Scanner;

public class Entrada3 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        int total = 0;

        while (true) {
            int valor = leitor.nextInt();
            if (valor == -1)
                break;
            total += valor;
        }

        System.out.println(total);
    }
}
{% endhighlight %}