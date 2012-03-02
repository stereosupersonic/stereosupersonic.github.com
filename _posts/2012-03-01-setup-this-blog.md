---
layout: post
title: Blog Setup
---

{{ page.title }}
================

<p class="meta">01 März 2012 - Wartenberg</p>

Nach dem ich schon länger nach einer einfachen Lösung für's bloggen gesucht habe,
bin ich zufällig auf die Kombination von Github-Pages und [Jekyll](http://github.com/mojombo/jekyll) gestoßen.

Hier beschreibe ich nun wie ich die erste Version meiner Seite zum Laufen gebracht habe.

Github Page eirichten
-----------------------------------------------------
1. ein Gihub Repository mit **Username**.github.com anlegen.
   In meinen Fall [stereosupersonic.github.com](http://stereosupersonic.github.com)  
1. das Projekt lokal erstellen 

<pre class="terminal"><code>
    mkdir stereosupersonic.github.com  
    cd stereosupersonic.github.com 
    git init
    touch index.html
    git add index.html   
    git commit -m 'hompage init' 
    git remote add origin git@github.com:stereosupersonic/stereosupersonic.github.com.git
    git push origin master
</code></pre>     

*unter [http://stereosupersonic.github.com](http://stereosupersonic.github.com) sollte man einen leere Seite sehen*    


##Domäne anpassen

1. eine Datei Namens **CNAME** anlegen und die Domäne eintragen *deimel.de*
1. nach github Pushen
1. beim Hoster oder DNS-Provider den DNS A record auf *stereosupersonic.github.com* zeigen lassen    


##Jekyll einrichten
1. gem install jekyll
2. die Verzeichnisse *"_layouts"*, *"_posts"*, *css* und *images* anlegen
3. habe mich hier <https://github.com/mojombo/mojombo.github.com> inspirieren lassen ;-) 
4. Pushen       


   
##ersten Blog Post schreiben  
1. im Verzeichnis "_posts" einen neu Datei anlegen im Muster **Jahr-Monat-Tag-titel-ohne-leerzeichen.md**
2. im Header layout: post  und title: Mein erster Post eintragen
3. mit Markdown den gewünschten Text formatieren 
4. Pushen

***Erster Blog-Eintrag ist online.***     
  
Probleme
----------------------------------------------------- 

wenn beim Start der Fehler kommt *invalid byte sequence in US-ASCII*
in der Bash folgende Variablen setzen:   
<code>export LANG=de_DE.UTF-8 </code>    
<code>export LC_ALL=de_DE.UTF-8 </code>  
   

TODO
--------
1. atom.xml für rss 
2. rss bei Feedburner eintragen
3. Template Engine auf Haml umstellen
4. Layout auf Twitter-Bootstrap umstellen   