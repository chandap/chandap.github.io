---
layout: post
title: Bipartite Check 
---

```python
import numpy as np
import io

''' input_graph.txt

1,2,3,4
5,4,3
6,3,4

'''

class Node(object):
    def __init__(self,id,neigh=None):
        self.id = id
        self.neighbors = neigh
        self.color = None

def update_graph(node_id,neighbors):
    if node_id not in graph:
        node = Node(node_id,neighbors)
        graph[node_id] = node        
    else:
        node = graph[node_id]
        node.neighbors += neighbors
        
        
def build_graph(fname):
    with open(fname,'r') as fin:
        for line in fin:
            x = line.strip().split(',')
            neighbors = list(x[1:])
            node_id = x[0]
            update_graph(node_id,neighbors)
            for ne in neighbors:
                update_graph(ne,[node_id])

def print_graph():
    print('----graph------')
    for key,value in graph.items():
        print(key,'->',graph[key].neighbors)
    print('\n')
    
graph = {}

# simple depth first traversal of the graph
def DFS(source,neighbor_color):
    if source.color is None:
        #assign opposite of neighbor color to the source
        source.color = ('RED' if neighbor_color is 'BLUE' else 'BLUE') 
        neighbors = graph[source.id].neighbors
        # call DFS for each of its neighbors
        for ne in neighbors:
            node_ne = graph[ne]
            ret = DFS(node_ne,source.color)
            if ret is False: return False
        return True    
    else: 
        # source already visited and colored. 
        # If the neighbor color is same as this nodes color, 
        # they belong to same partition and have an edge, so not bipartite.        
        return (False if source.color==neighbor_color else True)
    

if __name__ == '__main__':
    build_graph('input_graph.txt')
    print_graph()
    print('Bipartite' if DFS(graph['1'],'RED') else 'Not Bipartite')
```

    ----graph------
    1 -> ['2', '3', '4']
    6 -> ['3', '4']
    3 -> ['1', '5', '6']
    5 -> ['4', '3']
    4 -> ['1', '5', '6']
    2 -> ['1']
    
    
    Bipartite
    


```python

```
