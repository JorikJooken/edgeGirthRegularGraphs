compiler=gcc
flags=-std=gnu11 -march=native
densenauty32=-DWORDSIZE=32 -DMAXN=WORDSIZE nautyW1.a
densenauty64=-DWORDSIZE=64 -DMAXN=WORDSIZE nautyL1.a
densenauty128=-DWORDSIZE=128 -DMAXN=WORDSIZE nautyL1.a

all: genConReg genRG genRGPruning genRGLambda genRGLambdaOrbits genBipartiteRGLambda genRGLambdaSmarterHorizontalEdges genRGLambdaSmarterHorizontalEdgesAlsoMonitorAllEdges genRGLambdaSmarterHorizontalEdgesAlsoMonitorSomeEdges calcLamReg calcLamVertTran

calcLamReg: calcLambdaRegular.c bitset.h read_graph/readGraph6.c
	$(compiler) -o calcLambdaRegularExecutable calcLambdaRegular.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

calcLamVertTran: calcLambdaVertTran.c bitset.h read_graph/readGraph6.c
	$(compiler) -o calcLambdaVertTranExecutable calcLambdaVertTran.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genConReg: generateConnectedRegularGraphs.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateConnectedRegularGraphsExecutable generateConnectedRegularGraphs.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRG: generateRGGraphs.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGGraphsExecutable generateRGGraphs.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambda: generateRGLambdaGraphs.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsExecutable generateRGLambdaGraphs.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambdaOrbits: generateRGLambdaGraphsOrbits.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsOrbitsExecutable generateRGLambdaGraphsOrbits.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambdaSmarterHorizontalEdges: generateRGLambdaGraphsSmarterHorizontalEdges.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsSmarterHorizontalEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdges.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambdaSmarterHorizontalEdgesAlsoMonitorAllEdges: generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdges.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdges.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGLambdaSmarterHorizontalEdgesAlsoMonitorSomeEdges: generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdges.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdges.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genBipartiteRGLambda: generateBipartiteRGLambdaGraphs.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateBipartiteRGLambdaGraphsExecutable generateBipartiteRGLambdaGraphs.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

genRGPruning: generateRGGraphsPruningRuleAdded.c bitset.h read_graph/readGraph6.c
	$(compiler) -o generateRGGraphsPruningRuleAddedExecutable generateRGGraphsPruningRuleAdded.c read_graph/readGraph6.c $(densenauty64) $(flags) -O4

.PHONY: clean
clean:
	rm -f generateConnectedRegularGraphsExecutable generateRGGraphsExecutable generateRGGraphsPruningRuleAddedExecutable generateRGLambdaGraphsExecutable generateBipartiteRGLambdaGraphsExecutable generateRGLambdaGraphsSmarterHorizontalEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorAllEdgesExecutable generateRGLambdaGraphsSmarterHorizontalEdgesAlsoMonitorSomeEdgesExecutable calcLambdaRegularExecutable calcLambdaVertTranExecutable generateRGLambdaGraphsOrbitsExecutable
