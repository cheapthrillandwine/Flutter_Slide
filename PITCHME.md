### HOW TO RELEASE FLUTTER APP IN 30 DAYS FOR THE BEGINNERS 

#### Ryoichi KATAOKA @LIFE PEPPER inc. <br>

Twitter: @je_suis_laterre <br>
LinkedIn: Ryoichi KATAOKA <br>
Github: cheapthrillandwine

---

### WHO AM I ?

**EXPERIENCE**: <br>
Software Developer(11/2018 - ) <br>
Machine Learning Engineer(01/2018 - 01/2019) <br>

**LANGUAGE**: <br>
Python / JavaScript / React Native / Flutter 

**INTEREST**: <br>
Elm / Go

--- 

![PIC](lifepepper.png)

---

### Rec Loc Japan version 1.0 <br> ON Release at 20/05/2019 !!!

+++

![PIC](ReclocJapan.png)

---

### HOW MANY DEVELOPERS ?

FRONT END ==> **1**(ME) <br>
BACK  END ==> **2**(NOT FULL COMMIT) <br>

#### TOTAL **3** (LOL)

---

### HOW LONG TIME ?

ABOUT **30** DAYS

--- 

### DIFFICULTY

- Widget
- Video
- Nested JSON Parsing

--- 

### WHAT IS THE WIDGET !!??
🤔
 
+++

### TREE ??

![PIC](widgetTree.png)

###### (https://flutter.dev/docs/development/ui/layout)

+++

🤔

+++

### MY UNDERSTANDING...

+++

### BOX !!

![PIC](widgetBox2.png)

###### (https://flutter.dev/docs/development/ui/layout)

+++

### 😊

---

### HOW TO PLAY VIDEO STREAMING ??
😇

+++

### video_player ??
Github:[video_player](https://github.com/flutter/plugins/tree/master/packages/video_player)

- Loading Slowly
- Streaming Sometimes Stop
- Unstable

+++

### 😢

+++ 

### Chewie
Github:[chewie](https://github.com/brianegan/chewie)

- Loading 10s ==> 0.5s
- Streaming Smooth
- Stable

+++

### Demo

https://twitter.com/je_suis_laterre/status/1131071329275301888

### 🤗

---

### HOW TO JSON PARSING ?
😦

+++

### NESTED JSON

```json
[{
  "id":1,
  "name":"ProductName",
  "title": "ProductTitle",
  "images":[
    {
      "id":11,
      "imageName":"xCh-rhy",
      "title": "hogehoge",
      "imageUrl": "hogehoge.jpg",
      "videoUrl": "hogeohoge.mp4"
    },
    {
      "id":31,
      "imageName":"fjs-eun",
      "title": "fugafuga",
      "imageUrl": "fugafuga.jpg",
      "videoUrl": "fugafuga.mp4"
    }
  ]
}]
```

+++

### MODELS

```dart
// please access this api key http://api.recloc.tv/channels
class Article {
  final int id;
  final String name;
  final String title;
  final Image images;

  Channel({
    this.id, 
    this.name, 
    this.title,
    this.images});

  factory Article.fromJson(Map<String, dynamic> json){
    // var list = json['images'] as List;
    // print(list.runtimeType);

    return Article(
      id: json['id'],
      name: json['name'],
      title: json['title'],
      images: Article.fromJson(json['images'])
    );
  }
}

class Image {
  final int imagesId;
  final String imageName;
  final String title;
  final String imageUrl;
  final String videoUrl;
  
  Image(
    {
    this.id, 
    this.imageName, 
    this.title,
    this.imageUrl, 
    this.videoUrl, 
    }
  );

  factory Image.fromJson(Map<String, dynamic> json){
    return Image(
      imagesId: json['id'],
      imageName: json['imageName'],
      title: json['title'],
      imagesId: json['imageUrl'],
      videoUrl: json['videoUrl'],
    );
  }
}
```

+++

### Future / asnyc / await

```dart
Future <List<Article>> getData() async {
  List<Article> articleList;
  final String url = 'http://api.hogehoge.com/articles/';
  final resp = await http
      .get(Uri.encodeFull(url), headers: {"Accept": "application/json"}); 

   if (resp.statusCode == 200) {
     var data = json.decode(resp.body);
     var rest = data[0]["images"] as List;
     print(rest);
     articleList = rest.map<Article>((json) => Article.fromJson(json)).toList();
   } else
       throw Exception('We have not download data...');
   print("List Size: ${articleList.length}");   
   return articleList;  
}
```

+++

### 😆

---

### FUTURE

- BLoC (Bussiness Login Component) Pattern
- Architecture (Onion or Clean Architecture)
- Web App Release
...

-- 
### Thanks 
😆😆😆
