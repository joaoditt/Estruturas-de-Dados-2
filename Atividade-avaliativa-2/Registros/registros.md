# PARTE 1 – PESQUISA: BUBBLE SORT E QUICK SORT

| Característica | Bubble Sort | Quick Sort |
|---|---|---|
| Como funciona | Percorre a lista várias vezes, analisando elementos consecutivos até que não sejam necessárias mais trocas. | Divide a lista em partes menores usando um elemento como referência (pivô) e aplica o mesmo processo às partes. |
| Lógica de ordenação | Compara dois elementos vizinhos; se estiverem na ordem errada, troca suas posições. Os maiores vão sendo deslocados para o final da lista. | Compara os elementos com o pivô, colocando os menores de um lado e os maiores do outro. Depois, repete o processo em cada parte. |
| Melhor caso | O(n) | O(n log n) |
| Caso médio | O(n²) | O(n log n) |
| Pior caso | O(n²) | O(n²) |
| Uso de memória | O(1), baixo uso de memória. | O(log n) em média, devido à recursão. |
| Vantagem principal | Simples de entender e de implementar. | Muito eficiente, especialmente para grandes volumes de dados. |
| Limitação principal | Muito lento para grandes quantidades de dados. | Pode ter desempenho O(n²) dependendo da escolha do pivô. |
| Aplicação recomendada | Pequenas listas ou situações em que simplicidade é mais importante que desempenho. | Grandes conjuntos de dados, quando se busca maior eficiência na ordenação. |
| Uso não recomendado | Grandes listas ou grandes volumes de dados, devido ao seu custo O(n²). | Situações em que é necessário garantir O(n log n) no pior caso ou quando a escolha de um bom pivô é difícil. |

# PARTE 2 – EXPERIMENTO DE ORDENAÇÃO

## Tabela

| Tamanho do Array | Bubble Sort – Comparações | Bubble Sort – Trocas | Quick Sort – Comparações | Quick Sort – Movimentações |
|---|---|---|---|---|
| 10 | 45 | 31 | 22 | 11 |
| 20 | 190 | 103 | 62 | 31 |
| 1.000 | 499500 | 248466 | 9669 | 4515 |

## Respostas

a) Quick Sort, pois realizou menos comparações e movimentações.

b) Sim. O Quick Sort continuou realizando menos operações.

c) Ambos algoritmos ficaram mais lentos.

d) Bubble Sort.

e) Sim, o quick sort realizou bem menos operações que o bubble sort.

f) Quando os valores estão organizados de forma crescente.

g) Quando os valores não estão seguindo nenhum padrão aparente.

# PARTE 3 – INVESTIGAÇÃO DE BUSCA EM MATRIZES

## Tabela de Registro dos Resultados

| Matriz | Nº de elementos | Busca no início | Busca no final | Valor inexistente |
|---|---|---|---|---|
| 2 × 2 | 4 | 1 | 4 | 4 |
| 10 × 10 | 100 | 1 | 100 | 100 |
| 100 × 100 | 10.000 | 1 | 10.000 | 10.000 |

## Respostas

a) Porque a busca começa pela primeira posição da matriz. Então, se o valor estiver no início, ele é encontrado logo na primeira comparação.

b) O programa verifica todos os elementos da matriz. Depois de comparar todos, ele informa que o valor não foi encontrado.

c) O pior caso acontece quando o valor está no final da matriz ou quando ele não existe. Nesses casos, é preciso verificar todos os elementos.

d) Quanto maior for a matriz, mais elementos precisam ser verificados. Por isso, a quantidade de comparações também aumenta.

e) A complexidade é O(m × n), porque o programa percorre as linhas e as colunas da matriz usando os dois loops.

# PARTE 4 – HANDS ON 1: INVESTIGAÇÃO DO ARRAY

## Temperaturas Recebidas

| Índice | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---|---|---|---|---|---|---|---|---|---|
| Temp (°C) | 10 | 12 | 15 | 14 | 19 | 11 | 13 | 14 | 17 | 15 |

## Tabela de Resultados

| Informação | Resultado |
|---|---|
| Média das temperaturas | 14°C |
| Maior valor | 19°C |
| Índice do maior valor | 4 |
| Menor valor | 10°C |
| Índice do menor valor | 0 |
| Valores acima da média | 4 |
| Operações de Percurso | 50 |
| Complexidade | O(n) |

# PARTE 5 – HANDS ON 2: MATRIZ APLICADA – MONITORAMENTO DE SENSORES

## Tabela – Média de cada sensor

| Sensor | Média das 24 medições (°C) |
|---|---|
| Sensor 0 | 24,66 |
| Sensor 1 | 22,83 |
| Sensor 2 | 27,25 |
| Sensor 3 | 19,79 |
| Sensor 4 | 23,53 |

## Tabela – Estatísticas gerais

| Informação | Resultado |
|---|---|
| Maior temperatura registrada | 34,0 °C |
| Sensor responsável | Sensor 2 |
| Horário da ocorrência | 12h |
| Média geral das 120 medições | 23,61 °C |
| Limite informado | 28 °C |
| Leituras acima do limite | 18 |

# PARTE 6 – ANÁLISE E CONCLUSÃO

**PERGUNTA 1.** O aumento do tamanho da estrutura de dados influencia a quantidade de operações?

**PERGUNTA 2.** Bubble Sort e Quick Sort crescem da mesma maneira quando o número de elementos aumenta?

**RESPOSTA (já responde ambas):**

Sim. Em ambos casos, há um aumento tanto de comparações quanto de trocas/movimentações nos dois algoritmos. Podemos ver, porém, que o aumento de operações do Bubble Sort cresce bem mais rapidamente do que o Quick Sort, nas três faixas de tamanho (N), isso é observado mais notavelmente na mudança de N = 20 para N = 1000:

| Tamanho (N) | Bubble - Comp | Bubble - Troc | Quick - Comp | Quick - Mov |
|---|---|---|---|---|
| 10 | 45 | 23 | 27 | 14 |
| 20 | 190 | 108 | 75 | 39 |
| 1000 | 499500 | 248971 | 11918 | 5369 |

Na mudança de N = 20 para N = 1000, notamos que as comparações do Bubble Sort crescem de 190 para 499500, enquanto que o Quick Sort cresce de 75 para 11910.

Isso se deve pela maneira que o Bubble Sort funciona. Ele percorre repetidamente a estrutura, comparando elementos adjacentes e realizando trocas quando eles estão fora de ordem. Dessa forma, a quantidade de comparações cresce de maneira aproximadamente quadrática, O(N²). Isso pode ser observado nos resultados: para N = 10 foram realizadas 45 comparações, enquanto para N = 1000 foram realizadas 499.500.

Já no Quick Sort, esse crescimento é muito menor, refletido pelo método que o algoritmo usa de dividir em partes e ordená-las separadamente. Com isso, normalmente são necessárias muito menos operações, apresentando um comportamento médio de O(N log N). Nos resultados, isso fica evidente: para N = 1000, o Quick Sort realizou 11.918 comparações, enquanto o Bubble Sort realizou 499.500.

**PERGUNTA 3.** Por que analisar somente o resultado final da ordenação não é suficiente para comparar algoritmos?

**RESPOSTA:**

O resultado final realmente continua igual para ambos algoritmos, porém, cada um tem sua especificidade, tanto nos resultados de quantidade de operações quanto no tempo e uso de recursos:

| Tamanho (N) | Bubble Sort (s) | Quick Sort (s) |
|---|---|---|
| 10 | 0.000015 | 0.000016 |
| 20 | 0.000022 | 0.000028 |
| 1000 | 0.064699 | 0.001668 |

Novamente, podemos usar a diferença dos tamanhos '10' e '20' comparados ao tamanho '1000'. Os tempos dos tamanhos menores são bem parecidos, com o Bubble Sort sendo razoavelmente mais rápido. Já na medida '1000', vemos que o Quick Sort se destaca, com uma diferença de tempo consideravelmente mais veloz.

Nos testes realizados, Bubble Sort conseguiu ordenar tamanhos pequenos com tempos ligeiramente menores. Mesmo que tenha mais comparações, é um algoritmo simples, que faz suas comparações e trocas em estruturas pequenas sem muitas complicações, mas no momento que a estrutura de dados cresce, o número de operações aumenta significativamente. Já o Quick Sort utiliza de métodos de divisão da estrutura em partes menores, que reduzem a quantidade de comparações e movimentações de elementos em estruturas maiores.

Resumidamente, apenas o resultado da ordenação algorítmica não é suficiente para comparação pois diferentes algoritmos funcionam para diferentes casos e para diferentes implementações. A quantidade comparações e tempo de execução devem ser considerados ao estudar e comparar o desempenho de cada algoritmo durante o processo de ordenação.
