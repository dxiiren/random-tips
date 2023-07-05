Flutter Structure

Material App -> home:scaffold -> debug , backgroundCOlor
                              -> appbar (title)
                              -> body

## 1) Widget

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
    child: Text('Ini adalah text'),
  )
],

//2

```

## 2) List / Array
```dart
body: Stack(
  children: myList2,
  @
  child : Text('Ini adalah column')
)
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