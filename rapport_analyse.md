---
title: Évaluation Iramuteq, Markdown & Pandoc
author: Soniya Abbas ; Ophélie Hersant
date: 10/01/19
---

# Description 

Voici une analyse du corpus sur Robert Escarpit. Elle a été effectuée dans le cadre du cursus _"Hyperédition"_. L'objectif est d'analyse le corpus textuel qui contient _23 textes de Robert Escarpit sur Iramuteq_. C'est un compte-rendu qui explique tous les etapes de notre travail et le resultat obtenu.

Dans le premier temps, on vous présenterai toutes les étapes techniques et préparatoires avant de commencer l'analyse. Ensuite, on fera l'observation du processus d'analyse des données et leur visualisation. Enfin, nous finirons par la convertation ce rapport via Pandoc.

# Étap 1. Corpus 

Pour commencer le travail on a pris les textes classés dans le _"Articles et Communications scientifiques"_ partagés par Lucie Vieillecroze dans le cadre du **projet ReNum**. Ces textes a été nettoyé car après la numérisation ils avaient beaucoup de fautes techniques. Ensuite, on les a regroupé sur [le drive](https://drive.google.com/drive/u/0/folders/1Q9XiPuiUL8RnBsatS2sW_-IMrQ7uD2aX).

Puis, nous avons nettoyé le texte en supprimant les notes et les références (parce que pendant la premiere analyse on avait pas mal des abriviations qui fait la partie des graphes). Enfin on a ajouté des variables qui nous ont permis d'encoder le texte et de l'importer dans Iramuteq. Le principe d'encodage est le suivant :

~~~~
Variable : **** *categorie_XXX *categorie_XXX *categorie_XXX *categorie_XXX 
           *titre
~~~~

On a intergé les meta-donnees suivants :
- subject
- type
- date
- langue
- titre

Bilan : 23 variables.

Lien vers le fichier avec le corpus [.txt](https://github.com/soniyabbas/Analyse/blob/master/textes_corrigés_corpus_Escarpit.txt)

>Suite à l'encodage effectué on peut créer des sous-corpus differets. On est obligé à faire cette action car le corpus général est trop lourd - les visualisations ne sont pas representables (on ajoute dans ce dossier seulement quelques visualisations realisees pour montrer ce point de vue). 
>C'est pourquoi, on va analyser le sous-corpus regroupé par le meta-donnees "langue_français" (les autres langues ne sont pas pertinentes dans cette analyse). Puis, on va créer encore un sous-corpus par thèmes pour comparer les lexiqaux de thematiques differents (on a pris deux themes : information-communication et littérature).

# Étap 2. Analyse du sous-corpus en français

### Statistique générale

Nous commençons par l'analyse du sous-corpus en français pour voir sa statistique générale. On choisi tout par defaut pour obtenir le meilleur resultat dans la petite résumé de l’information basique des textes :

| Facteur | Quantité | Commentaire|
| -------------| -------------| -------------|
| Nombre de textes | 19 | |
| Nombre d'occurrences | 87257 |
| Nombre de formes | 7405 |
| Nombre d'hapax | 3371 | (3.86%des occurrences - 45.52% des formes) |
| Moyenne d'occurrences par texte | 4592.47 | |

Sur le graphique, on voit la dépendance, la fréquence des mots et la quantité des occurrences. Les rangs les plus élevés correspondent aux mots les plus fréquents. 

En même temps le logiciel a généré des tableaux .CSV qui nous permettent de voir les données differentes : 
- la fréquence décroissante des mots utilisés dans le corpus au total et leurs types,
- les formes les plus actives sans des articles, propositions, verbes (être et avoir) etc. (les agents pareils : la fréquence et les types)

>ce type de formes on va reprendre pour toutes nos analyses car ils sont plus pertinents

- les mots supplémentaires - secondaires,
- le nombre des mots qui ont été utilisé une fois dans le corpus.

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/statistique_generale.png">
</p>

### Nuage de mots

Cette analyse est assez simple et représente juste une illustration à partir des données que l'on utilise. Le but est de montrer l'ensemble des mots avec le plus grand nombre d'occurrences qui est déterminé par la taille de la police.

Là, on voit que des sujets principals de 19 textes sont autour des mots "communication", "information", "livre", "masse", "littérature", etc. 

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/nuage_1.png">
</p>

### Méthode Reinert

C'est la classification hiérarchique descendante qui permet de regrouper des mots et les répartir selon des thématiques mesurée par un test au Chi². L'analyse découpe le texte en segment (dendrogrammes), les regroupe en classe en fonction des composantes (des mots).

Sur ce graphique on voit la liste des mots regroupés dnas les classes differentes qui à son tour associees. Une classe represente les formes.

Cette analyse a regroupé mon corpus dans 6 classes. 

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/dendrogramme_fr.png">
</p>

Ce monde lexical renvoie de façon évidente aux domaines de l'information et la communication. En fonction des branches on a des liaisons entre les mots.

#### AFC (Analyse Factorielle des Correspondances)

Ce type d'analyse nous propose de voir la classification hiérarchique descendante sur une variable ou sur un ensemble de variables. Elle organise les données, après transformation statistique, sous forme de graphique à deux dimensions pour montrer la différence entre les variables ce que nous permet aussi de voir les liaisons entre la fréquence et le type de mot (la relation lexicale plus généralement). 

Ce sont les visualisations liées à l'analyse factorielle de correspondance mais réalisée à la base de l'analyse Reinert. On peut prendre pour hypothèse que les 5 classes mélangées décrivent le corpus principal ; une autre jouent un rôle secondaire.

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/fr_frequence.png">
</p>

Deux graphiques suivants sont modifié en fonction de criteriers supplementaires (_dans ce cas cela rend des graphes ilisible_).

##### Graphe des classes avec taille des mots proportionnelle à leur fréquence

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/graph_afc_frequence.png">
</p>

##### Graphe des classes avec taille des mots pro- portionnelle à leur score de chi-2 

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/graph_afc_chi2.png">
</p>

# Étape 3. Analyse comparative des textes de deux sujets en français

Afin de rendre l'analyse un peu plus précise, nous avons décidé de prendre comme exemple l'analyse de deux sujets (**information-communication et littérature**) que nous avons mis en évidence au cours de la phase de codage. Tous sont également parmi les textes en français.

Dans le premier temps, on a créé deux sous-corpus a partie le sous-corpus des textes en français. Le premier "Infocom" qui ont les métas-données : "communication", "infocom" et "information scientifique". Le deuxieme "lit" : "litterature" et "littérature de masse". 

Ensuite, on fais les memes analyse que dans la deuxieme etape.

### Infocom - Statistique générale

| Facteur | Quantité | Commentaire|
| -------------| -------------| -------------|
| Nombre de textes | 11 | |
| Nombre d'occurrences | 54092 | |
| Nombre de formes | 4881 | |
| Nombre d'hapax | 2159 | (3.99%des occurrences - 44.23% des formes) | 
| Moyenne d'occurrences par texte | 4917.45 |

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/resume-infocom.png">
</p>

### Lit - Statistique générale

| Facteur | Quantité | Commentaire|
| -------------| -------------| -------------|
| Nombre de textes | 2 | |
| Nombre d'occurrences | 7301 | |
| Nombre de formes | 1767 | |
| Nombre d'hapax | 1052 | (14.41%des occurrences - 59.54% des formes) | 
| Moyenne d'occurrences par texte | 3650.50 |

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/resume-lit.png">
</p>

### Infocom - Nuage de mots

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/nuage_infocom.png">
</p>

### Lit - Nuage de mots

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/nuage_lit.png">
</p>

### Infocom - Méthode Reinert et AFC

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/dendrogramme_infocom.png">
</p>

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/afc-infocom.png">
</p>

### Lit - Méthode Reinert et AFC

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/dendrogramme_lit.png">
</p>

<p align="center">
  <img src="https://github.com/soniyabbas/Analyse/blob/master/images/afc-lit.png">
</p>

---

### Bilan

