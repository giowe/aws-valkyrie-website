---
layout: home
title: AWS Valkyrie - Node.js web application framework
menu: home
lang: en
redirect_from: "/en/index.html"
url_prefix: aws-valkyrie-website
---
<section id="home-content">
  {% include header/header-{{ page.lang }}.html %}
  <div id="overlay"></div>
  <div id="homepage-leftpane" class="pane">
    <section id="description">
        <div class="aws-valkyrie"><a href="/{{ page.url_prefix }}/">AWS Valkyrie</a><span id="aws-valkyrie-version">{{ site.data.aws-valkyrie.current_version }}</span></div>
        <span class="description">Fast, unopinionated, minimalist web framework for <a href='https://nodejs.org/en/'>Node.js</a></span>
    </section>
    <div id="install-command">$ npm install aws-valkyrie --save</div>
  </div>
</section>

<section id="intro">

  <div id="boxes" class="clearfix">
    <div id="web-applications">
      <h3>Web Applications</h3> AWS Valkyrie is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.
    </div>

    <div id="apis">
      <h3>APIs</h3> With a myriad of HTTP utility methods and middleware at your disposal, creating a robust API is quick and easy.
    </div>

    <div id="performance">
      <h3>Performance</h3> AWS Valkyrie provides a thin layer of fundamental web application features, without obscuring Node.js features that you know and love.
    </div>

    <div id="frameworks">
      <h3>Frameworks</h3> Many <a href="{{ page.lang }}/resources/frameworks.html">popular frameworks</a> are based on AWS Valkyrie.
    </div>
  </div>

</section>