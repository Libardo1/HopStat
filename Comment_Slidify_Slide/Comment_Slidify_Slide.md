So I wanted to comment out a slide in [Slidify](http://slidify.org/) for a while and never figured out how to do it.  In normal html, you use the <code><!--</code> and <code>--></code> tags around the comment.  The thing I didn't understand was that when html sees <code>--</code> in some browsers, even if not a full <code>--></code>, it can then stop the comment.  [Explanation here](http://weblog-files.200ok.com.au/labels/html.html).  So, if you write:


```coffee
<!--

## I'm a commented slide 1

From Slidify's authoring process, this slide was made:
1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!

---
-->

## Slide 2

I'm a slide

```


You will have slide 1 and 2 still as slides.  So change this to be:


```coffee
<!--

## I'm a commented slide 1

From Slidify's authoring process, this slide was made:
1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!

-->

## Slide 2

I'm a slide

```


Now Slide 2 is the only slide in the deck (on top of the title slide).  Be aware, using <code>---></code> will not work because the way Slidify parses the slides I believe.  But, if you start the line with <code>&nbsp;---></code> (note the space), then you're all good.
Here is a rundown of slides:

```coffee
<!--

## I'm slide 1 - I'm commented out

From Slidify's authoring process, this slide was made:
1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!

-->

<!--

## This slide will be shown

Slidify says - yeah, we're sliding this.

--->

<!--

## This slide will not be shown

You can open with 2 hyphens and close with three

 --->

<!---

## This slide will not be shown

3 dashes with a space works, and you can open the html with three hyphens if you want. 

 --->

## Slide 2

I'm a slide
  
```


Hope this helps on your reproducible slide journey!
