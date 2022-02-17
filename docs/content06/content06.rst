==============================================
Service Policy
==============================================

HTTP LBのVIPに対するL7アクセス制御
==================

送信元の指定

+---------------+--------------------------------------------+
|送信元         |説明                                        |
+===============+============================================+
|IPv4 Prefix    |指定のネットワークアドレスからのアクセス    |
+---------------+--------------------------------------------+
|BGP ASN        |特定のAS番号からのアクセス                  |
+---------------+--------------------------------------------+
|Country List   |特定の国を指定（実態はグローバルIPアドレス）|
+---------------+--------------------------------------------+



宛先・リクエストの指定

+-------+----------------------+--------------------------------------------+
|宛先 　|　                    |説明                                        |
+=======+======================+============================================+
|Server |Domain Matcher        |ドメイン名を指定。完全一致または正規表現。  |
+-------+----------------------+--------------------------------------------+
|Request|HTTP Method           |メソッドとHTTPパス。Get, Put, Post等。      |
+-------+----------------------+--------------------------------------------+
|       |HTTP Query Parameters |クエリ文字列。?query=udp等。                |
+-------+----------------------+--------------------------------------------+
|       |HTTP Headers          |ヘッダ。User-Agent: Mozilla/4.0等。         |
+-------+----------------------+--------------------------------------------+
|       |Cookie Matcher        |Session-id=12345等                          |
+-------+----------------------+--------------------------------------------+
|       |Body Matcher          |Request Body String。                       |
+-------+----------------------+--------------------------------------------+


.. image:: ../content06/images/image-06-01.png
  :width: 640



Service PolicyでRuleを定義
==================

**Web App & API Protection** を選択

.. image:: ../content06/images/image-06-02.png
  :width: 640

____

**Manage** > **Service Policies** > **Service Policies** を選択

.. image:: ../content06/images/image-06-03.png
  :width: 320

____

\ ``Add service policy`` \ を押下

.. image:: ../content06/images/image-06-04.png
  :width: 480

____

設定内容の入力

.. image:: ../content06/images/image-06-05.png
  :width: 640

.. image:: ../content06/images/image-06-06.png
  :width: 640

____

\ ``Configure`` \ を押下

.. image:: ../content06/images/image-06-07.png
  :width: 640

____

\ ``Add Item`` \ を押下

.. image:: ../content06/images/image-06-08.png
  :width: 640

____

任意のNameを設定し、\ ``Configure`` \ を押下

.. image:: ../content06/images/image-06-09.png
  :width: 640

____

要件に応じてRuleを設定し、\ ``Apply`` \ を押下

.. image:: ../content06/images/image-06-10.png
  :width: 640

.. image:: ../content06/images/image-06-11.png
  :width: 640

.. image:: ../content06/images/image-06-12.png
  :width: 640

.. image:: ../content06/images/image-06-13.png
  :width: 640

.. image:: ../content06/images/image-06-14.png
  :width: 640

____

\ ``Add Item`` \ を押下

.. image:: ../content06/images/image-06-15.png
  :width: 640

____

\ ``Apply`` \ を押下

.. image:: ../content06/images/image-06-16.png
  :width: 640

____

\ ``Save and Exit`` \ を押下

.. image:: ../content06/images/image-06-17.png
  :width: 640

____

設定したService Policyが追加されていることを確認

.. image:: ../content06/images/image-06-18.png
  :width: 640













