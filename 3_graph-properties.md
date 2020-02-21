## Utilisation des proprietés

Tulip déclare chaque propriété sur l'ensemble de ses éléments. Chaque noeud et arête ont donc possiblement accès à chaque propriété.

### Types de propriétés

Afin de spécifier les traitements que nous souhaitons réaliser, chaque propriété peut être définie selon un certain type. En plus des types habituels tels que *string* et *integer*, Tulip compte quelques types particuliers:

* Integer
* Double
* Numeric (super type)
* Boolean
* String
* Color (tuple)
* Layout (tuple)
* Size (tuple)

Le **super type** *numeric* recouvre les types *integer* et *double*, nous offrant un ensemble d'opérations spécifique (tel que *max*, *min*, etc.).
De plus chacun de ces types peut être généralisé sous la forme de vecteurs, nous permettant ainsi de stocker pour chaque élément une série de coordonnées, couleurs, ou de Booléan par exemple.

### Accès aux propriétés

De manière similaire aux accés réalisés dans *python* pour les accès aux dictionnaires, Tulip utilise la syntaxe suivante:

```python
graph = tlp.newGraph()
n = graph.addNode()
graph['mesure'][n] = 30
```

Une fois initialisé sur un des éléments, la propriétés va initialiser la valeur par défaut à l'ensemble des autres éléments.

```python
n_bis = graph.addNode()
print(graph['mesure'][n_bis])
```

## Propriétés visuelles

Les propriétés contenant le mot-clés *view* sont celles utilisées par Tulip pour gérer toutes les informations visuelles des graphes. Entre autres, les plus utilisées sont:

* viewColor
* viewLabel
* viewLayout
* viewMetric
* viewSelection
* viewSize

### Récupération des types

Ces différentes propriétés utilisent des types différents tels qu'implémentés par Tulip. Pour les utiliser, le plus simple est de profiter des définitions et initialisations proposées par la librairie.

* tlp.Color
* tlp.Vec3f ou tlp.Coord


## Continuons

Pas encore d'exercice pour l'instant, passons à la [suite du cours](./4_element_iteration.md)
