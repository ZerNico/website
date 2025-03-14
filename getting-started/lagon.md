# Lagon

[Lagon](https://lagon.app/) is an open source runtime and platform to run TypeScript and JavaScript Functions at the Edge.
It's neither Node.js nor Deno.

Note that some middlewares don't work or are useless.

## 1. Install

First, install the Lagon CLI. Please refer to [the official documentation](https://docs.lagon.app/cli#installation).

## 2. Setup

A starter for Lagon is available.
Start your project with "create-hono" command.

```
npm create hono@latest my-app
```

Move to `my-app` and install the dependencies.

```
cd my-app
npm i
```

## 3. Hello World

Edit `src/index.ts` like below.

```ts
// src/index.ts
import { Hono } from 'hono'
const app = new Hono()

app.get('/', (c) => c.text('Hello Lagon!'))

export const handler = app.fetch
```

## 4. Run

Run the command.

```ts
lagon dev src/index.ts
```

Then, access `http://localhost:1234` in your browser.

## Limitations

- The "Cache" middleware isn't supported yet

## Serve static files

Lagon serves your static files using the `public` directory by default.
