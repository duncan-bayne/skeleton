# skeleton

A skeleton app for creating new micro-services.

## status

*Do not use this skeleton app for production work*. It should be considered proof-of-concept only.

## getting started

1. download the [archive of the skeleton app](https://www.github.com/duncan-bayne/skeleton/archive/master.zip)

1. unpack it and change into the directory

			unzip skeleton-master.zip
			cd skeleton-master

1. install the dependencies

			bundle install

1. optional: on OSX, install [Growl](http://growl.info/downloads) to get visual feedback from Guard

1. start Guard; this starts the server, and when files change, restarts the server and runs all the specs

			bundle exec guard

1. now that the server is running, check out [the specs](http://localhost:9292/specs) and [addition](http://localhost:9292/add/3/2)

## conventions

For proper integration with [avant-garde-ci](http://www.github.com/duncan-bayne/avant-garde-ci) it is important to follow certain conventions when developing your service.

### rake tasks

#### spec
Runs specs.  These should be quick-running and non-destructive, as they will be run on deployed instances of this service.

#### quality
Runs any static analysis tools you like.  By default this runs Roodi, but there's no hard and fast rules here, and the task doesn't have to pass for CI.

#### build
Performs any necessary pre-deployment steps.  E.g. if your service needs to perform asset precompilation, you should do so as part of the build task.

## FAQ / Troubleshooting / Bugs

### why does Growl show an error icon when the server is restarted successfully?
Because of [this bug](https://github.com/rchampourlier/guard-shotgun/issues/3).

### what development OSs are supported?
The skeleton app works out of the box on OSX and Linux.  It should work on Windows, but hasn't been tested and raised issues will likely languish.

### the JSON returned by /specs is hard to read
Try a JSON plugin for your browser:

* [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc/) for Chrome
* [JSONView](https://addons.mozilla.org/en-us/firefox/addon/jsonview/) for Firefox
* [safari-json-formatter](https://github.com/rfletcher/safari-json-formatter) for Safari

## licence

skeleton is licensed under the GNU Lesser General Public License.

### why the LGPL?

The GPL is specifically designed to reduce the usefulness of GPL-licensed code to closed-source, proprietary software. The BSD license (and similar) don't mandate code-sharing if the BSD-licensed code is modified by licensees. The LGPL achieves the best of both worlds: an LGPL-licensed library can be incorporated within closed-source proprietary code, and yet those using an LGPL-licensed library are required to release source code to that library if they change it.
