# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To find a path from the top-left to the bottom-right corner of a maze using backtracking, marking the path in a solution matrix.


## Algorithm
1. Initialize a solution matrix with zeros.

2. Start at the top-left corner and recursively explore possible paths.

3. Check if moving to a cell is safe (within bounds and open).

4. If reaching the bottom-right corner, mark the cell as part of the path.

5. If a path is found, print the solution matrix; otherwise, backtrack and return "Solution doesn't exist."

## Program:
```py
/*
Program to implement Rat in a Maze.
Developed by: SRIRAJ G
Register Number:  212222040161
*/
N = 4
 
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):

    if x==N-1 and y==N-1 and maze[x][y]==1:
        sol[x][y]=1
        return True
    if isSafe( maze, x, y ):
        sol[x][y]=1
        if solveMazeUtil(maze, x+1, y, sol):
            return True
        if solveMazeUtil(maze, x, y+1, sol):
            return True
        sol[x][y]=0
    return False

if __name__ == "__main__":
    
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:
![image](https://github.com/user-attachments/assets/56e8961f-50c4-489b-bf4c-d229942a98b4)



## Result:
The program prints the solution matrix if a path exists or "Solution doesn't exist" if no path is found.
