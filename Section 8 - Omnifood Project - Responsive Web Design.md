# Omnifood Project - Responsive Web Design

## Section Intro (128)

- We have used fluid grids (max-width, View Post Height etc) & Responsive Unit (rem)

- Now we will make it full responsive, with media query...!!

## How Media Queries Work (129)

![Image](./asset_HTML_CSS/Screenshot%202024-03-10%20012223.png)

- We are going to learn how media query works with max-width property. Which is used in desktop first stretegy.

- In Mobile First Stretegy, there we use media query with min-width

- So media Query is a tool,for basically overriding specific parts of our css at certain viewport width.

---

- Copy the Desktop Version nad paste it to make another folder, so that we can do it from scratch..

Just an experiment

```css
/************************************/
/*  HERO Section */
/************************************/
.section-hero {
  background-color: #fdf2e9;
  padding: 4.8rem 0 9.6rem 0;
}

@media (max-width: 1200px) {
  .section-hero {
    background-color: red;
  }
}

@media (max-width: 600px) {
  .section-hero {
    border: 20px dashed blueviolet;
    background-color: blue;
  }
}

.hero {
  max-width: 130rem;
  margin: 0 auto;
  padding: 0 3.2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 9.6rem;
  align-items: center;
}
```

## How to select breakpoints (130)

- What is break point? Breakpoint are the view port width at which we want or designed to change. In other words, breakpoints are the pixel values that we want to put in all media queires.

![Image](./asset_HTML_CSS/Screenshot%202024-03-10%20012249.png)

- So we will go with Perfect & Good Stretegy combined

## Responding to Small Laotops (131)

1. Before we do anything with Media Query, Make sure, in the head of HTML, we have this meta tag

` <meta name="viewport" content="width=device-width, initial-scale=1.0" />`

- This is very crucial. It comes with boiler plate. But incase you have missed, please write it down

- Without this meta tag, responsive design will not work in physical mobile devices. So basically it will not zoom out the page to fit on the screen. So it will take device width, initial scale set to 1

---

2. We will create a new file for media query.

- `queries.css`
- Also we need add it in our html

```html
<link rel="stylesheet" href="./css/general.css" />
<link rel="stylesheet" href="./css/style.css" />
<link rel="stylesheet" href="./css/queries.css" />
```

- So Basically Now put the Css in One Window & Query in one window

- Currently we are going with Desktop to Mobile, So the Initial all css are written for big window. So in Queries, we are using max-width in query

- If we were to made it opposite, like from mobile approach to desktop. Then initially we would have written it in Mobile Size, then in query, we would write in Min-width

```css
/* So lets Start Our Media Queries
and for that,  we need our breakpoints. SO basically the width at which we want to set the media queries


So we will go with the two stretigies
So basically looking where our design breaks and also taking into account common screen ranges
*/

/* rem and em do Not  depend on html font-size in media queries! 
Instead, 1rem = 1 em = 16px 


rem = root font size
em = current font size

rem has some bugs in Media Queries, so we should use em. And it is safer, and works exactly same like rem
*/

/* We will go with 1350 px first
So We divide it with 16, 1350/16 = 84.375

So our first media query will fire at 1344 px*/

/************************************/
/*  Below 1344 Px - Smaller Monitor : (84 x 16 = 1344) */
/************************************/

@media (max-width: 84em) {
  .hero {
    max-width: 120rem;
  }

  .heading-primary {
    font-size: 4.4rem;
  }

  /* We need to Make the Gallery in two column*/
  .gallery {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* 
-FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98 

- SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128
*/
```

## Responding to Landscape Tablets (132)

```css
/* 
-FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98 

- SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128
*/

/* So Now we will go for 1200.
So we observe the space it bit more, and font size also more

1200/16 = 75 */
/************************************/
/*  Below 1200px (Lanscape Tablet)
/************************************/
@media (max-width: 75em) {
  /* Lets fix the overall feeling of everything is being too big.

  How do we do that?

  So basically we can take advantage the fact that we used responsive units from th very start. So every thing will work here because we have already have the other 3 web disiging responsive units already in place. So already we have a fluid grid, responsive images & responsive units. Other wise non of it would have worked at all.

  */
  html {
    /* So we are dependent on REM for size of any kind, so this was our first technique to keep everything in REM, so that we can control the whole size of it at any point */

    /* So we have 10 PX currently, we want it to be 9 px, So , Therefore, 9/16=56.25% */
    /* font-size: 9px; */
    font-size: 56.25%;
  }

  .grid {
    column-gap: 4.8rem;
    row-gap: 6.4rem;
  }

  .heading-secondary {
    font-size: 3.6rem;
  }

  .heading-tertiary {
    font-size: 2.4rem;
  }

  /* For making the Logo and the Header in Hero Box aligned*/
  .header {
    padding: 0 3.2rem;
  }

  /* Gap between Links in Nav */
  .main-nav-list {
    gap: 3.2rem;
  }

  /* Fixing the Grid Gap in Hero Section */
  .hero {
    gap: 3.2rem;
  }

  /* Fixing the testimonail */
  .testimonial-container {
    padding: 9.6rem 3.2rem;
  }
}
```

## Responding to Tablets (132)

- A rule of Thumb, A Media Query should work over a range of atleast 200 or 300 pixels.

- As I have already Mentioned, We should not add Media Query on every 50 pixel to fix every single design problem that appears as we scale down the page.

- Lets analyze 300 pixer down, so starting from 900. and will make it work from 900px-700px at least

```css
/* From 940, we are going to make a media query */
/************************************/
/*  Below 944px (Tablet) : 940/16 = 58.75
/************************************/

@media (max-width: 59em) {
  html {
    /* wewant font size to be 8px
     8px/16px= 0.5*/
    font-size: 50%;
  }

  /* But if we make it little small resolution, it gets problem for reading
  
  
  So we will make one column view*/

  .hero {
    grid-template-columns: 1fr;
    padding: 0 8rem;
    gap: 6.4rem;
  }

  .hero-text-box,
  .hero-img-box {
    text-align: center;
  }

  .hero-img {
    width: 60%;
  }
  .delivered-meals {
    justify-content: center;
    margin-top: 3.2rem;
  }

  /* Making the Social Media Logo little less size */
  .logos img {
    height: 2.4rem;
  }

  /* Making the step number little small */
  .step-number {
    font-size: 7.4rem;
  }

  /* Meal Content Padding re-arrangement */
  .meal-content {
    padding: 2.4rem 3.2rem 3.2rem 3.2rem;
  }

  /* Testimonial, we will make it as one column */
  .section-testimonials {
    grid-template-columns: 1fr;
  }
  .gallery {
    grid-template-columns: repeat(6, 1fr);
  }

  /* Making the CTA > Form on one column */
  .cta {
    /* 3/5 = 60%  + 2/5 = 40% 
    Form (60%) + Image (40%) */
    grid-template-columns: 3fr 2fr;
  }

  .cta-form {
    grid-template-columns: 1fr;
  }

  .btn--form {
    margin-top: 1.2rem;
  }
}
```

## Building the Mobile Navigaation (134)

```html
<!-- Addeda nav-open class for JavaScript -->
<header class="header nav-open">
  <a href="#">
    <img class="logo" alt="Omnifood logo" src="img/omnifood-logo.png" />
  </a>
  <nav class="main-nav">
    <ul class="main-nav-list">
      <li><a class="main-nav-link" href="#">How it works</a></li>
      <li><a class="main-nav-link" href="#">Meals</a></li>
      <li><a class="main-nav-link" href="#">Testimonials</a></li>
      <li><a class="main-nav-link" href="#">Pricing</a></li>
      <li><a class="main-nav-link nav-cta" href="#">Try for free</a></li>
    </ul>
  </nav>

  <!-- 1. Adding one button with two icons -->
  <button class="btn-mobile-nav">
    <!-- 1st one is hamberger icon -->
    <ion-icon name="grid-outline" class="icon-mobile-nav"></ion-icon>
    <!-- 2nd one is close icon -->
    <ion-icon name="close-outline" class="icon-mobile-nav"></ion-icon>
  </button>
</header>
```

![image](./asset_HTML_CSS/Screenshot%202024-03-12%20173950.png)

Styles.css

```css
/************************************/
/* Header */
/************************************/
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #fdf2e9;
  height: 9.6rem;
  padding: 0 4.8rem;

  /* 🆕🆕Positon : Doing for animation only when we want it to overflow-x : none */
  position: relative;
}

.logo {
  height: 2.2rem;
}

/************************************/
/*Navigation*/
/************************************/

.main-nav-list {
  list-style: none;
  display: flex;
  align-items: center;
  gap: 4.8rem;
}

.main-nav-link:link,
.main-nav-link:visited {
  display: inline-block;
  text-decoration: none;
  color: #333;
  font-weight: 500;
  font-size: 1.8rem;
  transition: all 0.3s;
}

.main-nav-link:hover,
.main-nav-link:active {
  color: #cf711f;
}

/* Using and operator
We are creating a call to action in nav*/
.main-nav-link.nav-cta:link,
.main-nav-link.nav-cta:visited {
  padding: 1.2rem 2.4rem;
  border-radius: 9px;
  color: #fff;
  background-color: #e67e22;
}

.main-nav-link.nav-cta:hover,
.main-nav-link.nav-cta:active {
  background-color: #cf711f;
}

/* MOBILE 🆕🆕 */
.btn-mobile-nav {
  border: none;
  background: none;
  cursor: pointer;
  /* By Default, for normal width, it is not shown we want it to be hidden */
  display: none;
}
.icon-mobile-nav {
  height: 4.8rem;
  width: 4.8rem;
  color: #333;
}

/* 
 <ion-icon name="grid-outline" class="icon-mobile-nav"></ion-icon>
 <ion-icon name="close-outline" class="icon-mobile-nav"></ion-icon>
*/

/* 🆕🆕To select on the based on attribute */
/* For the initial time, close button to be disabled */
.icon-mobile-nav[name="close-outline"] {
  display: none;
}
```

![image](./asset_HTML_CSS/Screenshot%202024-03-12%20175122.png)
![image](./asset_HTML_CSS/Screenshot%202024-03-12%20175204.png)

query.css

```css
/* From 940, we are going to make a media query */
/************************************/
/*  Below 944px (Tablet) : 940/16 = 58.75
/************************************/

@media (max-width: 59em) {
  html {
    /* wewant font size to be 8px
     8px/16px= 0.5*/
    font-size: 50%;
  }

  /* But if we make it little small resolution, it gets problem for reading
  
  
  So we will make one column view*/

  .hero {
    grid-template-columns: 1fr;
    padding: 0 8rem;
    gap: 6.4rem;
  }

  .hero-text-box,
  .hero-img-box {
    text-align: center;
  }

  .hero-img {
    width: 60%;
  }
  .delivered-meals {
    justify-content: center;
    margin-top: 3.2rem;
  }

  /* Making the Social Media Logo little less size */
  .logos img {
    height: 2.4rem;
  }

  /* Making the step number little small */
  .step-number {
    font-size: 7.4rem;
  }

  /* Meal Content Padding re-arrangement */
  .meal-content {
    padding: 2.4rem 3.2rem 3.2rem 3.2rem;
  }

  /* Testimonial, we will make it as one column */
  .section-testimonials {
    grid-template-columns: 1fr;
  }
  .gallery {
    grid-template-columns: repeat(6, 1fr);
  }

  /* Making the CTA > Form on one column */
  .cta {
    /* 3/5 = 60%  + 2/5 = 40% 
    Form (60%) + Image (40%) */
    grid-template-columns: 3fr 2fr;
  }

  .cta-form {
    grid-template-columns: 1fr;
  }

  .btn--form {
    margin-top: 1.2rem;
  }

  /* MOBILE NAVIGATION 🆕🆕 */
  /* 1. SO Basically when we reach 944px break point, we want the button Visibility */
  .btn-mobile-nav {
    display: block;
  }

  /* 2. We want the main nav get positioned absolutely, when the screen is small. Like an Overlay */
  .main-nav {
    background-color: rgba(232, 232, 237, 0.928);

    /* Make it absoutely Positioned */
    position: absolute;
    top: 0;
    left: 0;

    /* Now make the height and width 100% for occupying the whole screen */
    height: 100vh;
    width: 100%;

    display: flex;
    align-items: center;
    justify-content: center;

    /*6.  For Sliding Animation */
    /* We use TranslateX a00%, means it will move to 100% horizontally right side
    Basically it will move the emelemt out of the screen completely by its own width, that is 100% */
    transform: translateX(100%);
    /* Transition Property : OnWhichProperty Duration TypeOfAnimation */
    transition: all 0.5s ease-in;

    /* Hiding the Navigation */
    /* if we use display : None, >> Allows no transition/animation at all */
    /* display: none; */
    /* For getting animation and also having the Display none function we, can use another trick */

    /* A. Hide it Visually */
    opacity: 0;

    /* B. Make it unaccessable to mouse & keyboard :, Just in case if user clickes on Tab Key. In the case of Display : none, we do not get the issue, but with opacity, we do not hide it, instead make it invisible, that means the Elemenet remians*/
    pointer-events: none;

    /* C. Hide ot from the screen reader */
    visibility: hidden;

    /* ☝️ This is the correct way to hide a element without using display: none */
  }

  /*3. Adding a extra class to decide the behaviour of Nav, when it is open, which will be controlled by JS, so basically state chnage 
   O V E R R I D I N G -- MAIN NAV
  */
  .nav-open .main-nav {
    opacity: 1;
    pointer-events: auto;
    visibility: visible;
    /*7.For animation  */
    transform: translateX(0);
  }
  /* 4. O V E R R I D I N G Icons visibility when state is OPEN & nav-open is available */
  .nav-open .icon-mobile-nav[name="close-outline"] {
    display: block;
  }
  /* 5. Hiding the hamberger, when nav-open is available  */
  .nav-open .icon-mobile-nav[name="grid-outline"] {
    display: none;
  }

  /* 2.1 For making the List Like a Stack */
  .main-nav-list {
    flex-direction: column;
    gap: 4.8rem;
  }
  .main-nav-link:link,
  .main-nav-link:visited {
    font-size: 3rem;
  }
}
```

- For making the sliding works, we need to restrict that the right side element which is overflowing must be invisible

general.css

```css
html {
  /* font-size: 10px; */
  font-size: 62.5%;

  /* Any Element which is overflowing the viewport of x-axis horizantally will be hidden*/
  overflow-x: hidden;
}

body {
  font-family: "Rubik", sans-serif;
  line-height: 1;
  font-weight: 400;
  color: #555;

  /* Any Element which is overflowing the viewport of x-axis horizantally will be hidden*/
  /* It works when nothing absolutely positioned in relation to body */
  overflow-x: hidden;
}
```

- Also we for making it happen, we need to make the Nav element positoned relative to parent element, here it is Header. Else it will not work

```css
/* Style.css */
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #fdf2e9;
  height: 9.6rem;
  padding: 0 4.8rem;

  /* 🆕🆕Positon : Doing for animation only when we want it to overflow-x : none */
  position: relative;
}
```

![image](./asset_HTML_CSS/Screenshot%202024-03-12%20183640.png)

![image](./asset_HTML_CSS/Screenshot%202024-03-12%20183716.png)

WHAT WE LEARNED?

- overflox-x (for restricting anything overflowing from the viewport in x axis)
- transformation : translate(100%) ....or translate(0)
- transition : all 0.5 (typeofAnimation Easein, easeout etc)
- Selection of element based on their attribute
- How to hide any element without display property, as it does not work with transition property

```css
/* A. Hide it Visually */
opacity: 0;

/* B. Make it unaccessable to mouse & keyboard*/
pointer-events: none;

/* C. Hide ot from the screen reader */
visibility: hidden;
```

---

## Responding to Smaller Tablets (135)

- Now we are targetting from 700px width. We have noticed, all the column started to look so much thin

![image](./asset_HTML_CSS/Screenshot%202024-03-12%20184157.png)

- So we need to make some column size chnage, so the first two meal in one row, and diet in other row etc...

- After making all as 2 column, we get an issue

![img](./asset_HTML_CSS/Screenshot%202024-03-13%20085309.png)

- So To fix the diet List, we need to do some trick

![img](./asset_HTML_CSS/Screenshot%202024-03-13%20085626.png)

---

Also footer, we need to make it 6 column, and then each upper row element span 2 column, and last line row should span 3 column

![img](./asset_HTML_CSS/Screenshot%202024-03-13%20121418.png)

```css
/* From 700 , we are going to make a media query */
/************************************/
/*  Below 700px (Smaller Tablet) : 700/16 = 43.75
/************************************/

@media (max-width: 44em) {
  /* Whatever we have 4 columns , or 3 Columns to 2 Colums only */
  .grid--3-cols,
  .grid--4-cols {
    grid-template-columns: repeat(2, 1fr);
  }

  /* As the dirt box does not look correct, we have to stretch upto last */
  .diets {
    grid-column: 1/-1;
    justify-self: center;
  }

  /* Decreasing the heading secondary margin botton*/
  .heading-secondary {
    margin-bottom: 4.8rem;
  }

  /* Pricing Table also getting shrinked, we mave made its width 75% earlier, now its time to make its width 100% */
  .pricing-plan {
    width: 100%;
  }

  /* Footer we need to improve. We need to put last 3 cloumn first row, and the 2nd 2 row in last column .*/
  .grid--footer {
    grid-template-columns: repeat(6, 1fr);
  }
  /* All nav col, putting them in 1st row as discussed */
  .nav-col {
    grid-row: 1;
    grid-column: span 2;
    margin-bottom: 3.2rem;
  }
  .logo-col,
  .address-col {
    grid-column: span 3;
  }
}
```

## Responding to Phones (136)

- Now we need to take care of Smaller phones

- For Mobile, general media query is 600px

- After seeing all this things we decided to have breakpoint at 550px

![image](./asset_HTML_CSS/mobile.gif)

```css
/* From 544 , we are going to make a media query */
/************************************/
/*  Below 544px (Mobile) : 544/16 = 34
/************************************/
@media (max-width: 34em) {
  /* From Now onwards, every thing will have only one column */

  .grid {
    row-gap: 4.8rem;
  }
  .grid--2-cols,
  .grid--3-cols,
  .grid--4-cols {
    grid-template-columns: 1fr;
  }

  /* White space below & at the end */

  .section-hero {
    padding: 2.4rem 0 6.4rem 0;
  }

  /* Padding of left/right side */
  .hero {
    padding: 0 3.2rem;
  }

  /* Make the button but small */
  .btn,
  .btn:link,
  .btn:visited {
    padding: 2.4rem 1.6rem;
  }

  /* Make the image big */
  .hero-img {
    width: 80%;
  }

  /* Make the Logo of Featured in Little samll */
  .logos img {
    height: 1.2rem;
  }

  /* Now HOW IT WORSK SECTION, MObile Image & Text is not in proper order
  We need to fix it manually */

  .step-img-box:nth-child(2) {
    grid-row: 1;
  }

  .step-img-box:nth-child(6) {
    grid-row: 5;
  }
  /* We need to put the Mobile Image closer to text */
  .step-img-box {
    transform: translateY(3.4rem);
  }

  /* Testimonaial Need to make one column */
  .testimonials {
    grid-template-columns: 1fr;
  }
  /* Image of Gallry need to make 4X3 */
  .gallery {
    grid-template-columns: repeat(4, 1fr);
    gap: 1.2rem;
  }

  /* CTA Need to make 2 Column */
  .cta {
    grid-template-columns: 1fr;
  }

  /* As the Image Divison has no height, as we have used background-image, So we need to give a height */
  .cta-img-box {
    height: 32rem;
    grid-row: 1;
  }

  .cta-text-box {
    padding: 3.2rem;
  }
}
```

**The End**
