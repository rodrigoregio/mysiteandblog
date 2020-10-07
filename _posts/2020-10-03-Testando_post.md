---
layout: post
title: Testando post
excerpt_separator: <!--more-->
tags: teste web
comments: false
---

Olá, este é somente um post de teste que estou fazendo para verificar se está ok...<!--more--> E aparentemente está tudo bem, porém ainda falta estilizar a página do blog, pois não quero que a fique assim. E ainda faltam algumas estilizações / edições nos textos das páginas.<br/><br/>

Como informado, já irei pegar um curso no site Treinaweb e fazer e daqui um ou dois dias postarei algo no blog comentando sobre o que entendi do curso.<br/><br/>

Obrigado por tudo Jekyll.<br/>
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