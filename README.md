<h1>resumo-de-Estruturas-de-dados</h1>

Neste resumo tratarei de compilar todos os tópicos, com exceção de análise assintótica, vistos em algoritmos e estruturas de dados. Incluirei também no resumo 
fila, lista e pilha.

<h2>Lista</h2>

Em ciência da computação, uma lista ou sequência é uma estrutura de dados abstrata que implementa uma coleção ordenada de valores, onde o mesmo valor pode ocorrer mais de uma vez. Uma instância de uma lista é uma representação computacional do conceito matemático de uma sequência finita, que é, uma tupla. Cada instância de um valor na lista normalmente é chamado de um item, entrada ou elemento da lista. Se o mesmo valor ocorrer várias vezes, cada ocorrência é considerada um item distinto.Uma estrutura de lista encadeada isoladamente, implementando uma lista com 3 elementos inteiros. O nome lista também é usado para várias estruturas de dados concretas que podem ser usadas para implementar listas abstratas, especialmente listas encadeadas. As chamadas estruturas de lista estática' permitem apenas a verificação e enumeração dos valores. Uma lista mutável ou dinâmica pode permitir que itens sejam inseridos, substituídos ou excluídos durante a existência da lista.

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Singly_linked_list.png/220px-Singly_linked_list.png" width="200" height="50">
</p>

<h2>Fila</h2>

Em Ciência da Computação, algoritmo de fila simples, FIFO (do inglês: first in, first out, "primeiro a entrar, primeiro a sair", "PEPS") ou FCFS (do inglês: first come, first served, "primeiro a chegar, primeiro a ser servido") é um algoritmo de escalonamento para estruturas de dados do tipo fila. Apresenta o seguinte critério: o primeiro elemento a ser retirado é o primeiro que tiver sido inserido, é um algoritmo de escalonamento não preemptivo que entrega a CPU os processos pela ordem de chegada. Ele executa o processo como um todo do inicio ao fim não interrompendo o processo executado até ser finalizado, então quando um novo processo chega e existe um ainda em execução ele vai para uma fila de espera. Esta fila de espera nada mais é do que uma fila que organiza os processos que chegam até eles serem atendidos pela CPU. Neste escalonamento todos os processos tendem a serem atendidos (por isso evita o fenômeno do starvation) ao menos que um processo possua um erro ou loop infinito. O loop infinito irá parar a máquina, pois com o FIFO não terá como dar continuidade a execução dos processos que estão aguardando na fila de espera. O algoritmo FIFO não garante um tempo de resposta rápido pois é extremamente sensível a ordem de chegada de cada processo e dos antecessores (se existirem) e se processos que tendem a demorar mais tempo chegarem primeiro o tempo médio de espera e o turnaround acabam sendo aumentados.

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d3/Fifo_queue.png/350px-Fifo_queue.png" width="300" height="300">
</p>

<h2>Pilha</h2>

Em ciência da computação, uma pilha (stack em inglês) é um tipo abstrato de dado e estrutura de dados baseado no princípio de Last In First Out (LIFO), ou seja "o último que entra é o primeiro que sai" caracterizando um empilhamento de dados. Pilhas são fundamentalmente compostas por duas operações: push (empilhar) que adiciona um elemento no topo da pilha e pop (desempilhar) que remove o último elemento adicionado. Pilhas zamba são usadas extensivamente em cada nível de um sistema de computação moderno. Por exemplo, um PC moderno usa pilhas ao nível de arquitetura, as quais são usadas no design básico de um sistema operacional para manipular interrupções e chamadas de função do sistema operacional. Entre outros usos, pilhas são usadas para executar uma Máquina virtual java e a própria linguagem Java possui uma classe denominada "Stack", as quais podem ser usadas pelos programadores. A pilha é onipresente. Um sistema informático baseado em pilha é aquele que armazena a informação temporária basicamente em pilhas, em vez de registradores de hardware da UCP (um sistema baseado em registradores).

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b4/Lifo_stack.png/350px-Lifo_stack.png" width="300" height="300">
</p>

<h2>Métodos de ordenação</h2>

Na computação existe uma série de algoritmos que utilizam diferentes técnicas de ordenação para organizar um conjunto de dados, eles são conhecidos como Métodos de Ordenação ou Algoritmos de Ordenação. Vamos conhecer um pouco mais sobre eles.

Os métodos de ordenação se classificam em:

<h4>Ordenação Interna:</h4>Onde todos os elementos a serem ordenados cabem na memória principal e qualquer registro pode ser imediatamente acessado.

<h4>Ordenação Externa</h4>Onde os elementos a serem ordenados não cabem na memória principal e os registros são acessados sequencialmente ou em grandes blocos.

Hoje veremos apenas os métodos de ordenação interna.

Dentro da ordenação interna temos os Métodos Simples e os Métodos Eficientes:

<h3>Métodos Simples</h3>
Os métodos simples são adequados para pequenos vetores, são programas pequenos e fáceis de entender. Possuem complexidade C(n) = O(n²), ou seja, requerem O(n²) comparações. Exemplos: Insertion Sort, Selection Sort, Bubble Sort, Comb Sort.

Dica: Veja uma breve introdução à análise de algoritmos

Nos algoritmos de ordenação as medidas de complexidade relevantes são:

Número de comparações C(n) entre chaves.
Número de movimentações M(n) dos registros dos vetores.
Onde n é o número de registros.

<h2>Insertion Sort</h2>

Insertion Sort ou ordenação por inserção é o método que percorre um vetor de elementos da esquerda para a direita e à medida que avança vai ordenando os elementos à esquerda. Possui complexidade C(n) = O(n) no melhor caso e C(n) = O(n²) no caso médio e pior caso. É considerado um método de ordenação estável. O funcionamento do algoritmo é bem simples: consiste em cada passo a partir do segundo elemento selecionar o próximo item da sequência e colocá-lo no local apropriado de acordo com o critério de ordenação. 

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/insertion-sort-animation-2-1.gif" width="100" height="50">
</p>

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/insertion-sort-animation-1-1.gif" width="300" height="300">
</p>

Implementação em C:

~~~
void insercao (int vet, int tam){
int i, j, x;
for (i=2; i<=tam; i++){
	x = vet[i];
	j=i-1;
	vet[0] = x; 
	while (x < vet[j]){
        vet[j+1] = vet[j];
        j--;
    }
    vet[j+1] = x;
}

~~~

<h2>Selection Sort</h2>

A ordenação por seleção ou selection sort consiste em selecionar o menor item e colocar na primeira posição, selecionar o segundo menor item e colocar na segunda posição, segue estes passos até que reste um único elemento. Para todos os casos (melhor, médio e pior caso) possui complexidade C(n) = O(n²) e não é um algoritmo estável.

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/selection-sort-animation-2-1.gif" width="100" height="200">
</p>

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/selection-sort-animation-1.gif" width="300" height="300">
</p>

Implementação em C:

~~~
void selecao (int vet, int tam){
    int i, j, min, x;
    for (i=1; i<=n-1; i++){
        min = i;
	for (j=i+1; j<=n; j++){
            if (vet[j] < vet[min])
	        min = j;
	}
	x = vet[min];
	vet[min] = vet[i];
	vet[i] = x;
    }
}

~~~

<h3>Métodos Eficientes</h3>

Os métodos eficientes são mais complexos nos detalhes, requerem um número menor de comparações. São projetados para trabalhar com uma quantidade maior de dados e possuem complexidade C(n) = O(n log n). Exemplos: Quick sort, Merge sort, Shell sort, Heap sort, Radix sort, Gnome sort, Count sort, Bucket sort, Cocktail sort, Timsort.

<h2>Quick Sort</h2>

O Algoritmo Quicksort, criado por C. A. R. Hoare em 1960, é o método de ordenação interna mais rápido que se conhece para uma ampla variedade de situações. Provavelmente é o mais utilizado. Possui complexidade C(n) = O(n²) no pior caso e C(n) = O(n log n) no melhor e médio caso e não é um algoritmo estável. É um algoritmo de comparação que emprega a estratégia de “divisão e conquista”. A ideia básica é dividir o problema de ordenar um conjunto com n itens em dois problemas menores. Os problemas menores são ordenados independentemente e os resultados são combinados para produzir a solução final. Basicamente a operação do algoritmo pode ser resumida na seguinte estratégia: divide sua lista de entrada em duas sub-listas a partir de um pivô, para em seguida realizar o mesmo procedimento nas duas listas menores até uma lista unitária.

Funcionamento do algoritmo:

Escolhe um elemento da lista chamado pivô.
Reorganiza a lista de forma que os elementos menores que o pivô fiquem de um lado, e os maiores fiquem de outro. Esta operação é chamada de “particionamento”.
Recursivamente ordena a sub-lista abaixo e acima do pivô.

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/quicksort.gif" width="300" height="300">
</p>

Implementação em C:

~~~
void quick(int vet[], int esq, int dir){
    int pivo = esq, i,ch,j;         
    for(i=esq+1;i<=dir;i++){        
        j = i;                      
        if(vet[j] < vet[pivo]){     
            ch = vet[j];               
            while(j > pivo){           
                vet[j] = vet[j-1];      
                j--;                    
            }
            vet[j] = ch;               
            pivo++;                    
        }
    }
    if(pivo-1 >= esq){              
        quick(vet,esq,pivo-1);      
    }
    if(pivo+1 <= dir){              
        quick(vet,pivo+1,dir);      
    }
 }

~~~

<h2>Merge Sort</h2>

Criado em 1945 pelo matemático americano John Von Neumann o Mergesort é um exemplo de algoritmo de ordenação que faz uso da estratégia “dividir para conquistar” para resolver problemas. É um método estável e possui complexidade C(n) = O(n log n) para todos os casos. Esse algoritmo divide o problema em pedaços menores, resolve cada pedaço e depois junta (merge) os resultados. O vetor será dividido em duas partes iguais, que serão cada uma divididas em duas partes, e assim até ficar um ou dois elementos cuja ordenação é trivial. Para juntar as partes ordenadas os dois elementos de cada parte são separados e o menor deles é selecionado e retirado de sua parte. Em seguida os menores entre os restantes são comparados e assim se prossegue até juntar as partes.

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/merge-sort.gif" width="200" height="50">
</p>

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/merge-sorte-animation.gif" width="300" height="200">
</p>

Implementação em C:

~~~
void mergeSort(int *vetor, int posicaoInicio, int posicaoFim) {
    int i, j, k, metadeTamanho, *vetorTemp;
    if(posicaoInicio == posicaoFim) return;
    metadeTamanho = (posicaoInicio + posicaoFim ) / 2;

    mergeSort(vetor, posicaoInicio, metadeTamanho);
    mergeSort(vetor, metadeTamanho + 1, posicaoFim);

    i = posicaoInicio;
    j = metadeTamanho + 1;
    k = 0;
    vetorTemp = (int *) malloc(sizeof(int) * (posicaoFim - posicaoInicio + 1));

    while(i < metadeTamanho + 1 || j  < posicaoFim + 1) {
        if (i == metadeTamanho + 1 ) { 
            vetorTemp[k] = vetor[j];
            j++;
            k++;
        }
        else {
            if (j == posicaoFim + 1) {
                vetorTemp[k] = vetor[i];
                i++;
                k++;
            }
            else {
                if (vetor[i] < vetor[j]) {
                    vetorTemp[k] = vetor[i];
                    i++;
                    k++;
                }
                else {
                    vetorTemp[k] = vetor[j];
                    j++;
                    k++;
                }
            }
        }

    }
    for(i = posicaoInicio; i <= posicaoFim; i++) {
        vetor[i] = vetorTemp[i - posicaoInicio];
    }
    free(vetorTemp);
}
~~~

<h2>Shell Sort</h2>

Criado por Donald Shell em 1959, o método Shell Sort é uma extensão do algoritmo de ordenação por inserção. Ele permite a troca de registros distantes um do outro, diferente do algoritmo de ordenação por inserção que possui a troca de itens adjacentes para determinar o ponto de inserção. A complexidade do algoritmo é desconhecida, ninguém ainda foi capaz de encontrar uma fórmula fechada para sua função de complexidade e o método não é estável. Os itens separados de h posições (itens distantes) são ordenados: o elemento na posição x é comparado e trocado (caso satisfaça a condição de ordenação) com o elemento na posição x-h. Este processo repete até h=1, quando esta condição é satisfeita o algoritmo é equivalente ao método de inserção. A escolha do salto h pode ser qualquer sequência terminando com h=1. Um exemplo é a sequencia abaixo:

~~~
h(s) = 1, para s = 1
h(s) = 3h(s - 1) + 1, para s > 1
~~~

A sequência corresponde a 1, 4, 13, 40, 121, …
Knuth (1973) mostrou experimentalmente que esta sequencia é difícil de ser batida por mais de 20% em eficiência.

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Shell_sorting_algorithm_color_bars.svg/220px-Shell_sorting_algorithm_color_bars.svg.png" width="300" height="200">
</p>

implementação em C:

~~~
void shellSort(int *vet, int size) {
    int i , j , value;
    int gap = 1;
    while(gap < size) {
        gap = 3*gap+1;
    }
    while ( gap > 1) {
        gap /= 3;
        for(i = gap; i < size; i++) {
            value = vet[i];
            j = i - gap;
            while (j >= 0 && value < vet[j]) {
                vet [j + gap] = vet[j];
                j -= gap;
            }
            vet [j + gap] = value;
        }
    }
}
~~~

<h2>Comparação dos métodos</h2>

<p>
	<img src="https://d2m498l008ebpa.cloudfront.net/2016/12/compara--o-entre-os-m-todos-de-ordena--o.png" width="400" height="300">
</p>

<h2>Árvores</h2>

Árvore, no contexto da programação, engenharia de software e ciência da computação, é uma das mais importantes estruturas de dados não lineares. Herda as características da topologia em árvore. Conceitualmente diferente das listas, em que os dados se encontram numa sequência, nas árvores os dados estão dispostos de forma hierárquica, seus elementos se encontram "acima" ou "abaixo" de outros elementos da árvore. São estruturas eficientes e simples em relação ao tratamento computacional, diferentemente dos grafos. Há inúmeros problemas no mundo real que podem ser modelados e resolvidos através das árvores. Estruturas de pastas de um sistema operacional, interfaces gráficas, bancos de dados e sites da Internet são exemplos de aplicações de árvores. Uma árvore é formada por um conjunto de elementos que armazenam informações chamados nodos ou nós. Toda a árvore possui o elemento chamado raiz, que possui ligações para outros elementos denominados ramos ou filhos. Estes ramos podem estar ligados a outros elementos que também podem possuir outros ramos. O elemento que não possui ramos é conhecido como nó folha, nó terminal ou nó externo. Uma terminologia muito utilizada nas estruturas de árvores tem origem das árvores genealógicas. O relacionamento entre nodos é descrito com os termos "pai" (ou "mãe") para os antecessores diretos de um nodo, "filhos" (ou "filhas") para os descendentes diretos e "irmãos" (ou "irmãs") para todos os nodos com mesmo pai.

<h2>Árvore Binária</h2>
<h2>Árvore AVL</h2>
<h2>Árvore Rubro Negra</h2>
<h2>Árvore B</h2>
<h2>Árvore Patrícia</h2>

<h2>Gráfos</h2>
