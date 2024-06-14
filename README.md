# Capacitor Example Project

Simple project to test out the capabilities of capacitor.

Using Vite, React, Typescript (SWC), Capacitor and MUI.

## Contents

- [Setup Steps MacOs](#setup-steps-macos)
  - [Prerequisites](#prerequisites)
  - [Capacitor/ React Setup](#capacitor/-react-setup)
- [Running](#running)
  - [Web](#web)
  - [Android](#android)
  - [IOS](#ios)
- [Vite Template: React + TypeScript + Vite](#vite-template:-react-+-typescript-+-vite)

## Setup Steps MacOs

### Prerequisites

- Node + NPM
- [Android Studio](https://developer.android.com/studio)
- [Xcode](https://developer.apple.com/xcode/)
- Ruby for Cocoapods:

```sh
# Ruby latest version using rbenv
brew install rbenv ruby-build
rbenv install 3.3.3

# Cocoapods (Verbose)
sudo gem install -V cocoapods
```

- Java for android

```sh
# Java
brew install openjdk@17

# Link files
sudo ln -sfn /opt/homebrew/opt/openjdk@17/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk

# Add to path
echo 'export PATH="/opt/homebrew/opt/openjdk@17/bin:$PATH"' >> ~/.zshrc
export CPPFLAGS="-I/opt/homebrew/opt/openjdk@17/include"
```

### Capacitor/ React Setup

https://capacitorjs.com/docs/basics/workflow

```sh
# Create empty vite react ts project called capacitor (I picked swc compiler)
npm create vite@latest capacitor --template react-ts
cd capacitor
npm i

# Install capacitor
npm i @capacitor/core\n npm i -D @capacitor/cli

# Initialise capacitor project
npx cap init

# Install ios and android platforms
npm i @capacitor/android @capacitor/ios

# Create android and ios projects
npx cap add android\n npx cap add ios

# Build react code to dist folder
npm run build

# Sync built dist folder with the ios and android projects
npx cap sync
```

## Running

### Web

`npm run dev`

### Android

`npx cap run android` - run on simulator
`npx cap open android` - runs in android studio

> If there are any issues try the android studio project first. You may need to: [check A studio build tools](https://stackoverflow.com/a/68972393)

### IOS

`npx cap run ios` - runs simulator
`npx cap open ios` - runs in xcode

> If there are any issues you may need to check xcode > settings > platforms and make sure the correct vesion ios is installed

## Vite Template: React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh
