# Gyral

**Model-View-Intent web components on the modern web platform.**

Gyral keeps the best idea of [Cycle.js](https://cycle.js.org) — your app is a pure function,
side effects happen at the edges as data, and data flows in one visible loop — and rebuilds it
on today's web: custom elements and Shadow DOM, its own small template layer, semantic HTML,
modern CSS, and server rendering that hydrates in place. No stream library to learn.

```ts
import { define, html } from '@gyral/core';

type Msg = { _tag: 'Increment' };

define<{ count: number }, Msg>()('gy-counter', {
  init: () => ({ count: 0 }),
  intent: { Increment: () => ({ _tag: 'Increment' }) },
  update: { Increment: (s) => ({ count: s.count + 1 }) },
  view: (s, i) => html`
    <output>${s.count}</output>
    <button type="button" data-intent=${i.Increment}>Increment</button>
  `,
});
```

```sh
npm create gyral@latest my-app
```

The current release is **0.3.1** on npm (`@gyral/*`). Start with the
[getting-started guide](https://gyral.dev/docs/getting-started/) or the [docs](https://gyral.dev/docs/).

## Repositories

| Repository                                          | What it is                                                                         |
| --------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [gyral](https://github.com/gyraljs/gyral)           | The framework: `@gyral/*` packages, `create-gyral`, examples, the agent skill      |
| [gyral-rs](https://github.com/gyraljs/gyral-rs)     | Gyral server rendering embedded in Rust (deno_core, bounded V8 workers, Axum)      |
| [gyral.dev](https://github.com/gyraljs/gyral.dev)   | The website at [gyral.dev](https://gyral.dev): docs, examples, blog                |
| [gyral-shop](https://github.com/gyraljs/gyral-shop) | A full department-store web app built with Gyral                                   |
| [benchmarks](https://github.com/gyraljs/benchmarks) | The same apps in Gyral and other frameworks, measured, including where Gyral loses |
| [brand](https://github.com/gyraljs/brand)           | Logos, wordmarks and the brand guide                                               |

Created by Mike Zupper · Inspired by Cycle.js (MIT)
