# Demo purposes - proving the breaking of vscode emmet auto suggest

# 1. download this repo
```
git clone https://github.com/inspiraller/vscode-emmet.git
```

# 2 cd into repo
```
cd vscode-emmet
```

# 3 install packages
```
npm i
```

# open vscode-emmet into vscode and start typing into 
**src/types/_utils.ts**
(type) const s: TF
```ts
const s: TF
```
- Expect: Autosuggest for TFuncstr
- Actual: No autosuggest

-----------------------------------------------------------------------------
# How to fix?
1. Comment out the console.log like this:

**babel.config.js**
```
// console.log(1); // <- this console log is breaking vscode emmet auto suggest. 
```

2. Typing into to this file - it still does not work
**src/types/_utils.ts**
(type) const s: TF
```ts
const s: TF
```

3. Close vscode, and reopen - then try typing:
**src/types/_utils.ts**
(type) const s: TF
```ts
const s: TF
```
Now it works.
-----------------------------------------------------------------------------
# How to reproduce problem:

1. Uncomment the line like this:
**babel.config.js**
```
console.log(1); // <- this console log is breaking vscode emmet auto suggest. 
```

2. Typing into to this file - it still works...
**src/types/_utils.ts**
(type) const s: TF
```ts
const s: TF
```

3. Close vscode, and reopen - then try typing:
**src/types/_utils.ts**
(type) const s: TF
```ts
const s: TF
```

Now it does not work.

# Conclusion?
It seems that something in the typescript compiler is getting broken having a console.log in babel.config.js?
What is it?

