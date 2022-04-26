React Native Pushwoosh Push Notifications module
===================================================

[![GitHub release](https://img.shields.io/github/release/Pushwoosh/pushwoosh-react-native-plugin.svg?style=flat-square)](https://github.com/Pushwoosh/pushwoosh-react-native-plugin/releases) 
[![npm](https://img.shields.io/npm/v/pushwoosh-react-native-plugin.svg)](https://www.npmjs.com/package/pushwoosh-react-native-plugin)
[![license](https://img.shields.io/npm/l/pushwoosh-react-native-plugin.svg)](https://www.npmjs.com/package/pushwoosh-react-native-plugin)

![platforms](https://img.shields.io/badge/platforms-Android%20%7C%20iOS-yellowgreen.svg)

| [Guide](https://www.pushwoosh.com/platform-docs/pushwoosh-sdk/cross-platform-frameworks/react-native/integrating-react-native-plugin) | [Documentation](docs/README.md) | [Sample](https://github.com/Pushwoosh/pushwoosh-react-native-sample) |
| ----------------------------------------------------------- | ------------------------------- | -------------------------------------------------------------------- |


### Installation
```
npm install pushwoosh-react-native-plugin --save
react-native link pushwoosh-react-native-plugin
```

For Android platform, also add the following lines to your project's build.gradle:

```
//you should already have buildscript and dependencies blocks in your project's build.gradle so just put the classpath line there
buildscript {
 dependencies {
 classpath 'com.google.gms:google-services:4.3.3'
 }
}

//add these lines to the very end of your build.gradle
apply {
 plugin com.google.gms.googleservices.GoogleServicesPlugin
}
```

### Usage

```js
import Pushwoosh from 'pushwoosh-react-native-plugin';

Pushwoosh.init({ 
    "pw_appid" : "YOUR_PUSHWOOSH_PROJECT_ID" , 
    "project_number" : "YOUR_GCM_PROJECT_NUMBER" 
});
Pushwoosh.register();
```

In order to use custom notification handling on iOS specify the parameter "pw_notification_handling" to "CUSTOM" when initializing the plugin(If no value specified Pushwoosh notification handler is used):

```js
import Pushwoosh from 'pushwoosh-react-native-plugin';

Pushwoosh.init({ 
    "pw_appid" : "YOUR_PUSHWOOSH_PROJECT_ID" , 
    "project_number" : "YOUR_GCM_PROJECT_NUMBER",
    "pw_notification_handling" : "CUSTOM"
});
Pushwoosh.register();
```

In order to use reverse proxy to connect to pushwoosh servers specify the parameter "reverse_proxy_url" with the url to your reverse proxy when initializing the plugin:

```js
import Pushwoosh from 'pushwoosh-react-native-plugin';

Pushwoosh.init({ 
    "pw_appid" : "YOUR_PUSHWOOSH_PROJECT_ID" , 
    "project_number" : "YOUR_GCM_PROJECT_NUMBER",
    "reverse_proxy_url" : "URL_TO_YOUR_REVERSE_PROXY"
});
Pushwoosh.register();
```
