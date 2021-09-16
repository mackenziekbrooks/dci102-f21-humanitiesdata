
In this section, we'll explore how Internet works, learn the basics of HTML and CSS, and setup your own website on WordPress. Before we can start doing research with humanities data, we need to understand a little bit about the context of our digital world.   

**Table of Contents:**

[TOC]

## What even is the Internet? 

The Internet is magic! Just kidding, it's not, but it can certainly seem that way. Maybe you're reading this on your phone in the middle of the lawn, or curled up in bed with your laptop. It's more than likely that you're using Wi-Fi or a cellular network and therefore have no physical connection to the Internet. It's understandable that it feels like magic sometimes! But in reality, the Internet is an immensely physical thing. Put simply, the Internet is computers directly connected to other computers. The information (text or media and all forms in between) you send and receive travels through wires and fiber-optic cables in the ground and even [under the ocean](https://www.submarinecablemap.com/). 

These connected or "networked" computers talk to each other using their own languages or more precisely, specific protocols. For instance, every computer has an address, known as an IP \(Internet Protocol\) address, to help direct traffic to the right place. Another protocol that you use even if you don't realize it, is the Hypertext Transfer Protocol, or HTTP. Your browser uses HTTP to render websites. When you type in `http://www.wlu.edu` your browser sends out a request to a computer that can serve up all the files at that particular address. The "server" returns the files and your browser (Safari, Chrome, Firefox) renders them into a website. At its simplest, a website is just a folder full of files and images. Those files are full of code, which we'll learn about in the next section.

Make sense? Here are a few videos that might help you visualize this great network of computers:

* [What is the Internet? ](https://www.youtube.com/watch?v=Dxcc6ycZ73M)
* [The Internet: Wires, Cables, and Wi-fi](https://www.youtube.com/watch?v=ZhEf7e4kopM)


## HTML
HTML, or Hypertext Markup Language, is one of the basic building blocks of the web. Every website you see is created using this language, from the most basic to most interactive. 

To see for yourself, go to your browser and open up a new tab. Visit any website you like. Right click, or `ctrl` + click to open up an options menu. Select `View Page Source`. If you're using Safari, try pressing `Command + Option + i`. You should see a new window full of text surrounded by angle brackets. That's the HTML that makes up the page you visited.

HTML stands for HyperText Markup Language. It is a set of tags, or *elements*, that adds structure to a document or page. When you write a document, you rely on style to indicate something about the text. You might put the title in a bigger font or break up paragraphs with tabs or new lines. Markup languages do this by adding tags around the content you wish to set apart. 

For example:

`<h1>This is a top level heading</h1>` is HTML that tells the browser to 1) increase the size of the text, but more importantly 2) that this piece of text represents a major section of the document. Which pieces of text on this page are an `<h1>`? Can you use the `View Page Source` trick to confirm?

What are other tags that you might expect to exist? If you were to analyze a website, what are the major components? What are the familiar conventions of websites, regardless of the type? 

Some things that come to mind: menus or navigation `<nav>`, images `<img src="kittens.jpg">`, or even just your basic paragraph `<p>`. 

To give you a taste, a basic HTML document might look like this: 

```
<html>
	<head>
		<title>My Awesome Website</title>
	</head>
	<body>
		<h1>Welcome/h1>
		<p>This is a long paragraph about my cat.</p>
	</body>
</html>
```

As you can see, angle brackets surround each tag. The tags themselves surround pieces of content. There's an opening tag and a closing tag. You can tell the closing tag by the slash after the angle bracket `</title>`. You should also notice that the tags are nested, that is some tags open and close themselves within the middle of other tags. The `<head>` and `<body>` tag are both children of `<html>`, and each of those tags has their own children. We'll learn more HTML down in [Activity 1.2](#activity-12-html). 

For now, the thing to remember is that HTML exists to tell the computer, specifically the browser, what to do with each piece of content. Another way to say this is *semantic markup*. Attaching structural or semantic meaning to content is especially important because not everyone (people or computers) uses their eyes to read the Web. Using valid HTML ensures that the Web is [accessible](https://www.w3.org/WAI/) to everyone, regardless of their ability. For instance, using heading tags like `<h1>` and `<h2>` tell a person about the organization of the page more than making text bold with the `<strong>` tag.  Altering the visual apprearance of the text without the structural headings won't convey the same meaning to a person who uses a screen reader.  Even if you don't go on to build websites for a living, something as simple as adding a caption to any image you publish can improve accessibility. An image without a caption or description is meaningless to someone who can't see it.  Can you find the caption or "alt text" for the image on this page? 

### Plain Text + Text Editors 
Before we move on, there's one other important thing to understand about writing HTML. HTML documents are plain text documents. The document do not contain styling like bold, italic, etc. Rather than using a Word doc or a Google doc, it's best to use a piece of software called a text editor. There are many text editors out there and it's personal preference which one you use. I like one called [Sublime](https://www.sublimetext.com/), but I know others use [Atom](http://atom.io) or [Visual Studio](https://visualstudio.microsoft.com/). Try a few out to see which one suits you, but know that I'll use Sublime throughout this course.

Even though the text is "plain", text editors have a feature called *syntax highlighting*, which means that the text changes color to help you write good code. When it's time to see what your markup or code can do, you'll need to open it in your browser or run it in the command line (the next chapter). 

## CSS

Our next building block of the web is CSS, or Cascading Style Sheets. We just learned that HTML will add structure to your document, but you need something else to add the pretty colors and images, also known as *style*. A style sheet is a plain text document that lists all the styles that you want to apply to your page. The cascading part refers to the priority scheme in CSS. You can apply styles widely (the whole page has the same font) or selectively (except for the menu which uses a different font).

If you analyze this page, what styles would you guess are in play? Are there some elements that look different than other elements? Cascading style sheets allow me to indicate that I want my headings to use a different font than my body text, for instance. 

CSS uses a different syntax than HTML. It can be a little confusing because it relies on HTML tags, but the structure is more list-like, rather than linear markup. Think about HTML as a document, and CSS as a separate list. Here's an example:

```
body {
	background-color: aquamarine;
	font-family: Helvetica, sans-serif;
}

h1 {
	font-size: 150%; 
}
```

The first step is to identify the HTML tag you wish to style. Here, we're styling everything that lives within the `<body>` tag. In CSS language, this is a selector. Once we identify our selector, we list, or *declare* the things we want to style within a pair of curly brackets. This can be called the "declaration block." We identify the thing, or "property" we wish to style, followed by a colon, then list the "value" we want to use, ending with a semi-colon. In CSS terms, it looks like this: 

```
selector {
property: value; 
otherProperty: anotherValue;
}
```

The syntax takes getting used to, but remember, you do not have to memorize every property or selector. Even experienced Web designers have to look things up. I recommend using the [W3 Schools](w3schools.com/) to find reliable code to copy. 

There's lots to love about CSS. In a relatively simple document, you can control the style of hundreds of HTML documents and ensure consistency. But you can also pinpoint one specific margin or border and change its color or add some padding. The [CSS Zen Garden](http://csszengarden.com/) site is a great example of the power of CSS. Each version of the site uses the same HTML, but different CSS.

One final note: to ensure that your CSS actually appears on your page, you need to add a piece of code to your HTML document that references the CSS document. We'll do this in [Activity 1.3](#activity-13-css).  


## Your domain 
There are many reasons you might want your own website. Whether it's for work, school, volunteering, organizing, art, or just for fun, there are plenty of ways to carve out your own corner of the Web. Social media platforms like LinkedIn or Facebook are ubiquitous now, but it used to be that if you wanted to appear in search results, you had to create your own website. If you are a student or navigating the professional world, chances are that 1) someone out there might Google you and 2) you want them to see accurate information and work that you're proud of. A professional website can be a simple single page with limited information, or it can contain your whole life. Chances are, at some point you've relied on information from a personal website. Maybe you found an article you need for a bibliography, a snippet of code that had been giving you trouble, or even an email address for someone who has lost their wallet. 

If you're conducting research in a field, making art, or selling products, there are others who will be interested in the work you're doing. Check out the sites of others in your intended field of study or career path to see what their websites look like. Some scholars share articles they've written, code libraries, data they've gathered, or new methods they're experimenting with. In the Digital Humanities, a field where many humanists work with data, open and public scholarship is highly valued. Many of the links in this coursebook go to the websites of DH-ers who have been generous enough to share a tutorial or write up their thoughts on a particular method. 

Whether you create a professional portfolio or not, there is a lot to be said for the form of a website. Most of the scholarship we read, not to mention everything else, has been designed and formatted to be consumed on the Web. Presenting your own work in that format gives you experience with seemingly silly things like getting your images to float nicely with your text or finding a place to reliably store your data. Creating a clean, well-organized website is harder than it looks! Just like it's easier to read a paragraph than to write one, creating a website takes practice. 

### Privacy
All that being said, you do not have to have a strong presence on the Web. You may have personal and legitimate reasons for not wanting to be found in search results. If you're a student, you may not want your homework following you for decades to come. You have the right to privacy and to completing your coursework in a secure way. While you are required to use your domain for this class, you can make it private during the course or remove it after the class is over.

### Reclaim Hosting
There are many places to find space on the Web, but many individuals and academic institutions work with [Reclaim Hosting](https://reclaimhosting.com), an education-focused web hosting company. Reclaim offers reasonable rates, good support, and an awareness of the needs of academic projects. Some institutions offer a "domain of one's" program in which affiliated individuals can obtain a domain. 

### WordPress 
Whether you knew it or not, chances are you have visited many, many WordPress websites. WordPress is an open-source content management system used by 42% of the web (as claimed by WordPress). Though it's thought of as a blogging platform, it powers plenty of [major websites](https://wordpress.org/showcase/). We'll use WordPress in this class as a platform for blog posts and your final project. It is easy to install on your domain and has plenty of customization options. It's likely that you might need to use WordPress at a future job, internship, or volunteer venture, so it's a good skill to have. Because of its popularity, there are many [resources](https://learn.wordpress.org/) online for learning or troubleshooting WordPress. 


## Activities 

### Activity 1.2: HTML

1. Using Sublime Text Editor, start a new document. Open the [W3 Schools tutorial](https://www.w3schools.com/html/html_intro.asp) in a new tab. Let's write some HTML!
2. First, save the file as `index.html` on your Desktop. Save your file regularly. 
3. Using the [HTML Basic](https://www.w3schools.com/html/html_basic.asp) as a guide, add the following tags to your document: `<html> <head> <title> <body>`. Don't forget to close the tags in the appropriate place.
4. To view your page in the browser, open `index.html` in your browser, usually with the key commands `Ctrl + o` or by going to File > Open.
5. Explore the tutorial on W3 and add seven more elements to the body of your HTML document, including a table, a link, and an image (that's three, find four more new elements to use beyond `h1` and `p`).
6. Create a second HTML page and link the two pages.

### Activity 1.3: CSS

Create a separate CSS document and save it as `style.css` in the same place as Activity 1.2.

1. Link the `style.css` file to your HTML document via the external stylesheet method. Consult the [W3 Schools](https://www.w3schools.com/html/html_css.asp) to figure out how to do this.
2. Add a background color.
3. Change the border on your table. 
4. Add style to your links when you hover over them. 
5. Add style to five more elements. This means you should identify five different elements from your HTML document and find ways to style them. Maybe your `<p>` needs to be indented or your `<a href=""` link should open in a new tab. Think about common styles you see online and try to replicate them.


### Activity 1.4: Make it live

When you opened your HTML files in your browser, you were viewing your files locally. Only you could see them on your computer. Now it's time to upload them to your domain so other people can view them.

1. Navigate to `http://yourdomain.wludci.info/cpanel` and login. 
2. In CPanel, open up the File Manager.
3. Navigate to the `public_html` folder. 
4. Create a new folder titled `activities` or something similar. 
5. Upload all your HTML and CSS files. 
6. Navigate to your equivalent of `https://username.wludci.info/activities`. What do you see?  


### Activity 1.5: Install WordPress

1. Login to the Cpanel for your domain by adding `/cpanel` to the end of your URL. Use the username and password sent to you by Reclaim Hosting/Jason Mickel. 
2. You should see a Wordpress icon near the top of the page. Click on it to begin installing Wordpress.
3. Find the "install this application" button. 
4. Work through the installation. You can leave the default settings except for the following:  
	* Directory  - since you might want to use this domain for other things, let's put course materials in a subdirectory, such as ``http://www.mydomain.info/dci102``. 
	* Change the administrator username and password to something you are likely to remember. Save these credentials for later!
	* Customize the website title and tagline.

5. Press install to finish up.
6. You should now be able to access your wordpress admin interface by appending `/wp-admin`to your selected URL. 


### Activity 1.6: Customize WordPress

1. Change your theme by going to `Appearance > Themes`. Select an installed theme, or find a new one with the `Add New` button. Activate multiple themes to try them out!
2. Check your comment settings in `Settings > Discussion` to make sure your classmates will be able to comment on your posts. 
3. Set up your menu (remember we'll have 3 units with similar assignments) by going to `Appearance > Menus`. You will need to create a menu, add pages to it, and select a location for that menu. This is usually the most confusing part of Wordpress! 
4. Before you start adding content to your site, play around with as many of the settings and features as possible. What do all the bells and whistles do? Add your own images or colors. This is *your* site!


## Resources 
* [Domain of One's Own Documentation](http://digital.brynmawr.edu/docs/)
* [HTML & CSS is Hard](https://www.internetingishard.com/html-and-css/)
* [Reclaim Hosting Support](https://community.reclaimhosting.com/)
* [W3 Schools HTML](https://www.w3schools.com/html/default.asp)
* [W3 Schools CSS](https://www.w3schools.com/css/default.asp)
