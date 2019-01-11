# Pandoc 

À l'aide du _Terminal_ et après l'installation du package supplémentaire _LaTex_ on a pu appliquer les commandes suivantes et créé deux fichiers en formats PDF et HTML : 

~~~
1. pwd - pour voir où on se trouve (normalement /Users/*nom d'ordinateur/utilisatur*)
2. cd - changer le dossier où on va travailler avec notre fichier .md (cd /Users/*nom
   d'ordinateur/utilisatur*/desktop/analyse_corpus_iramuteq-master
3. On applique des commendes qui nous aident à transformer le fichier en PDF et HTML :

pandoc -s -o rapport_analyse.pdf rapport_analyse.md

pandoc rapport_analyse_2_avec_svg.md -f markdown -t html -s -o rapport_pandoc.html

pandoc -s -o --css pandoc.css rapport_pandoc.html
~~~

Fichier d'analyse en [PDF]() et [HTML]()

Regarder l'analyse complète du corpus scientifique de Robert Escarpit [ici.](https://github.com/soniyabbas/Analyse_corpus_iramuteq/blob/master/rapport_analyse.md)
