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
<h1>Run callback after the component is unmounted</h1>
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