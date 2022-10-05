---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Katsushika_Hokusai_-_The_Great_Wave_off_the_Coast_of_Kanagawa.jpg/2560px-Katsushika_Hokusai_-_The_Great_Wave_off_the_Coast_of_Kanagawa.jpg
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
---

# The new wave of Javascript frameworks

By Fabrizio A. Vitale & Guido D'Orsi

---
layout: image
image: https://unsplash.com/photos/rCKIz0V7_Ok/download?ixid=MnwxMjA3fDB8MXxhbGx8fHx8fHx8fHwxNjY0OTc4MTY4&force=true&w=1920
---

# Once upon a time...


<style>
h1 {
  text-shadow: 1px 1px black;
}
</style>

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
image: https://unsplash.com/photos/XFqzxqQja3g/download?ixid=MnwxMjA3fDB8MXxhbGx8fHx8fHx8fHwxNjY0OTc5MDM4&force=true&w=1920
---

# The coming of React

<v-clicks>

- Declarative
- Performant (compared to .innerHTML)
- Composable

</v-clicks>

---
layout: image
image: https://unsplash.com/photos/layMbSJ3YOE/download?ixid=MnwxMjA3fDB8MXxzZWFyY2h8MTV8fGNpdHl8ZW58MHx8fHwxNjY0OTc4OTAw&force=true&w=1920
---

# Today

<style>
h1 {
  text-shadow: 1px 1px black;
}
</style>

---
layout: image-left
image: https://unsplash.com/photos/E3wehabi_B4/download?ixid=MnwxMjA3fDB8MXxzZWFyY2h8MXx8aGVhdnklMjBsaWZ0aW5nfGVufDB8fHx8MTY2NDkzNjMzNg&force=true&w=1920

class: bg-yellow-300
---

# React is starting to show it's limits

<v-clicks>

- Too many renders issue
- Hydration times
- Lack of standards

</v-clicks>

---
layout: image
image: https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Katsushika_Hokusai_-_The_Great_Wave_off_the_Coast_of_Kanagawa.jpg/2560px-Katsushika_Hokusai_-_The_Great_Wave_off_the_Coast_of_Kanagawa.jpg
---

# The new wave of Javascript frameworks

<v-click>

## Solid.js & Qwik 

</v-click>


<style>
h1, h2 {
  text-shadow: 2px 1px black;
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
