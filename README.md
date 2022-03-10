# Frontend Mentor - NFT preview card component solution

### Wassup! :call_me_hand:

This is my solution to the [NFT preview card component from ***Frontend Mentor***](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U)

**Frontend Mentor** challenges help you improve your coding skills by building realistic projects.

## Table of contents :earth_americas:

- [Overview](#overview-bookmark_tabs)
  - [Screenshot](#screenshot-framed_picture)
  - [Links](#links-link)
- [My process](#my-process-footprints)
  - [Built with](#built-with-hammer_and_wrench)
  - [What I learned](#what-i-learned-brain)
  - [Continued development](#continued-development-books)
  - [Useful resources](#useful-resources-mag_right)
- [Author](#author-raising_hand_man)
- [Acknowledgments](#acknowledgments-pray)

## Overview :bookmark_tabs:

### Screenshot :framed_picture:

![My solution](https://github.com/braga-git/frontendmentor-nft-previewcard-component/blob/main/design/mydesign.png)

### Links :link:

- [Solution codes](https://github.com/braga-git/frontendmentor-nft-previewcard-component)
- [Live site](https://braga-git.github.io/frontendmentor-nft-previewcard-component/)

## My process :footprints: 

### Built with :hammer_and_wrench:

- HTML5
- CSS3

### What I learned :brain:

I thought this one would be easier for me. It seemed pretty much like the other one, so it wasn't supposed to take me much time to finish it.

**Well.. I was wrong!**

I've done and redone it three times before actually progressing. This happened because I was struggling with what semantic elements I was going to use but, after that everything flowed quite good.

I started by doing what was easier for me, like styling the texts and images. 

There were somethings that were kinda hard for me and I needed to search for the answer.

My first doubt was on how to display the price `0.041 ETH` and the time left `3 days left` side by side. I had in mind that I could use an `ul` divided in 2 columns and I thought I should use the `list-style-image` for the icons. I was partly right (I hope)! I did use the `ul` divided in 2 columns, but by the time i tried to use the icons with the `list-style-image` property, it didn't go as I planned. It wans't aligned and I couldn't get it right with the tools and values available. Then I decided to use `background-image`for the icons and it went pretty well. Unfortunatelly there was still a problem. I had the content divided in 2 columns, but I needed the `3 days left` aligned with the right corner of the card. This wasn't the issue, as I knew I could use `text-align: right;`, but the trouble still was the clock icon. Because it didn't follow the `text-align: right;` (oh, what a beautiful world it would be), I had to use `background-position: center` to get it close to the beginning of the text and then use a `margin-left` with the NEGATIVE value of `-35` to finally get it into the position I wished.

The thing is, I don't know if it was the best option, since it can broke when it gets responsive, but it worked either in the desktop or the smartphone (iPhone 6). I would like to know if there is a way to get the column aligned in the right and the icon to follow the column when it gets aligned. Comment if you have an idea!

Here is the code:

```css
ul {
  list-style: none;
  columns: 2;
  font-size: 0.9em;
}

  ul>li.price {
    color: hsl(178, 100%, 50%);
    background-image: url('images/icon-ethereum.svg');
    background-repeat: no-repeat;
    background-position: left center;
    padding-left: 20px;
  }

  ul>li.timer {
    text-align: right;
    color: hsl(215, 51%, 70%);
    background-image: url('images/icon-clock.svg');
    background-repeat: no-repeat;
    background-position: center;
    margin-left: -35px;
  }
```

My next step was the NFT picture and my difficulty on this was the color overlay and the eye icon that are supposed to appear when hovering the cursor above it. I thouht it would be easy, but this is what take me more time to find and to apply correctly.

### Continued development :books:

-

### Useful resources :mag_right:

-

## Author :raising_hand_man:

Follow me for more "solutions" :wink: 

- Frontend Mentor - [@braga-git](https://www.frontendmentor.io/profile/braga-git)
- Instagram - [@braga.jpeg](https://www.instagram.com/braga.jpeg/)
- LinkedIn - [Gabriel Braga Camara](https://www.linkedin.com/in/gabrielbragacamara/)

## Acknowledgments :pray:

-
