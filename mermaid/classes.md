# Classes

Sometimes the common colors and node designs just won't do for the pizzazz your mermaid diagrams need to get the point across. However, you can define your own classes via CSS notation inside a diagram as follows:

```mermaid
flowchart LR
    id1["First Node"]:::testClass-->id2["Second Node"]:::testClass
    classDef testClass fill:#bdc3c7,stroke:#f39c12,stroke-width:2px,color:#3498db;
```

Note the class is added to each node via the inheritance notation `:::testClass`. This code produces the nodes in the following diagram:

![Diagram with different node classes](class-mermaid.jpg)