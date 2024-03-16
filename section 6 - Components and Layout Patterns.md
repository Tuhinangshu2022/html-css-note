# Components and Layout Patterns

## Section Intro (85)

- We will Learn About Components & Layouts

## Web Design Rules #10 - Part 1 : Elements & Components (86)

[Page 258-302](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Building ann Accordian Component - Part 1 (87)

![Image](./asset_HTML_CSS/Screenshot%202024-03-01%20192357.png)

Create a New Folder - 06 Components

![image](./asset_HTML_CSS/Screenshot%202024-03-01%20200346.jpg)

![Image](./asset_HTML_CSS/Screenshot%202024-03-01%20200547.png)

- We did some code, but it is half done. So will continue next. No need to take note

- We first Added Element, then stylaized it

## Building an Accordian Component - Part 2 (88)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <!-- Google Font Link -->
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&display=swap"
      rel="stylesheet"
    />
    <title>Document</title>

    <style>
      /*
      SPACING SYSTEM (px)
      2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

      FONT SIZE SYSTEM (px)
      10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
      */

      /* 
      
        MAIN COLOR #087f5b
        TINT : #099268
        GREY COLOR #343a40
        Tint of Gerey : #495057

      */

      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        font-family: "inter", sans-serif;
        color: #343a40;
        line-height: 1;
      }

      .accordian {
        width: 700px;
        /* Centering */
        margin: 100px auto;
        display: flex;
        flex-direction: column;
        gap: 20px;
      }

      .item {
        box-shadow: 0 0 32px rgba(0, 0, 0, 0.1);
        padding: 24px;
        display: grid;
        /* TO give Column Width : 
        if we want the column to be in content size, we use auto
        If we want the column to occupy the remaining space, we use 1fr
         */
        grid-template-columns: auto 1fr auto;
        column-gap: 24px;
        row-gap: 32px;
      }

      .number,
      .text {
        font-size: 24px;
        font-weight: 500;
      }

      .number {
        color: #ced4da;
      }
      .icon {
        width: 24px;
        height: 24px;
        stroke: #099268;
      }
      .hidden-box {
        grid-column: 2;
        display: none;
      }

      .hidden-box p {
        line-height: 1.6;
        margin-bottom: 24px;
      }

      .hidden-box ul {
        color: #868e96;
        margin-left: 20px;
      }

      /* THIS CAN BE DONE IN MUCH EASIER WAY WITH FLEXBOX */
      /* .hidden-box li {
        margin-bottom: 12px;
      }

      .hidden-box li:last-child {
        margin-bottom: 0;
      } */

      /* 🆕🆕 Now we will use flex instead of old way of adding margin */
      .hidden-box ul {
        display: flex;
        /* Making the flex vertical */
        flex-direction: column;
        gap: 12px;
      }

      /* 🆕🆕VERY IMPORTANT 
      OPEN STATE : Making a Class for Open */
      .open {
        border-top: 10px solid #099268;
      }

      .open .hidden-box {
        display: block;
      }

      .open .number,
      .open .text {
        color: #099268;
      }
    </style>
  </head>
  <body>
    <div class="accordian">
      <div class="item">
        <p class="number">01</p>
        <p class="text">Where are these chairs assembled?</p>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="m19.5 8.25-7.5 7.5-7.5-7.5"
          />
        </svg>
        <div class="hidden-box">
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eaque
            animi cupiditate distinctio doloremque labore modi, quos sed
            consectetur, repudiandae pariatur harum sapiente saepe quas autem
            corrupti nam! Reprehenderit, itaque aut.
          </p>

          <ul>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
          </ul>
        </div>
      </div>

      <div class="item open">
        <p class="number">02</p>
        <p class="text">How long do I have to return my chair?</p>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="m19.5 8.25-7.5 7.5-7.5-7.5"
          />
        </svg>
        <div class="hidden-box">
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eaque
            animi cupiditate distinctio doloremque labore modi, quos sed
            consectetur, repudiandae pariatur harum sapiente saepe quas autem
            corrupti nam! Reprehenderit, itaque aut.
          </p>

          <ul>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
          </ul>
        </div>
      </div>

      <div class="item">
        <p class="number">03</p>
        <p class="text">Do you ship to countries outside the EU?</p>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="m19.5 8.25-7.5 7.5-7.5-7.5"
          />
        </svg>
        <div class="hidden-box">
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eaque
            animi cupiditate distinctio doloremque labore modi, quos sed
            consectetur, repudiandae pariatur harum sapiente saepe quas autem
            corrupti nam! Reprehenderit, itaque aut.
          </p>

          <ul>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
            <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
          </ul>
        </div>
      </div>
    </div>
  </body>
</html>
```

## Building a Carouser Component - Part 1 (89)

![image](./asset_HTML_CSS/Screenshot%202024-03-02%20100036.png)

- We add the element first, no css
- Then we style the element & then cretae the layout

## Building a Carousel Component - Part 2 (90)

![Image](./asset_HTML_CSS/Screenshot%202024-03-02%20121713.png)

- Translate function of Transform : it moves the element, the first is x, and the second is y
- 50% means 50% of its height

---

- What we learnt ?

  1. Padding with 4 values
  2. Transform - Scale ---- To scale an image
  3. Important tencnique to place an element anywhere we wanted by using the combination of absolute positioning & transform with translate

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <!-- Google Font Link -->
      <link
        href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&display=swap"
        rel="stylesheet"
      />
      <title>Carousel Component</title>
      <style>
        /*
      SPACING SYSTEM (px)
      2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128
  
      FONT SIZE SYSTEM (px)
      10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
      
        MAIN COLOR #087f5b
        TINT : #099268
        GREY COLOR #343a40
        Tint of Gerey : #495057
  
      */

        * {
          margin: 0;
          padding: 0;
          box-sizing: border-box;
        }

        body {
          font-family: "inter", sans-serif;
          color: #343a40;
          line-height: 1;
        }

        .carousel {
          background-color: #099268;
          width: 800px;
          /* Centening */
          margin: 100px auto;
          border-radius: 8px;
          /* padding: 32px; */
          display: flex;
          align-items: center;
          gap: 32px;
          /* Increaed the padding, after the sclae up */
          /* padding-left: 86px;
        padding-right: 48px; */

          /* Clock wise also we can define - top right bottom left */
          padding: 32px 48px 32px 86px;
          gap: 86px;
          position: relative;
        }

        img {
          height: 200px;
          border-radius: 8px;
          /* Transform is for many different things, one of them is to scale things
        scale is a function, if we write 1, it will be kept as it is, if we write 2, it would be double the size... */
          transform: scale(1.5);
          box-shadow: 0 12px 24px rgba(0, 0, 0, 0.25);
        }

        .testimonial-text {
          font-size: 18px;
          font-weight: 500;
          line-height: 1.5;
          margin-bottom: 32px;
          /* Visual Hirerchy */
          color: #e6fcf5;
        }
        .testimonial-author {
          font-size: 14px;
          margin-bottom: 4px;
          color: #c3fae8;
        }
        .testimonial-job {
          font-size: 12px;
          color: #c3fae8;
        }

        /* CONTROLS */
        .btn {
          background-color: #fff;
          /* Button as by default a border, so we need to remove it */
          border: none;
          height: 40px;
          width: 40px;
          box-shadow: 0 12px 24px rgba(0, 0, 0, 0.25);

          /* If we are doing, this, so this two button will no longer be in the flow */
          position: absolute;
          border-radius: 50%;

          /* For making the Button and Svg in center */
          display: flex;
          align-items: center;
          justify-content: center;

          cursor: pointer;
        }

        .btn--left {
          /* In Realtion to Parent Element */
          left: 0;
          top: 50%;

          /* In relation to Element itself */
          /* Translate function moves the element, first perameter is x, the second is y */
          transform: translate(-40%, -50%);
        }
        .btn--right {
          right: 0;

          /* 50% from start of parent to start of absolute element */
          top: 50%;
          /* Translate function moves the element, first perameter is x, the second is y */
          transform: translate(40%, -50%);
        }

        .btn-icon {
          height: 24px;
          width: 24px;
          stroke: #099268;
        }

        /* DOTS */
        .dots {
          position: absolute;
          left: 50%;
          bottom: 0;
          transform: translate(-50%, 32px);
          display: flex;
          gap: 12px;
        }

        .dot {
          height: 12px;
          width: 12px;
          background-color: #fff;
          border: 2px solid #099268;
          border-radius: 50%;
          cursor: pointer;
        }

        .dot--fill {
          background-color: #099268;
        }
      </style>
    </head>
    <body>
      <div class="carousel">
        <img src="./maria.jpg" alt="Image of Maria, Smiling" />

        <blockquote class="testimonial">
          <p class="testimonial-text">
            "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ad nam
            nulla doloremque, earum nihil id dolorum et esse autem qui quas
            dolorem"
          </p>

          <p class="testimonial-author">Maria de Almedia</p>
          <p class="testimonial-job">Senior Manager at EDP Commercial</p>
        </blockquote>

        <button class="btn btn--left">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="btn-icon"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15.75 19.5 8.25 12l7.5-7.5"
            />
          </svg>
        </button>

        <button class="btn btn--right">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="btn-icon"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="m8.25 4.5 7.5 7.5-7.5 7.5"
            />
          </svg>
        </button>
        <div class="dots">
          <button class="dot dot--fill">&nbsp;</button>
          <button class="dot">&nbsp;</button>
          <button class="dot">&nbsp;</button>
          <button class="dot">&nbsp;</button>
        </div>
      </div>
    </body>
  </html>
  ```

## Building a Table Component - Part 1 (91)

- Table are not used a lot in web developement

- In Past, people used to make Table with different Table tag, now with flex & grid, it became very easy to make Table

- But if we really want to represent some data set, table is really useful.

```html
<body>
  <table>
    <thead>
      <tr>
        <th>Chair</th>
        <th>The Laid Back</th>
        <th>The Worker Bee</th>
        <th>The Chair 4/2</th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <th>Width</th>
        <td>180 cm</td>
        <td>60 cm</td>
        <td>220 cm</td>
      </tr>

      <tr>
        <th>Height</th>
        <td>180 cm</td>
        <td>60 cm</td>
        <td>220 cm</td>
      </tr>

      <tr>
        <th>Depth</th>
        <td>180 cm</td>
        <td>60 cm</td>
        <td>220 cm</td>
      </tr>

      <tr>
        <th>Weight</th>
        <td>180 cm</td>
        <td>60 cm</td>
        <td>220 cm</td>
      </tr>
    </tbody>
  </table>
</body>
```

## Building a Table Component - Part 2 (92)

```css
  <!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- Google Font Link -->
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&display=swap"
      rel="stylesheet"
    />
    <title>Document</title>
    <style>
      /*
      SPACING SYSTEM (px)
      2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

      FONT SIZE SYSTEM (px)
      10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
      */

      /*

        MAIN COLOR #087f5b
        TINT : #099268
        GREY COLOR #343a40
        Tint of Gerey : #495057

      */

      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        font-family: "inter", sans-serif;
        color: #343a40;
        line-height: 1;
        /* Centering */
        display: flex;
        justify-content: center;
        align-items: center;
      }

      table {
        width: 800px;
        /* background-color: red; */

        /* Centering the table , We will do it alternative way*/
        /* margin: 30px auto; */

        margin-top: 100px;
        /* border: 1px solid #343a40; */

        /* If two border is nearby, it will be collapsed to 1 border */
        border-collapse: collapse;
        font-size: 18px;
      }

      td,
      th {
        /* border: 1px solid #343a40; */
        padding: 16px 24px;
        text-align: left;
      }

      thead th {
        background-color: #099268;
        color: azure;

        /* If I want to make width of same size of any row */
        width: 25%;
      }

      /* We will add zebra stripe, to make every alternative row in different color */
      tbody tr:nth-child(odd) {
        background-color: #f8f9fa;
      }

      tbody tr:nth-child(even) {
        background-color: #e9ecef;
      }
    </style>
  </head>
  <body>
    <table>
      <thead>
        <tr>
          <th>Chair</th>
          <th>The Laid Back</th>
          <th>The Worker Bee</th>
          <th>The Chair 4/2</th>
        </tr>
      </thead>

      <tbody>
        <tr>
          <th>Width</th>
          <td>180 cm</td>
          <td>60 cm</td>
          <td>220 cm</td>
        </tr>

        <tr>
          <th>Height</th>
          <td>180 cm</td>
          <td>60 cm</td>
          <td>220 cm</td>
        </tr>

        <tr>
          <th>Depth</th>
          <td>180 cm</td>
          <td>60 cm</td>
          <td>220 cm</td>
        </tr>

        <tr>
          <th>Weight</th>
          <td>180 cm</td>
          <td>60 cm</td>
          <td>220 cm</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>


```

![Image](./asset_HTML_CSS/Screenshot%202024-03-02%20193749.png)

## CHALLANGE #1 Building a Pagination Component (93)

- And Selector : class.class {} = It applies on the element if it has both of the classes, we do not use any space

- Descendent selector has space between them, like parent-class child-class {}

- Display flex : by default is a block level elemenet, so it takes whole row

```css
  <!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- Google Font Link -->
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&display=swap"
      rel="stylesheet"
    />
    <title>Document</title>
    <style>
      /*
      SPACING SYSTEM (px)
      2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

      FONT SIZE SYSTEM (px)
      10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
      */

      /*

        MAIN COLOR #087f5b
        TINT : #099268
        GREY COLOR #343a40
        Tint of Gerey : #495057

      */

      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        font-family: "inter", sans-serif;
        color: #343a40;
        line-height: 1;
        display: flex;
        justify-content: center;
      }

      .btn {
        border: 1px solid #099268;
        height: 48px;
        width: 48px;
        border-radius: 50%;
        background: none;
        cursor: pointer;
        display: flex;
        justify-content: center;
        align-items: center;
      }

      .btn:hover {
        background-color: #099268;
      }

      .btn:hover .btn-icon {
        stroke: aliceblue;
      }
      .btn-icon {
        height: 24px;
        width: 24px;
        stroke: #099268;
      }
      .page-links:link,
      .page-links:visited {
        font-size: 18px;
        color: #343a40;
        text-decoration: none;

        /* Making square size */
        height: 36px;
        width: 36px;
        border-radius: 50%;

        /* Centering  the text inside of the element */
        display: flex;
        justify-content: center;
        align-items: center;
      }

      .page-links:hover,
      .page-links:active {
        background-color: #099268;
        color: azure;
      }

      /* For the active Page Line

      WE USED AND OPERATOR : IT MEANS IF BOTH THE CLASS IS PRESENT, THEN THE DECLARATION WILL BE APPLIED*/
      .page-links.page-links--active {
        background-color: #099268;
        color: azure;
      }

      .pagination {
        /* 1 Dimensional , so flex is right */
        display: flex;
        align-items: center;
        gap: 12px;

        /* We are not providing any width of the whole pagination container, because we want it to be t */

        margin-top: 200px;
      }

      .dots {
        color: #868e96;
      }
    </style>
  </head>
  <body>
    <div class="pagination">
      <button class="btn">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="btn-icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M15.75 19.5 8.25 12l7.5-7.5"
          />
        </svg>
      </button>
      <a href="#" class="page-links">1</a>
      <a href="#" class="page-links">2</a>
      <a href="#" class="page-links page-links--active">3</a>
      <a href="#" class="page-links">4</a>
      <a href="#" class="page-links">5</a>
      <a href="#" class="page-links">6</a>
      <span class="dots">...</span>
      <a href="#" class="page-links">23</a>

      <button class="btn">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="btn-icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="m8.25 4.5 7.5 7.5-7.5 7.5"
          />
        </svg>
      </button>
    </div>
  </body>
</html>
```

![image](./asset_HTML_CSS/Screenshot%202024-03-02%20204255.png)

## Web Design Rules #10 - Part 2 : Layout Patterns (94)

[Page 309-350](https://drive.google.com/file/d/1U2kms90R9gK4v4PvkB3JAXoA4p0gE8xp/view?usp=drive_link)

## Building a Hero Section - Part 1 (95)

![image](./asset_HTML_CSS/Screenshot%202024-03-02%20225453.png)

```html
<body>
  <header>
    <nav>
      <div>LOGO</div>
      <div>Navigation</div>
    </nav>

    <div>
      <h1>A Healthy Meal Delivered to Your Door, Every Single Day</h1>
      <p>
        The smart 265-days-per-year food subscription that will make you eat
        healthy again. Tailored to your personal testes and nutritional needs
      </p>
      <a href="#" class="btn">Start eating well</a>
    </div>
  </header>
  <section>
    <div>
      <h2>Some Random Heading</h2>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum in earum
        qui molestiae consectetur corrupti eius sequi cumque pariatur vel,
        libero quia officiis doloremque quasi laudantium optio dolore officia
        voluptas. Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Dolorum, temporibus magnam nesciunt, recusandae voluptatum voluptas
        inventore ullam quo perspiciatis officia facere aperiam ratione, odio
        expedita tenetur nisi? Quod, corrupti delectus!
      </p>
    </div>
  </section>
</body>
```

## Building a Hero Section - Part 2 (96)

![Image](./asset_HTML_CSS/Screenshot%202024-03-02%20234547.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&family=Rubik:ital,wght@0,300..900;1,300..900&display=swap"
      rel="stylesheet"
    />
    <title>Omnifood Hero Section</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }
      html {
        font-family: "Rubik", sans-serif;
        color: #444;
      }

      /* For centering */
      .container {
        width: 1200px;
        margin: 0 auto;
      }

      header {
        /* background-color: #462305; */
        /* We use View Port Height 100 */
        height: 100vh;

        /* We have another similar unit : VW > ViewPort Window. However we do not need it here.
        Infact we rarely use it
        
        Since these are block element, they will already occupy 100% of the available space by default*/
        position: relative;

        /* Backgorund Image & backgound Cover (To figure out automatically the exact size that the image need to be cover as the name says here, the entire element */
        background-image: linear-gradient(
            rgba(35, 35, 35, 0.6),
            rgba(35, 35, 35, 0.6)
          ), url(./hero.jpg);
        background-size: cover;
        color: #fff;
      }
      nav {
        font-size: 20px;
        font-weight: 700;
        display: flex;
        justify-content: space-between;
        /* Margin top will not work, as we have already specified margin 0 auto , so we will use padding instead*/
        padding-top: 50px;

        /* background-image: linear-gradient(to right, red, blue); */
        /* background-color: aqua; */
      }
      .header-container {
        width: 1200px;
        position: absolute;

        /* In relation to parent size */
        left: 50%;
        top: 50%;
        /* background-color: aqua; */
        /* In Relation  to the Element size */
        transform: translate(-50%, -50%);
      }

      .header-container-inner {
        width: 50%;
        /* background-color: blue; */
      }

      h1 {
        font-size: 52px;
        margin-bottom: 32px;
        line-height: 1.05;
      }

      p {
        font-size: 20px;
        line-height: 1.6;
        margin-bottom: 48px;
      }

      .btn:link,
      .btn:visited {
        font-size: 20px;
        font-weight: 600;
        background-color: #e67e22;
        color: #fff;
        text-decoration: none;

        /* As we know Anchor tag is a inline, so padding will not work. So we need to chnage it to inline-block */
        display: inline-block;
        padding: 16px 32px;
        border-radius: 10px;
      }

      h2 {
        font-size: 44px;
        margin-bottom: 48px;
      }

      section {
        padding: 96px 0;
        background-color: #f7f7f7;
      }
    </style>
  </head>
  <body>
    <header>
      <nav class="container">
        <div>LOGO</div>
        <div>Navigation</div>
      </nav>

      <div class="header-container">
        <div class="header-container-inner">
          <h1>A Healthy Meal Delivered to Your Door, Every Single Day</h1>
          <p>
            The smart 365-days-per-year food subscription that will make you eat
            healthy again. Tailored to your personal testes and nutritional
            needs
          </p>
          <a href="#" class="btn">Start eating well</a>
        </div>
      </div>
    </header>
    <section>
      <div class="container">
        <h2>Some Random Heading</h2>
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Harum in
          earum qui molestiae consectetur corrupti eius sequi cumque pariatur
          vel, libero quia officiis doloremque quasi laudantium optio dolore
          officia voluptas. Lorem ipsum dolor sit amet consectetur adipisicing
          elit. Dolorum, temporibus magnam nesciunt, recusandae voluptatum
          voluptas inventore ullam quo perspiciatis officia facere aperiam
          ratione, odio expedita tenetur nisi? Quod, corrupti delectus!
        </p>
      </div>
    </section>
  </body>
</html>
```

- I Learned How to Think to achieve Layout

- I have used utility class, like container to each element for margin auto & a fixed width

- Used Absolute Positioninng & Translate (Transformation) for achieveing exact position

- I have learned how to achive backgroud image , backgroud gradient

- I have learned how to achive height View Port Height

![image](./asset_HTML_CSS/Screenshot%202024-03-03%20000327.png)

## Building a Web Application Layout - Part 1 (97)

- Continue to next lecture.. No note

## Building a Web Application Layout - Part 2 (98)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>App Layout</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }
      body {
        font-family: sans-serif;
        color: #343a40;
        font-size: 24px;
        height: 100vh;
        display: grid;
        grid-template-columns: 80px 400px 1fr 250px;
        grid-template-rows: 80px 1fr;
        text-align: center;
        font-weight: bold;
      }

      nav,
      section,
      main,
      aside {
        padding-top: 24px;
      }

      nav {
        background-color: #343a40;
        color: #fff;
        grid-row: 1/-1;
      }

      menu {
        background-color: #7048e8;
        grid-column: 2/-1;
        display: flex;
        align-items: center;
        gap: 12px;
        padding: 0 40px;
      }

      button {
        display: inline-block;
        font-size: 16px;
        background-color: #5f3dc4;
        border: none;
        cursor: pointer;
        color: #fff;
        padding: 8px 12px;
        font-weight: 800;
      }

      menu button:last-child {
        /* To put the last button extreme right  */
        background-color: #fa5252;
        margin-left: auto;
      }

      section {
        background-color: #e9ecef;
        padding: 40px;
        display: flex;
        flex-direction: column;
        gap: 40px;

        /* How Elements that do not fit into the container appear */
        overflow: scroll;
        /* overflow: hidden; */
      }

      .email {
        background-color: #adb5bd;
        height: 96px;
        display: flex;
        align-items: center;
        justify-content: center;

        /* We need to do flex shrink, because we want it to scroll, any by default, flex-shrink is ON */
        flex-shrink: 0;
      }

      aside {
        background-color: #e9ecef;
      }
    </style>
  </head>
  <body>
    <nav>Nav</nav>
    <menu>
      <button>New</button>
      <button>Reply</button>
      <button>Forward</button>
      <button>Mark Unread</button>
      <button>Trash</button>
    </menu>
    <section>
      <div class="email">Eamil 1</div>
      <div class="email">Eamil 2</div>
      <div class="email">Eamil 3</div>
      <div class="email">Eamil 4</div>
      <div class="email">Eamil 5</div>
      <div class="email">Eamil 6</div>
      <div class="email">Eamil 7</div>
      <div class="email">Eamil 8</div>
      <div class="email">Eamil 9</div>
      <div class="email">Eamil 10</div>
      <div class="email">Eamil 12</div>
      <div class="email">Eamil 13</div>
    </section>
    <main>Email View</main>
    <aside>Additional Info</aside>
  </body>
</html>
```

![image](./asset_HTML_CSS/Screenshot%202024-03-03%20150003.png)

**THE END**
