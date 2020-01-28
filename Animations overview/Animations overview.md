# 2020/01/27 Animations overview

# Animations overview
https://flutter.dev/docs/development/ui/animations/overview

- Flutter のアニメーションシステムは Animation タイプオブジェクトをベースにしている。

# Animation

- Animation クラスはアニメーションしすてむの主要なブロックを構成する
- 多くのウィジェットはアニメーションを描画するときに パラメータとして Animation オブジェクトを受け取り、その現在値を読み取り、その値をリッスンします。

## addListener

- アニメーションの値が変更するたびに、Animation は addListener として登録した全てのリスナーに通知します。
- 大抵は Animation を購読している State オブジェクトは setState を呼び出す。
- setStateを呼びだして、新しい値で再構築が必要なウィジェットシステムに通知するために自身のリスナーのコールバックを呼び出す。 

- AnimatedWidgetとAnimatedBuilderはアニメーションの値が変わったときに、ウィジェットの再構築を助ける。このパターンはとても一般的です。

- AnimatedWidget は 状態を持たないアニメーションのためにとてもよく使える。
- AnimatedBuilder は複雑なウィジェットを作るのに使える、大きな関数の一部としてアニメーションを定義できる、利用する場合はウィジェットを作成して、ビルダー関数に渡すだけになります。

## addStatusListener

- Animation はまた AnimationStatus を提供する、AnimationStatusはどのように時間とともに進化するかどうか示します。
- AnimationStatus が変換するときには、アニメーションは全てのリスナーに通知します。（addStatusListenerで登録した全てのリスナーに）
- 大抵はアニメーションは非表示状態で開始されます。（非表示状態はそれらの範囲の開始を意味する。）
- アニメーションの進捗は 0 〜 1 で定義される。 0は非表示、アニメーションを開始したら 0 → 1、逆再生したときは 1 → 0 、 1 に到達したときはアニメーションの完了を表す。


# Animation Controller

- AnimationControler を利用して、アニメーションを制御する
- AnimationControler からリバースやカーブのアニメーションを作成ｄできる。リバースは逆再生、カーブは緩急を付けたアニメーション再生。

# Tween

- Tween を利用することで間を補間できる、切り替えることができる。
- ColorTweenなら色、 RectTweenなら四角の始まりと終わりを切り替えることができる。
- この補間は Tween クラスを継承し、lerp 関数を Override することで実装できる。