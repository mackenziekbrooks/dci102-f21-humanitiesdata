In this section, we'll learn about ways of analyzing spatial data, through maps or similar visualizations.

[TOC]


## What is spatial analysis? 

It's hard to deny the popularity of maps. Many of us use them on a daily basis - for wayfinding, as art on our walls, or as data visualization. Advancements in digital maps and location-based services from our cell phones make us more reliant on maps and **GIS** or geographic information systems, than ever before. Location-based data is now a huge commodity, not to mention a security and privacy issue. 

That being said, the tools of geographers can now be used by humanities scholars in a wide range of ways. Both commercial and academic mapping tools are available for studying the movement of humans through space and time. There are major Digital Humanities projects devoted to creating, organizing, and publishing data about historical locations. There are tools to layer historic maps onto modern maps, allowing the user to layer the past onto the present. 

But it's important to remember that all maps, historical or modern, print or browser-based, are representations of space. Google Maps is just as capable of distorting reality as a map from 1500. Humanities scholars are using maps to study the past, but they're also demonstrating that maps "are themselves highly contingent fabrications, bending the physical reality of the world to our innate need to grasp and process, and dangerously full of altered data." ([Torn/Apart](http://xpmethod.columbia.edu/torn-apart/))


## What does it look like in the humanities? 
Spatial work takes many forms in the humanities. In his [Spatial Humanities workshop](https://lincolnmullen.com/projects/spatial-workshop/), historian Lincoln Mullen describes two types: narrative maps and data map. We'll use these categories to explore what spatial humanities looks like. At this point, this coursebook will not cover virtual reality or three-dimensional space, but know that those are increasingly commons ways to represent space. They also generate a lot of data! 

### Narrative maps
According to Mullen, we can define narrative maps this way: 

> A narrative map tells a story plotted through space. The point of a narrative map is not to display data. Rather it is to provide an explicit visual counterpart to the implicit spatial underpinnings of a narrative or argument.

Narrative map are a little more like infographics than data visualizations in this way. They might depict a journey, narrate the movement of an event, or layer historical maps of the same place in a creative way. Like every tool or method, it's important to know your audience and goals when deciding to use a narrative map. They can be a great way to convey information in an engaging setting, particularly one that is public-facing, such as a digital exhibit for a museum. But they don't, by-and-large, contain a lot of data, which is what we're interested in in this coursebook. 


### Data maps 
Data maps are maps created to visualize or present data about or relevant to a location. In most cases, you are uploading a data set to an application and that application generates a view of the data, rather than dropping pins by hand. Your data set could contain information about many things - people, buildings, monuments, statistics, you name it - but there should be a spatial data component. What that component looks like often depends on the tool you're using. Some programs can identify state names or zip codes, others need specific coordinates. Of course, it also depends on the rest of your data. Do you want your map to show voting patterns by county? Then you'll need spatial data that is aware of county boundaries. Perhaps you want to show individual residences, then you're likely to need individual coordinates for each location. Do you need to keep time period in mind in case boundaries have changed? Maybe you want users to be able to interact with your map, how will that look?

Data driven maps can be tricky because it's not always clear what is easy to do and what is more difficult. Each tool has its own affordances or expectations. It can be a good idea to explore a new mapping tool with a sample data set to learn the features and limitations. In a later section, we'll share various mapping tools and their strengths and weaknesses.  

### Beyond maps 
It should be noted that there is more to analyzing space than just building maps. Advanced GIS applications or programming languages will provide you with methods (beyond your eyes) for analyzing patterns in your data. Most of these methods are beyond the scope of this coursebook, but know that they exist when you're ready to take your spatial analysis to the next level.

## Spatial data
Due to the volume of proprietary and open tools, spatial data can come in many forms. We'll get to file formats in a minute, but let's start with the basics:

* Coordinate system - By drawing lines around the earth (latitude and longitude), geographers have created a grid system from which we can calculate points and assign numbers to locations. The equator and the Prime Meridian are the lines where we start counting, where the latitude and longitude (respectively) is set to 0°. 

* Map projections - As we know, the earth is round. To project the round earth onto a flat map (or plane), adjustments must be made. Imagine trying to cover a baseball with a piece of paper - it's going to have some creases right? Geographers use various projections to account for this problem. Most of us will find the Mercator projection to be quite familiar, but it is actually quite [misleading](https://thetruesize.com/). If you have the option, you want to choose a projection that fairly represents the space you're depicting.
 

* Latitude/longitude - Latitude are lines drawn horizontally around the earth. Longitude are lines drawn vertically around the earth. Lat/long coordinates can be expressed in degrees, minutes, and seconds (38° 53′ 23″ N, 77° 00′ 32″ W) or decimals (38.8897, -77.0089). You'll typically use decimal lat/long in spatial data projects.

* Vector vs. raster - You'll encounter these terms when it comes time to put stuff on your map. Vector layers are made up of shapes (including points, lines, polygons, etc) that can shift and change along with your map. Even though they look like lines, they are actually the relationship between places. Raster layers are made up of pixels. Imagine adding a historic map or a satellite image to your mp. While raster layers can stretch to fit a certain area, they might pixelate or morph in undesirable ways.

* Shapefiles - Shapefiles is a term for vector spatial data. Your points, lines, polygons are called shapes. As data, they are expressed with coordinates. Specifically, they are used by the company ESRI in their ArCGIS suite of software. You'll see shapefiles with the file extensions: `.shp, .shx, .dbf, and .prj`. 

* GeoJSON - We've seen some of these letters before right? JSON is a serialized data format. GeoJSON is a common data format for storing geographic information. It might look something like this: ` 
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [125.6, 10.1]
  },
  `

## Mapping Tools 
The popularity and usefulness of maps means that there are a wide range of commercial and scholarly tools available. Unfortunately, many of the flashiest tools are only available at high cost. 

* ESRI ArcGIS - [ArcGIS](arcgis.com/) is the industry standard in GIS and is licensed by corporations and academic institutions. ESRI provides an ecosystem of software, most of it quite expensive and desktop based. [ArcGIS Online](https://www.arcgis.com/home/index.html) is the browser-based option, though you have to pay for full features. ESRI does provide [ArcGIS StoryMaps](https://storymaps.arcgis.com/), a great narrative map option, at no cost. 

* QGIS - [QGIS](https://qgis.org/en/site/) is free, open GIS software for your desktop. It allows you to view, modify, and analyze geospatial data. However, QGIS is more for crunching data, not publishing it online. 

* Google Maps - Most folks are familiar with Google Maps. The [My Maps](https://www.google.com/maps/d/) feature allows you to create your own map, including via an uploaded dataset (though there are limits on the amount of data and features). You might see some references to maps created with Google Fusion Tables - this product no longer exists. One of the reasons to be conscious of the companies you trust with your product. 

* Tableau - [Tableau](https://www.tableau.com/) is another industry piece of software, frequently licensed by businesses and universities. The free version is [Tableau Public](https://public.tableau.com/en-us/s/). 

* LeafletJS - [Leaflet.js](leafletjs.com/) is a JavaScript library created interactive maps for the web. You will need to know a little to a lot of code to get your map to do what you want, but it's a popular option for custom projects. 

* Palladio - [Palladio](http://hdlab.stanford.edu/palladio/) is a great digital humanities tool for early exploration of your data. The mapping capabilities are limited, but it's easy to get up and running with a prototyped map.

* StoryMapJS - [StoryMapJS](https://storymap.knightlab.com/) is the quintessential narrative map tool. You can customize your map and add to your story through slides in their standalone interface. There is no data component here, but you can add various media.

* Neatline - [Neatline](neatline.org/) is another narrative map tool that fits within a large digital exhibit platform called Omeka. Neatline allows you to insert text and image into your map, or even add in a timeline component.



## Activities

### Activity 6.1
To start thinking spatially, let's create a map from scratch. 

1. Gather some blank paper and your favorite writing/drawing/coloring instruments. 
2. Without consulting any existing maps, draw a map of campus. 
3. In a small group, we'll compare our maps with each other. How are your maps similar or different? What choices did you make? How are your choices informed by your hobbies, extracurriculars, personality, abilities, etc? What was challenging? What makes our campus hard/easy to map? 
4. Now, let's look at the existing [campus map](https://campusmap.wlu.edu/) as well as [images](https://wlu.app.box.com/file/875580429816) from the firm redesigning some of our spaces on campus. How did they approach our campus? What did they privilege or ignore? Does this depiction of space match your own perceptions? 

### Activity 6.2 
Let's continue building on our Coeducation Report data set so we can use it to try out some mapping tools in the next activity. Our data set needs coordinates, not just location names, for it to be easily to process by the mapping tools. Before I tell you exactly how to add coordinates, spend some time on Google. What services are out there for converting location names to coordinates? How do they work? What formats do they accept or produce? Remember, while it might be possible to convert each location one at a time, this would not be practical if our data set was any bigger. Let's look for some more automated solutions. 


### Activity 6.3 
There are a lot of options for tools that will create maps. In this activity, we'll divide into groups and test out a platform or two. We'll use the Coeducation Report as the data source for our map (it's in Box).

Groups: 

* Team Palladio: Nayongi, Gavron, Maya, Quinn
* Team ArcGIS: George, Richard, Elizabeth, Lily
* Team Google MyMaps: Caitlyn, Merrill, Kit, Gabe, Mark
* Team Tableau: Emma, Kaitlyn, Amanda, John, Mary Beth

Platforms:

* [Palladio](http://hdlab.stanford.edu/palladio/)
* [ArcGIS Online](https://www.arcgis.com/index.html) - Note that you can create a [free public account](https://www.esri.com/en-us/arcgis/products/create-account) or use the [StoryMaps](storymaps.arcgis.com/) feature. We have an institutional license if you want to use ArcGIS longer term.
* [Google My Maps](https://www.google.com/maps/d/)
* [Tableau Public](https://public.tableau.com/en-us/s/)


In your groups, answer the following questions. Record your answers in a Boxnote so that other students can consult the information. 

* Who created this tool? Is it open source? Is it free?
* How do I use it? Browser or download? OS preference?
* How do I add data? What formats does it accept?
* How do I add layers?
* How do I add shapes or pins?
* Can I add a historical map? How?
* Where is the basemap from? (Google, OpenStreetMap, etc.) Can I change it?
* What type of mapping project would suit this tool?
* Can you find the documentation? Other tutorials?
* Using the Coeducation Report data, create a map. You may need to alter the data to fit the requirements of the mapping tool. 

For your homework this week, you'll select a second platform and go through the same questions and upload the Coeducation data, then compare the two platforms.

## Resources
* [Spatial Humanities Workshop](https://lincolnmullen.com/projects/spatial-workshop/)

## Readings
* [Anatomy of a Web Map](http://maptime.io/anatomy-of-a-web-map/)
* [What is Spatial History?](https://web.stanford.edu/group/spatialhistory/cgi-bin/site/pub.php?id=29&project_id)

## Credits
Material for this section was derived from Lincoln Mullen's [Spatial Humanities Workshop](https://lincolnmullen.com/projects/spatial-workshop/) materials per the CC-BY-NC-SA 4.0 license. 
