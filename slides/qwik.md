---
layout: cover
---

<img src="/assets/qwik.png"/>

---
layout: section
---

# No Hydration?!?

---
layout: cover
---

# React 17 Hydration

<img src="/assets/hydration-1.png"/>

---
layout: cover
---

# React 17 Hydration

<img src="/assets/hydration-react-17.png"/>

---
layout: cover
---

# React 18 Hydration

<img src="/assets/hydration-1.png"/>

---
layout: cover
---

# React 18 Hydration

<img src="/assets/hydration-react-18.png"/>

---
layout: cover
---

# Islands Hydration (like Astro)

<img src="/assets/hydration-1.png"/>

---
layout: cover
---

# Islands Hydration (like Astro)

<img src="/assets/hydration-island.png"/>

---
layout: cover
---

# Qwik (resumability)

<img src="/assets/hydration-1.png"/>

---
layout: cover
---

# Qwik (resumability)

<img src="/assets/hydration-qwik-0.png"/>

---
layout: cover
---

# Qwik (resumability)

<img src="/assets/hydration-qwik.png"/>

---
layout: cover
---

<img src="/assets/qwik-lazy.png"/>

---

## Auto lazy loading!

```js
import { component$ } from '@builder.io/qwik';

export const App = component$(() => {
  const str = 'hello';

  return (
    <button onClick$={() => alert(str)}>
      Hello Qwik
    </button>
  );
});
```

[Playground](https://qwik.builder.io/playground#version=0.11.0&buildMode=development&entryStrategy=hook&files=JTVCJTdCJTIycGF0aCUyMiUzQSUyMiUyRmFwcC50c3glMjIlMkMlMjJjb2RlJTIyJTNBJTIyaW1wb3J0JTIwJTdCJTIwY29tcG9uZW50JTI0JTIwJTdEJTIwZnJvbSUyMCclNDBidWlsZGVyLmlvJTJGcXdpayclM0IlNUNuJTVDbmV4cG9ydCUyMGNvbnN0JTIwQXBwJTIwJTNEJTIwY29tcG9uZW50JTI0KCgpJTIwJTNEJTNFJTIwJTdCJTVDbiUyMCUyMGNvbnN0JTIwc3RyJTIwJTNEJTIwJ2hlbGxvJyU1Q24lNUNuJTIwJTIwcmV0dXJuJTIwJTNDYnV0dG9uJTIwb25DbGljayUyNCUzRCU3QigpJTIwJTNEJTNFJTIwYWxlcnQoc3RyKSU3RCUzRUhlbGxvJTIwUXdpayUzQyUyRmJ1dHRvbiUzRSUzQiU1Q24lN0QpJTNCJTVDbiUyMiU3RCUyQyU3QiUyMnBhdGglMjIlM0ElMjIlMkZlbnRyeS5zZXJ2ZXIudHN4JTIyJTJDJTIyY29kZSUyMiUzQSUyMmltcG9ydCUyMCU3QiUyMHJlbmRlclRvU3RyaW5nJTJDJTIwUmVuZGVyT3B0aW9ucyUyMCU3RCUyMGZyb20lMjAnJTQwYnVpbGRlci5pbyUyRnF3aWslMkZzZXJ2ZXInJTNCJTVDbmltcG9ydCUyMCU3QiUyMFJvb3QlMjAlN0QlMjBmcm9tJTIwJy4lMkZyb290JyUzQiU1Q24lNUNuZXhwb3J0JTIwZGVmYXVsdCUyMGZ1bmN0aW9uJTIwKG9wdHMlM0ElMjBSZW5kZXJPcHRpb25zKSUyMCU3QiU1Q24lMjAlMjByZXR1cm4lMjByZW5kZXJUb1N0cmluZyglM0NSb290JTIwJTJGJTNFJTJDJTIwb3B0cyklM0IlNUNuJTdEJTVDbiUyMiU3RCUyQyU3QiUyMnBhdGglMjIlM0ElMjIlMkZyb290LnRzeCUyMiUyQyUyMmNvZGUlMjIlM0ElMjJpbXBvcnQlMjAlN0IlMjBBcHAlMjAlN0QlMjBmcm9tJTIwJy4lMkZhcHAnJTNCJTVDbiU1Q25leHBvcnQlMjBjb25zdCUyMFJvb3QlMjAlM0QlMjAoKSUyMCUzRCUzRSUyMCU3QiU1Q24lMjAlMjByZXR1cm4lMjAoJTVDbiUyMCUyMCUyMCUyMCUzQ2h0bWwlM0UlNUNuJTIwJTIwJTIwJTIwJTIwJTIwJTNDaGVhZCUzRSU1Q24lMjAlMjAlMjAlMjAlMjAlMjAlMjAlMjAlM0N0aXRsZSUzRUhlbGxvJTIwUXdpayUzQyUyRnRpdGxlJTNFJTVDbiUyMCUyMCUyMCUyMCUyMCUyMCUzQyUyRmhlYWQlM0UlNUNuJTIwJTIwJTIwJTIwJTIwJTIwJTNDYm9keSUzRSU1Q24lMjAlMjAlMjAlMjAlMjAlMjAlMjAlMjAlM0NBcHAlMjAlMkYlM0UlNUNuJTIwJTIwJTIwJTIwJTIwJTIwJTNDJTJGYm9keSUzRSU1Q24lMjAlMjAlMjAlMjAlM0MlMkZodG1sJTNFJTVDbiUyMCUyMCklM0IlNUNuJTdEJTNCJTVDbiUyMiU3RCU1RA%3D%3D)

---

## Auto lazy loading! - Output

app_component_button_onclick_0x8svzfkndi.js
```js
import { useLexicalScope } from "@builder.io/qwik";
export const App_component_button_onClick_0X8SVzFKNdI = ()=>{
    const [str] = useLexicalScope();
    return alert(str);
};
```

app_component_akbu84a8zes.js
```js
import { jsxDEV as _jsxDEV } from "@builder.io/qwik/jsx-dev-runtime";
import { qrlDEV } from "@builder.io/qwik";
export const App_component_AkbU84a8zes = ()=>{
    const str = 'hello';
    return /*#__PURE__*/ _jsxDEV("button", {
        onClick$: qrlDEV(()=>import("./app_component_button_onclick_0x8svzfkndi"), "App_component_button_onClick_0X8SVzFKNdI", {
            file: "/app.tsx",
            lo: 137,
            hi: 153,
            displayName: "App_component_button_onClick"
        }, [
            str
        ]),
        children: "Hello Qwik"
    }, void 0, false, {
        fileName: "/app.tsx",
        lineNumber: 6,
        columnNumber: 10
    }, this);
};
```
---

## Auto lazy loading! - Resuming

```html {all|8-12,15-17}
<!DOCTYPE html>
<html q:container="paused" q:version="0.11.0" q:render="ssr" q:base="/repl/21uldbnhtl3/build/">
  <html>
    <head q:head>
      <title q:head>Hello Qwik</title>
    </head>
    <body>
      <!--qv q:id=0 q:key=AkbU84a8zes:-->
      <button
        on:click="app_component_button_onclick_0x8svzfkndi.js#App_component_button_onClick_0X8SVzFKNdI[0]"
        q:id="1"
      >Hello Qwik</button><!--/qv-->
    </body>
  </html>
  <script type="qwik/json">
    {"ctx":{"#1":{"r":"0"}},"objs":["hello"],"subs":[]}
  </script>
  <script id="qwikloader">
   // qwik loader minifyed code
  </script>
  <script>
    window.qwikevents.push("click")
  </script>
</html>
```

--- 

# [Demo Time!](https://next-wave-fw-qwik.netlify.app/?q=Javascript)

---

# Is production ready?

<v-clicks>
- Meta-framework: Qwik City (supports both SSR and SSG)
- It's still in alpha (they are still working on the core API)
- You can easily find some bugs related to the rendering
- The docs are barebone and there are many undocumented API
</v-clicks>

---

# Open source

Qwik is still young and requires alot of work to become stable.

It's a huge opportunity to become a contributor!

<v-clicks>
- Open issues
- Contribute to the documentation
- Join discord and collaborate on the development!
</v-clicks>
