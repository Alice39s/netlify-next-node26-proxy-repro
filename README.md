# netlify-next-node26-proxy-repro

A Next.js 16 app with a Node.js `proxy`. On Node.js 26.8.0 and later, `netlify build` fails in the `onBuild` step of `@netlify/plugin-nextjs` 5.16.4:

```
Plugin "@netlify/plugin-nextjs" internal error
Error: Could not patch functions config manifest file
```

The [netlify build workflow](../../actions/workflows/netlify-build.yml) builds the app three times: on Node.js 24, on Node.js 26, and on Node.js 26 with [`fix.patch`](fix.patch) applied to the installed plugin.

The [CodeSandbox VM sandbox](https://codesandbox.io/p/sandbox/github/Alice39s/netlify-next-node26-proxy-repro) runs on Node.js 26 (`.devcontainer/devcontainer.json`) and starts `netlify build` when it boots (`.codesandbox/tasks.json`).

To run it yourself, use Node.js 26.8.0 or later:

```bash
npm install
npx netlify-cli build --offline
```
