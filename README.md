# api documentation for  [gulp-bower-files (v0.2.7)](https://github.com/ck86/gulp-bower-files)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-bower-files.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-bower-files) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-bower-files.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-bower-files)
#### Build gulp.src() of your bower packages main files.

[![NPM](https://nodei.co/npm/gulp-bower-files.png?downloads=true)](https://www.npmjs.com/package/gulp-bower-files)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-bower-files/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-bower-files_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-bower-files/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-bower-files/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-bower-files/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Christopher Knötschke",
        "email": "cknoetschke@gmail.com"
    },
    "bugs": {
        "url": "https://github.com/ck86/gulp-bower-files/issues"
    },
    "dependencies": {
        "gulp-util": "^2.2.14"
    },
    "description": "Build gulp.src() of your bower packages main files.",
    "devDependencies": {
        "event-stream": "^3.1.0",
        "gulp": "^3.5.6",
        "mocha": "^1.18.2",
        "should": "^3.2.0-beta1"
    },
    "directories": {},
    "dist": {
        "shasum": "3208513ca63a7dc21789d316dcdda9f1fe749414",
        "tarball": "https://registry.npmjs.org/gulp-bower-files/-/gulp-bower-files-0.2.7.tgz"
    },
    "homepage": "https://github.com/ck86/gulp-bower-files",
    "keywords": [
        "gulpplugin",
        "bower"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "cknoetschke",
            "email": "cknoetschke@gmail.com"
        }
    ],
    "name": "gulp-bower-files",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/ck86/gulp-bower-files.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "0.2.7"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-bower-files](#apidoc.module.gulp-bower-files)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.</span>package (opts, collection)](#apidoc.element.gulp-bower-files.package)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.</span>package_collection (opts)](#apidoc.element.gulp-bower-files.package_collection)
1.  object <span class="apidocSignatureSpan">gulp-bower-files.</span>package.prototype
1.  object <span class="apidocSignatureSpan">gulp-bower-files.</span>package_collection.prototype

#### [module gulp-bower-files.package](#apidoc.module.gulp-bower-files.package)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.</span>package (opts, collection)](#apidoc.element.gulp-bower-files.package.package)

#### [module gulp-bower-files.package.prototype](#apidoc.module.gulp-bower-files.package.prototype)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.package.prototype.</span>addDependencies ()](#apidoc.element.gulp-bower-files.package.prototype.addDependencies)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.package.prototype.</span>collectData ()](#apidoc.element.gulp-bower-files.package.prototype.collectData)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.package.prototype.</span>getFiles (force)](#apidoc.element.gulp-bower-files.package.prototype.getFiles)

#### [module gulp-bower-files.package_collection](#apidoc.module.gulp-bower-files.package_collection)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.</span>package_collection (opts)](#apidoc.element.gulp-bower-files.package_collection.package_collection)

#### [module gulp-bower-files.package_collection.prototype](#apidoc.module.gulp-bower-files.package_collection.prototype)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>add (name, path)](#apidoc.element.gulp-bower-files.package_collection.prototype.add)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>collectPackages ()](#apidoc.element.gulp-bower-files.package_collection.prototype.collectPackages)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>getFiles ()](#apidoc.element.gulp-bower-files.package_collection.prototype.getFiles)
1.  [function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>process ()](#apidoc.element.gulp-bower-files.package_collection.prototype.process)



# <a name="apidoc.module.gulp-bower-files"></a>[module gulp-bower-files](#apidoc.module.gulp-bower-files)

#### <a name="apidoc.element.gulp-bower-files.package"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.</span>package (opts, collection)](#apidoc.element.gulp-bower-files.package)
- description and source-code
```javascript
package = function (opts, collection) {
    this.collection        = collection;
    this.name           = opts.name || null;
    this.path           = opts.path || null;
    this.main           = opts.main || null;
    this.dependencies   = opts.dependencies;
    this.ignore         = opts.ignore || false;
    this.debugging      = collection.debugging || false;

    if(this.ignore) return;

    this.collectData();
    this.addDependencies();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-bower-files.package_collection"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.</span>package_collection (opts)](#apidoc.element.gulp-bower-files.package_collection)
- description and source-code
```javascript
package_collection = function (opts) {
    this.opts               = opts;
    this.opts.main          = opts.main || null;
    this.opts.env           = opts.env || process.env.NODE_ENV;
    this.debugging          = opts.debugging || false;
    this.overrides          = {};
    this._queue             = [];
    this._lastQueueLength   = 0;
    this._packages          = {};
    this._processed         = {};
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.gulp-bower-files.package"></a>[module gulp-bower-files.package](#apidoc.module.gulp-bower-files.package)

#### <a name="apidoc.element.gulp-bower-files.package.package"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.</span>package (opts, collection)](#apidoc.element.gulp-bower-files.package.package)
- description and source-code
```javascript
package = function (opts, collection) {
    this.collection        = collection;
    this.name           = opts.name || null;
    this.path           = opts.path || null;
    this.main           = opts.main || null;
    this.dependencies   = opts.dependencies;
    this.ignore         = opts.ignore || false;
    this.debugging      = collection.debugging || false;

    if(this.ignore) return;

    this.collectData();
    this.addDependencies();
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.gulp-bower-files.package.prototype"></a>[module gulp-bower-files.package.prototype](#apidoc.module.gulp-bower-files.package.prototype)

#### <a name="apidoc.element.gulp-bower-files.package.prototype.addDependencies"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.package.prototype.</span>addDependencies ()](#apidoc.element.gulp-bower-files.package.prototype.addDependencies)
- description and source-code
```javascript
addDependencies = function () {
    for(var name in this.dependencies) {
        this.collection.add(name, path.join(this.path, "..", name));
    }
}
```
- example usage
```shell
...
this.dependencies   = opts.dependencies;
this.ignore         = opts.ignore || false;
this.debugging      = collection.debugging || false;

if(this.ignore) return;

this.collectData();
this.addDependencies();
}

Package.prototype = {
/**
 * Collects data from first found config file
 */
collectData: function() {
...
```

#### <a name="apidoc.element.gulp-bower-files.package.prototype.collectData"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.package.prototype.</span>collectData ()](#apidoc.element.gulp-bower-files.package.prototype.collectData)
- description and source-code
```javascript
collectData = function () {
    var paths = [
        path.join(this.path, "bower.json"),
        path.join(this.path, "package.json"),
        path.join(this.path, "component.json"),
        path.join(this.path, ".bower.json")
    ];

    var data = paths.reduce(function(prev, curr) {
        if(prev !== null) return prev;

        if(!fs.existsSync(curr)) return prev;

        try {
            return JSON.parse(fs.readFileSync(curr, "utf8"));;
        } catch(e) {
            return null;
        }
    }, null);

    if(data === null)
        return;

    if(!this.main && data.main)
        this.main = data.main;

    if(this.dependencies === undefined && data.dependencies && data.dependencies)
        this.dependencies = data.dependencies;
}
```
- example usage
```shell
...
this.main           = opts.main || null;
this.dependencies   = opts.dependencies;
this.ignore         = opts.ignore || false;
this.debugging      = collection.debugging || false;

if(this.ignore) return;

this.collectData();
this.addDependencies();
}

Package.prototype = {
/**
 * Collects data from first found config file
 */
...
```

#### <a name="apidoc.element.gulp-bower-files.package.prototype.getFiles"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.package.prototype.</span>getFiles (force)](#apidoc.element.gulp-bower-files.package.prototype.getFiles)
- description and source-code
```javascript
getFiles = function (force) {
    if(this.ignore) return [];
    if(this.main === null && (this.main = this.collection.opts.main) === null) return [];

    var main = this.main;
    var files = [];

    if(typeof main === "object" && !Array.isArray(main)) {
        if(!(main = main[this.collection.opts.env])) return [];
    }

    main = Array.isArray(main) ? main : [main];

    if(force !== true) {
        for(var name in this.dependencies) {
            if(this.collection._processed[name] !== true) {
                return false;
            }
        }
    }

    main.forEach(function(file) {
        files.push(path.join(this.path, file));
    }.bind(this));

    if(this.debugging) {
        files.forEach(function(file) {
            logger("Package\t\t", "select file\t", this.name, file);
        }.bind(this));
    }

    if(this.collection.opts.checkExistence === true) {
        files.forEach(function(file) {
            if(!fs.existsSync(file)) {
                throw new Error("File on path '" + file + "' does not exist.");
            }
        });
    }

    return files;
}
```
- example usage
```shell
...

if(!opts.includeDev)
    opts.includeDev = false;

try {
    var collection = new PackageCollection(opts);
    collection.collectPackages();
    var files = collection.getFiles();
} catch(e) {
    throw e;
    throw new PluginError(PLUGIN_NAME, e.message);
}

if(!files || !files.length) {
    // @TODO: find a better way to return a stream without files
...
```



# <a name="apidoc.module.gulp-bower-files.package_collection"></a>[module gulp-bower-files.package_collection](#apidoc.module.gulp-bower-files.package_collection)

#### <a name="apidoc.element.gulp-bower-files.package_collection.package_collection"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.</span>package_collection (opts)](#apidoc.element.gulp-bower-files.package_collection.package_collection)
- description and source-code
```javascript
package_collection = function (opts) {
    this.opts               = opts;
    this.opts.main          = opts.main || null;
    this.opts.env           = opts.env || process.env.NODE_ENV;
    this.debugging          = opts.debugging || false;
    this.overrides          = {};
    this._queue             = [];
    this._lastQueueLength   = 0;
    this._packages          = {};
    this._processed         = {};
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.gulp-bower-files.package_collection.prototype"></a>[module gulp-bower-files.package_collection.prototype](#apidoc.module.gulp-bower-files.package_collection.prototype)

#### <a name="apidoc.element.gulp-bower-files.package_collection.prototype.add"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>add (name, path)](#apidoc.element.gulp-bower-files.package_collection.prototype.add)
- description and source-code
```javascript
add = function (name, path) {
    if(typeof this._packages[name] !== "undefined")
        return;

    if(this.debugging) {
        logger("PackageCollection", "add\t\t", name, path);
    }

    this._packages[name] = true;

    var opts = this.overrides[name] || {}
    opts.name = name;
    opts.path = path;

    this._packages[name] = new Package(opts, this);
}
```
- example usage
```shell
...
},

/**
 * Adds package dependencies to the collection
 */
addDependencies: function() {
    for(var name in this.dependencies) {
        this.collection.add(name, path.join(this.path, "..", name));
    }
},

/**
 * Gets main files of the package
 *
 * @param  {Boolean}    force  If true it will not wait for the dependencies
...
```

#### <a name="apidoc.element.gulp-bower-files.package_collection.prototype.collectPackages"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>collectPackages ()](#apidoc.element.gulp-bower-files.package_collection.prototype.collectPackages)
- description and source-code
```javascript
collectPackages = function () {
    if(!fs.existsSync(this.opts.paths.bowerJson))
        throw new Error("bower.json does not exist at: " + this.opts.paths.bowerJson);

    var bowerJson = JSON.parse(fs.readFileSync(this.opts.paths.bowerJson, "utf8"));
    var dependencies = bowerJson.dependencies || {};

    this.overrides = bowerJson.overrides || {};

    if(this.opts.includeDev === true && bowerJson.devDependencies) {
        for(var name in bowerJson.devDependencies) {
            dependencies[name] = bowerJson.devDependencies[name];
        }
    }

    for(var name in dependencies) {
        this.add(name, path.join(this.opts.paths.bowerDirectory, "/", name));
    }
}
```
- example usage
```shell
...
    opts.base = opts.paths.bowerDirectory;

if(!opts.includeDev)
    opts.includeDev = false;

try {
    var collection = new PackageCollection(opts);
    collection.collectPackages();
    var files = collection.getFiles();
} catch(e) {
    throw e;
    throw new PluginError(PLUGIN_NAME, e.message);
}

if(!files || !files.length) {
...
```

#### <a name="apidoc.element.gulp-bower-files.package_collection.prototype.getFiles"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>getFiles ()](#apidoc.element.gulp-bower-files.package_collection.prototype.getFiles)
- description and source-code
```javascript
getFiles = function () {
    for(var name in this._packages) {
        this._queue.push(this._packages[name]);
    }

    return this.process();
}
```
- example usage
```shell
...

if(!opts.includeDev)
    opts.includeDev = false;

try {
    var collection = new PackageCollection(opts);
    collection.collectPackages();
    var files = collection.getFiles();
} catch(e) {
    throw e;
    throw new PluginError(PLUGIN_NAME, e.message);
}

if(!files || !files.length) {
    // @TODO: find a better way to return a stream without files
...
```

#### <a name="apidoc.element.gulp-bower-files.package_collection.prototype.process"></a>[function <span class="apidocSignatureSpan">gulp-bower-files.package_collection.prototype.</span>process ()](#apidoc.element.gulp-bower-files.package_collection.prototype.process)
- description and source-code
```javascript
process = function () {
    var queue = this._queue;
    var srcs = [];
    var force = false;

    if(this._lastQueueLength === queue.length) {
        force = true;
    }

    this._lastQueueLength = queue.length;

    this._queue = [];

    queue.forEach(function(package) {
        var packageSrcs = package.getFiles(force);

        if(packageSrcs === false) {
            return this._queue.push(package);
        }

        srcs.push.apply(srcs, packageSrcs);
        this._processed[package.name] = true;
    }.bind(this));

    if(this._queue.length) {
        srcs.push.apply(srcs, this.process());
    }

    return srcs;
}
```
- example usage
```shell
...
 * @return {Array}
 */
getFiles: function() {
    for(var name in this._packages) {
        this._queue.push(this._packages[name]);
    }

    return this.process();
},

/**
 * processes the queue and returns the srcs of all packages
 *
 * @private
 * @return {Array}
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
