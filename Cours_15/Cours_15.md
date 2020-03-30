Cours DH 

# Introduction à l'analyse de réseau

Simon Gabay
Neuchâtel, Lundi 30 mars 2020

---
# Introduction
---

![20% center](images/solutio_problematis.jpg)

---

## Les sept ponts de Königsberg

* Leonhard Euler (1707-1783), mathématicien et physicien suisse
* «Solutio problematis ad geometriam situs pertinentis», _Mémoires de l'Académie des sciences de Berlin_, 1735
* Est-ce qu'il existe une promenade dans Königsberg permettant, peu importe le point de départ, de revenir à son point de départ en prenant tous les pontsune seule fois?
* Euler l'origine de la théorie des graphes parce qu'il fut le premier à proposer un traitement mathématique de la question, suivi par Alexandre-Théophile Vandermonde.

---

![46%](images/Konigsberg2.png) ![58%](images/Konigsberg1.jpg)
![25%](images/konigsberg3.png) ![17%](images/konigsberg4.png)

Source: [wikipedia](https://commons.wikimedia.org/wiki/File:Solutio_problematis_ad_geometriam_situs_pertinentis,_Fig._1.png), [wikipedia](https://commons.wikimedia.org/wiki/File:Image-Koenigsberg,_Map_by_Merian-Erben_1652.jpg), [wikipedia](), [wikipedia](https://commons.wikimedia.org/wiki/File:K%C3%B6nigsberg_graph.svg)

---
## The Rise of the Medici

>to understand state formation one must penetrate beneath the veneer of formal institutions, groups, and goals down to the relational substrata of peoples' actual lives

John F. Padgett et Christopher K. Ansell, Robust Action and the Rise of the Medici, _Amercian Journal of Sociology_, 98(6), 1993

Tentative de représentation graphique des réseaux de sociabilité dans la Florence du XVème s.

---

![13% center](images/padgettAnsell1993_Medici.png)


---
## Théorie des graphes

* Comment représenter des relations complexes?
* Le graphe est un modèle abstrait de dessin de réseaux reliant des objets
* C'est aussi une représentation mathématique. Ainsi, dans sa version la plus simple (graphe simples non orienté), un graphe est un couple _G = (V, E)_ où
	* _V_ est un ensemble de sommets
	* _E _ un ensemble d'arêtes, sachant que _E ⊆ {{x, y} | (x, y) ∈ V2}_ c'est-à-dire que E inclus au sens large l'arête (ou paire de sommets) {x, y}_ tel que _x, y_ appartiennent à V au carré.

Nous reviendrons à cete question mathématiques.

---
## Définitions

* Un _graphe_ est une somme de points et de lignes
* Un point dans le graphe est appelé _nœud_ (_node_)
* Une ligne dans le graphe est appelée _arête_ (_edge_)
* Un _réseau_ est un graphe avec des attributs

---
![35 % center](images/nodes_edges.png)

---
## Les types de réseaux
Un réseau peut être
* non-orienté (_undirected graph_). . .
* . . . orienté (_directed graph_). . .
* . . . signé (_signed graph_). . .
* . . . ou valué (_valued graph_)

---
## Non-orienté (_undirected graph_)
![35% center](images/undirected_graph.png)

---
## Orienté (_directed graph_)
![35% center](images/directed_graph.png)

---
## Valué (_weighted_ ou _valued graph_)
![35% center](images/valued_graph.png)

---
## Valué (_weighted_ ou _valued graph_)
![35% center](images/valued_graph_2.png)

---
## Les Cliques

Les réseaux forment des _cliques_ (_clusters_) ou _communautés_. Ces clusters peuvent s’organiser selon différents types.

---
## Les types de réseaux
* Cercle (_ring_)
* Filet (de poisson) (_mesh_)
* Étoile (_star_)
* Complet (_fully connected_)
* Ligne (_line_)
* Arbre (_tree_)
* Vide (sans lien)
* Bus (_bus_)

---
![40% center](images/topology_network.png)

---
# Construction du réseau

---
## Construction

---
Un graphe peut se présenter sous trois formes
* Le graphe lui-même
* Une matrice
* Une liste de nœuds et d’arêtes
---

![40% center](images/graph_matrix.png)

---

![65% center](images/graph_list.png)

---
## Les modèles de réseaux

* _Random Network_ (RN)
* _Small-World Network_ (SWM)
* _Scale-Free Network_ (SFN), ou "sans échelle"

---

![50% center](images/Building-networks.png)

Source [Xu, Li, Liu 2014](https://www.researchgate.net/figure/Process-of-building-random-network-small-world-network-and-scale-free-network_fig5_263324035)

---
## _Small-World Network_ (SWM)
 Distribution gaussienne

![100% center](images/Building-networks_SW.png)

Source [Xu, Li, Liu 2014](https://www.researchgate.net/figure/Process-of-building-random-network-small-world-network-and-scale-free-network_fig5_263324035)

---
## _Scale-Free Network_ (SFN)

Loi de puissance

![100% center](images/Building-networks_SA.png)

Source [Xu, Li, Liu 2014](https://www.researchgate.net/figure/Process-of-building-random-network-small-world-network-and-scale-free-network_fig5_263324035)

---
## Mise en page

On va parler de _Force-based layout_ ou de _Force-directed graph drawing_

L'objctif est de positionner les nœuds d'un graphe pour faciliter sa visualisation en utilisant un système de force appliqués entre les nœuds et les arcs. 

---

Pour cela, on va utiliser un algorythme qui va
1. Repousser les nœuds entre eux, comme des aimants, les plus éloignés se repoussant le moins

![100% center](images/layout_repulsion.png)

Source [Rémi Damlencour](http://www-igm.univ-mlv.fr/~dr/XPOSE2012/visualisation_de_graphes/algorithmes.html)

2. Les liens fonctionnent comme des ressorts

![80% center](images/layout_ressort.png)

Source [Rémi Damlencour](http://www-igm.univ-mlv.fr/~dr/XPOSE2012/visualisation_de_graphes/algorithmes.html)

---
## Les algorythmes

* Fruchterman Reingold, le plus ancien, presque obsolète
* Yifan Hu, pour une modélisation rapide de petits réseaux (max 100 000 de nœuds)
* Force Atlas 2, pour analyse de complémentarités et les grands réseaux (1 000 000 de nœuds)
* OpenOrd, pour la distinction de clusters

---
# Analyse

---
Analyser le réseau
* Robustesse (_robustness_): capaciter du graphe à rester identique malgré des perturbations (enlever un nœud)
* Centralité (_centrality_) : capturer la notion d’importance dans un graphe, en identifiant les sommets les plus significatifs
* Densité (_density_): la proportion de liens dans un réseau relativement au total de liens possibles.

---

![80% center](images/centrality_2.jpg)

---
## Centralité
* Centralité de degré: Nombre de connexions du nœud
(_Degree_)
* Centralité de proximité: Distance moyenne du nœud à tous
les autres nœuds (_Closeness_)
* Centralité d’intermédiarité: Nombre de fois que le nœud se trouve sur le plus court chemin entre deux autres nœuds (_Betweeness_)
* Centralité de vecteurs propres Score d’autorité attribué à un nœuds en fonction du score de ses voisins. (_Eigenvector_) C’est l’algorythme de google.

---

![20% center](images/centrality.png)
