# 2020/01/26 Introduction to animations

# Introduction to animations

- Flutter のアニメーションは簡単に埋め込むことができるようになっている。
- 多くのウィジェット、特にマテリアルウィジェットはそのテーマで標準のエフェクトが定義されている。
- その他にも独自のエフェクトを作成することは可能になっています。

# Animation types

- アニメーションタイプは`Tween animation`と`Physics-based animation`の２つの種類がある。

## Tween animation

- 短くて、開始と停止が決まっているアニメーションを定義する
- フレームワークが開始から停止のフレームワークの速度や遷移を計算してくれる。

## Physics-based animation

- 現実世界に似るような動きをモデル化されるフレームワークです。
- 例えばバレーボールのトスのアニメーションなど（おそらく重力などのシミュレーションができる？）

# Common animation patterns

- 一般的に使用されるアニメーションパターンの一部をリストし、詳細を確認できる場所を示します。

## Animated list or grid

- リストに追加と削除、アニメーション( [animated-list](https://flutter.dev/docs/catalog/samples/animated-list) )

## Shared element transition
- 画像などのアイテムをさわって、次のページに遷移するときのアニメーション
- これらのアニメーションは Navigator などで実装されている。
- Hero というアニメーションもある。


## Staggered animation

- 段階的なアニメーション、何段か図形を定義して作成するアニメーション？