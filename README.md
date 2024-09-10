# Typescript project starter

1. `npm install -g pnpm`
1. `npm init -y`
1. `pnpm add -D typescript @types/node nodemon ts-node @swc/core @swc/helpers regenerator-runtime`
1. `npx tsc --init`
1. tsconfig.json:
    ```json
    {
        "compilerOptions": {
            "target": "ES2022",
            "lib": ["ESNext"],
            "module": "commonjs",
            "rootDir": ".",
            "sourceMap": true,
            "outDir": "dist",
            "esModuleInterop": true,
            "forceConsistentCasingInFileNames": true,
            "strict": true,
            "skipLibCheck": true
        },
        "ts-node": {
            "swc": true
        }
    }
    ```
1. Add to package.json scripts: `"dev": "nodemon src/index.ts"`
