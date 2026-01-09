TinyMCE - JavaScript Library for Rich Text Editing
===================================================

Building TinyMCE for Nexus
------------------------
The releasing of a new version of TinyMCE for Nexus must happen on a dev local machine. There's no pipeline that does
this, because it didn't make sense to have a pipeline for this one-off task.

To release a new version, first follow the steps in "Building TinyMCE" section below to build TinyMCE on your local
machine. Then perform the following steps to prepare the release:

1. Update the version number in `package.json` to the new version.
2. Update changelog.txt with the changes made since last release.
3. Commit the changes to git.
4. Create a git tag for the new version.
5. Run `npm publish` command.

Building TinyMCE
-----------------
Install [Node.js](https://nodejs.org/en/) on your system.
Clone this repository on your system
```
$ git clone https://github.com/tinymce/tinymce.git
```
Open a console and go to the project directory.
```
$ cd tinymce/
```
Install `grunt` command line tool globally.
```
$ npm i -g grunt-cli
```
Install all package dependencies.
```
$ npm install
```
Now, build TinyMCE by using `grunt`.
```
$ grunt
```
Bundle themes and plugins into a single file TinyMCE by using `grunt`.
```
$ grunt
```


Build tasks
------------
`grunt`
Lints, compiles, minifies and creates release packages for TinyMCE. This will produce the production ready packages.

`grunt start`
Starts a webpack-dev-server that compiles the core, themes, plugins and all demos. Go to `localhost:3000` for a list of links to all the demo pages.

`grunt dev`
Runs tsc, webpack and less. This will only produce the bare essentials for a development build and is a lot faster.

`grunt test`
Runs all tests on PhantomJS.

`grunt bedrock-manual`
Runs all tests manually in a browser.

`grunt bedrock-auto:<browser>`
Runs all tests through selenium browsers supported are chrome, firefox, ie, MicrosoftEdge, chrome-headless and phantomjs.

`grunt webpack:core`
Builds the demo js files for the core part of tinymce this is required to get the core demos working.

`grunt webpack:plugins`
Builds the demo js files for the plugins part of tinymce this is required to get the plugins demos working.

`grunt webpack:themes`
Builds the demo js files for the themes part of tinymce this is required to get the themes demos working.

`grunt webpack:<name>-plugin`
Builds the demo js files for the specific plugin.

`grunt webpack:<name>-theme`
Builds the demo js files for the specific theme.

`grunt --help`
Displays the various build tasks.

Bundle themes and plugins into a single file
---------------------------------------------
`grunt bundle --themes=modern --plugins=table,paste`

Minifies the core, adds the modern theme and adds the table and paste plugin into tinymce.min.js.
