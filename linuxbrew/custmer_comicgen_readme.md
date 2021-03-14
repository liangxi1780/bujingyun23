# comicgen

 
We love comics. We badly wanted to create comic strips. But there was one
problem. Some of us can't draw a straight line for nuts.

But why should that stop us from creating comics? So here's a gift to ourselves
and the world &mdash; a **Comic Creator**.

We are sure you'd love the company of our friends [Dee](#?name=dee) &
[Dey](#?name=dey). Go on & have some fun.
 

 
## Installation

Load the comicgen library by adding this line in your HTML page's ` `:

```html
 
  
```

You can also install comicgen locally using `npm` or `yarn`:

```bash
npm install comicgen
yarn install comicgen
```

... and then include:

```html
 
  
```

## Usage

To embed a character, add:

```html
  
```

This inserts the following image in your HTML.
You can embed it anywhere, including inside an ` ` element.

![name=dee angle=straight emotion=smile pose=thumbsup](docs/dee-straight-smile-thumbsup.png)

The character is defined by 4 attributes:

- `name`: the name of the character (e.g. `dee`, `dey`)
- `angle`: which angle are they are facing (e.g. `straight`, `side`)
- `emotion`: what emotion their face expresses (e.g. `sad`, `happy`)
- `pose`: what pose their body shows (e.g. `pointingup`, `holdinglaptop`)

The list of valid combinations are available on the
[comicgen interactive gallery](http://u.720life.cn/g/267747b3015c3872c2b320ec57da5ad2ec50e268d9e71070e2888b5649507d1f).

The characters are drawn on a 500 x 600 canvas. You can change this using:

- `width`: width of the image. Default: 500
- `height`: height of the image. Default: 600
- `x`: left position or x-offset. Default: 0
- `y`: top position or y-offset. Default: 1
- `mirror`: shsow mirror image. Value can be empty string or 1. Default: empty string
- `scale`: how much larger to make the image. Default: 1

Comicgen is tested on Chrome, Edge, and Firefox. It does not work on Internet Explorer.

## Composition

To combine multiple characters in a panel, embed them in an ` ` element.

You can change the `x`, `y`, `width`, `height`, `mirror` and `scale` to position each character.

```html
 
    
    
 
```

![Dee and Dey together](docs/dee-and-dey-together.png)

You can resize the combined image by changing the `width` and `height` of the
SVG container.

```html
 
    
    
 
```

Set `viewBox` to the width and height of the comicgen elements. Then you can set
the outer `width` and `height` to anything.

![Dee and Dey scaled down](docs/dee-and-dey-meet.png)

This normally scales the image to fit both the width and height. To fit only one
side, use [preserveAspectRatio](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1266a30c30d64538d41ce28890d1e43c0e9b10293dd745710ffef1e86b0e761383e7337b6544c5fb45b7049dc292c90f975).
For example, `preserveAspectRatio="xMidYMin slice"` in this case fits to width
and slices the height, preserving the top (YMin) of the image.

```html
 
    
    
 
```

![Dee and Dey fit width](docs/dee-and-dey-slice.png)

## Panels

[comicgen.css](http://u.720life.cn/g/bb7a93d719a99772080f396520384e59c27209cd5a38a719e72f463c5a989ea3ca81fbd2d819623e48de82019c5d689b16012ea1fd9f7fb6b380e7b8302a764d)
provides 2 classes for layout:

- `comic-panel`
- `comic-row`

Use `class="comic-panel"` to can embed characters in a thick grey border. For example

```html
 
    
 
```

![Dee in a panel](docs/dee-panel.png)

Panels are typically placed inside a `class="comic-row"`:

Here's an example with 2 panels. The second panel has 2 characters.

```html
 
   
      
   
   
     
        
        
     
   
 
```

![Dee and Dey in panels](docs/dee-and-dey-panels.png)

You can override the panel's background, border width and color using CSS
variables in your stylesheet.

```css
:root {
  --comic-background: #eee;     /* Light grey background. Default: transparent */
  --comic-border-color: #ccc;   /* Light grey border. Default: grey */
  --comic-border-width: 1px;    /* Thin border. Default 2px */
}
```

![Dee and Dey in panels, with CSS styling](docs/dee-and-dey-panels-styled.png)


## Captions

[comicgen.css](http://u.720life.cn/g/bb7a93d719a99772080f396520384e59c27209cd5a38a719e72f463c5a989ea3ca81fbd2d819623e48de82019c5d689b16012ea1fd9f7fb6b380e7b8302a764d)
provides `comic-caption-top` and `comic-caption-bottom` to add captions inside
a `.comic-panel`.

For example, this defines a caption on top:

```html
 
   Hi! I'm Dee. 
    
 
```

![Dee with a caption on top](docs/dee-caption-top.png)

... or the bottom:

```html
 
   Hi! I'm Dee. 
    
 
```

![Dee with a caption at the bottom](docs/dee-caption-bottom.png)

You can override the caption's background, font and padding using CSS variables
in your stylesheet.

```css
:root {
  --comic-caption-background: #eee;         /* Light grey background. Default: white */
  --comic-caption-font: Neucha, cursive;    /* Custom Google font. Default: cursive */
  --comic-caption-padding: 0.25rem 0.5rem;  /* Custom margin. Default: 0.25rem */
}
.comic-caption-top, .comic-caption-bottom { /* Apply any custom styles you want */
  text-transform: uppercase;
}
```

![Dee with a caption on top, styled with CSS](docs/dee-caption-top-styled.png)

[Google fonts has handwriting fonts](http://u.720life.cn/g/215b706e92c30f831f42c75448c4994b678d057ddd184065bc29f5cb74820919a10f7f67ad6cfd4f8bd8cc5cd9ca079f)
that can be used for the caption lettering.

## Strips

You can combine [captions](#captions) with [panels](#panels) to create a strip
like this:

```html
 
   
     Hi! I'm Dee. 
      
   
   
     I'm in a comic strip called Dee & Dey. 
      
   
   
     And this is Dey, my co-star on this strip. 
     
        
        
     
   
 
```

![Dee and Dey with captions](docs/dee-and-dey-captions.png)

 


## API

To explicitly run comicgen on a selector, run `comicgen(selector)`. This lets
you dynamically create or change a a character.

Here's an example in jQuery showing how you can create a character dynamically:

```js
// Add the character
$('  ').appendTo('body')
// Call comicgen()
comicgen('.new')
```

![Dynamic character rendered via JS](docs/dee-sad-yuhoo-400-300.png)

You can pass an `options` parameter to `comicgen()` to provide default values.
For example:

```js
$('  ').appendTo('body')
comicgen('.new', {
  name: 'dey',      // Set the default name.   overrides this
  emotion: 'sad',   // Set the default emotion
  pose: 'yuhoo',    // Set the default pose, etc
  width: 400,
  height: 300
})
```

![Dynamic character rendered via JS, with default options](docs/dee-sad-yuhoo-400-300.png)

## Release

To publish a new version on npm:

```bash
# Update package.json version
# Run tests on dev branch
npm run lint
npm test
npm run test-chrome
npm run test-edge
npm run test-firefox

# Ensure that there are no build errors on the server
git commit . -m"DOC: Release version x.x.x"
git push

# Merge into dev branch
git checkout master
git merge dev
git tag -a v0.x.x -m"Add a one-line summary"
git push --follow-tags

# Publish to https://www.npmjs/package/comicgen maintained by @sanand0
npm publish

git checkout dev
```


 

## Credits

- Library developed by Kriti Rohilla   and S Anand  
- Conceived & designed by Ramya Mylavarapu   & Richie Lionell  

### Character credits

- Dee: By Ramya Mylavarapu  
  under [CC0 license](http://u.720life.cn/g/f92437de2a0f19dbeda7f9325abcfd61db9d474f307a3deccdbc39dff618a31e94b6bc1522be26ba37f23e4682431a2c)
- Dey: By Ramya Mylavarapu  
  under [CC0 license](http://u.720life.cn/g/f92437de2a0f19dbeda7f9325abcfd61db9d474f307a3deccdbc39dff618a31e94b6bc1522be26ba37f23e4682431a2c)
- [Humaaans](http://u.720life.cn/g/69ea3f395bfd06df177a331691c56b417f713fa487acb9f142698c63b9a31891): By [Pablo Stanley](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fe5c181fcc2b84eb1d66dd320c7cc64dc2)
  under [CC-BY license](http://u.720life.cn/g/f92437de2a0f19dbeda7f9325abcfd61608973388e99646292f37c07cffde0791d4260ec77bd72bc02dbfcf5e4b9b278)

 

 
## Contributing

We'd love your help in improving Comicgen.

If you're a developer, you could help
[fix bugs](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465fed865014c3137345fc473ba00c42a44e45ea18a952c0d2cc93ade294ad70ff) or
[add features](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465fed865014c3137345fc473ba00c42a4c977e48f32551444d74bf26e9517b1ce6cfc9e677b7cd051490294ffed2c2dac).
Some issues are marked
[help wanted](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465fed865014c3137345fc473ba00c42a435612ae5b41110cb6dd23818a12896fe949dc1807b915dba35920817b6a2df51).
These are a good starting point.

If you're a designer, you could help add new characters.

### Add new characters

Characters are made of 1 or more SVG images.

The easiest way to create a character is to draw a dozen SVGs and save them as
individual files **of the same dimensions**. For example:

![Series of SVG images for a character](docs/character-single-images.png)

A better way would be to break up the character into different parts. For
example, you could draw faces with different emotions and save them under an
`faces/` folder:

![Faces for a character](docs/character-faces.png)

Then you could draw the bodies under a `bodies/` folder:

![Bodies for a character](docs/character-bodies.png)

If you do this, you must make sure that:

- All faces have the **same dimensions**, and are at the **same position** within the SVG
- All bodies have the **same dimensions**, and are at the **same position** within the SVG
- When you super-impose any face on any body, the **images should align**.

You can choose to break up the images in any number of ways. For example:

- `faces/`, `bodies/`
- `face/`, `trunk/`, `leg`, `shoes`
- `hair`, `face`, `eyes`, `mouth`, `trunk/`, `legs/`

The more combinations you have, the more complex your image becomes. You could
start small and then add variety.

### Submit new characters

Give your character a name (e.g. "Ant Man"). Save the SVG files under a folder
with the character name (e.g. "ant-man" - lower-case, use hyphens as separator).
Add this folder under the
[files/](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465fed865014c3137345fc473ba00c42a4abba67a577631d4adac00bdd8a7cc8aeef725c2b6cecda8e091918b7d10c214a) folder.

Then [send a pull request](http://u.720life.cn/g/1f425b0b33da40ebdfbaffd56fc945099f6a3b8e3d1757532c84b41e77de74d9e8cfa2165fd745a9f0a3258a46a3baa9f9dbc5a30e55a923c18a032ce0eedb4f)
or email S Anand  .

When doing this, please mention one of the following:

- "I release these images under the [CC0](http://u.720life.cn/g/f92437de2a0f19dbeda7f9325abcfd61db9d474f307a3deccdbc39dff618a31e94b6bc1522be26ba37f23e4682431a2c) license", OR
- "I release these images under the [CC-BY](http://u.720life.cn/g/f92437de2a0f19dbeda7f9325abcfd61608973388e99646292f37c07cffde0791d4260ec77bd72bc02dbfcf5e4b9b278) license"


 

 
## Share

 
   
      
   
   
      
   
   
      
   
   
      
   
 
 

 
 
 
    Share on Twitter  
    Share on Facebook 
    Share on LinkedIn 
    Fork on Github  
 
 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e22cc53ad7922014c80ce491d6bc93a6ee75deb56b55000e5ec000c60a6cf5121a99a22f28c6879b18fd131238da1d774)