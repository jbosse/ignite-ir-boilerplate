# ARCHIVED

I am currently working on Nativescript Vue applications because we are using Vue for our web interfaces in my day job. As a result, the only time I see the repository is when an issue is opened and it takes time I don't currently have to keep up with what is going on with both React and Ignite. 

As a result I am archiving this repo.

If you are here because you want to use Expo with React and Ignite, please look a the first few commits to this repo in the commit history. It is really easy to initialize your app with the default Ignite boilerplate and make the changes necessary to use the Expo fork of React Native.

If you are an active Ignite/React Native/Expo user and would like to maintain this repository, please send me an email and I will gladly transfer this repo to you and figure out how to transfer the npm publish rights as well.

---

[![Build Status](https://semaphoreci.com/api/v1/jbosse/ignite-expo-boilerplate/branches/master/badge.svg)](https://semaphoreci.com/jbosse/ignite-expo-boilerplate)
[![Maintainability](https://api.codeclimate.com/v1/badges/9b673e2d752791ec2dff/maintainability)](https://codeclimate.com/github/jbosse/ignite-expo-boilerplate/maintainability)

# Ignite Expo Boilerplate

## Ignite IR Fork full of Expo.io Goodness

This is a fork of the [Infinite Red Boilerplate](https://github.com/infinitered/ignite-ir-boilerplate) that has been modified to work with [Expo.io](https://docs.expo.io/versions/latest/index.html).

Currently includes:

* Expo React Native (https://github.com/expo/react-native/archive/sdk-26.0.0.tar.gz)
* React Navigation
* Redux
* Redux Sagas
* And more!

## Quick Start

When you've installed the [Ignite CLI](https://github.com/infinitered/ignite), you can get started with this boilerplate like this:

```
ignite new MyLatestCreation -b ignite-expo
```

## Boilerplate walkthrough

Your `App` folder is where most of the goodies are found in an Ignite Next app. Let's walk through them in more detail. Start with `Containers/App.js` (described below) and work your way down the walkthrough in order.

### Containers

Containers are (mostly) full screens, although they can be sections of screens or application containers.

* `App.js` - your main application. We create a Redux store and configure it here
* `RootContainer.js` - main view of your application. Contains your status bar and navigation component
* `LaunchScreen.js` - this is the first screen shown in your application. It's loaded into the Navigation component
* `Styles` - styling for each of the above containers and screens

To generate a new Container or Screen you can use the following generator commands:

* `ignite g container New` - Will create a `New.js` and also a `Styles/NewStyle.js`.
* `ignite g list New` - The same as the `container` command, but it will give you a walkthrough to generate a ListView screen. Allowing you to even pick `FlatList` or not, grid, and some other options. 
* `ignite g screen New` - Will create a `NewScreen.js` and also a `Styles/NewScreenStyle.js`. Important to mention that the `screen` generator will add the `Screen` on the file/class name to make easierto identify

Those commands will also add the new container to the navigations file.

### Navigation

Your primary and other navigation components reside here.

* `AppNavigation.js` - loads in your initial screen and creates your menu(s) in a StackNavigation
* `Styles` - styling for the navigation

### Components

React components go here...pretty self-explanatory. We won't go through each in detail -- open each file to read the comments and view the code.

To generate a new Component you can use the following generator commands:

* `ignite g component New` - Will create a `New.js` and also a `Styles/NewStyle.js`.
* `ignite g component path/New` - The same as above, but will use a relative path
* `ignite g component --folder path` - An alternative to `ignite g component path/index`
* `ignite g component --folder path new ` - An alternative to `ignite g component relativePath/New`

### Storybook

[Storybook](https://storybook.js.org/) has been setup to show off components in the different states. Storybook is a great way to develop and test components outside of use in your app. To get started:

* Set `launchStorybook: __DEV__` inside `App/Config/DebugConfig.js`
* Run `yarn run storybook`
* In a separate terminal, run `yarn run ios` or `yarn run android`

All stories are contained in the `*.story.js` files along side the components.

### Themes

Styling themes used throughout your app styles.

* `ApplicationStyles.js` - app-wide styles
* `Colors.js` - defined colors for your app
* `Fonts.js` - defined fonts for your app
* `Images.js` - loads and caches images used in your app
* `Metrics.js` - useful measurements of things like navBarHeight

### Config

Initialize and configure things here.

* `AppConfig.js` - simple React Native configuration here
* `DebugConfig.js` - define how you want your debug environment to act
* `ReactotronConfig.js` - configures [Reactotron](https://github.com/infinitered/reactotron) in your project (Note: this [will be extracted](https://github.com/infinitered/ignite/issues/779) into a plugin in the future)
* `ReduxPersist.js` - configures Redux Persist (Note: this [will be extracted](https://github.com/infinitered/ignite/issues/780) into a plugin in the future)

### Fixtures

Contains json files that mimic API responses for quicker development. These are used by the `Services/FixtureApi.js` object to mock API responses.

### Redux, Sagas

Contains a preconfigured Redux and Redux-Sagas setup. Review each file carefully to see how Redux interacts with your application.

Here again we have generators to help you out. You just have to use one of the following:

* `ignite g redux Amazing` - Will generate and link the redux for `Amazing`.
* `ignite g saga Amazing` - The same as above, but for the Sagas

_TODO: explain more about Redux & Redux Sagas here_

### Services

Contains your API service and other important utilities for your application.

* `Api.js` - main API service, giving you an interface to communicate with your back end
* `ExamplesRegistry.js` - lets you view component and Ignite plugin examples in your app
* `FixtureApi.js` - mocks your API service, making it faster to develop early on in your app
* `ImmutablePersistenceTransform.js` - part of the redux-persist implementation (will be removed)
* `RehydrationServices.js` - part of the redux-persist implementation (will be removed)

### Lib

We recommend using this folder for modules that can be extracted into their own NPM packages at some point.

### Images

Contains actual images (usually png) used in your application.

### Transforms

Helpers for transforming data between API and your application and vice versa. An example is provided that you can look at to see how it works.

### Tests

This folder (located as a sibling to `App`) contains sample Jest snapshot and unit tests for your application.

If you would like to have the `ignite generate` command include the generation of tests when avaiable, add 
`"test": "jest"` or `"test": "ava"` to `./ignite/ignite.json`, depending on the test runner you are using.
