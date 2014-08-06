Pixelated User Agent
====================

This contains the Pixelated User Agent, which is composed of a web UI written as a JavaScript single page app, and a service that provides a REST-ful interface that the UI can use for all User Agent actions. For now, all of these actions are mail-related but this might evolve later. The default service is written to talk to a Pixelated or LEAP provider.

# Running it
The User Agent is composed of 2 components:
- The Web Ui, which is the the HTML, CSS and JS files served to the browser; and
- The Service component, which is the web service that serves the Web Ui to the browser, provides the REST API which the the Web Ui uses, and integrates with the LEAP or Pixelated provider.

## Web Ui
The Web Ui needs to generate the templates and CSS to be served. For that, you need (from inside `./web-ui`) to run the command `./go build` at least once after downloading the code. From here on, you can run `./go watch` to auto-generate the resources as they are changed.

## Service

## Fake Service
This is a Fake Service used for testing the Web Ui. It works as the real service, but mocking the connection to the LEAP/Pixelated provider with a predefined dataset of emails.

To run the Fake Service, run the command `./go server:start` on the terminal. `./go server:restart` restarts the service.

# Setting things up
Before being able to run the Service (the Fake or real), you must first set this components up by installing their dependencies.

## Web Ui
From inside `./web-ui`:
```
$ bundle install
$ npm install
$ bower install
```
If you don't have `bower` installed globaly, change the third line to `$ ./node_modules/bower/bin/bower install`

## Service

## Fake Service
From inside `./fake-service`
```
$ bundle install
```
And that's it.
