# たぬえさ3を使用したﾀｽｶﾘﾏｽの自動化設定

## 事前準備
+ たぬえさ3のインストール
+ たぬえさをTwitch認証して連携
+ ~~TanuEsa3.exeが保存されているフォルダを確認してください(設定の途中でフォルダ内のファイルを操作します)
  フォルダ名は以下"TanuEsa3.x.x"と呼ぶ(xにはバージョンの数値が入ります)~~

## 使用環境
+ Windows10 , OBS27.1.1 , TanuEsa3.0.8のみ動作を確認

## 設定方法
+ 任意の設定でトリガーをひとつ作る<br>
  たぬえさ3にて、設定 > イベント設定 > チャット > テキスト を選択<br>
  トリガー一覧を追加 > 抽選箱一覧 > 抽選タグ一覧までが作られる
+ ~~TanuEsa3.x.x\settings\triggers.xmlファイルを別名保存する(後で差分を確認するのでテキストエディタなどで開いておいても良い)
  以下、このファイルをbefore.xmlと呼ぶ~~
+ オペレーション一覧を追加する
+ 作ったオペレーションに任意の画像を設定する(このとき設定した画像がﾀｽｶﾘﾏｽ)<br>
  設定する画像は他のトリガーで使用していないものにしてください<br>
  全ての設定が終わった後に別画像に差し替えるのは問題ありません
+ 位置・音量・遅延ボタンから位置設定を選択
+ 右側、中段にある削除ボタンを2回押す
+ 保存ボタンを押して位置編集を閉じる > 保存して閉じるボタンを押して位置等を閉じる > 赤色の保存ボタンを押してオペレーションを保存する
+ TanuEsa3.x.x\settings\triggers.xmlファイルをテキストエディタなどで開く
  ~~以下、このとき開くファイルをtriggers.xmlと呼ぶ~~<br>
※ここまでの設定はテキストに限らずチャネポ報酬などでも問題ない筈

+ ~~before.xmlとtriggers.xmlの差分を表示する
  サクラエディタのDIFF差分やWinMergeなど、差分が分かれば何でも良い~~
+ ~~差分箇所内のPossタグを削除する~~
+ ctrl + F キーで設定した画像の名前を検索する<br>
  ここで2件以上ヒットする場合はオペレーションの画像設定からやり直してください
+ ctrl + F キーで「\<poss>」を検索する<br>
  **メモ帳の場合、検索する方向は「上へ」を指定してください**
+ \<Poss>と書かれた行から</poss>と書かれた行までを削除する<br>
  \<Poss> , \</Poss> ごと消します
+ 削除した箇所に本リポジトリのtasukarimasu.xml内のコード全て(Possタグ)を貼り付ける
+ triggers.xmlを保存する
+ 一度たぬえさ3を終了し、再度たぬえさ3を開く
+ 設定したトリガーを発火、またはプレビューでチェック
+ 問題なければ設定した画像がﾀｽｶﾘﾏｽ


### 注意
> [!warning]
> 以下の点に注意してください

+ 基本的な大きさは50％で設定しています(幅(%)と高さ(%))
  大きめの画像を用意しておけばすぐにﾀｽｶﾘﾏｽ
+ ﾀｽｶﾘﾏｽの設定をした後はオペレーション一覧の位置・音量・遅延タブから位置設定が開けなくなります
  おそらく設定数が多いためメモリが足りず、たぬえさが強制終了します
  他のトリガーには影響は無い筈です
+ 細かい調整(座標や表示時間)を行う場合はPossタグ内の数値やbool値を直接操作する必要があります
  TE3PosOptionタグをある程度切り取り、別の場所に退避させておけば
  たぬえさの既存GUI(位置設定)を使用できます
  目安として"最初～カモメのダンス後の回転" , "セカンド出塁～2点獲得" , "最後のｱｻﾞﾏｽ～ラスト"
  それぞれの間に以下コメントを残している
  "second start" , "2point get"
  いずれか1つ分を残す程度であればたぬえさは強制終了しない筈です
  ただし他のトリガーの設定を行いたぬえさが自動でファイル更新を行うときはコメントが消える

