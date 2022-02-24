==============================================
Network CE Site
==============================================
    Site Interface​
    Virtual Network​
    Network Connector​
    Fleet​
    ローカルクライアントのNode冗長​
    Routing BGP​
    BGPによるルート冗長​
    Static Route​
    Site Mesh Group

Network
==============================================

Networkを構成する要素。​


.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - 要素
      - 概要
    * - Interface
      - SiteのInside（LAN）、Outside（Internet）のIPアドレス、DHCPサーバ、DNSの指定等。
    * - Virtual Network
      - Global Network（オーバーレイネットワーク）。Site-to-Site接続等で使用。
    * - Network Connector
      - SiteのInside Local NetworkとGlobal Network等を接続。SNATやForward Proxyの有無を設定。
    * - Fleet
      - 上記要素をSiteへ定義するパラメータの集合体。Fleetのラベルを発行しSiteへ付ける。
    * - BGP
      - SiteのInside/Outsideアンダーレイで接続するBGP Peer
    * - Static Routing
      - SiteのInside/OutsideアンダーレイでStatic Routingで接続
    * - Site Mesh Group
      - Site間でフルメッシュまたはハブアンドスポークでIPSec接続すること。Volterra REを経由しない通信。

.. figure:: images/image-01-01.png
  :width: 1080

オブジェクトの関係図

Site Interface
==============================================

CE Siteのインタフェース設定 – Inside Interface
※Outside Interfaceの基本設定はSite構築時に作成済。

.. image:: images/image-01-02.png
  :width: 1080

.. image:: images/image-01-03.png
  :width: 1080

CE Siteのインタフェース設定 – Outside Interface
OutsideインタフェースでBGP Peerを張る場合に設定

.. image:: images/image-01-04.png
  :width: 1080

Virtual Network
==============================================

Site間でLAN-to-LAN通信をしたり、Siteからインターネットへアクセスするためのオーバーレイネットワーク。

.. image:: images/image-01-05.png
  :width: 1080


Network Connector
==============================================

Site間でLAN-to-LAN接続するために、SiteのInsideとVirtual Networkをコネクト。

.. image:: images/image-01-06.png
  :width: 1080

SiteのInsideとインターネット接続。

.. image:: images/image-01-07.png
  :width: 1080

Fleet
==============================================

作成したInterfaceとNetwork Connector（Virtual Network指定済み）をSiteへ設定。

.. image:: images/image-01-08.png
  :width: 1080

.. image:: images/image-01-09.png
  :width: 1080

作成したFleetをSiteへ定義（Siteへ設定が反映される）

.. image:: images/image-01-10.png
  :width: 1080

ローカルクライアントのNode冗長
==============================================
ローカルクライアントからのアクセスはデフォルトGWの冗長で切り替わる


.. image:: images/image-01-11.png
  :width: 1080


aaa
==============================================

.. image:: images/image-01-01.png
  :width: 1080

