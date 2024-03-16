# Webdesign Rules & Framework

## Section Intro (65)

## Project Overview (66)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <link rel="stylesheet" href="style.css" />
    <title>Lisbon Chair Shop</title>
  </head>
  <body>
    <div class="container">
      <header>
        <div class="header-text-box">
          <h1>We design and build better chairs, for a better life</h1>
          <p class="header-text">
            In a small shop in the heart of Lisbon, we spend our days
            relentlessly perfecting the chair. The result is a perfect blend of
            beauty and comfort, that will have a lasting impact on your health.
          </p>
          <a class="btn btn--big" href="#">Shop chairs</a>
        </div>
        <img src="hero.jpg" alt="Photo" />
      </header>

      <section>
        <h2>What makes our chairs special</h2>
        <div class="grid-3-cols">
          <div>
            <p class="features-title"><strong>Science meets design</strong></p>
            <p class="features-text">
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Natus
              similique adipisci praesentium.
            </p>
          </div>

          <div>
            <p class="features-title">
              <strong>Maximal comfort</strong>
            </p>
            <p class="features-text">
              Reprehenderit optio placeat quasi excepturi architecto, explicabo
              facilis perspiciatis error maxime magnam.
            </p>
          </div>

          <div>
            <p class="features-title">
              <strong>Ethical and sustainable</strong>
            </p>
            <p class="features-text">
              Deleniti recusandae quidem nesciunt, eos dolorum iure, quaerat
              omnis est laudantium voluptatem voluptas!
            </p>
          </div>
        </div>
      </section>

      <section class="testimonial-section">
        <div class="grid-3-cols">
          <img src="customers.jpg" alt="People sitting on chairs" />
          <div class="testimonial-box">
            <h2>"We couldn't live without these chairs anymore"</h2>
            <blockquote class="testimonial-text">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolor
              repellat at, nesciunt quia cum minima ipsum culpa totam sapiente
              recusandae earum debitis doloribus in quasi voluptatibus!
            </blockquote>
            <p class="testimonial-author">&mdash; Mary and Sarah Johnson</p>
          </div>
        </div>
      </section>

      <section>
        <h2>Our bestselling chairs</h2>
        <div class="grid-3-cols">
          <figure class="chair">
            <img src="chair-1.jpg" alt="Chair" />
            <div class="chair-box">
              <h3>The Laid Back</h3>
              <ul class="chair-details">
                <li>
                  <!-- Span is a generic INLINE text element, it doesn't have any meaning. It's like a div element, but inline -->
                  <span>Leisure and relaxing</span>
                </li>
                <li>
                  <span>Comfortable for 4h</span>
                </li>
                <li>
                  <span>Vegan leather</span>
                </li>
                <li>
                  <span>Weighs 16 kg</span>
                </li>
              </ul>
              <div class="chair-price">
                <strong>250€</strong>
                <a href="#" class="btn btn--small">Add to cart</a>
              </div>
            </div>
          </figure>

          <figure class="chair">
            <img src="chair-2.jpg" alt="Chair" />
            <div class="chair-box">
              <h3>The Worker Bee</h3>
              <ul class="chair-details">
                <li>
                  <span>Work</span>
                </li>
                <li>
                  <span>Comfortable for 8h</span>
                </li>
                <li>
                  <span>Vegan leather</span>
                </li>
                <li>
                  <span>Weighs 22 kg</span>
                </li>
              </ul>
              <div class="chair-price">
                <strong>525€</strong>
                <a href="#" class="btn btn--small">Add to cart</a>
              </div>
            </div>
          </figure>

          <figure class="chair">
            <img src="chair-3.jpg" alt="Chair" />
            <div class="chair-box">
              <h3>The Chair 4/2</h3>
              <ul class="chair-details">
                <li>
                  <span>Leisure and relaxing</span>
                </li>
                <li>
                  <span>Comfortable all day!</span>
                </li>
                <li>
                  <span>Organic cotton</span>
                </li>
                <li>
                  <span>Weighs 80 kg</span>
                </li>
              </ul>
              <div class="chair-price">
                <strong>1450€</strong>
                <a href="#" class="btn btn--small">Add to cart</a>
              </div>
            </div>
          </figure>
        </div>
      </section>

      <footer>
        Copyright &copy; 2027 by Jonas Schmedtmann. Part of "Build Responsive
        Real-World Websites with HTML and CSS" online course. Use for learning
        purposes only.
      </footer>
    </div>
  </body>
</html>
```

```css
/*
SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* ------------------------ */
/* GENERAL STYLES */
/* ------------------------ */
body {
  font-family: sans-serif;
}

.container {
  width: 960px;
  margin: 0 auto;
}

header,
section {
  margin-bottom: 48px;
}

h2 {
  margin-bottom: 48px;
}

.grid-3-cols {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 80px;
}

/* ------------------------ */
/* COMPONENT STYLES */
/* ------------------------ */

/* HEADER */
header {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  column-gap: 80px;
  margin-top: 48px;
}

.header-text-box {
  align-self: center;
}

h1 {
  margin-bottom: 24px;
}

.header-text {
  margin-bottom: 24px;
}

img {
  width: 100%;
}

/* FEATURES */
.features-icon {
}

.features-title {
  margin-bottom: 16px;
}

.features-text {
}

/* TESTIMONIAL */
.testimonial-section {
}

.testimonial-box {
  grid-column: 2 / -1;
  align-self: center;
}

.testimonial-box h2 {
  margin-bottom: 24px;
}

.testimonial-text {
  font-style: italic;
  margin-bottom: 24px;
}

/* CHAIRS */
.chair-box {
  padding: 24px;
}

h3 {
  margin-bottom: 24px;
}

.chair-details {
  list-style: none;
  margin-bottom: 24px;
}

.chair-details li {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 24px;
}

.chair-details li:last-child {
  margin-bottom: 0;
}

.chair-icon {
}

.chair-price {
  display: flex;
  justify-content: space-between;
}

footer {
  margin-bottom: 48px;
}
```

## Overview of Web Design and Website Personalities (67)

[Page 81-92](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Wec Design Rules #1 : Typography (68)

[Page 95-107](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Implementing Typography (69)

- As we are cretaing a Website which creates modern minimilisic chair, we are going with minimilistic personality & with innovation

- We will use `inter` as typefaces, from the family of sans sarif

- **go to `font.google.com` & select what you want, 400, 500, 700, 800... (Do not go below 400 as a rule) and get the link from the website & Paste it in the head, before our css link tag**

- So it is also a stylesheet, but with a difference that this is a URL which comes from another server (Google here)

- Then in the Body, add the Typeface

```css
/* So if the internet has issue or any reason browser could not doenload the CSS, then it will show sans sarif, else, it willl show Inter 

So priority is Inter, then if it is not available, then use sans-sarif*/
body {
  font-family: "Inter", sans-serif;
}
```

- Font Size : Choose one of this different Option below

```
FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
```

- Also you can visit type-scale.com

---

```css
/*
SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* ------------------------ */
/* GENERAL STYLES */
/* ------------------------ */
body {
  /* Typography */
  font-family: "Inter", sans-serif;
}

.container {
  width: 960px;
  margin: 0 auto;
}

header,
section {
  margin-bottom: 48px;
}

h2 {
  margin-bottom: 48px;

  /* Typography */
  /*  24 / 30 / 36 */
  font-size: 36px;
  letter-spacing: -0.5px;
}

.grid-3-cols {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 80px;
}

/* ------------------------ */
/* COMPONENT STYLES */
/* ------------------------ */

/* HEADER */
header {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  column-gap: 80px;
  margin-top: 48px;
}

.header-text-box {
  align-self: center;
}

h1 {
  margin-bottom: 24px;

  /*  44 / 52 / 62 */
  /* Typography */
  font-size: 44px;
  line-height: 1.1;

  letter-spacing: -1px;
}

.header-text {
  margin-bottom: 24px;
  /* Typography */
  /* 18 / 20 / 24 */
  font-size: 18px;
  line-height: 1.7;
}

img {
  width: 100%;
}

/* FEATURES */
.features-icon {
}

.features-title {
  margin-bottom: 16px;

  /* Typography */
  font-size: 20px;
}

.features-text {
  /* Typography */
  font-size: 18px;
  line-height: 1.7;
}

/* TESTIMONIAL */
.testimonial-section {
}

.testimonial-box {
  grid-column: 2 / -1;
  align-self: center;
}

.testimonial-box h2 {
  margin-bottom: 24px;
  /* Typography */
  /* 20/24/30 */
  font-size: 24px;
}

.testimonial-text {
  font-style: italic;
  margin-bottom: 24px;

  /* Typography */
  font-size: 18px;
  line-height: 1.7;
}

/* CHAIRS */
.chair-box {
  padding: 24px;
}

h3 {
  margin-bottom: 24px;
  /* Typography */
  font-size: 20px;
}

.chair-details {
  list-style: none;
  margin-bottom: 24px;
}

.chair-details li {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 24px;
}

.chair-details li:last-child {
  margin-bottom: 0;
}

.chair-icon {
}

.chair-price {
  display: flex;
  justify-content: space-between;
  /* Typography */
  font-size: 20px;
}

footer {
  margin-bottom: 48px;
  /* Typography */
  font-size: 14px;
}
```

- We did not justified any text
- We did not center any text
- We do not have any text which is longer than 75 characters

---

## Web Design Rules #2 (Colors)

[Page 110-124](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Implementing Colors (71)

- We can see more green in the image & Also the shop focuses on Health, >> So color green can be a good choice. As Green stands for nature, growth & Health

- Search > Open Color > `yeun.github.com/open-color/`

- Copy the hexa decimal code

- Now we will geneaate shades & Tint of this color . We will get it from the website near to our main color

- Select a Grey Also for text

```css
/* MAIN COLOR #087f5b
  GREY COLOR #343a40

*/
```

- For testing the Visibility > We can take the Background color & Text Color > Go to Coolers.co > Contrast Checker > We will get ranking

---

```css
/*
SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
*/

/* MAIN COLOR #087f5b
    TINT : #099268
  GREY COLOR #343a40
  Tint of Gerey : #495057

*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* ------------------------ */
/* GENERAL STYLES */
/* ------------------------ */
body {
  font-family: "inter", sans-serif;
  /* Adding Text Color 🆕🆕 */
  color: #343a40;
  border-bottom: 8px solid #087f5b;
}

.container {
  width: 960px;
  margin: 0 auto;
}

header,
section {
  margin-bottom: 48px;
}

h2 {
  margin-bottom: 48px;
  /* 24/30/ 36 / 44 / 52 */
  font-size: 36px;
  letter-spacing: -0.5px;
}

.grid-3-cols {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 80px;
}

/* 🆕🆕🆕 */
.btn:link,
.btn:visited {
  background-color: #087f5b;
  color: #fff;
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 600;

  display: inline-block;
}
/* 🆕🆕🆕 */
.btn:hover,
btn:active {
  background-color: #099268;
}

/* 🆕🆕🆕 */

.btn--big {
  font-size: 18px;
  padding: 16px 32px;
}

/* 🆕🆕🆕 */

.btn--small {
  font-size: 14px;
  padding: 8px 12px;
}

/* ------------------------ */
/* COMPONENT STYLES */
/* ------------------------ */

/* HEADER */
header {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  column-gap: 80px;
  margin-top: 48px;
}

.header-text-box {
  align-self: center;
}

h1 {
  /* 44, 52,62  */
  font-size: 44px;
  line-height: 1.1;
  letter-spacing: -1px;
  margin-bottom: 24px;
}

.header-text {
  margin-bottom: 24px;
  /* 18 / 20 / 24 */
  font-size: 18px;
  line-height: 1.7;
}

img {
  width: 100%;
}

/* FEATURES */
.features-icon {
}

.features-title {
  margin-bottom: 16px;
  font-size: 20px;
}

.features-text {
  font-size: 18px;
  line-height: 1.7;
}

/* TESTIMONIAL */
.testimonial-section {
  /* Coloring entire section */
  background-color: #087f5b;
  color: #fff;
  padding: 24px;
}

.testimonial-box {
  grid-column: 2 / -1;
  align-self: center;
}

.testimonial-box h2 {
  margin-bottom: 24px;
  font-size: 24px;
}

.testimonial-text {
  font-style: italic;
  margin-bottom: 24px;
  font-size: 18px;
  line-height: 1.7;
}

/* CHAIRS */
.chair-box {
  padding: 24px;
}

h3 {
  margin-bottom: 24px;
  font-size: 20px;
}

.chair-details {
  list-style: none;
  margin-bottom: 24px;
}

.chair-details li {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 24px;
}

.chair-details li:last-child {
  margin-bottom: 0;
}

.chair-icon {
}

.chair-price {
  display: flex;
  justify-content: space-between;
  font-size: 20px;
}

/* 🆕🆕 */
footer {
  margin-bottom: 48px;
  /* 12 / 14 / 16 */
  font-size: 14px;
  color: #495057;
}
```

---

![Image](./asset_HTML_CSS/Screenshot%202024-02-29%20124110.png)

## Web Design Rule #3: Images & Illustrations (72)

[Page 127-147](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Web Design Rule #4: Icons (73)

[Page 150-160](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Implementing Icons (74)

- First We Need to get Icons Pack. So We are going to `heroicons.com` & will use this

- There are different ways to implement SVG in HTML

- One of the way is to download actual SVG files & incorporate into HTML just like regural images. However it has couple of limitation.

- 2nd way is to copy the SVG code. That works because SVG is just code. This is similar specification to HTML, but basically to describe design

---

- FEATURE BLOCK

- Most common usecases of ICONS is to create feature blocks. Where we have icons, like here at the TOP, then some heading & then some description.

- So copy the SVG Code. And Paste it in the HTML & Give a Proper class name, instead of the default className

---

- VISUAL ASSISTANT TO TEXT

- One of the usecase of icons is giving visual assistant to text

---

- We did not make the icons too big & also we tried to choose the icons which makes sense

![Image](./asset_HTML_CSS/Screenshot%202024-02-29%20175818.png)

```html
<li>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    fill="none"
    viewBox="0 0 24 24"
    stroke-width="1.5"
    stroke="currentColor"
    class="chair-icon"
  >
    <path
      stroke-linecap="round"
      stroke-linejoin="round"
      d="M9.813 15.904 9 18.75l-.813-2.846a4.5 4.5 0 0 0-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 0 0 3.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 0 0 3.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 0 0-3.09 3.09ZM18.259 8.715 18 9.75l-.259-1.035a3.375 3.375 0 0 0-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 0 0 2.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 0 0 2.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 0 0-2.456 2.456ZM16.894 20.567 16.5 21.75l-.394-1.183a2.25 2.25 0 0 0-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 0 0 1.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 0 0 1.423 1.423l1.183.394-1.183.394a2.25 2.25 0 0 0-1.423 1.423Z"
    />
  </svg>

  <!--Span is a generic INLINE text element, it doesn't have any meaning. It's like a div element, but inline -->
  <span>Leisure and relaxing</span>
</li>
```

```css
.chair-icon {
  /* While Stilinf the color of SVG icon, we have two property, Stroke & Fill. If it is a Outline SVG, Use Stroke, & if it is a Solid Icon, use Fill  */
  stroke: #087f5b;
  /* fill: #087f5b; */
  width: 24px;
  height: 24px;
}

.features-icon {
  /* To chnage the color */
  stroke: #087f5b;
  width: 40px;
  height: 40px;
  margin-bottom: 16px;
}
```

## Web Design Rules #5: Shadows (75)

[Page 163-174](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

---

## Implementing Shadows (76)

- We will add shadow each of these cards, and these are the common usecases of shadows. To add a Medium Size Shadow in Product Cart.

SEMENTIC HTML :

- We use Figure Element, Article Element to Describe Product Cart Like This
- We Use Section Element to Describe Whole Section of out of one section in Webpage

---

```css
.chair {
  /*
  
  1st Value :  We can Specify the length, which will then be the Horizontal offset between the box & shadow
  
  2nd Value for  Vertical Direction, Basically Offset in Vertical Drection between box & shadow

  3rd Value is the Blur of the shadow

  4th Value : OPTIONAL -  It allows basically to scale the shadow up (Kind of Radius)

  5th Value : Color of the Shadow. We May Use RGBA Notation also
  
  */
  /* box-shadow: 20px 20px 20px 10px rgba(0, 0, 0, 0.5); */

  /* Best Practice */
  box-shadow: 0px 20px 30px 0px rgba(0, 0, 0, 0.07);

  /*TEXT SHADOW */
  /* in Text Shadow we have the first 3 values (Line box shadow) & the last one 5th Value */
  /* Best Practice */
  /* 🟢 Text Shadow is useful when you have text on top of an image */
  /* text-shadow: 0px 5px 5px rgba(0, 0, 0, 0.2); */
}
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-01%20050952.png)

## Web Design Rules #6: Border-Radius (77)

[Page 176-182](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Implementing Border Radius (78)

```css
.btn:link,
.btn:visited {
  background-color: #087f5b;
  color: #fff;
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 600;

  display: inline-block;
  /* There are two ways of doing it, But one only works when the element is square
  
  - So if the element is square, to make it round, we give border radius of 50%
  
  Since, in our case, it is not square, We have to use a big value, like 100px, - It can not be less than the height 
  */
  border-radius: 100px;
}

/* We are applying Border radius in all the images */
img {
  border-radius: 12px;
}

.testimonial-section {
  /* Coloring entire section */
  background-color: #087f5b;
  color: #fff;
  padding: 24px;
  border-radius: 12px;
}

/* CHAIRS */
.chair {
  box-shadow: 0px 20px 30px 0px rgba(0, 0, 0, 0.07);
  border-radius: 12px;
}

/* Removing the Below Image */
.chair img {
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-01%20061532.png)

![image](./asset_HTML_CSS/Screenshot%202024-03-01%20061555.png)

---

## Web Design Rules #7: Whitespace (79)

[Page 185-197](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Web Design Rules #8 :Visual Hirerchy (80)

[Page 199-217](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Implementing Whitespace and Visual Hierarchy (81)

**BEFORE**

![image](./asset_HTML_CSS/Screenshot%202024-03-01%20080723.png)

![Image](./asset_HTML_CSS/Screenshot%202024-03-01%20100311.png)

- Currently We have implemented some visual Hirerchy Already. Like first the user will see the image, then Header Then Button.. Also in the bottom part, we have implemented some other visual hirerchy to emphasize the testimonial by giving it a Background color.

- Between the Section, We have less white Space, We need to add more. Means a Ton of White SPace. if needed.

- We also add some spaces between Elements and reduced some space to make it more inlined with proximity principle. Here, in the Header Text, Then in the 2ns Section, icons and the Text benith of it, got more space, and we have a testimonual section, where we can give light green color text.

- Also in Cart Card, Article, We have used Porximity Rule

```css
/*
SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
*/

/* MAIN COLOR #087f5b
    TINT : #099268
  GREY COLOR #343a40
  Tint of Gerey : #495057

*/

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* ------------------------ */
/* GENERAL STYLES */
/* ------------------------ */
body {
  font-family: "inter", sans-serif;
  color: #343a40;
  border-bottom: 8px solid #087f5b;
}

.container {
  width: 960px;
  margin: 0 auto;
}

header,
section {
  /* SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128 */
  /* 🆕🆕 */
  margin-bottom: 128px;
}

h2 {
  margin-bottom: 48px;
  /* 24/30/ 36 / 44 / 52 */
  font-size: 36px;
  letter-spacing: -0.5px;
}

.grid-3-cols {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 80px;
}

.btn:link,
.btn:visited {
  background-color: #087f5b;
  color: #fff;
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 600;

  display: inline-block;
  /* There are two ways of doing it, But one only works when the element is square
  
  - So if the element is square, to make it round, we give border radius of 50%
  
  Since, in our case, it is not square, We have to use a big value, like 100px, - It can not be less than the height 
  */
  border-radius: 100px;
}

.btn:hover,
btn:active {
  background-color: #099268;
}

.btn--big {
  font-size: 18px;
  padding: 16px 32px;
}

.btn--small {
  font-size: 14px;
  padding: 8px 12px;
}

/* We are applying Border radius in all the images */
img {
  border-radius: 12px;
}

/* ------------------------ */
/* COMPONENT STYLES */
/* ------------------------ */

/* HEADER */
header {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  column-gap: 80px;
  /* SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128 */
  /* 🆕🆕 */
  margin-top: 64px;
}

.header-text-box {
  align-self: center;
}

h1 {
  /* 44, 52,62  */
  font-size: 44px;
  line-height: 1.1;
  letter-spacing: -1px;
  /* 🆕🆕 */
  margin-bottom: 48px;
}

.header-text {
  margin-bottom: 24px;
  /* 18 / 20 / 24 */
  font-size: 18px;
  line-height: 1.7;
}

img {
  width: 100%;
}

/* FEATURES */
.features-icon {
  /* To chnage the color */
  stroke: #087f5b;
  width: 40px;
  height: 40px;
  /* 🆕🆕 */
  margin-bottom: 24px;
}

.features-title {
  margin-bottom: 16px;
  font-size: 20px;
}

.features-text {
  font-size: 18px;
  line-height: 1.7;
}

/* TESTIMONIAL */
.testimonial-section {
  /* Coloring entire section */
  background-color: #087f5b;
  color: #fff;
  padding: 24px;
  border-radius: 12px;
}

.testimonial-box {
  grid-column: 2 / -1;
  align-self: center;
}

.testimonial-box h2 {
  margin-bottom: 24px;
  font-size: 24px;
}

.testimonial-text {
  font-style: italic;
  margin-bottom: 24px;
  font-size: 18px;
  line-height: 1.7;
  /* 🆕🆕 */
  color: #c3fae8;
}

.testimonial-author {
  color: #63e6be;
}

/* CHAIRS */
.chair {
  box-shadow: 0px 20px 30px 0px rgba(0, 0, 0, 0.07);
  border-radius: 12px;
}

.chair img {
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}

.chair-box {
  /* 🆕🆕 */
  padding: 32px;
}

h3 {
  margin-bottom: 24px;
  font-size: 20px;
}

.chair-details {
  list-style: none;
  /* 🆕🆕 */
  margin-bottom: 64px;
}

.chair-details li {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 16px;
}

.chair-details li:last-child {
  margin-bottom: 0;
}

.chair-icon {
  /* While Stilinf the color of SVG icon, we have two property, Stroke & Fill. If it is a Outline SVG, Use Stroke, & if it is a Solid Icon, use Fill  */
  stroke: #087f5b;
  /* fill: #087f5b; */
  width: 24px;
  height: 24px;
}

.chair-price {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 20px;
}

footer {
  margin-bottom: 48px;
  /* 12 / 14 / 16 */
  font-size: 14px;
  color: #495057;
}
```

## Web Design Rules #9: User Experience (UX) (82)

[Page 219-233](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## The Website-Personalities-Framework (83)

[Page 235-255](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## The Missing Piece : Steal Like An Artist! (84)

- Website Personalities + Design Ingredients + Design Guidelines/Rules + `GETTING INSPIRED & STEALING LIKE AN ARTIST`

- So Not completely Copying a design! Instead, it's about taking good parts and adapting them to our needs.

---

- He uses couple of aggregator sides which features a lot of great designs all the time.

These are : 1. Land Book.com 2. Onepagelove.com 3. awwwards.com 4. screenlane.com

---

**Lets Start**:

Suppose we have selected in a startup company, where we have given a task to create a startup/upbeat personality website. So with this we already know how we should actually apply each of these ddesign ingredients according to their personality.

Now go to these sides, ans get inspiration

**The End**
01-03-2024
