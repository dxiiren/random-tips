Flutter Structure
```dart
Material App -> home:scaffold -> debug , backgroundColor
                              -> appbar (title)
                              -> body

//MATERIAL APP
return MaterialApp(
  debugShowCheckedModeBanner: false,
  theme: ThemeData(
    brightness: Brightness.dark,
    appBarTheme: AppBarTheme(
      color: Colors.red,
    )
  ),
  home: ProductHome()
);

//APPBAR
appBar: AppBar(
  leading: Text('Ini leading'),
  leadingWidth: 100,
  title: Text('Resitku'),
  centerTitle: true,
  actions: [
    Container(
      width: 100,
      height: 100,
      child: Text('Ini actions'),
    )
  ],
  bottom: PreferredSize(
    preferredSize: Size.fromHeight(100),
    child: Text('Ini Bottom'),
  ),
  flexibleSpace: Container(
    child: Text('Ini Flexible'),
  ),
),
```

## 1) Visible Widget
```dart
//TEXT
Text(
  'Hi ini adalah text je ',
  maxLines : 2,
  overflow: textOverflow.ellipses,
  textDirection : TextDirection
  style : TextStyle(
    backgroundColor:
    fontSize:
    fontWeigth:
    decoration: TextDecoration()
  )
)

//IMAGE
Image(
  fit:BoxFit.cover ,
  image: NetworkImage('https://picsum.photos/200')  //AssetImage('')
)

//BUTTON
FloatingActionButton(
  onPressed: () {     // onPressed: null
    setState(() {
      counter++;
    });
  },

  child: Icon(Icons.add),
),

//TEXT FEILD
child: TextField(
  //features
  autocorrect: true,
  autofocus: true,
  showCursor: true,
  enableSuggestions: true,
  enableInteractiveSelection: true,
  enabled: true,
  obscureText: false,
  keyboardType: TextInputType.name,
  readOnly: false,

  //decoration
  textAlign: TextAlign.start,
  textCapitalization: TextCapitalization.characters,
  style: TextStyle(
    color: Colors.amber,
    fontSize: 20,
  ),
  decoration: InputDecoration(
    icon: Icon(Icons.person_2,size: 30,),
    border: OutlineInputBorder(),
    prefixText: "Name : ",
    hintText: "Please enter your name",
    labelText: "Full Name",
    prefixIcon: Icon(Icons.remove_red_eye ,size: 30),
    suffixIcon: Icon(Icons.camera_enhance ,size: 30), 
  ),


  //control
  controller: myController,
  //onchanged
  // onEditingComplete: ,
  onSubmitted: (value) {
    print(value);
  },

),

```




## 2) Invisible Widget

- A) Column / Row
```dart
body: Column(
  mainAxisAlignment: MainAxisAlignment.start,
  crossAxisAlignment: CrossAxisAlignment.start,
  alignment: Alignment.bottomLeft,

  children: myList2,
  @
  child : Text('Ini adalah column')
)
```

-B) Container
```dart
children: [
  Container(
    width: 100,
    height: 100,
    color: Colors.amber,
    padding: EdgeInsets.all(10),
    margin: EdgeInsets.symmetric(
      vertical: 15,
      horizontal: 8
    ),
    child: Text('Ini adalah text'),
  )
],
```

- B) Stack
```dart
body: Stack(
  children: myList2,
  @
  child : Text('Ini adalah column')
)
```

- C) Card
```dart
body: Card(
  margin: EdgeInsets.all(20),
  padding: EdgeInsets.all(10),
  child : Container(
  )
)
```

- D) Single Child Scroll
```dart
body: SingleChildScrollView(
  scrollDirection: Axis.horizontal,
  child: Row()
```

- C) ListView
```dart
body: ListView(
  children: myList2,
)
```

- D) Grid View
```dart
body: GridView.count(
  padding: EdgeInsets.all(10),
  crossAxisCount: 3,
  crossAxisSpacing: 20,
  mainAxisSpacing: 10,
  childAspectRatio: 3/4,
  children: myList,
),
```

- E) Grid View Builder
```dart
body: GridView.builder(
  padding: EdgeInsets.all(10),
  gridDelegate:
      SliverGridDelegateWithFixedCrossAxisCount(
        crossAxisCount: 2,
        crossAxisSpacing: 10,
        mainAxisSpacing: 10,
      ),
  itemBuilder: ((context, index) {
    return GridTile(
      child: Image.network(dummyData[index].imageurl),
      footer: Container(
        color: Colors.blue,
        child: Column(
          children: [
            Text(dummyData[index].name),
            Text(dummyData[index].harga),
            Text(dummyData[index].description),
          ],
        ),
      ),
    );
  }),
  itemCount: dummyData.length,
)
```

- D) ListView Builder
```dart
body: ListView.builder(
  itemCount : myList.length
  itemBuilder: (context,index){
    return ListTile(
      title: Text('Ahmad Albab'),
      subtitle: Text(' Ini mesej daripada Ahmad Albab'),
      leading: CircleAvatar(),
      trailing: Text('10:00 PM'),
      tileColor : Colors.red,
      contextPadding: EdgeInsects.all(10),
      onTap(){
      }
    ),
  },
)
```

- E) ListView Separator
```dart
body: ListView.separated(
  itemCount : myList.length
  itemBuilder: (context,index){
    return Container(

    );
  },
  separatorBuilder: (context,index){
    return Container(

    );
  },
)
```




## 2) List / Array
```dart
List<Color> myColor = [Colors.red, Colors.blue, Colors.yellow, Colors.green];

List<Widget> myList = [
  Container(
    height: 300,
    width: 300,
    color: Colors.amber,
    child: Text('Ini Aplikasi Resitku'),
  ),
  Container(
    height: 300,
    width: 300,
    color: Colors.red,
    child: Text('Ini Aplikasi Resitku'),
  ),
];

List<Widget> myList2 = List.generate(100, (index) => Text(" Ini nombor  ${index+1}" , style: TextStyle(fontSize: 20 + double.parse(index.toString())),));

//MODEL
import 'package:flutter/material.dart';

class Product {
  @required
  String name = "";
  @required
  String imageurl = "";
  @required
  String description = "";
  @required
  String harga = "";

  Product(this.name, this.imageurl, this.description, this.harga);
}


List<Product> dummyData = List.generate(100, (index) {
  return Product(
      faker.person.name(),
      "https://picsum.photos/id/$index/200",
      faker.lorem.sentence(),
      Random().nextInt(1000).toString());
});
```

## 3) ANIMATION

- A) NAVIGATION
```dart
return Scaffold(
  appBar: AppBar(title: Text("Page 1")),
  floatingActionButton: FloatingActionButton(
    onPressed: () {
      //THIS ONE TO NAVIGATE
      Navigator.of(context).pop();
    },
    child: Icon(Icons.keyboard_arrow_left),
  ),
  floatingActionButtonLocation: FloatingActionButtonLocation.centerFloat,
  body: Center(
    child: Text(
      'Ini Page 1',
      style: TextStyle(fontSize: 50),
    ),
  ),
  // body: ,
);
```

- B) ROUTE
```dart
  //main.dart
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomePage(),
      debugShowCheckedModeBanner: false,
      initialRoute: '/homepage',
      routes: {
        '/pageone' : (context) => PageOne(),  //class
        '/pagetwo' : (context) => PageTwo(),  //class
        '/pagethree' : (context) => PageThree()  //class
      },
    );

  //pageOne
  body: Center(
    child: Column(
      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
      children: [
        Text('Ini First Page'),
        Row(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: () {
                //this one to change to back page
                Navigator.of(context).pop();
              },
              child: Text('Back')),
            SizedBox(
              width: 30,
            ),
            ElevatedButton(
              onPressed: () {
                //this one to change to another page
                Navigator.of(context).pushNamed('/pagetwo');
              },
              child: Text('Next')),
          ],
        )
      ],
    )
  ),
```

- C) Popup
```dart
//SHOW DIALOG + ALERT DIALOG
floatingActionButton: FloatingActionButton(
  child: Icon(Icons.delete),
  onPressed: () {
    showDialog(
      context: context,
      builder: (context) {
        return AlertDialog(
          title: Text('Confirm ?'),
          content: Text('Are you sure want to delete this item ?'),
          actions: [
            ElevatedButton(
              onPressed: () {
                Navigator.of(context).pop();
              },
              child: Text('Yes')
            ),
            ElevatedButton(
              onPressed: () {
                Navigator.of(context).pop();
              },
              child: Text('No')
            ),
          ],
        );
      }
    );
  }
),
```
======


## Any Random Notes :
- Learn Flutter here : https://www.youtube.com/watch?v=epRWFH47xCI&list=PL7jdfftn7HKsfTtv8FOaTbLIf7feiQTRu&pp=iAQB
- https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple
- https://stackoverflow.com/questions/59970266/how-to-handle-deep-linking-to-a-flutter-app
- https://youtu.be/KNAb2XL7k2g

## Any Random Code :
```dart
return MaterialApp(
   debugShowCheckedModeBanner: false,
   title: 'Starter Template',
   theme: ThemeData(
     primarySwatch: Colors.blue,
   ),
   home: Home(),
 )
```
