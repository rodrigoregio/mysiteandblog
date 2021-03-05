---
layout: post
title: Experiências chatbot da twitch
excerpt_separator: <!--more-->
tags: twitch python
comments: true
---
Sim, comecei a fazer livestream (ou melhor, livecoding).<!--more--> E devido a isto achei que meu canal deveria ter um bot totalmente feito na live e com as instruções / sugestões dos participantes no chat (até agora poucas pessoas aparecem na live, logo não tive muitas instruções ou sugestões, mas vamos seguindo kkkk). 

<br>Dado este conceito vou dar aqui minhas visões de como fazer o bot. Por estudos da faculde do ano passado achei melhor fazer o bot com a linguagem Python. Então decidi procurar um tutorial na internet de como fazer isto e encontrei este tutorial [aqui](https://dev.to/ninjabunny9000/let-s-make-a-twitch-bot-with-python-2nd8) e segui os passos.

<br>Primeiro ele pede para fazer uma conta na twitch (isso foi facil pois ja tinha kkk), depois ele pede para acessar uma url e solicitar o codigo de autenticação, e outro link para registrar o bot na twitch. Até aqui normal :)

<br>Após isso ele pede para instalar o python e as bibliotecas necessárias (pipenv, twitchio).

<br>E depois disso ele pede para criar um arquivo .env (para os mais antigos é como um arquivo .ini) com os dados obtidos nas urls citadas, mais alguns dados como o nome do bot, o canal em que ele irá ficar, etc. E no final do arquivo colocar um if para executar o bot.

<br>Após isso o site diz para acordar o bot e executar o comando informado, executei e o bot não acordou, deram várias mensagens de erro e como solucionar (dizia para verificar se os dados estão corretos e se o arquivo .env e o arquiovo bot.py estão na mesma pasta, a solução informada era simples, mas como não funcionou procurei outros tutoriais de como fazer isso.

<br>Navegando um pouco encontrei esse repositório da twitch no [github](https://github.com/twitchdev/chatbot-python-sample) e procurei executar de forma mais parecida que pudesse. E Bingo!, o bot acordou! Meio manco mas acordou kkk, disse meio manco pois algumas coisas não funcionaram, detalharei aqui.

<br>Primeiro, abri logo o arquivo bot.py vi que este bot recebia os dados do arquivo .env nos próprios argumentos que fosse chamado. Então adaptei meu codigo para que recebesse os dados do arquivo .env (posteriormente  modifiquei o arquivo .env para data.ini, o funcionamento é o mesmo). Criei a classe twitchbot (com o nome BoiroBot), criei minha classe seguindo os moldes do repósitório, porém (agora vem os defeitos) não sabia como responder diretamente a quem chamava o bot, e outro defeito (que perdura até hoje) é que o bot entra com meu nome e não com o dele. Na verdade o segundo problema é o menor. Então procurei outro tutorial para seguir.

<br>Navegando mais um pouco encontrei este tutorial no [youtube](https://www.youtube.com/playlist?list=PLYeOw6sTSy6ZFDkfO9Kl8d37H_3wLyNxO) e percebi que seguia os moldes do repositório da twitch, então consegui solucionar o problema de pegar o nome de quem chamou o bot.

<h1>Considerações finais</h1>

<br>Na minha opinião o mais dificil foi começar a fazer o bot, pois requer certa atenção no desenvolvimento. Após o início segui / sigo o desenvolvimento tranquilamente... Ainda não consegui solucionar o problema do nome do bot, já pesquisei de algumas formas e não o encontrei, se você souber me orientar ficarei muito agradecido!

<br>Sintam-se livres para me contactar nos comentários ou nas minhas redes sociais!
PS.: Já parei de fazer o livecoding pois meu computador não é adequado para isto e atualmente estou trabalhando.