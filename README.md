<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250" align="right">

# Project Summary

In this project we will be creating a single page portfolio site using HTML and CSS.

This project is designed to reinforce what you have learned during the previous week. At the bottom of this README is a high level overview of key topics. Use that to help solidify the skills in conjunction with this project

## Step One
Open your terminal and navigate to where your project will live. You should have a `devmtn` or similary named folder that will hold all of your projects during your time at DevMountain.

Once you have navigated to the appropriate folder, create a new folder called `html-portfolio`. Navigate inside of `html-portfolio` and create two files: `index.html` and `style.css`.

Open your newly created folder in your text editor.

### Solution
<details>

  * **_Navigate to Appropriate folder_**
  * `mkdir html-portfolio`
  * `touch index.html && style.css`
</details>

## Step Two
Open the `index.html` file. This is where we will build out the main structure of our page. Let's build that structure now.

There is a common pattern that most all `.html` files follow and it looks similar to this:

```html
<!DOCTYPE html>
<html>
<head>
  <!-- Information like site title, links to CSS & JS -->
</head>
<body>
  <!-- Elements go here -->
</body>
</html>
```

Create this same structure for your site. You will also need to include a title for your site and a link to your `style.css` file.

### Solution
<details>
<summary><code>index.html</code></summary>
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <link rel="stylesheet" href="./style.css">      
    <title>Portfolio Page</title>
  </head>
  <body>
    <!-- Elements go here -->
  </body>
  </html>
  ```
</details>

## Step Three
Inside of the `index.html` file, let's go ahead and start to add some structure to our page. Our layout will follow a common pattern for each section; Container -> Title -> Content.

* Create a `div` with a class of `hero`. This will be the main content someone sees once they come to our page.
  * Inside of the new `div`, create an `h1` element that has the text of your name and a class of `title`.

* Below the newly created `div`, we will want to create a new `div` with a class of `about`.
  * Create an `h1` inside of the `div` element with the text of `About`. It should also have a class of `title`.

* Next we will make a new `div` with a class of `projects`.
  * We will need to follow the same steps as above. Create an `h1` inside of the `projects` `div`. The text should be `Projects` and have a class of `title`.

* Last, we will create a `div` with a class of `contact`.
  * Following the pattern we set above, add an `h1` with the text of `Contact` and class of `title`.


### Solution
<details>
<summary><code>index.html</code></summary>

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="./style.css">      
  <title>Portfolio Page</title>
</head>
<body>
  <div class="hero">
    <h1 class="title">Bryan</h1>
  </div>
  <div class="about">
    <h1 class="title">Title</h1>
  </div>
  <div class="projects">
    <h1 class="title">Projects</h1>
  </div>
  <div class="contact">
    <h1 class="title">Contact</h1>
  </div>
</body>
</html>
```
</details>

## Step Four
All right, let's get to some styling. It can often be intimidating to know which part of your site you should start to structure next. One practice to make things seem more simple and get an idea of the structure of your site is to add solid colors to each section so they have some sort of visual representation.

Open the `style.css` file and add the CSS below to the top of your file.

```css
  .hero {
    height: 500px;
    background: #e05050;
  }
  .about {
    height: 500px;
    background: #62ce62;
  }
  .projects {
    height: 500px;
    background: #e2e25f;
  }
  .contact {
    height: 500px;
    background: #6464f5;
  }
```

Let's go ahead and open up our project in your browser of choice so we can see how are portfolio page is shaping up so far.

You should see four large blocks of color with the appropriate text in the top left corner of each block.

We will be leaving these solid colors in place until we manipulate each section to include its own styling.

Let's add a background image to our `hero` div. Head on over to [unsplash](www.unsplash.com), and find an image you want to use as the background for your div.

* Search for a topic like Hawaii, Mountains or Snow and select a picture that is appealing to you. 
* In the top right, click the button that says `Download free`.
* Create a new folder called `images` that in next to your `index.html` and `style.css` files.
* Move the newly downloaded image into our `images` folder.

Your file structure should now look something like this:

```
html-portfolio
│   index.html
│   style.css   
└───images
│   │   image.jpg
```

Now lets get to work on using that new image as the background to our `hero` div and styling the `h1`.

Back inside of the `style.css` file, add a new property to the `.hero` selector called `background` with a value of `url(PATH_TO_IMAGE) center no-repeat;`. We also want to add a property called `background-size` and set it to `cover`.

This will make our image fill the available space of our div, which is `500px` tall and `100%` of the available screen space.

Below our `.hero` selector, create a new selector: `.hero h1`. Think for a moment what element this will target...The `h1` inside of the `.hero` div! We want to remove the `margin` from the element, align it in the middle of the div and make it a little bit bigger. Feel free to adjust the font weight and family as you see fit.

### Solution
<details>
<summary><code>style.css</code></summary>

```css
.hero {
  height: 500px;
  background: url(PATH_TO_IMAGE) center no-repeat;
  background-size: cover;
}

.hero h1 {
  margin: 0;
  text-align: center;
  font-size: 4em;
  font-family: sans-serif;
  font-weight: 100;
}
  ```
</details>

We are well on our way to creating a beautiful page.

## Step Five
You may notice now that there is a gap between all of your sections even though you haven't specified for there to be one. The reason for this is because of the margin that is applied by default to the `h1` tag. Let's go ahead and remove that from all `h1` tags. Be careful when you do this though as it will be applied to all `h1` tags that have access to this style sheet so be sure to target the `.title` class.

Head over to the `style.css` file and select all `h1` elements and apply a `margin` of `0`. Notice now that we are repeating ourselves in the `.hero h1` selector. We can remove that styling so it remains DRY (don't repeat yourself).

We now want to style our `About` section. Let's first start off by remove the green background color. You will also notice that we have a set height of `500px`. It will be rare you want something to be a set height. You will most likely want it to be th height of it's child elements. Remove the `height` property and notice that it is now just has big as our `About` text. Let's add some more content inside of our `about` container in the `index.html` file.

We will want to add a simple paragraph about ourselves. This should be a few sentences talking all about you. Underneath that we want to list out five hobbies.

You might notice now that this just isn't very visually appealing. We can do a little bit of CSS to make it look better. Go ahead and add a property of `max-width` with a value of `800px` to the `.about` selector. Using `max-width` is a great option because something will never be bigger but can still be flexible enough to scale on a mobile screen.

We also want to add a `margin` property with a value of `15px auto`. This will align our content right in the middle of our screen and add `15px` to the top and bottom to give it some spacing.


### Solution
<details>
<summary><code>index.html</code></summary>

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="./style.css">      
  <title>Portfolio Page</title>
</head>
<body>
  <div class="hero">
    <h1 class="title">Bryan</h1>
  </div>
  <div class="about">
    <h1 class="title">Title</h1>
      <p>My name is Bryan Smith and I am an instructor at DevMountain. I have been developing for about 5 years now and absolutely love it. Do I have any other hobbies you ask? I sure do! You can see them below:
      </p>
      <ul>
          <li>Skateboarding</li>
          <li>Home Renovation</li>
          <li>Tattoos</li>
          <li>Lawn Care</li>
          <li>Hanging Out With My Family</li>
      </ul>
  </div>
  <div class="projects">
    <h1 class="title">Projects</h1>
  </div>
  <div class="contact">
    <h1 class="title">Contact</h1>
  </div>
</body>
</html>
```
</details>
<details>
<summary><code>style.css</code></summary>

```css
.title {
  margin: 0;
}
/* more css */
/* more css */
/* more css */
.hero h1 {
  text-align: center;
  font-size: 4em;
  font-family: sans-serif;
  font-weight: 100;
}
.about {
  max-width: 800px;
  margin: 15px auto;
}
```
</details>

## Step Six

In this step we will be adding some place holders for our projects. It will follow some of the same steps as before but add a few new layers to our structure.

Starting off in our `index.html` page, inside of the `Projects` div but below the `h1`, we need to create a child `div` that has a class of `.projects`. Let's stop and think for a moment though, didn't we already use a class called `.projects`? We did! Be very careful with naming things. While we can reuse class names, this would be a totally different structure than our original `.projects` class, so lets rename the container div to be `projects-container`. You will also need to update the `style.css` file the correct name as well.

Now that we have that sorted out, we will want to add three placeholders for some future projects we will build. Inside of the div with a class of `projects`, add three `div` elements that each have a class of `project`.

* We will want to remove the yellow background from the `Projects` div and replace it with a black background which means we will also need to update our font color to be white. 
* We then will want to center our title in the middle of the page. 

* After that, we want to add some styling to each project. Give them all a `height` and `width` of 300px. Apply a `display` property that would allow them to line up side by side to each other. We also want them displayed in the middle of the screen. We may also want to add a little space between each placeholder.

* Once that is complete, let's add a second class name to each project. This can be done following this syntax `class="project one"`. Give each project an additional class of `one`, `two` and `three`, respectively.

* Give each newly added class a different color property.

### Solution
<details>
<summary><code>index.html</code></summary>

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="./style.css">      
  <title>Portfolio Page</title>
</head>
<body>
<div class="hero">
	<h1 class="title">Bryan Smith</h1>
</div>
<div class="about">
	<h1 class="title">About</h1>
	<p>My name is Bryan Smith and I am an instructor at DevMountain. I have been developing for about 5 years now and absolutely love it. Do I have any other hobbies you ask? I sure do! You can see them below:</p>
	<ul>
		<li>Skateboarding</li>
		<li>Home Renovation</li>
		<li>Tattoos</li>
		<li>Lawn Care</li>
		<li>Hanging Out With My Family</li>
	</ul>
</div>
<div class="projects-container">
	<h1 class="title">Projects</h1>
	<div class="projects">
		<div class="project one"></div>
		<div class="project two"></div>
		<div class="project three"></div>
	</div>
</div>
<div class="contact">
	<h1 class="title">Contact</h1>
</div>
</body>
</html>
```
</details>
<details>
<summary><code>style.css</code></summary>

```css
.projects-container {
	background: #111;
	color: #fff;
	padding: 50px 0;
	text-align: center;
}
.projects {
	margin: 0 auto;
}
.project {
	height: 300px;
	width: 300px;
	margin: 0 15px;
	background: red;
	display: inline-block;
}
.project.one {
	background: green;
}
.project.two {
	background: blue;
}
.project.three {
	background: aquamarine;
}
```
</details>

## Step Seven
In our final step, we will be updating our `Contact` section to include our email address, phone number and link to our github profile.

Lets start off by removing the blue background and height of `500px` from the `.contact` selector.

Notice that our `h1` is still all the way on the left. We want it to be uniform with our `About` section `h1` so let's copy the styling to make the width the correct size. Think for a moment how we can accomplish that without repeating ourselves?

We can add a `,` after the `.about` selector and then target our `.contact` class so we can easily share styling across different sections of our page. 

We will now want to create our links to be contacted. We will want to create three new `div`s each with their own class:
 * `email`
 * `phone`
 * `github`

 Inside of each div there should be an `a` element. Remember, `a` tags are used to send a user to a specific place or perform certain action. The `a` elements should have the appropriate values for yourself.

The last thing we will need to do is center our `contact ` div and the text inside of it. Think about how we can accomplish that goal before moving forward.

### Solution
<details>
<summary><code>index.html</code></summary>

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="./style.css">      
  <title>Portfolio Page</title>
</head>
<body>
  <div class="hero">
    <h1 class="title">Bryan</h1>
  </div>
  <div class="about">
    <h1 class="title">Title</h1>
      <p>My name is Bryan Smith and I am an instructor at DevMountain. I have been developing for about 5 years now and absolutely love it. Do I have any other hobbies you ask? I sure do! You can see them below:
      </p>
      <ul>
          <li>Skateboarding</li>
          <li>Home Renovation</li>
          <li>Tattoos</li>
          <li>Lawn Care</li>
          <li>Hanging Out With My Family</li>
      </ul>
  </div>
  <div class="projects">
    <h1 class="title">Projects</h1>
  </div>
  <div class="contact">
    <h1 class="title">Contact</h1>
    <div class="email">
		  <p>Email: <a href="mailto: abc@example.com">bryan@devmtn.com</a></p>
    </div>
    <div class="phone">
      <p>Phone: <a href="tel:1-562-867-5309">1-562-867-5309</a></p>
    </div>
    <div class="github">
      <p>GitHub: <a href="github.com/bryansmith33">Check out my code!</a></p>
    </div>
  </div>
</body>
</html>
```
</details>
<details>
<summary><code>style.css</code></summary>

```css
.title {
	margin: 0;
}
.hero {
	height: 500px;
	background: url(PATH_TO_IMAGE)
		center no-repeat;
	background-size: cover;
}

.hero h1 {
	text-align: center;
	font-size: 4em;
	font-family: sans-serif;
	font-weight: 100;
}
.about,
.contact {
	max-width: 800px;
	margin: 15px auto;
}
.projects-container {
	background: #111;
	color: #fff;
	padding: 50px 0;
	text-align: center;
}
.projects {
	margin: 0 auto;
}
.project {
	height: 300px;
	width: 300px;
	margin: 0 15px;
	background: red;
	display: inline-block;
}
.project.one {
	background: green;
}
.project.two {
	background: blue;
}
.project.three {
	background: aquamarine;
}
.contact {
	margin: 50px auto;
	text-align: center;
}
```
</details>

## Wrap Up

**HTML**: HyperText Markup Languge. Whhat we will use to structure our pages and create our layouts. Follows a parent - child relationship/nesting structure.

**Element**: The specific name of something that we will use to structure our site. Things like `h1`, `p`, `div`.

**Tag**: The opening `<` and  closing `/>` wrapping the element. Remember, some elements like `img` are self closing meaing they are closed like this `<img />`.

**CSS**: Cascading Style Sheet. What we will use to style our pages. CSS follows two rules: Cascading and Specificity.

**Cascading**: CSS will apply its styling from the top of the file to the bottom. If there is a selector that has the same specificty lower in the file, that styling will take precedence.

**Specificity**: CSS follows a weighting system for specificity. The higher the weight, the more specific the styling thus meaing it will be applied.

**Class**: The most common way to select an element for styling. can be applied to the element like this: `class="class-name"` and then selected in the CSS file like this: `.class-name {}`. Classes have a weight of 10.

**ID**: IDs are another option for styling and selecting elements. They are more specific than classes. They should be used sparingly. They ca be assigned like this: `id="id-name"` and accessed in the CSS file like this `#id-name{}`. IDs have a weight of 100, meaning they take precedence even if they are at the top of your CSS file compared to a lower class.

**Height**: CSS property we use to set the height of our element. It is best practice to let your parent container element adjust to the size of its children content.

**Width**: CSS property to set the width of our element.

**Margin**: CSS property to set the space between our elements. This is an invisible boundary that other elements will respect.

**Padding**: CSS property to add additional space to our element. This will make our element larger.

**CSS Unit Measurements**:
  * **px**: Represents pixels.
  * **%**: Represents a percentage of available space.




## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2019. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250">
</p>
