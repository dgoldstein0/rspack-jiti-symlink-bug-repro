# rspack-repro

- [Rspack website](https://rspack.rs/)
- [Rspack repo](https://github.com/web-infra-dev/rspack)

## Repro

```bash
cd package_root;
pnpm i;
pnpm build:rspack;
```

expect to see rspack build, but it fails with error:

```
> rspack-repro@1.0.0 build:rspack /home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root
> cross-env RSPACK=1 node --preserve-symlinks --preserve-symlinks-main ./node_modules/@rspack/cli/bin/rspack.js

[rspack] CLI failed:
Error: Cannot find module 'html-webpack-plugin'
Require stack:
- /home/dgoldstein/src/rspack-jiti-symlink-bug-repro/symlinked-config-helper.js
    at Module._resolveFilename (node:internal/modules/cjs/loader:1207:15)
    at Function.resolve (node:internal/modules/helpers:193:19)
    at jitiResolve (/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/compiled/jiti/dist/jiti.cjs:1:148703)
    at jitiRequire (/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/compiled/jiti/dist/jiti.cjs:1:150290)
    at import (/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/compiled/jiti/dist/jiti.cjs:1:158307)
    at /home/dgoldstein/src/rspack-jiti-symlink-bug-repro/symlinked-config-helper.js:1:251
    at eval_evalModule (/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/compiled/jiti/dist/jiti.cjs:1:155533)
    at jitiRequire (/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/compiled/jiti/dist/jiti.cjs:1:150967)
    at import (/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/compiled/jiti/dist/jiti.cjs:1:158307)
    at /home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/rspack.config.mjs:3:59
    at async Function.import (/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/compiled/jiti/dist/jiti.cjs:1:158301)
    at async loadRspackConfig (file:///home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/dist/162.js:1097:26)
    at async RspackCLI.loadConfig (file:///home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/dist/162.js:1259:24)
    at async RspackCLI.buildCompilerConfig (file:///home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/dist/162.js:1144:35)
    at async runBuild (file:///home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/dist/162.js:759:24)
    at async file:///home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/dist/162.js:774:13
    at async RspackCLI.run (file:///home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/dist/162.js:1201:34)
    at async runCLI (file:///home/dgoldstein/src/rspack-jiti-symlink-bug-repro/package_root/node_modules/@rspack/cli/bin/rspack.js:22:3) {
  code: 'MODULE_NOT_FOUND',
  requireStack: [
    '/home/dgoldstein/src/rspack-jiti-symlink-bug-repro/symlinked-config-helper.js'
  ]
}
```
