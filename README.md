# Kadecot-Pepper Sample
[Kadecot](http://kadecot.net) access sample for [Choregraphe](http://www.softbank.jp/robot/developer/tools/sdk/)  (Softbank's Pepper development environment)

![User Interface](https://raw.githubusercontent.com/SonyCSL/KadecotPepperSample/master/kadecot-choregraphe.png)

[Pepper](http://www.softbank.jp/robot/)からスマートメーターや分電盤から提供される電力データにアクセスするためのソースコードです。
ソニーCSLのAndroidアプリ「[Kadecot](http://kadecot.net/)」に加え、「[生活デザインアプリコンテスト](http://lifedesign-app.org/)」のサポートイベントにて配布される、「Kadecot Support Plug-in」を同一端末内に入れて動作させ、かつ「開発者モード」にチェックを入れる必要があります(通信は[JSONP API](http://kadecot.net/blog/2750/)を使って行います)。

このアーカイブに含まれるのは、getPowerとgetPowerHistoryの二つのprocedureへのアクセスをおこなうChoregrapheのプロジェクトですが、入力となる文字列を変更することで、任意のKadecotのプロパティを取得することができると思います．（上記の図ではPowerNowとPowerHistoryへのアクセスと書いてありますが、getPowerとgetPowerHistoryにSupport Plug-inの仕様が変更になっています）
pythonのrequestsパッケージではなくurllib2パッケージを使用しています．

[Kadecot HTTP Path Edit]ボックスと[Kadecot HTTP GET]ボックスが同梱したボックスライブラリ(kadecot.cbl)にあります．
[Kadecot HTTP Path Edit]ボックスは，KadecotのHTTP GETアクセス時のパスを出力します．
デフォルトでは，procedureはPowerNowで，電力瞬時値を獲得するためのパスを出力します．
procedureをPowerHistoryにすると，電力の履歴を獲得するためのパスを出力します．

出力したパスを[Kadecot HTTP GET]ボックスに渡すことで，Kadecotにアクセスします．
[Kadecot HTTP GET]ボックスの出力はKadecotからのjsonデータを文字列にしたものです．
