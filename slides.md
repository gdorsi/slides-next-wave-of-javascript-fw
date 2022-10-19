---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: "/assets/2560px-Katsushika_Hokusai_-_The_Great_Wave_off_the_Coast_of_Kanagawa.jpg"
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
drawings:
  persist: false
# use UnoCSS
css: unocss
colorSchema: dark
---

# The new wave of Javascript frameworks

<style>
h1 {
  font-weight: 500;
  text-shadow: 4px 2px black;
}
</style>


<p class="text-pic">By Fabrizio A. Vitale & Guido D'Orsi</p>

---

# The first rise of the Javascript frameworks

<v-click>

## jQuery 🏆

</v-click>

<v-click>
```js
Select2.prototype.render = function () {
  var $container = $(
    '<span class="select2 select2-container">' +
      '<span class="selection"></span>' +
      '<span class="dropdown-wrapper" aria-hidden="true"></span>' +
    '</span>'
  );

  $container.attr('dir', this.options.get('dir'));

  this.$container = $container;

  this.$container[0].classList
    .add('select2-container--' + this.options.get('theme'));

  Utils.StoreData($container[0], 'element', this.$element);

  return $container;
};
```
</v-click>

<style>
h2 {
  background-color: yellow;
  background-image: linear-gradient(45deg, yellow 10%, orange 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: image-right
image: "/assets/rowell-heria-XFqzxqQja3g-unsplash.jpg"
---

# The coming of React

<v-clicks>

- Declarative
- Performant (compared to .innerHTML)
- Composable
- SSR!

</v-clicks>

---
layout: image
image: "/assets/jezael-melgoza-layMbSJ3YOE-unsplash.jpg"
---

<h1 class="text-pic">Today</h1>

---
layout: image-left
image: "/assets/alora-griffiths-E3wehabi_B4-unsplash.jpg"

class: bg-yellow-300
---

# React is starting to show it's limits

<v-clicks>

- Too many renders issue
- Lack of standards
- Hydration times

</v-clicks>

---
layout: image
image: "/assets/2560px-Katsushika_Hokusai_-_The_Great_Wave_off_the_Coast_of_Kanagawa.jpg"
---

<header class="fw-intro-header">
  <h1 class="text-pic fixed">The new wave of Javascript frameworks</h1>
  
  <v-click>
    <h2 class="text-pic fixed">Solid.js & Qwik</h2> 
  </v-click>
</header>

<style>
.fw-intro-header.fw-intro-header h1 {
  right: 1rem;
  top: 3rem;
}

.fw-intro-header.fw-intro-header h2 {
  right: 1rem;
  top: 8rem;
}
</style>

---
src: ./slides/solidjs.md
class: solidjs-slides
---

---
src: ./slides/qwik.md
class: qwik-slides
---

---

# Conclusions

## SolidJS

<v-clicks>

- Lightweight and fast runtime ⚡️
- Familiar DX for React developers
- Deceptively shallow learning curve

</v-clicks>

## Qwik

<v-clicks>

- Blazing fast page loads ⚡
- WIP 🚧
- All the closures must be serializable

</v-clicks>

---
layout: two-cols
---

# Thank you!

<div class="left-col-content">

## Slides

- [https://next-wave-fw-slides.netlify.app](https://next-wave-fw-slides.netlify.app)
- [<uim-github /> source](https://github.com/gdorsi/slides-next-wave-of-javascript-fw)


## Demo apps

- qwik [https://next-wave-fw-qwik.netlify.app/](https://next-wave-fw-qwik.netlify.app/)
- react [https://next-wave-fw-react.netlify.app/](https://next-wave-fw-react.netlify.app/)
- solid [https://next-wave-fw-solid.netlify.app/](https://next-wave-fw-solid.netlify.app/)
- [<uim-github /> source](https://github.com/FaberVitale/next-frameworks-sample-app)

## Speakers

- [Guido D'Orsi](https://github.com/gdorsi)
- [Fabrizio Vitale](https://github.com/FaberVitale)
</div>

::right::

<div class="slide-links">
<img width="240" height="240" src="/assets/slides-url.svg" />
</div>

<style>
h1 {
  font-size: 3.5rem !important;
  font-weight: 500;
  margin-bottom: 2rem !important;
}

h2 {
  margin-top: 2rem !important;
  margin-bottom: 0.3rem;
}

.slide-links {
  padding: 4rem 0 0;
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  gap: 1rem;
}

.left-col-content {
  font-size: 1rem;
}

</style>