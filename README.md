# Teste-Estagio-TargetSistemas-2024

Técnica:

1) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.

IMPORTANTE: Esse número pode ser informado através de qualquer entrada de sua preferência ou pode ser previamente definido no código;

```
package prova;

import java.util.Scanner;

public class SequenciaFibonacci {

    public static void sequenciaFibonacci(int fibonacci[], int max) {
        int atual = 1, anterior = 0, aux = 0;

        for (int i = 0; i < max; i++) {
            fibonacci[i] = aux;
            aux = atual;
            atual = anterior + atual;
            anterior = aux;
        }
    }

    public static void imprimir(int fibonacci[]) {
        for (int i = 0; i < fibonacci.length; i++) {
            System.out.print(fibonacci[i] + " ");
        }
        System.out.println();
    }

    public static int procurarNumero(int fibonacci[], int num) {

        for (int i = 0; i < fibonacci.length; i++) {
            if (num == fibonacci[i]) {
                return i;
            }
        }
        return -1;
    }

    public static void informe(int fibonacci[], int result) {
        if (result != -1) {
            System.out.println("Valor " + fibonacci[result] + " encontrado na posição " + result);
        } else {
            System.out.println("Número não encontrado!");
        }
    }

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("Por favor, informe o número máximo: ");
        Integer max = input.nextInt();

        System.out.println("Por favor, informe um número desejado: ");
        Integer num = input.nextInt();

        int[] fibonacci = new int[max];

        sequenciaFibonacci(fibonacci, max);
        imprimir(fibonacci);

        int result = procurarNumero(fibonacci, num);
        informe(fibonacci, result);
    }
}
```

2) Escreva um programa que verifique, em uma string, a existência da letra ‘a’, seja maiúscula ou minúscula, além de informar a quantidade de vezes em que ela ocorre.

IMPORTANTE: Essa string pode ser informada através de qualquer entrada de sua preferência ou pode ser previamente definida no código;

```
const readline = require('readline');

// Configura o readline para capturar a entrada do usuario
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

// Exibir os resultados
function exibeResultado(minuscula, maiuscula){

    console.log(`Quantidade de letras 'a' minúsculas: ${minuscula}`);
    console.log(`Quantidade de letras 'A' maiúsculas: ${maiuscula}`);
    console.log(`Total de ocorrências da letra 'a' (minúscula e maiúscula): ${minuscula+maiuscula}`);
}

// Funcao para verificar a existencia e a quantidade de ocorrencias da letra 'a' e 'A'
function verificarLetraA(texto) {
    let minuscula = 0;
    let maiuscula = 0;

    // Contar o numero de ocorrencias das letras 'a' e 'A'
    for (let i = 0; i < texto.length; i++) {

        if (texto[i] === 'a') { 
            minuscula++;
        } else if (texto[i] === 'A') {
            maiuscula++;
        }
    }

    //Exibe um print da quantidade de numeros minusculos, maiusculos e o total
    exibeResultado(minuscula, maiuscula);
    
    // Verificar a existencia da letra 'a'
    if ((minuscula + maiuscula) > 0) {
        console.log("A letra 'a' (ou 'A') foi encontrada.");
    } else {
        console.log("A letra 'a' (ou 'A') não foi encontrada.");
    }
}

// Funcao para capturar a entrada do usuario e chamar a funcao de verificacao
function obterEntradaUsuario() {
    rl.question('Digite uma frase para verificar: ', (entrada) => {
        verificarLetraA(entrada);
        rl.close();
    });
}

// Iniciar o processo
obterEntradaUsuario();

```

3) Observe o trecho de código abaixo: int INDICE = 12, SOMA = 0, K = 1; enquanto K < INDICE faça { K = K + 1; SOMA = SOMA + K; } imprimir(SOMA);

```
O valor final da variável SOMA será 77.
```

Ao final do processamento, qual será o valor da variável SOMA?

4) Descubra a lógica e complete o próximo elemento:  
a) 1, 3, 5, 7, ___  
b) 2, 4, 8, 16, 32, 64, ____  
c) 0, 1, 4, 9, 16, 25, 36, ____  
d) 4, 16, 36, 64, ____  
e) 1, 1, 2, 3, 5, 8, ____  
f) 2,10, 12, 16, 17, 18, 19, ____  

```
a) 1, 3, 5, 7, 9                 //Lógica: Números ímpares consecutivos.
b) 2, 4, 8, 16, 32, 64, 128      //Lógica: Cada número é o dobro do anterior (multiplicação por 2).
c) 0, 1, 4, 9, 16, 25, 36, 49    //Lógica: Sequência de quadrados perfeitos (0^2, 1^2, 2^2, ... 7^2)
d) 4, 16, 36, 64, 100            //Lógica: Sequência dos quadrados de números pares (2^2, 4^2, ... 10^2)
e) 1, 1, 2, 3, 5, 8, 13          //Lógica: Sequência de Fibonacci (cada número é a soma dos dois anteriores).
f) 2, 10, 12, 16, 17, 18, 19, 20 //Lógica: Após o número 2, sequência de números começando de 10, com exclusão apenas do número 11.
```

5) Você está em uma sala com três interruptores, cada um conectado a uma lâmpada em salas diferentes. Você não pode ver as lâmpadas da sala em que está, mas pode ligar e desligar os interruptores quantas vezes quiser. Seu objetivo é descobrir qual interruptor controla qual lâmpada. Como você faria para descobrir, usando apenas duas idas até uma das salas das lâmpadas, qual interruptor controla cada lâmpada?  

```
Ligaria o 1º interruptor para a lâmpada conectada a ele esquentar.
Em seguida, desligaria o 1º e ligaria o 2º interruptor.

Dessa forma, a lâmpada acesa está conectada ao 2º interruptor;
a lâmpada quente está ligada ao 1º interruptor,
e a lâmpada fria só pode ser do 3º interruptor.
```
