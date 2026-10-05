# Gyral

**Model-View-Intent web components on the modern web platform.**

Gyral keeps the best idea of [Cycle.js](https://cycle.js.org) — your app is a pure function,
side effects happen at the edges as data, and data flows in one visible loop — and rebuilds it
on today's web: custom elements and Shadow DOM, [Lit](https://lit.dev) templates, semantic HTML,
modern CSS, and server rendering that hydrates in place. No stream library to learn.

```ts
define<{ count: number }, Msg>('gy-counter', {
  init: () => ({ count: 0 }),
  intent: { Increment: () => ({ _tag: 'Increment' }) },
  update: { Increment: (s) => ({ count: s.count + 1 }) },
  view: (s, i) => html`
    <output>${s.count}</output>
    <button type="button" data-intent=${i.Increment}>Increment</button>
  `,
});
```

Gyral is in active development ahead of its first public release. Source, docs and packages
are coming soon.

Created by Mike Zupper · Inspired by Cycle.js (MIT)
