Flutter Structure
```dart
Material App -> home:scaffold -> debug , backgroundColor
                              -> appbar (title)
                              -> body
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

```




## 2) Invisible Widget

- A) Column / Row
```dart
body: Column(
  mainAxisAlignment: MainAxisAlignment.start,
  crossAxisAlignment: CrossAxisAlignment.start,
  children: myList2,
  @
  child : Text('Ini adalah column')
)
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

- D) ListView Builder
```dart
body: ListView.builder(
  itemCount : myList.length
  itemBuilder: (context,index){
    return Container(

    );
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

- F) Things to put in children

```dart
//1. CONTAINER
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

//2. LIST TILE
children: [
  ListTile(
    title: Text('Ahmad Albab'),
    subtitle: Text(' Ini mesej daripada Ahmad Albab'),
    leading: CircleAvatar(),
    trailing: Text('10:00 PM'),
    tileColor : Colors.red,
    contextPadding: EdgeInsects.all(10),
    onTap(){
    }
  ),

  Divider(),
  SizedBox(
    width:
    height:
  )
]




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