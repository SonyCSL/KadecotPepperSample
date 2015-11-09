# Kadecot-PepperSample
Kadecot access sample for Choregraphe (Softbank's Pepper development environment)

Pepperからスマートメーターや分電盤から提供される電力データにアクセスするためのソースコードです。
ソニーCSLのAndroidアプリ「Kadecot」に加え、「生活デザインアプリコンテスト」のサポートイベントにて配布される、「Kadecot Support Plug-in」を同一端末内に入れて動作させ、かつ「開発者モード」にチェックを入れる必要があります(通信はJSONP APIを使って行います)。

このアーカイブに含まれるのは、PowerNowとPowerHistoryの二つのprocedureへのアクセスをおこなうChoregrapheのプロジェクトです．我々の開発環境ではpythonのrequestsパッケージがインポートできなかったため，urllib2パッケージに変えたものを使用しています．(おそらく，エミュレータかChoregraphe自体のバージョン(2.0.5)が古いことが原因だと思います)

[Kadecot HTTP Path Edit]ボックスと[Kadecot HTTP GET]ボックスが同梱したボックスライブラリ(kadecot.cbl)にあります．
[Kadecot HTTP Path Edit]ボックスは，KadecotのHTTP GETアクセス時のパスを出力します．
デフォルトでは，procedureはPowerNowで，電力瞬時値を獲得するためのパスを出力します．
procedureをPowerHistoryにすると，電力の履歴を獲得するためのパスを出力します．

出力したパスを[Kadecot HTTP GET]ボックスに渡すことで，Kadecotにアクセスします．
[Kadecot HTTP GET]ボックスの出力はKadecotからのjsonデータを文字列にしたものです．
