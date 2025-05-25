## Clear cache of a project

Clear cache, delete lock file and remove `node_modules` recursively:
```bash
pnpm cache delete && rm -rf pnpm-lock.yaml && find . -name 'node_modules' -type d -prune -exec rm -rf '{}' +
```