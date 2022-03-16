# FASE3
```
Data Structuresand Algorithms.
Degree in Computer Engineering
Double Degree in Computer Engineering
and Business Administration
Degree in Applied Mathematics and
Computing
Double Degree in Data Science and
Engineering
```
```
University Carlos III of Madrid
```
```
Labcase. COURSE 2020- 2021
```
Phase 3 **–** Cvid-19 Vaccination Campaign. Graphs

Every day, the Health Department of the Community of Madrid receives a Map with
the different health centers where vaccines must be delivered. The objective of this
phase is to develop a data structure that allows to represent the distribution map. Such
a map will be made up of the health centers. To simplify the practical case, in this
phase, we are only going to store the name of each health center. The map, in addition
to the health centers, also represents the possible connections or paths between the
health centers. Thus, if two health centers are directly connected, the map will contain
the distance in km between both health centers. On the map, there are health centers
which are not directly connected, so it will be necessary to go through one or more
intermediate health centers.

In this phase, we already provide you with the implementation of the Map data
structure, with the following functionality:

```
● Function addHealthCenter (), that allows adding a new health center to the
map.
```

```
● Function addConection (), that receives two health centers and their distance
in km. The function creates a connection between both centers.
```
```
● Function removeConnection (), that receives two health centers, and removes
their connection.
```
```
● Function __str __ (), that shows all health centers and their direct connections
to other centers and their distances.
```
```
● Function areConnected (), that checks if two health centers are directly
connected. If they are connected, it returns the distance, otherwise it returns 0.
```
```
● Function createPath (), that allows visiting all health centers. The function
returns a Python list containing the health centers in the order of visit applying
the depth first search algorithm. As the starting center, we consider the first
health center that was added to the map in its initialization.
```
```
● Function minimumPath (), that receives two health centers, start and end, and
that obtains the minimum path from start to end (applying Dijkstra's algorithm).
The function returns a Python list with the delivery points that make up such
minimum path (including start and end), and it also returns the distance
between start and end.
```
The objective of this phase is to implement other versions of the minimumPath method
but, instead of applying Dijkstra's path, applying other algorithms to obtain the
minimum path (shortest distance in km) between two health centres. The algorithms
to be applied are:

- The Bellman-Ford algorithm
- The Floyd-Warshall algorithm

The Bellman-Ford algorithm calculates and returns the minimum path with its
associated cost. If it finds a negative connection, it returns false. As in Dijkstra's
algorithm, an array, d, is used to store the distances from a source vertex, s, to each
of the vertices of the graph. Thus, for each vertex v in the graph, d[v] stores the cost


of the minimum path from the source vertex s to v. An array, p, is also used to store
the vertices previous to each vertex on the path from the source. The pseudocode for
this algorithm is shown below:

```
Bellman-Ford (G,start)
```
```
Initialize:
For each vertex v
set d[v] = infinite
p[v] = null
p[start] = 0
```
```
For each vertex v
For each connection (u,v)
If d[v] > d[u] + w(u,v) then
d[v] = d[u] + w(u,v)
p(v) = u
```
For each connection (u,v) check
If d[v] > d[u] + w(u,v) then
return FALSE ‘the algorithm does not converge
return True

The Floyd-Warshall algorithm allows finding the minimum path between all possible
pairs of vertices of a graph. It uses the adjacency matrix (with the weights of each
connection) and a matrix P to store the minimum paths. The pseudocode of this
algorithm is shown below:

```
Floyd-Warshall (G)
Initialize
Let D be the adjacency matrix (distances between vertices)
Let P be a matrix to store the minimum paths
If i=j or Dij= infinite then Pi,j = null
otherwise Pi,j=i
```

```
For k = 0 To len(V)- 1
```
For i = 0 To len(V)- 1

```
For j = 0 To len(V)- 1
```
Di,j = min(Di,j , Di,k + Dk,j )

If min = Di,k + Dk,j then

Pi,j = Pk,j

Together with the statement of this phase, the following files are given to the student:

```
1.The file phase3.py which already contains the implementation of the Map
class and which you have to complete by adding the methods
minimumPathBF (based on the implementation of the Bellman-Ford
algorithm) and minimumPathsFM (based on the Floyd-Warshall algorithm) to
obtain the minimum path between the health centres. The file already contains
part of the code, to help you get started.
```
```
2.The file unittest-phase3.py which already contains the tests needed to
evaluate the methods that are already implemented in the file phase3.py. You
must create the tests needed to validate the new minimumPathBF and
minimumPathsFM methods. You should include as many tests as necessary
to cover all possible cases to make your solution as robust as possible.
```
Note: In this phase, a health center does not include information about its patients.

Algorithm Analysis:
What is the temporal complexity of each of the functions requested in the statement?
Justify the best and worst case, indicating its complexity. You must add your answer
in a comment of the function.


Rules:

1. At this stage, the following Python structures are allowed: lists and dictionaries.
2. Please upload only the file phase3.py to the task "Delivery Phase 3",
    created in the global classroom of your small group. Please do not rename
    the file or upload a zip. In the phase3.py file, include a comment with the
    name, NIA and small group of each team member. Only one member of the
    team should upload the solution proposed by the team. Deadline for delivery is
    May 12, 11:55 p.m.
3. Defence: During the face-to-face class on Thursday, May 13. The defence
    of the Lab case is an oral exam. Attendance is mandatory. If a student does not
    attend, his/her grade in the Lab case will be NP. During this defence, the
    teacher will ask each member of the team a series of questions that must be
    answered individually. Each team member shall be able to discuss any of the
    decisions made during the design or implementation of any of the
    functionalities described in the case study. The final grade of the Lab case
    will be conditioned by the grade obtained in the defence. If a student is not
    able to discuss and defend certain decisions, he/she will not be qualified with
    respect to them, even if they are correctly implemented.
4. It is recommended to follow the recommendations described in Zen of Python
    (https://www.python.org/dev/peps/pep-0020/) and the style guide
    (https://www.python.org/dev/ peps / pep-0008 /) published on the official
    Python website.


