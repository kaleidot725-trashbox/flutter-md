# 2020/01/07 WIP Adding interactivity to your Flutter

# Adding interactivity to your Flutter
https://flutter.dev/docs/development/ui/interactive

- ステートレスウィジェットを管理する、ステートフルウィジェットを作成して、タップするとアイコンと数字が変化するウィジェットを作成したい。
- 上記を達成するために星とカウントの両方を含む、単一のカスタムウィジェットを作成する

# Stateful and stateless widgets

- StatelessWidgetは Icon や IconButton 、 Text などのウィジェットのことです。
- StatelessWidgetは StatelessWidgetのサブクラスになります。

- StatefulWidget は Checkbox, Radio, Slider, InkWell, Form, TextFiled などのウィジェットのことです。
- StatefullWidgetは StatefullWidgetのサブクラスになります。

- Widgetの状態は State オブジェクトに分けて格納している。 例えばチェックボックスがチェックされたとき、スライダーの値が変化させたときなど State が変化する。そのときにウィジェットの状態を変えるには setState() を呼び出す必要がある。 setState()を呼び出すとフレームワークがウィジェットを再描画する。

# Creating a stateful widget

- CustomStatefullWidgetを作成するには次の2つのクラスが必要
- StatefullWidgetのサブクラス、Stateのサブクラス、ここにウィジェットを生成するbuild()が定義される
- 