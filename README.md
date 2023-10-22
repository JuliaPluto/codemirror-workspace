# Codemirror workspace

This repository enables one to work only the different codemirror projects required to compile a codemirror bundle for Pluto's frontend.

Make sure version in `lezer-julia/package.json` match `lezer-julia` version in `lang-julia/package.json`. Equally, version in `lang-julia/package.json` must match version in `codemirror-pluto-setup/package.json` for `@plutojl/lang-julia` otherwise, the version will be fetched from npm repository.

```bash
cd codemirror-workspace
git submodule update --init --recursive
yarn install
```

## lezer-julia

```bash
cd lezer-julia
make
make test
```

## lang-julia

```bash
cd lang-julia
npm run prepare
```

## codemirror-pluto-setup

```bash
cd codemirror-pluto-setup
npm run bundle
cp dist/index.es.js <path to pluto.jl>/frontend/imports/
# edit <path to pluto.jl>/frontend/imports/CodeMirror.js to import from index.es.js
```

