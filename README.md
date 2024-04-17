# Creating-Network-Diagrams-in-GEPHI
Network diagrams can be helpful at the beginning of a project to understand the data, and at the end of a project to bring a result to life. Gephi is a useful program for creating, manipulating and rendering high quality graphs. It is open-source and a bit temperamental, relative to say Stata or Matlab, but more than worth the odd crash (just make sure to keep saving). It is free to download from here- https://gephi.org/users/download/. 

Graphs are made of nodes and edges, so first we need to import them. We need a file (.csv or similar) of edges, with the structure:

	|Source	|Target|Weight|
 |--------|
	|1|2|x|
	|1|3|y|
	|2|1|z|

where Source and Target are nodes, and weight refers to the strength of the connection between them. Then we need a file of Nodes with their characteristics:

	Node	Characteristic 1	Characteristic 2	
	1	a	x	
	1	b	y	
	2	c	z	


Then start a new Gephi project and import these using the wizards, e.g.:
