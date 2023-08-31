# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)
- [Acknowledgments](#acknowledgments)


## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

- Live Site URL: [visit here](https://mlooper5.github.io/product-preview-card-component-main/)

## My process
- Review the design mockup and style guide for the project
- Create color and type variables
- Built section structure in HTML for mobile
- Styled common components that are used across screen sizes
- Created a media query for desktop
- Ran accessibility check on webpage using the Accessibility Insights extension

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow


### What I learned

I learned about using different images depending on the size of the viewport. [This](https://aboutbits.it/blog/2021-08-04-responsive-images) article breaks down a few options. I first tried using img srcset but this approach only works if the image is the same at different screen sizes with different resolutions. In this project however, the image is cropped differently for desktop and mobile sizes. The image doesn't change to the correct crop as you resize in a chromium browser.

```html
<section class="hero">
  <img 
    src="./images/image-product-mobile.jpg" 
    alt="Flat lay of perfume surrounded by leaves" 
    sizes="(min-width: 600px) 300px, (max-width: 599px) 343px"
    srcset="./images/image-product-desktop.jpg 300w, ./images/image-product-mobile.jpg 343w"
  />
</section>
```
A better option is using the `<picture>` tag since this gives finer control of which photo to use for different screen size. Instead of having one image that is scaled up or down based on the viewport width, multiple images can be designed to more nicely fill the browser viewport.

The <picture> element contains two tags: one or more `<source>` tags and one `<img>` tag.

The browser will look for the first `<source>` element where the media query matches the current viewport width, and then it will display the proper image (specified in the srcset attribute). The `<img>` element is required as the last child of the `<picture>` element, as a fallback option if none of the source tags matches.

```html
<section class="hero">
  <picture>
    <source srcset="images/image-product-desktop.jpg" media="(min-width: 600px)" />
    <img src="images/image-product-mobile.jpg" alt="Flat lay of perfume surrounded by leaves" />
  </picture>
</section>
```
To keep the component centered on the screen I use this CSS:
```css
body {
 display: grid;
 height: 100vh;
 justify-content: center;
 align-items: center;
 align-content: center;
}
```

### Continued development

I will continue focusing on a mobile first approach on future projects. Starting with a mobile-first design has many advantages. Scaling from mobile to desktop gives me more freedom to add new functionalities without affecting the existing ones on mobile. I found it much easier to scale my project up rather than trying to scale down. 


## Author

- Website - [Miranda Cooper](https://www.mirandacooper.design/)



