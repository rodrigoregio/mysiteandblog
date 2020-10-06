---
layout: post
title: AsyncTask e Android
excerpt_separator: <!--more-->
tags: Android
comments: true
---
O curso abordou sobre AsyncTask que pelo que entendi do curso, o **AsyncTask** executa <!--more--> procedimentos assincronos, ou seja, que rodam em background. Para processamentos assincronos não podemos executar na thread da UI (User Interface), então criamos esse AsyncTask que cria uma Thread que espera o resultado do acesso. Para testar meus entendimentos Criei um aplicativo que usa a api [Genderize.IO](https://genderize.io) (ela responde se um ou mais nomes são do sexo masculino ou feminino). Neste post não colocarei muito código, para ver o código acesse o projeto no github [Projeto](https://github.com/rodrigoregio/NameAPIs).

Para acessar API's primeiramente devemos adicionar permissão para HttpUrlConnection no AndroidManifest.

```xml
<uses-permission android:name="android.permission.INTENET"/>
```

O aplicativo pega nomes digitados (separados por virgula) em um TextView e também há um botão (ao digitar os nomes o usuario clica no botão). Ao clicar no botão é chamado a função verificaNomes, ela pega os nomes digitados pelo usuário e quebra (split) separando por virgula, exemplo, "Rodrigo,José" se tornará um array de Strings que nomeei nomesList e terá os valores ["Rodrigo", "José"]. Se a nomesList tiver um nome somente ele acessará a url `"https://api.genderize.io?name="+nomesList[0]`, e se tiver mais de um nome acessará com um for que ficará da seguinte forma:
    
```java
stringBuilder = new StringBuilder("https://api.genderize.io/?&");
for (String nome : nomesList) {
	stringBuilder.append("&name="+nome);
}
```

O aplicativo funcionará somente online, então fiz uma função para saber se o usuario está online. Se o usuario estiver online chamará uma função chamada buscaDados.

Antes da função buscaDados explicarei sobre a AsyncTask (até porque a buscaDados chamará a AsyncTask. Em nossa classe MainActivity mesmo criamos a classe MyTask que extende a AsyncTask, para extender devemos extender da seguinte forma extends **AsyncTask<String,String,String>**.

Não tinha entendido o porque da tag **<String,String,String>**, mas pesquisando mais sobre ela, encontrei que ela recebe tipo três "parâmetros". O primeiro String é um parâmetro (que usamos para passar a url onde ela pega os dados. O segundo String é o progresso (pode-se substituir o String por um int e exibirá a porcentagem do procedimento como quando fazemos um download. E o terceiro String é o resultado, o que ele pegou.

Fazendo isto nós teremos que sobrescrever ao menos um método, o **doInBackground()**. Nele criamos uma String que receberá o conteúdo da api. Criamos uma classe chamada **HttpManager**.

Essa HttpManager é o que realiza a conexão, criamos um metodo chamado **getDados(String uri)** que tem como parametro a url, e ela trabalha como uma conexão com banco de dados. Criamos uma URL com a uri que passamos como argumento. Criamos uma conexão com HttpUrlConnection abrimos a url fazendo um casting para o HttpUrlConnection. Como disse anteriormente ela trabalha como um banco de dados, para mais detalhes acesse o projeto no Github [classe HttpManager](https://github.com/rodrigoregio/NameAPIs/blob/master/app/src/main/java/top/rregio/nameapis/HttpManager.java)

Após retornar ao doInBackground retornamos a string conseguida na api. Na classe do AsyncTask também sobrescrevi outros dois métodos o **onPreExecute** (nele coloquei para que mostre somente um progressbar (item com a animação de que está carregando) e outro chamado **onPostExecute** (fiz com que ele desabilite a animação do progressbar e chame um metodo chamado atualizarView(String s) este método somente coloca a string retornada no doInBackground em um TextView.

E por enquanto é somente estes passos que meu aplicativo faz, e é isto que entendi o sobre acesso a API's com Android.