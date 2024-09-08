# Flutter Demo App with Drawer

This is a simple Flutter application demonstrating the usage of a Drawer widget. The app contains a custom AppBar, a Drawer with multiple ListTiles for navigation, and a body showcasing the welcome message.

## Features

- **AppBar**: Custom AppBar with a yellow background and the title "Flutter Demo App".
- **Drawer**: A navigation drawer with the following sections:
  - My Profile
  - My Course
  - Go Premium
  - Saved Videos
  - Edit Profile
  - LogOut
- **Custom Drawer Header**: A Drawer header with user information, including name, email, and an avatar with custom styling.
#Project Structure
The main file for the app is main.dart, which contains the following key components:

MyApp: The root widget of the application.
MyHomePage: The home page of the app, containing the AppBar, body content, and the Drawer.

## Code

Here’s the main code of the application (`main.dart`):

```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  final appTitle = 'Flutter Demo App';
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: appTitle,
      home: MyHomePage(title: appTitle),
    );
  }
}

class MyHomePage extends StatelessWidget {
  final String title;

  const MyHomePage({Key? key, required this.title})
      : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(title),
        backgroundColor: Colors.yellow,
      ),
      body: const Center(
        child: Text(
          'Welcome to the Demo of Drawer in Flutter',
          style: TextStyle(fontSize: 30.0),
        ),
      ),
      drawer: Drawer(
        child: ListView(
          padding: const EdgeInsets.all(0),
          children: [
            const UserAccountsDrawerHeader(
              decoration: BoxDecoration(color: Color(0xff968d40)),
              accountName: Text(
                "Yogi",
                style: TextStyle(fontSize: 18),
              ),
              accountEmail: Text("xxxyyyzzz@gmail.com"),
              currentAccountPictureSize: Size.square(50),
              currentAccountPicture: CircleAvatar(
                backgroundColor: Color.fromARGB(255, 165, 255, 137),
                child: Text(
                  "Y",
                  style: TextStyle(fontSize: 30.0, color: Colors.blue),
                ),
              ),
            ),
            ListTile(
              leading: const Icon(Icons.person),
              title: const Text(' My Profile '),
              onTap: () {
                Navigator.pop(context);
              },
            ),
            ListTile(
              leading: const Icon(Icons.book),
              title: const Text(' My Course '),
              onTap: () {
                Navigator.pop(context);
              },
            ),
            ListTile(
              leading: const Icon(Icons.workspace_premium),
              title: const Text(' Go Premium '),
              onTap: () {
                Navigator.pop(context);
              },
            ),
            ListTile(
              leading: const Icon(Icons.bookmark),
              title: const Text(' Saved Videos '),
              onTap: () {
                Navigator.pop(context);
              },
            ),
            ListTile(
              leading: const Icon(Icons.settings),
              title: const Text(' Edit Profile '),
              onTap: () {
                Navigator.pop(context);
              },
            ),
            ListTile(
              leading: const Icon(Icons.logout),
              title: const Text('LogOut'),
              onTap: () {
                Navigator.pop(context);
              },
            ),
          ],
        ),
      ),
    );
  }
}
