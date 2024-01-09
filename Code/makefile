compiler=gcc
flags=-std=gnu11 -march=native
densenauty32=-DWORDSIZE=32 -DMAXN=WORDSIZE nautyW1.a
densenauty64=-DWORDSIZE=64 -DMAXN=WORDSIZE nautyL1.a

all: genRGLambda genRGLambdaSmarterHorizontalEdges genRGLambdaSmarterHorizontalEdgesAlsoMonitorAllEdges genRGLambdaSmarterHorizontalEdgesAlsoMonitorSomeEdges


genRGLambda: generateRGLambdaGraphs.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsExecutable generateRGLambdaGraphs.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambdaSmarterHorizontalEdges: generateRGLambdaGraphsSmarterHorizontalEdges.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsSmarterHorizontalEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdges.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambdaSmarterHorizontalEdgesAlsoMonitorAllEdges: generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdges.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdges.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambdaSmarterHorizontalEdgesAlsoMonitorSomeEdges: generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdges.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdges.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

.PHONY: clean
clean:
	rm -f generateRGLambdaGraphsExecutable generateRGLambdaGraphsSmarterHorizontalEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdgesExecutable
