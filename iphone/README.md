# HockeyApp Module

## Description

HockeyApp SDK module for Titanium. Currently only unauthenticated support is available, including crash reports.

The module is licensed under the MIT license.

## Referencing the module in your Titanium Mobile application ##

Simply add the following lines to your `tiapp.xml` file:

```xml
    <modules>
        <module platform="iphone">nl.rebelic.hockeyapp</module>
        <module platform="android">nl.rebelic.hockeyapp</module>
    </modules>
```

## Example

Put the following code in your app.js (or alloy.js if you are using Alloy) to enable the module.

```javascript
	var hockeyapp = require('nl.rebelic.hockeyapp');
	hockeyapp.start('<yourappid>');
```
To show the modal feedback compose window on iOS:

```javascript
    hockeyapp.showFeedbackComposeView();
```
To show the modal feedback list view on iOS:

```javascript
    hockeyapp.showFeedbackListView();
```


## Getting UIApplicationMain exceptions

* Copy the Titanium build plugin named `hockeyapp` from the `plugin` directory to your Ti project directory under the
`plugins` folder.
* Add the following to `tiapp.xml`

```xml
    <plugins>
        <plugin>hockeyapp</plugin>
    </plugins>
```

This will modify the `main.m` file generated by Titanium in order to catch NSExceptions involving UIApplicationMain.
The exception description is persisted in NSUserDefaults and used by the hockeyapp module for sending additional info
on the actual cause of the crash.

