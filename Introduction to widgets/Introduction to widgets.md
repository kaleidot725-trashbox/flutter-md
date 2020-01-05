# 2020/01/05 - Introduction to widgets

# Introduction to widgets
https://flutter.dev/docs/development/ui/widgets-intro

- Flutter ウィジェットは　React にインスパイアされたモダンなフレームワークを利用して組み立てます。
- ウィジェットは現在の構成と状態を考慮して、ビューがどのように見えるか記述し、変更の必要があれば再構築する。

# Hello World

- `runApp()`はウィジェットで関数を呼び出す、これが最小限のFlutterアプリになる。
- `runApp()`ではウィジェットを受け取り、そのウィジェットをウィジェットツリーのルートとする。
- アプリを作成するときにはウィジェットの状態を管理するかどうかで、
　`StatelessWidget`を利用するか、`StatefulWidget`を利用するか決めていく。
- アプリはこの定義したウィジェットをアプリが終了するまで、順番にレンダリングしていく。

# Basic widgets

- Text, Row, Column, Stack, Container などの基本的なウィジェットがある。

# Using Material Components

- Flutter には Material Design に対応した複数のウィジェットがある。
- MaterialApp ウィジェットを使うことで、簡単にマテリアルデザインに対応したアプリを作成できる。
- ナビゲータを含む、複数のウィジェットで Flutter アプリは構成される
- ナビゲーターはスムーズに画面観を遷移されるために利用されるものです。

# Handling gesture

- `GestureDetector` ウィジェットを利用すれば、ユーザーのジェスチャを検知できる。
- 見た目に関しては`GetsureDetector`ウィジェットの`child`に`Container`を定義することで表現する、
  ユーザーのジェスチャに応じて、見た目を変化させたい時は`onTap`等を定義し、`Container`を変更するようにする。
# Changing widgets in response to input

- `StatelessWidgets`は後から変更できない、後から変更する場合は`StatefullWidgets`を利用する。
- なぜ`StatefulWidget`と`State`が分かれているのか？、この２つのオブジェクトは違うライフサイクルを持っているからです。
- Widget はアプリの現在の状況に応じて生成されるオブジェクトで、
  State はアプリで build を実行してから永続的になるオブジェクトです。
  
```dart
class Counter extends StatefulWidget {
  // CounterStateではアプリの状態を保持し続ける
  @override
  _CounterState createState() => _CounterState();
}

class _CounterState extends State<Counter> {
  int _counter = 0;

  void _increment() {
    // setStateを呼び出すとなにか変更したことを通知する
    // setStateの中で更新処理を加えると、変更した内容がViewに反映される
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    // BuildメソッドはsetStateを呼び出すたびに呼び出されます。
    // 次の例だと RaisedButton の _incrtement を呼び出すと、setStateが呼び出されるので、
    // build メソッドが再度呼び出されます。
    return Row(
      children: <Widget>[
        RaisedButton(
          onPressed: _increment,
          child: Text('Increment'),
        ),
        Text('Count: $_counter'),
      ],
    );
  }
}
```