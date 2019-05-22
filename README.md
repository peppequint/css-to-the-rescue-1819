<div align="center">
	<h1 align='center'>Restaurant menu</h1>
<img align='center' src="./img/screenshot-application.png" width="620" />
</div>
<p align="center">
	Interactive restaurant menu, only made with CSS.
	<br>
	<a href="https://peppequint.github.io/css-to-the-rescue-1819/">Live demo</a>
</p>
<br>

## Table of contents

- [Clone](#clone)
- [Concept](#concept)
- [Restrictions](#restricions)
- [Methodology](#methodology)
- [Status](#status)
- [Sources](#sources)

## Clone

```shell
# Clone repository
git clone https://github.com/peppequint/css-to-the-rescue-1819.git

# Go to the repository
cd css-to-the-rescue-1819
```

## Concept

For this assignment I have made a restaurant menu. The concept is based on a table with four chairs in a restaurant. Each person can select there preferred dishes for the evening and it will be served to there table.

### Only CSS

During this assignment I did not wrote any line of Javascript. So every interaction is made with checkboxes and lots and lots of animations.

#### Checkboxes

The first customised shape I made was the knife at the bottom of every menu card. It is made with an input.

```html
<input type="checkbox" class="m-card--check m-card--first" />
```

With the CSS below, I made different shapes and one with text to give it some context.

```css
.m-card--check {
  -webkit-appearance: none;
  background-color: black;
  bottom: 7rem;
  border: 3px solid black;
  border-radius: 100% 0% 96% 4% / 0% 0% 100% 100%;
  color: white;
  cursor: pointer;
  display: block;
  height: 2.5rem;
  left: 45rem;
  position: absolute;
  width: 12rem;
  z-index: 1000 !important;
}

.m-card--check:before {
  background-color: black;
  border-bottom-left-radius: 2rem;
  content: "";
  display: block;
  height: 0.75rem;
  left: -2.5rem;
  position: absolute;
  top: 0.45rem;
  width: 2.5rem;
}

.m-card--check:after {
  content: "Keuze gemaakt";
  display: block;
  font-size: 1rem;
  font-weight: bold;
  left: 0.75rem;
  position: relative;
  top: 0.15rem;
}
```

To see if someone has made there choice by clicking on the knife, this line of code activates the animation to 'throw away' the menu card.

```css
.m-card--first:checked,
.m-card--first:checked ~ .m-card--first {
  animation: leave 1000ms ease forwards;
}
```

Also there are custom made 'icon' checkboxes. To achieve this, I turned off the opacity of the `input` and overwritten it with a `div`.
To style this new `div` I used, the same as the knife, `::before` & `::after` to create customised shapes.

```css
.m-checkbox--check {
  border-bottom: 15px solid black;
  border-left: 15px solid black;
  border-right: 15px solid black;
  border-top: 1px solid black;
  border-top-right-radius: 70px;
  border-top-left-radius: 70px;
  cursor: pointer;
  display: inline-block;
  height: 1.25rem;
  position: relative;
  transform: rotate(0deg);
  transition: 150ms ease;
  width: 1.5rem;
}

.m-checkbox--check::before {
  background-color: black;
  bottom: -18px;
  content: "";
  height: 4px;
  left: -22px;
  position: absolute;
  width: 2.85rem;
}

.m-checkbox--check::after {
  background-color: black;
  content: "";
  height: 4px;
  left: -2px;
  position: absolute;
  top: -5px;
  width: 5px;
}
```

## Restrictions

For this project I had to comply with two restrictions. I have chosen the following restrictions:

- [ ] Two colours
- [ ] No squares, no rectangles, no circles, no triangles

## Methodology

Also I used a methodology for this project. In this case, BEM. Sometimes it was really hard to follow the rules of BEM when you are experimenting with CSS, but for serious business project I think this methodology is really useful.

## Sources

- [CSS Transform Playground](https://css-transform.moro.es/)
- [Wooden pattern](https://www.transparenttextures.com/patterns/wood-pattern.png)
- [Noise pattern](http://api.thumbr.it/whitenoise-361x370.png?background=ffffffff&noise=5c5c5c&density=13&opacity=62)
