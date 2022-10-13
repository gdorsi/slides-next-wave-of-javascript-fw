---
layout: cover
---

<img src="/assets/solid-logo-full.svg"/>


---
layout: two-cols
---

<header>
<h1>Conditional rendering</h1>
</header>

## React

```ts
function App() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);
  const toggle = () => setIsLoggedIn((val) => !val);

  return isLoggedIn ? (
    <button onClick={toggle}>Log out</button>
  ) : (
    <button onClick={toggle}>Log in</button>
  );
}
```

[playground](https://stackblitz.com/edit/react-ts-rwam95?file=index.tsx)

::right::

## Solid

```ts
function App() {
  const [isLoggedIn, setIsLoggedIn] = createSignal(false);
  const toggle = () => setIsLoggedIn((val) => !val);

  return (
    <Show 
      when={isLoggedIn()} 
      fallback={<button onClick={toggle}>Log in</button>}
    >
      <button onClick={toggle}>Log out</button>
    </Show>
  );
}
```

[playground](https://playground.solidjs.com/?version=1.4.1#NobwRAdghgtgpmAXGGUCWEwBowBcCeADgsrgM4Ae2YZA9gK4BOAxiWGjIbY7gAQi9GcCABM4jXgF9eAM0a0YvADo1aAGzQiAtACsyAegDucAEYqA3EogcuPfr2ZCouOAGU0Ac2hqsvVwAtaQylZeUUVOg1tPQsrKxl6CGZcNFoIXgBBQkIACgBKfiteBzSyPmA1Wg8POBEASQhfMjhcABkqmvqIAF1eAF4HJxd3Lyg1HJkx5rzLdJKIMt5cDrU4ft58-oA+Xma2jtqGnJyANzGCvp2AQjO1Gbi5oVwmdJyi4t4AHgCg3kN-YR9ECVaqHCD5aSTNRqExQZgAayBnxM9Fwy3SaQAwhoEUDltVVpItu0PLwMJ99Ci0WktkT3h8vlT0bwsTjESB8R5CcSqizURSmTT6V99D9DFt3vcIJIHkJROJjhcdp8soRePotr4RLRmPR4BBcAA6Gq4ACiq31uAAQvg6iI3mAoNkVHkpWBJN0gA)

---
layout: two-cols
---

<header>
<h1>Render lists</h1>
</header>

## React

```ts
const palette = [
  '#26547C', '#EF476F', '#FFD166', '#06D6A0'
];

function Palette({ palette }: { palette: string [] }) {
  return (
    <ul className="color-list">
      {palette.map((color) => (
        <li key={color} style={{ background: color }} />
      ))}
    </ul>
  );
}
```

[playground](https://stackblitz.com/edit/react-ts-7m7cen?file=index.tsx)

::right::

## Solid

```ts
const palette = [
  '#26547C', '#EF476F', '#FFD166', '#06D6A0'
];

function Palette(props: { palette: string[] }) {
  return (
    <ul class="color-list">
      <For each={props.palette}>
        {(color) => <li style={{ background: color }} />}
      </For>
    </ul>
  );
}
```

[playground](https://stackblitz.com/edit/solidjs-templates-zqyzcv?file=src%2Findex.tsx)

---
layout: two-cols
---

<header>
<h1>Run effect after on mount</h1>
</header>

## React

```ts
import { useEffect } from 'react';

function connectToDataSource() {
  console.log("subscribed");
  return () => { console.log("unsubscribed"); }
}

function Comp() {
   useEffect(() => {
    return connectToDataSource();
   }, []); 

   return <div>pink</div>;
}
```

[playground](https://stackblitz.com/edit/react-ts-h5vcsb?file=App.tsx)

::right::

## Solid

```ts
import { onMount, onCleanup } from "solid-js";

function connectToDataSource() {
  console.log("subscribed");
  return () => { console.log("unsubscribed"); }
}

function Comp() {
  onMount(() => {
    onCleanup(connectToDataSource());
  });

  return <div>pink</div>;
}
```


[playground](https://playground.solidjs.com/?version=1.4.1#NobwRAdghgtgpmAXGGUCWEwBowBcCeADgsrgM4Ae2YZA9gK4BOAxiWGjIbY7gAQi9GcCABM4jXgF9eAM0a0YvADo1aAGzQiAtACsyAegDucAEYqA3EogcuPfr1oQAsgwi4sDiAGE1cKBHpCKVl5RRU6DW09CysrGXoIZlw0R15mRwg4JIAVWgARKFwoAGUGFjgACgBKfiteNMcIuAA6NVoAcwrw+hMyZkY0EzgRFSrLCHqhXCYJ6t4AXgA+e3SIJtaOrrAEsh6+gaGRsDGpK0lYiHjE5NSvBUI5kDrPFwTcCrml2on6zx8-AIPVaZHL5QolMqsapjZ6SGEQZ5TGa8AA8IjQADdFoQMABrFH6dFY8bnBGJRp8BIwVx8eaCYRiRgfGpfFF3Ti8fSLDwiWjMejwNzNdpwXAAUV8gtwACF8ABJERbKCEQijACE8KsZFF2Q4cAY7ypNI8AFYAAwWsZgSQAXSAA)

---
layout: two-cols
---


<header>
<h1>Clean up after the component is unmounted</h1>
</header>


## React

```ts
import { useEffect } from 'react';

function Comp() {
   useEffect(() => {
    return () => {
      console.log("cleanup");
    }
   }, []); 

   return <div>pink</div>;
}
```

[playground](https://stackblitz.com/edit/react-ts-sibmkh?file=index.tsx)

::right::

## Solid

```ts
import { onCleanup } from "solid-js";

function Comp() {
  onCleanup(() => {
    console.log("cleanup");
  });

  return <div>pink</div>;
}
```

[playground](https://playground.solidjs.com/?version=1.4.1#NobwRAdghgtgpmAXGGUCWEwBowBcCeADgsrgM4Ae2YZA9gK4BOAxiWGjIbY7gAQi9GcCABM4jXgF9eAM0a0YvADo1aAGzQiAtACsyAegDucAEYqA3EogcuPfr1oQAwmrhQI9QlNnzFKuhraehZWVjL0EMy4aI68TgqEABQAlPxWvA7Oru6eiSm8ALwAfGkQGRnMjgFwAHRqtADmiSrM2R6EKsmWZVJdoT1CuExlADwiaABuRYQYANYj+uNT3ZL9lRBkfBEwDBC4AIKEXgWCwmKMeanFvCPxnLz6RVi8IrTM9PB7NQ1wuACirk+uAAQvgAJIiZpgKBHToAQj6ECsZF+ABUOHAGLhEttdgcjs8ACwABlJiLAkgAukA)

---
layout: two-cols
---

<header class="flex">
<h1>Create new project | Vite template</h1>
</header>

<img style="width: 60%; margin: 2rem auto 0;" src="/assets/vite-logo-shadow.png" alt="vite logo" aria-hidden="true" />

::right::

<section style="padding: 2rem; ">
```bash
npx degit solidjs/templates/ts my-solid-app
```

<div style="padding-top: 2rem;" />

## Guide

- [List of available templates](https://github.com/solidjs/templates/blob/master/README.md#solid-templates-using-vite)
- [Vite docs](https://vitejs.dev/)

## Rendering

- Client-side rendering - [solid-router](https://github.com/solidjs/solid-router).

</section>

---
layout: two-cols
---

<header class="flex">
<h1>Create new project | Astro</h1>
</header>

 <img style="margin: 5rem 1rem 0" src="/assets/astro-logo-dark.svg" alt="astro logo" />

::right::

<section style="padding: 2rem; ">

## Rendering

- [SSG - island architecture](https://docs.astro.build/en/concepts/islands)
- [SSR - node app o Edge functions](https://docs.astro.build/en/guides/server-side-rendering/)

## Guide

- [Getting started](https://docs.astro.build/en/getting-started/)
- [Integrate Solid](https://docs.astro.build/en/guides/integrations-guide/solid-js/)

</section>

---
layout: two-cols
---

<header class="flex">
<h1>Create new project | SolidStart</h1>
</header>

 <img style="margin: 2rem 0 0" src="/assets/solid-bg-1.svg" alt="solid logo" />

::right::

Meta-framework developed by the [SolidJS team](https://www.solidjs.com/contributors),
powered by [vite](https://vitejs.dev/) and currently in **beta**.

<section style="padding: 2rem; ">

## Rendering

- Client-side rendering (CSR)
- Server-side rendering (SSR)
- Streaming SSR
- Static site generation (SSG)

## Guides

- [What's SolidStart](https://start.solidjs.com/getting-started/what-is-solidstart)
- [Project setup](https://start.solidjs.com/getting-started/project-setup)

</section>
