### Ch 1: Modules System, FS, REPL, NPM, Package.json

#### What is Node.js?ip- Node.js is a runtime environment that allows you to execute JavaScript code outside of a web browser.kin It provides APIs for asynchronous, non-blocking I/O operations.I/O Node.js uses the V8 JavaScript engine, which is also used by Google Chrome. V8 J### Is Node.js a web server? by Go, Node.js is not a web server.s is nois a runtime environment to execute JavaScript code.o createver, you can use Node.js to create web servers using modules like `http` or frameworks like Express.eb serverWhat are modules?tp` or fras are like libraries in C, C++.dules?
- Me encapsulates related code into a single unit of code.ted code intule has its own context, so it cannot interfere with other modules.fere with othan be reused across multiple projects.e projects.
-s a built-in module system.
#### What is ts the module system in Node.js? module system ia CommonJS module system.system.
- Moduleeusable pieces of code that can be exported from one program and imported for use in another program. exported from oneaded using the `require()` function. has its own contex its own context, so it cannot interfere with other modules.es can be reused acreused across multiple projects.
- In Node.js, every  use functions directly in Node.js?ctions defined in one file is treated as a separate module.dule in another module,fined in one module in another module, we need to export the functions using the `module.exports` object.orts` object.
- We can ported functions in another module using the `require()` function.require()` function.

#json and why is it important? It includes information sle that contains metadata about a Node.js project.nt because it helps manage  such as the project name, version, description, dependencies, and scripts.oject dependencies, scripts,it helps manage project dependencies, scripts, and configurations.encies, run scripts, and manaendencies, run scripts, and manage project settings.-Print-Loop.
- It is a simple REPL stands for Read-Eval-Print-Loop.ns the result.
- It is useful  computer programming environment. JavaScript
- `require` is usedas user input and returns the result.n include modules, JSON, and loca snippets and debugging.files.
    - Example: `re` and `import` typically in modern JavaScript envre` is used in CommonJS modules, typically in Node.js environments. It is synchronous and can include modules, JSON, and local filet is asynchronous and can import modequire('module-name');`
- `import` is used in ES6 moduldefault exports.
    - Example: `impvironments, including both client-side and server-side applications. It is asynchronous and can import modules, named exports, and default exporconditionally, while `import` statemenm 'module-name';`
- Note: `require` can be used co
#### All about the `fs` module
- Theare hoisted to the top of the file and cannot be used conditiona, deleting files, and more.
- Example: - The `fs` module in Node.js provides file system-related functionalds:
- `fs.readFile(path, options, callba manipulate files and directories.
- Common functions include readingire contents of a file.
- `fs.readFileSyns, deleting files, and more.
- Example: `const fs = require('fs
- `fs.writeFile(file, data, options, callbdFile(path, options, callback)`: Asynchronously reads the entire contents of a data, options)`: Synchronously writes data Synchronously reads the entire contents of a file.

##### Write file methods:
- `fs.wously reads the contents of a directory.
- `fchronously writes data to areaddirSync(path, options)`(file, data, options)`: Synchronously writes data to a file.

 directory.
- `fs.mkdirSync(path, options)`: Sys, callback)`: Asynchronously reads the contents of a dira file.
- `fs.unlinkSync(path)`: Synchronously dronously reads the contents of a diretes a file.
- `fs.rmdir(path, callcallback)`: Asynchronously creates a directory.
- `fs.mkdirSync(path, opt module provides both synchronous and asynchronous nlink(path, callback)`: Asynchronously deletethods for file system operations. It is recomusly a text file in ECMAScript 6:
```js
import fs from 'fs';

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log(data);
});
```

#### What is performance.now() in Node.js?
- The `performance.now()` method in Node.js returns a high-resolution timestamp in milliseconds.
- It is useful for measuring performance and benchmarking code execution time.
- Example:
```js
const { performance } = require('perf_hooks');

const start = performance.now();

// Code to measure
for (let i = 0; i < 1000000; i++) {
    // Some operation
}

const end = performance.now();
console.log(`Execution time: ${end - start} milliseconds`);
```

#### What is NPM?
- NPM stands for Node Package Manager.
- It is a package manager for Node.js packages/modules.
- It is used to install, manage, and publish Node.js packages.
- It comes bundled with Node.js installation.

#### Explain NPM INIT 
- `npm init` is a command used to initialize a new Node.js project.
- It creates a `package.json` file with project metadata such as name, version, description, entry point, test command, and dependencies.
- It guides you through a series of prompts to set up the project configuration.
- It is recommended to run `npm init` in the root directory of your project.

#### What is the purpose of `package-lock.json`?
- `package-lock.json` is a file generated by NPM to lock down the version of dependencies installed in a project.
- It ensures that the same versions of dependencies are installed across different environments.
- It helps in maintaining consistent and reproducible builds.
- It is recommended to commit `package-lock.json` to version control along with `package.json`.

#### What is the difference between `dependencies` and `devDependencies` in `package.json`?
- `dependencies`: These are the packages required for the application to run in production.
- `devDependencies`: These are the packages required for development and testing purposes.
- `dependencies` are installed when running `npm install`, while `devDependencies` are installed when running `npm install --dev` or `npm install --only=dev`.

#### How to install a package using NPM?
- To install a package using NPM, you can use the `npm install` command followed by the package name.
- Example: `npm install package-name`
- By default, the package will be installed as a dependency. To install it as a devDependency, you can use the `--save-dev` flag.
- Example: `npm install package-name --save-dev`

#### How to uninstall a package using NPM?
- To uninstall a package using NPM, you can use the `npm uninstall` command followed by the package name.
- Example: `npm uninstall package-name`
- By default, the package will be uninstalled from both dependencies and devDependencies. To uninstall it from only devDependencies, you can use the `--save-dev` flag.
- Example: `npm uninstall package-name --save-dev`

#### How to update a package using NPM?
- To update a package using NPM, you can use the `npm update` command followed by the package name.
- Example: `npm update package-name`
- By default, the package will be updated to the latest version. To update it to a specific version, you can specify the version number.
- Example: `npm update package-name@1.0.0`

#### How to list installed packages using NPM?
- To list installed packages using NPM, you can use the `npm list` command.
- Example: `npm list`
- By default, it will list all installed packages in the current project.
- To list only the top-level packages, you can use the `--depth=0` flag.
- Example: `npm list --depth=0`

#### How to run scripts defined in `package.json` using NPM?
- To run scripts defined in `package.json` using NPM, you can use the `npm run` command followed by the script name.
- Example: `npm run script-name`
- By default, it will run the script specified in the `scripts` section of `package.json`.
- You can also define custom scripts in the `scripts` section of `package.json` and run them using `npm run`.

#### Semantic Versioning (SemVer)
- Semantic Versioning (SemVer) is a versioning scheme for software that uses a three-part version number: `MAJOR.MINOR.PATCH`.
- Each part of the version number has a specific meaning:
    - `MAJOR`: Incremented for incompatible API changes.
    - `MINOR`: Incremented for adding functionality in a backward-compatible manner.
    - `PATCH`: Incremented for backward-compatible bug fixes.
- Example: `1.2.3` where `1` is the major version, `2` is the minor version, and `3` is the patch version.
- Using SemVer helps in communicating the nature of changes in new releases and managing dependencies effectively.
- More information can be found at [semver.org](https://semver.org/).


#### Understanding Version Ranges in `package.json`
- In `package.json`, version ranges can be specified using different symbols to define the acceptable versions of a dependency.
- Common symbols include:
    - `~`: Tilde specifies the most recent patch version. For example, `~1.2.3` will match all `1.2.x` versions where `x` is greater than or equal to `3`.
    - `^`: Caret specifies the most recent minor version. For example, `^1.2.3` will match all `1.x.x` versions where `x` is greater than or equal to `2`.
    - `*`: Asterisk matches any version. For example, `*` will match any version of the dependency.
    - `>=`: Greater than or equal to specifies a minimum version. For example, `>=1.2.3` will match any version greater than or equal to `1.2.3`.
    - `<=`: Less than or equal to specifies a maximum version. For example, `<=1.2.3` will match any version less than or equal to `1.2.3`.
    - `>`: Greater than specifies versions greater than the given version. For example, `>1.2.3` will match any version greater than `1.2.3`.
    - `<`: Less than specifies versions less than the given version. For example, `<1.2.3` will match any version less than `1.2.3`.
- Using these symbols helps in managing dependencies and ensuring compatibility with different versions of packages.
- Example:
    - `"dependencies": { "package-name": "~1.2.3" }`
    - `"dependencies": { "package-name": "^1.2.3" }`
    - `"dependencies": { "package-name": ">=1.2.3" }`
- More information can be found in the [npm documentation](https://docs.npmjs.com/about-semantic-versioning).


#### what is gitingore file
- The `.gitignore` file is used to specify files and directories that should be ignored by Git.
- It helps in preventing sensitive or unnecessary files from being committed to the repository.
- Common examples of files to ignore include log files, build artifacts, configuration files, and dependencies.
- The `.gitignore` file uses patterns to match files and directories that should be ignored.
- Example:
    - `node_modules/`: Ignores the `node_modules` directory.
    - `*.log`: Ignores all files with the `.log` extension.
    - `config.json`: Ignores the `config.json` file.
- It is recommended to create a `.gitignore` file in the root directory of the project to manage ignored files effectively.
