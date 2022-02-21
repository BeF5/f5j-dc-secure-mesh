==============================================
DDoS
==============================================

HTTP LBのVIPへのDDoS攻撃を防御。


.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - 手法
      - 説明
    * - Javascript Challenge
      - JavaScriptによる問い合わせを送り、ブラウザかどうかを識別
    * - Captcha Challenge  
      - 応答者がボットではなく人であることを確認
    * - Policy Based Challenge 
      - MLでユーザの挙動を学習しBlock/Javascript/Captchaチャレンジを適用
    * - Rate Limiting
      - | HTTP LB VIPに対するレートリミット。
        | 送信元の識別子：IP Prefix、ASN、HTTP Cookie、HTTP Header Name等。
        | レートリミットの対象：特定のHTTPメソッド、Domain、パス、ヘッダー等。
    * - Client Blocking
      - 特定の送信元のIP PrefixまたはASNをブロック。

      
.. image:: ../content08/images/image-08-01.png
  :width: 640


Javascript Challenge
==================

JavaScriptによる問い合わせを送り、ブラウザーかどうかを識別。
ブラウザと識別された場合、レスポンスにCookieを挿入して、次回以降のリクエストでは問い合わせない。

.. image:: ../content08/images/image-08-02.png
  :width: 1080


Captcha Challenge
==================

指定したイメージを選択させ、クライアントがBotではなく人であることを確認。

.. image:: ../content08/images/image-08-03.png
  :width: 1080


Policy Based Challenge - ML
==================

ML（機械学習）でMaliciousユーザを脅威3レベルに分類。各レベル毎にアクションを指定。

.. image:: ../content08/images/image-08-04.png
  :width: 1080

____

脅威レベル毎のアクションを変更。

.. image:: ../content08/images/image-08-05.png
  :width: 1080

____

ユーザ識別子の変更。デフォルトではMaliciousユーザ=クライアントIPアドレス。

.. image:: ../content08/images/image-08-06.png
  :width: 1080

____

MLを有効にする。

.. image:: ../content08/images/image-08-07.png
  :width: 1080



Maliciousユーザ検知 - ML
==================

.. image:: ../content08/images/image-08-08.png
  :width: 1080


Policy Based Challenge - Static
==================

MLではなく送信元や宛先指定でアクションを決める。

.. image:: ../content08/images/image-08-09.png
  :width: 1080


Rate Limiting
==================

HTTP LB VIPに対するレートリミット。<br>
送信元の識別子：IP Prefix、ASN、HTTP Cookie、HTTP Header Name等。
レートリミットの対象：特定のHTTPメソッド、Domain、パス、ヘッダー等。

.. image:: ../content08/images/image-08-10.png
  :width: 1080

____

送信元の識別子を選択。

.. image:: ../content08/images/image-08-11.png
  :width: 1080

____

レートリミットの値と対象を選択。

.. image:: ../content08/images/image-08-12.png
  :width: 1080

____

レートリミットの対象を選択。

.. image:: ../content08/images/image-08-13.png
  :width: 1080


Client Blocking
==================

特定の送信元のIP PrefixまたはASNをブロック。

.. image:: ../content08/images/image-08-14.png
  :width: 1080


