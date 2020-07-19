# React Native

## React Native Ecosystem
- What is native development?
- Why is it important to develop a native app vs a responsive react app?
- It’s still just state and components
- But no HTML or CSS
- You can still “style” things using the framework guidelines

## Expo
- Expo Is the dev environment
- Snack is an online sandbox
- expo-cli is the local equivalent to create-react-app (you can eject)
- Running locally, you can use your own device or the official simulator
- Only Apple users can test iPhones
- Anyone can test android, but you need to start up an ADB from The Android Studio IDE

### Written in JavaScript—rendered with native code
React primitives render to **native platform UI**, meaning your app uses the same native platform APIs other apps do.
Many platforms, one React. Create platform-specific versions of components so a single codebase can share code across platforms.
With React Native, one team can maintain two platforms and share a common technology—React.

Example:
```
import React from 'react';
import {Text, View} from 'react-native';
import {Header} from './Header';
import {heading} from './Typography';

const WelcomeScreen = () =>
  <View>
    <Header title="Welcome to React Native"/>
    <Text style={heading}>Step One</Text>
    <Text>
      Edit App.js to change this screen and turn it
      into your app.
    </Text>
    <Text style={heading}>See Your Changes</Text>
    <Text>
      Press Cmd + R inside the simulator to reload
      your app’s code.
    </Text>
    <Text style={heading}>Debug</Text>
    <Text>
      Press Cmd + M or Shake your device to open the
      React Native Debug Menu.
    </Text>
    <Text style={heading}>Learn</Text>
    <Text>
      Read the docs to discover what to do next:
    </Text>
   </View>
   ```
   
   
