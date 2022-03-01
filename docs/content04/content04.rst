==============================================
Load Balancing
==============================================

Origin Pool​
==============================================

Load BalancingするエンドポイントをOrigin Server、その集合体をOrigin Poolと呼ぶ。

.. figure:: images/image-04-01.png
  :width: 1080
​
Origin Serverの種類

.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - 種類
      - 説明
    * - IP Address
      - パブリック/プライベートのIPアドレス
    * - DNS Name
      - パブリック/プライベートのFQDN
    * - Service Name
      - K8sまたはConsulのサービス名

サービスのポート番号を指定
ロードバランスアルゴリズムを指定

Load Balancing Control
==============================================

| Origin Poolは単一または複数Site内のサービス、各Siteの単一または複数サービスを指定できる。
| Load Balancerは単一または複数のOrigin Poolを指定できる。

.. figure:: images/image-04-02.png
  :width: 1080


Load Balancer Algorithm（LB）

.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - アルゴリズム
      - 概要
    * - Round Robin
      - 順番にエンドポイントを選択
    * - Least Active Request
      - 有効なリクエスト数が少ないエンドポイント
    * - Random
      - ランダムにエンドポイントを選択
    * - Source IP Stickiness
      - 送信元IPで宛先エンドポイントを維持
    * - Cookie Based Stickiness
      - Cookieを挿入し宛先エンドポイントを維持
    * - Ring Hash Policy
      - Consistent Hashing実装でEndpointの増減時に既存分散通信への影響を少なくする


Load Balancer Algorithm（OP）

.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - アルゴリズム
      - 概要
    * - Round Robin
      - 順番にエンドポイントを選択
    * - Least Active Request
      - 有効なリクエスト数が少ないエンドポイント
    * - Random
      - ランダムにエンドポイントを選択
    * - Ring Hash Policy
      - Consistent Hashing実装でEndpointの増減時に既存分散通信への影響を少なくする
    * - Load Balancer Override
      - LBのアルゴリズムに委任する。SourceIPやCookieでPersistenceする場合はこれを選択。


LB配置とVIP公開 – HTTP/HTTPS
==============================================

| LBは各SiteやVolterra REなどへ自由に配置。
| クライアントがアクセスするLBの仮想IPをVIPと呼ぶ。VIPはインターネット、またはイントラネットに公開される。
| 分散先のOrigin Poolを選択。ロードバランスアルゴリズムを指定

.. list-table::
    :header-rows: 1
    :stub-columns: 0

    * - VIP
      - 説明
    * - Advertise on Internet
      - VolterraのグローバルIPでインターネットへ公開。RE経由の通信。
    * - Advertise on Internet(Specified VIP)
      - 追加されたVolterraのグローバルIPでインターネットへ公開。RE経由の通信。
    * - Advertise Custom
      - ユーザのグローバルIPでインターネット、プライベートIPでイントラへ公開。

.. figure:: images/image-04-03.png
  :width: 1080
​






xxx
==============================================
​
.. figure:: images/image-04-03.png
  :width: 1080
​