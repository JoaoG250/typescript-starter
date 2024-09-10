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
1. `pnpm add -D eslint @eslint/js @types/eslint__js typescript-eslint eslint-config-prettier eslint-plugin-prettier`
1. `pnpm add -D --save-exact prettier`
1. eslint.config.mjs:
    ```js
    // @ts-check

    import eslint from "@eslint/js";
    import tseslint from "typescript-eslint";
    import eslintPluginPrettier from "eslint-plugin-prettier/recommended";

    export default tseslint.config(
    eslint.configs.recommended,
    ...tseslint.configs.strict,
    ...tseslint.configs.stylistic,
    {
        rules: {
        "@typescript-eslint/explicit-function-return-type": "error",
        },
    },
    eslintPluginPrettier, // last item always
    );
    ```
1. prettier.config.mjs:
    ```js
    export default {
        trailingComma: "all",
    };
    ```
1. test application: `pnpm run dev`
