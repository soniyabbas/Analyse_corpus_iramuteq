---
title: Évaluation Iramuteq, Markdown & Pandoc
author: Soniya Abbas ; Ophélie Hersant
date: 10/01/19
---

# Description 

Voici une analyse du corpus sur Robert Escarpit. Elle a été effectuée dans le cadre du cursus _"Hyperédition"_. L'objectif est d'analyse le corpus textuel qui contient _23 textes de Robert Escarpit sur Iramuteq_. C'est un compte-rendu qui explique tous les etapes de notre travail et le resultat obtenu.

Dans le premier temps, on vous présenterai toutes les étapes techniques et préparatoires avant de commencer l'analyse. Ensuite, on fera l'observation du processus d'analyse des données et leur visualisation. Enfin, nous finirons par la convertation ce rapport via Pandoc.

# Étap 1. Corpus 

Pour commencer le travail on a pris les textes classés dans le _"Articles et Communications scientifiques"_ partagés par Lucie Vieillecroze dans le cadre du **projet ReNum**. Ces textes a été nettoyé car après la numérisation ils avaient beaucoup de fautes techniques. Ensuite, on les a regroupé sur (le drive)[https://drive.google.com/drive/u/0/folders/1Q9XiPuiUL8RnBsatS2sW_-IMrQ7uD2aX]

Puis, nous avons nettoyé le texte en supprimant les notes et les références (parce que pendant la premiere analyse on avait pas mal des abriviations qui fait la partie des graphes). Enfin on a ajouté des variables qui nous ont permis d'encoder le texte et de l'importer dans Iramuteq. Le principe d'encodage est le suivant :

> Variable : **** *subject_XXX *type_XXX *date_XXX *langue_XXX 
             *titre

Bilan : 43 variables.

Lien vers le fichier avec le corpus (.txt)[]
