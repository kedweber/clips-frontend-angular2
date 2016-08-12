# CLiPs Cross-Platform Mobile Angular2 Frontend

## Description

This repository is meant as a skeleton framework for a private production, CLiPs, which is designed to assist educational 
professionals in the Southeast Asian markets. While providing me with the ability of exposing the public both to the 
CLiPs project, it will also help others who want to create a multi-platform, responsive mobile/web app (Android and iOS), 
in Angular 2, while incorporating test driven development in a transpiled hard-typed JavaScript.

The database here will be a severally crippled flat JSON file version simply for the sake of example. If you have an interest in this educational 
profiling/reporting system, please do contact me via the [https://github.com/kedweber/clips-frontend-angular2/issues](issues page) 
leaving contact information and/or your PRs (Personal Requests).

### The Environment

Here are some of the tools we will be using to develop our web and mobile apps.

* Package Managers - Getting you started 
    * Node Package Manager
    * Bower
* Core Javascript Environment
    * Angular 2
    * TypeScript
* Javascript Piping
    * Gulp
* Exporting iOS and Android Apps
    * Ionic
* Test Driven Development
    * Karma
    * Jasmine
    * PhantomJS
    * Protractor
    * Angular Mocks
    
### Project File Structure

**NOTE**: This section is standard, and will likely be changed to consolidate work with Gulp.
    
    project (folder)
    |- app
    |   |- app.component.js
    |   |- app.module.js
    |   |- main.js
    |- index.html
    |- styles.css
    
## Installation



#### Installing Node Package Manager - NPM

NPM is a package manager that can assist us with the management of our backend services. Verify that you are running 
at least node v4.x.x and npm 3.x.x by running node -v and npm -v in a terminal/console window. 
Older versions produce errors with our Angular 2 on TypeScript environment.

[Update npm](https://docs.npmjs.com/cli/update) packages by issuing the following command. If the **-g** flag is specified,
this command will update globally installed packages. This will also install missing packages.
As with all commands that install packages, the **--dev** flag will cause **devDependencies** to be processed as well.

```
npm update [-g] [<pkg>...]
```

#### Initializing NPM in Local Project

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
name: (angular2) CLiPS-FrontEnd
version: (1.0.0) 0.0.1
description: The CLiPs Angular2 Front-end
entry point: (index.js) gulpfile.js
test command:
git repository: https://github.com/kedweber/clips-frontend-angular2.git
keywords: CLiPs, Angular2, Ionic, Karma, Jasmine, Unit Testing, Mobile, Multi-platform, Educational
author: kedweber
license: (ISC)

About to write to /Users/ked/projects/angular2/package.json:

{
  "name": "CLiPS-FrontEnd",
  "version": "0.0.1",
  "description": "The CLiPs Angular2 Front-end",
  "main": "gulpfile.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/kedweber/clips-frontend-angular2.git"
  },
  "keywords": [
    "CLiPs",
    "Angular2",
    "Ionic",
    "Karma",
    "Jasmine",
    "Unit",
    "Testing",
    "Mobile",
    "Multi-platform",
    "Educational"
  ],
  "author": "kedweber",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/kedweber/clips-frontend-angular2/issues"
  },
  "homepage": "https://github.com/kedweber/clips-frontend-angular2"
}

Is this ok? (yes)
```

#### Bower

Similar to NPM, Bower is another package manager, but most commonly leans more towards front-end packages.

```
MacBook-Pro:~/project user$npm install -g bower
/usr/local/bin/bower -> /usr/local/lib/node_modules/bower/bin/bower
bower@1.7.9 /usr/local/lib/node_modules/bower
```

Note the reported version **bower@1.7.9** as you will have to assure that this goes into our **devDependencies**
section of our package.json file, as shown in part below, where the **bower** key is given the value of **^1.7.9**:

```
"bugs": {
    "url": "https://github.com/kedweber/clips-frontend-angular2/issues"
  },
  "homepage": "https://github.com/kedweber/clips-frontend-angular2",
  
  // if the following section doesn't exist add the line below; otherwise, add the bower line within the section
  "devDependencies": {
    "bower": "^1.7.9"
  }
  
}
```
??? Symlink node_modules to global bower

Or if you have plenty of space, have concerns about future compatibility issues with other projects on the same system
or just simply want to keep all your bower installed modules in the local project directory; then
run the following command, which will automatically add the **devDependencies** section to your package.json file.

```
sudo npm install bower --save-dev
```

If you are placing this project into a repository, you may wish to add the line ```node_modules/``` to your **.gitignore** 
file now.

Now we need to generate our **bower.json** file. Move to your **app** directory and issue the following command:

```
~/project/app$ bower init
? name CLiPS-FrontEnd
? description The CLiPs Angular2 Front-end
? main file
? what types of modules does this package expose?
? keywords CLiPs, Angular2, Ionic, Karma, Jasmine, Unit Testing, Mobile, Multi-platform, Educational
? authors (Kedweber <ked@weberstudio.net>) 
? license MIT
? homepage http://kedweber.github.io
? set currently installed components as dependencies? Yes
? add commonly ignored files to the ignore list? Yes
? would you like to mark this package as private which prevents it from being accidentally published to the registry? No

{
    name: 'CLiPS-FrontEnd',
    keywords: [
        'CLiPs',
        'Angular2',
        'Ionic',
        'Karma',
        'Jasmine',
        'Unit',
        'Testing',
        'Mobile',
        'Multi-platform',
        'Educational'
    ]
    authors: [
        'Kedweber <ked@weberstudio.net>'
    ],
    description: 'The CLiPs Angular2 Front-end',
    main: '',
    moduleType: ,
    license: 'MIT',
    homepage: 'http://kedweber.github.io',
    ignore: [
        '**/.*',
        'node_modules',
        'bower_components',
        'test',
        'tests'
    ]
}

? Looks good? Yes

```

#### TypeScript Configuration

See the **Install Angular 2** section if you do not wish to use TypeScript, but prefer Dart or vanilla Javascript. You 
may also wish to opt for reading the manual to [install Angular 2](https://angular.io/docs/js/latest/quickstart.html) with 
all of its options.



#### Install Angular 2

The Angular crew expects you to be able to [install Angular 2](https://angular.io/docs/js/latest/quickstart.html) in 5 minutes. 
First you will have to decide which language you will use to write your Angular code. I will be using **TypeScript** here, but
you can chose between:

    Javascript
    Dart by Google
    TypeScript by Microsoft and Google

Make sure you have prepared your environment in the previous steps.

    (a) Create the project folder
    (b) Add package definition and configuration files
    
        NPM Package Configuration **package.json**
        TypeScript compiler configuration file **tsconfig.json***
        TypeScript definition files indetified by the **typings.json** file
        SystemJS's configuration file **typings.json**

    (c) Install packages
    

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

#### Ionic for Cross-Platform Mobile Development

#### Unit Testing

##### Karma

Karma is a JavaScript test runner, which we can use to generate our test reports. It can be setup to run in multiple
browsers. Karma supports multiple test frameworks, including Jasmine.

##### Jasmine

Jasmine is a JavaScript Testing Framework that doesn't depend on any other Javascript Frameworks.

##### PhantomJS

A "headless" browser, or rather a browser without a user interface in which you can run your Jasmine tests.

##### Protractor

Created by the Google Team and can run end-to-end tests over Jasmine.

##### Angular Mocks - ngMock modules

[Angular Mocks or ngMock](https://docs.angularjs.org/guide/unit-testing) is a JavaScript Library which allows for
[Angular Services](http://www.w3schools.com/angular/angular_services.asp)
to be mocked and to be injected into tests. It provides a collection of mocks for common Angular Services;
for example, the Angular **$http** Service.

```
npm install [-g] angular-mocks
```

or

```
bower install angular-mocks
```

The mocks are then available at bower_components/angular-mocks/angular-mocks.js.

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