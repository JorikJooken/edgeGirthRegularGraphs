# Exhaustive generation of edge-girth-regular graphs

This repository contains code and data related to the paper "Exhaustive generation of edge-girth-regular graphs". All code can be found in the directory "Code", whereas all data can be found in the directory "Data".

For integers $v$, $k$, $g$ and $\lambda$ an $egr(v,k,g,\lambda)$ graph is a $k$-regular graph with girth $g$ on $v$ vertices such that every edge is contained in exactly $\lambda$ cycles of length $g$.

Below, we briefly describe the different programs and data.

## DATA
The files "allFoundEdgeGirthRegularGraphsUntilOrder250.g6" and "allFoundEdgeGirthRegularGraphsMoreThan250Vertices.g6" contain the edge-girth-regular graphs in graph6 format that were found in the paper (spread over two files, depending on the order of the graph). The files "commentsUntilOrder250.txt" and "commentsMoreThan250Vertices.txt" correspond to these two files and indicate for each graph the parameters $v$, $k$, $g$ and $\lambda$. Finally, the file "someSmallEdgeGirthRegularGraphs.g6" contains a number of small edge-girth-regular graphs that we will use later to illustrate the code.

## CODE

This folder contains multiple files containing code for the exhaustive generation of edge-girth-regular graphs. There are also several files containing helper functions (e.g. to support reading graphs in graph6 format, efficiently representing sets as bitsets and so on). We will only briefly discuss the code that is directly related to edge-girth-regular graphs.

All code for generating edge-girth-regular graphs supports graphs that have at most 64 vertices. The code in the folder "veryLargeGraphs" can handle arbitrary large graphs (as large as your RAM is able to handle).

### generateRGLambdaGraphs.c, generateRGLambdaGraphsSmarterHorizontalEdges.c, generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdges.c and generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdges.c

These programs are different implementations of an algorithm that can be used to generate all connected $egr(v,k,g,\lambda)$ graphs for fixed parameters $v$, $k$, $g$ and $\lambda$.

The programs can be compiled by executing the makefile:
```bash
make
```

These programs expect the four parameters $v$, $k$, $g$ and $\lambda$ as input and will output a list of all $egr(v,k,g,\lambda)$ graphs (one graph in graph6 format per line). For example, executing the following command:

```bash
./generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdgesExecutable 10 3 5 4
```
 will output a list of all $egr(10,3,5,4)$ graphs (the Petersen graph is in fact the only such graph):

```bash
Computation started for v, k, g and lambda: 10 3 5 4
IsP@PGXD_
Computation finished for v, k, g and lambda: 10 3 5 4
```

The other programs can be invoked by changing the name of the executable. For example, invoking the command:

```bash
./generateRGLambdaGraphsExecutable 24 3 6 2
```

will produce in a few seconds an exhaustive list of all $egr(24,3,6,2)$ graphs (there are two such graphs):
```bash
Computation started for v, k, g and lambda: 24 3 6 2
WsP@@?OC?S@?@C@??O?@O?X?@???I???_?Ac??WO?_A???p
WsP@@?OC?S@?@G@??O??O?O?@O??GO?IG?Ag??W?@?c?AAA
Computation finished for v, k, g and lambda: 24 3 6 2
```

The different programs can have different speeds, depending on the precise values of $v$, $k$, $g$ and $\lambda$. For large orders, we advice you to first empirically check which program is the fastest one for smaller orders and then use this program for the large order as well.

### veryLargeGraphs/calcLambdaRegular.cpp

This program can be compiled by executing the following command:
```bash
g++ -g -std=c++11 -O3 calcLambdaRegular.cpp -o calcLambdaRegularExecutable
```

This program expects as input a list of connected regular graphs in graph6 format (one graph per line). It will output for each graph the parameters $v$, $k$, $g$ and $\lambda$ (where $\lambda$ will be indicated as "-1" if the graph is not edge-girth-regular). For example, executing the following command:

```bash
./calcLambdaRegularExecutable < ../../Data/someSmallEdgeGirthRegularGraphs.g6
```

will produce the following output:
 ```bash
K~~~vnnv|~n~
12 10 3 8
K~~~~~~~~~~~
12 11 3 10
LoCOOGA?GAC@OC
13 2 13 1
Ls`?XGRQR@B`Kc
13 4 4 2
```

This indicates that for example the graph 

```bash
K~~~vnnv|~n~
```

is a 12-vertex graph with girth 3 in which every vertex has degree 10 and each edge is contained in 8 pairwise distinct cycles of length 3 (i.e. an $egr(12,10,3,8)$ graph). Another example is the graph:
```bash
Ls`?XGRQR@B`Kc
```
This is an $egr(13,4,4,2)$ graph.
