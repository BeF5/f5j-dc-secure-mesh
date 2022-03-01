==============================================
Network Firewall CE Site
==============================================

|Network Policy​
|Forward Proxy Policy​
|Fast ACL

Virtual Network​
==============================================

Network Firewallは３つのタイプをサポート。

.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - タイプ
      - レベル
      - 概要
    * - Network Policy
      - L3-4
      - 送信元・宛先を定義しIngress/Egressでルールを作成。セッションベースのため戻りのルールは不要。
    * - Fast ACL
      - L3-4
      - CEまたはREに配置したVIP（LB）宛の通信を抑制。DDOS対策。TCP Flag等のL4 Policer。
    * - Forward Proxy Policy
      - L7
      - 送信元のIP Prefixと宛先のTLS Domain、HTTP URL、IP Prefix、BGP ASNを制限。

.. figure:: images/image-02-04.png
  :width: 1080

オブジェクトの関係​

Network Policy
==============================================

.. figure:: images/image-02-05.png
  :width: 1080

.. figure:: images/image-02-06.png
  :width: 1080
​
.. figure:: images/image-02-07.png
  :width: 1080

Network Policy – Label制御
==============================================

Network Interfaceにアサインしたラベルを用いアクセス制御できる。

.. figure:: images/image-02-08.png
  :width: 1080
​
Network Policyでラベルを選択

.. figure:: images/image-02-09.png
  :width: 1080
​
Fast ACL
==============================================

Fast ACLを作成。​

.. figure:: images/image-02-10.png
  :width: 1080

Policerを作成しProtocl PolicerまたはFast ACLへ定義。

.. figure:: images/image-02-11.png
  :width: 1080

Protocl Policerを作成しFast ACLへ定義。

.. figure:: images/image-02-12.png
  :width: 1080


Forward Proxy Policy
==============================================

Network ConnectorでForward ProxyとSNATを有効にする。

.. figure:: images/image-02-13.png
  :width: 1080

Forward Proxy Policyを作成。

.. figure:: images/image-02-14.png
  :width: 1080

.. figure:: images/image-02-15.png
  :width: 1080

最後のAll PermitのPolicyを作成。事前に作成したNetwork FirewallにPolicyを割り当て。

.. figure:: images/image-02-16.png
  :width: 1080
