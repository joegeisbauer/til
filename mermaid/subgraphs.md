# Subgraphs

Subgraphs are a very handy tool in mermaid flowcharts diagram. They give you some control over how parts of the graph appear and the order in which things are connected. The implementation is for subgraphs is rather simple as you can see below:

```mermaid
flowchart LR
    sg1-->sg2
    subgraph sg1 [Graph 1]
        direction TB
        sg1-top[Graph 1 Top]-->sg1-bottom[Graph 1 Bottom]
    end
    subgraph sg2 [Graph 2]
        direction TB
        sg2-top[Graph 2 Top]-->sg2-bottom[Graph 2 Bottom]
    end
```

The above code produces the following flowchart diagram.

![FlowChart Diagram](subgraph_example.jpg)

Note the `LR` next to flowchart represents the left-to-right flow of the chart. Similarly, you can set the flow of the subgraph using the `direction` command, which we set to `TB`, or top-to-bottom, here.