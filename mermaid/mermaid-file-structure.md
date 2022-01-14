# Mermaid File Structure

Today I learned that structuring your mermaid file can be very important for others understanding and for ease of manipulation and future maintenance. Here is the structure I am thinking works best for now.

```mermaid
flowchart TB

    %% List of all nodes including the type of node and any text for the node. You can also define class inheritance here.

    %% Structure of the graph including subgraphs and their nodes.

    %% List of all relationships in the graph.

    %% Class definitions for nodes and subgraphs, as well as assigning classes to subgraphs. (Nodes are handled up above with shorthand notation.)
```

This structure allows the most pertinent information to be given to the viewer of the file from the top to the bottom. They first need to know the nodes that are contained in the graph. Then as they read the file, they get an idea of the structure of the graph according to grouped nodes. Once they hit the relationship section of the code, they have a general idea of the overall nodes and node groups and can begin digging into the relationships between nodes. Then, they are ready to dive into the classes for understanding of their meaning in the context of your flowchart, which may also be one of the lesser important things about the flowchart although it does provide more meaning in the context of presenting the flowchart's ideas. 