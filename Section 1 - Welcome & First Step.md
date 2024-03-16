# Welcome and First Steps

## Course Structure and Projetcs (1)

It covers:

- Webdesign
- HTML
- CSS
- Responsive Design

---

Overview :

Course is Divided into 9 Section

![All Section](./asset_HTML_CSS/Screenshot%202024-01-27%20173542.png)

## Read Before you Start (2)

He gave the Link for Everything :

![Resource](./asset_HTML_CSS/Screenshot%202024-01-27%20174808.png)

[Link For Download](https://drive.google.com/drive/folders/15xXgmVgUoJw-9w98sC8MmVSq8nttZgbL?usp=drive_link)

## A High Level Overview of Web Development (3)

- We are trying to access a Webpage omnifood.dev in the browser. So what happens when we try to access this page? is that our browser send a request to the server where this page is hosted on the internet.

- Each & Every website is hosted on something called a server, which is basically a computer that is connected to the internet and is able to receive request like this one.

- So again, when we browse to a certain website, our web browser will send a request to the server where the website is stored, So where it is hosted.

- Then when the server receives the request, it will take all the files that make up the website and send them back to the browser. So we say the server send a response to the browser. SO it esssentially contains all of these files that the website is made of.

- So we have some HTML, CSS, JS, JPG etc other files

- **These HTML, CSS, JS are precisely the three languages that browsers can understand.** So what it means is that all of the code that makes up a website needs to always be written in HTML, CSS & JS

- Once the browser receives these HTML, CSS, JS files, from the server response, it will take the code and render the website that we are trying to access.

- **And the Process of Writing HTML, CSS, JS code that the browser can understand in a process we call front-end web developement**

- **As a side note : Whenever the files that make up the website are simply stored on the web server and are then sent to the browser as they are (Without any transformation), we say we have a static website**

![Fronend](./asset_HTML_CSS/Screenshot%202024-01-27%20181406.png)

---

**LETS UNDERSTAND BACK_END DEVELOPEMENT**

- Let's now understand when we try to accessa website, like Udemy.com

- So the first stp, is a request is sent to the web-server where udemy.com is hosted

- So why is a website like udemy so different from something called omnifood.dev static webside? Well a complex side udemy.com is really completely different from a static site because there is a lot of content that is always changing all the time. Like in udemy there is always new courses, new reviews always added to a course etc.

- **And in order to make a system like this to work, udemy.com needs a whole application running on the server and they also need a big database, which basically contains all the courses, all the reviews, all the nuser, basially all the content(data) that is being displayed on their website**

- To do all this, front-end technologies like HTML, CSS are simply not enough.

- So to write application that are actually executed on webserver, developers use some kind of back-end language like Node.js, PHP, Python. So what these language do is to take data out of a database and basically assemble that data into the final files that will then sent to the browser as the response. This Whole Process is called backend developement. Because this is invisible part of a website. So its a website's backend.

- In this case, we say we have a dynamic website because the website is dynamically assembled from different pieces on the server. and that happens each time someone visits the website.

![Backend](./asset_HTML_CSS/Screenshot%202024-01-27%20194259.png)

---

![Language](./asset_HTML_CSS/Screenshot%202024-01-27%20194353.png)

## Setting up our code editor (4)

**All the Tools we need :**

1. Code Editor : VSCode

2. Extension for VSCode : Prettier, AutoRename Tag, Image Preview, etc. (I have currently all the Extension from Different Courses of Jonas. I have added it here as a reference)

![Extension](./asset_HTML_CSS/Screenshot%202024-01-27%20195646.png)

3. **Now Go to Settings** :

   - Search : Deafult Formatter > Set it to prettier
   - Search : Format on Save > Tick it (Format on Save)
   - Search : Auto Save > OnFocusChange
   - Search : Tab Size > 2 (used for indentation)

4. **Theme** :

   - Extension > One Monokai Theme > Set the Theme
   - Also you can click on Setting Icon (Left Bottom Corner) > Color Theme > Now you can choose different theme that VS code has

5. **File Icon Theme** : Optional
   - click on Setting Icon (Left Bottom Corner) > File Icon Theme > Seti

## Your Very First Webpage (5)

- In VS Code, We always need to be inside of some Folder, and that folder is called Project Folder.
- Go to Desktop > Create A Folder > 01-Test > Now come to VSCode > Select the Folder > Now In VSCode, I have the Folder Opened

- Now Create a file inside of the Folder > So we have option of creating Files inside a VSCode
- `index.html` : So we are calling it index because that is the default name of the first page of any website.

- So index is always the entry point of any website and so all web projects always need to have as `index.html`

- `!+Tab` on your Keyboard for getting the basic empty HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
  <!-- 1. Head Part will not be seen in the Browser -->
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <!--2. Title of the Webpage, Will be showin in the TAB-->
    <title>My First Webpage</title>
  </head>

  <!--Body Part is only visible to Browser Window-->
  <body>
    <!--Adding a Header-->
    <h1>Hello World!</h1>

    <!--Adding a Paragraph-->
    <p>My Name is Tuhinangshu Choudhury, and this is my very first webpage</p>
  </body>
</html>
```

- Open the `index.html` file in the Browser

## Downloading Course Material (6)

He showed how to download the Starter File from GitHub. Nothing Important here for note down.

## Watch Before you Start (7)

- Do not get overwhelmed and afraid
- Keep following the course and Keep Practicing as much as you can
- Write the code PLEASE. Make your hand dirty
- Take Note
- Try all the coding challange
- Before moving on from a section, make sure that you understand exactly what was covered. So Take Break, Review the code, Review the Note, Review the Project, and code yourself for practice
- Have fun. Coding is a lot of fun.
- So if you are feeling frustrated, stop whatever you are doing and come back later

---

**THE END**

**27-01-2024 TIME : 9:49 PM**
