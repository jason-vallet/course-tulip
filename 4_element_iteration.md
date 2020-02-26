## Parcours des éléments du graphe

Le parcours d'éléments dans le graphe peut se faire plusieurs manière. Simplement, nous pouvons passer par tous les éléments les uns après les autres.

```python
i = 0
for n in graph.nodes():
    graph['viewMetric'][n] = i
    i += 1
```

Si nous le souhaitons, nous pouvons également réaliser notre parcours à partir d'un élément de départ et n'accéder qu'à ses voisins (c'est à dire, les éléments auxquels il est connecté).

```python
n = graph.getOneNode()
for n_alt in graph.getInOutNodes(n):
    graph['viewColor'][n_alt] = tlp.Color(255, 0, 0)
```

Ce genre de parcours peut également être réalisé sur les arêtes elles-mêmes:

```python
n = graph.getOneNode()
for e in graph.getInEdges(n):
    graph['viewSelection'][e] = True
```

Alternativement, il est possible d'initialiser ce genre d'opérations à partir d'une arête.

```python
e = graph.getOneEdge()
i = 0
for n in graph.ends(e):
    graph['viewLayout'][n] = tlp.Coord(i, i+1, 0)
    i += 1
```

Notez qu'il est également possible d'accéder directement au noeud situé à la source de l'arête `e` avec la méthode `graph.source(e)` et au noeud destinataire de la relation avec la méthode `graph.target(e)`.


## À vous de jouer

C'est maintenant votre tour de vérifier vos acquis en réalisant les [exercices suivants](./4_exercice.md)
