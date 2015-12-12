---
layout: post
---

The very first thing to know about web development is HTML.  **HTML is the language used by your browser to render a website.**  Let's start off with an example.  Check out the code and it's rendered counterpart below:

#### HTML code
<a id="example"></a>
{% highlight html linenos %}
<!DOCTYPE html>
<html>
  <head>
    <title>My Website</title>
    <meta name="author" content="Matthew Prestifilippo">
  </head>
  <body>
    <h1>My Great Company</h1>
    <p>My company <strong>makes</strong> things:</p>
    <ul>
      <li>Lions</li>
      <li>Tigers</li>
      <li>Bears</li>
    </ul>
  </body>
</html>
{% endhighlight %}

#### HTML rendered
<pre><iframe style="border:none; height: 200px; width: 300px; overflow: hidden;" src="/demos/html/demo.html"></iframe></pre>

You might be able to see that **My Great Company** and **My company makes things** is rendered, but **My Website** is not rendered.  This is because only things in between the `<body>...</body>` are rendered on the web page.  HTML that is inside of `<head>` is kind of like a <a href="https://en.wikipedia.org/wiki/Letterhead" target="_blank">letterhead</a> in that it is used to tell you information about the page itself.  In this example, our `<head>` just let's us know the title of the page and the author.

HTML is made up of elements.  For example, `<h1>My Great Company</h1>` is an HTML element, and so is `<body>...</body>`.  The general form, or syntax, of an element is `<tagname>text</tagname>` where `tagname` is one of the defined elements.  There are more than 100 types of HTML elements, and you can <a href="http://www.w3.org/TR/html-markup/elements.html" target="_blank">click here to see a complete list of HTML tags</a>.  Every HTML page starts with the **html** element, and has a **head** and **body** element.

### Exercise 1: Try HTML
> In this exercise, you will be able to edit HTML and see how the HTML affects the rendering.

> * Go to the <a href="https://jsbin.com/zasalakico/edit?html,output" target="_blank">jsbin editor</a>

> * Edit the html to render two headings.  One that says: "Hello, World" and one that says "Hello, Venus".

> * Nest an `<h1>` element inside of a `<p>` element like this: `<p>beginning <h1>title</h1> ending</p>`.  What happens to the text?

## HTML Syntax and Structure

We know that HTML is made up of elements, but we need to get some general rules in order to understand how more complex websites are made.

### Nesting

Some elements are "inside" other elements.  Just as the `<title>` element is inside the `<head>` element.  This is called **nesting**.  Nested elements are called **child elements**, and naturally, the elements that are doing the nesting are called **parent elements**.  So in our example above, `<title>` and `<meta>` are the child elements of the parent element `<head>`, and `<head>` and `<body>` are the child elements of the parent element `<html>`.

All child elements must end before their parent ends.
> **Good**

> `<p>This is a <em>good</em> example</p>`

> **Bad**

> `<p>This is a <em>bad</p> example</em>`

> Notice how the `<p>` element ended before the `<em>` element.


The end result of all of this nesting creates a **tree structure**.

![html tree](/images/posts/html/html-tree.png "html tree")

The tree structure doesn't embody a tree as in a maple tree.  Instead, it embodies something similar to a family tree which has parents, children, siblings, ancestors, and descendants.


### version, html, head, title, body
All html documents start with a line that specifies the HTML version, known as `DOCTYPE`.  The difference between this tag and the other elements that we have seen is that it has no closing tag.  It is also required to always be the very first line of your HTML document.  If you scroll back up to the <a href="#example">initial example</a>, you will notice we included `<!DOCTYPE html>` as the first line of the document.  At the time of this writing, HTML is currently on version 5 (you may have heard of HTML5).  The reason for the different versions is the addition of new tags, such as the `<video>`, to better suit demands for different types of content other than text, on the web.  By specifying the `DOCTYPE`, it lets the browser know how to properly display the HTML using appropriate rules for displaying the document.

The `<html>` element represents the **root element** of the document.  Like all of the other of the tags in this section, there may be only one `<html>` element in your document.  `<html>` will also contain the `<head>` and `<body>` elements.  The `<head>` element contains **metadata** about the HTML document.  **Metadata is a general term for any data that describes other data**.  One example of metadata would be the `<title>`, which doesn't get displayed on the page, but it displays on the window or browser tab.  Google will also use the `<title>` for listing the page on it's search results.  The search result below lists "HTML Tutorial - W3Schools", which means the title element looks like this: `<title>HTML Tutorial - W3Schools</title>`.

![html titles on google](/images/posts/html/titles-on-google.png "use of titles")

Lastly, we have the `<body>` tag which is the rendered section of the HTML document.

<a id="exercise-2"></a>
### Exercise 2: Create your own document
> You have the knowledge to create your first document, so we need to strengthen your confidence and skills by building a document from scratch.

> 1. Download a code editor if you don't have one already.  I recommend <a href="https://atom.io/" target="_blank">Atom</a>.

> 2. Open your code editor, and create a file named "index.html"

> 3. Create a document that:
> <ul style="list-style: disc; font-size: 14px;">
    <li>Has the title "My Interests"</li>
    <li>Specifies you as the author in it's metdata</li>
    <li>Displays a headline "My Interests"</li>
    <li>List 3 interests (they don't have to be real).
  </ul>

> <a href="/demos/html/interests.html" target="_blank">Click here to see my sample solution</a>

### What tags do I use?

If you tried out <a href="#exercise-2">exercise 2</a>, you may have found yourself wondering what tags to use.  This is a common problem with first timers, and will happen throughout your career.  You may have listed your 3 interests in side of one paragraph with `<p>1. soccer, 2. football, 3. hockey</p>` or you may have used the `<ul>` tag that was used in the <a href="#example">example</a> at the beginning of this article.  So which tag should is the correct one?

### semantic html

When writing HTML, you are really just categorizing and describing your data.  For example, if you have a list of items, you should probably take advantage of the list tags `<ul>` and `<ol>` to display your data.  If you are presenting a navigation section, you should use the `<nav>` tag.  If you are displaying an article, you should use the `<article>` tag.  You could technically *mark up* a list with a `<p>` tag, but then you lose semantics.  In order to know when to use which tag, it's important to get comfortable with all of the HTML tags.  Let's check out some of the fundamental tags to start writing.

### Basic tags

#### link
The link is one of the most important HTML tags since it connects pages together.  The format of a link is `<a href="http://example.com/">This is the link text</a>`.  This is the first time that we have seen anything other than the tag name inside of the `<` and `>` symbols.  The `href="..."` part is called an **attribute**, and the general form of an attribute is **attributeName="attributeValue"**.  The **href** attribute specifies the the webpage to go to when clicking on the text inside of the `<a>` tag.  Aside from linking to other webpages, you can link to other elements inside of an article, such as a table of contents.  This is possible through the use of the **id** attribute.  If you want webpage to scroll down to a specific element in the page, you can set the id, and reference it in the **href** attribute by prefixing the id with a `#` in the href attribute.  Ex:
{% highlight html %}
<a href="#content">Click here to go to content</a>
<h1 id="content">This is the content</h1>
{% endhighlight %}
I suggest trying this in <a href="https://jsbin.com/" target="_blank">jsbin</a> to get more comfortable with this behavior if it seems confusing.

#### article
Most of the web is made up of articles, such as news or blogs, so it makes sense that there is a special tag just for this use case.  A typical article is made up of a title and multiple paragraphs, which would look like this:
{% highlight html %}
<article>
  <h1>Principia Mathematica Proven Wrong</h1>
  <p>Physics doesn't exist.</p>
  <p>Newton didn't know what he was talking about...</p>
</article>
{% endhighlight %}

#### video
Prior to HTML5, there was no way to add a video to your HTML document without using Adobe Flash.  <a href="https://en.wikipedia.org/wiki/Apple_and_Adobe_Flash_controversy" target="_blank">Recent decisions with major tech companies</a> has caused Flash to go the wayside, and bring native browser support for video playback come to the forefront.

<video controls><source src="http://vjs.zencdn.net/v/oceans.mp4" /></video>
{% highlight html %}
<video controls><source src="http://vjs.zencdn.net/v/oceans.mp4" /></video>
{% endhighlight %}

#### image
The syntax to add an image to your page is `<img src="http://prestifilippo.org/images/posts/html/html-tree.png" />`.  This tag is somewhat different than most of the other tags that we have seen since it does not have a closing tag.  Tags that do not have a closing tag are called <a href="http://www.w3.org/html/wg/drafts/html/master/syntax.html#void-elements" target="_blank">void elements</a>.

#### lists
When enumerating a list, from a search result, or a list of friends, etc..., a list tag is a good choice.  Lists come in two forms: ordered (`<ol>`), and unordered (`<ul>`).  A somewhat handy display property of these tags is that they display numbers or bullet characters in front of each list item.
<h6>Unordered List</h6>
<ul><li>unordered item</li><li>unordered item</li></ul>
<h6>Ordered List</h6>
<ol><li>ordered item</li><li>ordered item</li></ol>
{% highlight html %}
<h6>Unordered List</h6>
<ul>
  <li>unordered item</li>
  <li>unordered item</li>
</ul>
<h6>Ordered List</h6>
<ol>
  <li>ordered item</li>
  <li>ordered item</li>
</ol>
{% endhighlight %}
#### header
This tag is for encapsulating header information, such as the page's title, table of contents, or search form.  This tag may be used more than once.  So if there are multiple sections in a page that require header information, like an article, then you may choose to use this tag to wrap things such as a title.

#### footer
This tag is for encapsulating footer information such as links, copyright info, and logos.  This is much like the header tag, except it's for what you would typically see at the end of a document.

### Basic attributes
#### class
#### id

## Readability

One of the most important things about code is that it is readable.  Yes, it has to work, but eventually you or others will have to come back to your code to make updates or fix errors.  Proper indentation is essential for making HTML readable.  If you look back at the <a href="#example">first example</a>, you will see that most the children elements are offset one tab length further than their parents, and siblings are offset at the same tab length.  This enables you to easily visualize where elements begin, end, and what elements they contain.  There is one exception, though, and that is the `<strong>` element.  So how do you know when you are supposed to indent on a new line or keep it inline?  If we take the example above, and try to reformat the `<strong>` element to be indented, it will look like this:

{% highlight html %}
<p>
  My company
  <strong>makes</strong>
  things:
</p>
{% endhighlight %}

This is also readable, but now it takes away from the actual flow of the prose that is in the `<p>` element.  So now we have two competing rules of "always indent" vs "reading prose".  Decisions like this come down to taste, so it is up to you to choose which style you'd like to follow.  Both are acceptable.

### Whitespace
> The contents of the `<p>` element above were split on separate lines.  Won't this format the text in separate lines when it is rendered?  Surprisingly, no, it does not affect how the text is rendered.  When HTML is rendered, there is only one space between two text nodes no matter how much space you put between them.  If you need to add more space between text, there are two options.  You can either use the `<pre>` tag, or you could use something called a character entity reference.  The character entity reference for a blank space is `&nbsp;` where nbsp is an acronym for non-breaking space.

### The Escape character: &amp;
Since we use the &lt; and &gt; symbol to denote the beginning of a tag, you might be wondering how to render a &lt;.  It might seem easy to know when a &lt; is the start of a tag or part of the text, but computers can't use any abstract contextual information (*yet*) to determine what was meant by the programmer.  So, long story short, &lt; is reserved to only be used when starting a tag.  In order to get around this limitation, an escape character is used: `&`.  An **escape character is a character that starts an alternative interpretation of the characters to follow**. So when the browser sees a &amp;, it stops trying to render text verbatim, and instead uses the subsequent characters to render the special character.  The *subsequent characters* are what is known as the character entity reference.

## Hypertext Markup Language
We jumped into some code examples before breaking down the acronym HTML.  HTML stands for Hypertext Markup Language.  Now that you have an idea of how HTML works, these terms will make a lot of sense.

### Hypertext
Hypertext is a term for text that is connected via links.  The idea is that if you need to learn more about a term or phrase, you can just click on that term, and more information will be presented.

### Markup Language
Markup Language is a system for annotating a document.  A document is some piece of data, like a user profile, an article, or a calendar.  Given that data, it is important to *mark up* things such as a person's name, a title, or a date.  This makes it easy for programmers to access any desired part of the document for processing such as adding a document to Google or assigning a color.

## Loose ends
### CSS
### XML &amp; DTD
### Documentation
### The DOM


<!-- classes, ids -->
<!-- rendering, box model, css -->
<!-- forms -->
<!-- format (root html element, tree structure, attributes, ) -->