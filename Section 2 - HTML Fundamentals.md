# HTML Fundamentals

## Section Intro (8)

- We will learn very fundamentals language of Web devolepment, which is HTML.
- We are going to Learn HTML by building very easy HTML project

## Introduction to HTML (9)

![HTML 1](./asset_HTML_CSS/Screenshot%202024-01-27%20222111.png)

![HTML 2](./asset_HTML_CSS/Screenshot%202024-01-27%20222137.png)

## HTML Document Structure (10)

- We will learn the HTML Structure

- In this Session, we are going to create a Website : ` The Code Megazine`

![Code Megazine](./asset_HTML_CSS/Screenshot%202024-01-27%20223058.png)

---

- Create A Project Folder > 02-HTML-Fundamentals > Now copy and Paste the Starter Code

- Open it is the VS-Code

- Create a `index.html` (as the Starter File does not have it) - It is the Main/Start Page

```html
<!--1. The First Thing we need to do is to declare a DOCTYPE as html in order to tell the browser that this document uses html & all the browser will then know that they should use the HTML five Specification to render the HTML-->
<!DOCTYPE html>

<!--2. Each and Every HTML document always needs to start with the HTML Element. It is the Parent element of Both HEad & Body-->
<html>
  <!--3. Inside of HTML, we need one Head Element. So the Head element is for the things that are not visible in the Browser Window. So it contains the Page title, Additional Information about the Page, Link to CSS file etc-->
  <head>
    <!--Name of the Web Page, will be displayed in the Browser Tab-->
    <title>The Basic Language of the Web : HTML</title>
  </head>

  <!--4.Inside of HTML  Next We need one Body Element. This is for all the elemet which is visible on the page-->
  <body>
    <h1>The Basic Language of the Web : HTML</h1>
  </body>
</html>

<!--So We follow Indentation : It means Any Child Element should have a specific amout of space from the Parent Element, to make it visually obvious-->
```

## Text Elements (11)

- In this Lecture, we will continue learning HOW TO MARKUP TEXT. So we will use some Headings, some paragraphs, Bold, Italic

```html
<!DOCTYPE html>

<html>
  <head>
    <title>The Basic Language of the Web : HTML</title>
  </head>

  <body>
    <!--1. Different Heading Element . Heading is basically to break up text into logical sections
        2. Each and Every Page should have ONLY ONE H1 Heading (Very Important- Though it is not mandatory)
        3. Other Heading can have multiple Presence
      -->
    <!-- 
    <h1>The Basic Language of the Web : HTML</h1>
    <h2>The Basic Language of the Web : HTML</h2>
    <h3>The Basic Language of the Web : HTML</h3>
    <h4>The Basic Language of the Web : HTML</h4>
    <h5>The Basic Language of the Web : HTML</h5>
    <h6>The Basic Language of the Web : HTML</h6>
      -->

    <h1>📘 The Code Magazine</h1>

    <h2>The Basic Language of the Web: HTML</h2>
    <!--Paragraph is Used to Markup Bigger Block of Text-->

    <!--To Make a Bold Text We have Two Element, one in <b>{it is a older HTML Element} and the other is <strong> {it is HTML5 element : Recomended for Sementic }-->
    <p>Posted by <strong>Laura Jones</strong> on Monday, June 21st 2027</p>

    <!--To Make Italic, We have two Option
      1. <i> Element {OLD HTML ELEMENT }
      2. <em> Element {HTML 5 with Sementic : Recomended} as it tells Emphasize
    -->
    <p>
      All modern websites and web applications are built using three
      <em>fundamental</em>
      technologies: HTML, CSS and JavaScript. These are the languages of the
      web.
    </p>
    <p>
      In this post, let's focus on HTML. We will learn what HTML is all about,
      and why you too should learn it
    </p>

    <h3>What is HTML?</h3>

    <p>
      HTML stands for <strong>H</strong>yper<strong>T</strong>ext
      <strong>M</strong>arkup <strong>L</strong>anguage. It's a markup language
      that web developers use to structure and describe the content of a webpage
      (not a programming language).
    </p>
    <p>
      HTML consists of elements that describe different types of content:
      paragraphs, links, headings, images, video, etc. Web browsers understand
      HTML and render HTML code as websites.
    </p>

    <h3>Why should you learn HTML?</h3>
  </body>
</html>
```

## More Text Elements : List (12)

- In this Lecture, We will Learn How to Create a List with Bullet Points & Also with Numbers

```html
<p>In HTML, each element is made up of 3 parts:</p>

<!--Order List <ol>: Will have number-->
<!--Then We Need to add List <li> to add Content. So <li> is used for List Item-->
<ol>
  <li>The opening tag</li>
  <li>The closing tag</li>
  <li>The actual element</li>
</ol>

<h3>Why should you learn HTML?</h3>

<p>
  There are countless reasons for learning the fundamental language of the web.
  Here are 5 of them:
</p>

<!--Unorder List <ol>: Will have no number-->
<!--Then We Need to add List <li> to add Content. So <li> is used for List Item-->
<ul>
  <li>To be able to use the fundamental web dev language</li>
  <li>
    To hand-craft beautiful websites instead of relying on tools like Worpress
    or Wix
  </li>
  <li>To build web applications</li>
  <li>To impress friends</li>
  <li>To have fun 😃</li>
</ul>
```

- We need to Wrap Each Content inside Particular Element for having sementic meaning. If we do not use any elemnt (h1, p, li etc.), then all the text will be considered as a block of code only

## Images and Attribute (13)

- Will Learn How to add Image Element in HTML

```html
<!DOCTYPE html>

<!--We can also specify attribute in some other element, Example In HTML Tag, We can add Language Attribute as lng, to Specify the Language that we use for this webpage-->
<html lng="en">
  <head>
    <!--We can specify the Character Set Attribute in meta element (It is also a self closing element)-->
    <!--Meta Data means Data about the Data-->
    <!--UTF-8 Means all the simple character we use in Simple Emglish-->
    <meta charset="UTF-8" />
    <title>The Basic Language of the Web : HTML</title>
  </head>

  <body>
    <h1>📘 The Code Magazine</h1>

    <h2>The Basic Language of the Web: HTML</h2>

    <!--To add image, we use <img/> Element. As it does not have any content, so it is self closing-->
    <!--We have Attribute : These are nothing but pieces of Dat/information that describe the Element-->
    <!--It has src, alt, height, width attribute-->
    <img
      src="./laura-jones.jpg"
      alt="Headshot of Laura Jones"
      height="50"
      width="50"
    />

    <p>Posted by <strong>Laura Jones</strong> on Monday, June 21st 2027</p>
    <!--To add image, we use <img/> Element. As it does not have any content, so it is self closing-->
    <!--We have Attribute : These are nothing but pieces of Dat/information that describe the Element-->
    <!--It has src, alt, height, width attribute-->
    <img
      src="./post-img.jpg"
      alt="HTML Code on a screen"
      width="500"
      height="200"
    />

    <p>
      All modern websites and web applications are built using three
      <em>fundamental</em>
      technologies: HTML, CSS and JavaScript. These are the languages of the
      web.
    </p>
    <p>
      In this post, let's focus on HTML. We will learn what HTML is all about,
      and why you too should learn it
    </p>

    <h3>What is HTML?</h3>

    <p>
      HTML stands for <strong>H</strong>yper<strong>T</strong>ext
      <strong>M</strong>arkup <strong>L</strong>anguage. It's a markup language
      that web developers use to structure and describe the content of a webpage
      (not a programming language).
    </p>
    <p>
      HTML consists of elements that describe different types of content:
      paragraphs, links, headings, images, video, etc. Web browsers understand
      HTML and render HTML code as websites.
    </p>

    <p>In HTML, each element is made up of 3 parts:</p>

    <ol>
      <li>The opening tag</li>
      <li>The closing tag</li>
      <li>The actual element</li>
    </ol>

    <h3>Why should you learn HTML?</h3>

    <p>
      There are countless reasons for learning the fundamental language of the
      web. Here are 5 of them:
    </p>

    <ul>
      <li>To be able to use the fundamental web dev language</li>
      <li>
        To hand-craft beautiful websites instead of relying on tools like
        Worpress or Wix
      </li>
      <li>To build web applications</li>
      <li>To impress friends</li>
      <li>To have fun 😃</li>
    </ul>

    <p>Hopefully you learned something new here. See you next time!</p>
  </body>
</html>
```

## Hyperlinks (14)

- One of the Fundamental Building Blocks of the Internet are `Hyperlinks`, and in Short `links`

- `Links` are what actually enables the internet to be a world wide web. So without links between pages, there would be no web

- Let's Now Learn How to Place Links in our web page

---

- **Now We can place links into two big categories**.
  1. The First Category : Links that point to other pages within our own website
  2. The Second Category : Links that point to outside of website

---

```html
<h1>📘 The Code Magazine</h1>

<!--Here we will Create 1st kind of Link, which is baically links points to the pages that are part of the blog-->
<!--First We created New Pages : blog.html-->
<!--We will use Anchor Element, with href attribute-->

<a href="./blog.html">Blog</a>

<!--To Specify a Link which Does not go anywhere, we can use href="#", So here basically what it does it go to the top of the current page-->
<a href="#">Challanges</a>
<a href="#">Flexbox</a>
<a href="#">CSS Grid</a>

<h2>The Basic Language of the Web: HTML</h2>

<img
  src="./laura-jones.jpg"
  alt="Headshot of Laura Jones"
  height="50"
  width="50"
/>

<p>Posted by <strong>Laura Jones</strong> on Monday, June 21st 2027</p>
```

```html
<!--Here We created 2nd Type of Link, which points to the outside of the Website-->
<!--We use anchor element, <a> with href attribute, that takes the Link-->
<!--To open the Page in New Tab, we use TARGET attribute with UNDERCOREblank "_blank"-->
<p>
  You cab learn more at the
  <a href="https://developer.mozilla.org/en-US/docs/Web/HTML" target="_blank"
    >MDN Web Docs</a
  >.
</p>
```

- So we learned Target Attribute, Href Attribute, Href="#" also

---

## Structuring Our Page (15)

- Now we will add some structure to our document and to our element

- Let's Now Learn Couple of HTML5 Element for that

- So when I said, that page is lacking some structure, what I meant is that all of these element that is placed in our document, they are simply appearing one after another here. They are not really very distinguised from one another, and they are not group together in any logical way

- Let's fix it by adding some container element which will group these elements together.

- These Container (Grouping) element will not change any visual, but will help in Keeping the code sementic

```html
<!DOCTYPE html>

<html lng="en">
  <head>
    <meta charset="UTF-8" />
    <title>The Basic Language of the Web : HTML</title>
  </head>

  <body>
    <!--So We can also use Header Element to group the Top Part of Web Document-->
    <header>
      <h1>📘 The Code Magazine</h1>

      <!--For Page/or any Navigation, We use <nav> -->
      <!--Nav Stands for navigation-->
      <!--So these Links will be nicely included in the Navigation (Container/Grouped)-->
      <nav>
        <a href="./blog.html">Blog</a>
        <a href="#">Challanges</a>
        <a href="#">Flexbox</a>
        <a href="#">CSS Grid</a>
      </nav>
    </header>

    <!--So below that, all the things are blogs, So we can use Article Element. We can use it to wrap anythings which is simply Things from Real World. Like a Phone, Pen, Compoter, They are article-->
    <article>
      <!--For Addressing the Top Part of the Article, We use Header again, to describe the article in more clearly-->
      <header>
        <h2>The Basic Language of the Web: HTML</h2>

        <img
          src="./laura-jones.jpg"
          alt="Headshot of Laura Jones"
          height="50"
          width="50"
        />
      </header>

      <p>Posted by <strong>Laura Jones</strong> on Monday, June 21st 2027</p>

      <img
        src="./post-img.jpg"
        alt="HTML Code on a screen"
        width="500"
        height="200"
      />

      <p>
        All modern websites and web applications are built using three
        <em>fundamental</em>
        technologies: HTML, CSS and JavaScript. These are the languages of the
        web.
      </p>
      <p>
        In this post, let's focus on HTML. We will learn what HTML is all about,
        and why you too should learn it
      </p>

      <h3>What is HTML?</h3>

      <p>
        HTML stands for <strong>H</strong>yper<strong>T</strong>ext
        <strong>M</strong>arkup <strong>L</strong>anguage. It's a markup
        language that web developers use to structure and describe the content
        of a webpage (not a programming language).
      </p>
      <p>
        HTML consists of elements that describe different types of content:
        paragraphs, links, headings, images, video, etc. Web browsers understand
        HTML and render HTML code as websites.
      </p>

      <p>In HTML, each element is made up of 3 parts:</p>

      <ol>
        <li>The opening tag</li>
        <li>The closing tag</li>
        <li>The actual element</li>
      </ol>

      <p>
        You cab learn more at the
        <a
          href="https://developer.mozilla.org/en-US/docs/Web/HTML"
          target="_blank"
          >MDN Web Docs</a
        >.
      </p>

      <h3>Why should you learn HTML?</h3>

      <p>
        There are countless reasons for learning the fundamental language of the
        web. Here are 5 of them:
      </p>

      <ul>
        <li>To be able to use the fundamental web dev language</li>
        <li>
          To hand-craft beautiful websites instead of relying on tools like
          Worpress or Wix
        </li>
        <li>To build web applications</li>
        <li>To impress friends</li>
        <li>To have fun 😃</li>
      </ul>

      <p>Hopefully you learned something new here. See you next time!</p>
    </article>

    <!--For the Last part of the Document, We have footer-->
    <!--We took help of HTML Entity🟢🟢. For different Character. You will get it from Google-->
    <footer>Copyright &copy; 2027 by The Code Magazine</footer>
  </body>
</html>
```

## A Note on Sementic HTML (16)

- So in HTML, when we talk about Sementic, what we mean is that certain elements have actually a meaning or purpose attached to them.

- So when we think about certain HTML element, we should not think about what the element looks like as it renders on the Page, instead we should think what that element actually means and what is stands for. So this this basically the defination of Sementic HTML

- Example : `<strong>`, `<em>` instead of `<b> or <i>`

- Also some example : `<nav>, <header>, <article> , <footer>, <p>`

- So we use Sementic HTML to give our elements a meaning.

- Reason for Practicing Sementic HTML ? Well They help in
  1. Search Engine Optimization, accessibility,
  2. For the people who relies on screen readers to consume our webpage

## Installing Additional VS Code Extensions (17)

- **Image Preview** (it will show the image in HTML)

- **Color Highlight** (it will help in CSS)

- **Auto rename tag** (So it will help to edit Tag name, if we edit one tag, it will edit the close tag)

- **Live Server**

## CHALLANGE #1 (18)

- So currently images are not in a specific folder. So Create a folder and put all the images inside of that folder.

- Now change the path of `src`

- Now the challange is, Create a Aside Element and Create a List of Multiple Child Element

![Challange 1](./asset_HTML_CSS/Screenshot%202024-01-28%20024945.png)

```html

  <!--Aside element is usually used for some secondary information that complements  the imformation in the main part of the page-->
    <aside>
      <h4>Related posts</h4>
      <ul>
        <li>
          <img
            src="./img/related-1.jpg"
            alt="Person typing in Keyboard"
            height="60"
            width="60"
          />
          <a href="#">How to Learn Web Developement</a>
          <p>By Jonas Schemedtmann</p>
        </li>
        <li>
          <img
            src="./img/related-2.jpg"
            alt="Lightening Storm in the Sky"
            height="60"
            width="60"
          />
          <a href="#">The Unknown power of CSS</a>
          <p>By Jim Dillon</p>
        </li>
        <li>
          <img
            src="./img/related-3.jpg"
            alt="Code in Monitor"
            height="60"
            width="60"
          />
          <a href="#">Why JavaScript is Awsome</a>
          <p>By Matilda</p>
        </li>
      </ul>
    </aside>

    <footer>Copyright &copy; 2027 by The Code Magazine</footer>
  </body>

```

## CHANNANGE #2 (19)

![Challange 2](./asset_HTML_CSS/Screenshot%202024-01-28%20025554.png)

```html
<article>
  <h2>Converse Chuck Taylor All Star Low Top</h2>
  <img
    src="https://i.ibb.co/Jr7Wh1d/challenges.jpg"
    alt="Chuck Taylor All Star Shoe"
    height="250"
    width="250"
  />

  <p><strong>$65.00</strong></p>
  <p>Free Shipping</p>
  <p>
    Ready to dress up or down these classic canvas chucks are an everyday
    wardrobe staple
  </p>

  <a href="https://www.converse.in/" target="_blank">More information &rarr;</a>

  <h3>Product details</h3>

  <ul>
    <li>Leightweight, durable canvas sneaker</li>
    <li>Lightly padded footbed for added comfort</li>
    <li>Iconic Chuck Taylor ankle patch</li>
  </ul>

  <button>Add to cart</button>
</article>
```

**THE END**

**DATE : 28-01-2024 TIME : 3:18 AM**
