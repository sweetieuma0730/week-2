week-2(a)
import 'package:flutter/material.dart';

void main() {
  runApp(MyFullWidgetDemo());
}

class MyFullWidgetDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Widget Showcase',
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Text('Widget Demo AppBar'),
          backgroundColor: Colors.purple,
        ),
        body: SingleChildScrollView(
          padding: EdgeInsets.all(16),
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.stretch,
            children: [
              Container(
                color: Colors.lightBlue[100],
                padding: EdgeInsets.all(10),
                child: Image.network(
                  'https://images.pexels.com/photos/674010/pexels-photo674010.jpeg?cs=srgb&dl=pexels-anjana-c-169994674010.jpg&fm=jpg',
                  height: 150,
                  fit: BoxFit.contain,
                ),
              ),
              SizedBox(height: 16),
              Container(
                color: Colors.yellow[200],
                padding: EdgeInsets.all(16),
                child: Center(
                  child: Text(
                    'Hello from Flutter!',
                    style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
                    textAlign: TextAlign.center,
                  ),
                ),
              ),
              SizedBox(height: 16),
              Container(
                margin: EdgeInsets.symmetric(vertical: 10),
                padding: EdgeInsets.all(16),
                color: Colors.green[200],
                child: Text(
                  'This is a container with margin and padding',
                  style: TextStyle(fontSize: 18),
                  textAlign: TextAlign.center,
                ),
              ),
              SizedBox(height: 16),
              Container(
                color: Colors.red[100],
                padding: EdgeInsets.all(16),
                child: Center(
                  child: IconButton(
                    icon: Icon(Icons.thumb_up, size: 40),
                    color: Colors.deepPurple,
                    onPressed: () {
                      print('IconButton Pressed');
                    },
                  ),
                ),
              ),
              SizedBox(height: 16),
              Container(
                color: Colors.orange[100],
                padding: EdgeInsets.all(16),
                child: Column(
                  children: [
                    TextField(
                      decoration: InputDecoration(
                        labelText: 'Name',
                        border: OutlineInputBorder(),
                      ),
                    ),
                    SizedBox(height: 10),
                    TextField(
                      decoration: InputDecoration(
                        labelText: 'Email',
                        border: OutlineInputBorder(),
                      ),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}


week-2(b)
import 'package:flutter/material.dart';

void main() {
  runApp(LayoutDemoApp());
}

class LayoutDemoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Layout Structures Demo',
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Text('Row, Column & Stack Layouts'),
          backgroundColor: Colors.deepPurple,
        ),
        body: SingleChildScrollView(
          child: Padding(
            padding: const EdgeInsets.all(16.0),
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.stretch,
              children: [
                Text(
                  'Row Layout (Horizontal)',
                  style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Row(
                  mainAxisAlignment: MainAxisAlignment.spaceAround,
                  crossAxisAlignment: CrossAxisAlignment.center,
                  children: [
                    Icon(Icons.home, color: Colors.blue),
                    Text('Home'),
                    ElevatedButton(onPressed: () {}, child: Text('Click')),
                  ],
                ),
                Divider(),
                Text(
                  'Column Layout (Vertical)',
                  style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Icon(Icons.person, color: Colors.orange),
                    Text('Profile'),
                    ElevatedButton(onPressed: () {}, child: Text('Edit')),
                  ],
                ),
                Divider(),
                Text(
                  'Nested Row & Column',
                  style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Row(
                  children: [
                    Expanded(
                      child: Column(
                        children: [
                          Text('Left Section'),
                          Icon(Icons.arrow_left),
                        ],
                      ),
                    ),
                    Expanded(
                      child: Column(
                        children: [
                          Text('Right Section'),
                          Icon(Icons.arrow_right),
                        ],
                      ),
                    ),
                  ],
                ),
                Divider(),
                Text(
                  'Row with Expanded Widgets',
                  style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Row(
                  children: [
                    Expanded(child: Container(height: 50, color: Colors.red)),
                    Expanded(child: Container(height: 50, color: Colors.green)),
                    Expanded(child: Container(height: 50, color: Colors.blue)),
                  ],
                ),
                Divider(),
                Text(
                  'Stack Layout (Overlapping)',
                  style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Center(
                  child: Container(
                    width: 200,
                    height: 200,
                    color: Colors.grey[300],
                    child: Stack(
                      alignment: Alignment.center,
                      children: [
                        Container(width: 150, height: 150, color: Colors.red),
                        Container(width: 100, height: 100, color: Colors.green),
                        Container(width: 50, height: 50, color: Colors.blue),
                        Positioned(
                          right: 10,
                          bottom: 10,
                          child: Text(
                            'Positioned Text',
                            style: TextStyle(
                              color: Colors.white,
                              backgroundColor: Colors.black,
                            ),
                          ),
                        ),
                      ],
                    ),
                  ),
                ),
                Divider(),
                Text(
                  'Stack with Image & Text',
                  style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Center(
                  child: Stack(
                    alignment: Alignment.bottomCenter,
                    children: [
                      Image.network(
                        'https://images.pexels.com/photos/674010/pexels-photo674010.jpeg?cs=srgb&dl=pexels-anjana-c-169994674010.jpg&fm=jpg',
                        width: 200,
                        height: 200,
                        fit: BoxFit.cover,
                      ),
                      Container(
                        width: 200,
                        color: Colors.black54,
                        padding: EdgeInsets.all(4),
                        child: Text(
                          'Flutter Logo',
                          style: TextStyle(color: Colors.white),
                          textAlign: TextAlign.center,
                        ),
                      )
                    ],
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}



