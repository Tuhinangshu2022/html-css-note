# Layouts : Floats, Flexbox, and CSS Grid Fundamentals

## Section Intro (44)

- How to build layouts from floats
- Using modern technology like Flexbox & CSS Grid

## The 3 Ways of Building Layouts (45)

![Layout](./asset_HTML_CSS/Screenshot%202024-02-13%20112900.png)

![Layout](./asset_HTML_CSS/Screenshot%202024-02-13%20112917.png)

![Layout](./asset_HTML_CSS/Screenshot%202024-02-13%20112936.png)

## Using Floats (46)

- We need to Before undersatding a float layout, first, we need to understand how the float property actually works. So that is going to the goal of this lecture

![What we will learn](./asset_HTML_CSS/Screenshot%202024-02-13%20113449.png)

- Lets start with new starter files. Since we are continuing from the previous section, I will go ahead to copy the same folder and paste it with different name, `04-css-layout`

```css
/* F L O A T S 🆕🆕 */

/* In Some cases, we can make display chnage, from block to inline-block to make something work, but let's
learn something new, which is float */

/* I want the Image of Author and Any Autor Name Paragraph to be in side by side */
.author-img {
  /* By this the image is going to be out of the document flow,just like an absolutesly positioned element, but the difference with the float is that then all the other elements will basically float around it */
  float: left;
}

.author {
  /* We are trying to add some space between the elements */
  /* padding-left: 10px; */
  /* The ABove code will not work, as the text start behind the image, that is why adding 10 pixel of padding will not chnage a lot */

  padding-left: 70px;
  /* It will work☝️ */
  padding-top: 10px;
}

/* So the understanding is the image has been taken completely out of the pages flow. It is as if the image is'not even on the page. It does not effect the surrounding elements */
```

![Image](./asset_HTML_CSS/Screenshot%202024-02-13%20140432.png)

**Now let's learn how we can actually fix the fact that the p element basicalls starts right at the begining of the container**

```css
/* F L O A T S 🆕🆕 */

.author-img {
  float: left;
}

.author {
  padding-left: 70px;
  padding-top: 10px;
  float: left;
}

/* Now the image & P both float side by side, and p starts right after the image */
```

![image](./asset_HTML_CSS/Screenshot%202024-02-13%20140826.png)

---

- We can also move it to right also (author)

---

- This is the last state of code, and the best way

```css
/* F L O A T S 🆕🆕 */

.author-img {
  float: left;
  /* Floating Element also works with Margin */
  margin-bottom: 20px;
}

.author {
  /* padding-left: 70px; */
  /* padding-top: 10px; */
  float: left;
  margin-top: 10px;
  margin-left: 20px;
}
```

---

Let's Fix the Header

```css
h1 {
  float: left;
}

nav {
  float: right;
}

/* But the Header height got lost, infact it is only visible because we have some padding in the header.

Why?

All of its child element, 2 here, all of them are floated. This means there 2 elements are not in the page, as if they have been removed. So the header element has no content anymore, that way it makes sense the heght is ZERO now

This Phenomena is called collapsine elemnts. when it happens we say the element height is collapsed, it happens here because the children are floating, as if they are not in the page anymore*/
```

![Image](./asset_HTML_CSS/Screenshot%202024-02-13%20142649.png)

![image](./asset_HTML_CSS/Screenshot%202024-02-13%20142832.png)

## Clearing Floats (47)

- Lets now fix the problem of the hrader height that we encountered last time. So it is collapsing elements

- We will learn clraeing floats

- Add another elmenet from the header, and clear it from there

```html
<header class="main-header">
  <h1>📘 The Code Magazine</h1>

  <nav>
    <a href="./blog.html">Blog</a>
    <a href="./challange.html">Challanges</a>
    <a href="#">Flexbox</a>
    <a href="#">CSS Grid</a>
  </nav>

  <!-- Add a New Class with class name clear, for naming convention -->
  <div class="clear"></div>
</header>
```

```css
h1 {
  float: left;
}

nav {
  float: right;
}

/* We just select the element, and we use the clear property, to clear left, right or both existing float */
.clear {
  clear: both;
}
```

- We can do it another way also, by adding a new class named by clearFix hack.

```html
<header class="main-header clearfix">
  <h1>📘 The Code Magazine</h1>

  <nav>
    <a href="./blog.html">Blog</a>
    <a href="./challange.html">Challanges</a>
    <a href="#">Flexbox</a>
    <a href="#">CSS Grid</a>
  </nav>
  <!-- <div class="clear"></div> -->
</header>
```

```css
/* After selecting the clearfix, we add a brand new pseudo elemnt as a last child */
.clearfix::after {
  /* Content is required */
  content: "";
  clear: both;
  /* Also pseudo elemnts are inline elemnts by default, so we need to make them block level */
  display: block;
}
```

## Building a Simple Float Layout (48)

- We will create a Side-bar in our page

```css
.container {
  /* 🆕🆕 1. Make the container big, For all the layout, we do this */
  width: 1200px;

  margin-left: auto;
  margin-right: auto;
  /* position: relative; */
}

article {
  /* Adding background color to see what we are doing now */
  background-color: #ffe70e;

  /* Since they are block element, they are using 100% of their available width of the container, So if we want them side by side, each of them needs to have a certain width. SO our container is 1200px width, so lets divide the width with a proper width */

  width: 900px;

  float: left;
}

aside {
  /* Adding background color to see what we are doing now */
  background-color: rebeccapurple;
  width: 300px;
  float: right;
}

footer {
  /* Adding background color to see what we are doing now */
  background-color: blue;
}

/* The Float Property has a certain feature, So even footer is not floated, but the footer is floating around pf these 2 elements, this is what the float property does. It makes it so the elemnt comes after it will float around that first element. So here we have 1st article, then aside then comes footer, so if we set the aside to float, then the element that comes after it float around  */
```

![image](./asset_HTML_CSS/Screenshot%202024-02-13%20163308.png)

- Solution :

```css
footer {
  /* Adding background color to see what we are doing now */
  background-color: blue;

  /* The Float Property has a certain feature, So even footer is not floated, but the footer is floating around pf these 2 elements, this is what the float property does. It makes it so the elemnt comes after it will float around that first element. So here we have 1st article, then aside then comes footer, so if we set the aside to float, then the element that comes after it float around 
  
  Solotion : to clrear both*/

  clear: both;
}
```

---

- Lets create some space between the article and aside

```css
/* Selecting the Element */

article {
  /* background-color: #ffe70e; */

  /* width: 900px; */
  /* 🆕🆕 Creating space by chnaging the width */
  width: 825px;

  float: left;
}

aside {
  /* Adding background color to see what we are doing now */
  /* background-color: rebeccapurple; */
  width: 300px;
  float: right;
}

footer {
  /* Adding background color to see what we are doing now */
  /* background-color: blue; */

  clear: both;
}
```

## Box-Sizing : Border-Box (49)

![image](./asset_HTML_CSS/Screenshot_1%2013-02-2024%201.png)

SOLUTION :

```css
/* Removed the Margin  */
.related {
  list-style: none;
  margin-left: 0;
}
```

- Now are adding some padding in the aside, to create a space, and we will face some issue, (he is teaching)

```css
aside {
  background-color: #f7f7f7;
  border-top: 5px solid #1098ad;
  border-bottom: 5px solid #1098ad;

  /* After removing the margin, We added some padding  */
  padding: 50px 40px;
}
```

- Now aside come to down. Buy why?

![image](./asset_HTML_CSS/Screenshot%202024-02-13%20165432.png)

- So total container width is 1200, article is 825, and aside is 300 + 40+40= 380. SO that is why it is not fixing in the side part, and came down.

- How to fix? Should we now manually chnage the size of this aside here in order to account for the padding? or we we have a another way?

- We have another way. So its time to leave behind the default behaviour of the box model. Lets learn how the other version of box model really looks like.

![image](./asset_HTML_CSS/Screenshot%202024-02-13%20170019.png)

- Now the width is actually what we define in our code, & not the Adding Padding.
- So Real Inside Content Width may gets affected, but it does not matter, we have full control over it now

```css
* {
  margin: 0px;
  padding: 0px;
  /* We want that all the element gets the property to br applied */
  box-sizing: border-box;
}
```

- This a simple most popular global reset

## Challange #1 (50)

![Chnallange](./asset_HTML_CSS/Screenshot%202024-02-13%20171351.png)

- Create containers
- Inside 3 conteainer
- Between div, 40px space

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="./style1.css" />
  </head>
  <body>
    <article class="product">
      <h2 class="product-title">Converse Chuck Taylor All Star Low Top</h2>
      <!-- We add a clear fix at last for not getting any next element to be attached after the floated element -->
      <div class="container clearfix">
        <img
          src="https://i.ibb.co/Jr7Wh1d/challenges.jpg"
          alt="Chuck Taylor All Star Shoe"
          height="250"
          width="250"
          class="product-img"
        />
        <!-- Adding a new container 4 -->
        <div class="product-info">
          <p class="price"><strong>$65.00</strong></p>
          <p class="shipping">Free Shipping</p>
          <p class="product-description">
            Ready to dress up or down these classic canvas chucks are an
            everyday wardrobe staple
          </p>

          <a class="more-info" href="https://www.converse.in/" target="_blank"
            >More information &rarr;</a
          >

          <div class="colors">
            <div class="color color-black"></div>
            <div class="color color-blue"></div>
            <div class="color color-red"></div>
            <div class="color color-yellow"></div>
            <div class="color color-green"></div>
            <div class="color color-brown"></div>
          </div>
        </div>

        <!-- Adding another container 5 -->
        <div class="product-details">
          <h3 class="details-title">Product details</h3>

          <ul class="details-list">
            <li>Leightweight, durable canvas sneaker</li>
            <li>Lightly padded footbed for added comfort</li>
            <li>Iconic Chuck Taylor ankle patch</li>
          </ul>
        </div>
      </div>
      <button class="add-btn">Add to cart</button>
    </article>
  </body>
</html>
```

```css
* {
  margin: 0;
  padding: 0;
  /* 1 */
  box-sizing: border-box;
}

body {
  /* For inherited */
  font-family: sans-serif;
  line-height: 1.4;
}

/* PRODUCT */
.product {
  border: 4px solid black;
  width: 825px;

  margin: 50px auto;
  position: relative;
}

.product::before {
  content: "sale";
  font-weight: bold;
  text-transform: uppercase;
  background-color: #ec2f2f;
  padding: 7px 15px;
  font-size: 15px;
  /* text-align: center; */
  color: #f7f7f7;
  /* Letter Spacing 🆕🆕 Learnt */
  letter-spacing: 2px;

  position: absolute;
  top: -20px;
  left: -35px;
}

.product-title {
  background-color: #f7f7f7;
  text-transform: uppercase;
  text-align: center;
  font-size: 30px;
  padding: 15px;
}

.product-img {
  /* 9 */
  float: left;
  margin-right: 40px;
}

/* PRODUCT INFORMATION */
.product-info {
  /* 7. We have to calculate the total width
  So there is a calculation : 
  total - Img - borderOfBigContainer - space(Between both the 3 container)
  825-250-(4+4)+ (40+40) =487
  487/2 = 245.5px
    */

  width: 243px;
  float: left;
  /* 40 px  side */
  margin-right: 40px;
  margin-top: 20px;
}

.price {
  font-size: 24px;
  float: left;
  /* 2 */
  float: left;
}

.shipping {
  color: #777;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 12px;
  margin-bottom: 20px;
  /* 3 */
  float: right;
  /* 10 */
  margin-top: 8px;
}

.product-description {
  /* 6  So whenever you have some elements floating around with some elements placing itself where you do not want it, then you can simple clear the float*/
  clear: both;

  /* 11 */
  margin-bottom: 10px;
}

/* MORE INFO */

.more-info:link,
.more-info:visited {
  color: black;

  display: inline-block;
  margin-bottom: 30px;
}
.more-info:hover,
.more-info:active {
  text-decoration: none;
}

.color {
  height: 22px;
  width: 22px;
  display: inline-block;
  margin-right: 5px;
}

.color-black {
  background-color: black;
}
.color-blue {
  background-color: blue;
}
.color-red {
  background-color: red;
}

.color-yellow {
  background-color: yellow;
}

.color-green {
  background-color: green;
}

.color-brown {
  background-color: brown;
}
/* PRODUCT DETAILS */

.product-details {
  /* 8 */
  width: 243px;
  float: left;
}

.details-title {
  text-transform: uppercase;
  font-style: 16px;
  margin-bottom: 15px;
  margin-top: 15px;
  /* 12 */
  margin-top: 20px;
}

.details-list {
  margin-left: 20px;
}

.details-list li {
  margin-bottom: 15px;
}

/* Button */
.add-btn {
  background-color: black;
  color: #f7f7f7;
  border: none;
  font-size: 20px;
  text-transform: uppercase;
  cursor: pointer;

  padding: 15px;
  width: 100%;
  border-top: 5px solid black;
}

.add-btn:hover {
  background-color: white;
  color: black;
}

/* Trick for clear fix */
.container {
  background-color: #ec2f2f;
}

.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```

## Introduction to Flexbox (51)

- Let's learn the basic of flexbox, so that we will learn in isolation

- get the file from isolation, grab the `flexbox.html` & `cssgrid.html` in the current working folder

flexbox.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flexbox</title>
    <style>
      .el--1 {
        background-color: blueviolet;
      }
      .el--2 {
        background-color: orangered;
      }
      .el--3 {
        background-color: green;
        height: 150px;
      }
      .el--4 {
        background-color: goldenrod;
      }
      .el--5 {
        background-color: palevioletred;
      }
      .el--6 {
        background-color: steelblue;
      }
      .el--7 {
        background-color: yellow;
      }
      .el--8 {
        background-color: crimson;
      }

      .container {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        /* FLEXBOX */
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="el el--1">HTML</div>
      <div class="el el--2">and</div>
      <div class="el el--3">CSS</div>
      <div class="el el--4">are</div>
      <div class="el el--5">amazing</div>
      <div class="el el--6">languages</div>
      <div class="el el--7">to</div>
      <div class="el el--8">learn</div>
    </div>
  </body>
</html>
```

![flexbox](./asset_HTML_CSS/flexbox%20fundamentals.jpg)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flexbox</title>
    <style>
      .el--1 {
        background-color: blueviolet;
      }
      .el--2 {
        background-color: orangered;
      }
      .el--3 {
        background-color: green;
        height: 150px;
      }
      .el--4 {
        background-color: goldenrod;
      }
      .el--5 {
        background-color: palevioletred;
      }
      .el--6 {
        background-color: steelblue;
      }
      .el--7 {
        background-color: yellow;
      }
      .el--8 {
        background-color: crimson;
      }

      .container {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 30px;
        margin: 40px;

        /* FLEXBOX */
        display: flex;
        /* All the elements immediately comes now side by side.
        And all the elements here, we call flex items, because they are the child element of flex container 
        
        - All the elemnts horizontally takes only the space they need for the text content
        
        - Vertically things are different, So vertically all the flex itms are as tall as the tallest elements. So CSS(el--3) has the largest height, so all the elements has height if the tallest*/

        /* To make all the element vertically cerntered:;
        
        So the flex container still takes height of the height element, (which is 150px), but all the other ones simply takes the place that they need for the text or in generak for the content and then they get vertically aligned in the centre
        */
        align-items: center;

        /* to put the element from start from the top */
        align-items: flex-start;

        /* to put the elemenet start from the bottom */
        align-items: flex-end;

        /* By default, the value of align items is stretch. So it means all the element becomes as tall as the tallest element */
        align-items: stretch;

        /* TO center all the element horizontally. So basically all the items inside of the flex container */
        justify-content: center;

        /* To make all the elements has same space between space  */
        justify-content: space-between;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="el el--1">HTML</div>
      <div class="el el--2">and</div>
      <div class="el el--3">CSS</div>
      <div class="el el--4">are</div>
      <div class="el el--5">amazing</div>
      <div class="el el--6">languages</div>
      <div class="el el--7">to</div>
      <div class="el el--8">learn</div>
    </div>
  </body>
</html>
```

## A Flexbox Overview (52)

![flexBox](./asset_HTML_CSS/Screenshot%202024-02-14%20021616.png)
![flexBox](./asset_HTML_CSS/Screenshot%202024-02-14%20021632.png)
![flexBox](./asset_HTML_CSS/Screenshot%202024-02-14%20021654.png)

## Spacing and Alligning Flex Items (53)

```css

  <!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flexbox</title>
    <style>
      .el--1 {
        background-color: blueviolet;
      }
      .el--2 {
        background-color: orangered;
      }
      .el--3 {
        background-color: green;
        height: 150px;
      }
      .el--4 {
        background-color: goldenrod;
      }
      .el--5 {
        background-color: palevioletred;
      }
      .el--6 {
        background-color: steelblue;
      }
      .el--7 {
        background-color: yellow;
      }
      .el--8 {
        background-color: crimson;
      }

      .container {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 30px;
        margin: 40px;

        /* FLEXBOX */
        display: flex;

        /* Cross Axis (Vertically) */
        align-items: center;

        /* Main Axis (Horizontally) */
        justify-content: space-between;
      }

      /* To override the alignmenet of any particulat flex item */
      .el--1 {
        /* Cross Axis  */
        align-self: flex-start;
      }

      .el--5 {
        /* Agian overriding the particular flex element */
        align-self: stretch;
      }

      /* So when want to put any flex element in first or last */
      .el--6 {
        /* Default value of element is 0, So if we want to move any elemenr to very first position, all we need to do to specify a number that is lower than that  */
        /* Now the el 6 has become the first element */
        order: -1;
      }

      .el--4 {
        /* To Move any element to the last, we specify more than 0 */
        order: 1;
      }

      /* If want to put element even more last, than we need to specify number more than the previous one */
      .el--3 {
        order: 2;
      }

      /* to add space between manually in flex item. Till now we saw flexbox automatically create space between flex items using justified content. but now we will learn manually creating space

      There is two ways we can do, one is adding a margin  */
      .el {
        /* margin-right: 15px; */
        /* So we created 15px of sapce in the right side, of all the element, as we selected all the element */
      }

      /* But we can make it simple with gap property in the container, to make space between the flexelement in one go

      Also if you inspect, there is no margin also*/
      .container {
        gap: 20px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="el el--1">HTML</div>
      <div class="el el--2">and</div>
      <div class="el el--3">CSS</div>
      <div class="el el--4">are</div>
      <div class="el el--5">amazing</div>
      <div class="el el--6">languages</div>
      <div class="el el--7">to</div>
      <div class="el el--8">learn</div>
    </div>
  </body>
</html>


```

## The Flex Property (54)

- Let's now earn the basics of the flex property which is the property that we use in order to actually size flex items

```html

<style>
  .el {
        /* DEFAULTS :  */
        /* flex-grow: 0;
        flex-shrink: 1;
        flex-basis: auto; */

        /* When we want to size flex items and in particular with a width, then we usually do not use the width property, but instead we use flex-basis */

        /* Lets say we want the element to have wodth of 100px*/
        /* So it works as if the content size is not excedding, it will keep 100px, if the Content inside is more that 100px, only those will get stretched up*/

        /* flex-basis: 100px; */

        /* So the flex-basis are not rigid, it is like a recommendation that we make to the browser, but the broeser will based on the content, figure out the optimal length

        Also by default flexbox is allowed to shrink elemnts so that they fit the container, and that means the flex-shrint:1 is actually means, so again, if there is no enough space in the container to fit the item with the size that we describe hwew using flex-basis, then flex box is allowed to shrink these items by default as it is set as 1

        if we do not want shrink, we can chnage it*/

        /* So it will overflow from the container if they are more than the size of container */
        /* flex-basis: 200px; */
        flex-shrink: 0;

        /* ALso we have flex grow, just opposite of Flex-shrink, that determines whether elements are allowed to grow as large as they can or not

        So the container is Filled up with no gap left in last part. OS if any last part has remianing gap, then all the flex item will get same amount*/

        /* flex-grow: 1; */
      }

      /* What happens when we sleect only one element to flex grow? */
      .el--1 {
        /* So now only this element is allowed to fillup the remining space */
        /* flex-grow: 1; */
      }

      /* What happens if one of them is 2 in flex-grow */
      .el--2 {
        /* It would get double of the available empty space than the other four
        So if the empty space is 600px, so all the flex element will get 100 px, but this onlw will get 200px , also if we select 3, then it can become 300 also*/
        /* flex-grow: 2; */
      }

      .el {
        /* We should use the shorthand
        flex-grow, flex-shrink, flex-basis */
        flex: 0 0 200px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="el el--1">HTML</div>
      <div class="el el--2">and</div>
      <div class="el el--3">CSS</div>
      <div class="el el--4">are</div>
      <div class="el el--5">amazing</div>
      <div class="el el--6">languages</div>
      <!-- <div class="el el--7">to</div>
      <div class="el el--8">learn</div> -->
    </div>
  </body>
</html>

```

## Adding Flexbox to our Project (55)

```html
<header class="post-header">
  <h2>The Basic Language of the Web: HTML</h2>
  <!-- 🆕🆕 author box (For Creating flex box) -->
  <div class="author-box">
    <img
      src="./img/laura-jones.jpg"
      alt="Headshot of Laura Jones"
      height="50"
      width="50"
      class="author-img"
    />

    <p id="author" class="author">
      Posted by <strong>Laura Jones</strong> on Monday, June 21st 2027
    </p>
  </div>

  <img
    class="post-img"
    src="./img/post-img.jpg"
    alt="HTML Code on a screen"
    width="500"
    height="200"
  />
</header>

<aside>
  <h4>Related posts</h4>
  <ul class="related">
    <!-- Added Class and Div🆕🆕 -->
    <li class="related-post">
      <img
        src="./img/related-1.jpg"
        alt="Person typing in Keyboard"
        height="75"
        width="75"
      />
      <div>
        <a href="#" class="related-link">How to Learn Web Developement</a>
        <p class="related-author">By Jonas Schemedtmann</p>
      </div>
    </li>
    <li class="related-post">
      <img
        src="./img/related-2.jpg"
        alt="Lightening Storm in the Sky"
        height="75"
        width="75"
      />
      <div>
        <a href="#" class="related-link">The Unknown power of CSS</a>
        <p class="related-author">By Jim Dillon</p>
      </div>
    </li>
    <li class="related-post">
      <img
        src="./img/related-3.jpg"
        alt="Code in Monitor"
        height="75"
        width="75"
      />
      <div>
        <a href="#" class="related-link">Why JavaScript is Awsome</a>
        <p class="related-author">By Matilda</p>
      </div>
    </li>
  </ul>
</aside>
```

```css
/* So we need to fix, Author Image, Nav & aside */
.main-header {
  display: flex;
  /* Vertically Item alignement */
  align-items: center;
  /* Horizontally  */
  justify-content: space-between;
}

/* We have made a new flex container for author image & Author name(p) */
.author-box {
  display: flex;
  align-items: center;

  margin-bottom: 20px;
}

.author {
  margin-bottom: 0;
  margin-left: 15px;
}

/* Now we are adding some new classes to put the Header of Related Post and author name come right side */
.related-post {
  display: flex;
  align-items: center;
  margin-bottom: 30px;
  /* Adding gap between image and the right side div */
  gap: 20px;
}

.related-link:link {
  font-size: 17px;
  font-weight: bold;
  font-style: normal;

  /* We know anchor is inline, so having margin bottom, we need to turn it back to block */
  margin-bottom: 5px;
  display: block;
}

.related-author {
  margin-bottom: 0;
  font-size: 14px;
  font-weight: normal;
  font-style: italic;
}
```

## Building a simple Flexbox Layout (56)

```css
/* Overall page layout */
/* We will add article and aside element side by side */
/* First Question, what is the Flex Container */
/* We need to create a Flex Cntainer named ROW for article & aside */

.row {
  display: flex;
  gap: 75px;
  margin-bottom: 60px;
  /*Veritically  */
  align-items: flex-start;
}

aside {
  /* For defining the width of element  */
  /* DEFAULTS :  */
  /* flex-grow: 0;
        flex-shrink: 1;
        flex-basis: auto; */
  flex: 0 0 300px;
}

article {
  /* flex: 0 0 825px; */
  /* It will also work, as we have already defined gap in flex container & aside width
  
  So we are just giving the article element to grow as much as it wants, knowing the fact, that gap & aside is already declared*/
  flex: 1;

  margin-bottom: 0;
}
```

## Challange #2 (57)

![Chnallange](./asset_HTML_CSS/Screenshot%202024-02-13%20171351.png)

```css
/* Main Page Layput for the 3 container */
.row {
  display: flex;
  gap: 40px;
}

/* Product Price & Free Shipping */
.product-price {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
}

.shipping {
  /* Overriding the margin */
  margin-bottom: 0;
}

/* Product Colors */
.product-colors {
  display: flex;
  gap: 10px;
}

.product-info {
  flex: 1;
  margin-top: 10px;
  /* margin-right: 40px; */
}

.product-details {
  flex: 1;
  margin-left: 10px;
}
```

## Introduction to CSS Grid (58)

- Lets learn in Isolation the CSS Grid

- We have the html file for this

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS Grid</title>
    <style>
      .el--1 {
        background-color: blueviolet;
      }
      .el--2 {
        background-color: orangered;
      }
      .el--3 {
        background-color: green;
        height: 150px;
      }
      .el--4 {
        background-color: goldenrod;
      }
      .el--5 {
        background-color: palevioletred;
      }
      .el--6 {
        background-color: steelblue;
      }
      .el--7 {
        background-color: yellow;
      }
      .el--8 {
        background-color: crimson;
      }

      .container--1 {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        /* CSS GRID */
      }

      .container--2 {
        /* STARTER */
        font-family: sans-serif;
        background-color: black;
        font-size: 40px;
        margin: 100px;

        width: 1000px;
        height: 600px;

        /* CSS GRID */
      }
    </style>
  </head>
  <body>
    <div class="container--1">
      <div class="el el--1">(1) HTML</div>
      <div class="el el--2">(2) and</div>
      <div class="el el--3">(3) CSS</div>
      <div class="el el--4">(4) are</div>
      <div class="el el--5">(5) amazing</div>
      <div class="el el--6">(6) languages</div>
      <div class="el el--7">(7) to</div>
      <div class="el el--8">(8) learn</div>
    </div>

    <div class="container--2">
      <div class="el el--1">(1)</div>
      <div class="el el--3">(3)</div>
      <div class="el el--4">(4)</div>
      <div class="el el--5">(5)</div>
      <div class="el el--6">(6)</div>
      <div class="el el--7">(7)</div>
    </div>
  </body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS Grid</title>
    <style>
      .el--1 {
        background-color: blueviolet;
      }
      .el--2 {
        background-color: orangered;
      }
      .el--3 {
        background-color: green;
        height: 150px;
      }
      .el--4 {
        background-color: goldenrod;
      }
      .el--5 {
        background-color: palevioletred;
      }
      .el--6 {
        background-color: steelblue;
      }
      .el--7 {
        background-color: yellow;
      }
      .el--8 {
        background-color: crimson;
      }

      .container--1 {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        /* CSS GRID */
        /* 1 */
        /* Just like flex box, we have flex container & Flex item
        In CSS Grid, we have grid container, & Grid Items
         */
        display: grid;
        /* 2. Then we need to define 2 dimensional layout 

        - Here we can define as many width value as we want, and for each of these value, one column will be created */

        /* grid-template-columns: 250px 250px; */
        grid-template-columns: 250px 250px 150px 150px;

        /* 3. ☝️ If you observe, the el--3 has height 150, that is why the whole row height is 150 altogether 
        
        - If no height were present, then it would have been the height of content*/

        /* 4. To size the all the row manually. But only the CSS(EL3) which has defined height of 150, it did not chnagem but all the other row size got chnaged */
        grid-template-rows: 300px 200px;

        /* 5. Just like flex box, we can also specify gap in CSS grid . And this is the only way of defining gap between grid items
        
         5. Always use gap, and never margin (It wont work then)*/
        /* grid-gap  & gap both are same*/
        /* It creates gap between row and columns */
        /* gap: 20px; */

        /* 6. We can aslo define seperate gap value for column and rows */
        column-gap: 30px;
        row-gap: 60px;
      }

      .container--2 {
        display: none;
        /* STARTER */
        font-family: sans-serif;
        background-color: black;
        font-size: 40px;
        margin: 100px;

        width: 1000px;
        height: 600px;

        /* CSS GRID */
      }
    </style>
  </head>
  <body>
    <div class="container--1">
      <div class="el el--1">(1) HTML</div>
      <div class="el el--2">(2) and</div>
      <div class="el el--3">(3) CSS</div>
      <div class="el el--4">(4) are</div>
      <div class="el el--5">(5) amazing</div>
      <div class="el el--6">(6) languages</div>
      <div class="el el--7">(7) to</div>
      <div class="el el--8">(8) learn</div>
    </div>

    <div class="container--2">
      <div class="el el--1">(1)</div>
      <div class="el el--3">(3)</div>
      <div class="el el--4">(4)</div>
      <div class="el el--5">(5)</div>
      <div class="el el--6">(6)</div>
      <div class="el el--7">(7)</div>
    </div>
  </body>
</html>
```

![Image](./asset_HTML_CSS/Screenshot%202024-02-14%20201251.png)

## A CSS Grid Overview (59)

![Css Grid](./asset_HTML_CSS/Screenshot%202024-02-14%20202854.png)
![Css grid](./asset_HTML_CSS/Screenshot%202024-02-14%20202916.png)
![Css Grid](./asset_HTML_CSS/Screenshot%202024-02-14%20202937.png)
![Css Grid](./asset_HTML_CSS/Screenshot%202024-02-14%20202955.png)

## Sizing Grid Columns and Rows (60)

![css grid 1](./asset_HTML_CSS/css%20grid%201.jpg)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS Grid</title>
    <style>
      .el--1 {
        background-color: blueviolet;
      }
      .el--2 {
        background-color: orangered;
      }
      .el--3 {
        background-color: green;
        /* height: 150px; */
      }
      .el--4 {
        background-color: goldenrod;
      }
      .el--5 {
        background-color: palevioletred;
      }
      .el--6 {
        background-color: steelblue;
      }
      .el--7 {
        background-color: yellow;
      }
      .el--8 {
        background-color: crimson;
      }

      .container--1 {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        display: grid;
        /* Create Columns & Rows */
        /* grid-template-columns: 250px 250px 150px 150px; */
        grid-template-rows: 300px 200px;
        /* Gaps  */
        column-gap: 30px;
        row-gap: 60px;

        /* 1. 🆕🆕 If we create column with fr unit, it will allow us to create flexible column & flexible rows. 
        Using px will give these tracks very rigid dimension. So if we zoom the page, the cell may overflow. So the width of the column will always be the same that we defined, even if we resize the screen.
        
        So at some point it overflowed the container. And many times that is not what we need. Instead we want flexible columns & rows. For that, we can use fr unit
        
        2. So if we have space & want to be filled by the third column only. So it is little bit like setting flex to one in the flexbox*/
        grid-template-columns: 250px 250px 1fr 150px;

        /* 3. If we want 3rd & 4th column should fill the free space if there is any. So it is like setting flex-grow : 1 */
        grid-template-columns: 250px 250px 1fr 1fr;

        /* 4. To Create a grid where all the column with same width. But ofcourse, if we zoom out the page, it will try to keep the size intact, unless it breaks */
        grid-template-columns: 1fr 1fr 1fr 1fr;

        /* 5. If we want double the space of the other column */
        grid-template-columns: 2fr 1fr 1fr 1fr;

        /* 6. We can also spesify auto keyword instead. So if we tell auto in the last column, it will take exactly the size that is necessary to fill its content, and in practice, this is exactly what we need for one of the column*/
        grid-template-columns: 1fr 1fr 1fr auto;

        /* 7. We can also use repeat function to create columns repeat(number of column, size) */
        grid-template-columns: repeat(4, 1fr);

        /* 8. Suppose, we have 3 coulmns, so we will have automatically 3 rows, because , gril element is 8, so 3,3,2. 
        
        Now the first 2 rows are explixit row, as we have mentioned ther sise. But in the 3rd row, we have not defined any size and has been created automatically, so it becomes implicit row. And it will take the size of content only*/

        /* 9. ROWS : fr unit is also available for rows
        - If we have a height in amy css grid element, so by default it would be the height of all rows, of we use 1fr everywhere
        - If we do not have any height, biggest row with big content will be the height
        
        - So Can also specify height of container for making it more suitable for use as per our need*/
        height: 500px;
        grid-template-rows: repeat(2, 1fr);

        /* 10. We have auto keyword in rows also, so the auto css grid element will take the space it needs and all the remianing space is automatically filled up by first row track */
        grid-template-rows: 1fr auto;
      }

      .container--2 {
        display: none;
        /* STARTER */
        font-family: sans-serif;
        background-color: black;
        font-size: 40px;
        margin: 100px;

        width: 1000px;
        height: 600px;

        /* CSS GRID */
      }
    </style>
  </head>
  <body>
    <div class="container--1">
      <div class="el el--1">(1) HTML</div>
      <div class="el el--2">(2) and</div>
      <div class="el el--3">(3) CSS</div>
      <div class="el el--4">(4) are</div>
      <div class="el el--5">(5) amazing</div>
      <div class="el el--6">(6) languages</div>
      <div class="el el--7">(7) to</div>
      <div class="el el--8">(8) learn</div>
    </div>

    <div class="container--2">
      <div class="el el--1">(1)</div>
      <div class="el el--3">(3)</div>
      <div class="el el--4">(4)</div>
      <div class="el el--5">(5)</div>
      <div class="el el--6">(6)</div>
      <div class="el el--7">(7)</div>
    </div>
  </body>
</html>
```

## Placing and Spanning Grid Items (61)

- Untill now, we have basically let CSS grid decide where to place our items in a completely automatic way simply following the source HTML code.

- Sometimes we need to place elements manually in grid cell other than the predefined one

- Lets learn how

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS Grid</title>
    <style>
      .el--1 {
        background-color: blueviolet;
      }
      .el--2 {
        background-color: orangered;
      }
      .el--3 {
        background-color: green;
        height: 150px;
      }
      .el--4 {
        background-color: goldenrod;
      }
      .el--5 {
        background-color: palevioletred;
      }
      .el--6 {
        background-color: steelblue;
      }
      .el--7 {
        background-color: yellow;
      }
      .el--8 {
        background-color: crimson;
      }

      .container--1 {
        /* STARTER */
        font-family: sans-serif;
        background-color: #ddd;
        font-size: 40px;
        margin: 40px;

        display: grid;

        /* Gaps  */
        column-gap: 20px;
        row-gap: 20px;

        /* Colums & Rows */
        grid-template-columns: repeat(4, 1fr);
        grid-template-rows: repeat(2, 1fr);
      }

      /* 1. 🆕🆕 How to place a certain grid item into another grid cell, the 8th one into 2nd one. So basically placing grid cell that was not its default one
        
        Go to Dev Tools > Insteact > Turn on Grid > You will see, Cell, Gutters, Row, Columns, Grid Lines with number*/

      /* 2 */
      .el--8 {
        /* Statrt number / End Number */
        grid-column: 2/3;
        grid-row: 1/2;
      }

      .el--2 {
        grid-column: 1/2;
        grid-row: 2/3;
      }

      /* S P A N N I G */

      /* 3. We can have grid-item spent across multiple grid cells */
      .el--2 {
        /* So el2 will be spread to two columns as well */
        /* grid-column: 1/4; */
      }

      /* We can use span word */
      .el--2 {
        /* It is like, start from 1st cloumn and span across 3 cells */
        /* grid-column: 1 / span 3; */
      }

      /* In Some situation, we might not even know how many columns are there, in those situation, there is very nice trick that we can use instead of manually spanning one row for entire column */
      .el--2 {
        /* grid-column: 1/-1; */
      }

      /* Suppose we want spanning for rows */
      .el--6 {
        /* So we do not have 5, so it will create rows also */
        /* grid-row: 3 /5; */
      }

      .el--2 {
        /* grid-row: 1/-1; */

        /* Same */
        /* grid-row: 1 / span 2; */
      }

      /* We can place multiple element in same cell */
      .el--8 {
        grid-column: 1/2;
        grid-row: 2/3;
      }

      .container--2 {
        display: none;
        /* STARTER */
        font-family: sans-serif;
        background-color: black;
        font-size: 40px;
        margin: 100px;

        width: 1000px;
        height: 600px;

        /* CSS GRID */
      }
    </style>
  </head>
  <body>
    <div class="container--1">
      <div class="el el--1">(1) HTML</div>
      <div class="el el--2">(2) and</div>
      <div class="el el--3">(3) CSS</div>
      <div class="el el--4">(4) are</div>
      <div class="el el--5">(5) amazing</div>
      <div class="el el--6">(6) languages</div>
      <div class="el el--7">(7) to</div>
      <div class="el el--8">(8) learn</div>
    </div>

    <div class="container--2">
      <div class="el el--1">(1)</div>
      <div class="el el--3">(3)</div>
      <div class="el el--4">(4)</div>
      <div class="el el--5">(5)</div>
      <div class="el el--6">(6)</div>
      <div class="el el--7">(7)</div>
    </div>
  </body>
</html>
```

## Aligning Grid Items and Tracks (62)

Now just like an FlexBox, in CSS grid we als have the ability of aligining grid items. Lets now learn how that works

- Lets Work with Container 2

```css
/* New Topic  --  A L I G N I N G    G R I D    I T E M S*/
.el--3 {
  background-color: green;
  height: 150px;
}

.container--2 {
  /* STARTER */
  font-family: sans-serif;
  background-color: black;
  font-size: 40px;
  margin: 40px;

  width: 700px;
  height: 600px;

  /* CSS GRID */
  /* 1 */
  display: grid;
  /* Lets Create 3 By 2 Grid */
  grid-template-columns: 125px 200px 125px;
  grid-template-rows: 250px 100px;

  /* The Element 3 has 150 px height, that is why even the row height is 250, it is occupying 150 px,
        But for the Elemenet 1 & 4, both are following the defined 250 height */

  /* 2. Aligining grid items is a little bit different than it is in Flexbox, because
        -  we can align both the tracks inside the container
        -  we can aslo align the grid items inside of the tracks, Because sometimes the grid items are smaller than the cells that they are in */

  /* Let's now leanr aligning the grid tracks inside of the grid container. So basically the columns and rows inside of thr grid container

        This possible, because the grid items here is smaller than the grid container. We can see we have some empty space here*/

  /* 3 ALIGNING TRACKS INSDIE THE CONTAINER : Distributing empty space */
  /* It will make the entire track in the middle (Horizontally) inside of the container */
  justify-content: center;
  /* We can aslo use other values */
  /* justify-content: space-between; */

  /* Aligning vertically */
  align-content: center;
  /* align-content: end; */

  /* If we give gap, then all the tracks will have 50px gap */
  gap: 20px;

  /* Thats it for aliging tracks inside of the container */

  /* 4. ALIGNING THE ITEMS INSIDE THE CELLS : Moving items around inside the cell */
  /* By default it comes with stretch */
  align-items: center;
  justify-items: center;

  /* CONCLUSION : 
        
        1. The property ending with content, they are about aligning tracks inside of the container
        2.. The Property ending with item : They are about aligning items in the cell*/
}

/*5.  Overriding the ITEMS Property individually */
/* This is very good way for centering individual items in CSS Grid */
.el--3 {
  align-self: end;
  justify-self: end;
}
```

![Css grid 2](./asset_HTML_CSS/CSS%20Frid%202.jpg)

## Building a Simple CSS Grid Layout (63)

- Lets get back to our Page

- The idea is those things which are made of 1 dimensional, we will keep is as it i s with flexBox (Navigation, Author, in the related post)

- Only 2 dimension things we will chnage to CSS Grid, So the overall page layout is 2 dimensional

- So we have a big header, then we have a article, then the aside element (right side), finally we have a footer (all the way from the left to right side)

- **Alse there is a practice that we define the column value, and not the row value. So basically we want the biggest container should dictate the size of row**

```html
<div class="container">
  <header></header>
  <article></article>
  <aside></aside>
  <footer></footer>
</div>
```

```css
/* Overall page layout */
/* We will add article and aside element side by side */
/* First Question, what is the Flex Container */
/* We need to create a Flex Cntainer named ROW for article & aside */

/* 1. We have deactivated the row class, beacuse we want to do it with cssg rid */

/* FLEX BOX Layout */
/* .row {
  display: flex;
  gap: 75px;
  margin-bottom: 60px;

  align-items: flex-start;
} */

/* aside {
  flex: 0 0 300px;
} */
/* 
article {

  flex: 1;

  margin-bottom: 0;
} */

/* So we have a container , inside of which, we have mainheader, article, aside, and footer */

/* CSS Grid Layout */
.container {
  display: grid;
  grid-template-columns: 1fr 300px;
  column-gap: 75px;
  row-gap: 60px;
  align-items: start;
}

.main-header {
  grid-column: 1/-1;
  /* Removing Margin */
  margin-bottom: 0;
}

article {
  /* Remved Margin */
  margin-bottom: 0px;
}
aside {
  /* align-self: start; */
}

footer {
  /* background-color: #ffe70e; */
  grid-column: 1/-1;
}
```

## Challange #3 (64)

- Make the structure of the Html like this

```html
<article class="product">
  <h2 class="product-title">Converse Chuck Taylor All Star Low Top</h2>
  <img class=" class="product-img"">
  <div class="product-info"></div>
  <div class="product-details"></div>
  <button class="add-btn">Add to cart</button>
</article>
```

```css
* {
  margin: 0;
  padding: 0;
}

body {
  /* For inherited */
  font-family: sans-serif;
  line-height: 1.4;
}

/* PRODUCT */
.product {
  border: 5px solid black;
  width: 825px;

  margin: 50px auto;
  position: relative;
}

/* 1. Adding Before Pseudo Elements 🆕🆕 */
.product::before {
  content: "sale";
  font-weight: bold;
  text-transform: uppercase;
  background-color: #ec2f2f;
  padding: 7px 15px;
  font-size: 15px;
  /* text-align: center; */
  color: #f7f7f7;
  /* Letter Spacing 🆕🆕 Learnt */
  letter-spacing: 2px;

  position: absolute;
  top: -20px;
  left: -35px;
}

.product-title {
  background-color: #f7f7f7;
  text-transform: uppercase;
  text-align: center;
  font-size: 30px;
  padding: 15px;
}

/* PRODUCT INFORMATION */
.price {
  font-size: 24px;
}

.shipping {
  color: #777;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 12px;
  margin-bottom: 20px;
}

/* MORE INFO */

.more-info:link,
.more-info:visited {
  color: black;

  /* 🆕🆕Anchor Element is an inline block, so top & bottom margin will not work, so we are chnaging it to inline-block */
  display: inline-block;
  margin-bottom: 30px;
}
.more-info:hover,
.more-info:active {
  text-decoration: none;
}

.color {
  height: 22px;
  width: 22px;

  /* 🆕🆕We can not use inline, then height & width will not work,, So we are going with inline block */
  /* display: inline-block; */
  /* margin-right: 5px; */
}

.color-black {
  background-color: black;
}
.color-blue {
  background-color: blue;
}
.color-red {
  background-color: red;
}

.color-yellow {
  background-color: yellow;
}

.color-green {
  background-color: green;
}

.color-brown {
  background-color: brown;
}
/* PRODUCT DETAILS */

.details-title {
  text-transform: uppercase;
  font-style: 16px;
  margin-bottom: 15px;
  margin-top: 15px;
}

.details-list {
  margin-left: 20px;
}

.details-list li {
  margin-bottom: 15px;
}

/* Button */
.add-btn {
  background-color: black;
  color: #f7f7f7;
  border: none;
  font-size: 20px;
  text-transform: uppercase;
  cursor: pointer;

  padding: 15px;
  width: 100%;
  border-top: 5px solid black;
}

.add-btn:hover {
  background-color: white;
  color: black;
}

.row {
  display: flex;
  gap: 40px;
}

/* Product Price & Free Shipping */
.product-price {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
}

.shipping {
  /* Overriding the margin */
  margin-bottom: 0;
}

/* Product Colors */
.product-colors {
  display: flex;
  gap: 10px;
}

.product-info {
  flex: 1;
  /* margin-top: 10px; */
  /* margin-right: 40px; */
}

.product-details {
  flex: 1;

  /* margin-left: 10px; */
}

/* CSS GRID */

.product {
  display: grid;
  grid-template-columns: 250px 1fr 1fr;
  column-gap: 40px;
}
.product-title {
  /* Stretch */
  grid-column: 1/-1;
}

.product-img {
  /* Nothing to do here */
}

.product-info {
  justify-self: center;
  padding-top: 10px;
}

.product-details {
  justify-self: center;
  padding-right: 20px;
}

.add-btn {
  /* Stretch */
  grid-column: 1/-1;
}
```

**THE END**
**16-02-2024**
