
> [!IMPORTANT]
> You are looking at an old version (<2.14.0) of the NSW Design System. [There is a newer version of the NSW Design System](https://github.com/digitalnsw/nsw-design-system)

# NSW Design System V2.14.0 Archive

> [!NOTE]
> This repository has been archived by the NSW Design System team on Aug 23, 2023, and is now in a read-only state. While no further updates or contributions will be accepted, the existing content remains available for reference.
>
> If you are maintaining a legacy version take a look at the components and guidance offered by the [NSW Design System V2 documentation site](https://nswdesignsystem.surge.sh).
> 
> Feel free to explore the repository to access historical information and resources. While it won't receive any new updates, you can still review the codebase and discussions that took place in the past.
> 
> If you have questions related to the repository's content or its context, please consult the available documentation or use the issue tracker for assistance. This repository's content can serve as a resource for learning and inspiration for future projects. Thank you for your interest in this repository, and we hope it continues to be a useful resource for the development community.


## Using the NSW Design System V2

How you use the NSW Design System V2 depends on your team's capabilities. We recommend using `npm` but also provided in a CDN, and a downloadable starter kit which includes all the compiled assets.

 1. [Installing with NPM](#installing-with-npm)
 3. [Adding the font and icons](#adding-the-font-and-the-icons)
 4. [Importing javascript into your project](#importing-javascript-into-your-project)
 5. [Using JSDelivr CDN](#using-jsdelivr-cdn)
 
### Installing with NPM
1.  Install  `Node/npm`. 
    
    -   More information can be found via the nodejs [Installation guides](https://nodejs.org/en/download/)
    
2.  Generate a `package.json` file using the `npm init` command in the terminal. You will be prompted to enter several pieces of information, like the name of your application, version, description etc.
    
4.  Add  `nsw-design-system`  to your project’s  `package.json`:
    - `npm install --save nsw-design-system@2`

The NSW Design System is now installed as a dependancy of your project, check out how to [import styles](#importing-styles-into-your-project) and [javascript](#importing-javascript-into-your-project) in to your project build.

### Option 1: Importing all styles
The NSW Design System styles need to be added to the main Sass file in your project.  
Use the below snippet to import the NSW Design System (ideally placed before any other imports or sass):
```
@import 'node_modules/nsw-design-system/src/main';
```

### Option 2: Import core and certain components
The core library includes the design system's base theme, typography, mixins and helper functions. You can import this and take advantage of our variables and helpers.

In your own main Sass file, you can import NSW Design System’s core library.

```
// Core libraries
@import 'node_modules/nsw-design-system/src/global/scss/settings/settings';
@import 'node_modules/nsw-design-system/src/global/scss/tools/all';
@import 'node_modules/nsw-design-system/src/global/scss/helpers/all';
@import 'node_modules/nsw-design-system/src/global/scss/style/all';
@import 'node_modules/nsw-design-system/src/styles/section/section';
@import 'node_modules/nsw-design-system/src/styles/spacing/spacing';
@import 'node_modules/nsw-design-system/src/styles/typography/typography';

```

You can choose to import components as you need it. In the same file, import the Sass files of each component

```
// Components
@import 'node_modules/nsw-design-system/src/components/accordion/accordion';
@import 'node_modules/nsw-design-system/src/components/card/card';
@import 'node_modules/nsw-design-system/src/components/notification/notification';
```

With this setup you can also start theming with a few sets of variable changes.

#### Adding the font and the icons
In your main html document add this line of code inside the `<head>` tag. Make sure that it's placed before the NSW Design System styles import.
```
  <link href="https://fonts.googleapis.com/css?family=Montserrat:400,600&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```
Another way is to import it in css:
```
@import url('https://fonts.googleapis.com/css?family=Montserrat:400,600&display=swap');
@import url('https://fonts.googleapis.com/icon?family=Material+Icons');
```
### Importing javascript into your project
Some NSW Design System components require javascript to provide advanced functionality. To ensure the page is ready for javascript to run, include the follow scripts tags at the end of the html document.
```
    <script src="path/to/main.js"></script>
    <script>window.NSW.initSite()</script>
  </body>
</html>
```
Depending on your project set up, you might wish to copy the file into your project from `node_modules` or add the reference to your build workflow.


### Using JSDelivr CDN
The bundled css and js files are also hosted in [JSDelivr](https://www.jsdelivr.com).

You can add the files to your main html document
```
<html>
  <head>
    ...
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/nsw-design-system@2/dist/css/main.css">
  </head>
  <body>
    ...
    <script src="https://cdn.jsdelivr.net/npm/nsw-design-system@2/dist/js/main.min.js"></script>
    <script>window.NSW.initSite()</script>
  </body>
</html>
```
