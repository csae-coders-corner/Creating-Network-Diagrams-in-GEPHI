
![CC Graphics 2024_NeworkDiagrams](https://github.com/csae-coders-corner/Creating-Network-Diagrams-in-GEPHI/assets/148211163/c53c1645-aed2-4972-8692-7c240f941680)

# Creating-Network-Diagrams-in-GEPHI
Network diagrams can be helpful at the beginning of a project to understand the data, and at the end of a project to bring a result to life. Gephi is a useful program for creating, manipulating and rendering high quality graphs. It is open-source and a bit temperamental, relative to say Stata or Matlab, but more than worth the odd crash (just make sure to keep saving). It is free to download from here- https://gephi.org/users/download/. 

Graphs are made of nodes and edges, so first we need to import them. We need a file (.csv or similar) of edges, with the structure:

|Source	|Target|Weight|
|-------|------|------|
|1      |2     |x     |
|1      |3     |y     |
|2      |1     |z     |

where Source and Target are nodes, and weight refers to the strength of the connection between them. Then we need a file of Nodes with their characteristics:

|Node	|Characteristic 1 |Characteristic 2|	
|-------|-----------------|----------------|
|1	|a	          |x	           |
|1	|b	          |y	           |
|2	|c	          |z	           |


Then start a new Gephi project and import these using the wizards, e.g.:

![GEPHI 1](https://github.com/csae-coders-corner/Creating-Network-Diagrams-in-GEPHI/assets/148211163/e5f5dc25-4a43-44e0-bf45-553d76dde4cb)

![GEPHI 2 jpg](https://github.com/csae-coders-corner/Creating-Network-Diagrams-in-GEPHI/assets/148211163/3e73e437-e20a-49ce-874d-68e72b14c36e)

This produces an uninformative, and somewhat sinister, initial depiction:

![GEPHI 3](https://github.com/csae-coders-corner/Creating-Network-Diagrams-in-GEPHI/assets/148211163/f374fda5-7c04-46c5-a09c-e220acb90560)

We can now play around with all Gephi’s great features to reach a representation that is useful. This example uses India’s input-output table for 1998, restricted to primary commodities and manufacturing. Firstly, we only care about edges which represent a genuine supply relationship – i.e. where product A is an input to product B, or vice versa. In the Data Laboratory tab, I replace the default values of the field ‘Weight’ with those of the field ‘alpha1’, i.e. with the input shares computed from the input-output table.

![GEPHI 4](https://github.com/csae-coders-corner/Creating-Network-Diagrams-in-GEPHI/assets/148211163/c08b80b1-925f-460f-bf18-e707f9b9f00a)

Returning to the Overview tab, I can then filter on Edge Weight to view only those edges with a weight greater than zero, and on the left I can run the Fruchterman-Reingold algorithm to spread the nodes out in a clearer way:

![GEPHI 5](https://github.com/csae-coders-corner/Creating-Network-Diagrams-in-GEPHI/assets/148211163/65ced165-4639-42c2-9394-658f61a76dfa)

At this point, one can then play around with Gephi’s various features, which are generally quite intuitive. For instance, I might size the nodes by out-degree (i.e. the number of downstream goods that they are inputs for) to get a sense of their importance in the network. 

Say one is interested in understanding the impact of Chinese competition on the Indian production network. When importing the nodes table, I include the characteristic ‘change between 1999 and 2013 in the share of Chinese imports in total Indian imports of the good’. I can then colour nodes darker red the greater this increase in import competition, and add labels for the 15% of products experiencing the greatest increase. Finally, switching to Gephi’s Preview tab, I can export the resulting graph as a high-resolution pdf:

![GEPHI 6](https://github.com/csae-coders-corner/Creating-Network-Diagrams-in-GEPHI/assets/148211163/9e27cc2f-b642-4f9e-8a8c-ed39605db5ed)

We can see that the main Indian industries affected by Chinese import competition were neither primary commodities (the large nodes at the centre, which supply many other industries), nor advanced manufactures (generally small and at the edge, as they are final goods). Instead the most affected industries were intermediate manufactures, with particular clusters in textiles, electronics and chemicals.

Gephi also has the “filters” feature which allows users to visualise specific kinds of nodes and edges i.e. a subgraph of the original graph. For example, the “Attributes” filter can be used to only view links among nodes that exhibit a certain characteristic, the “Edges” filter to only view edges with a certain weight , and the “Topology” filter to view the “ego network” of any pre-specified node i.e. their immediate links, the links of their links, and so on.  

**Alex Copestake, DPhil Candidate in Economics, Oxford
12 October 2020**
