# Templated graphviz

This Repository contains an exploration to generate graphviz dot files
with a templating engine (ninja2) in order to compensate shortcomings within the dot format.

## Requirements
* jq,dot,j2 needs to be installed
  * `brew install graphviz jq`
  * `pip2.7 install j2cli`

## Usage

### Command line (local)
* `./compile` 
* `./compile json_data/nodes_1.json` 

### using the docker container

## Example

### json input
```
...
  "nodes":[
    {
      "id":"node1",
      "name": "label for node 1",
      "bgcolor":"blue"
    },
    {
      "id":"node2",
      "style":"note"
    },
...
    {
      "id":"node6"
    }
  ],
  "edges": [
    {
      "nodes":["node1","node2"]
    },
...
    {
      "nodes":["node5","node6"],
      "attributes":"color=green;constraint=false;dir=back;xlabel=\"edge label\";"
    },
    {
      "nodes":["node1","node6"],
      "style":"note"
    }
  ]
...
```

### Rendered PNG

![example.png](rendering/example.png)

