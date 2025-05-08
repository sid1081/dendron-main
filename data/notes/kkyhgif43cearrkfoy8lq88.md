
# Setup for Node for Typescript

```
mkdir my-node-app
cd my-node-app/
git init
npm init -y
npm i -D typescript ts-node @types/node
npx tsc --init
```

# Package.json setup

```
"build": "tsc",
"dev": "node --env-file=.env --watch -r ts-node/register src/index.ts",
```

