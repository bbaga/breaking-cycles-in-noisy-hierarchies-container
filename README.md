# breaking-cycles-in-noisy-hierarchies-container

## Bulding the container
```bash
docker-compose build
```

## Running the scripts
Place the graph data in a tsv file (i.e: graph.tsv) and move the file into the `mount` directory in this repository, then run a command like below:
```bash
docker-compose run run-env python remove_cycle_edges_by_hierarchy.py -g /tmp/mount/graph.tsv -s ensembling
```

### Example graph.tsv
```text
1 2
1 5
2 3
3 4
4 5
5 6
5 7
6 8
3 1
8 5
8 9
9 6
```

### Results
The result files will be placed into the `mount` folder