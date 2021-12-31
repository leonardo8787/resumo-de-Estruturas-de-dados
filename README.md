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

Uma árvore binária é uma estrutura de dados caracterizada por: Ou não tem elemento algum (árvore vazia).
Ou tem um elemento distinto, denominado raiz, com dois ponteiros para duas estruturas diferentes, denominadas subárvore esquerda e subárvore direita. Perceba que a definição é recursiva e, devido a isso, muitas operações sobre árvores binárias utilizam recursão. É o tipo de árvore mais utilizado na computação. A principal utilização de árvores binárias são as árvores binárias de busca.

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/200px-Binary_tree.svg.png" width="300" height="200">
</p>

Os nós de uma árvore binária possuem graus zero, um ou dois. Um nó de grau zero é denominado folha. Em uma árvore binária, por definição, cada nó poderá ter até duas folhas, sendo que ela se compara com a ABB (árvore binária de busca), apesar de não ter a propriedade da mesma ("na abb, existe uma regra na inserção"). A profundidade de um nó é a distância deste nó até a raiz. Um conjunto de nós com a mesma profundidade é denominado nível da árvore. A maior profundidade de um nó, é a altura da árvore. Uma árvore "estritamente binária" é uma árvore na qual todo nó tem zero ou duas folhas. Existem autores, porém, que adotam essa definição para o termo quase completa, e utilizam o termo completa apenas para árvores em que todos os níveis têm o máximo número de elementos.

<h2>Árvore AVL</h2>

Árvore AVL é uma árvore binária de busca balanceada, ou seja, uma árvore balanceada (árvore completa) são as árvores que minimizam o número de comparações efetuadas no pior caso para uma busca com chaves de probabilidades de ocorrências idênticas. Contudo, para garantir essa propriedade em aplicações dinâmicas, é preciso reconstruir a árvore para seu estado ideal a cada operação sobre seus nós (inclusão ou exclusão), para ser alcançado um custo de algoritmo com o tempo de pesquisa tendendo a {\displaystyle O(\log n)}{\displaystyle O(\log n)}. As operações de busca, inserção e remoção de elementos possuem complexidade {\displaystyle O(\log n)}{\displaystyle O(\log n)}(no qual {\displaystyle n}n é o número de elementos da árvore), que são aplicados a árvore de busca binária. O nome AVL vem de seus criadores soviéticos Adelson Velsky e Landis, e sua primeira referência encontra-se no documento "Algoritmos para organização da informação" de 1962. Nessa estrutura de dados cada elemento é chamado de nó. Cada nó armazena uma chave e dois ponteiros, uma para a subárvore esquerda e outro para a subárvore direita. No presente artigo serão apresentados: os conceitos básicos, incluindo uma proposta de estrutura; apresentação das operações busca, inserção e remoção, todas com complexidade {\displaystyle O(\log n)}{\displaystyle O(\log n)}.

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/200px-Binary_tree.svg.png" width="300" height="200">
</p>

Uma árvore binária T é denominada AVL quando, para qualquer nó de T, as alturas de suas duas subárvores, esquerda e direita, diferem em módulo de até uma unidade.

<h4>Balanceamento</h4>

Toda árvore AVL é balanceada, isto é, sua altura é O(log n).

A vantagem do balanceamento é possibilitar que a busca seja de complexidade O(log n). Entretanto, as operações de inserção e remoção devem possuir custo similar. No caso da árvore AVL, a inserção e remoção têm custo O(log n). Por definição, todos os nós da AVL devem ter fb = -1, 0 ou 1. Para garantir essa propriedade, a cada inserção ou remoção o fator de balanço deve ser atualizado a partir do pai do nó inserido até a raiz da árvore. Na inserção basta encontrar o primeiro nó desregulado (fb= -2 ou fb= 2), aplicar o operação de rotação necessária, não havendo necessidade de verificar os demais nós. Na remoção a verificação deverá prosseguir até a raiz, podendo requerer mais de uma rotação.

<h4>Complexidade</h4>

A árvore AVL tem complexidade {\displaystyle O(\log n)}O(\log n) para todas operações e ocupa espaço n, onde n é o número de nós da árvore.

<h2>Árvore Rubro Negra</h2>

Uma árvore rubro-negra é um tipo de árvore binária de busca balanceada, uma estrutura de dados usada em ciência da computação, tipicamente para implementar vetores associativos. A estrutura original foi inventada em 1972, por Rudolf Bayer. que a chamou de "Árvores Binárias B Simétricas", mas adquiriu este nome moderno em um artigo de 1978 escrito por Leonidas J. Guibas e Robert Sedgewick. Ela é complexa, mas tem um bom pior-caso de tempo de execução para suas operações e é eficiente na prática: pode-se buscar, inserir, e remover em tempo O(log n), onde n é o número total de elementos da árvore. De maneira simplificada, uma árvore rubro-negra é uma árvore de busca binária que insere e remove de forma inteligente, para assegurar que a árvore permaneça aproximadamente balanceada.

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/66/Red-black_tree_example.svg/500px-Red-black_tree_example.svg.png" width="300" height="200">
</p>

Uma árvore rubro-negra é uma árvore de busca binária onde cada nó tem um atributo de cor, vermelho ou preto. Além dos requisitos ordinários impostos pelas árvores de busca binárias, as árvores rubro-negras tem os seguintes requisitos adicionais:
Um nó é vermelho ou preto.
A raiz é preta. (Esta regra é usada em algumas definições. Como a raiz pode sempre ser alterada de vermelho para preto, mas não sendo válido o oposto, esta regra tem pouco efeito na análise.)
Todas as folhas(nil) são pretas.
Ambos os filhos de todos os nós vermelhos são pretos.
Todo caminho de um dado nó para qualquer de seus nós folhas descendentes contem o mesmo número de nós pretos.
Essas regras asseguram uma propriedade crítica das árvores rubro-negras: que o caminho mais longo da raiz a qualquer folha não seja mais do que duas vezes o caminho mais curto da raiz a qualquer outra folha naquela árvore. O resultado é que a árvore é aproximadamente balanceada. Como as operações de inserção, remoção, e busca de valores necessitam de tempo de pior caso proporcional à altura da árvore, este limite proporcional a altura permite que árvores rubro-negras sejam eficientes no pior caso, diferentemente de árvore de busca binária. Para perceber por que essas propriedades garantem isto, basta observar que nenhum caminho pode ter dois nós vermelhos sucessivos, devido à propriedade 4. O caminho mais curto possível tem todos os nós pretos, e o caminho mais longo possível alterna entre nós vermelhos e pretos. Desde que todos os caminhos máximos têm o mesmo número de nós pretos, pela propriedade 5, isto mostra que nenhum caminho é mais do que duas vezes mais longo que qualquer outro caminho. Em muitas das representações de estruturas de dados em árvore, é possível para um nó pai ter só um filho, e os nós folha contêm dados. É possível representar árvores rubro-negras neste paradigma, mas ele modifica várias propriedades e deixa os algoritmos mais complexos. Por essa razão, este artigo usa "folhas nulas", que não contêm nenhum dado e simplesmente servem para indicar onde a árvore termina, como mostrado acima. Esses nós muitas vezes são omitidos dos desenhos, resultando em uma árvore que parece contradizer os princípios acima mencionados, mas que de fato não faz. Uma conseqüência disto é que todo nó interno (não-folha) têm dois filhos, embora um ou ambos filhos possam ser folhas nulas. Alguns explicam uma árvore rubro-negra como uma árvore de busca binária cujas bordas, em vez de nós, são coloridas em vermelho ou preto, mas isto não faz nenhuma diferença. A cor de um nó na terminologia deste artigo corresponde à cor da borda que une o nó ao seu pai, exceto que o nó de raiz é sempre preto (propriedade 2) ao passo que a borda correspondente não existe.



<h2>Árvore B</h2>

Em ciência da computação, uma árvore B é uma estrutura de dados em árvore, auto-balanceada, que armazena dados classificados e permite pesquisas, acesso sequencial, inserções e remoções em tempo logarítmico. A árvore B é uma generalização de uma árvore de pesquisa binária em que um nó pode ter mais que dois filhos.[1] Diferente das árvores de pesquisa binária auto-balanceadas, a árvore B é bem adaptada para sistemas de armazenamento que leem e escrevem blocos de dados relativamente grandes, como discos. É normalmente usada em bancos de dados e sistemas de arquivos e foi projetada para funcionar especialmente em memória secundária como um disco magnético ou outros dispositivos de armazenamento secundário. As árvores B são semelhantes as árvores preto e vermelho, mas são melhores para minimizar operações de E/S de disco. Muitos sistemas de bancos de dados usam árvores B ou variações da mesma para armazenar informações. Dentre suas propriedades ela permite a inserção, remoção e busca de chaves numa complexidade de tempo logarítmica e, por esse motivo, é muito empregada em aplicações que necessitam manipular grandes quantidades de informação tais como um banco de dados ou um sistemas de arquivos. Inventada por Rudolf Bayer e Edward Meyers McCreight em 1971 enquanto trabalhavam no Boeing Scientific Research Labs, a origem do nome (árvore B) não foi definida por estes. Especula-se que o B venha da palavra balanceamento, do nome de um de seus inventores Bayer ou de Boeing, nome da empresa. Árvores B são uma generalização das árvores binária de busca, pois cada nó de uma árvore binária armazena uma única chave de busca, enquanto as árvores B armazenam um número maior do que um de chaves de busca em cada nó, ou no termo mais usual para essa árvore, em cada página. Como a ideia principal das árvores B é trabalhar com dispositivos de memória secundária, quanto menos acessos a disco a estrutura de dados proporcionar, melhor será o desempenho do sistema na operação de busca sobre os dados manipulados.

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/92/B-tree-definition.png/400px-B-tree-definition.png" width="300" height="200">
</p>

Os dispositivos de memória de um computador consistem na memória principal e secundária, sendo cada uma delas com suas características. A memória primária é mais conhecida como memória volátil de endereçamento direto (RAM), esta por sua vez apresenta baixo tempo de acesso, porém armazena um volume relativamente pequeno de informação e altos custos. Já a memória secundária, possui um endereçamento indireto, armazena um grande volume de informação e possui um acesso (seek) muito lento quando comparada com a memória primária. A árvore B é uma solução para cenários em que o volume de informação é alto (e este não pode ser armazenado diretamente em memória primária) e, portanto, apenas algumas páginas da árvore podem ser carregadas em memória primária. As árvores B são organizadas por nós, tais como os das árvores binárias de busca, mas estes apresentam um conjunto de chaves maior do que um e são usualmente chamados de páginas. As chaves em cada página são, no momento da inserção, ordenadas de forma crescente e para cada chave há dois endereços para páginas filhas, sendo que, o endereço à esquerda é para uma página filha com um conjunto de chaves menor e o à direita para uma página filha com um conjunto de chaves maior. A figura acima demonstra essa organização de dados característica. Se um nó interno x contém n[x] chaves, então x tem n[x] + 1 filhos. as chaves do nó x são usadas como pontos de divisão que separam o intervalo de chaves manipuladas por x em x[x] subintervalos, cada qual manipulado por um filho de x. Vale lembrar que todo este endereçamento está gravado em arquivo (memória secundária) e que um acesso a uma posição do arquivo é uma operação muito lenta. Através da paginação é possível carregar em memória primária uma grande quantidade de registros contidos numa única página e assim decidir qual a próxima página que o algoritmo de busca irá carregar em memória primária caso esta chave buscada não esteja na primeira página carregada. Após carregada uma página em memória primária, a busca de chave pode ser realizada linearmente sobre o conjunto de chaves ou através de busca binária.

<h2>Árvore Patrícia</h2>

A árvore PATRICIA é uma representação compacta de uma Trie onde os nós que teriam apenas um filho são agrupados nos seus antecessores. É comum que as árvores Trie possuam um grupo disperso de chaves, desse modo, muitos nós possuem apenas um descendente. Isto faz com que as Trie tenham um custo grande de espaço. Uma Trie usa cada uma das partes de uma chave, por vez, para determinar a sub-árvore. Por outro lado, a árvore PATRICIA escolhe um elemento da chave (armazenando a sua posição) para determinar a sub-árvore. Isso remove a necessidade de nós com apenas um descendente. Concebido por Donald Morrison, PATRICIA é um algoritmo para realização de buscas em árvores com as chaves dos nós representadas em binário, sem armazenar as chaves nos nós. O nome é um acrônimo de “Practical Algorithm To Retrieve Information Coded In Alphanumeric”, e o método é particularmente útil para tratamento de chaves de tamanho variável extremamente longas, tais como títulos e frases. No caso de pesquisas analíticas, os dados podem tirar proveito deste método desde que as informações sejam armazenadas como cadeias de texto. Uma restrição dessas árvores é a necessidade de não haver um elemento que seja prefixo de outro, o que pode facilmente ser obtido se necessário.

<h2>Gráfos</h2>

Em ciência da computação, um grafo é um tipo abstrato de dados que destina-se a implementar os conceitos matemáticos de grafo não-direcionado e gráfico direcionado, especificamente no campo da teoria dos grafos. Um grafo consiste de um conjunto finito (e, possivelmente, mutável) de vértices ou nós ou pontos, com um conjunto de pares não ordenados destes vértices para um grafo não-direcionado, ou um conjunto de pares ordenados para um grafo direcionado. Esses pares são conhecidos como arestas, arcos ou linhas para um grafo não-direcionado e como setas, arestas dirigidas, arcos dirigidos ou  linhas dirigidas para um grafo direcionado. Os vértices podem ser parte do grafo, ou podem ser entidades externas representadas por índices inteiros ou referências. Uma estrutura de dados do tipo grafo pode também associar a cada aresta algum peso, como um rótulo simbólico ou um atributo numérico (custo, capacidade, comprimento, etc.).

<p>
	<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Directed.svg/125px-Directed.svg.png" width="300" height="200">
</p>

