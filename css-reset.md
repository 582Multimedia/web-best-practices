# CSS Reset

A CSS reset adds common, useful styles & properties used for all web pages.
Create and link to a CSS reset on all your web projects.

See my example [reset.css](css/reset.css)

## Explantions of styles
We create a style using the * wildcard symbol that applies to all elements.

```
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

`box-sizing: border-box;` 
sets the DOM box model so that boxes include borders. This is more natural.

This will be easier if you understand the box model. **add reference** 

`margin: 0;` sets margins to 0, since different browsers have different default margins.

`padding: 0;`sets padding to 0, since different browsers have different default padding.

Note that we will have to add back margins & padding to elements, but now they will be consistent across browsers.


### html style
These properties apply to the root, html element.
```
html {
  font-size: 24px;
  line-height: 1.44;
  height: 100%;
  scroll-behavior: smooth;
}
```
`font-size: 24px;` default font size for most browsers is 16px. Set the base font to 20px or more for more legible and accessible pages.

`line-height: 1.44;` adds a bit of extra space between lines. Again good for readability.

`height: 100%` is probably useless. But there it is, still hanging around after decades.

`scroll-behaviour: smooth;` makes the pages scroll smoothly when clicking links to elements by id within the page. The default is just jumping to the the linked element. So 1980s.

## typography

Set relative font sizes using a [type scale](https://typescale.com/).
This one is a minor-third.
```
h1 {
  margin-top: 0;
  font-size: 4.3rem;
}

h2 {font-size: 2.074rem;}

h3 {font-size: 1.728rem;}

h4 {font-size: 1.44rem;}

h5 {font-size: 1.2rem;}

small, .text_small {font-size: 0.833rem;}
```

Note that we use rem (not px or em or %). This is the preferred unit in most cases. It allows for better accessibility, while keeping things simple. See **Peter's application** for more info.

## code and preformatted elements
```
pre,
code {
  font-size: .833rem;
  font-family: 'Courier New', Courier, monospace;
  color: rgba(255, 255, 255, 0.75);
  white-space: pre-wrap;
}
```
You might not need this, but I add it to make it easy to display preformatted code on a web page.

### ignore this basic styling for now. It is more opionated, in terms of fonts & colours.

## links / anchor elements
Anchor tags are a bit tricky because of their pseudo-elements for :hover and :visited because a link has different states. 

```
* anchor tag pseudo elements */
a{
  font-family: 'Inter', sans-serif;
}
a:link,
a:visited {
  color: rgba(151, 193, 234, 0.85);
  transition: color 0.5s;
}

a:hover,
a:focus {
  color: rgba(236, 121, 66, 1);
  text-decoration: none;
}

a:active {
  color: rgba(151, 193, 234, 0.85);
}

```
These styles get rid of the ugly blue and purple default colours. Obviously, change the font and colours to fit your project.

I like having these in my reset, since I often use dark themes.

However, I often redefine these in project or page css files.

## images and videos
Most important here is setting images to fill their surrounding element / box in order that they are responsive.

```
img, video {
  max-width: 100%;
  height: auto;
}
```
### embedded YouTube video embeds
These are mostly for embedded YouTube videos. 
```
.video_container{
  width: 100%;
}
.video_container iframe{
  width: 100%;
  aspect-ratio: 16/9;
}
.video_container.anamorphic iframe{

  aspect-ratio: 2.85/1;
}
```
Again, I embed many YouTube videos.
If you don't you can leave this section out.

While you don't have to use this exact css reset, it is good practice, saving you time, making your coding efficient and your sites more consistent across browsers.

Be sure it is the 1st css file you link. That way, it's easy to overwrite any of these styles when needed for your particular project or page.

Simple right?
Well maybe not. Check out these articles:
  - [from CSS-Tricks](https://chriscoyier.net/2023/10/03/being-picky-about-a-css-reset-for-fun-pleasure/)
  - [from Josh Comeau](https://www.joshwcomeau.com/css/custom-css-reset/)

  - [a poll !!](https://css-tricks.com/new-poll-what-kind-of-css-reset-do-you-use/)

  - [Eric Meyer, who started it all](https://css-tricks.com/poll-results-what-css-reset-do-you-use/)

  - [still not enough](https://perishablepress.com/a-killer-collection-of-global-css-reset-styles/)
 