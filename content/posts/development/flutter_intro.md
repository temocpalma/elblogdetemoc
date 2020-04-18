+++
title = "Flutter Intro"
type="slide"
pre ="<i class='fa fa-anchor'></i> "
weight = 4
date = "2020-04-20"

theme = "sky"
[revealOptions]
transition= 'concave'
controls= true
progress= true
history= true
center= true
+++

### Basic Concepts

* Multiplataform Mobile Apps Development SDK

* Created by Google

* Dart Language
   - Created like option to javascript
   - It is compiled into native ARM code

___

### Basic Concepts (part 2)

* Own render engine
   - Skia based
   - Own great widget library
   - No longer version problems

* Official development framework for Fucshia

___

### Install Flutter

* Download SDK
* Extract file in a location
* Add tool to your path
* Run flutter doctor
   - Check output and perform the tasks for finish setup
      - Set up an editor (Android Studio, Xcode, Visual Studio Code)

[Install guide](https://flutter.dev/docs/get-started/install)

___

### Widgets

* All in flutter is a widget
* Apps are made up of a widget tree
* Exists two widget types:
   - Stateless: are immutable, meaning that their properties can’t change
   - Stateful: allow user interaction, it can change its state and therefore its appearance
___

### Stateful Widgets

* Requires at least two classes:
   - StatefulWidget class: only create the state
   ```
   class MyStatefulWidget extends StatefulWidget {
      @override
      MyStatefulWidgetState createState() => MyStatefulWidgetState();
   }
   ```
   - State class: contains all state logic
   ```
   class MyStatefulWidgetState extends State<MyStatefulWidget> {
      ...
      @override
      Widget build(BuildContext context) {
         ...
      }
      ...
   }
   ```
___

### Demo app

* *lib* folder: contains all implemented code
   - *main.dart* is the main class
* *pubspec.yaml:* manages the assets and dependencies

___

### Resources

* <a href="https://flutter.dev/docs/development/ui/widgets-intro" target="_blank">Introduction to widgets</a>
* <a href="https://flutter.dev/docs/reference/widgets" target="_blank">Flutter widget index</a>
* <a href="https://flutter.dev/docs/cookbook" target="_blank">Cookbook</a>
* <a href="https://api.flutter.dev/" target="_blank">Flutter API</a>
* <a href="https://pub.dev/" target="_blank">Packages</a>
* <a href="https://dart.dev/guides/language/language-tour" target="_blank">Dart language</a>

[Cerrar](/posts/development)
