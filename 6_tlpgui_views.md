## Utilisation des `views` avec python

En plus de sa librairie de base, la version python de Tulip peut aussi être utilisée pour ouvrir et manipuler des fenêtres d'interface graphique afin de visualiser directement les résultats obtenus. Pour ceci, nous devons installer la librairie `tulipgui`:

```
pip3 install tulipgui-python
```

Nous pouvons ensuite la charger dans notre environnement python en utilisant la commande suivante.

```python
from tulipgui import *
```

## Gestion des vues

Les vues ont un cycle de vie indépendant et doivent en conséquence être manipulées précautionneusement. Une vue est créée à partir de son nom, d'un graphe d'initialisation et d'une ensemble de paramètres.

```python
nodeLinkView = tlpgui.createView("Node Link Diagram view", graph, {}, False)
```

Si nous souhaitons avoir un rendu invisible, il est également possible de ne pas afficher la vue directement. Cette fonctionnalité est très appréciable lorsque nous travaillons sur de très gros jeux de données.

Nous pouvons alors interagir avec la fenêtre et faire appel à l'ensemble des fonctionnalités de celle-ci.

```python
nodeLinkView.centerView()
```

Une des fonctionnalités particulièrement intéressante si nous souhaitons réaliser des calculs et obtenir des rendus de manière différée est l'appel à l'outil de capture d'image qui pourra sauvegarder les dessins générés en quelques opérations rapides.

```python
path_pic = "image/exemple.png"
nodeLinkView.saveSnapshot(path_pic, 1000, 1000)
tlpgui.closeView(nodeLinkView)
```


## À vous de jouer

C'est maintenant votre tour de vérifier vos acquis en réalisant les [exercices suivants](./6_exercice.md).

