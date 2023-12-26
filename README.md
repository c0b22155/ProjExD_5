# 吹き飛べ！！こうかとん！！！

## 実行環境の必要条件
* python >= 3.10
* pygame >= 2.1

## ゲームの概要
いわゆるボンバーマンのオマージュ。デフォルトで二人プレイにするのが特徴。長方形のマップがあり、等間隔に侵入できないブロックがある。特定のボタン（左SHIFTと右SHIFT）を押すと爆弾を設置することができ、十字の形に爆発する。

## ゲームの実装
### 共通基本機能
* 背景と破壊できないブロックが等間隔にあるマップの作成
*1Pキャラクターの作成：1PキャラクターはWASDで操作できるものとする。なめらかに動くのではなく、1マスずつ移動を行う。
*1Pキャラクターの移動機能：WASDに対応して、上下左右に移動を行う。


### 担当追加機能
* 2Pキャラクタ―の追加（担当：小松）：十字キーで操作できる二人目のキャラクターの追加。1Pキャラクターと性能的には同一。なめらかに動くのではなく、1マスずつ移動する。また死ぬ判定も作成する。

* 爆弾設置機能（担当：山根木）：爆発に関するクラスを作成する。（爆弾が爆発するエフェクトを生成する）爆弾設置から指定の時間が経過したのち、爆弾を中心として上下左右と中心に爆破エフェクトを発生させる。

* 爆弾、壁、プレイヤーの当たり判定（担当：若林）：爆弾の爆発によってマップに変更を加えるかどうかを判定する。変更する場合は変更する。judgement関数を用いて爆弾の周りの壁を判定しマップの改変を行う。

* 破壊可能な壁を設置する機能（担当：喜多村）：初期マップにて、プレイヤーが通行可能なマスに破壊可能な壁をランダムに配置する機能。

* 無敵機能（担当：高尾）：ゲーム中にキャラクターが一度だけ使用可能な機能。使用時間中は爆弾の判定を無効にする。


### ToDo
[  ]  勝敗判定機能
[  ] score

### メモ


### 参考
*https://www.youtube.com/watch?v=CTwmZ6h21dk 
*グループ内のイメージを確立するために利用した動画


プレイヤーの足元に爆弾を置き、爆発のエフェクトを発生させる機能

class Bomb(pg.sprite.Sprite）で爆弾の設置

class Explosion(pg.sprite.Sprite)で爆弾の四方に爆発が起こるようにする。
