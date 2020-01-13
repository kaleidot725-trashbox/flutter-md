# 2020/01/07 Adding interactivity to your Flutter

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

# Managing state

- 状態を管理する方法は色々とある
- ウィジェットの設計者は、どの方法で状態を管理するか選択する

1. ウィジェットが自身の状態を管理する
3. ウィジェットの親が状態を管理する
4. 上記の２つをミックスしたアプローチ

チェックボックスの状態を管理する場合は親がふさわしく、
アニメーションの状態を管理するなら自身がというように分けるのがよいらしい。どっちかよくわからないときには親で管理する方法を選ぶのがよいです。

## The widget manages its own state

- ListViewを利用している開発者はスクロールを管理したくないです、ListView側で勝手にやってくれることを期待しています。
- 上記のような例の場合には自身で状態を管理する必要がでてきます。
- この場合だと自身の表示に利用する状態は全て自身が保持する

## The parent widget manages the widget’s state

- ウィジェットの親状態を管理するのが一番合理的らしい
- この場合だと自身の表示に利用する状態は全て親が保持する
- 親はウィジェットを生成する際に、子に状態を渡して表示に反映させる

## A mix-and-match approach

- 作成するウィジェトによっては、親も状態を持つし、子も状態を持つことがある。
- 例えば押しているときにボーターを表示、はなしたらボーダーを非表示するボタン、でかつ押したあとに表示が切り替わるボタンを作るとしたら、ボーダーに関しては自身で管理、押したかどうかの状態は親が管理など混ぜて使うことはある。

