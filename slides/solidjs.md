---
layout: cover
---

<img src="/assets/solid-logo-full.svg"/>

--- 
layout: two-cols
---

<style>
.solid-perf-img-wrapper {
  height: 100%;
  width: 100%;
}

.solid-perf-img {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%
}
</style>

<header>
<h1>SolidJS is Performant</h1>
</header>

<div class="relative solid-perf-img-wrapper solid-js-bg2">
  <img class="solid-perf-img" src="/assets/christian-englmeier-J7EUjSlNQtg-unsplash.jpg" logo="speed" aria-hidden="true" />
</div>

::right::
<div class="solidjs-click-list">

<v-clicks>

- It's **just** [7.3KB min+gzip](https://bundlephobia.com/package/solid-js@1.5.1).
- At the top of UI speed and memory utilization [benchmarks](https://krausest.github.io/js-framework-benchmark/index.html).
- Blazing fast server-side rendering, based on string interpolation.
- No Virtual Dom, [components render once](https://www.solidjs.com/guides/reactivity).

</v-clicks>


</div>

---

# Familiar api for React developers

<div class="solidjs-click-list">
<v-clicks>

- [useState](https://reactjs.org/docs/hooks-reference.html#usestate) <mdi-arrow-right /> [createSignal](https://www.solidjs.com/docs/latest/api#createsignal)
- [useEffect](https://reactjs.org/docs/hooks-reference.html#useeffect) <mdi-arrow-right /> [createEffect](https://www.solidjs.com/docs/latest/api#createeffect)
- [useMemo](https://reactjs.org/docs/hooks-reference.html#usememo) <mdi-arrow-right /> [createMemo](https://www.solidjs.com/docs/latest/api#creatememo)
- [useContext](https://reactjs.org/docs/hooks-reference.html#usecontext) <mdi-arrow-right /> [useContext](https://www.solidjs.com/docs/latest/api#usecontext)
- [&lt;Suspense /&gt;](https://reactjs.org/docs/react-api.html#reactsuspense) <mdi-arrow-right /> [&lt;Suspense /&gt;](https://www.solidjs.com/docs/latest/api#suspense)
- [useQuery/useSwr](https://swr.vercel.app/) <mdi-arrow-right /> [createResource](https://www.solidjs.com/docs/latest/api#createresource)
- [and much more...](https://www.solidjs.com/docs/latest/api)

</v-clicks>

</div>

---
layout: center
---

# Solid component

```typescript
function Counter() {
  const [count, setCount] = createSignal(0);

  return (
    <button 
      type="button" 
      onClick={() => setCount((n) => ++n)}
    >
      {count}
    </button>
  );
}
```

A simple Solid component it's just a function that returns a [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)

that runs **once** per instance, in other words, does not rerender. 
---

<style>
  .react-recon-pos {
    right: 3rem;
    top: 12rem;
  }
  .react-recon-count {
    right: 20rem;
    top: 10.2rem;
    font-size: 1.4rem;
  }
</style>

<h1 class="absolute">React reconciliation</h1>

<div class="relative" style="padding: 2.5rem 1rem 1rem">
  <div class="absolute react-recon-count">
    count: <s>7</s>=><strong>8</strong>
  </div>
  <pre><code class="absolute react-recon-pos">setCount(n => n + 1);</code></pre>
 <img src="/assets/react-reconciliation.svg" alt="react reconciliation" />
</div>

---

<style>
  .react-recon-pos {
    right: 3rem;
    top: 12rem;
  }

  .react-recon-count {
    right: 20rem;
    top: 10.2rem;
    font-size: 1.4rem;
  }
</style>

<h1 class="absolute">SolidJS update</h1>
<div class="relative" style="padding: 2.5rem 1rem 1rem">
  <div class="absolute react-recon-count">
    count: <s>7</s>=><strong>8</strong>
  </div>
  <pre><code class="absolute react-recon-pos">setCount(n => n + 1);</code></pre>
 <img src="/assets/solidjs-update.svg" alt="react reconciliation" />
</div>

---

# Fine-Grained reactivity

```typescript
function createSignal(value) {
  const subscribers = new Set();

  const read = () => {
    const listener = getCurrentListener(); // component, createEffect etc...
    if (listener) subscribers.add(listener);
    return value;
  };

  const write = (nextValue) => {
    value = nextValue;
    for (const sub of subscribers) sub.run();
  };

  return [read, write];
}
```

- subscribers are created with [createEffect](https://www.solidjs.com/docs/latest/api#createeffect), [createRenderEffect](https://www.solidjs.com/docs/latest/api#createrendereffect), createComponent etc...
- observables are created with [createSignal](https://www.solidjs.com/docs/latest/api#createsignal), [createStore](https://www.solidjs.com/docs/latest/api#createstore), [createMemo](https://www.solidjs.com/docs/latest/api#creatememo) etc...

[reactivity guide](https://www.solidjs.com/guides/reactivity)

--- 
layout: two-cols
---

<header>
<h1>Component State</h1>
</header>

## React

```ts
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button
      type="button" 
      onClick={() => setCount((n) => ++n)}
    >
      {count}
    </button>
  );
}
```

[playground](https://stackblitz.com/edit/react-ts-nrbhfx?file=index.tsx)

::right::

## Solid

```ts
function Counter() {
  const [count, setCount] = createSignal(0);

  return (
    <button 
      type="button" 
      onClick={() => setCount((n) => ++n)}
    >
      {count}
    </button>
  );
}
```

[playground](https://playground.solidjs.com/?version=1.4.1#NobwRAdghgtgpmAXGGUCWEwBowBcCeADgsrgM4Ae2YZA9gK4BOAxiWGjIbY7gAQi9GcCABM4jXgF9eAM0a0YvADo1aAGzQiAtACsyAegDucAEYqA3EogcuPfr2ZCouOAGU0Ac2hqps+YpU6DW09CysrZloIMj4TXAhXAjU4XgBefiteZTAZKNwtMjQALzgVRGyAZiEYFSwrSUsIKxl6CGZcNCjeAGEGCBdGAAoASgyILMjovmBI1twsXjI4XF65gF00hycXdy8oNUGABmHGzMFlpnHBs6yAHhN6XFwumPxk1JA4hKS4aQJiVIqB5PKIqXhRboaZgAaw+IzSAD5FstVv1BoMIKNUkiANQ4zGSBE3LL8Wb9STE276YHPCBE8a8E71cIQISicTorFI26oga8fQIhYiWjMejwfoAOg8ywAoslxbgAEL4ACSImuYCghEIKmGTMwkjWQA)


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
<h1>Run effect on mount</h1>
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

# Ecosystem | Libraries

<div class="solidjs-click-list">
<v-clicks>

- [react-use](https://github.com/streamich/react-use) <mdi-arrow-right /> [solid-primitives](https://github.com/solidjs-community/solid-primitives)
- [react-router](https://reactrouter.com/en/main) <mdi-arrow-right /> [solid-router](https://github.com/solidjs/solid-router)
- [react-transition-group](https://reactcommunity.org/react-transition-group/) <mdi-arrow-right />  [solid-transition-group](https://github.com/solidjs/solid-transition-group)
- [react-testing-library](https://testing-library.com/docs/react-testing-library/intro/) <mdi-arrow-right /> [solid-testing-library](https://github.com/solidjs/solid-testing-library)
- [@tanstack/react-query](https://tanstack.com/query/v4/docs/adapters/react-query) <mdi-arrow-right /> [@tanstack/solid-query](https://tanstack.com/query/v4/docs/adapters/solid-query)
- [@tanstak/react-table](https://tanstack.com/table/v8/docs/adapters/react-table) <mdi-arrow-right /> [@tanstack/solid-table](https://tanstack.com/table/v8/docs/adapters/solid-table)
- [react-window](https://react-window.vercel.app/#/examples/list/fixed-size) <mdi-arrow-right />  [solid-virtual](https://tanstack.com/virtual/v3/docs/adapters/solid-virtual)
- [...and much more](https://www.npmjs.com/search?q=solidjs)

</v-clicks>
</div>

---
layout: two-cols
---

<style>
  .asterisk {
    position: fixed;
    left: 4rem;
    bottom: 3rem;
    z-index: 2;
  }
</style>

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

## Rendering

- Client-side rendering - [solid-router](https://github.com/solidjs/solid-router).
- [Server-side rendering \*](https://www.solidjs.com/guides/server) 

## Guides

- [List of available templates](https://github.com/solidjs/templates/blob/master/README.md#solid-templates-using-vite)
- [Vite docs](https://vitejs.dev/)

</section>

<div class="asterisk"> 
<a href="https://vitejs.dev/guide/ssr.html#server-side-rendering" target="_blank">* some assembly required</a>
</div>

---
layout: two-cols
---

<header class="flex">
<h1>Create new project | Astro</h1>
</header>

 <img style="margin: 5rem 1rem 0" src="/assets/astro-logo-dark.svg" alt="astro logo" />

::right::

<section style="padding: 2rem; ">


```bash
npm create astro@latest
```

<br />

## Rendering

- [SSG - island architecture](https://docs.astro.build/en/concepts/islands)
- [SSR - node app o Edge functions](https://docs.astro.build/en/guides/server-side-rendering/)

## Guides

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

---
layout: image-right
image: /assets/mahdi-bafande.jpg
---

## Resources

- [SolidJS intro (100 Seconds)](https://www.youtube.com/watch?v=hw3Bx5vxKl0)
- [SolidJS Tutorial](https://www.solidjs.com/tutorial/introduction_basics)
- [API Reference](https://www.solidjs.com/docs/latest/api)
- [FAQ: Why doesn't my early return work in Solid?](https://www.youtube.com/watch?v=Ilf34WjMBkU)
- [Benchmarks](https://krausest.github.io/js-framework-benchmark/index.html)

## Community

- [<uim-twitter /> - twitter](https://twitter.com/solid_js)
- [<uim-discord /> - discord](https://discord.com/invite/solidjs)
- [<uim-github /> - github](https://github.com/solidjs/solid)
- [<uim-youtube /> - youtube](https://www.youtube.com/channel/UCXsRnrbzIX8KHdf86PE241Q)