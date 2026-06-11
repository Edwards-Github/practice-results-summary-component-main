# Frontend Mentor - Results summary component solution

This is a solution to the [Results summary component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/results-summary-component-CE_K6s0maV). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
    	<br>
	  Desktop:
		<br>
	  	<img width="1440" height="1080" alt="desktop-design" src="https://github.com/user-attachments/assets/5c5be026-d705-4d20-866a-5692117447c7" />
	  Mobile:
		<br>
		<img width="375" height="809" alt="mobile-design" src="https://github.com/user-attachments/assets/dc46714d-f4ae-46e1-8ab1-ab6ca8d58b03" />
  - [Links](#links)
- [My process](#my-process)
  - [Built with] HTML and CSS
  - [What I learned] (#what-i-learned)
	1. .right-half {
  		background-color: hsl(0, 0%, 100%);
  		width: 15%;
  		height: 35%;
  		margin-left: 30px;
	    }
	    a. For this css, it actually used 100% of the width, but then added margin-left: 30px ON TOP OF the full width which caused the upper half on mobile to be misaligned.

	2. Make the left and right halves width concrete. For example, width: 500px; this makes the overall card maintain its structure. The justify-content: space-between
   	   will handle the spacing for the text in reaction-container.

  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration) Claude, Gemini
- [Author](#author) Edward Li
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page
- **Bonus**: Use the local JSON data to dynamically populate the content

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it. 

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

**Note: Delete this note and the paragraphs above when you add your screenshot. If you prefer not to add a screenshot, feel free to remove this entire section.**

### Links

- Solution URL: [Add solution URL here](https://github.com/Edwards-Github/practice-results-summary-component-main)
- Live Site URL: [Add live site URL here](https://edwards-github.github.io/practice-results-summary-component-main/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox

### What I learned

Use this section to recap over some of your major learnings while working through this project. Writing these out and providing code samples of areas you want to highlight is a great way to reinforce your own knowledge.

To see how you can add code snippets, see below:

```html
<h1>Some HTML code I'm proud of</h1>
```
```css
.proud-of-this-css {
  color: papayawhip;
}
```
```js
const proudOfThisFunc = () => {
  console.log('🎉')
}
```

1. The Power of a "Card Wrapper" Container
In your HTML, your .left-half and .right-half are sitting directly inside your .page-container (which takes up the whole screen).

The issue: When you want to style the component as a single cohesive card (like adding a shared border-radius or an overall box-shadow), you have to split those styles up manually between the left and right halves.

The Improvement: Introduce a single component wrapper (e.g., <div class="card">) around both halves. The full-screen background handles centering, the card wrapper handles the component's size and shadow, and the halves just divide the internal space.

```HTML
<div class="page-container"> <div class="component-card"> <div class="left-half">...</div>
    <div class="right-half">...</div>
  </div>
</div>
```
2. Move from Percentages to Max-Widths for Layouts
In your initial code, you used width: 25% for both sides. Percentages tell an element to resize strictly based on how big the browser window is. If the browser window shrinks to nothing, your card shrinks to nothing.

The Improvement: For components like this, use fixed widths (width: 350px) or maximum widths (max-width: 700px). This tells the browser: "Be this exact size on a computer screen, regardless of how much the user shrinks or expands their browser window."

3. Replace Hardcoded Margins with Flexbox gap
Inside your .reaction-container, you used margin: 5px 50px 5px 5px; on the .category text to push the scores away. As you experienced, hardcoded margins are rigid and break alignment when space gets tight.

The Improvement: Lean into modern Flexbox spacing. By using justify-content: space-between on the container, the browser automatically pushes the left items to the far left, and the right items to the far right. If you want space between an icon and its text, use the gap property.

```CSS
/* Clean, modern row spacing */
.reaction-container {
  display: flex;
  justify-content: space-between; /* Automatically pushes content to opposite edges */
  align-items: center;
}

.sub-container {
  display: flex;
  align-items: center;
  gap: 12px; /* Perfectly spaces the icon from the text without breaking */
}
```

4. Semantic HTML Adjustments
You used a <h1> tag for the word "Summary". In standard web layout practices, an <h1> is reserved for the primary title of the entire webpage (usually just one per page for SEO and screen-reader accessibility).

The Improvement: Since "Your Result" and "Summary" are equal visual sections within a component, changing them both to <h2> or <h3> tags makes your HTML outline structurally perfect.


### Continued development

1. I want to continue to work on the spacing between elements and giving them the flexibility when window sizes changes while stopping the text from overflowing.

2. I want to continue working on my html structure and experiment to get it a lot cleaner.

3. I want to make my html and css cleaner.

**Note: Delete this note and replace the list above with resources that helped you during the challenge. These could come in handy for anyone viewing your solution or for yourself when you look back on this project in the future.**

### AI Collaboration

Describe how you used AI tools (if any) during this project. This helps demonstrate your ability to work effectively with AI assistants.

- What tools did you use (e.g., ChatGPT, Claude, GitHub Copilot)? Claude and Gemini
- How did you use them (e.g., debugging, generating boilerplate, brainstorming solutions)? Used them to debug or learn how certain parts interact with each other.
- What worked well? What didn't? The AI played as a patient teacher that guided me towards a solution as opposed to just giving me the answer.

**Note: Delete this note and the content above if you didn't use AI, or replace with your own experience.**

## Author

- Website - [Edward](https://www.linkedin.com/in/edward-li-493a37179/)
- Frontend Mentor - [@Edwards-Github](https://www.frontendmentor.io/profile/Edwards-Github)
