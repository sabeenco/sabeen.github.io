---
layout: post
categories: development
---
This cheat sheet saves me from learning by heart commands for all the different tools and task runners used in web development.

## Npm

Install Node.js
```shell
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
```

Node comes with npm installed so you should have a version of npm. However, npm gets updated more frequently than Node does, so you'll want to make sure it's the latest version.
```shell
sudo npm install npm@latest -g
```

Check for package versions
```shell
npm outdated
```

Update packages
```shell
npm update
```

Update package globally
```shell
npm update <package-name> -g
```

Install package
```shell
npm install --save / --save-dev
```

Uninstall package
```shell
npm uninstall --save / --save-dev
```

Install only production dependencies (ignore devDependencies)
```shell
NODE_ENV=production npm install
```

Package use semantic versioning: 1.0.1 major minor patch
`~1.0.0` install only patch updates
`^1.0.0` install only minor updates

Zip Folder
```shell
zip -r zipname.zip foldertozip/
```

Example of `package.json` file with Less
```json
{
  "name": "helpdesk",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "lint": "jshint src/js/*.js",
    "uglify": "uglifyjs src/vendor/uikit/js/uikit.js src/js/* -m -c -o assets/js/main.js",
    "concat": "uglifyjs src/vendor/uikit/js/uikit.js src/js/* -b -o assets/js/main.js",
    "css": "lessc src/less/main.less > assets/css/main.css",
    "css:min": "lessc src/less/main.less > assets/css/main.css --clean-css",
    "watch": "watch 'npm run dev' src/js/ src/less/",
    "dev": "npm run lint && npm run concat && npm run css",
    "build": "npm run lint && npm run uglify && npm run css:min",
    "postinstall": "bower install && npm run concat && npm run css"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/chromjak/helpdesk.git"
  },
  "author": "",
  "license": "MIT",
  "bugs": {
    "url": "https://github.com/chromjak/helpdesk/issues"
  },
  "homepage": "https://github.com/chromjak/helpdesk#readme",
  "devDependencies": {
    "bower": "latest",
    "jshint": "latest",
    "less": "latest",
    "less-plugin-clean-css": "latest",
    "uglify-js": "latest",
    "watch": "latest"
  }
}
```

Example of `package.json` file with Sass
```json
{
  "name": "helpdesk",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "lint": "jshint src/js/*.js",
    "uglify": "uglifyjs node_modules/bootstrap/dist/js/bootstrap.js src/js/* -m -c -o assets/js/main.js",
    "concat": "uglifyjs node_modules/bootstrap/dist/js/bootstrap.js src/js/* -b -o assets/js/main.js",
    "scss": "node-sass -o assets/css src/scss",
    "scss:min": "node-sass --output-style compressed -o assets/css src/scss",
    "watch": "watch 'npm run dev' src/js/ src/scss/",
    "dev": "npm run lint && npm run concat && npm run scss",
    "build": "npm run lint && npm run uglify && npm run scss:min",
    "postinstall": "npm run concat && npm run scss"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/chromjak/helpdesk.git"
  },
  "author": "",
  "devDependencies": {
    "jshint": "latest",
    "node-sass": "latest",
    "uglify-js": "latest",
    "watch": "latest"
  }
}
```

## Git

```shell
git init
git add README.md
git commit -m "first commit"
git remote add origin <repository URL>
git push -u origin master
```

Cache GitHub credentials
```shell
git config --global credential.helper "cache --timeout=3600"
```
Configure local git user
```shell
git config --list
git config --global user.name "Ivan Chromjak"
git config --global user.email ivan@company.com
git remote set-url origin https://github.com/username/repository.git
```

Tags/Releases
```shell
git tag <tagname> (v1.2.3)
git push --tags
```

## Grunt

Install Grunt Globally
```shell
sudo npm install -g grunt-cli
```

## Gulp

Install Gulp Globally
```shell
sudo npm install gulp-cli -g
```

## Bower

Change package directory
```shell
.bowerrc file
{
  "directory": "src/vendor"
}
```

## Jekyll

```shell
jekyll new <folder_name>

gem install bundler

bundle install

jekyll s
```
