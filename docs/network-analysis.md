In this section, we'll explore network analysis as a tool for understanding relationships between people and things.

[TOC]

## What is network analysis? 

Networks are everywhere. Once you start, it's hard to stop seeing them. The internet is a network, Facebook is a network, [Kevin Bacon](https://oracleofbacon.org/) is the central node in the Hollywood network. Studying the connections between people and things is a major activity in the humanities, so "network analysis" feels like a natural method for working with humanities data. Network analysis varies by discipline, but originates from graph theory in mathematics. This is a simplification, but the idea is that one can measure significant people in a network by how many connections they have to other people and by the weight or significance of those connections. You can also learn who might serve as a bridge between social groups or whether you have a dense network of highly connected people or a more disperse group. We can visualize these networks through a network graph - points connected by lines. 


You don't necessarily have to just study people with network analysis, but it's a common approach. The specific name for this methodology is **SNA** or Social Network Analysis. SNA is used in many disciplines, with a heavy presence in the social sciences. It's important to recognize that each discipline will have its own conventions and expectations for SNA. You should tread carefully until you have a firm foundation. As Scott Weingart reminds us in "[Networks Demystified](http://www.scottbot.net/HIAL/index.html@p=6279.html):" 

> "Networks can be used on any project. Networks should be used on far fewer."

This is not to scare you! But learning about network analysis is the perfect moment to pause and remember that you are not working in a vacuum. The methods you use have a historical and modern context and you are responsible for learning that context. 

That being said, network visualizations can be a great place to start. They can help you learn more about your data or illuminate a new direction for your research agenda. Plus, they're fun. Learning the basics will help you be better judge of whether it is, in fact, a good fit for your project. 


## Nodes, edges, ties, what?
Let's take a moment to define some of the terms you'll encounter in network analysis. 

* Nodes/points/agents/vertices - All of these words refer to the points on your network graph. If you're doing social network analysis, the points are the people in your graph. 

* Edges/ties - Refers to the connections between nodes, usually represented by lines between points. Edges can be weighted (stronger or weaker edges) or directional (some relationships are mutual, some are not). The line could be drawn thin or thick based on the weight, or with an arrow to signify direction. The connection between you and your roommate might have a strong weight for example. If you follow a celebrity on Twitter, but they don't follow you back, we can imagine that as a relationship with a single direction. 

* Centrality - the more connections a node has, the more central they are to the network. You can measure centrality in different ways, such as betweenness (the shortest distance between nodes) or eigenvector (way to measure influence in a network). Think about your friends. The person who seems to know everyone might not be the same as the person who can spread information effectively, or to far off parts of the network. 

* Attributes - Information about your nodes. If your network contains people, attributes might be their age, birth dates, affiliation, occupation, etc. 

* Bimodal or multi-modal - a network in which more than one type of thing is being connected. While a unimodal network might connect people to people, a bimodal network looks at authors and their books, or people to places. Scott Weingart has more to say about [bimodal networks](http://www.scottbot.net/HIAL/index.html@p=41158.html).

## Network data 
To visualize your network, you need to set up your data is particular way. This might vary depending on the software you use, but it's a good place to start: 

An **edge list** is a two-column spreadsheet that forms the the network by listing the nodes and their connections. It's in a deceptively simple format:

|Source|Target|
|---|---|
|Kevin Bacon|John Lithgow|
|Kevin Bacon|Sarah Jessica Parker|
|Sarah Jessica Parker|Matthew Broderick|
|Matthew Broderick|Jennifer Grey|
|Jennifer Grey|Patrick Swayze|
|Patrick Swayze|Demi Moore|
|Demi Moore|Kevin Bacon|
|Jennifer Grey|Laurence Fishburne|
|Laurence Fishburne|Keanu Reeves|
|Kevin Bacon|Laurence Fishburne|

You'll notice that some names can appear more than once, and not necessarily in the same column. Each of these rows represents a single connection, in this case, a movie. Take a minute to try to draw this extremely limited 80s-90s movie network on paper. What do you expect to see? Who has the most connections? Who seems central and who seems like an outlier? How flawed is this network? Add to it if you can. 

An edge list might build the network, but we need an **attribute table** to add context to our network. An attribute table lists each node only once, then displays information about that node in subsequent columns. 

|Name|Gender|Is known for a dance scene|
|---|---|---|
|Kevin Bacon|M|Y|
|Matthew Broderick|M|Y|
|Laurence Fishburne|M|N|
|Jennifer Grey|F|Y|
|John Lithgow|M|N|
|Demi Moore|F|Y|
|Sarah Jessica Parker|F|N|
|Keanu Reeves|M|N|
|Patrick Swawyze|M|Y|

Now I can use this information to filter or slice the view of my network. I can also use it to refine my questions or my data set. It's easy for me to see that I have [more men in my network](https://6dfb.tumblr.com/post/44879380376/an-entry-of-ones-own-or-why-are-there-so-few) than women.

If you want to see this data as a visualization, try loading it into [Palladio](http://hdlab.stanford.edu/palladio-app/#/upload).

Copy and paste the following text into the white box in Palladio, then press `Load`: 

```
Source,Target,
Kevin Bacon,John Lithgow,
Kevin Bacon,Sarah Jessica Parker,
Sarah Jessica Parker,Matthew Broderick,
Matthew Broderick,Jennifer Grey,
Jennifer Grey,Patrick Swayze,
Patrick Swayze,Demi Moore,
Demi Moore,Kevin Bacon,
Jennifer Grey, Laurence Fishburne,
Laurence Fishburne, Keanu Reeves,
Kevin Bacon, Laurence Fishburne,
```
To generate a network, visit the `Graph` tab. Use the menu on the right of the screen to select the "source" column in `Source` and the "target" column in `Target`. You should see a network appear! Does it look like what you expected? 


## Tools 

* [Palladio](http://hdlab.stanford.edu/palladio/) is a data visualization tool created by Stanford's Humanities + Design Research Lab. It's a browser-based tool that accepts structured data and creates network, geospatial, and gallery visualizations. It's easy to use, but can crash under too much data. It's a great way to create first draft visualizations of your data. 

* [Gephi](https://gephi.org/) is a robust network/graph visualization tool. It runs from your computer and can accept large data sets (though you will need some patience). Gephi has a lot of options for changing the appearance of your network via filters and layout. You can also generate statistics about graph density etc. There are a number of [tutorials](https://gephi.org/users/) available.

* [Cytoscape](http://www.cytoscape.org/) was designed for the sciences, but is now being used for more general network analysis and visualization purposes. 

* [Nodegoat](https://nodegoat.net/) is a data modeling and visualization platform with options for network analysis.

* [igraph](http://igraph.org/redirect.html) is a network analysis package for use with R, Python, and C++

* [UCINET](https://sites.google.com/site/ucinetsoftware/home) is available on Windows only. It is not free software, but 90 day trials are available. [Tutorials](https://sites.google.com/site/analyzingsocialnetworks/analyses) are available on the UCINET site. Hanneman and Riddle created this [textbook](http://www.faculty.ucr.edu/~hanneman/nettext/) for use with UCINET.


## Activities

### Activity 5.1 

In order to practice using the terminology and methods of network analysis, let's design a network from scratch. Use the materials provided. 

1. [In your group, select a topic for your network](https://wlu.app.box.com/notes/871866042025). It should be approachable for all members of your group. Game of Thrones? W&L students? Sports? A novel or TV show?
2. List all the nodes in your network. Do they have types? Do they have attributes? Is this a bi-modal or multi-modal network?
3. Start making connections or edges in your network. What type of edges do you need? Do the edges have a weight?
4. Think about centrality. Do you have an ego network? How might you start calculating centrality?

### Activity 5.2
Let's practice putting together a network visualization with sample data. 

1. Download the [results](https://docs.google.com/spreadsheets/d/1cUxojS6pQIkQCu_QVyPhZg2_yRuGM-XQuTqnMIcR5EE/edit?usp=sharing) of our super duper quick survey. 
2. To create an edge list, open the results in Open Refine. Follow these instructions carefully!
	* Remove the timestamp column.
	* From the first column after the names, select Transpose > Transpose cells across columns into rows.
	* Select the one column option and title your new column Value.
	* Check the box for Fill down in other columns.
	* Press Transpose. You should end up with **two columns** where each person's name is listed multiple times, corresponding with their answer to each survey question.
	* Extract your new edge list as .csv to download back to your computer.
3. Open [Palladio](http://hdlab.stanford.edu/palladio-app/) and drag your new edge list into the white box.
4. In Palladio, navigate to the Graph menu item. 
5. In the Settings box, you'll want to use the drop down menu to select a column from the data (name or target). You should now see a network viz!
6. Test out the checkboxes to see how that changes your visualization. What do the Facets do at the bottom of the screen? How do you download this image?
7. What are the limits of Palladio? 

### Activity 5.3

Let's continue practicing our skills reviewing established projects. Instead of a blog post, be prepared to talk about this project with your classmates. Select one of the following projects to explore. Use the review criteria from [Reviews in DH](https://reviewsindh.pubpub.org/review-process) to analyze the project.  

* [Kindred Britain](http://kindred.stanford.edu/#)
* [Belfast Group Poetry](https://belfastgroup.digitalscholarship.emory.edu/)
* [Six Degrees of Francis Bacon](http://sixdegreesoffrancisbacon.com/)
* [Linked Jazz](https://linkedjazz.org/)
* [Viral Texts](https://viraltexts.org/)

During class, we'll divide into groups to discuss the project you chose. Add your answers to a [Box note for your group](https://wlu.app.box.com/folder/148325460861). 

1. What is this project about? What are the goals?
2. Where/what is the data? How was it been gathered? Cleaned? Manipulated?
3. How is this a humanities project?
4. How effective are the network **visualizations**? Why do you say that?
5. What about the design, layout, and organization of the project? What works? What doesn't? How does it contribute to your understanding of the project? 
6. Who is in the network? Who might be left out of it? 
7. What technology is being used?
8. What research questions are in play? What other questions can you imagine? 

### Activity 5.4
 
Since you had such an easy time with Palladio, let's take our networks to the next level with [Gephi](https://gephi.org/). We'll use our [class sample data](https://docs.google.com/spreadsheets/d/1cUxojS6pQIkQCu_QVyPhZg2_yRuGM-XQuTqnMIcR5EE/edit?usp=sharing) from last week, plus we'll need an [attribute table](https://docs.google.com/spreadsheets/d/16j_dBrH0MqJQGRvNEOK1KPc85BjJJaQ7VUEngcSEDug/edit?usp=sharing). 

1. First, be sure you have your edge list formatted correctly. It should have two columns - one labeled **Source** and one labeled **Target**. We did this tranformation in Activity 5.2
2. Next, we need to work on the attribute table. We'll fill this out together. 
3. Download both files as `.csv`. 
4. We'll use these [Gephi instructions](../assets/GephiInstructions-fall2021.docx) to create our network (right click to download if the link doesn't work. 

### Activity 5.5

Now try putting together a network visualization from our trusty cemetery dataset. 

1. First, what are your questions? Who are the people in our data set? What networks should try to explore? You might have started on a line of thinking during the visualization week. Feel free to continue that! But try to identify questions that connect people to other people (not people to grave sites).
2. Next, we need an edge list. We know that this is a two column spreadsheet, what belongs in each column?
3. Go ahead and put some data together. This is a big data set, so we'll have to start somewhere. You are free to slice and dice this data to come up with a more manageable network, but give some thoughts to what those parameters will be. You could pick a family or a section for instance.
4. Upload your data into [Palladio](https://hdlab.stanford.edu/palladio/) or Gephi to create your network.
5. What worked? What didn't? Is network analysis the right method to use here? What can you learn by the network visualization and what might be obscured? 



## Resources
* [Creating a Network Graph with Gephi](http://miriamposner.com/dh101f15/index.php/creating-a-network-graph-with-gephi/) - Miriam Posner
* [From Hermeneutics to Data to Networks: Data Extraction and Network Visualization of Historical Sources](https://programminghistorian.org/en/lessons/creating-network-diagrams-from-historical-sources) - Programming Historian tutorial
* [Introduction to Network Analysis](http://thomaspadilla.org/na2014/) - Thomas Padilla and Brandon Locke

## Readings

* [An Entry of One’s Own, or Why Are There So Few Women In the Early Modern Social Network?](https://6dfb.tumblr.com/post/44879380376/an-entry-of-ones-own-or-why-are-there-so-few)
* [Demystifying Networks](http://www.scottbot.net/HIAL/index.html@p=6279.html)
* [Network Analysis Fundamentals](http://www.themacroscope.org/?page_id=892)
* [The Network Turn: Changing Perspectives in the Humanities](https://www.cambridge.org/core/elements/network-turn/CC38F2EA9F51A6D1AFCB7E005218BBE5)
