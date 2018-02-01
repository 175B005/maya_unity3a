# maya_unity3
maya unity 連携機能３（アニメーション　リグ・キャラクタアニメーション編 *人型*）

 1. 前回の復習。アニメーションを簡単につけるやり方と、Ｕｎｉｔｙに持っていく方法をやりました。  
今回はその続きになります。リグをつけて、ささっと人間を動かしていきましょう。
 1. はじめにunityとmayaをコラボ状態で起動しておきます。（[一回目ページ1..9](https://github.com/175B005/maya_unity)）
 1. モデルがない人のために、ここではunity assetを使っていきます。（Unityちゃんモデル）
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction.jpg)![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction3.jpg)
 1. unity でアセットをインポートします。（インポートするのはモデルのみでおｋ）  
 1. モデルデータをシーンに出していきます。
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction1.jpg)
 1. 右クリック< Export より、編集用のフォルダ（前回ページ参照）にパッケージ化します。
 1. maya側に行き、unityメニューのimportを選択。今のパッケージしたモデルを読み込む。
 1. maya上にunityちゃんがきたら、初期設定完了です。
---

### ここから本番 ![](http://unity-chan.com/images/imageUnityOk02.png)

 1. 左上メニューバーの「モデリング」を「リギング」に変更（ショートカットが使いやすい）  
色がついていない！と思った方は、上部メニューのサッカーボールマークをONにすると、色が反映されます。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction2.jpg)
 1. モデルを全選択。→　上部メニューの「スケルトン」<下の「クイックリグ」を選択して、  
出てきたメニューの「自動リグ」を選択。  
すると、あら不思議、勝手にモデルにリグが付きます  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction4.jpg)
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction5.jpg)
※エラーの場合の対処法→リンク
 1. ですが、モデルによってはこのUnityちゃんのように、髪の毛が多いキャラが  
いるので、それまで、勝手に認識して、リグを入れてしまいます。
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction7.jpg)
 1. なので、少しだけ調節してしきたいと思います。
 1. まず、このコントロールリグは要らないので、上書きで、ガイドを作ります。  
クイックリグ< 段階的に< ガイド< ガイドを作成
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx1.jpg)
 1. このガイドは骨を入れる関節部分のガイドということなので、  
これがしっかりしていないと、リグが入りません。位置を調整して、しっかりとモデルの関節の位置にしましょう。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx2.jpg)  
 1. 片方を調節してしまえば、反転させることもできますよ。
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx3.jpg)
 1. 次はスケルトンとコントロールリグをつけます。  
段階的に< スケルトンとリグの作成<▼のどっちも作るを選択< 作成  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx4.jpg)
 1. ..さっきとほぼ同じのがでてきました。先ほどの「自動リグ」というのは、  
 - このガイド、スケルトン、スキニングを全部やってくれる、ワンクリック機能だったのです。  
      - ガイド：キャラクターの関節位置を表すガイド。後の動きなどには一切関係しなくなる。後で消してもおｋ.  
      - スケルトン：骨。リグ。この形状によって、扱いやすいHumanoidや、Genericなどが存在する。(unityでのAvatarになる)    
      - スキニング：リグとモデルを選択し行う。モデルとリグを紐付けし、リグを動かすことで、モデルを同時に動かす。    

### では、アニメーションをつけていきたいと思います。

1. まず先の手順で、スキニングがエラーなく終わっていれば、  
コントロールリグを動かすと、モデルが動いていることがわかります。  
1. 確認できたら、初期の位置まで戻して、前回ページ同様に、  
アニメーションのタイマを１フレームに設定。  
このとき、1フレーム毎にモデルのリグを全選択して、キー値設定をします。  
これをしないと、編集した内容がパーになります。。。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx5.jpg)
1. 次に二個目。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx6.jpg)
1. 最後！  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx7.jpg)
1. アニメーションを複数作ることを考えて、今回はレイヤ分けをしておきたいと思います。  
右メニュー< レイヤエディタ< アニメーション< 今編集していたリグを全選択。< 「レイヤ」< 選択項目から作成  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx9.jpg)
1. ではこれをリグに焼きこんで、覚えさせます。  
（このままだと動きを作っただけで、モデルのリグには何の影響も出ません。）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx8.jpg)
1. 書き出しをしていきます。（FBX形式）  
→  手順通りにこのオブジェクトしか作っていない。0000までカット  
→  この他にもオブジェクトがある。失敗した。不安。な方。このまま。  
1. まずアウトライナを開き、選択するオブジェクトを確認。  
上部メニュー< ウィンドウ< アウトライナ  
(この機能は構造確認しながら選択などできるので便利。)  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx10.jpg)
1. では必要なものを選択していきます。（リグ、リファレンス、モデル）  
選択項目の書き出しもあるのですが、いろいろくっつかないものがあるので今回は使いません。私わからない。。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx11.jpg)
1. 選択したもの以外を反転で選択。（なければいい）Ctrl + H　で非表示にします。  
（このアウトライナから、薄くなっているものを選択してShift + Hを押すと表示できます。）
1. 表示しているものが、編集していたモデルとリグだけになったら再度全選択して、  
ファイル< すべてを書き出し選択  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx12.jpg)
1. 書き出しのメニューが出てくるので、規定のものではなく、プリセットの編集から編集していきます。  
チェックする項目：アニメーション/アニメーションベイク処理/開始終了ステップ、全てをリサンプル/  
変形したモデル/スキン、ブレンドシェイプ/コンストレイト、スケルトン定義/組み込みメディア  
にチェックをいれて、プリセットを保存してください。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx13.jpg)
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx14.jpg)
1. メニューを保存して閉じたら、「全て書き出し」を選択
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx15.jpg)
1. はい、書き出し（場所はどこでもいいです。）  
ここでもプリセットの編集でこなってもいいですが、さっきの設定が残っているなら、それでおｋです。  
設定内容はさっきと同じです。
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx16.jpg)
1. unity側で読み込みます。Asset < ImportNewAsset < さっきの書き出したファイルを選択、  
（というか、ファイルのドラッグ＆ドロップでimportできるのでそれでも別にいいです。）
1. なんかポーズしてて、inspectorにアニメーションが入っていればおｋ。
1. 前ページを参考にアニメーションの設定をしたら、後は実行してください。
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx17.jpg)
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx18.jpg)
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx19.jpg)
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx20.jpg)


 [前ページ](https://github.com/175B005/maya_unity2)| [次ページ](https://github.com/175B005/maya_unity4)|[目次](https://github.com/175B005/maya_unity_index)
