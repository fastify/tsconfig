# tsconfig

> Shared [TypeScript configuration](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) for fastify projects

## Install

```
$ npm install --save-dev fastify-tsconfig
```

## Usage

Create your own `tsconfig.json` in the projects' root folder and extend it from `fastify-tsconfig`, overriding or adding the desired settings. By default, no `outDir` is set (because of [this issue](https://github.com/Microsoft/TypeScript/issues/29172)), so be sure to add one.

Depending on the type of the project, you should add the following settings.

### Application
`tsconfig.json`
```json
{
 "extends": "fastify-tsconfig",
 "compilerOptions": {
 "outDir": "dist",
 "sourceMap": true
 },
 "include": [
 "src/**/*.ts"
 ]
}
```
### Package
`tsconfig.json`

```json
{
 "extends": "fastify-tsconfig",
 "compilerOptions": {
 "outDir": "dist",
 "declaration": true
 },
 "include": [
 "src/**/*.ts"
 ]
}
```
### Monorepo Package
`tsconfig.json`

```json
{
 "extends": "fastify-tsconfig",
 "compilerOptions": {
 "outDir": "dist",
 "declarationMap": true,
 "composite": true
 },
 "include": [
 "src/**/*.ts"
 ]
}
```

Check the other settings [here](./tsconfig.json)

## Configuration target

The configuration targets ES2022, which is supported in Node.js 16 and later. Only one feature still needs to be implemented: [RegExp Match Indices shows up in flags](https://node.green/#ES2022). However, using ES2022 as a target makes widely used features not being compiled. To target an older version, override the `target` property.

## License

Licensed under [MIT](./LICENSE).

---

Inspired by: [sindresorhus/tsconfig](https://github.com/sindresorhus/tsconfig)

