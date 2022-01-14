# Subgraph Classes

Just like we defined classes for nodes, we can also now define classes for subgraphs within our graph. This is nice for styling, but it is also nice for organizing your flowchart or graph. For example, I use subgraphs with the class definition

```mermaid
classDef subgraphNoBG fill:None,stroke:None;
```

in order to get rid of the background color and frame around subgraphs when I am just using them to get the right flow for the overall graph in mermaid. This can be very helpful and allow you to organize your graphs in a much better manner than just setting the direction and trusting mermaid to control the rest.

You then assign your class to subgraph1 and subgraph2 by the following syntax

```mermaid
class subgraph1,subgraph2 subgraphNoBG;
```