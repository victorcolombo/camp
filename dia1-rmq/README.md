﻿# Resumo

## **Range Minimum Query e Sparse Table:**

Foram comparados alguns algoritmos para resolver o seguinte problema:

É dado array v de n posições e querys, que podem ser do tipo i j, a partir das quais deve-se responder o valor mínimo de um elemento cujo índice está entre i e j, ou do tipo i x, a partir das quais deve-se mudar o elemento no índice i para x.

As soluções propostas, cujos códigos encontram-se na pasta "Códigos RMQ" e suas devidas complexidades para cada tipo de operação são:

| Solução |  Pré-processamento  |   Memória adicional   |  Por query   |Mudar elemento
|--|--|--|--|--|
Força-bruta   |  O(1)      |   O(1)           |     O(n)  |      O(1)  | 
PD         | O(n²)   |  O(n²)       |       O(1)       |    O(n²)  | 
Sqrt decomposition  |    O(n)   | O(sqrt(n))   | O(sqrt(n))   |  O(sqrt(n))
Segment Tree   |  O(n)    |    O(n)     | O(log(n))   |   O(log(n))
Sparse Table   |  O(n.log(n))  |   O(n.log(n))    | O(1)   |  O(n.log(n))

(*)não estou contando o tempo e memória para ler e armazenar todos os elementos

Há também uma coluna implícita, que é a dificuldade de implementar cada um desses algoritmos. Isso também deve ser levado em conta na hora de uma prova. Dessa forma, não há algoritmo universalmente melhor que todos os outros e tudo deve ser levado em conta quando se depara com um problema similar.

Nota-se que nenhum algoritmo é estritamente melhor que nenhum outro. Dois deles foram abordados com mais calma:


## Square-root decomposition:

A ideia é dividir o array em blocos de tamanho sqrt(n), dessa forma, com apenas alguns segmentos pré-processados, podemos obter um algoritmo que não utiliza tanta memória e tempo de pré-processamento quanto a programação dinâmica mas não tem a query tão lenta quanto o brute-force.

Vale pontuar que o problema em questão não chega nem perto de demonstrar o poder e versatilidade dessa técnica. Uma outra maneira na qual essa ideia pode ser aplicada, por exemplo, é o algoritmo de MO, no qual as querys são separadas em blocos de raiz seguindo alguma propriedade.


## Sparse table:

Manter, para cada início possível, o mínimo do segmento que têm esse início e o tamanho é alguma potência de dois. Dessa forma, qualquer segmento pode ser representado como a sobreposição de dois que já foram calculados e a query pode ser feita, portanto, em O(1). Outra vantagem desse método também é que sua implementação é bem sucinta comparada aos outros.



## Sparse Table(again) e Lowest Common Ancestor:



Agora o problema é o seguinte:

É dada uma árvore de n nós. Queremos responder perguntas do tipo: dados os vértices i e j, qual o mais baixo ancestral comum de ambos.

A solução proposta, de complexidade log(n) após n*log(n) pré-processamento, é similar á da Sparse Table do RMQ: manter, para cada nó, os ancestrais de distâncias iguais às potências de dois.

Tendo isso, sobe-se o vértice mais baixo para a altura do outro. Caso ainda não sejam iguais, faz-se uma espécie de busca binária no quanto que ambos os vértices precisam "subir" para que o ancestral em questão seja o mesmo.

Dessa forma, pode-se encontrar o ancestral comum de dois vértices em O(log n). Essa técnica pode ser usada também, com poucas modificações, para encontrar o tamanho do caminho entre dois nós em uma árvore com essa mesma complexidade.


# Exercícios

## Sparse Table e Square-root decomposition:
https://www.spoj.com/problems/RMQSQ/
https://www.spoj.com/problems/HISTOGRA/
https://www.spoj.com/problems/FREQUENT/
J-Shopping http://codeforces.com/gym/101201

## Lowest Common ancestor
https://www.spoj.com/problems/LCA/
https://www.spoj.com/problems/QTREE2/
http://codeforces.com/problemset/problem/609/E
http://acm.timus.ru/problem.aspx?num=1471

Agradecimentos a Yan Couto, do qual roubei grande parte dessa lista.

