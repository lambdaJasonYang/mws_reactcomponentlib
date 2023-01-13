# Getting Started with Create React App

```
npx create-react-app mylib --template typescript
```

* Go to package.json and rename `"dependencies"` to `"devDependencies"`
* remove `"private": true`
* add `"main": "dist/index.js",`
* add `"module": "dist/index.js",`
* add `"files": [ "dist", "README.md" ],`

add 

```
  "peerDependencies": {
    "@types/react": "^18.0.26",
    "@types/react-dom": "^18.0.10",
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
```

make folder lib in src

```
npm i babel-cli --save-dev
```

in root, make a .babelrc

```
{
  "presets": [["react-app", { "absoluteRuntime": false }]]
}
```

replace build script with

```
"build": "rm -rf dist && NODE_ENV=production babel src/lib --out-dir dist --copy-files --ignore __tests__,spec.js,test.js,__snapshots__"
```