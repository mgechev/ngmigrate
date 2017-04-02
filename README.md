# Automated Migration

Tool for automatic migration of Angular applications.

`ngmigrate` is PoC, so it implements a single migration strategy - `<template>` elements to `<ng-template>`.

![](./resources/migrate.gif)

### Context-aware automated migration of `<template>` to `<ng-template>`.

This tool will automatically migrate your templates from the deprecated `<template>` element to the new `<ng-template>` introduced by Angular 4.

The replacement is context-aware, which means that it will consider the semantics of your code; this makes it better than simple "Search/Replace" with `sed` or other similar tools.

Under the hood the tool parses your code with the Angular Compiler, [codelyzer](https://github.com/mgechev/codelyzer) and [tslint](https://github.com/palantir/tslint). Once the code is properly analyzed, it goes through a process of migration which replaces all occurrences of `<template>` with `<ng-template>`.

# Warning

**Do not perform the migration on code which is not under version control!**

Although the tool is well tested, glitches are possible. In order to not loose information, perform the migration under version control and check the diff once done.

# How to use it?

```
$ npm i -g ngmigrate
$ ngmigrate [PATH_TO_YOUR_FILES]
```

# License

MIT

