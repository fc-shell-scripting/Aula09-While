# While
---
- [While](#while)
    - [Introdução](#introducao)
    - [Break](#break)
    - [Exercícios](#exercicios)
    - [Desafios](#desafios)

## Introdução
Vimos aula passada o comando _if_, que permite verificarmos uma determinada condição uma vez. Mas e se quisermos fazer essa verificação mais de uma vez? Usar diversos _ifs_ não é uma opção boa, porque vamos ter que repetir o mesmo código diversas vezes. E se não soubermos quantas vezes precisamos repetir? Nessas situações, podemos usar a estrutura de repetição _while_. estruturas de repetição, também chamados de laços ou loops, indicam ao interpretador que um determinado bloco de informações deve ser repetido, e contém uma condição a ser verificada no início ou final de cada ciclo de execução.

A estrutura padrão:
```shell
while [[ condicao ]]; do
    #bloco de comandos a ser repetido
done
```
A estrutura acima faz a verificação da condição, e se ela for verdadeira o bloco de comandos dentro dela será executada. Ao final deste ciclo de execução, quando o interpretador chegar no comando _done_, ele irá retornar para o início da estrutura _while_, onde uma novamente será checado se a condição é verdadeira. Se for, um novo ciclo de execução ocorrerá; Se não for, o interpretador irá sair do bloco de execução, indo para a linha seguinte ao comando _done_.

Para exemplificar, vamos usar um exemplo que mostra na tela numeros de 0 até 99:
```shell {.line-numbers}
#!/bin/bash

numero=0
while (( numero < 100 )); do
    echo "$numero"
    numero=$(($numero + 1))
done
```
Neste exemplo, veja que usamos dois parênteses para executar operações aritméticas, ao invés de dois colchetes, que são usados para operações com strings. Existem outras formas de se representar estas operações, mas vamos usar estas para fins didáticos.

## Break
Algumas vezes queremos sair do loop antes da condição do loop ser falsa.  Para isso, devemos usar o comando _break_. Este comando sai do laço de repetição mais próximo:

```shell
while [[ condicao1 ]]; do
    #codigo a ser repetido
    if [[ condicao2 ]]; then
        break
    fi
done
```
O exemplo acima é uma das formas mais simples de se sair do loop antes que ele chegue ao final, ou tenha sua consdição como falsa.

## Exercícios
1. Faça um programa que solicite um número ao usuário e vá somando em uma variável. Quando o usuário digitar 0, o prgrama deve sair do loop e mostrar o resultado das somas.
2. Faça um programa que gere a média de _n_ números digitados pelo usuário
3. Faça um programa que pergunte o nome de um usuário e mostre os dados deste usuário no arquivo /etc/passwd. Quando o nome do usuário for "sair", o programa deve terminar.

## Desafios
1. Crie um programa que realize um cadastro de produtos. Ao final do programa, perguntar ao usuário se ele deseja cadastrar mais um produto. Repetir o processo de cadastro se sim. Finalizar o programa se não. Armazene os dados em um _produtos.csv_
2. Crie um programa que realize uma consulta de produto dentro do arquivo _produtos.txt_
3. Crie um programa de menu que permita ao usuário acessar o cadastro, ou consulta do programa anterior