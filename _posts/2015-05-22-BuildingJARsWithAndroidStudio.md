---
layout:     post
title:      Building JARs With Android Studio
date:       2015-05-22
summary:    Summary!
categories: android java
---

Android Studio offers an in-built Gradle-build system, which makes things a lot easier. Say for example, you’re trying to use [Picasso](http://square.github.io/picasso/) as a third-party library in your Android app. You could go about this in two ways:

* Download the jar file and place it in the `build/libs/` folder, or
* Add it as a dependency, by placing `compile 'com.squareup.picasso:picasso:2.5.2'` in your `build.gradle` file

In case you come across a third party library that is neither hosted online, nor has a readily available jar file, the only option you’ve got is to build the jar file yourself. This post is meant to be an under-a-minute tutorial to help you building the JAR file yourself.

# Building a JAR file using Android Studio

Consider the [Spotify Web API Wrapper](https://github.com/kaaes/spotify-web-api-android),

1. Clone the repo locally. Try, `git clone https://github.com/kaaes/spotify-web-api-android.git`
2. Import the project in Android Studio
3. Build - Make Project
4. In the Terminal, `gradlew jar`

You’re done! The jar file is now found in `build/libs`.
