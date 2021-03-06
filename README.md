Pretty Toast
============

![Logo](http://i.imgur.com/40mG7Lj.png)

This is quite simple toast library, that make it easier to show and create custom toast.

This library provides following features :

 * Bunch of predefined static methods for frequently used messages `Error`, `Info`,`Warning` ...
 * Flexible `Builder` class, so you construct almost any kind of toast message
 * Main class extends native `Toast` class
 * No memory leaks
 * Support starting from `Android 2.1` (`API 7`)

**UPDATE**
I updated library to version 0.2.0. There are some important issues were fixed. Now popup window looks much better.
So please use 0.2.0 version.

Screenshots and Examples
------------------------

![](./screen-animation.gif)

You can download example app from [Google Play Store](https://play.google.com/store/apps/details?id=ua.com.crosp.solutions.prettytoast)

Download and Installation 
-------------------------

Download [the latest AAR][1] or grab via Maven:
```xml
<dependency>
    <groupId>ua.com.crosp.solutions.library</groupId>
    <artifactId>pretty-toast</artifactId>
    <version>0.2.0</version>
</dependency>
```
or Gradle:
```groovy
compile 'ua.com.crosp.solutions.library:pretty-toast:0.2.0'
```


Usage
-----

**NOTE** :
If you want to use `Iconify Android` icons, you need to inject icons into yours `ApplicationContext`, invoke  
```java
PrettyToast.initIcons();
```
It should be called once, and `Application` class is great place for this, but you can also call it anywhere you want, `Iconify Library` takes care of filtering duplicates, so it will not waste your memory, but this doesn't mean that you should call `initIcons()` in a loop :)

For sure, if you are already using `Iconify Library` you don't need to invoke `initIcons()`, than in your `Application` custom class you have to have something like this.
```java
Iconify
                .with(new FontAwesomeModule())
                .with(new EntypoModule())
                .with(new TypiconsModule())
                .with(new MaterialModule())
                .with(new MaterialCommunityModule())
                .with(new MeteoconsModule())
                .with(new WeathericonsModule())
                .with(new SimpleLineIconsModule())
                .with(new IoniconsModule());
```
By the way, you can call `PrettyToast.initIcons()` instead of code above. It does the same thing.

Predefined static methods

```java
 PrettyToast.showWarning(getApplicationContext(), "WARNING");
 PrettyToast.showInfo(getApplicationContext(), "INFO");
 PrettyToast.showSuccess(getApplicationContext(), "SUCCESS");
 PrettyToast.showError(getApplicationContext(), "ERROR");
 PrettyToast.showDim(getApplicationContext(), "DIM");
```

Using `Builder` class

```java
   new PrettyToast.Builder(getApplicationContext())
                        .withRightIcon("mdi-earth")
                        .withMessage("Custom toast")
                        .withLeftIcon("mdi-stackoverflow")
                        .withDuration(Toast.LENGTH_SHORT)
                        .withLeftIconColor(R.color.firebrick)
                        .withBackgroundResource(R.drawable.background_custom)
                        .withGravity(new PrettyToast.Gravity(Gravity.START, 15, 0))
                        .withTextSize(24)
                        .withRightIconColor(R.color.blueviolet)
                        .withTextColor(R.color.blue)
                        .build()
                        .show();
```

Using completely custom view

```java
 new PrettyToast.Builder(getApplicationContext())
                        .withCustomView(LayoutInflater.from(MainActivity.this).inflate(R.layout.toast_custom, null, false))
                        .build()
                        .show();
```

You can use any icon provided by [Android-Iconify](https://github.com/JoanZapata/android-iconify) library

#Credits
- [Joan Zapata](https://github.com/JoanZapata)  The creator of [Android-Iconify](https://github.com/JoanZapata/android-iconify)
- [Pierry Borges](https://github.com/Pierry/SimpleToast) Thanks for the idea

License
-------

    Copyright 2016 Oleksandr Molochko

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.



 [1]: http://repo1.maven.org/maven2/ua/com/crosp/solutions/library/pretty-toast/0.1.0/pretty-toast-0.1.0.aar

