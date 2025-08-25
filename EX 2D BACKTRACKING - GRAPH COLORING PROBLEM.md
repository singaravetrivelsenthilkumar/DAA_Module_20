# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1.Initialize a graph with V vertices and a 2D adjacency matrix.

2.For each vertex, check if it's safe to assign a color using isSafe function (no adjacent vertex has the same color).

3.Recursively try assigning colors to vertices, starting from the first vertex.

4.If all vertices are successfully colored, return True and print the assigned colors.

5.If no valid coloring exists, backtrack and print "No solution exists".

## Program:
```py
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: SRIRAJ G
Register Number:  212222040161
*/
class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.Graph=[[0 for column in range(vertices)]for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.V):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColourUtil(self,m,colour,v):
        if v==self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColourUtil(m,colour,v+1):
                    return True
                colour[v]=c
        return False
    def graphColouring(self,m):
        colour=[0]*self.V
        if not self.graphColourUtil(m,colour,0):
            print("No solution Exist")
            return False
        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c,end=' ')
        print()
        return True
```

## Output:
![image](https://github.com/user-attachments/assets/732da3cf-0529-4fe4-80ec-3de81f67536d)



## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
