# Omnifood Project - Setup & Desktop Version

## Section Intro (99)

- We will learn Theory and Practical

## The 7 Steps to a Great Website (100)

[Page 353-360](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

1. Define : Who the Website for? What the website is for (Business & User Goal)? Target Audience? Extra : Competition Research, User Persona.
2. Plan : Website Content (Text, images, videos). Plan out the Sitemap, Plan Out the Sections, Website Personality
3. Sketch : Components & Layout Patterns. Draw with Pen & Paper.
4. Design & Build
5. Test & Optimize
6. Lunch
7. Maintain & Update

## Defining and Planning the Project (Steps 1 and 2) (101)

[Page 362-365](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Sections :

- Logo+Navigation
- Hero Section
- Featured In (Social Proof)
- How it works
- Meals (and list of Diets)
- Gallery and (Testimonial)
- Pricing & Features
- CTA
- Footer

## Sketching Initial Layout Ideas (Step 3) (102)

![Image](./asset_HTML_CSS/Screenshot%202024-03-03%20190037.png)

## First Design & Development Steps (Steps 4) (103)

- Uiface.com, unsplash.com - We get images for free

- Created Folder for CSS also

```css
/*

---- 01 Typography system
-FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98

- Font-Weights : Default 400

- Line Heights : 1




--- 02 Colors

- Main Color : #e67e22
- Tint
- Shades
- Accents
- Grey : #555


--- 03 Images
- Unsplash
- uifaces
- We have already though all required images

--- 04 Shadows


--- 05 Border Radius


--- 06 White Space

- SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  line-height: 1;
  font-weight: 400;
  color: #555;
}
```

## Responsive Design Pronciples (104)

![image](./asset_HTML_CSS/Screenshot%202024-03-03%20200506.png)
![image](./asset_HTML_CSS/Screenshot%202024-03-03%20200530.png)
![image](./asset_HTML_CSS/Screenshot%202024-03-03%20200549.png)

## How rem & max-width Work (105)

```css
.test {
  /* If we use Width, it will make additional Width if the screen in small. By a Horizontal scroll */
  /* It will create a Horizontal Scroll */
  /* width: 1000px; */

  /* If we want that - If there is no more additional space to fit these thousan pixels here, then theelement should simply have the width of the parent containner */
  /* So when we had 1000 px width, we wanted it. And when we have less then 1000 px, i want it to take up the width of parent container. So No Horizontal Scrolling */

  /* Summary : if the container width is larger then the specified max-width, then the width of the element is equal to the value that was specified for max-width. However if the container width is less than the specified max-width, then the width of the element will be 100% of the container element width.*/
  /* max-width: 1000px; */

  /* REM : Root Element for Fontsize
  So the Root of the document is the HTML element. So bacially the parent elemenet of all the others 
  
  Now if we do not define any font size on the HTML element, which is again the root element, then one rem is simply equal to the default browser font size, which is always 16 px, unless the user does actually chnage it*/

  /* max-width: 50rem; */
  /* By Default : 1 rem == 16px, that because we have not specified any font size in HTML element, so therefore the default font size of 16 is taken
  
  50 rem == 800px*/

  /* You might find it strange that we define length in our design basedon some font size. But actually that is exactly where the strength of remm unit lies. Then we can simply chnage the font size on the HTML element, then it will automatically chnage all the length that are defined anywhere in our CSS with the rem unit */

  max-width: 50rem; /*800px*/
  color: aliceblue;
  font-size: 2rem; /*32px*/
  padding: 4rem; /*64px*/

  background-color: red;
}

html {
  /* Now if we chnage fontsize to 10px, then all 1 rem will become 10px */
  /* font-size: 10px; */
}

/* So by chnaging the font size, we can chnage the entire layout */

/* 
So it is very handly when dealing with smaller screen, then we want all the length a little bit smaller. Then instead of chnaging all of these  value individually using media quaries, we can simply chnage the font size up here, in the Html, then it will shrink down everything a little bit */

/* T R I C K S */
/* An useful trick to make the font-size to 10px for easy calculation 
So 1 rem will be exactly 10px*/

/* Now This approach is not perfect. Because by doing it like this we will not respect the user's defination of the browser font size. So lets say user chnage browser font size from 16px to 20px, then they would expect the font size in our page would increase. But with this setup : font-size : ...px, it will not happen. No matter what the user would set the font size in browser to now, we will have always the defult font size/root font size here at 10 pixel

And this would create a huge usubility problem who some reason have to increase or even to decrease the font size of the browser

So to avoid that we will not set a fixed value like this 
html {
  font-size: 10px;
} 

instead to a percentage of the default font size of the browser 
html {
  font-size: 62.5%;
} 

*/

html {
  /* So we want 10px, but to achieve
  10px/16px = 0.625 = 62.5%
  
  
  Percentage of user's browser font size setting*/
  font-size: 62.5%;
}
```

## Building the Hero - Part 1 (106)

![image](./asset_HTML_CSS/Screenshot%202024-03-04%20080359.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <link rel="stylesheet" href="./css/style.css" />

    <title>Omnifood</title>
  </head>
  <body>
    <section class="secton-hero">
      <div class="hero">
        <div class="hero-text-box">
          <h1 class="heading-primary">
            A healthy meal delivered to your door, every single day
          </h1>
          <p class="hero-description">
            The smart 365-days-per-year food subscription that will make you eat
            healthy again. Tailored to your personal tastes and nutritional
            needs. We have delivered 250,000+ meals last year!
          </p>
          <a href="#" class="btn">Start eating well</a>
          <a href="#" class="btn">Learn more &darr; </a>
        </div>

        <div class="hero-img-box">
          <img
            src="./img/hero.png"
            alt="Woman enjoying food, meals in storgae container and food bowls on a table"
            class="hero-img"
          />
        </div>
      </div>
    </section>
  </body>
</html>
```

```css
/*

---- 01 Typography system
-FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98

- Font-Weights : Default 400

- Line Heights : 1




--- 02 Colors

- Main Color : #e67e22
- Tint
- Shades
- Accents
- Grey : #555


--- 03 Images
- Unsplash
- uifaces
- We have already though all required images

--- 04 Shadows


--- 05 Border Radius


--- 06 White Space

- SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  /* font-size: 10px; */
  font-size: 62.5%;
}

body {
  font-family: sans-serif;
  line-height: 1;
  font-weight: 400;
  color: #555;
}

.hero {
  max-width: 130rem;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.hero-img {
  width: 100%;
}
```

![image](./asset_HTML_CSS/Screenshot%202024-03-04%20082324.png)

## Building the Hero - Part 2 (107)

- Lets Start with styling the text > Color, Size, Line Height, letter space

- Then make the Layout Perfect

- Then we do the Link Element

- As linnks Box have different color, we added different class also, one if fill(for CTA), one is outline(Learn more)

- We added a shadow inside (to make border inside)

- We learnet transition

- TO get tint & shades, of the main color, go to `maketintandshades.com` and paste the main color

Some Extra Tricks :

```css
.btn--outline:hover,
.btn--outline:active {
  background-color: #fdf2e9;

  /* 🆕🆕 Adding Border inside of the button.
  If we add border simply, it will add at the outisde of the button, so it will make the button size little big */

  /* border: 3px solid #fff; */

  /* T R I C K  to add border inside */
  /* So we add white color of shadow, of 3px scale. 
  Here we do not give x,y, blur value. 
  
  And Also we add inset Keyword, so with inset, the shadow will be added inside of the element
  
  The Inset keyword do not work with box-border, that is why we need to use box-shadow trick*/
  box-shadow: inset 0 0 0 3px #fff;
}

.btn:link,
.btn:visited {
  font-size: 2rem;

  text-decoration: none;
  display: inline-block;
  padding: 1.6rem 3.2rem;
  border-radius: 9px;

  /* 🆕🆕 TO make the transition little bit more animated */
  /* So transition Property : To Transit two value in animtion 
  We need to specify which property we want to animate & duration of animation time
  
  So we want backgrounf color & the color to animate
  Also in 3rd value, we can add the type of animation. But we will leave it for later*/
  /* transition: all 1s; */
  transition: background-color 0.5s;
}

/* We added a Helper Class, and we want it applied, no matter other style on the element, so we add important keyword
We will use it in many places */
.margin-right-sm {
  margin-right: 1.6rem !important;
}
```

![image](./asset_HTML_CSS/Screenshot%202024-03-04%20191140.png)

```css
/*

---- 01 Typography system
-FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98

- Font-Weights : Default 400

- Line Heights : 1




--- 02 Colors

- Main Color : #e67e22
- Tint ##fdf2e9;
- Shades ; #cf711f;
- Accents
- Grey : #555 , #333


--- 03 Images
- Unsplash
- uifaces
- We have already though all required images

--- 04 Shadows


--- 05 Border Radius


--- 06 White Space

- SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  /* font-size: 10px; */
  font-size: 62.5%;
}

body {
  font-family: sans-serif;
  line-height: 1;
  font-weight: 400;
  color: #555;
}

.section-hero {
  background-color: #fdf2e9;
  padding: 9.6rem 0;
}
.hero {
  max-width: 130rem;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 9.6rem;
  align-items: center;
}
.heading-primary {
  font-size: 5.2rem;
  font-weight: 700;
  line-height: 1.05;
  color: #333;
  letter-spacing: -0.5px;
  margin-bottom: 3.2rem;
}

.hero-description {
  font-size: 2rem;
  line-height: 1.6;
  margin-bottom: 4.2rem;
}

.btn:link,
.btn:visited {
  font-size: 2rem;

  text-decoration: none;
  display: inline-block;
  padding: 1.6rem 3.2rem;
  border-radius: 9px;

  /* 🆕🆕 TO make the transition little bit more animated */
  /* So transition Property : To Transit two value in animtion 
  We need to specify which property we want to animate & duration of animation time
  
  So we want backgrounf color & the color to animate
  Also in 3rd value, we can add the type of animation. But we will leave it for later*/
  /* transition: all 1s; */
  transition: background-color 0.5s;
}

.btn--full:link,
.btn--full:visited {
  background-color: #e67e22;
  color: #fff;
}

.btn--full:hover,
.btn--full:active {
  background-color: #cf711f;
  /* background-color: red; */
}

.btn--outline:link,
.btn--outline:visited {
  background-color: #fff;
  color: #555;
}

.btn--outline:hover,
.btn--outline:active {
  background-color: #fdf2e9;

  /* 🆕🆕 Adding Border inside of the button.
  If we add border simply, it will add at the outisde of the button, so it will make the button size little big */

  /* border: 3px solid #fff; */

  /* T R I C K  to add border inside */
  /* So we add white color of shadow, of 3px scale. 
  Here we do not give x,y, blur value. 
  
  And Also we add inset Keyword, so with inset, the shadow will be added inside of the element
  
  The Inset keyword do not work with box-border, that is why we need to use box-shadow trick*/
  box-shadow: inset 0 0 0 3px #fff;
}

.hero-img {
  width: 100%;
}

/* We added a Helper Class, and we want it applied, no matter other style on the element, so we add important keyword */
.margin-right-sm {
  margin-right: 1.6rem !important;
}
```

## Building the Hero - Part 3 (108)

- We need a typeface : Google Font > Inter, Rubik (Little roundy in edge)

- So we chose Rubik, and not inter. We keep experimenting the typefaces

- we have updated some font typeface & font weight in button

- So bottom of the button, we will add some faces of user, for this we create a div & class = "delivered-melas"

- I used flex, instead of grid. Here we do not care about the size of the column, We simply want the content determine the size

- Also after using the Images, we want them to overlap. So to do that, we can not use gap property of flex, as it will not work. Instead we can use individual margin with negetive value. Also we have added some border

- Also we have higlighted the Delevered Number. but to check whether the color with good contrast, we checked the color in `coolors.com`

```css
/* Delivered imgs */
.delivered-meals {
  display: flex;
  margin-top: 8rem;

  align-items: center;
  gap: 1.6rem;
}

.delivered-imgs {
  display: flex;
}

.delivered-imgs img {
  height: 4.8rem;
  width: 4.8rem;
  border-radius: 50%;
  margin-right: -1.6rem;
  border: 3px solid #fdf2e9;
}

.delivered-imgs img:last-child {
  margin: 0;
}

.delivered-text {
  font-size: 1.8rem;
  font-weight: 600;
}

.delivered-text span {
  color: #cf711f;
  font-weight: 700;
}
```

```html

  <!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&family=Rubik:ital,wght@0,300..900;1,300..900&display=swap"
      rel="stylesheet"
    />

    <link rel="stylesheet" href="./css/style.css" />

    <title>Omnifood</title>
  </head>
  <body>
    <section class="section-hero">
      <div class="hero">
        <div class="hero-text-box">
          <h1 class="heading-primary">
            A healthy meal delivered to your door, every single day
          </h1>
          <p class="hero-description">
            The smart 365-days-per-year food subscription that will make you eat
            healthy again. Tailored to your personal tastes and nutritional
            needs.
          </p>
          <a href="#" class="btn btn--full margin-right-sm"
            >Start eating well</a
          >
          <a href="#" class="btn btn--outline">Learn more &darr; </a>
          <!-- 🆕🆕🆕 -->
          <div class="delivered-meals">
            <div class="delivered-imgs">
              <img src="./img/customers/customer-1.jpg" alt="customer photo">
              <img src="./img/customers/customer-2.jpg" alt="customer photo">
              <img src="./img/customers/customer-3.jpg" alt="customer photo">
              <img src="./img/customers/customer-4.jpg" alt="customer photo">
              <img src="./img/customers/customer-5.jpg" alt="customer photo">
              <img src="./img/customers/customer-6.jpg" alt="customer photo">

            </div>
            <p class="delivered-text">
              <span>250,000+</span> meals  delivered last year!
            </p>
        </div>
      </div>
        <div class="hero-img-box">
          <img
            src="./img/hero.png"
            alt="Woman enjoying food, meals in storgae container and food bowls on a table"
            class="hero-img"
          />
        </div>

    </section>
  </body>
</html>

```

![image](./asset_HTML_CSS/Screenshot%202024-03-04%20220140.png)

## Building the Header (109)

- We have used header, nav

- We used main element, for containing all the section. We exclude header & footer

- We have made some division in Css, for general & specific declaration

```css
/*

---- 01 Typography system
-FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98

- Font-Weights : Default 400

- Line Heights : 1




--- 02 Colors

- Main Color : #e67e22
- Tint ##fdf2e9;
- Shades ; #cf711f; 
- Accents
- Grey : #555 , #333


--- 03 Images
- Unsplash
- uifaces
- We have already though all required images

--- 04 Shadows


--- 05 Border Radius


--- 06 White Space

- SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  /* font-size: 10px; */
  font-size: 62.5%;
}

body {
  font-family: "Rubik", sans-serif;
  line-height: 1;
  font-weight: 400;
  color: #555;
}

/************************************/
/* General Reusable Components */
/************************************/
.heading-primary {
  font-size: 5.2rem;
  font-weight: 700;
  line-height: 1.05;
  color: #333;
  letter-spacing: -0.5px;
  margin-bottom: 3.2rem;
}

.btn:link,
.btn:visited {
  font-size: 2rem;
  font-weight: 600;
  text-decoration: none;
  display: inline-block;
  padding: 1.6rem 3.2rem;
  border-radius: 9px;
  transition: background-color 0.5s;
}

.btn--full:link,
.btn--full:visited {
  background-color: #e67e22;
  color: #fff;
}

.btn--full:hover,
.btn--full:active {
  background-color: #cf711f;
  /* background-color: red; */
}

.btn--outline:link,
.btn--outline:visited {
  background-color: #fff;
  color: #555;
}

.btn--outline:hover,
.btn--outline:active {
  background-color: #fdf2e9;

  box-shadow: inset 0 0 0 3px #fff;
}

.margin-right-sm {
  margin-right: 1.6rem !important;
}

/************************************/
/* Header */
/************************************/
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #fdf2e9;
  /* 🟢🔴We are giving height to the header, but usually we allow the content to define the height & adding some padding usually. But in this case, we want the navigation a sticky navigation. So that is why we are giving fixed height*/
  height: 9.6rem;
  padding: 0 4.8rem;
}

.logo {
  height: 2.2rem;
}

/************************************/
/*  HERO Section */
/************************************/
.section-hero {
  background-color: #fdf2e9;
  padding: 4.8rem 0 9.6rem 0;
}
.hero {
  max-width: 130rem;
  margin: 0 auto;
  /* 🔴🔴🟢🟢Adding padding, as we want to have some size in the left & right if screen os small */
  padding: 0 3.2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 9.6rem;
  align-items: center;
}

.hero-description {
  font-size: 2rem;
  line-height: 1.6;
  margin-bottom: 4.2rem;
}

.hero-img {
  width: 100%;
}

.delivered-meals {
  display: flex;
  margin-top: 8rem;

  align-items: center;
  gap: 1.6rem;
}

.delivered-imgs {
  display: flex;
}

.delivered-imgs img {
  height: 4.8rem;
  width: 4.8rem;
  border-radius: 50%;
  margin-right: -1.6rem;
  border: 3px solid #fdf2e9;
}

.delivered-imgs img:last-child {
  margin: 0;
}

.delivered-text {
  font-size: 1.8rem;
  font-weight: 600;
}

.delivered-text span {
  color: #cf711f;
  font-weight: 700;
}
```

```html
<body>
  <!-- 🆕🆕 -->
  <header class="header">
    <img class="logo" alt="Omnifood logo" src="img/omnifood-logo.png" />
    <nav class="main-nav">Navigation</nav>
  </header>
  <main>
    <section class="section-hero">
      <div class="hero">
        <div class="hero-text-box">
          <h1 class="heading-primary">
            A healthy meal delivered to your door, every single day
          </h1>
          <p class="hero-description">
            The smart 365-days-per-year food subscription that will make you eat
            healthy again. Tailored to your personal tastes and nutritional
            needs.
          </p>
          <a href="#" class="btn btn--full margin-right-sm"
            >Start eating well</a
          >
          <a href="#" class="btn btn--outline">Learn more &darr; </a>

          <div class="delivered-meals">
            <div class="delivered-imgs">
              <img src="./img/customers/customer-1.jpg" alt="customer photo" />
              <img src="./img/customers/customer-2.jpg" alt="customer photo" />
              <img src="./img/customers/customer-3.jpg" alt="customer photo" />
              <img src="./img/customers/customer-4.jpg" alt="customer photo" />
              <img src="./img/customers/customer-5.jpg" alt="customer photo" />
              <img src="./img/customers/customer-6.jpg" alt="customer photo" />
            </div>
            <p class="delivered-text">
              <span>250,000+</span> meals delivered last year!
            </p>
          </div>
        </div>
        <div class="hero-img-box">
          <img
            src="./img/hero.png"
            alt="Woman enjoying food, meals in storgae container and food bowls on a table"
            class="hero-img"
          />
        </div>
      </div>
    </section>
  </main>
</body>
```

![image](./asset_HTML_CSS/Screenshot%202024-03-04%20224009.jpg)

## Building the Navigation (110)

```html
<header class="header">
  <img class="logo" alt="Omnifood logo" src="img/omnifood-logo.png" />
  <nav class="main-nav">
    <ul class="main-nav-list">
      <li><a class="main-nav-link" href="#">Section 1</a></li>
      <li><a class="main-nav-link" href="#">Section 2</a></li>
      <li><a class="main-nav-link" href="#">Section 3</a></li>
      <li><a class="main-nav-link" href="#">Section 4</a></li>
      <li><a class="main-nav-link nav-cta" href="#">Section 5</a></li>
    </ul>
  </nav>
</header>
```

```css
/************************************/
/*Navigation*/
/************************************/

.main-nav-list {
  list-style: none;
  display: flex;
  align-items: center;
  gap: 3.2rem;
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
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-04%20224009.jpg)

## Settting up a Reusable Grid (111)

- We are going to add more section after the hero section, for how it works

- So beofre that we are going to learn the technique of creating reuse grid

```html
<section class="section-how">
  <div class="container grid grid--2-cols">
    <div>Test 1</div>
    <div>Test 2</div>
    <div>Test 3</div>
    <div>Test 4</div>
  </div>
</section>
```

```css
/************************************/
/*  HOW it works Section */
/************************************/

.section-how {
  padding: 9.6rem 0;
  background-color: rgb(255, 0, 0);
}

/* A Generic Container : We will use it multiple time. This is an element we are gonna use in order to center the content on our page. So inside of the browser viewport */
.container {
  /* 1140px */
  max-width: 120rem;
  margin: 0 auto;

  /* For not getting glued in the side, when screen is small, we add little padding */
  padding: 0 3.2rem;

  /* SO Finally we will end up with 1140 px, which is basically a generally accepted width */
}

/* Generic Class */
.grid {
  display: grid;
  gap: 9.6rem;
}

/* Generic class */
.grid--2-cols {
  grid-template-columns: repeat(2, 1fr);
}

/* Generic class */
.grid--3-cols {
  grid-template-columns: repeat(3, 1fr);
}

/* Generic class */
.grid--4-cols {
  grid-template-columns: repeat(4, 1fr);
}

/* Individual Grid */
.section-how div div {
  background-color: #333;
  padding: 100px;
  font-size: 50px;
}
```

- Observance, in Hero also we could use the same container, but in hero, we used width of 130rem. So basically it is little bit big

- We also learned to create generic class, so that we can reuse them in different places

## Building the How-it-Works Section - Part 1 (112)

![image](./asset_HTML_CSS/Screenshot%202024-03-05%20130323.png)

![image](./asset_HTML_CSS/Screenshot%202024-03-05%20133455.png)

- We are using Z Pattern

```html
<section class="section-how">
  <!-- Heading of section -->
  <div class="container">
    <span class="subheading">How it works</span>
    <h2 class="heading-secondary">
      Your daily dose of health in 3 simple steps
    </h2>
  </div>

  <!-- As we want grid for the Z pattern, we wll create another division (container) -->
  <div class="container grid grid--2-cols">
    <!-- Step 01 -->
    <div class="step-text-box">
      <p class="step-number">01</p>
      <h3 class="heading-tertiary">Tell us what you like (and what not)</h3>
      <p class="step-description">
        Never again waste time thinking about what to eat! Omnifood AI will
        create a 100% personalized weekly meal plan just for you. It makes sure
        you get all the nutrients and vitamins you need, no matter what diet you
        follow!
      </p>
    </div>
    <div class="step-img-box">
      <img
        src="./img/app/app-screen-1.png"
        class="step-img"
        alt="iphone app preferences selection screen"
      />
    </div>

    <!-- Step 02 -->
    <div class="step-img-box">
      <img
        src="./img/app/app-screen-1.png"
        class="step-img"
        alt="iphone app meal approving plan"
      />
    </div>

    <div class="step-text-box">
      <p class="step-number">02</p>
      <h3 class="heading-tertiary">Approve your weekly meal plan</h3>
      <p class="step-description">
        Once per week, approve the meal plan generated for you by Omnifood AI.
        You can change ingredients, swap entire meals, or even add your own
        recipes.
      </p>
    </div>

    <!-- Step 03 -->

    <div class="step-text-box">
      <p class="step-number">03</p>
      <h3 class="heading-tertiary">Receive meals at convenient time</h3>
      <p class="step-description">
        Best chefs in town will cook your selected meal every day, and we will
        deliver it to your door whenever works best for you. You can change
        delivery schedule and address daily!
      </p>
    </div>
    <div class="step-img-box">
      <img
        src="./img/app/app-screen-1.png"
        class="step-img"
        alt="iphone app delivery screen"
      />
    </div>
  </div>
</section>
```

```css
.section-how {
  padding: 9.6rem 0;
}

.step-img {
  width: 50%;
}

.heading-secondary {
  font-weight: 700;
  color: #333;
  letter-spacing: -0.5px;

  /* Unique */
  font-size: 4.4rem;
  line-height: 1.2;
  margin-bottom: 9.6rem;
}

.subheading {
  display: block;
  font-size: 1.6rem;
  font-weight: 500;
  color: #cf711f;
  text-transform: uppercase;
  margin-bottom: 1.6rem;
  letter-spacing: 0.75px;
}
```

- Letter we have combined the common property of headings, and put all the code in common section

```css
/************************************/
/* General Reusable Components */
/************************************/

.container {
  /* 1140px */
  max-width: 120rem;
  margin: 0 auto;

  /* For not getting glued in the side, when screen is small, we add little padding */
  padding: 0 3.2rem;

  /* SO Finally we will end up with 1140 px, which is basically a generally accepted width */
}

.grid {
  display: grid;
  gap: 9.6rem;
}

.grid--2-cols {
  grid-template-columns: repeat(2, 1fr);
}

.grid--3-cols {
  grid-template-columns: repeat(3, 1fr);
}

.grid--4-cols {
  grid-template-columns: repeat(4, 1fr);
}

/* Common Property */
.heading-primary,
.heading-secondary {
  font-weight: 700;
  color: #333;
  letter-spacing: -0.5px;
}

.heading-primary {
  font-size: 5.2rem;
  line-height: 1.05;

  margin-bottom: 3.2rem;
}

.heading-secondary {
  font-size: 4.4rem;
  line-height: 1.2;
  margin-bottom: 9.6rem;
}

.subheading {
  display: block;
  font-size: 1.6rem;
  font-weight: 500;
  color: #cf711f;
  text-transform: uppercase;
  margin-bottom: 1.6rem;
  letter-spacing: 0.75px;
}
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-05%20142814.png)

## Building the How-it-Works Section - Part 2 (113)

- We will segregate css file into multiple file

- general.css, style.css

- We have to make the text in step description in certer. We have 3 ways to do.

1. We can make flex, then flex-direction : col, and justify content & align items

2. Selecct the step box > Since they are grid items,we can set align self to center

3. We can also do the same thing from parent element, by using align items : center

We will go with the 3rd Option

- We will also have writtten grid--center-v & heading-tertiary class in general css style for reusing

- Also we will add some circle behind the mobile image. We will not pollute our html, instead we will use pseudo element

- We have learnt how to add circle

- We have also learnt to make a squre in after/beofre pseudo element with a trick

- We have also learned the z-index

![image](./asset_HTML_CSS/Screenshot%202024-03-05%20170911.png)

```css
/************************************/
/*  HOW it works Section */
/************************************/

.section-how {
  padding: 9.6rem 0;
}

.step-number {
  font-size: 9.8rem;
  font-weight: 600;
  color: #eee;
  margin-bottom: 1.2rem;
}

.step-description {
  font-size: 1.8rem;
  line-height: 1.8;
}

/* TO center the image */
.step-img-box {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.step-img {
  width: 35%;
}

/* Inserting 2clild elemnt to make a circle */
.step-img-box::before,
.step-img-box::after {
  content: "";
  background-color: #fdf2e9;
  display: block;
  /* Making it round */
  border-radius: 50%;
  /* TO put it behind */
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.step-img-box::before {
  /* Want to make it a squre first */
  width: 60%;
  /* Height will not work,  */
  /* height: 60%; */
  /* We can use a traick
  To give same height of 60%, add a padding to the bottom  */
  /* 60 % of parents width */
  padding-bottom: 60%;
  /* Elements with higher value will appear first */
  z-index: -2;
}

.step-img-box::after {
  width: 45%;
  padding-bottom: 45%;
  background-color: #fae5d3;
  z-index: -1;
}
```

General

```css
.grid {
  display: grid;
  row-gap: 9.6rem;
  column-gap: 6.4rem;
}

.grid--2-cols {
  grid-template-columns: repeat(2, 1fr);
}

.grid--3-cols {
  grid-template-columns: repeat(3, 1fr);
}

.grid--4-cols {
  grid-template-columns: repeat(4, 1fr);
}

.grid--center-v {
  align-items: center;
}

/* Added Tertiary Heading Style */
.heading-primary,
.heading-secondary,
.heading-tertiary {
  font-weight: 700;
  color: #333;
  letter-spacing: -0.5px;
}

.heading-primary {
  font-size: 5.2rem;
  line-height: 1.05;

  margin-bottom: 3.2rem;
}

.heading-secondary {
  font-size: 4.4rem;
  line-height: 1.2;
  margin-bottom: 9.6rem;
}

.heading-tertiary {
  font-size: 3rem;
  line-height: 1.2;
  margin-bottom: 3.2rem;
}

.subheading {
  display: block;
  font-size: 1.6rem;
  font-weight: 500;
  color: #cf711f;
  text-transform: uppercase;
  margin-bottom: 1.6rem;
  letter-spacing: 0.75px;
}
```

```html
<div class="container grid grid--2-cols grid--center-v">
  <!-- All Text & Image -->
</div>
```

## Building the Featured-In Section (114)

![image](./asset_HTML_CSS/Screenshot%202024-03-05%20171624.png)

![image](./asset_HTML_CSS/Screenshot%202024-03-05%20183027.png)

- Learned Opacity
- Learned Filter : Greyscale, Contrast, blur etc

```css
   <section class="section-featured">
        <!-- We want the content to be centered in the view port -->
        <div class="container">
          <h2 class="heading-featured-in">As featured in</h2>
          <div class="logos">
            <img src="./img/logos/techcrunch.png" alt="Logo of Tech Crunch" />
            <img
              src="./img/logos/business-insider.png"
              alt="Logo of Business Insider"
            />

            <img
              src="./img/logos/the-new-york-times.png"
              alt="Logo of New Work Times"
            />

            <img src="./img/logos/forbes.png" alt="Logo of forbes" />

            <img src="./img/logos/usa-today.png" alt="Logo of USA Today" />
          </div>
        </div>
<section>

```

```css
/************************************/
/* Featured iN Section */
/************************************/
.section-featured {
  padding: 4.8rem 0 3.2rem 0;
}

.heading-featured-in {
  font-size: 1.4rem;
  text-transform: uppercase;
  letter-spacing: 0.75px;
  font-weight: 500;
  text-align: center;
  margin-bottom: 2.4rem;
  color: #888;
}

.logos {
  display: flex;
  justify-content: space-around;
}

.logos img {
  height: 3.2rem;
  /* n Image, we have filter property */
  /* filter: grayscale(100%); */

  /* To make one color only, full black */
  filter: brightness(0);
  opacity: 50%;
}
```

## Building the Meal Section - Part 1 (115)

![iamge](./asset_HTML_CSS/Screenshot%202024-03-05%20183706.png)

![image](./asset_HTML_CSS/Screenshot%202024-03-05%20183731.png)

- We will use another type of Icon : Not the hero icon. Why? Because heroicon clutters up our html

- So this time we will use ionicon > `ionic.io`

![Image](./asset_HTML_CSS/Screenshot%202024-03-05%20195836.png)

```html
<section class="section-meals">
  <!-- Heading of section -->
  <div class="container">
    <span class="subheading">Meals</span>
    <h2 class="heading-secondary">Omnifood AI chooses from 5,000+ recipes</h2>
  </div>

  <!-- Cart. So we have implemented one only for now -->
  <div class="container grid grid--3-cols">
    <div class="meal">
      <img
        src="./img/meals/meal-1.jpg"
        alt="Japanese Gyozas"
        class="meal-img"
      />
      <span class="tag">Vegetarian</span>
      <p class="meal-title">Japanese Gyozas</p>
      <ul class="meal-attributes">
        <li class="meal-attribute">
          <ion-icon name="flame-outline"></ion-icon>
          <span>650 calories</span>
        </li>
        <li class="meal-attribute">
          <ion-icon name="restaurant-outline"></ion-icon>
          <span> NutriScore &reg; 74 </span>
        </li>
        <li class="meal-attribute">
          <ion-icon name="star-outline"></ion-icon>
          <span>4.9 rating (357)</span>
        </li>
      </ul>
    </div>
    <div class="meal">Meals</div>
    <div class="list">List of Diets</div>
  </div>
</section>
```

```css
/************************************/
/*  Meal Section */
/************************************/

.section-meals {
  padding: 9.6rem 0;
}

.meal-img {
  width: 100%;
}

.meal-title {
  font-size: 2.4rem;
  color: #333;
  font-weight: 600;
  margin-bottom: 3.2rem;
}

.meal-attributes {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1.6rem;
}
.meal-attribute {
  font-size: 1.8rem;
}
```

## Building the Meal Section - Part 2 (116)

```html
<section class="section-meals">
  <!-- Heading of section -->
  <div class="container">
    <span class="subheading">Meals</span>
    <h2 class="heading-secondary">Omnifood AI chooses from 5,000+ recipes</h2>
  </div>

  <!-- Grid 3 -->
  <div class="container grid grid--3-cols">
    <!-- 1st Meal -->
    <div class="meal">
      <img
        src="./img/meals/meal-1.jpg"
        alt="Japanese Gyozas"
        class="meal-img"
      />

      <div class="meal-content">
        <div class="meal-tags">
          <span class="tag tag--vegetarian">Vegetarian</span>
        </div>
        <p class="meal-title">Japanese Gyozas</p>
        <ul class="meal-attributes">
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="flame-outline"></ion-icon>
            <span><strong>650</strong> calories</span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="restaurant-outline"></ion-icon>
            <span> NutriScore &reg; <strong>74</strong> </span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="star-outline"></ion-icon>
            <span> <strong>4.9</strong> rating (357)</span>
          </li>
        </ul>
      </div>
    </div>

    <!-- 2nd Meal -->
    <div class="meal">
      <img src="./img/meals/meal-2.jpg" alt="Avocado Salad" class="meal-img" />

      <div class="meal-content">
        <div class="meal-tags">
          <span class="tag tag--vegan">Vegan</span>
          <span class="tag tag--paleo">Paleo</span>
        </div>
        <p class="meal-title">Avocado Salad</p>
        <ul class="meal-attributes">
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="flame-outline"></ion-icon>
            <span><strong>400</strong> calories</span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="restaurant-outline"></ion-icon>
            <span> NutriScore &reg; <strong>92</strong> </span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="star-outline"></ion-icon>
            <span> <strong>4.8</strong> rating (441)</span>
          </li>
        </ul>
      </div>
    </div>
    <div class="list">List of Diets</div>
  </div>
</section>
```

```css
************************************/
/*  Meal Section */
/************************************/

.section-meals {
  padding: 9.6rem 0;
}

.meal {
  box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.075);
  border-radius: 11px;

  /* 🆕🆕To make sure that whatever element is on the element, it should get overflowed 
  
  Because, I wanted, the image above of it should also get the same radius*/
  overflow: hidden;
}

.meal-content {
  padding: 3.2rem 4.8rem 4.8rem 4.8rem;
}

.meal-tags {
  margin-bottom: 1.2rem;
  display: flex;
  gap: 0.4rem;
}

.tag {
  display: inline-block;
  padding: 0.4rem 0.8rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  color: #333;
  border-radius: 100px;
  font-weight: 600;
}

.tag--vegetarian {
  background-color: #51cf66;
}

.tag--vegan {
  background-color: #94d82d;
}

.tag--paleo {
  background-color: #ffd43b;
}

.meal-title {
  font-size: 2.4rem;
  color: #333;
  font-weight: 600;
  margin-bottom: 3.2rem;
}

.meal-attributes {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1.6rem;
}
.meal-attribute {
  font-size: 1.8rem;
  display: flex;
  align-items: center;
  gap: 1.6em;
}
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-05%20224740.png)

## Building the Meal Section - Part 3 (117)

- We will make the diet list

- Before that we have a Bug in transition... So we just gave background color as transition, lets make it all, so that it will work for the learn more shadow peoerty also

```css
/* Updated the transition */
.btn:link,
.btn:visited {
  font-size: 2rem;
  font-weight: 600;
  text-decoration: none;
  display: inline-block;
  padding: 1.6rem 3.2rem;
  border-radius: 9px;
  /* transition: background-color 0.5s; */
  transition: all 0.5s;
}
```

We also added some special classes for reuse

```css
/* HELPER CLASSES */
.margin-right-sm {
  margin-right: 1.6rem !important;
}
.margin-bottom-md {
  margin-bottom: 4.8rem !important;
}
.center-text {
  text-align: center;
}
```

```css
.link:link,
.link:visited {
  display: inline-block;
  color: #e67e22;
  text-decoration: none;
  border-bottom: 1px solid currentColor;
  padding-bottom: 2px;

  transition: all 0.3s;
}

.link:hover,
.link:active {
  color: #cf711f;
  border-bottom: 1px solid transparent;
}
```

```html
<section class="section-meals">
  <!-- Heading of section -->
  <div class="container center-text">
    <span class="subheading">Meals</span>
    <h2 class="heading-secondary">Omnifood AI chooses from 5,000+ recipes</h2>
  </div>

  <!-- Grid 3 -->
  <div class="container grid grid--3-cols margin-bottom-md">
    <!-- 1st Meal -->
    <div class="meal">
      <img
        src="./img/meals/meal-1.jpg"
        alt="Japanese Gyozas"
        class="meal-img"
      />

      <div class="meal-content">
        <div class="meal-tags">
          <span class="tag tag--vegetarian">Vegetarian</span>
        </div>
        <p class="meal-title">Japanese Gyozas</p>
        <ul class="meal-attributes">
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="flame-outline"></ion-icon>
            <span><strong>650</strong> calories</span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="restaurant-outline"></ion-icon>
            <span> NutriScore &reg; <strong>74</strong> </span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="star-outline"></ion-icon>
            <span> <strong>4.9</strong> rating (357)</span>
          </li>
        </ul>
      </div>
    </div>

    <!-- 2nd Meal -->
    <div class="meal">
      <img src="./img/meals/meal-2.jpg" alt="Avocado Salad" class="meal-img" />

      <div class="meal-content">
        <div class="meal-tags">
          <span class="tag tag--vegan">Vegan</span>
          <span class="tag tag--paleo">Paleo</span>
        </div>
        <p class="meal-title">Avocado Salad</p>
        <ul class="meal-attributes">
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="flame-outline"></ion-icon>
            <span><strong>400</strong> calories</span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="restaurant-outline"></ion-icon>
            <span> NutriScore &reg; <strong>92</strong> </span>
          </li>
          <li class="meal-attribute">
            <ion-icon class="meal-icon" name="star-outline"></ion-icon>
            <span> <strong>4.8</strong> rating (441)</span>
          </li>
        </ul>
      </div>
    </div>

    <!-- DIET LIST 🆕🆕 -->
    <div class="diets">
      <h3 class="heading-tertiary">Works with any diet:</h3>
      <ul class="list">
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span> Vegetarian</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span> Vegan </span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span> Pescatarian</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span> Gluten-free </span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Lactose-free Keto </span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Keto </span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Paleo </span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Low FODMAP</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Kid Friendly</span>
        </li>
      </ul>
    </div>
  </div>
  <!-- LINK 🆕🆕 -->
  <div class="container all-receipes">
    <a href="#" class="link">See all Receipe &rarr;</a>
  </div>
</section>
```

- We have added some animation in the meal boxes also

```css
/************************************/
/*  Meal Section */
/************************************/

.section-meals {
  padding: 9.6rem 0;
}

/* 🆕🆕🆕 */
.meal {
  box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.075);
  border-radius: 11px;

  /* To make sure that whatever element is on the element, it should get overflowed 
  
  Because, I wanted, the image above of it should also get the same radius*/
  overflow: hidden;
  transition: all 0.5s;
}

.meal:hover {
  /* Translate function takes X-axis(horizontal) & y axis(vertical) */
  transform: translateY(-1.2rem);
  box-shadow: 0 3.2rem 6.4rem rgba(0, 0, 0, 0.2);
}

.meal-content {
  padding: 3.2rem 4.8rem 4.8rem 4.8rem;
}

.meal-tags {
  margin-bottom: 1.2rem;
  display: flex;
  gap: 0.4rem;
}

.tag {
  display: inline-block;
  padding: 0.4rem 0.8rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  color: #333;
  border-radius: 100px;
  font-weight: 600;
}

.tag--vegetarian {
  background-color: #51cf66;
}

.tag--vegan {
  background-color: #94d82d;
}

.tag--paleo {
  background-color: #ffd43b;
}

.meal-title {
  font-size: 2.4rem;
  color: #333;
  font-weight: 600;
  margin-bottom: 3.2rem;
}

.meal-attributes {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1.6rem;
}
.meal-attribute {
  font-size: 1.8rem;
  display: flex;
  align-items: center;
  gap: 1.6em;
}

.meal-icon {
  height: 2.4rem;
  width: 2.4rem;
  /* These Icons are treated as Text, that is why, they are not working with fill, stroke */
  color: #e67e22;
}

/* Meal Image */
.meal-img {
  width: 100%;
}

/* Diet Lists */
.list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1.6rem;
}

.list-item {
  font-size: 1.8rem;
  display: flex;
  align-items: center;
  gap: 1.6rem;
}

.list-icon {
  width: 3rem;
  height: 3rem;
  color: #e67e22;
}

.all-receipes {
  text-align: center;
  font-size: 1.8rem;
}
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-06%20114453.png)

## Building the Testimonials Sections - Part 1 (118)

![image](./asset_HTML_CSS/Screenshot%202024-03-06%20114623.png)

![image](./asset_HTML_CSS/Screenshot%202024-03-06%20123604.png)

```html
<section class="section-testimonials grid grid--2-cols">
  <!-- Heading of section -->
  <div class="testimonials-container">
    <span class="subheading">Testimonials</span>
    <h2 class="heading-secondary">Once you try it, you can't go back</h2>

    <!-- 1 box for testimonials -->
    <div class="testimonials">
      <!-- We use figure for diagrams, photos, code-linsting, Testimonial that can have a caption and that is self-contained -->
      <figure class="testimonial">
        <img
          src="./img/customers/dave.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          Inexpensive, healthy and great-tasting meals, without even having to
          order manually! It feels truly magical.
        </blockquote>
        <p class="testimonial-name">&mdash; Dave Bryson</p>
      </figure>

      <figure class="testimonial">
        <img
          src="./img/customers/ben.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          The AI algorithm is crazy good, it chooses the right meals for me
          every time. It's amazing not to worry about food anymore!
        </blockquote>
        <p class="testimonial-name">&mdash; Ben Hadely</p>
      </figure>

      <figure class="testimonial">
        <img
          src="./img/customers/steve.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          Omnifood is a life saver! I just started a company, so there's no time
          for cooking. I couldn't live without my daily meals now!.
        </blockquote>
        <p class="testimonial-name">&mdash; Steve Miller</p>
      </figure>

      <figure class="testimonial">
        <img
          src="./img/customers/hannah.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          I got Omnifood for the whole family, and it frees up so much time!
          Plus, everything is organic and vegan and without plastic.
        </blockquote>
        <p class="testimonial-name">&mdash; Hannah Smith</p>
      </figure>
    </div>
  </div>

  <!-- 2 box for gallery -->
  <div class="gallery">Gallery</div>
</section>
```

```css
/************************************/
/* Testimonial Section */
/************************************/

.section-testimonials {
  padding: 9.6rem 0;
}

/* We can not use the generic clas for grid, because we want different gap */
.testimonials {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4.8rem;
}

/* Though we use 100% image for width in Grid for fluidity
but in this case, we want them as a fixed size */
.testimonial-img {
  width: 6.4rem;
  border-radius: 50%;
  margin-bottom: 1.2rem;
}

.testimonial-text {
  font-size: 1.8rem;
  line-height: 1.8;
  margin-bottom: 1.6rem;
}

.testimonial-name {
  font-size: 1.6rem;
  color: #777;
}
```

## Building the Testimonials Sections - Part 2 (119)

- Now we will add gallery

```css
/************************************/
/* Testimonial Section */
/************************************/

.section-testimonials {
  /* padding: 9.6rem 0; */
  background-color: #fdf2e9;
  display: grid;
  grid-template-columns: 65fr 45fr;
  /* If user make the viewport little narrow, we get a weired space in the row. To remove it, we use align-items :center */
  align-items: center;
}

.testimonial-container {
  padding: 9.6rem;
}

/* We can not use the generic clas for grid, because we want different gap */
.testimonials {
  display: grid;
  grid-template-columns: 1fr 1fr;
  row-gap: 4.8rem;
  column-gap: 8rem;
}

/* Though we use 100% image for width in Grid for fluidity
but in this case, we want them as a fixed size */
.testimonial-img {
  width: 6.4rem;
  border-radius: 50%;
  margin-bottom: 1.2rem;
}

.testimonial-text {
  font-size: 1.8rem;
  line-height: 1.8;
  margin-bottom: 1.6rem;
}

.testimonial-name {
  font-size: 1.6rem;
  /* color: #777; */
  color: #6f6f6f;
}

/* Gallery */
.gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.6rem;
  padding: 1.6rem;
}

.gallery-item {
  /* 🆕🆕🆕 We do not want that after the hover effect, the image gets overflowed */
  overflow: hidden;
}

.gallery-item img {
  /* 🆕🆕🆕🟢🟢 To Remove the white space between images. We use display : Bloack */
  display: block;
  /* To make the size of image flexible */
  width: 100%;

  /* Animation */
  transition: all 0.5s;
}

/* Making an Hover effect, so when images are hovered, it sould be bigger little bit */
.gallery img:hover {
  transform: scale(1.1);
}
```

```html
<section class="section-testimonials">
  <!-- Heading of section -->
  <div class="testimonial-container">
    <span class="subheading">Testimonials</span>
    <h2 class="heading-secondary">Once you try it, you can't go back</h2>

    <!-- 1 box for testimonials -->
    <div class="testimonials">
      <!-- We use figure for diagrams, photos, code-linsting, Testimonial that can have a caption and that is self-contained -->
      <figure class="testimonial">
        <img
          src="./img/customers/dave.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          Inexpensive, healthy and great-tasting meals, without even having to
          order manually! It feels truly magical.
        </blockquote>
        <p class="testimonial-name">&mdash; Dave Bryson</p>
      </figure>

      <figure class="testimonial">
        <img
          src="./img/customers/ben.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          The AI algorithm is crazy good, it chooses the right meals for me
          every time. It's amazing not to worry about food anymore!
        </blockquote>
        <p class="testimonial-name">&mdash; Ben Hadely</p>
      </figure>

      <figure class="testimonial">
        <img
          src="./img/customers/steve.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          Omnifood is a life saver! I just started a company, so there's no time
          for cooking. I couldn't live without my daily meals now!.
        </blockquote>
        <p class="testimonial-name">&mdash; Steve Miller</p>
      </figure>

      <figure class="testimonial">
        <img
          src="./img/customers/hannah.jpg"
          alt="headshot of customer"
          class="testimonial-img"
        />
        <!-- We use Bolckqute for quoting any area, like a testimonial -->
        <blockquote class="testimonial-text">
          I got Omnifood for the whole family, and it frees up so much time!
          Plus, everything is organic and vegan and without plastic.
        </blockquote>
        <p class="testimonial-name">&mdash; Hannah Smith</p>
      </figure>
    </div>
  </div>

  <!-- 2 box for gallery -->
  <div class="gallery">
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-1.jpg"
        alt="Photo of beatifully arranged food"
      />
      <!-- <figcaption>Caption....</figcaption> -->
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-2.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-3.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-4.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-5.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-6.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-7.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-8.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-9.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-10.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-11.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
    <figure class="gallery-item">
      <img
        src="img/gallery/gallery-12.jpg"
        alt="Photo of beatifully arranged food"
      />
    </figure>
  </div>
</section>
```

![image](./asset_HTML_CSS/Screenshot%202024-03-06%20190616.png)

## Building the Pricing Section - Part 1 (120)

![image](./asset_HTML_CSS/Screenshot%202024-03-06%20190749.png)

```html
<section class="section-pricing">
  <!-- Heading of section -->
  <div class="container">
    <span class="subheading">Pricing</span>
    <h2 class="heading-secondary">Eating well without breaking the bank</h2>
  </div>

  <!-- Will create new container for the pricing box side by side -->
  <div class="container grid grid--2-cols">
    <div class="pricing-plan">
      <header class="plan-header">
        <p class="plan-name">Starter</p>
        <p class="plan-price"><span>$</span>399</p>
        <p class="plan-text">per month. That's just $13 per meal</p>
      </header>
      <!-- Reusing the HTML from Meal section -->
      <ul class="list">
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>1 meal per day</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Order times are between 11am and 9pm</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Delivery is free</span>
        </li>
      </ul>
      <div class="plan-sign-up">
        <a href="#" class="btn btn--full">Start eating well</a>
      </div>
    </div>
    <div class="pricing-plan">
      <header class="plan-header">
        <p class="plan-name">Complete</p>
        <p class="plan-price"><span>$</span>649</p>
        <p class="plan-text">per month. That's just $11 per meal</p>
      </header>
      <!-- Reusing the HTML from Meal section -->
      <ul class="list">
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>2 meals per day</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Order 24/7</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Delivery is free</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Get access to latest recipes</span>
        </li>
      </ul>
      <div class="plan-sign-up">
        <a href="#" class="btn btn--full">Start eating well</a>
      </div>
    </div>
  </div>
</section>
```

```css
/************************************/
/* Pricing Section */
/************************************/

.section-pricing {
  padding: 9.6rem 0;
}

.plan-header {
  text-align: center;
  margin-bottom: 4.8rem;
}

.plan-name {
  color: #cf711f;
  font-weight: 600;
  font-size: 2rem;
  text-transform: uppercase;
  letter-spacing: 0.75;
  margin-bottom: 3.2rem;
}
.plan-price {
  font-size: 6.2rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 1.6rem;
}

.plan-price span {
  font-size: 3rem;
  font-weight: 500;
  margin-right: 0.8rem;
}
.plan-text {
  font-size: 1.6rem;
  line-height: 1.6;
  color: #6f6f6f;
}

.plan-sign-up {
  margin-top: 4.8rem;
  text-align: center;
}
```

- As I have used List, in different places, So I have moved the Css Declaration in General Section

```css
/* Reusing the CSS Declaration for LIST */
.list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1.6rem;
}

.list-item {
  font-size: 1.8rem;
  display: flex;
  align-items: center;
  gap: 1.6rem;
}

.list-icon {
  width: 3rem;
  height: 3rem;
  color: #e67e22;
}
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-06%20194917.png)

## Building the Pricing Section - Part 2 (121)

- When we want to use multiple grid container, we want distance from one another.

```css
.grid {
  display: grid;
  row-gap: 9.6rem;
  column-gap: 6.4rem;

  /* margin-bottom: 9.6rem; */
}

/* When grid is last child, then margin bottom should be zero */
/* .grid:last-child {
  margin-bottom: 0;
} */

/* Or we can do it more nice way */
.grid:not(:last-child) {
  margin-bottom: 9.6rem;
}
```

```css
/************************************/
/* Pricing Section */
/************************************/

.section-pricing {
  padding: 9.6rem 0;
}

.pricing-plan {
  /* background-color: #fdf2e9; */
  border-radius: 11px;
  /* padding: 4.8rem; */

  /* Currently this is block level element, so it takes full length 
  We want they should take less width*/
  width: 75%;
}

/* To make the first column iteams to be justified to the end  */
.pricing-plan--starter {
  justify-self: end;
  border: 2px solid #fdf2e9;
  padding: 4.6rem;
}

/* TO make olnt the complete plan box colorful */
.pricing-plan--complete {
  background-color: #fdf2e9;
  padding: 4.8rem;
  overflow: hidden;
  position: relative;
}

/* TO make a ribon 🆕🆕👌👌*/
.pricing-plan--complete::before {
  content: "Best Value";
  color: #333;
  position: absolute;
  text-transform: uppercase;
  font-size: 1.4rem;
  font-weight: 700;
  top: 6%;
  right: -18%;
  background-color: #ffd43b;
  padding: 0.8rem 8rem;

  transform: rotate(45deg);
}

/* Giving a Red Color for the last */
.pricing-plan--starter .list li:last-child span,
.pricing-plan--starter .list li:last-child .list-icon {
  color: rgb(233, 139, 139);
}

.plan-header {
  text-align: center;
  margin-bottom: 4.8rem;
}

.plan-name {
  color: #cf711f;
  font-weight: 600;
  font-size: 2rem;
  text-transform: uppercase;
  letter-spacing: 0.75px;
  margin-bottom: 3.2rem;
}
.plan-price {
  font-size: 6.2rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 1.6rem;
}

.plan-price span {
  font-size: 3rem;
  font-weight: 500;
  margin-right: 0.8rem;
}
.plan-text {
  font-size: 1.6rem;
  line-height: 1.6;
  color: #6f6f6f;
}

.plan-sign-up {
  margin-top: 4.8rem;
  text-align: center;
}
```

```html
<section class="section-pricing">
  <!-- Heading of section -->
  <div class="container">
    <span class="subheading">Pricing</span>
    <h2 class="heading-secondary">Eating well without breaking the bank</h2>
  </div>

  <!-- Will create new container for the pricing box side by side -->
  <div class="container grid grid--2-cols">
    <!-- 1st Price -->
    <div class="pricing-plan pricing-plan--starter">
      <header class="plan-header">
        <p class="plan-name">Starter</p>
        <p class="plan-price"><span>$</span>399</p>
        <p class="plan-text">per month. That's just $13 per meal</p>
      </header>
      <!-- Reusing the HTML from Meal section -->
      <ul class="list">
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>1 meal per day</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Order from 11am and 9pm</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Delivery is free</span>
        </li>
        <li class="list-item">
          <ion-icon name="close-circle-outline" class="list-icon"></ion-icon>
          <span>Access to latest recipes</span>
        </li>
      </ul>
      <div class="plan-sign-up">
        <a href="#" class="btn btn--full">Start eating well</a>
      </div>
    </div>

    <!-- 2nd Price -->
    <div class="pricing-plan pricing-plan--complete">
      <header class="plan-header">
        <p class="plan-name">Complete</p>
        <p class="plan-price"><span>$</span>649</p>
        <p class="plan-text">per month. That's just $11 per meal</p>
      </header>
      <!-- Reusing the HTML from Meal section -->
      <ul class="list">
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span><strong>2</strong> meals per day</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Order <strong>24/7</strong></span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Delivery is free</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Get access to latest recipes</span>
        </li>
      </ul>
      <div class="plan-sign-up">
        <a href="#" class="btn btn--full">Start eating well</a>
      </div>
    </div>
  </div>
  <!-- Adding Features after the Prices -->
  <div class="container grid grid--4-cols">
    <div class="feature">Feature 1</div>
    <div class="feature">Feature 2</div>
    <div class="feature">Feature 3</div>
    <div class="feature">Feature 4</div>
  </div>
</section>
```

![image](./asset_HTML_CSS/Screenshot%202024-03-07%20131708.png)

## Building the Features Part (122)

![image](./asset_HTML_CSS/Screenshot%202024-03-07%20140834.png)

- Here we have user helper class : in the price box, margin-bottom-md
- Also regarding the text (TEX regarding), we used grid, so that we can have access to margin bottom consistency
- So to override any general rule, we used helper function

```css
/* Middle of Price & Feature */
.plan-details {
  font-size: 1.6rem;
  line-height: 1.6;
  text-align: center;
}
/* FEATURE */

.feature-icon {
  color: #e67e22;
  font-size: 3.2rem;

  margin-bottom: 3.2rem;

  /* We want to make a circle, */
  background-color: #fdf2e9;
  padding: 1.6rem;
  border-radius: 50%;
}

.feature-title {
  font-size: 2.4rem;
  color: #333;
  font-weight: 700;
  margin-bottom: 1.6rem;
}
.feature-text {
  font-size: 1.8rem;
  line-height: 1.8;
}
```

```html
<section class="section-pricing">
  <!-- Heading of section -->
  <div class="container">
    <span class="subheading">Pricing</span>
    <h2 class="heading-secondary">Eating well without breaking the bank</h2>
  </div>

  <!-- Will create new container for the pricing box side by side -->
  <div class="container grid grid--2-cols margin-bottom-md">
    <!-- 1st Price -->
    <div class="pricing-plan pricing-plan--starter">
      <header class="plan-header">
        <p class="plan-name">Starter</p>
        <p class="plan-price"><span>$</span>399</p>
        <p class="plan-text">per month. That's just $13 per meal</p>
      </header>
      <!-- Reusing the HTML from Meal section -->
      <ul class="list">
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>1 meal per day</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Order from 11am and 9pm</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Delivery is free</span>
        </li>
        <li class="list-item">
          <ion-icon name="close-circle-outline" class="list-icon"></ion-icon>
          <span>Access to latest recipes</span>
        </li>
      </ul>
      <div class="plan-sign-up">
        <a href="#" class="btn btn--full">Start eating well</a>
      </div>
    </div>

    <!-- 2nd Price -->
    <div class="pricing-plan pricing-plan--complete">
      <header class="plan-header">
        <p class="plan-name">Complete</p>
        <p class="plan-price"><span>$</span>649</p>
        <p class="plan-text">per month. That's just $11 per meal</p>
      </header>
      <!-- Reusing the HTML from Meal section -->
      <ul class="list">
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span><strong>2</strong> meals per day</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Order <strong>24/7</strong></span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Delivery is free</span>
        </li>
        <li class="list-item">
          <ion-icon
            class="list-icon"
            name="checkmark-circle-outline"
          ></ion-icon>
          <span>Get access to latest recipes</span>
        </li>
      </ul>
      <div class="plan-sign-up">
        <a href="#" class="btn btn--full">Start eating well</a>
      </div>
    </div>
  </div>

  <!-- 🆕🆕 Adding the Price Text Line -->
  <div class="container grid">
    <aside class="plan-details">
      Prices include all applicable taxes. You can cancel at any time. Both plas
      include the following:
    </aside>
  </div>

  <!--🆕🆕  Adding Features after the Prices -->
  <div class="container grid grid--4-cols">
    <!-- 1st Feature -->
    <div class="feature">
      <ion-icon name="infinite-outline" class="feature-icon"></ion-icon>
      <p class="feature-title">Never cook again!</p>
      <p class="feature-text">
        Our subscriptions cover 365 days per year, even including major
        holidays.
      </p>
    </div>
    <!-- 2nd Feature -->
    <div class="feature">
      <ion-icon name="nutrition-outline" class="feature-icon"></ion-icon>
      <p class="feature-title">Local and organic</p>
      <p class="feature-text">
        Our cooks only use local, fresh, and organic products to prepare your
        meals.
      </p>
    </div>
    <!-- 3rd Feature -->
    <div class="feature">
      <ion-icon name="leaf-outline" class="feature-icon"></ion-icon>
      <p class="feature-title">No waste</p>
      <p class="feature-text">
        All our partners only use reusable containers to package all your meals.
      </p>
    </div>
    <!-- 4th Feature -->
    <div class="feature">
      <ion-icon name="pause-outline" class="feature-icon"></ion-icon>
      <p class="feature-title">Pause anytime</p>
      <p class="feature-text">
        Going on vacation? Just pause your subscription, and we refund unused
        days.
      </p>
    </div>
  </div>
</section>
```

## Building the Call-To-Action Section - Part 1 (123)

![image](./asset_HTML_CSS/Screenshot%202024-03-06%20190813.png)

```css
/************************************/
/* CTA  Section */
/************************************/

.section-cta {
  padding: 9.6rem 0;
}

.cta {
  display: grid;
  grid-template-columns: 2fr 1fr;
  /* background-color: #e67e22; */
  box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.15);
  border-radius: 11px;

  /* We will use gradient.
  Bradient is treated as an Image 
  
  - By Deafult : gradient flows form top to bottom
  
  - we can give degress to chnage the direction
  linear-gradient(90deg, red, #e67e22);
  linear-gradient(135deg, red, #e67e22);
  
  - We can also use Simple english
  linear-gradient(to right, red, #e67e22);*/
  background-image: linear-gradient(to right bottom, #eb984e, #e67e22);
  /* temp */
  height: 50rem;

  overflow: hidden;
}

.cta-text-box {
}

.cta-img-box {
  background-image: linear-gradient(
      rgba(235, 152, 78, 0.3),
      rgba(230, 126, 34, 0.3)
    ), url("./../img/eating.jpg");
  background-size: cover;
  background-position: center;
}
```

```html
<!-- CTA SECTION -->
<section class="section-cta">
  <div class="container">
    <div class="cta">
      <div class="cta-text-box">CTA</div>
      <!-- 
              Now we have an empty div element. which has no content at all.
              But visually this div still contain image, but it is non-accessable the screen readers
              
              Role: is an attribute : It would say this div element acts as if it was an image. So the role of this div is to be like an image
              
              aria-label: For Description we use aria-label (Just like we do for image alt attribute)
              
              - Nw the screen reader will be able to read it
            -->
      <div
        class="cta-img-box"
        role="img"
        aria-label="Woman enjoying food"
      ></div>
    </div>
  </div>
</section>
```

![image](./asset_HTML_CSS/Screenshot%202024-03-07%20163338.png)

## Building the Call-To-Action Section - Part 2 (124)

![img](./asset_HTML_CSS/Screenshot%202024-03-07%20170757.png)

- We will work with form elements for the first time:

```html
<!-- CTA SECTION -->
<section class="section-cta">
  <div class="container">
    <div class="cta">
      <div class="cta-text-box">
        <h2 class="heading-secondary">Get your first meal for free</h2>
        <p class="cta-text">
          Healthy, tasty and hassle-free meals are waiting for you. Start eating
          well today. You can cancel or pause anytime. And the first meal is on
          us!
        </p>

        <!-- FORM 🆕🆕 -->
        <form class="cta-form" action="#">
          <!-- We use label & Input together
                For making the label attached to Input field, we use for Attribute & ID attribute -->
          <div>
            <label for="full-name">Full Name</label>
            <input
              id="full-name"
              type="text"
              placeholder="John Smith"
              required
            />
          </div>

          <div>
            <label for="email">Email address</label>
            <input
              id="email"
              type="email"
              placeholder="me@example.com"
              required
            />
          </div>

          <!-- The value of input field, is basically what the user provides. Like name, email etc
                
                But in select, the value will be the text written in value attribute of option-->
          <div>
            <label for="select-where">Where did you hear from us?</label>
            <select id="select-where" required>
              <option value="">Please choose one option</option>
              <option value="friends">Firends & Family</option>
              <option value="youtube">Youtube</option>
              <option value="podcast">Podcast</option>
              <option value="ads">Facebook ads</option>
              <option value="others">Other</option>
            </select>
          </div>

          <button class="btn">Sign up now</button>
        </form>
      </div>
      <div
        class="cta-img-box"
        role="img"
        aria-label="Woman enjoying food"
      ></div>
    </div>
  </div>
</section>
```

```css
/************************************/
/* CTA  Section */
/************************************/

.section-cta {
  padding: 9.6rem 0;
}

.cta {
  display: grid;
  grid-template-columns: 2fr 1fr;
  /* background-color: #e67e22; */
  box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.15);
  border-radius: 11px;
  background-image: linear-gradient(to right bottom, #eb984e, #e67e22);
  /* temp */
  height: 50rem;

  overflow: hidden;
}

.cta-text-box {
  padding: 4.8rem 6.4rem 6.4rem 6.4rem;
  color: #45260a;
}

.cta-text-box .heading-secondary {
  color: #45260a;
  margin-bottom: 3.2rem;
}

.cta-text {
  font-size: 1.8rem;
  line-height: 1.8;
  margin-bottom: 4.8rem;
}

.cta-img-box {
  background-image: linear-gradient(
      rgba(235, 152, 78, 0.3),
      rgba(230, 126, 34, 0.3)
    ), url("./../img/eating.jpg");
  background-size: cover;
  background-position: center;
}
/* NEW🆕🆕 */
.cta-form {
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 3.2rem;
  row-gap: 2.4rem;
}
```

## Building the Call-To-Action Section - Part 3 (125)

- Now we will style the input element
- Focus State (for those who work with Keyboard only)
- Focus State can be manupulated by OUTLINE PROPERY. But we will use bax-shadow property

![img](./asset_HTML_CSS/Screenshot%202024-03-08%20131342.png)

```html
<!-- CTA SECTION -->
<section class="section-cta">
  <div class="container">
    <div class="cta">
      <div class="cta-text-box">
        <h2 class="heading-secondary">Get your first meal for free</h2>
        <p class="cta-text">
          Healthy, tasty and hassle-free meals are waiting for you. Start eating
          well today. You can cancel or pause anytime. And the first meal is on
          us!
        </p>

        <form class="cta-form" action="#">
          <!-- We use label & Input together
                For making the label attached to Input field, we use for Attribute & ID attribute -->
          <div>
            <label for="full-name">Full Name</label>
            <input
              id="full-name"
              type="text"
              placeholder="John Smith"
              required
            />
          </div>

          <div>
            <label for="email">Email address</label>
            <input
              id="email"
              type="email"
              placeholder="me@example.com"
              required
            />
          </div>

          <!-- The value of input field, is basically what the user provides. Like name, email etc
                
                But in select, the value will be the text written in value attribute of option-->
          <div>
            <label for="select-where">Where did you hear from us?</label>
            <select id="select-where" required>
              <option value="">Please choose one option</option>
              <option value="friends">Firends & Family</option>
              <option value="youtube">Youtube</option>
              <option value="podcast">Podcast</option>
              <option value="ads">Facebook ads</option>
              <option value="others">Other</option>
            </select>
          </div>

          <button class="btn btn--form">Signup Now</button>
        </form>
      </div>
      <div
        class="cta-img-box"
        role="img"
        aria-label="Woman enjoying food"
      ></div>
    </div>
  </div>
</section>
```

```css
/************************************/
/* CTA  Section */
/************************************/

.section-cta {
  padding: 9.6rem 0;
}

.cta {
  display: grid;
  grid-template-columns: 2fr 1fr;
  /* background-color: #e67e22; */
  box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.15);
  border-radius: 11px;
  background-image: linear-gradient(to right bottom, #eb984e, #e67e22);
  /* temp */
  /* height: 50rem; */

  overflow: hidden;
}

.cta-text-box {
  padding: 4.8rem 6.4rem 6.4rem 6.4rem;
  color: #45260a;
}

.cta-text-box .heading-secondary {
  /* color: #45260a; */

  /* 🆕🆕 from parent to child */
  color: inherit;
  margin-bottom: 3.2rem;
}

.cta-text {
  font-size: 1.8rem;
  line-height: 1.8;
  margin-bottom: 4.8rem;
}

.cta-img-box {
  background-image: linear-gradient(
      rgba(235, 152, 78, 0.3),
      rgba(230, 126, 34, 0.3)
    ), url("./../img/eating.jpg");
  background-size: cover;
  background-position: center;
}

.cta-form {
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 3.2rem;
  row-gap: 2.4rem;
}

/* NEW  🆕🆕 */
.cta-form label {
  /* Label is a inline element, so to make in in different line, we have to make it as Block level element  */
  display: block;
  font-size: 1.6rem;
  font-weight: 500;
  margin-bottom: 1.2rem;
}
.cta-form input,
.cta-form select {
  width: 100%;

  padding: 1.2rem;
  font-size: 1.8rem;

  /* We have forced to inherit the font family which is used in all places
  So baiscally we can pass data from parent to child*/
  font-family: inherit;
  color: inherit;

  border: none;
  background-color: #fdf2e9;
  border-radius: 9px;

  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.2);
}

/* To make the palcaholder styled, we use pseudo element */
.cta-form input::placeholder {
  color: #aaa;
}

/* Overriding the focus state, because the background color is different */
.cta *:focus {
  outline: none;

  box-shadow: 0 0 0 0.8rem rgba(253, 242, 233, 0.69);
}
```

General CSS

```css
/* Focus Style change
Global Reset for focus */
*:focus {
  outline: none;
  /* outline: 4px dotted #e67e22; */
  /* outline-offset: 8px; */

  /* Zero in all direction, Also no spread, And sclae it little bit */
  box-shadow: 0 0 0 0.8rem #e67d228f;
}

/* Making the reusable class, so when it is Link or When it is button, in both times, it should work */
.btn,
.btn:link,
.btn:visited {
  font-size: 2rem;
  font-weight: 600;
  text-decoration: none;
  display: inline-block;
  padding: 1.6rem 3.2rem;
  border-radius: 9px;
  /* transition: background-color 0.5s; */
  transition: all 0.5s;

  /* Only for Buttom Elementitself */
  border: none;
  cursor: pointer;
  font-family: inherit;
}

.btn--form {
  background-color: #45260a;
  color: #fdf2e9;
  align-self: end;
  padding: 1.2rem;
}

.btn--form:hover {
  background-color: #fff;
  color: #555;
}
```

## Building the Footer - Part 1

![image](./asset_HTML_CSS/Screenshot%202024-03-06%20190834.png)

- We will use footer elemnt.
- We will use it outside of main element
- Main Area od a Website is for non-repeated content.
- And footer & Header might be used in other pages of the overall website

---

![image](./asset_HTML_CSS/Screenshot%202024-03-08%20142429.png)

- We have added `grid--5-cols`
- We have encompassed Image element with `<a>..img..<a/>` element for clicking purpose
- We learned the Break Element (for Next Line)
- For Phone and Email to work like - if they are clicked, they should be opened, then we have user some trick

```html
<address class="contacts">
  <p>623 Harrison St., 2nd Floor, San Francisco, CA 94107</p>
  <p>
    <a href="tel:415-201-6370">415-201-6370</a> <br />
    <a href="mailto:hello@omnifood.com"> hello@omnifood.com </a>
  </p>
</address>
```

```html
<footer class="footer">
  <!-- 5 Colum Grid -->
  <div class="container grid grid--5-cols">
    <!-- Logo Column which inclued social media & copyright-->
    <div class="logo-col">
      <a href="https://fonts.google.com/" class="footer-logo">
        <img class="logo" alt="Omnifood logo" src="img/omnifood-logo.png" />
      </a>

      <ul class="social-links">
        <li>
          <a href="#"><ion-icon name="logo-facebook"></ion-icon></a>
        </li>
        <li>
          <a href="#"><ion-icon name="logo-instagram"></ion-icon></a>
        </li>
        <li>
          <a href="#"><ion-icon name="logo-twitter"></ion-icon></a>
        </li>
      </ul>

      <p class="copyright">
        Copuright &copy; 2027 by Omnifood, Inc. All rights reserved.
      </p>
    </div>
    <!-- Address Column -->
    <div class="address-col">
      <p class="footer-heading">Contact Us</p>
      <address class="contacts">
        <p>623 Harrison St., 2nd Floor, San Francisco, CA 94107</p>
        <p>
          <a href="tel:415-201-6370">415-201-6370</a> <br />
          <a href="mailto:hello@omnifood.com"> hello@omnifood.com </a>
        </p>
      </address>
    </div>

    <!-- 3rd Column -->
    <nav class="nav-col">
      <p class="footer-heading">Account</p>
      <ul class="footer-nav">
        <li><a href="#">Create account</a></li>
        <li><a href="#">Sign in</a></li>
        <li><a href="#">iOS app</a></li>
        <li><a href="#">Android App</a></li>
      </ul>
    </nav>

    <!-- 4th Coulmn -->
    <nav class="nav-col">
      <p class="footer-heading">Company</p>
      <ul class="footer-nav">
        <li><a href="#">About Omnifood</a></li>
        <li><a href="#">For Business</a></li>
        <li><a href="#">Cooking partners</a></li>
        <li><a href="#">Careers</a></li>
      </ul>
    </nav>

    <!-- 5th Column -->
    <nav class="nav-col">
      <p class="footer-heading">Resources</p>
      <ul class="footer-nav">
        <li><a href="#">Receie Directory</a></li>
        <li><a href="#">Help Center</a></li>
        <li><a href="#">Privacy & Terms</a></li>
      </ul>
    </nav>
  </div>
</footer>
```

```css
/************************************/
/* Footer  Section */
/************************************/

.footer {
  padding: 9.6rem 0;
}
```

general css

```css
.grid--5-cols {
  grid-template-columns: repeat(5, 1fr);
}
```

## Building the Footer - Part 2

![image](./asset_HTML_CSS/Screenshot%202024-03-08%20182946.png)

```html
<footer class="footer">
  <!-- 5 Colum Grid -->
  <div class="container grid grid--footer">
    <!-- Logo Column which inclued social media & copyright-->
    <div class="logo-col">
      <a href="https://fonts.google.com/" class="footer-logo">
        <img class="logo" alt="Omnifood logo" src="img/omnifood-logo.png" />
      </a>

      <ul class="social-links">
        <li>
          <a href="#" class="footer-link"
            ><ion-icon name="logo-facebook" class="social-icon"></ion-icon
          ></a>
        </li>
        <li>
          <a href="#" class="footer-link"
            ><ion-icon name="logo-instagram" class="social-icon"></ion-icon
          ></a>
        </li>
        <li>
          <a href="#" class="footer-link"
            ><ion-icon name="logo-twitter" class="social-icon"></ion-icon
          ></a>
        </li>
      </ul>

      <p class="copyright">
        Copuright &copy; 2027 by Omnifood, Inc. All rights reserved.
      </p>
    </div>
    <!-- Address Column -->
    <div class="address-col">
      <p class="footer-heading">Contact Us</p>
      <address class="contacts">
        <p class="address">
          623 Harrison St., 2nd Floor, San Francisco, CA 94107
        </p>
        <p>
          <a href="tel:415-201-6370" class="footer-link">415-201-6370</a>
          <br />
          <a href="mailto:hello@omnifood.com" class="footer-link">
            hello@omnifood.com
          </a>
        </p>
      </address>
    </div>

    <!-- 3rd Column -->
    <nav class="nav-col">
      <p class="footer-heading">Account</p>
      <ul class="footer-nav">
        <li><a class="footer-link" href="#">Create account</a></li>
        <li><a class="footer-link" href="#">Sign in</a></li>
        <li><a class="footer-link" href="#">iOS app</a></li>
        <li><a class="footer-link" href="#">Android App</a></li>
      </ul>
    </nav>

    <!-- 4th Coulmn -->
    <nav class="nav-col">
      <p class="footer-heading">Company</p>
      <ul class="footer-nav">
        <li><a class="footer-link" href="#">About Omnifood</a></li>
        <li><a class="footer-link" href="#">For Business</a></li>
        <li><a class="footer-link" href="#">Cooking partners</a></li>
        <li><a class="footer-link" href="#">Careers</a></li>
      </ul>
    </nav>

    <!-- 5th Column -->
    <nav class="nav-col">
      <p class="footer-heading">Resources</p>
      <ul class="footer-nav">
        <li><a class="footer-link" href="#">Receie Directory</a></li>
        <li><a class="footer-link" href="#">Help Center</a></li>
        <li><a class="footer-link" href="#">Privacy & Terms</a></li>
      </ul>
    </nav>
  </div>
</footer>
```

```css
/************************************/
/* Footer  Section */
/************************************/

.footer {
  /* We have added more Padding, to make it distict */
  padding: 12.8rem 0;
  border-top: 1px solid #eee;
}

.grid--footer {
  /* We have re-written the grid rule, as the general grid class always create equal size column */
  grid-template-columns: 1.5fr 1.5fr 1fr 1fr 1fr;
}

.logo-col {
  display: flex;
  flex-direction: column;
}

.footer-logo {
  /* As we know link is a inline element, so for adding margin, e need to make it block level element */
  display: block;
  margin-bottom: 3.2rem;
}

.footer-heading {
  font-size: 1.8rem;
  font-weight: 500;
  margin-bottom: 4rem;
}

.social-links {
  list-style: none;
  display: flex;
  gap: 2.4rem;
}

.social-icon {
  height: 2.4rem;
  width: 2.4rem;
}

.copyright {
  font-size: 1.4rem;
  line-height: 1.6;
  columns: #767676;
  margin-top: auto;
}
/* Address Element  Has italic Font,  So We need to chnage it to Normal Fort */
.contacts {
  font-style: normal;
  font-size: 1.6rem;
  line-height: 1.6;
}

.address {
  margin-bottom: 2.4rem;
}

.footer-nav {
  list-style: none;
  /* Lets add gap between the list element*/
  display: flex;
  flex-direction: column;
  gap: 2.4rem;
}

.footer-link:link,
.footer-link:visited {
  text-decoration: none;
  font-size: 1.6rem;
  color: #767676;

  transition: all 0.3s;
}

.footer-link:hover,
.footer-link:active {
  color: #333;
}
```

TRICK

![image](./asset_HTML_CSS/Screenshot_1%20-%2008-03-2024.png)

I want to bring the Copyright section aligened with other, so basically bring it in the bottom

```css
.copyright {
  font-size: 1.4rem;
  line-height: 1.6;
  columns: #767676;

  /* Margin top Auto */
  margin-top: auto;
}
```

---

Also to make the padding bottom little more in CTA Section

```css
/************************************/
/* CTA  Section */
/************************************/

.section-cta {
  /* Top - right-bottom-left */
  /* padding: 9.6rem 0 12.8rem 0; */

  /* We can also write 3 values 
  Top - Horizontal - Left*/
  padding: 4.8rem 0 12.8rem;
}
```

**THE END**
