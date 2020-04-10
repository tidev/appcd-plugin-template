# <%= packageName %>

## Getting Started

You must have Yarn 1.x installed. Please refer to the Yarn docs for installation
instructions for your machine: https://classic.yarnpkg.com/en/docs/install.

## Building the plugin

The plugin project comes with a gulp script containing build task that will lint the code, then
transpile the code using Babel.

```sh
yarn run build
```

## Link the Plugin

In order for the Appc Daemon to find your plugin, you need to wire up some links.

```sh
yarn link
appcd pm link
```

The `yarn link` command will create a symlink to your plugin so that it can be referenced by other
projects. The `appcd pm link` will scan the Yarn links for Appc Daemon plugins, then symlink those
to the appcd home plugins directory which is where the Appc Daemon will find your plugin.

## Ensure the Appc Daemon is running

```sh
appcd start
```

## Test your plugin

```sh
appcd exec /<%= serviceName %>/latest
```

## Develop your plugin

To speed up development, start the watch script:

```sh
yarn run watch
```

## View debug logs

```sh
appcd logcat *<%= serviceName %>*
```

## Documentation

Please refer to the Appc Daemon's [Plugin System][plugin_system] docs for information about plugin
types, lifecycle, `package.json` settings, `appcd-*` dependencies, and debugging.

[plugin_system]: https://github.com/appcelerator/appc-daemon/blob/master/docs/Components/Plugin-System.md
