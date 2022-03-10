# Frontend Mentor - NFT preview card component solution

### Wassup! :call_me_hand:

This is my solution to the [NFT preview card component from ***Frontend Mentor***](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U)

**Frontend Mentor** challenges help you improve your coding skills by building realistic projects.

Em breve em português.

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

I don't know if it was the best option, since it can brake when it gets responsive, but it worked either in the desktop or the smartphone (iPhone 6). I would like to know if there is a way to get the column aligned in the right and the icon to follow the column when it gets aligned. 

**Please, comment if you have an idea!**

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

---

My next step was the NFT picture and my difficulty on this was the color overlay and the eye icon that were supposed to appear when hovering the cursor above it. I thought it would be easy, but this is what take me more time to find and apply correctly. Looking at the code now, it doesn't seem so complex, but I definitely wouldn't be able to do it alone before. What I thought was much simpler, just adding the `background-color` with a `opacity: 0.5` in the pseudo-class `:hover`, but life is not an orange.

**The thing is:** Ok, it was kinda hard to make it fit and works properly on the image but, after applying the `background-color` i wanted and setting the `opacity` that looked similiar to the challenge, I realized that the eye icon was with the same `opacity` of the `background-color`. 

And now you thinking: 

> Well, it's easy to fix!

**Yeah! It was easy to fix..**

After 3 hours of me slamming my head in the table trying to figure it out what I was doing wrong.

I was strongly trying to increase the `opacity` of the icon in the `:hover` selector, but if I changed the `opacity` to **1**, it didn't changed only the icon opacity but of the background-color too. 

I simply needed to keep the `opacity: 1` and reduce the opacity of the `background-color` on it's very element.

![Opacity](https://github.com/braga-git/frontendmentor-nft-previewcard-component/blob/main/design/opacity.png)

And.. Yeah.. That's it..

Here is the codes:

```html
<div class="container-overlay">

  <a href="#"><img src="images/image-equilibrium.jpg" alt="Equilibrium picture" class="nft-image"></a>

  <div class="content-overlay overlayFade">
    
    <div class="view"><img src="images/icon-view.svg" alt=""></div>
    
  </div>
            
</div>
```

```css
.container-overlay {
  position: relative;
  width: 100%;
  height: 100%;
  display: inline-block;
}

  .nft-image {
    display: block;
    border-radius: 10px;
    width: 100%;
    height: 100%;
  }

  .content-overlay {
    position: absolute;
    transition: all .3s ease;
    opacity: 0;
    border-radius: 10px;
  }    
                    
  .overlayFade {
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    border-radius: 10px;
    background-color: hsla(178, 100%, 50%, 0.397);
  }

      .view {
        position: absolute;

        top: 50%;
        left: 50%;

        transform: translate(-50%, -50%);
      }

      .container-overlay:hover .overlayFade {
        width: 100%;
        opacity: 1;
        cursor: pointer;
       }
```

---

And the last thing I had to worry was on how to display the image of the author and text side by side, and vertically aligned. It was very easy! I just needed to group then inside a div with the properties `display: flex` and `align-items: center`.

This is another thing I think that may brake if the site be displayed on a very small screen. But like the columns, it worked on my dispositives.

Here is the codes:

```html
<div class="container-author">

  <div class="author-image"></div>

  <div class="text-author">

    <p>Creation of <a href="#">Jules Wyvern</a></p>

  </div>

</div>
```
```css
.container-author {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

  .author-image {
    height: 30px;
    width: 30px;
    background-image: url('images/image-avatar.png');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: 100%;
    border: 1px solid white;
    border-radius: 50%;
    margin-right: 20px;
  }

  .text-author > p{
    font-size: 0.9em;
    padding-bottom: 0px;
  } 

      .text-author > p > a {
        color: white;            
        text-decoration: none;
      }

        .text-author > p > a:hover {
          color: hsl(178, 100%, 50%);
        }
```

### Continued development :books:

**Media Query** is what I want to understand now.  I wanted to size down the card a little bit, but didn't know how to do it and (from what I read) theres somethings that I can't do or the best way to doo is using the `@media`, like turning responsive an element that has fixed sizes.

If you take a look on the site on my smartphone, you can see it creates a scroll bar and I can't see the attribuition text below the card because I can't remove the Safari's navigation bar.

![Scrollbar Mobile](https://github.com/braga-git/frontendmentor-nft-previewcard-component/blob/main/design/scrollbar-mobile.jpg)

I wanted to fix it, but I'll study more about it and after I can come back and do it.

### Useful resources :mag_right:

- [Transform property explained (only in portuguese)](https://youtu.be/-w0Qo_qQiRg) - If you saw my [last solution](https://github.com/braga-git/frontendmentor-qrcode-component), you will remember of my doubts about the `transform` property. Well, you can see that I used it again in this solution but now I'm more aware of it's usability. You can understand more about it on [this video](https://youtu.be/-w0Qo_qQiRg) (that is only in portuguese, sorry) from [@gustavoguanabara](https://github.com/gustavoguanabara). He explain in a perfect visual way the functions of the property in this case.

- [Image overlay hover effect](https://youtu.be/Cfv_9l8F0Lo) - Here you can see the code I used to add the hover effect to the NFT picture. It's a very good video and he explains more effects than only this one. It's worth watching it! 

## Author :raising_hand_man:

Follow me for more "solutions" :wink: 

- Frontend Mentor - [@braga-git](https://www.frontendmentor.io/profile/braga-git)
- Instagram - [@braga.jpeg](https://www.instagram.com/braga.jpeg/)
- LinkedIn - [Gabriel Braga Camara](https://www.linkedin.com/in/gabrielbragacamara/)
