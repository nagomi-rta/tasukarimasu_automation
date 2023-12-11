# tasukarimasu_automation
## たぬえさ3を使用したﾀｽｶﾘﾏｽの自動化設定ファイルです

事前準備<br>
・たぬえさ3のインストール<br>
・たぬえさをTwitch認証して連携<br>
・TanuEsa3.exeが保存されているフォルダを確認してください(設定の途中でフォルダ内のファイルを操作します)<br>
  フォルダ名は以下"TanuEsa3.x.x"とする(xにはバージョンの数値が入ります)<br>

使用環境<br>
・Windows10 , OBS27.1.1 , TanuEsa3.0.8のみ動作を確認<br>

設定方法<br>
・たぬえさ3にて、設定 > イベント設定 > チャット > テキスト を選択<br>
・トリガー一覧 > 抽選箱一覧 > 抽選タグ一覧まで、任意の設定で作る<br>
・TanuEsa3.x.x\settings\triggers.xmlファイルを別名保存する(後で差分を確認するのでテキストエディタなどで開いておいても良い)<br>
  以下、このファイルをbefore.xmlと呼ぶ<br>
・オペレーション一覧に表示画像のタグを作る<br>
・作ったタグに任意の画像を設定する(このとき設定した画像がﾀｽｶﾘﾏｽ)<br>
・位置・音量・遅延タブの設定は一切触らないこと<br>
・TanuEsa3.x.x\settings\triggers.xmlファイルをテキストエディタなどで開く<br>
  以下、このとき開くファイルをtriggers.xmlと呼ぶ<br><br>
※ここまでの設定はテキストに限らずチャネポ報酬などでも問題ない筈<br>

・before.xmlとtriggers.xmlの差分を表示する<br>
  サクラエディタのDIFF差分やWinMergeなど、差分が分かれば何でも良い<br>
・差分箇所内のPossタグを削除する<br>
・削除した箇所に本リポジトリのtasukarimasu.xml内のコード全て(Possタグ)を貼り付ける<br>
・triggers.xmlを保存する<br>
・一度たぬえさ3を終了し、再度たぬえさ3を開く<br>
・設定したトリガーを発火、またはプレビューでチェック<br>
・問題なければ設定した画像がﾀｽｶﾘﾏｽ<br>



注意<br>
・基本的な大きさは50％で設定しています(幅(%)と高さ(%))<br>
  大きめの画像を用意しておけばすぐにﾀｽｶﾘﾏｽ<br>
・ﾀｽｶﾘﾏｽの設定をした後はオペレーション一覧の位置・音量・遅延タブから位置設定が開けなくなります<br>
  おそらく設定数が多いためメモリが足りず、たぬえさが強制終了します<br>
  他のトリガーには影響は無い筈です<br>
・細かい調整(座標や表示時間)を行う場合はPossタグ内の数値やbool値を直接操作する必要があります<br>
  TE3PosOptionタグをある程度切り取り、別の場所に退避させておけば<br>
  たぬえさの既存GUI(位置設定)を使用できます<br>
  目安として"最初～カモメのダンス後の回転" , "セカンド出塁～2点獲得" , "最後のｱｻﾞﾏｽ～ラスト"<br>
  いずれか1つ分を残す程度であればたぬえさは強制終了しない筈です<br>
