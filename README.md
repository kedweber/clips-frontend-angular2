# CLiPs Cross-Platform Mobile Angular2 Frontend

## Description

## Installation

### The Environment

#### Installing Node Package Manager - NPM

NPM is a package manager that can assist us with the

[Update npm](https://docs.npmjs.com/cli/update) packages by issuing the following command. If the **-g** flag is specified,
this command will update globally installed packages. This will also install missing packages.
As with all commands that install packages, the **--dev** flag will cause **devDependencies** to be processed as well.

```
npm update [-g] [<pkg>...]
```

#### Installing Gulp and Gulp Related Packages Globally

Gulp is a ...

It will need to be installed both globally, and locally within the project folder. You can determine if Gulp is already
installed by issuing the command below. If installed, you will see the version currently installed.

```
~/project$ gulp -v
[11:37:11] CLI version 3.9.1
```

If it is not installed, you can simply do so using NPM to install it globally. You may have to prefix the following
command as the super user; using ```sudo```.

```
npm install -g gulp
```

#### Initializing Gulp in Local Project

Issuing the ```npm init``` command within the project's root folder will render a walk-through where you will be
prompted through the creation of the package.json file. Note that for the **main** variable, the default value is
**index.js**. It is more common to distinguish this file name as **gulpfile.js**, but of course you may name it whatever
you desire.

```
~/project$ npm init

This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sane defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg> --save` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
name: (angular2) CLiPS FrontEnd
version: (1.0.0) 0.0.1
description: The CLiPs Angular2 Front-end
entry point: (index.js) gulpfile.js
test command:
git repository:
```

#### Ionic for Cross-Platform Mobile Development

#### Unit Testing

## Change Log

[See CHANGELOG.md](CHANGELOG.md)

## Permissions and Disclaimer

This License has been voluntarily deprecated by its author, henceforth referred to as "creator" and/or any "contributors".
Copyright (c) 2016, KedWeber under a Creative Commons licence.

Permission to use, copy, modify and distribute this software and its documentation for any purpose and without
fee is hereby granted, provided that the above copyright notice appear in all  copies,
and hitherto both the copyright notice and this permission notice appear in supporting
documentation, and that the named creator or related contributors are not be used in advertising
or publicity pertaining to distribution of the software without specific, written prior permission.
Said creator and any of the contributors make no representation about the suitability of this software for any purpose.
It is provided "as is" without express or implied warranty.

SAID "creator" AND CONTRIBUTORS DISCLAIM ALL WARRANTIES WITH REGARD TO THIS SOFTWARE, INCLUDING ALL IMPLIED WARRANTIES
OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL said "creator" AND THE CONTRIBUTORS BE LIABLE FOR ANY SPECIAL,
INDIRECT OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS,
WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION
WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.