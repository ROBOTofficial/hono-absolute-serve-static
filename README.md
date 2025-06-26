# `serveStaticWithAbsolute`

Absolute path version of @hono/node-server.

It has everything in common with serveStatic of @hono/node-server except that path and root are treated as absolute paths. (All options are also common.)

**This feature has been tested only on nodejs. We cannot guarantee that it will work on non-nodejs environments.**

This repository will be archived when absolute paths are officially introduced to serveStatic in @hono/node-server.

## Usage

```js
import { Hono } from "hono";
import { join } from "node:path";
import { serve } from "@hono/node-server";
import { serveStaticWithAbsolutePath } from "hono-absolute-serve-static";

const app = new Hono();

app.use(
	"/static/*",
	serveStaticWithAbsolutePath({
		root: join(import.meta.dirname, "./assets")
	})
);

serve({
	fetch: app.fetch,
	port: 3000
});
```

## Respect

[@hono/node-server](https://github.com/honojs/node-server)
