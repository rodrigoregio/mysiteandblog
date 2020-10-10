---
layout: post
title: Redes, componentes, protocolos e serviços
excerpt_separator: <!--more-->
tags: faculdade
comments: true
---
*Texto base 1 parte 1 - Componentes*<br/><br/>
Olá a todos, sobre esta matéria eu fiz umas anotações, porém meu texto ficou muito grande, e você pode conferir no link ao final da página.<!--more--> Aqui tentarei resumir os parágrafos em até 3 linhas, vamos lá?<br/><br/>
Começando o autor informa que a internet é a rede que conecta milhões de dispositivos de computação ao redor do mundo, há algum tempo atrás eram em menor quantidade.<br/><br/>
Os dispositivos conectados tem o nome de **sistemas finais** e são interligados de diversas formas, como com cabos coaxiais, fios de cobre trançados, etc. Os dispositivos finais enviam pacotes pela rede.<br/><br/>
Alguns dos dispositivos da rede são os **roteadores** e **switches**, os switches são usados em redes de acesso (para por exemplo separar um departamento) e os roteadores geralmente são o nucleo da rede (porta de entrada e saida de dados da sua casa/empresa). Os dados percorrerão a rede por uma **rota** (ou caminho).<br/><br/>
No parágrafo seguinte o autor faz uma analogia como que uma empresa envia produtos a um deposito com alguns kliômetros de distancia, que divide os produtos em caminhões (análogos aos pacotes de dados), que percorrerão um caminho (análogos á rota). E que no destino o caminhão é descarregados e os produtos agrupados novamente.<br/><br/>
Uma breve descrição sobre os ISP's que são provedores de serviços de internet (residênciais mais famosos no Brasil sao Claro, Vivo, etc). E que estes conectam dispositivos finais, para isto devem estar conectados com outros. Eles são separados por niveis (quanto mais alto o nivel mais rapido são).<br/><br/>
Breve descrição sobre a IETF (Força Tarefa de Engenharia da Internet), que fazem os documentos padrões sobre os protocolos. Os documentos são chamados RFC (requisição de comentários), esses documentos são solicitados analise e comentários por outras pessoas.<br/><br/>
**Texto base 1 parte 2 - Serviços**<br/><br/>
Aqui o autor da outra definição da internet, que ela é uma infra estrutura que provê serviços á aplicações. Os serviços são executados em sistemas finais, e aplicações são conhecidas como **aplicações distribuidas** por trocarem informações. Os serviços e aplicações orientam a internet a realizarem a troca de informações.<br/><br/>
Os sistemas finais oferecem uma API que é um conjunto de regras que um emissor deve cumprir para enviar a mensagem. E faz uma analogia de que Alice quer enviar uma carta a Bob (que está em outro local), e explica sobre os procedimento ao enviar uma carta, como o endereçamento, selo, enviar aos correios, etc. E que isso ocorre nas redes.<br/><br/>
**Texto base 1 parte 3 - Protocolos**<br/><br/>
Sobre os protocolos o autor faz a analogia de quando se quer saber as horas na rua, e como ocorre esta conversa para obter a informação, dizemos oi, esperamos resposta, respondido sabemos se a pessoa pode nos atender ou não, podendo pedimos as horas e aguardamos a resposta.E o mesmo ocorre nas redes.<br/><br/>
Então um protocolo define formato e ordem das mensagens trocadas, bem como ações realizada na transmissão / recebimento de mensagens.<br/><br/>
**Texto base 1 parte 4 - Protocolos e modelos de serviços**<br/><br/>
O autor faz outra analogia para explicar as camadas de protocolos, e usa os procedimentos de quando vamos fazer uma viagem de avião. Descreve que compramos a passagem, vamos ao balcão da linha aérea, despachamos a mala, acessamos o portão de embarque, embarcamos, decolamos, etc. E o mesmo ocorre nas redes.<br/><br/>
Cada passo que damos acima é uma camada, e que cada camada realiza um serviço e têem seus próprios procedimentos, e alguns complementam outros. E ainda podemos alterar como funciona um serviço sem afetar a funcionalidade de outros, como o desembarque por sexo (portões diferentes para homens e mulheres).<br/><br/>
Camadas de aplicação<br/><br/>
As camadas de aplicação é onde residem as aplicações de rede e seus protocolos, alguns deles são HTTP, FTP, SMTP e outros. E as aplicações trocam mensagens.<br/><br/>
Camada de transporte<br/><br/>
Camada de transporte é onde é carregado os dados da aplicação entre os lados cliente e servidores de uma aplicação. Os protocolos são TCP e UDP, o TCP oferece serviços orientados a conexão ás aplicações, estas trocam **segmentos**.<br/><br/>
Camada de rede<br/><br/>
Camada de rede é responsável por movimentar os pacotes de dados que nesta camada são conhecidos como **datagrama**. A camada anterior passa o segmento e o endereço de destino, esta provê a entrega. Define os campos do datagrama e como roteadores/sistemas agem nesses campos. Possui somente  o protocolo IP e todos itens da rede devem executa-lo.<br/><br/>
Camada de enlace<br/><br/>
A camada de rede roteia os datagramas entre origem e destino, porém depende da camada de enlace de dados. Seus serviços dependem do protocolo usado, alguns são Ethernet, Wi-fi (conjunto de protocolos que começam com IEEE 802), PPP. Seus pacotes são chamados **quadros**.<br/><br/>
Camada Física<br/><br/>
A camada de enlace movimenta quadros entre os elementos da rede, porém a camada física movimenta os bits dentro de um quadro individualmente. Esta camada depende do enlace e do meio de transmissão (fios de cobre trançados, fibra ótica, etc). Em cada meio de transmissão os bits percorrem o enlace de modo diferente.<br/><br/>
Modelo OSI<br/><br/>
Aqui fala que o modelo OSI possui 7 camadas e o modelo padrão da Internet contém 5. E que 5 camadas OSI são equivalentes ás 5 da Internet. Camadas OSI **aplicação, sessão, apresentação, transporte, rede, enlace e física**, Internet **aplicação, transporte, rede, enlace e físico**. OSI antigo, Internet atual. Na Internet as duas camadas (sessão e apresentação) estão presentes na de aplicação.<br/><br/>
**Texto base 1 parte 4 - Encapsulamento**<br/><br/>
A partir do envio os dados passam na pilha de protocolos (OSI ou Internet) de cima para baixo na saida e na chegada ao destino percorre de baixo para cima. Cada ponta do cabo realiza a verificação pertencente. E o autor termina com outra analogia de Alice e Bob, dizendo que para enviar um memorando é realizado o encapsulamento colocando envelopes, e na outra ponta é desencapsulado.<br/><br/>
**Texto base 2 - Definição de redes**<br/><br/>
Neste texto o autor começa definindo a rede como um conjunto de dois ou mais dispositivos, chamados **nós** que usam um conjunto de regras, chamados **protocolos**, em comum para compartilhar recursos (de hardware ou mensagens) entre sí através da rede.<br/><br/>
Dentre os nós que podem se conectar podemos citar:
* Impressoras
* Repetidores
* Terminais de computadores
* Pontes (bridges)
* Computadores
* roteadores
Termos e expressões nas redes de computadores serão descritos abaixo:<br/><br/>
**Endereçamento** - É colocar um endereço a cada nó da rede, seria o equivalente a fazer o que as empresas de telefonia fizeram, todos os telefones tem um número próprio.<br/><br/>
**Meio** - Ambiente físico para conectar os nós da rede, normalmente algum cabo ou até o ar (pelo wi-fi).<br/><br/>
**Protocolos** - É um conjunto de regras usadas para realizar uma conexão, assim como os humanos tem regras para se comunicar em todos os lugares. Não nos comunicamos em um tribunal como nos comunicamos em uma festa por exemplo. Assim os nós tem protocolos que regem a forma de comunicação, entre eles o SMTP, HTTP, etc.<br/><br/>
**Roteamento** - significa determinar qual será o caminho percorrido pelos pacotes de dados. Para fazer o roteamento dos pacotes utilizamos um **roteador**.<br/><br/>
**Classificação de redes pela área ocupada**<br/><br/>
***Local Area Network*** - para redes menores de 10 km de raio, usada para conectar casas, prédios, empresas, etc.<br/><br/>
***Wide Area Network*** - para redes com áres maiores de 10 km de raio, usada para conectar computadores entre diferentes países, estados ou cidades.<br/><br/>
***Metropolitan Area Network*** - para conectar computadores ao longo de uma grande cidade ou região metropolitana. Imagine, uma empresa deseja conectar-se comas filiais na região da cidade.<br/><br/>
***Personal Area Network*** - para conectar nós próximos, dispositivos bluetooth criam esta rede.
***Global Area Network*** - para conectar redes de longa distância ao redor do globo. A internet é o exemplo de uma GAN.<br/><br/>
***Storage Area Network*** - Esta não sei o porque de ela estar aqui, mas ela é uma rede definida especificamente para armazenar dados.<br/><br/>
**Classificação de redes pela topologia**<br/><br/>
![Topologias de rede](https://upload.wikimedia.org/wikipedia/commons/9/96/NetworkTopologies.png)<br/><br/>
**Rede ponto a ponto** - Neste tipo de rede o nó só pode se comunicar com o nó adjacente (ao lado). Suponhamos a rede com os nós A, B e C o nó A só pode se comunicar com o nó B, então para se comunicar com C fala primeiro com B. Na figura acima a rede em barramento (Bus) é a unica que não a representa.<br/><br/>
**Rede estrela** - Neste tipo de rede todos os nós se conectam a um nó adjacente central. Os nós na extremidade não se conectam entre si, somente com o núcleo (geralmente um Hub). Na imagem acima a terceira rede da primeira linha a representa (star)<br/><br/>
**Rede em laço** - Neste tipo de rede todos nós se conectam entre sí, um exemplo dela é a em anel (ring) e a totalmente conectada (fully connected). Na em anel, se um cabo se romper a rede não é danificada, pois os dados trafegam nos dois sentidos (horário e antihorário). Na completamente conectada se um cabo se romper elas se comunicarão por outra rota.<br/><br/>
**Rede em árvore** - Neste tipo de rede os nós estão dispostos em uma forma hierárquica, o nó principal conecta os de nível abaixo, e por assim vai na rede. Na figura a segunda topologia da segunda linha a representa (tree).
***Redes de difusão*** - Neste tipo de rede sempre que uma máquina envia uma mensagem, ela (a mensagem) se propaga por toda a rede de forma que todos os nós a escutem, não sei quanto á segurança nessas redes, mas os nós irão analisar da seguinte forma: Esta mensagem é pra mim? Sim, recebe a mensagem. Não, continuo o trabalho e ignoro a mensagem. Uma vantagem é que podemos classificar as mensagens em 3 tipos: Mensagens destinadas a um unico nó (provavelmente aplicam algum nivel de segurança), mensagens destinadas a uma quantidade de nós específicos e mensagens destinadas a todos os nós.
**Redes em barramento** - este tipo de rede tem as características da rede de difusão (todos os nós irão ouvir a mensagem). Na figura a ultima topologia a representa (Bus).
**Rede via satélite** - Neste tipo de rede é colocado um satélite na órbita da terra para transmitir as mensagens. Este tipo de rede também é uma rede de difusão. E não há uma topologia na figura para a representar.<br/><br/>

[Link texto completo](https://www.notion.so/Web-semana-1-0c23a8849df045ddaf1c300f01a99881)