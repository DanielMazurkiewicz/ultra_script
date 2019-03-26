@ultra/script
=================

Credits
---------------

This project is based on [AssemblyScript](https://www.assemblyscript.org)


Roadmap
---------------
 
  * Automatic generation of unique identifiers with write back to source code
  * Automatic generation of serial numbers based on unique identifiers
  * Native translations support
  * Native HTML templates support


Getting started
---------------

All the details are provided in the [AssemblyScript wiki](https://github.com/AssemblyScript/assemblyscript/wiki) - make sure to pay it a visit. With that being said, the easiest way to get started with AssemblyScript is to point npm at the GitHub repository (for now)

```
$> npm install --save-dev AssemblyScript/assemblyscript
```

followed by [scaffolding](https://github.com/AssemblyScript/assemblyscript/wiki/Using-the-CLI#scaffolding-with-asinit) a new project including the necessary configuration files, for example in the current directory:

```
$> npx asinit .
```

Once the project is set up, it's just a matter of using your existing [TypeScript tooling](https://code.visualstudio.com) while coding, and [using the CLI](https://github.com/AssemblyScript/assemblyscript/wiki/Using-the-CLI) to build to WebAssembly, either manually, or using (and maybe modifying) the generated build task in the generated `package.json`:

```
$> npm run asbuild
```

The CLI API can also [be used programmatically](./cli).

If you rather prefer an installation suitable for development, pretty much the same can be achieved by cloning the GitHub repository instead:

```
$> git clone https://github.com/AssemblyScript/assemblyscript.git
$> cd assemblyscript
$> npm install
$> npm link
```

**Note** that a fresh clone of the compiler will use the distribution files in `dist/`, but it can also run [the sources](./src) directly through ts-node after an `npm run clean`, which is useful in development. This condition can also be checked by running `asc -v` (it is running the sources if it states `-dev`).


Building
--------

To build an UMD bundle to `dist/assemblyscript.js` (depends on [binaryen.js](https://github.com/AssemblyScript/binaryen.js)), including a browser version of asc to `dist/asc.js` (depends on assemblyscript.js):

```
$> npm run build
```

Cleaning the distribution files (again):

```
$> npm run clean
```

Linting potential changes:

```
$> npm run check
```

Running the [tests](./tests):

```
$> npm test
```

Running everything in order (lint, clean, test, build, test):

```
$> npm run all
```
