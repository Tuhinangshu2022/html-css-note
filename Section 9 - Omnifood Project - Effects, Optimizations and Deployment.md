# Omnifood Project - Effects, Optimizations and Deployment

## Section Intro (137)

- No Important Info

## A Short Description to JavaScript (138)

- Connect Script in

```html
<!-- In the head -->
<script defer src="./JS/script.js"></script>
```

```html
<p class="copyright">
  Copuright &copy; <span class="year">2027</span> by Omnifood, Inc. All rights
  reserved.
</p>
```

```js
console.log("hello");

const myName = "Tuhinangshu Choudhury";
console.log(myName);

// Selecting a Element
const h1 = document.querySelector(".heading-primary");
console.log(h1); //<h1 class="heading-primary">

// h1.textContent = myName; //<h1 class="heading-primary">Tuhinangshu Choudhury</h1>
// h1.style.backgroundColor = "red"; //<h1 class="heading-primary" style="background-color: red;">Tuhinangshu Choudhury</h1>
// h1.style.padding = "5rem"; //<h1 class="heading-primary" style="background-color: red; padding: 5rem;">Tuhinangshu Choudhury</h1>

// We can listen for a listner

/*
h1.addEventListener("click", function () {
  h1.textContent = myName;
  h1.style.backgroundColor = "red";
  h1.style.padding = "5rem";
});
*/

// To add Copyright Date everytime
const yearEl = document.querySelector(".year");
yearEl.textContent = new Date().getFullYear();
```

## Making the Mobile Navigation Work (139)

```js
//Make Mobile Navigation Work
//We want to make that, when the button is clicked, the class ".open-nav" we need to add in header. That's it

const btnNavEl = document.querySelector(".btn-mobile-nav");
const headerEl = document.querySelector(".header");

btnNavEl.addEventListener("click", function () {
  headerEl.classList.toggle("nav-open");
});
```

- One Problem We saw, When we click on the Button, the focus state does not appear over the Menu, So to fix it

```css
.btn-mobile-nav {
  display: block;
  z-index: 999;
}
```

## Implementing Smooth Scrolling (140)

- First We need to update the Links

- So where we want to reach, we need an id for it, then we can use the id in the href

```html
<a href="#cta" class="btn btn--full margin-right-sm">Start eating well</a>

<!-- More Code -->

<!-- CTA SECTION -->
<!-- We have added a ID -->
<section class="section-cta" id="cta">
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

- After adding all the href in nav. We can proceed.

- In General.css

```css
html {
  /* font-size: 10px; */
  font-size: 62.5%;
  overflow-x: hidden;

  /* Added Scroll behaviour 
  Does Not work in Safari & Microsoft edge*/
  scroll-behavior: smooth;
}
```

- It would work in all browser, But In Safari, it would not work.
- For to make it work in Safari, lets do something in safari

- Also we need to add this Script

```html
<!-- For using in Safari, the Scroll Behaviour -->
<script
  defer
  src="https://unpkg.com/smoothscroll-polyfill@0.4.4/dist/smoothscroll.min.js"
></script>
```

```js
// Smoth Scrolling Animation
// Let's select all the links, So anchor element which has anchor property
const allLinks = document.querySelectorAll("a:link");
console.log(allLinks); //NodeList(28)

//1. As all links is a NodeList, a Iterator, so We are adding using forEach to add event Listner one by one
allLinks.forEach(function (link) {
  // 2. We have the access to the event
  link.addEventListener("click", function (e) {
    console.log(e); //PointerEvent
    //3. Default Behaviour is If we click on links, it would scroll to the href. So we are restricting it
    e.preventDefault();

    //4. Reading the href attribute
    const href = link.getAttribute("href");
    console.log(href); //#cta, #how etc.....

    //5. scroll back to top
    if (href === "#")
      window.scrollTo({
        // We use scrollTo when we know the pixel value
        top: 0, // 20, 30.. So these are pixel
        behavior: "smooth",
      });

    //For all the Href which strats with "#", Scroll to Other links
    if (href !== "#" && href.startsWith("#")) {
      console.log(href); //It comes as #cta, #how..etc
      // So basically they will work as Id Selector, because they have # with them
      const sectionEl = document.querySelector(href);
      console.log(sectionEl);
      sectionEl.scrollIntoView({
        // We use scrollIntoView, when we do not know the Pixel value,
        behavior: "smooth",
      });
    }

    // Close Mobile Navigation. I.e, if the Mobile Navigation is Opened, then we need to close it
    if (link.classList.contains("main-nav-link")) {
      headerEl.classList.toggle("nav-open");
    }
  });
});
```

## Implementing a Sticky Navigation Bar (141)

Style.css

```css
/* STICKY NAVIGATION */
.sticky .header {
  /* It will fix the elemeent in the view port, and will not move as we scroll, This will come out of the flow like position absolute */
  position: fixed;
  top: 0;
  bottom: 0;
  /* Allow it to be in 100% of the viewport */
  width: 100%;
  /* Giving a Fixed Height */
  height: 8rem;

  /* No idea why it is added */
  padding-top: 0;
  padding-bottom: 0;

  background-color: rgba(255, 255, 255, 0.97);
  z-index: 9999;

  box-shadow: 0 1.2rem 3.2rem rgba(0, 0, 0, 0.03);
}

/* As it is jumping becuase, it come out of the flow all of a sudden and section hero looses its header from the top (9.6rem), we are adding some margin top for compasioonate in the section hero.  */

/* So Basically, We need a sticky class in Parent, so that we can add margin top in Section hero for making it work. SO lets add it in the body */
.sticky .section-hero {
  margin-top: 9.6rem;
}
```

```js
// STICKY NAVIGATION FUNCTIONALITIES
// We want this to be sticky, when it crosses the Hero Section
const sectionHeroEl = document.querySelector(".section-hero");

// We wil use intersection Observer API
// In the perameter, we want what I want it to happen, so basically a function & in Second, we want some option here
const obs = new IntersectionObserver(
  function (entires) {
    //3.. We will have acces of array of entries. So we will have one entry for each thrashhold value
    // This wil have only one Element, so we can take it out by [0]
    const ent = entires[0];
    console.log(ent); //IntersectionObserverEntry

    //4. if intersection == false, we will add an class to header
    if (ent.isIntersecting === false) document.body.classList.add("sticky");
    if (ent.isIntersecting === true) document.body.classList.remove("sticky");
  },
  {
    //2.
    // In the View Port.
    //Root == Null, means we will observe inside of the view port
    root: null,
    //So this will create a event when 0% section of the element is outside of the view port
    //We could have a value like 1, it means our observing element is completely inside of the view port (100% Visibility)
    //But here we are using 0, as we want to get an event as soon as the hero section moves out completely of the view port (100% Outside)
    threshold: 0,
    // Rootmargin is applied outside of the root
    // So basically we want that when -80px remianing before fully invisibility, we want the event to fire, It is 80px, beacuse it the height of the navigation bar
    rootMargin: "-80px",
  }
);

// 1. We will Observe some element in the HTML using the intersectionObserver, And in this case, this Hero Section
obs.observe(sectionHeroEl);
```

## Browser Supprt & Fixing Flexbox Gap in Safari (142)

![image](./asset_HTML_CSS/Screenshot%202024-03-15%20183859.png)

- CSS Property whether it works or not in browser, we can take help of the website
  `caniuse.com`

- We can search the Css-property & check whether it supports or not

- Example: Backdrop-filter Property Does not work in Safari. It creates a Blur effect in the content which in behind

![image](./asset_HTML_CSS/Screenshot%202024-03-15%20185343.png)

query.css

```css
.main-nav {
  /* background-color: rgba(232, 232, 237, 0.928); */
  background-color: rgba(232, 232, 237, 0.5);

  /* BACKDROP FILTER __ BLUR */
  backdrop-filter: blur(10px);

  /* Make it absoutely Positioned */
  position: absolute;
  top: 0;
  left: 0;

  height: 100vh;
  width: 100%;

  transform: translateX(100%);

  display: flex;
  align-items: center;
  justify-content: center;

  transition: all 0.5s ease-in;

  opacity: 0;
  pointer-events: none;
  visibility: hidden;
}
```

- in Safari, it does not work,, So not blured
- So we need to use `webkit` prefix to solve

```css
.main-nav {
  /* background-color: rgba(232, 232, 237, 0.928); */
  background-color: rgba(232, 232, 237, 0.5);

  /* BACKDROP FILTER __ BLUR */
  -webkit-backdrop-filter: blur(10px);
  backdrop-filter: blur(10px);

  /* Make it absoutely Positioned */
  position: absolute;
  top: 0;
  left: 0;

  height: 100vh;
  width: 100%;

  transform: translateX(100%);

  display: flex;
  align-items: center;
  justify-content: center;

  transition: all 0.5s ease-in;

  opacity: 0;
  pointer-events: none;
  visibility: hidden;
}
```

- in Firefox, it works as well, but in Video, it was telling that it does not work, but in 2024. it works fine

- These are called vendor prefix `-webkit-`

---

- So we learnt what browser support is, & also very important tool here to check how well a certain CSS Property that we might want to use is supported across all browser, and also we learnt how to use vendor prefixes, to make a css property work across multiple browser.

- In this case, we used `backdrop prperty`

---

- Now Also an important thing, which is to fix the gap property in Flexbox for the Safari Browser

- Upuntill 2021, flexbox did not work properly in Safari. Basically the gap property. So for few years, use it because some people may use old safari version

```js
// Fixing flexbox gap property missing in some Safari versions
function checkFlexGap() {
  var flex = document.createElement("div");
  flex.style.display = "flex";
  flex.style.flexDirection = "column";
  flex.style.rowGap = "1px";

  flex.appendChild(document.createElement("div"));
  flex.appendChild(document.createElement("div"));

  document.body.appendChild(flex);
  var isSupported = flex.scrollHeight === 1;
  flex.parentNode.removeChild(flex);
  console.log(isSupported);

  if (!isSupported) document.body.classList.add("no-flexbox-gap");
}
checkFlexGap();
```

Now go to Queiries, and add it in Query.css

```css
.no-flexbox-gap .main-nav-list li:not(:last-child) {
  margin-right: 4.8rem;
}

.no-flexbox-gap .list-item:not(:last-child) {
  margin-bottom: 1.6rem;
}

.no-flexbox-gap .list-icon:not(:last-child) {
  margin-right: 1.6rem;
}

.no-flexbox-gap .delivered-faces {
  margin-right: 1.6rem;
}

.no-flexbox-gap .meal-attribute:not(:last-child) {
  margin-bottom: 2rem;
}

.no-flexbox-gap .meal-icon {
  margin-right: 1.6rem;
}

.no-flexbox-gap .footer-row div:not(:last-child) {
  margin-right: 6.4rem;
}

.no-flexbox-gap .social-links li:not(:last-child) {
  margin-right: 2.4rem;
}

.no-flexbox-gap .footer-nav li:not(:last-child) {
  margin-bottom: 2.4rem;
}

@media (max-width: 75em) {
  .no-flexbox-gap .main-nav-list li:not(:last-child) {
    margin-right: 3.2rem;
  }
}

@media (max-width: 59em) {
  .no-flexbox-gap .main-nav-list li:not(:last-child) {
    margin-right: 0;
    margin-bottom: 4.8rem;
  }
}
```

## Testing Performance with Lighthouse (143)

- Nothing to write, Just read it in Lighthouse, what are the issues

## Adding Favicon and Meta Description (144)

- Meta Description is a Short Summary of our website's content. And also the text that will appear for each of the search results in Google and Other Search Engine

- Also We need to Give Proper Title

- Also we need to add a icon, in the Website Tab, This icon is called fav-icon. So Before that we need to resize the image for better performace, 64X64

- We add website in Homescreen in Android & Apple Devices. So We need a Icon for that. For thais we need resolution

  - Apple - 180x180
  - Android - 192X192
  - Andorid - 512X512

  ```html
  <meta
    name="description"
    content="Omnifood is an AI-Powered food subscription that will make you eat healthy again, 365 days per year. It's tailored to your personal taste & nutritional needs. "
  />

  <link rel="icon" href="./img/favicon.png" />
  <link rel="apple-touch-icon" href="./img/apple-touch-icon.png" />

  <title>Omnifood &mdash; Never cook again</title>
  ```

  - For Android, it works little bit different. We have to create a file `manifest.webmanifest`

  - This is kind of a file extension that is used for androis to recognise a different favicons basically.

  ```js
  {
    "icons": [
      {
        "src": "./img/favicon-192.png",
        "type": "image/png",
        "sizes": "192x192"
      },
      {
        "src": "./img/favicon-512.png",
        "type": "image/png",
        "sizes": "512x512"
      }
    ]
  }
  ```

  ```html
  <link rel="manifest" href="./manifest.webmanifest" />
  ```

## Image Optimizations (145)

- So our basic principle is , the actual image size, so the image file itself should always be double of the size that is actually displayed on the screen.

- Why? The Reason we need an image that is double the size than is actually displayed on the screen, is that the high density screens actually need two pixels of the image to display one pixel in design

- Intrinsic Size is the actual size of the image (file), and rendered size in on Screen

![image](./asset_HTML_CSS/Screenshot%202024-03-16%20124707.png)

So Rendered Image should be 1 & intrinsic Size should be 2

![image](./asset_HTML_CSS/Screenshot%202024-03-16%20134032.png)

---

So first use image > Check its renders size > Then Risize the File to double > Save it

---

---

**NOW WE NEED TO COMPRESS THE IMAGE SIZE, AS BIGGER FILE WILL MAKE THE WEBSITE SLOWER**

- Go to `squoosh.app` > Compress the File > Replace the file in > The Best is we can go for WEBP format. & Make some chnages to find the right size

---

```html
<div class="hero-img-box">
  <!-- <img
              src="./img/hero-mini.png"
              alt="Woman enjoying food, meals in storgae container and food bowls on a table"
              class="hero-img"
            /> -->
  <img
    src="./img/hero.webp"
    alt="Woman enjoying food, meals in storgae container and food bowls on a table"
    class="hero-img"
  />
</div>
```

- But still there is a doubt, whether we can use webp in Browser, So to check, we need to see in `caniuse.app` > webp

![Image](./asset_HTML_CSS/Screenshot%202024-03-16%20173917.png)

---

- So we found, in Some Version of Safari, it does not work. So there is a Trick to solve it

```html
<div class="hero-img-box">
  <!-- Inside of Picture, we will define our two possible image, So we will use webp & comporessed png both
            
            And Browser will decide, which image it can show-->
  <picture>
    <source srcset="./img/hero.webp" type="image/webp" />
    <source srcset="./img/hero-mini.png" type="image/png" />

    <!-- In Image element, we use src = Fallback, Basically the fallback , which is basically all the browser should basically able to render -->
    <img
      src="./img/hero-mini.png"
      alt="Woman enjoying food, meals in storgae container and food bowls on a table"
      class="hero-img"
    />
  </picture>
</div>
```

![Image](./asset_HTML_CSS/Screenshot%202024-03-16%20175353.png)

- This is how we can maintain high performance image quality with WEBP. Also taking care of the fact that if user does not have new version of browswr, it will open the old png format also..

- Basically very important for the User Perspective

## Deployment to Netlify (146)

- No Note

## Making the Form Work with Netlify Forms (147)

Lets make the signup form Work with Netlify.

- So in Netlify, We have an Option : Forms > And Follow the DOCS. It is easy

---
