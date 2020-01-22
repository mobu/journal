---
title: "Stream tutorial"
date: 2020-01-21T11:36:30-06:00
draft: false
---
## Streams

To create a Stream you have to create a **StreamController**

```dart
var controller = new StreamController<String>();

controller.add("Item1"); // Put first item on the belt
```

 - The generic type (in this case String) that has to be passed when
   creating a StreamController defines which type of objects we can push
   onto the Stream.
   
Now we’ve got the trap set, using the `.listen()` method on the stream of the StreamController.

```dart
var controller = new StreamController<String>();


controller.stream.listen((item) => print(item)); // this is the trap

controller.add("Item1");
controller.add("Item2");
controller.add("Item3");
```

 - You have to pass a function into the .listen() method because it
   needs to know what to do when it “hears” something (when a new data
   object arrived at the end of the Stream).
 - This function that you’re passing in needs to accept a parameter that
   is of the same type the StreamController was created with.
   
https://www.burkharts.net/apps/blog/fundamentals-of-dart-streams/
