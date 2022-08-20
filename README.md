# flutter_d1_restaurant_picker

- main.dart
```dart
import 'dart:math';

import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatefulWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  List<String> restaurans = ["McDonald\'s", "Pizza Hut", "Besto", "Geprek"];

  int? currentIndex;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              const Text('What do you want to eat?'),
              if (currentIndex != null)
                Text(
                  restaurans[currentIndex!],
                  style: const TextStyle(
                    fontSize: 30,
                    fontWeight: FontWeight.bold,
                  ),
                ),
              const Padding(
                padding: EdgeInsets.only(
                  top: 16,
                ),
              ),
              FlatButton(
                onPressed: () {
                  updateIndex();
                },
                child: const Text('Pick Resturant'),
                color: Colors.purple,
                textColor: Colors.white,
              )
            ],
          ),
        ),
      ),
    );
  }

  void updateIndex() {
    final random = Random();
    final index = random.nextInt(restaurans.length);

    setState(() {
      currentIndex = index;
    });
  }
}
```

---

```
Copyright 2022 M. Fadli Zein
```