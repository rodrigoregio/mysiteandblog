---
layout: post
title: Python, memória e arquivos
excerpt_separator: ...<!--more-->
tags: faculdade python
comments: true
---
*Estudo Universidade*<br/><br/>
´Algoritmos e programação de computadores 2 (python)´<br/><br/>...<!--more-->
*Texto base 1 parte 1 - Memória*<br/><br/>
O texto trata sobre tipos mutáveis e imutáveis na linguagem Python. E que todos os tipos numéricos; como bool, interface, float e complex; são imutáveis.<br/><br/>
As atribuições em python funcionam da seguinte forma, ao fazer ´A=5´ o python cria a variável e um objeto int e armazena na memória o valor 5, isto se chama ponteiro pois a variavel ´A´ aponta ao valor ´5´. E se você atribuir outro valor á variável A por exemplo ´A=10´ o python esquece, ou melhor, perde o ponteiro ao valor ´5´ e aponta ao novo valor ´10´, ao perder o ponteiro não podemos mais acessar o valor (mas podemos criar outro).<br/><br/>
O mesmo não ocorre a uma lista, pois podemos fazer o seguinte 'lista=[2,3,6]' como dito anteriormente a linguagem cria a variável e cria a lista na memória, e ainda aponta a variável ao endereço da memória. Ao fazermos o seguinte ´lista[1]=4´ a linguagem não cria outro objeto então o endereço é o mesmo. Então a lista é mutável.<br/><br/>
O autor ainda brinca da seguinte forma: e quanto ao objeto str (string), tecnicamente ela é uma lista de caracteres, tanto é que podemos acessar um item fazendo assim: ´umaString="acaba"´ e ainda ´print(umaString[0])´. O autor fala que irá ver e executa algo parecido porém deu erro. E conclui que Strings também são ´imutáveis´.<br/><br/>
Sobre a mutabilidade, o autor da o exemplo com listas fazendo da seguinte forma:<br/><br/>
´listA=[2,4,6]<br/>
listB=listA´<br/><br/>
O que fizemos acima foi criar a variavel listA e apontamos ao valor ´[2,4,6]´ e na linha abaixo atribuimos a mesma lista a ´listB´. Em seguida fez a seguinte atribuição: ´listB[2]=8´<br/><br/>
Na atribuição acima, o indice dois da lista será alterada nas duas variáveis, pois as duas apontam ao mesmo objeto. E se fizermoso codigo abaixo obteremos o mesmo valor.<br/><br/>
´print(listA)<br/>
print(ListB)´<br/><br/>
´Swap´ - o python com atribuições mutiplas permite fazer a troca de objetos entre variaveis, para fazer isto precisariamos de mais uma variavel, fariamos da seguinte forma:<br/><br/>
´a=3<br/>
b=4´<br/><br/>
Essas são as variaveis e se quisessemos trocalas fariamos assim:<br/><br/>
´temp=a<br/>
a=b<br/>
b=temp´<br/><br/>
E com a atribuição multipla fariamos da seguinte forma:<br/><br/>
´a, b = b, a´<br/><br/>
Embora que não vejo uma aplicação, com a atribuição multipla economiza memória descartando a variavel temp.<br/><br/>
*Texto base 1 parte 2 - Arquivos*<br/><br/>
No texto o autor da uma breve informação sobre arquivos, e sobre o sistema de arquivos, que eles são feitos para organizar nossos arquivos e que o sistema de arquivos contem pastas (chamados diretórios) onde colocamos nossos arquivos.<br/><br/>
O topo da hierarquia do sistema de arquivos. onde o topo é denominado diretório raiz e com uma razão, o topo é o inicio da raiz, e os niveis abaixo são raizes "filhas". E que o diretório raiz varia de acordo com o sistema operacional.<br/><br/>
Cada arquivo no sistema pode ser referenciado com um caminho, e este caminho pode ser absoluto, no qual deve ser especificado todo os diretórios incluindo o raiz, no linux um arquivo de texto na pasta Documents do usuario é feito da seguinte forma:<br/><br/>
´/users/rodrigo/Documents/arquivo.txt´<br/><br/>
O caminho também pode ser relativo, onde partimos do diretório atual. Portanto se estivessemos no diretorio Documents (citado acima) e quisessemos usar um arquivo no diretorio /users/shared teriamos que fazer da seguinte forma:<br/><br/>
´../../shared/outroArquivo.txt´<br/><br/>
Cada ´../´ se refere ao diretório pai do diretorio atual, então o diretorio pai do Documents é rodrigo, o diretorio pai do diretorio rodrigo é users ai acessamos a outra pasta e o arquivo.<br/><br/>
Sobre a leitura de arquivos, o python tem o método ´open('nomeArquivo.txt', 'r')´ que retorna um objeto do tipo ´Fluxo de Entrada ou Saída´ e que esse objeto é chamado pelos programadores como ´objeto de arquivo´. Os parâmetros do método open() são o nome do arquivo (um objeto do tipo str) e o modo de abertura (outro objeto str) que podem ser 'r' = leitura, 'w'=escrita, 'a' = acrescimo (ou em ingles ´append´) este método adiciona um novo conteudo ao final do arquivo.<br/><br/>
Alguns metodos de arquivos são arquivoEntrada.read() le o arquivo inteiro, arquivoEntrada.read(n) onde n é a quantidade de caracteres a serem lidos, arquivoEntrada.readline() lê uma linha inteira, arquivoEntrada.readlines() le o arquivo inteiro e retorna uma lista de linhas do arquivo, arquivoEntrada.write(s) escreve a string s no arquivo, e arquivoEntrada.close() fecha o arquivo.<br/><br/>
E ao ler um arquivo o python cria um cursor que aponta a um caractere do arquivo, ao abrir um arquivo com o texto abaixo o cursor apontará ao primeiro caractere. Então o cursor receberá o caractere 'E'.<br/><br/>
´Este arquivo tem 3 linhas.<br/>
<br/>
A linha acima está em branco.´<br/><br/>
Se fizermos ´arquivo.read(5)´ ele lerá os 5 primeiros caracteres e apontará ao proximo caractere, entao o cursor receberá o caractere 'a'. E se apos o ´read(5)´ fizermos o ´readline()´ o python lerá o restante da linha entao retorna 'rquivo tem 3 linhas.\n'. E assim funciona, ele le os caracteres e o cursor aponta ao proximo caractere.<br/><br/>
E o autor mostra como usálos, fazendo exemplos práticos como o read() que é util para ler o arquivo todo e substituir uma substring a uma outra string, contar quantos caracteres o arquivo possui, etc.<br/><br/>
O readlines() é util para ler uma linha inteira, usado para por exemplo analisar um log de um servidor.  que este método é melhor para arquivos grandes pois não temos o arquivo inteiro na memória.<br/><br/>
A seguir o autor mostra como ocorre a gravação em um arquivo. E que para abrir o arquivo para gravação devemos usar ´open('nomeArquivo.txt','w')´ e que deste modo se o arquivo não existir o python o criará. E abrindo com o 'w' (do segundo parametro) temos a função ´write()´ para gravar dados e começará na posição do cursor e retorna a quantidade de caracteres escrito, se quiser escrever novamente o cursor estará no final da string escrita anteriormente... E ainda que se quisermos escrever algo diferente de string devemos converter para string antes de escrevermos com o str().<br/><br/>
*Texto base 2 - Revisão de algoritmos*<br/><br/>
O segundo texto base desta semana fala sobre algorítmos, que eles são um conjunto de passos bem definidos que tem como objetivo solucionar algum problema computacional ou não. Deu exemplos de algoritmos não computacionais (como fazer um sorvete) e computacionais como o algoritmo de euclides para obtenção do mdc de dois numeros. E ainda que os algoritmos tem valores de entrada e valores de saida. Um algoritmo deve ser coerente com as entradas, finito, correto, e com passos que possam ser entendidos pelo usuários.<br/><br/>
E que os algoritmos podem ser escritos / descritos em modo texto (com uma linguagem e semantica) ou de modo gráfico (como fluxogramas que também tem uma semantica de simbolos usados). Os elementos gráficos de um fluxogramas são conectados por setas que indicam o caminho a ser percorrido pelo algoritmo. E o texto continua, só não estou com paciência de continuar.<br/><br/>
*Texto base 3 - Arquivos*<br/><br/>
Este texto base, também não o li todo, mas pelo visto trata da parte dois do texto base 1 porém mais detalhado. Como a codificação ASCII, UTF-8, etc. E ao contrário do primeiro ele começa explicando pela escrita de arquivos (provavelmente por ter somente um método referente, o arquivo.write()). E sobre a abertura de arquivos em python com o metodo open(), ele diz ainda que há outros parâmetros neste método, como descreve abaixo:<br/><br/>
´open(arquivo, modo='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=true, opener=none)´<br/><br/>
E explica cada um parametro, onde file é o arquivo a ser aberto, o mode que são os modos de leitura-escrita-ambos-adição, sobre o buffering é a bufferização do arquivo com as opções 0 (não usa buffer) - 1 (só se usa em arquivos texto e o buffer terá uma linha do arquivo - >1 o inteiro indica o tamanho do buffer - e se não for especificado adotará o valor -1 que é o metodo padrão de buffer, o encode se trata das codificações como "ansi" e "utf-8". Os outros parametros não serão abordados no livro. E mostra os metodos para arquivos, como close(), flush() este método descarrega o buffer do arquivo aberto para a gravação do mesmo sem fechar, read() readline() readlines() write(s) já abordados anteriormente, writelines(lista) que grava todos os itens da lista no arquivo, e seek(int) que leva o cursor na posição int de caracteres do arquivo.<br/><br/>
{% if page.comments %}
<div id="disqus_thread"></div>  
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://rregio-top.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}