## Choix d'une librairie

*python* propose plusieurs librairies permettant de gérer des graphes de manière pratiquement identiques. Parmi les plus connues, nous pouvons citer notamment [igraph]('https://igraph.org/') et [networkx]('https://networkx.github.io/') qui proposent l'ensemble des fonctionnalités de base pour travailler avec des données organisées sous forme de graphe.

Dans ce cours, nous allons cependant utiliser la librairie [Tulip](https://tulip.labri.fr/). Cette dernière va nous apporter un ensemble d'algorithmes et d'outils qui vont nous faciliter la tâche et nous épargner de réimplémenter des solutions n'existant dans aucune des deux autres librairies.

En plus d'être utilisable avec *python*, Tulip est également disponible sous la forme d'une application complète proposant une interface graphique. Nous verrons comment utiliser cette interface au fur et à mesure du cours, cependant cette dernière peut parfois présenter des problèmes stabilité, pensez donc à sauvegarder régulièrement si vous souhaitez limiter l'utilisation des interfaces en ligne de commande.

## Création d'un graphe

Avant toute chose, nous importons notre librairie:

```python
from tulip import tlp
```

À partir de ce point, nous pouvons soit importer un graphe sauvegardé dans un fichier au format compréhensible par Tulip (par défaut `*.tlp`, `*.tlpz`, `*.tlpb`, `*.tlpbz`, ...):

```python
graph = tlp.loadGraph('./datasets/example.tlp')
```

Ou alors créer notre propre graphe vide:

```python
graph = tlp.newGraph()
```

Nous pouvons ensuite créer plusieurs noeuds et arêtes.

```python
n1 = graph.addNode()
n2 = graph.addNode()
n3 = graph.addNode()

e1 = graph.addEdge(n1, n2)
e2 = graph.addEdge(n1, n3)
```

Que nous pouvons finalement sauvegarder:

```python
tlp.saveGraph(graph, './datasets/example_copy.tlpbz')
```

## Interaction avec le graphe et itération

Tulip stocke certaines informations concernant le graphe de façon directe. Par exemple, nous pouvons ainsi connaître le nombre de noeuds présents dans le graphe:

```python
graph.numberOfNodes()
```

Si nous avons besoin d'informations plus spécifiques comme le degré d'un noeud précis, ou même d'identifier le noeud de départ ou d'arrivée d'une arête, il devient nécessaire d'indiquer en plus du graphe concerné, l'élément visé:

```python
graph.deg(n0)
graph.source(e1)
graph.target(e1)
```

```
2
<node 0>
<node 2>
```

Il est possible de récupérer l'ensemble des noeuds et arêtes du graphe afin d'itérer sur chacun des éléments existants. Nous pouvons par exemple utiliser les méthodes `nodes` et `edges` qui nous permettrons de parcourir l'ensemble des entités:

```python
for n in graph.nodes():
    print(n)

for e in graph.edges():
    print(e.id)
```

```
<node 0>
<node 1>
<node 2>

0
1
```

## À vous de jouer

C'est maintenant votre tour de vérifier vos acquis en réalisant les [exercices suivants](./2_exercice.md).
