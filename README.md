# rn-skeleton
I had some trouble finding example for integrating keys frameworks all together, but never example how everything would work together. There are probably other ways feel free to leave comments or suggestions.

React native skeleton project for
* React Native
* React-Redux
* Redux-Persist
* React Navigation
* Redux-Saga

![Overview](./documentation/ScreenShot.png)


# Step by step installation guide

I'll try to show all the commands you need to run to create your own project if you don't want to clone this one.

[Building Projects with Native Code](https://facebook.github.io/react-native/docs/getting-started.html)


## Shell tools
```Bash
npm install -g create-react-native-app
npm install -g react-native-cli
npm install -g react-native-git-upgrade
```

## Init

```Bash
react-native init RNskeleton
git init
git add .
git commit -m "initial"
npm install
```

## Dependencies

### React Component
```Bash
npm install --save prop-types
```

### Redux,Persist,Saga
```Bash
npm install --save react-redux redux redux-logger
npm install --save redux-persist
npm install --save redux-saga
```

### Navigation
```Bash
npm install --save react-navigation
```

### Icons and Native Elements
```Bash
npm install --save react-native-elements
npm install --save react-native-vector-icons
react-native link
```

### Fonts
```Bash
react-native link
```

## Runing Simulators
### iOS
```
react-native run-ios
```
### Android
```
react-native run-android
```
Show RN options
```
adb shell input keyevent 82
```
Reload RN
```
adb shell input text "RR"
```

# Architecture

From the application creation there are few choice to be made, I'll try to explains my decisions or sometime just use the defacto.

## Expo or Native Code
Right from the start you have to make one big decision, should I use Expo or go Native Code. The key to architecture is sometime delay the decision until it is important. Commiting to Expo right now seems to be a big steps and I want to decide which components to include along the way. I also want to be able to use my own native component, I could always eject with Expo but would be left with a big dependencies. Since this is a learning journey, I decided to go the native code way.



# Tutorial

React Native doesn't allow you to have anything other then alphanum chararcters in your project name, I name my repo rn-skeleton so I opt for RNskeleton and change the directory name when creating the project [Init](##Init).

Finaly this is the first version of react native 0.50 that doesn't generate the index.android.js and index.ios.js. We can start editing the App.js directly. I want my files to be under /src rather then /app since there is alreay an app.json and an App.js.

Change your App.js
<script src="https://gist.github.com/syl20lego/4a19ac0ec90cab66cc3811d071864f26?file=gist.md"></script>


# References

[Expo demonstrating how to build my app Capo Keys from scratch to deployment](https://www.youtube.com/playlist?list=PL06z42zB6YZ-9CQDX015uaeqMcSErKbes)
* Excellent tutorial to develop an application from begining to the end using Expo and Redus. Very good explanations on everything he is doing

[Simple React Native application with Redux](https://github.com/jlebensold/peckish)
* Provided me with the basic skeleton for redux, `createReducer.js` is interesting to simplify the reducer switch case. I haven't use it yet since it makes the reducers pattern looking different.

[What is the right way to do asynchronous operations in Redux?](https://decembersoft.com/posts/what-is-the-right-way-to-do-asynchronous-operations-in-redux/)
+ Provides good overview of different solutions for asynchronous framework working with redux. In the end, I select redux-sagas since I like keeping my actions being plain object and reducers simple and only handling states

# Environment

macOS Sierra
Version 10.12.6

npm --version
5.5.1

node --version
v6.11.3

react-native --version
react-native-cli: 2.0.1
react-native: 0.50.4
