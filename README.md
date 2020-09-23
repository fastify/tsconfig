# tsconfig

> Shared [TypeScript configuration](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) for fastify projects

## Install

```
$ npm install --save-dev fastify-tsconfig
```

## Usage

Extend your own `tsconfig.json` file from `fastify-tsconfig` and override/add the desired settings. By default no `outDir` is set (because of [this issue](https://github.com/Microsoft/TypeScript/issues/29172)) , so be sure to add one.

`tsconfig.json`

```json
{
  "extends": "fastify-tsconfig",
  "compilerOptions": {
    "outDir": "build",
    "target": "es2018",
    "lib": ["es2018"]
  }
}
```

Check the other settings [here](./tsconfig.json)

## Configuration target

The configuration targets es2018, that is supported in Node.js 10 and later. There is only one feature that is is missing from Node.js v10: [Proxy "ownKeys"](https://node.green/#ES2018) . However using es2018 as target makes some widely used features ("object rest properties", "object spread properties", and "Asynchronous Iterators") not being transpiled. To target some other version, just override `target` property.

## License

Licensed under [MIT](./LICENSE).

---

Inspired by: [sindresorhus/tsconfig](https://github.com/sindresorhus/tsconfig)
