## 1) Flutter Structure

Material App -> home:scaffold -> debug , backgroundCOlor
                              -> appbar (title)
                              -> body

- Body

1) Column / Row
```dart
body: Column(
  mainAxisAlignment: MainAxisAlignment.start,
  crossAxisAlignment: CrossAxisAlignment.start,
  children: myList2,
  @
  child : Text('Ini adalah column')
)
```

2) Stack
```dart
body: Stack(
  children: myList2,
  @
  child : Text('Ini adalah column')
)
```

3) ListView
```dart
body: ListView(
  children: myList2,
)
```

4) ListView Builder
```dart
body: ListView.builder(
  itemCount : myList.length
  itemBuilder: (context,index){
    return Container(

    );
  },
)
```

5) ListView Separator
```dart
body: ListView.separated(
  itemCount : myList.length
  itemBuilder: (context,index){
    return Container(

    );
  },
  separatorBu: (context,index){
    return Container(

    );
  },
)
```

- Things to put in children

1) Container
```dart
children: [
  Container(
    width: 100,
    height: 100,
    color: Colors.amber,
    child: Text('Ini adalah text'),
  )
],
```















======

Learn Flutter here : https://www.youtube.com/watch?v=epRWFH47xCI&list=PL7jdfftn7HKsfTtv8FOaTbLIf7feiQTRu&pp=iAQB

## Any Random Notes :
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