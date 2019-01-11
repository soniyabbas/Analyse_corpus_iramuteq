# Pandoc 

On a utilisé les commandes suivants pour recuperer les fichiers en formats PDF et HTML : 

~~~~
1. cwd - pour voir où on se trouve (normalement /Users/*nom d'ordinateur/utilisatur*)
2. cd - changer le dossier où on va travailler avec notre fichier .md (cd /Users/*nom
   d'ordinateur/utilisatur*/desktop/analyse_corpus_iramuteq-master
3. On applique des commendes qui nous aident à transformer le fichier en PDF et HTML :

pandoc -s -o rapport_analyse.pdf rapport_analyse.md

pandoc -s -o rapport_analyse.pdf --css pandoc.css rapport_pandoc.html
~~~
