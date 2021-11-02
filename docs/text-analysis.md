In this section, we'll learn about ways of using the computer to read and analyze texts. 

Much of the material in this section was adapted and condensed (with permission and blessing) from the [Text Analysis Coursebook](http://walshbr.com/textanalysiscoursebook/) written by Sarah Horowitz and Brandon Walsh. Check out their coursebook for the full chapters and accompanying exercises. 

[TOC]

## Close Reading

Text analysis is something that we all engage in, whether we realize it or not. The term is broad and capacious and encapsulates a variety of different activities. Even something as simple as slowing down when you see a stop sign is a kind of text analysis: doing so means you have parsed the meaning of the words on the sign and reacted accordingly.

Indeed any of the following, related activities are forms of text analysis:

* Paraphrasing a text
* Searching for hidden meanings in a text
* Adapting a text and reflecting on it
* Examining the details in a text

This last point is worth pausing over: close reading, in particular, is often proclaimed as one of the primary analytical tool of scholars and students in the humanities. To read closely means to give careful attention to the various components that make up a text, ones which cause us to think or feel a certain way about it. Close reading relies on a core principle about the text under study:

> Everything about the text matters, whether the author intended for it to matter or not.

Consider the following thought experiment. One day you come home to find the following note from your roommate on the counter:

``` took care of these dishes? Thanks.```

Next to the note: dirty dishes. Was your roommate in a hurry and actually asking you to wash dishes? Or were they sarcastically trying to give you grief for not having done your part? Lots of questions. To imagine responses to them you might employ a range of assumptions and interpretations depending on the scenario:

* Context: you have been growing more and more irritated with your roommate for some time now. Their actions just really get under your skin: dirty dishes, laundry everywhere, the works. They clearly meant the note as an insult.

* Author: your roommate is actually a great person and would never leave a passive aggressive note. In fact, they probably meant it as a joke.

* Text: Take a look at that question mark. And then the curt second sentence. Your roommate put those things there on purpose to be rude.

The list could go on and on. We employ a similar range of skills when we read anything, be it fiction, poetry, or historical documents. Close reading might be best described as an activity in which a reader simply lets no detail of the text go unquestioned. The best way at approaching a good close reading is by asking (and attempting to answer) questions about every piece of a text.


## How Computers Read 

We've talked about how computers and humans have their respective skills. With respect to text analysis, we can say that computers and humans have complementary skills. Computers are good at doing things that would take us a long time to do or that would be incredibly tedious. Computers can easily count and compare and will do so for pretty much as long as you tell them to do so. In contrast, humans are very good at understanding nuance and context. Thus, you wouldn’t want a computer to do any close reading, or unpack the claims of a primary or secondary text; this is something you are far better at. By the same token, it’s probably easier to have a computer list all the numbers between one and 45678987 than to do it yourself.

Before we start analyzing texts, we need to know how computers understand text. Consider the following sentence:

“We saw 8 1/2.”

Taken alone, the sentence doesn’t tell us much. Its meaning depends a lot on the question to which we might be responding, and we can think of two possible questions with very different contexts:

* “How many movies did you see?

* “What movie did you see?”

In the first case, we might be responding with the number of movies that we had seen. It was a slow weekend, and we spent it at the local movie theater hopping from film to film. It was a great time! In the second situation, we might be responding with the title of a specific film, 8 1/2 by Italian director Frederico Fellini. So one answer is a number, and one answer is a name. Since humans are good at grasping context, we would easily be able to distinguish between the two. In most situations, we would just adjust our understanding internally before moving on with the conversation.

Computers cannot make inferences like these, and this fact has serious implications: numbers and words have significantly different uses. Here are two further extensions of the conversation:

* If you add four to how many movies you saw, what is the result?

If we were talking about a number of movies, my response would clearly be, “Oh that’s 12.5. Why are you giving me a math quiz?” If we were talking about the Fellini film, we might respond, “What? Oh, we were talking about a title, not a number. We can’t add things to a title.” Again, humans have the ability to respond to context, infer, and adapt. Computers aren’t nearly as flexible: they need to know ahead of time, in most cases, what kind of information they are dealing with. That way they can act as you anticipated.

We learned earlier about the concept of "data types." Well now they matter! In the above example, we encountered: 

* Strings: characters, the stuff of words
* Integers: a whole numbers

The distinction between strings and integers is important for text analysis. You can perform arithmetic operations on integers while strings respond less well to such things. You can capitalize words, but not numbers. And computers generally want you to deal with similar objects: you can combine strings (words can become sentences) or add numbers, but trying to combine a string and an integer will break things. To be clear to the computer which data type we mean, we use can indicate strings with "quote" marks and integers without. `8` vs. `"8"`. In response, the computer wants us to to know that it doesn't know that `"8"` is related to `"Eight"` or `"Eighth"` or even `"eight"`.

It might seem surprising that computers aren't smarter than that, but it brings us to one of the first steps in text analysis: tokenization, or the process by which we break apart all of the words and punctuation in a text into separate tokens. "I love you" becomes "I", "love", "you", ".".

We can break things down even further once we’ve divided a text into individual words. While we often care about how many times each particular token or word occurs, we might also care about the different kinds of words. We might want to keep track, on the one hand, of all the different words in a text regardless of how often they occur. But we might also want a different kind of vocabulary list. Rather than counting all the words, we might just want to grab a single example of each token type. If we have the following document:`Test test test sentence sentence`

We have five tokens and two types (‘test’ and ‘sentence’). A list of types might be good for getting a sense of the kinds of language used in a text, while a raw list of tokens could be useful for figuring out what kinds of words occur in which proportions. Depending on our research questions and interests, statistics like these can help us figure out what the document discusses as well as how it is being discussed.

“But wait,” you say, “computers care about capitalization. So if we tokenize a text and try to compare ‘word’ and ‘Word’ they will think they are entirely different things!” Good catch! You’re right, those differences in capitalization often aren’t meaningful. It is a fairly common practice to lowercase all the words after you tokenize them. This process is often called normalizing the data, since we are smoothing out inconsistencies that might get in the way of our research questions. This whole collection of processes of segmentation, tokenization, and normalization has a name of its own as well: preprocessing, all those things you do to data before you work with it. Depending on your interests, you might include other steps, such as tagging tokens for parts of speech or filtering out particular types of words. Note that preprocessing can change your list of types. A computer would not recognize “Said” and “said” as being of the same type, but, if you normalize capitalization so that every token is lowercased, a computer would see them as the same word. So you often need to decide what pieces you care about at the beginning of the process.


## Bag of words
When we read, our eyes move in sequence across the page and take in phrase after phrase in the order in which they were intended. This sense of chronology is integral to how we, as human readers, understand texts. But it is possible to imagine other ways of reading. Have you ever skimmed over a page backwards looking at every other word? You probably still got the gist of the text even though you didn’t read it in order and even though you missed many of the words.

If we take the words in a text as being indicative of its underlying topics, we actually don’t need to worry about word order so much. The sequence of words, sometimes called the **syntagmatic axis**, only matters for certain kinds of reading. But we can find out interesting things about texts if we are a little more flexible and think about them not as things that unfold over time but rather as pure token counts, as bags of words. In a **bag of words model**, word order becomes irrelevant. All we care about is what words occur in a text and how often they do so. 

You can use a bag of words approach to determine how different or similar whole books or authors are from each other. If we have lists of words for each text as well as for the corpus (or set of documents) as a whole, we can actually work backwards to get a sense of the underlying topics that we were talking about a moment ago. Instead of skimming a paragraph to determine its basic topic, we could scan full texts – and scan lots of them. And rather than trying to get a sense of 1-3 topics, we could break our text apart into 15-20 different topics. Now we are cooking with gas, and we’re talking about topic modeling.

## Topic Modeling

Given enough time and energy, we can imagine a tool that would infer topics for us without us having to read all of our documents first. The approach that we will take is a technique called **topic modeling**, a computational method that allows you to discover the topics that construct a text. Topic modeling does so by exercising a variety of statistical protocols over and over again on a text. 

Topic modeling involves some complex statistics, so the following description might seem a bit hand-wavey.  Topic modeling software looks for words that tend to occur next to each in statistically significant ways. The sum total of these words that occur next to each other becomes legible to a reader as a topic. Unlike the human brain, topic modeling software can process hundreds of thousands of texts, over and over again, refining its sense of how all the pieces fit together. It can give us a sense of the themes and discourses that run beneath an entire corpus.

In the following example, you can see a list of 10 topics from a corpus of 42 narratives by enslaved women, taken from the [North American Slave Narratives](https://docsouth.unc.edu/neh/index.html) collection and generated using the [Topic Modeling Tool](https://github.com/senderle/topic-modeling-tool). 

```
0. 	aunt dice thy mos master sam riverside john ye soul eyes phillis er river mistress thee evelyn song trevor thine
1. 	sojourner truth god people good isabella de mother years lord mind slavery son meeting washington time colored church master jesus
2. 	time life made day house great man long mr home found children give woman place work make friend called heard
3. 	mrs lincoln harriet mr mother de people president time war years woman white south letter received dress york room millie
4. 	mother master peter children mr free told slave good man slaves young day morning time don people mistress night house
5. 	miss de mr ann jane good young face master peterkin henry eyes don ll amy white polly room poor yer
6. 	negro colored years women men race war country people children free miss john slaves mrs white made slavery south negroes
7. 	good god years poor mind toussaint master heart love received jesus great thy read people saviour year thou lived man
8. 	lord god time people good church told day thought brother meeting home night mrs work sister man mother morning pray
9. 	church school work teacher people year time years conference good philadelphia members number great class colored god young early st
```


So when you run topic modeling software, it looks for words that occur near each other in texts in meaningful ways over the course of the corpus. In most cases, it looks for words that occur in documents together. Remember, these words are not dependent on their location within the document. Topic modeling works on a bag of words model that only cares about whether or not the words occur within the text, not their position within it. But you might occasionally chunk larger documents into a series of paragraphs so that the software thinks about them each as separate documents for finer granularity. There are a number of similar tricks for refining your processes.

Until now, we have stressed approaching text analysis with a clear sense of your interests and the research questions that drive them. Topic modeling works a little differently: it is more useful for exploratory work. We call topic modeling **unsupervised classification** because we are asking the computer to analyze and mark a text without giving it any clear directions. We just say, “here is some text. Do your thing and tell me what you find.” A **supervised classifier** would take information from us to help it make decisions. We might say, “read this text. If it has more than fifty uses of the word ‘crime’ mark it as ‘detective fiction.’ If it has fifty uses of the word ‘love,’ mark it as ‘romance’”). Unsupervised classifiers like topic modeling instead know very little about the underlying texts that they are examining. Instead, they process them based on an underlying model.

In the last section we called the bag of words model an epistemology of texts, a way of understanding documents that might be different from what you were familiar with. In the case of the kind of topic modeling we have been discussing, that model could further be called **Latent Dirichlet Allocation** (LDA). We won’t go into any detail about the specifics of LDA, but it is important to know that this is the model you are working with and that LDA assumes that a text is constructed from a small number of topics.

## Sentiment Analysis 

As we learn more complex ways to analyze texts, you might find yourself wondering: Is a particular text happy or sad? For that matter, is a sentence? A word?

This type of analysis that tries to capture the emotional resonance of a text is called **sentiment analysis**. You’ve probably engaged with this kind of work without realizing it. If you’ve ever been to Rotten Tomatoes to see what score a movie has gotten, you are looking at an aggregated number of reviews that have been marked as positive or negative. Businesses have a stake in such things as well. If you tweet about your recent flight, the airline would probably want to know whether you hated it or loved it. The former might result in you being directed to customer service, while the latter could result in a benign response like “thanks for flying with us!”

Sentiment analysis can also offer interesting opportunities for textual analysis. 

t would be fascinating to have a computer that could easily mark the sentiments in texts for you. If you have been following dutifuly along, however, you should know that computers can’t do much of anything without being explicitly told how. They can do very little in the way of understanding data without a human to guide them. Trying to extract complicated information like the sentimental arc of a text, how we are meant to feel about a sentence, or how an author intended us to feel are all complicated tasks that computers have a difficult time with. In fact, they can be hard for two different people to agree on. Try to guess whether these two sentences would be classified as good or bad:

`“I am very happy.”`

`“She is so sad.”`

Those were easy ones: good and bad. Hot and cold. How about this one:

`“It was the best of times, it was the worst of times…”`

This sentence is from Charles Dickens’s Tale of Two Cities and is probably a bit hard to parse in such a binary way. If it is both good and bad, it probably comes out as neutral, right? But Dickens was talking about the era of the French Revolution here; his whole point was that this was an extraordinary time, hardly a “neutral” situation. In fact, he is interested in juxtaposing different things - best/worst, London/Paris, etc. - not in resolving them. We would probably need some system for determining what to do in such situations.

Try this sentence, by Jane Austen, which complicates matters even further:

`“It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.”`

An avid reader of Austen would know that her texts come loaded with satire. It is unlikely she actually means her words to be taken at face value. Virtually no truths actually are universally acknowledged to be true, so the sentence winks at the reader and should not be taken in full seriousness. In fact, much of her work is meant as a scathing criticism of the culture and people around her. These opinions are largely indirect, couched in irony and satire that asks the reader to read against what the text says on the surface.

All of these things are difficult to convey to readers, let alone computers. Sentiment analysis through technology is tricky, but that doesn’t mean that researchers don’t try. The process is difficult and riddled with error, but also intellectually interesting in a number of ways. How do we map complicated abstract ideas like emotion in a way that computers could understand them? What can sentiment analysis like this tell us about the objects that we study?

## Building your corpus 

In text analysis lingo, **corpus** is another word for your data set. A corpus is a collection or body of texts with certain boundaries, usually determined by the researcher. A corpus may be the entire run of a newspaper or [literary works by African-American authors](http://www.electrostani.com/2020/07/announcing-open-access-african-american.html). 

But where does the text come from? There are a lot of existing places to search for existing corpora (the plural of corpus, a lovely word). Libraries, archives, and museums have been sharing their collections online for a long time, but have only recently started making it easy for researchers to use those collections in a computational way. Some institutions [build tools](https://analytics.hathitrust.org/) for you to use, or offer their [data as a download](https://lib.msu.edu/dsc/datasets/). You might also be able to contact an institution to see what they could make available. 

If you are not finding a pre-packaged corpus available, you have options for creating your own. If you're working from print material, you will need to scan the pages and extract the text through a process known as **Optical Character Recognition**. Be warned, this could be a lot of work! If you want to work with something that is already digital, but not well organized, there are [tools for scraping information](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) from the Web.

In most cases, your corpus will consist of a collection of text files in a folder or series of folders. Since we've established that the computer doesn't really care about styling when it comes to processing documents, using the `.txt` format is best. 

In most cases, you will want some identifying metadata in your file names so you can identify the file in a graph or other visualization. You'll want to generate a file naming convention that highlights what is unique about each document (date, name, etc). In the Data section, we talked about how computers use file names to sort content. If you want your text files to appear in chronological order, you should begin your file names with a year. 

### Copyright 

One final note on copyright. Creative works published after 1925 (as of 2020) are within copyright, meaning you do not have the right to do anything you want with them. The principles of fair use allow you to use those works for academic purposes, but that does not usually extend to republishing them in full. If you wanted to perform text analysis on a recently published novel, you might have to generate that text yourself, and then only share your results, not the corpus itself. Fortunately, materials published before 1925 are available for use! You can find texts in places like [Project Gutenburg](https://www.gutenberg.org/) or the [Public Domain Review](https://publicdomainreview.org/).

## Text Analysis Tools

* [Voyant](voyant-tools.org/) - A robust and popular tool for conducting many types of text analysis. FYI, you can run Voyant [locally](docs.voyant-tools.org/resources/run-your-own/voyant-server/) on your own computer. This is useful for large datasets or times when Voyant is slow.
* [Lexos](http://lexos.wheatoncollege.edu/upload) - This tool from Wheaton College performs some powerful pre-processing of your corpus for text analysis.
* [AntConc](http://www.laurenceanthony.net/software/antconc/) - Software package for linguistic analysis of texts, particularly concordance work.
* [Google Books Ngram Viewer](https://books.google.com/ngrams)  -  A popular tool for visualizing n-grams over time in the Google Books data set. Prof. Brandon Walsh delves into the nuances of the Ngram Viewer over on his [text analysis workbook](https://bmw9t.gitbooks.io/introduction-to-text-analysis/content/issues/google-ngram.html). You can apply the same technology to your own corpus with a took called [Bookworm](http://bookworm.culturomics.org/).
* [MALLET](http://mallet.cs.umass.edu/http://mallet.cs.umass.edu/) - Stands for MAchine Learning for LanguagE Toolkit. It's a powerful command line tool for topic modeling. 
* [Scott Enderle's Topic Modeling Tool](https://senderle.github.io/topic-modeling-tool/documentation/2017/01/06/quickstart.html) - is an option for topic modeling if you don't want to use the command line. It creates nice HTML pages for interacting with the data. 
* [NLTK](http://www.nltk.org/) - Python library containing a number of text analysis tools. If you feel comfortable with the command line or have programming experience, you might want to explore this option. Check out the [Steinheil Affair project on GitHub](https://github.com/wludh/frenchnewspapers) for an example of what can be with NLTK. You might also be interested in [A Humanist's Cookbook for Natural Language Processing with Python](https://github.com/walshbr/humanists-nlp-cookbook/blob/release/toc.ipynb).


## Activities

### Activity 7.1 - 4 Ways of Reading a Text

In this activity, we'll work through Prof. Brandon Walsh's "4 Ways of Reading a Text" lecture. To prepare, please print one copy of this [handout packet](../assets/4waystoread-handouts.docx). 


### Activity 7.2 - Voyant

Let's spend some time getting comfortable with [Voyant Tools](http://voyant-tools.org/).
 
1. Visit [Project Gutenberg](https://www.gutenberg.org/browse/scores/top) and find a text you know well. Maybe it's one you read in a class or one that's just a personal favorite. 
2. Download the plain text version of your selected book. 
3. In [Voyant Tools](http://voyant-tools.org/), upload the text file you just downloaded. 
4. Use the little window icon to change the tool being displayed in each window.
5. Answer the following questions. For each question, identify the visualization tool you used to find the answer. Sometimes there are more than one way to visualize the results. Which methods work bets? 
	* What are the most common words in your text? The least common? 
	* Search for a meaningful word in the Trends tool. How is that word used over the course of your text?
	* What are the topics of your text? Which tool did you use to find the topics?
	* Which tools help you find connections between words? 
	* What is the weirdest visualization you can find? 
	* Which visualization seems totally bizarre and not helpful? Why? 
	* How do you export your results? 
	* What types of questions can you form about your text with these tools? 

6. If you finish with Voyant, take your text to [Lexos](http://lexos.wheatoncollege.edu/upload). What is different about this tool? Why is it useful? What other features does it have? Who created it? 


### Activity 7.3

Now that you're comfortable with [Voyant](http://voyant-tools.org/), let's return to the Ring-tum Phi and compare it to another corpus: the [Alumni Magazine](https://github.com/wludh/dataset-AlumniMagazine). 
 
1. Select similar portions of time from both the Ring-tum Phi and the Alumni Magazine. You probably don't want to start with the entire decade - it's often best to start with a small bit of data and move up from there.  
2. Assemble your corpus. Now that you're familiar with Voyant, what makes the most sense for each file? How many years should go in each file aka what is the "granularity?" How do you need to structure the corpus to balance the granularity of each file? IE: if one text file contains an entire year and another file contains just one month, how will that affect your graph? 
3. Upload your corpus to Voyant. To add a multiple files, find the Documents tab in the lower left corner. Press the Modify button, then Add, then Upload, to add more text files to Voyant. Make sure your files are named in a way so that they will be easy to distinguish from one another.
4. Try out the various visualizations in Voyant. Which work best for a comparison between these two corpora? What can you learn about how these two publications cover the same topics? How might you use text analysis methods in your own project?
5. Select three of the most meaningful visualizations and include them in a post along with 400-500 on the experience of text analysis, the meaning in your visualizations, and the answers to the questions in step 4. 



## Projects
* [Mining the Dispatch](http://dsl.richmond.edu/dispatch/)
* [The Proceedings of the Old Bailey](https://www.oldbaileyonline.org/)
* [Quantifying Kissinger](http://blog.quantifyingkissinger.com/)
* [Dash Amerikan](http://dashamerikan.scholarslab.org/)
* [Robots Reading Vogue](http://dh.library.yale.edu/projects/vogue/)
* [A Topic Model of Literary Studies Journals](http://www.rci.rutgers.edu/~ag978/quiet/#)
* [America's Public Bible](http://americaspublicbible.org/)

## Resources 
* [Corpus Analysis with AntConc](https://programminghistorian.org/en/lessons/corpus-analysis-with-antconc)




