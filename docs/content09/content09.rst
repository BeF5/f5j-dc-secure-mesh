==============================================
WAF & Bot Protection
==============================================

WAF
==============================================

WAF：Webアプリケーションに対するシグネチャベースの攻撃検知。

.. image:: ../content09/images/image-09-01.png
  :width: 480

WAF用語

.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - 用語
      - 説明
    * - Attack Type
      - 攻撃または攻撃のクラスを識別するルールまたはパターン。複数の攻撃シグネチャを持つ。
    * - Attack Signature
      - 攻撃シーケンスを識別するルールまたはパターン。HTTPリクエストとレスポンスに適用。
    * - Accuracy Level
      - 検知するシグネチャレベルを指定。Lowレベルまで指定すると誤検知が多くなる。  
    * - False Positive Suppression
      - 機械学習により誤検知を抑制する機能。
    * - Threat Campaign Detection
      - 新たな脅威に対し即座にシグネチャを提供。
    * - Violation Detection
      - HTTPヘッダーやJSONデータなど標準化された形式から逸脱したものを検知。


Bot Protection & Defense
==============================================

Bot Protection：BotやWebツール、ブラウザ等の不正な振る舞いを検知。

.. image:: ../content09/images/image-09-02.png
  :width: 480
  
BOTの種類

.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - 種類
      - 説明
    * - Good Bot
      - 既知の検索エンジンの振る舞いやシグネチャ
    * - Suspicious Bot
      - | 悪意のないツールやBotの動作を示すもの。以下はSuspicious Botに分類される。
        | Tools - Site crawlers, monitors, spiders, web downloaders.
        | Bots - Social media agents, Search Bot。
    * - Malicious Bot
      - Botシグネチャ、ブラウザ検証テスト、脆弱性スキャナー等で検知したもの。  

____

Bot Defense：JSまたはSDKによりデータ収集、機械学習でリクエストが悪意のあるBotか判断。

.. image:: ../content09/images/image-09-03.png
  :width: 480


App Firewall
==============================================

WAF、Bot Protection用にApp Firewallを作成。

.. image:: ../content09/images/image-09-04.png
  :width: 480

____

.. image:: ../content09/images/image-09-05.png
  :width: 1080


App Firewall – WAF Custom
==============================================

.. image:: ../content09/images/image-09-06.png
  :width: 800


App Firewall – Bot Protection
==============================================

.. image:: ../content09/images/image-09-07.png
  :width: 800


HTTP LoadBalancer
==============================================

App FirewallをHTTP LBで指定。

.. image:: ../content09/images/image-09-08.png
  :width: 800


WAF イベント検知
==============================================

.. image:: ../content09/images/image-09-09.png
  :width: 800


Bot Protection イベント検知
==============================================

.. image:: ../content09/images/image-09-10.png
  :width: 800


Bot Defense
==============================================

Bot DefenseをLBで定義。

.. image:: ../content09/images/image-09-11.png
  :width: 480

____

.. image:: ../content09/images/image-09-12.png
  :width: 880

____

.. image:: ../content09/images/image-09-13.png
  :width: 800


Bot Defense イベント検知
==============================================

.. image:: ../content09/images/image-09-14.png
  :width: 800

____

.. image:: ../content09/images/image-09-15.png
  :width: 800





 
  
  
  
  
  

