.. include:: header.rst

.. _api-callback:

====================
Callback API
====================

入出金検知時にコールバックされるCallback APIについて記します。

------------------------------------------------------------------------------

入金Callback API
====================

Nesta Platformからライセンシーに入金を通知するCallback API


-------------
Method
-------------

``GET`` Method


-------------
Endpoint
-------------

ライセンシーが設定したURL

-------------
Query strings
-------------

.. code-block::

  deposit_id	8
  customer_id	nesta_1614818709
  currency	nesta
  amount	123000000000000000
  tx_hash	0xd4487be051a815c8c66105a4c79df533d40736e1d7957ba26b9ca04c278691b7
  created_at	2021-03-08 08:33:56
  created_at_timestamp	1615192436


- ``deposit_id`` - ``String``: 入金通知を識別するためのID (通知の重複を排除するため)
- ``customer_id`` - ``String``: アドレスが割当てられているカスタマー(エンドユーザ)ID
- ``currency`` - ``String``: 通貨名
- ``amount`` - ``String``: 金額
- ``tx_hash`` - ``String``: 当該トランザクションのハッシュ(ブロックチェーンにより呼び方が異なる場合がある)
- ``created_at`` - ``String``: 検知時刻のタイムスタンプ YYYY-MM-DD hh:mm:ss 形式
- ``created_at_timestamp`` - ``String``: 検知時刻のUnixTimestamp


-------------
Response[200]
-------------

.. code-block::

  Bodyなし

------------------------------------------------------------------------------

出金Callback API
====================

今後のアップデートで導入予定
