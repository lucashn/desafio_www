---
layout: post
title:  "Ordenação"
date:   2019-11-07 20:22:00 -0400
categories: estudo
---

Um problema recorrente na escrita de programas é o da ordenação de uma sequência de valores. Exemplos incluem ordenar uma sequência de números em ordem crescente e ordenar uma sequência de palavras de acordo com a ordem do dicionário.

Apesar de ser possível implementar um algoritmo de ordenação você mesmo, para o uso corriqueiro é preferível utilizar a implementação já disponível na biblioteca padrão da linguagem de programação utilizada.

Exemplo de ordenação de um vetor de inteiros na linguagem Java:

{% highlight java %}
import java.util.Arrays;

public class Ordenacao1 {
    public static void main(String[] args) {
        int vetor[] = {1, 5, 3, 8, 10, 2, 6};
        Arrays.sort(vetor);
        
        for(int e : vetor) {
            System.out.println(e);
        }
    }
}
{% endhighlight %}

Para compilar e rodar na linha de comando:

    $ javac Ordenacao1.java
    $ java Ordenacao1

Se você estiver trabalhando com alguma estrutura de dados da biblioteca padrão (Coleção), como, por exemplo, um *ArrayList*, utilize o método *Collections.sort(colecao)*, como visto no exemplo abaixo:

{% highlight java %}
import java.util.Collections;
import java.util.ArrayList;

public class Ordenacao2 {
    public static void main(String[] args) {
        ArrayList<Integer> vetor = new ArrayList<>();
        vetor.add(5);
        vetor.add(3);
        vetor.add(8);
        vetor.add(2);
        vetor.add(6);
        
        Collections.sort(vetor);
        
        for(int e : vetor) {
            System.out.println(e);
        }
    }
}
{% endhighlight %}

Existem diversos métodos de ordenação, com diferentes propriedades e aplicações. Alguns métodos, como o *Bubblesort*, *Insertion sort* e *Selection sort*, são simples, porém ineficientes para grandes sequências quando comparados com métodos como o *Quicksort*, *Mergesort* e *Heapsort*. Mesmo assim, aconselha-se o estudo de todos os métodos para que o estudante entenda os mecanismos por trás da ordenação.

As linguagens de programação usualmente implementam variantes do *Quicksort* e *Mergesort*, como é o caso de algumas das implementações da linguagem Java. Assim, em Java, basta chamar o método correspondente (*Arrays.sort* ou *Collections.sort*) para ordenar a sua sequência de valores.

A [página da Wikipedia][1] sobre métodos de ordenação apresenta os principais métodos.

## Probemas relacionados

- [Amigos do Habay][3]
- [Bolhas e baldes][2]

[1]: https://pt.wikipedia.org/wiki/Algoritmo_de_ordena%C3%A7%C3%A3o
[2]: https://br.spoj.com/problems/BALDES/
[3]: https://www.urionlinejudge.com.br/judge/pt/problems/view/2136
