# learn-grid-the-easy-way

## The Background
I used this template from [Kevin powell](https://github.com/kevin-powell/learn-grid-the-easy-way/tree/main) that he builded for his [Youtube video](https://www.youtube.com/watch?v=rg7Fvvl3taU&t=181s) where he show how to use the [grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) to make styling complex grid layout more easy.

## The Process
I follow along the video and in the end I decided make the layout by myself using [grid-column](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column) approach to compare with grid-template-areas taught on the video tutorial.

## Example


```html
<main class="testimonial">
    <section>
        <p>
        Lorem Lorem
        </p>
    </section>
     <section>
        <p>
        Lorem Lorem
        </p>
    </section>
     <section>
        <p>
        Lorem Lorem
        </p>
    </section>
    ......

</main>
```

To use the grid-template-areas you first make your container a grid and then you give a name for each item on the grid (I name it one to five, but a meaninfull name should be better).

```css
main {
    display: grid;
    gap: 1.5rem;
    grid-auto-columns: 1fr;
    grid-template-areas:
    'one'
    'two'
    'three'
    'four'
    'five';
}
```

Them we set the names for each item on the grid.
I used nth-child because it easy doing like that.

```css
.testimonial:nth-child(1) {
  grid-area: one;
}

.testimonial:nth-child(2) {
  grid-area: two;
}

.testimonial:nth-child(3) {
  grid-area: three;
}

.....

```
At this moment we're done.
We can change the layout of the grid based on the media query if we want, we can also increaseor decrease the number of column and rows and also change the position of the grid items.

### Two columns and 4 rows

```css
@media screen and (min-width: 33em) {
  .testimonial-grid {
      grid-template-areas:
      "one one"
      "two three"
      "five five"
      "four four";
  }
}
```

### Two columns and 4 rows but the item five now take a space of two rows

```css

@media (min-width: 38em) {

  .testimonial-grid {
    grid-template-areas: 
     'one one'
     'two five'
     'three five'
     'four four';
  }
}

```

### Three columns and 3 rows and changes the order of the items in the grid

```css
@media screen and (min-width: 50em) {
  .testimonial-grid {
      grid-template-areas:
      "one one two"
      "five five five"
      "three four four";
  }
}

```
### The desktop view

```css

@media (min-width: 75em) {

  .testimonial-grid {
    grid-template-areas: 
     'one one two five'
     'three four four five';
  }

}
```

@media (min-width: 75em)![@media (min-width: 75em)](/images/media-75.png)

@media (min-width: 50em)![@media (min-width: 50em)](/images/media-50.png)

@media (min-width: 38em)![@media (min-width: 38em)](/images/media-38.png)

@media (min-width: 33em)![@media (min-width: 33em)](/images/media-33.png)

Mobile ![mobile)](/images/mobile-first.png)


## Links
I create a site for the solution.
check the result here - [Live code](https://learn-css-grid-the-easy-way.vercel.app/).

## Conclusion
It was very fun styling it by myself, I learn a lot in the process, and with no doubt the [grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) is easier to use and maintan the code as well.
