Cours DH UniNe

# Analyse de réseau avec Gephi

Simon Gabay
Genève, Lundi 20 avril 2020

---
# Installation
---
## Java

Pour faire fonctionner Gephi, il vous faut installer Java 8 (_Java SE Runtime Environment 8_ de son petit nom). Pour ce faire:
* Allez à cette adresse: https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html
* Créez si besoin un compte _Oracle_

---

![65% center](images/Java.png)

---
## Instructions supplémentaires pour les utilisateurs _Windows_

1. Attention: Gephi s’installe tout seul en **32-bit** et il nous faut du **64-bit**
	* ouvrir `C:\Program Files (x86)\Gephi-0.9.1\bin\`.
	* Il faut executer `gephi64.exe` et pas ` gephi.exe` si vous avez une machine récente (_Windows 10_ 64bit).

2. pour trouver gephi64 : aller dans le menu Démarrage
	* Chercher gephi;
	* Clic droit (propriétés): donne l’adresse du dossier du fichier où est `gephi.exe`, qui est aussi le dossier où est gephi64.exe
	* Lancer `properties`. Contrôler que le chemin de fichier est celui de `gephi64.exe?.
3. Penser (très sérieusement) à arrêter d'utiliser _Windows_.

---
# Préparation des données

---
## Types de réseau

* réseau normal
* réseau bipartite

---

## Réseau normal
On a qu'un seul type de sommet, et chaque individu est relié à un autre par une valeur commune. Dans ce cas les auteurs, imprimeurs et éditeurs sont reliés par l'identifiant de l'imprimé qui les a réunis.

| Clef      | Valeur      |
|-----------|-------------|
| Imprimé_1 | Auteur_1    |
| Imprimé_1 | Imprimeur_1 |
| Imprimé_1 | Imprimeur_2 |
| Imprimé_1 | Editeur_1   |
| Imprimé_2 | Auteur_1    |
| Imprimé_2 | Editeur_2   |

---
## Réseau bipartite

On a deux types de sommets, chaque individu étant lié à celui à qui il est associé dans le tableau.

| Clef        | Valeur      |
|-------------|-------------|
| Auteur_1    | Imprimeur_1 |
| Auteur_1    | Imprimeur_1 |
| Auteur_1    | Imprimeur_2 |
| Auteur_1    | Editeur_1   |
| Auteur_1    | Editeur_2   |
| Imprimeur_1 | Imprimeur_1 |
| Imprimeur_1 | Editeur_1 |
| Imprimeur_2 | Editeur_1   |
| Auteur_1    | Editeur_2   |

---
## Créer le réseau pour Gephi

À partir de ce type de tableau, vous pouvez créer les fichiers nécessaires pour _Gephi_ en utilisant l'application en ligne https://medialab.github.io/table2net.

---
# Premier test
---
## Ouverture

Nous allons devoir importer nos données. Elles peuvent être de deux types:
* des fichiers de tableur classiques (`.tsv`, `.csv`)
* des fichiers `.gexf` (_Graph Exchange XML Format_) – l'équivalent d'un objet _igraph_ dans _R_.

---
## Mes fichiers
Il faut faire attention à utiliser des en-têtes pour les colonnes
![100% center](images/TSV.png)

---
## Ouverture

Fermer la fenêtre d'accueil et aller dans le `Data Laboratory`

![100% center](images/ouverture.png)

---
## Nouveau projet

![100% center](images/nouveau_projet.png)

---
## Importer une feuille de tableur

![100% center](images/import_1.png)

---
## Choisir la feuille des arêtes

![100% center](images/import_2.png)

---
## Définir les paramètres d'import

Normalement les paramètres sont pré-remplis, mais on peut choisir si nous avons un `tsv` ou un `csv`, les nœuds ou les arêtes…
![100% center](images/edges.png)

---
## Définir les paramètres d'import II

Normalement les paramètres sont une nouvelle fois pré-remplis (on se rappelle ici que nous avions utilisé des en-tête…)
![100% center](images/edges_2.png)

---
## Finalisation de l'import

On n'oublie pas de cocher la case `Append to existing workspace`, car on veut ouvrir plusieurs feuilles dans le même espace de travail. Précisez que le graphe n'est pas dirigé (dans notre cas).

![100% center](images/edges_3.png)

---
## Finalisation de l'import II

Il existe un bouton `More options…`. Vous pouvez notament y gérer la question des liens multiples (transformer plusieurs fois le même lien en un poids en faisant la somme, par exemple).

![100% center](images/edges_4.png)

---
## Observation du résultat
Et voilà! Normalement il n'y a rien si on clique sur `nodes` sauf la liste des `IDs` utilisés pour les arêtes. Importons donc les nœuds!
![100% center](images/edges_5.png)

---
## Observation du résultat

Si vous ne voyez pas apparaître automatiquement les données, affichez-les
![100% center](images/data_table.png)

---
## Les nœuds

On recommence la même procédure avec les nœuds. À vous de jouer!

---
## Observation du résultat

![100% center](images/nodes.png)

---
## Naviguer dans Gephi
* `Overview` permet de créer le graphe
* `Data Laboratory` permet de gérer les données
* `Preview` permet de finaliser l'image du graphe produite

![100% center](images/nav.png)

---
## `Overview`

Ici nous allons pouvoir manipuler le graphe: choisir le layout, faire des calculs de centralité, _etc._

![100% center](images/overview.png)

---
## `Layout`

Choisissons un layout au hasard, pour voir ce que ça donne. Par exemple `Force Atlas 2`. On clique sur `Run`, on attend que le graphe se stabilise, puis sur `Stop`.

![100% center](images/force_atlas.png)

---
## `Layout` II

Rappel: on ne choisit pas les _layouts_ au hasard: on le fait en fonction du type de données, et des options proposées. _Force Atlas_ offre certaines fonctionnalités utile, comme _no overlap_ ("Empêcher le recouvrement") qui permet d'éviter que deux nœuds se chevauchent, ce qui peut être un problème pour la production du rendu final – pensez à le cocher dans les options!
 
---
## `Layout` III

Si le résultat est illisible, on peut "l'agrandir" avec le layout `expansion`. Répéter l'opération autant de fois que nécessaire.
![100% center](images/expansion.png)

---
## `Layout` IV

Le même graphe sans avec l'option _no overlap_
![100% center](images/expansion_2.png)

---
## `Layout` IV

Explorez les différents layouts, les différentes options

---
## Coloriage

Il est possible de customiser son graphe simplement. On se rappelle que, dans nos données, nous avons un `Type` pour les nœuds: colorions ces derniers en fonction du type dans `Appearance`.

![100% center](images/Apparence.png)

---
## Coloriage II
Comme les arêtes ont un poids, on peut ajuster la couleurs des liens en fonction du poids. Retournez dans `Appearance`, choisissez `Edges`>`Ranking`>`Weight`et cliquez sur `Apply`.
![100% center](images/Apparence_2.png)

---
## Coloriage III
On se rappelle aussi que les nœuds représentent des personnes, qui ont un nom. Affichons-les! Cliquez sur l'icone en bas à droite du graphe, choisissez `Labels`, cliquez sur `Nodes`, choisissez la police et la taille

![100% center](images/labels.png)

---
## `Statistics`

Les différentes indicateurs (densité, centralité…) sont produits simplement dans le panneau `Statistics`.

![100% center](images/centrality.png)

---
## `Statistics` II

Le résultat est ajouté dans le `Data laboratory`. Il en ira de même pour chaque calcul effetué.
![100% center](images/centrality_2.png)

---
## Coloriage IV
On peut récupérer les valeurs produites pour les afficher. Retournez dans `Appearance`, cliquez sur `Edges` puis l'icone `Size`, et choisissez `Ranking`>`Degree` et cliquez sur `Apply`.

![100% center](images/Apparence_3.png)

---
## `Preview`

Allez dans l'onglet `Preview`, et cliquez sur `Refresh` (il faudra cliquer sur ce bouton après chaque manipulation).

![100% center](images/Preview.png)

---
## `Preview` II

Finalisez votre publication en ajoutant toutes les informations nécessaires: nom des labels, _etc._
![100% center](images/Preview_2.png)

---
## Export

Vous pouvez exporter/sauvegarder votre document en différents formats: 
* L'image en JPG, PDF ou SVG (recommandé pour l'ouvrir dans _Inkscape_ ou _Illustrator_)
* Les données en CSV, TSV, GEFX, GML…

---
# À vous de jouer
---

Recommencez l'exercice, mais avec un graphe de très grande taille, surtout pour voir l'impact des différents algorithmes de tracé de graphe sur la spatialisation du résultat. Nous vous invitons à importer et visualiser les données dans le dossier `Data/Maxi` (que nous reprenons à Martin Grandjean, dont [le site](http://www.martingrandjean.ch/) et les travaux vous seront d'une grand utilité si vous vous intéressez aux réseaux).