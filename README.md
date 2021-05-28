# Frontend Mentor - Stats preview card component solution

This is a solution to the [Stats preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/stats-preview-card-component-8JqbgoU62). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
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

### Screenshot

![](images/screenshots/desktop.png)
![](images/screenshots/mobile.png)

### Links

- Solution URL: [Solution](https://www.frontendmentor.io/solutions/sass-and-parcel-bundler-5cYQlQU92)
- Live Site URL: [Live site](https://stats-preview-card-sergioreynoso.netlify.app)

## My process

### Built with

- Semantic HTML5 markup
- Sass
- Flexbox
- CSS Grid
- CSS Blend Modes
- Mixins
- Parcel Bundler
- Desktop-first workflow

### What I learned

For my HTML markup, I named my classes according to the [BEM methodology](https://en.bem.info/methodology/)

```html
<div class="card">
  <div class="card__content">
    <h1 class="card__heading">
      Get <span class="heading-highlight">insights</span> that help your
      business grow.
    </h1>
    <p class="card__text">
      Discover the benefits of data analytics and make better decisions
      regarding revenue, customer experience, and overall efficiency.
    </p>
  </div>
</div>
```

I also used both CSS Grids and Flexbox together. I used grids to break up the text area of the card from the image area because I wanted to utilized the fractional properties of each column. In the design the left column was slightly wider than the right column, in the example below, I used percentage and fractional units to get as close as possible to to design. Flexbox was used to center the card on the screen.

```css
.card {
  display: grid;
  grid-template-columns: 51.5% 1fr;
}
```

For the image section, I wanted to bring the image as is and style with with css using a combination of a pseudo element over the image with a blend mode of multiply. To make this effect more modular so that it can be applied to any image element I put it into a mixin.

```css
@mixin img-effect($color: c.$color-primary) {
  &::before {
    content: "";
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    position: absolute;
    background-color: $color;
    mix-blend-mode: screen;
    opacity: 0.7;
  }

  img {
    mix-blend-mode: multiply;
    opacity: 0.7;
  }
}
```

### Continued development

I would like to continue exploring writing markup as modular as possible using the BEM methodology and the features modern css and sass has to feer, for example; partials, variables, functions, and mixins.

## Author

- Website - [](www.sergiorswork.com)
- Frontend Mentor - [@sergioreynoso](https://www.frontendmentor.io/profile/sergioreynoso)
- LinkedIn - [@sreynoso](https://www.linkedin.com/in/sreynoso/)

## Acknowledgments

I would like to thank [Jonas Schmedtmann](https://codingheroes.io) for all his great [Demy courses](https://www.udemy.com/user/jonasschmedtmann/), as well as [Kevin Powell](https://www.kevinpowell.co) for all the great css content.
