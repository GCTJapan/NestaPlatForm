.. include:: header.rst

.. _api-payment:

====================
Deposit/Withdrawals
====================

入出金に関するAPI

------------------------------------------------------------------------------

[POST] /transfer
====================

入金または出金を報告する。(ライセンス上の必須要件)

-------------
Request Body
-------------

.. code-block::

  {
    "customer_id": "abccasion_1234",
    "transaction_id": "f5RCkTRQRD5B4ATKpmYJUbeQK8WmsGVk",
    "log": "{ \n  \"format\":\"dp-1\",\n  \"licensee_id\": \"licensee_123\",\n  \"customer_id\": \"customer_456\",\n  \"transaction_time\": 1598508145,\n  \"transaction_id\":\"TY8W84YQS329EG2XMVLTUH4T\",\n  \"amount\":123.45,\n  \"currency\": \"usd\",\n  \"method\": \"credit card\"\n}"
  }

- ``customer_id`` - ``String``: 当該ユーザのカスタマーID(エンドユーザID)
- ``licensee_id`` - ``String``: ライセンシーID
- ``log`` - ``String(json)``: 入出金の詳細ログ。 :doc:`書式はこちらを参照</data-payment>`


-------------
Response[200]
-------------

.. code-block::


  {
    "result": true,
    "customer_id": "customer_123",
    "transaction_id": "f5RCkTRQRD5B4ATKpmYJUbeQK8WmsGVk",
    "log_hash": "bdc3f11399147b4d17896b71d8f4a42568275687dfe8704af8235fad1b75b9093ffa197bbf5fc690429cb8e39b90b9a26740e1ad3fe435f1157e98be94005724"
  }

- ``result`` - ``Boolean``: 実行結果
- ``customer_id`` - ``String``: 新規作成されたカスタマーID(エンドユーザID)
- ``session_id`` - ``String``: セッションID
- ``log_hash`` - ``String``: 算出されたログハッシュ(ブロックチェーンに保存される)

------------------------------------------------------------------------------

[POST] /withdraw
====================

NestaPlatformからユーザへの暗号資産の送金をリクエストする。

-------------
Request Body
-------------

.. code-block::

  {
    "customer_id": "abccasino_1234",
    "currency": "btc",
    "amount": 1.245,
    "to_address": "3PXXo2Dro5HwNMxTv9V7qmWrZjHpPhL1F3"
  }

- ``customer_id`` - ``String``: 当該ユーザのカスタマーID(エンドユーザID)
- ``currency`` - ``String``: 通貨名, 通貨シンボル
- ``amount`` - ``Number``: 金額
- ``to_address`` - ``String``: 送金先アドレス


-------------
Response[200]
-------------

.. code-block::

  {
    "result": true,
    "customer_id": "hogehoge1234456",
    "currency": "btc",
    "amount": 1.245,
    "to_address": "3PXXo2Dro5HwNMxTv9V7qmWrZjHpPhL1F3",
    "withdraw_id": "15"
  }

- ``result`` - ``Boolean``: 実行結果
- ``customer_id`` - ``String``: 新規作成されたカスタマーID(エンドユーザID)
- ``currency`` - ``String``: 通貨名, 通貨シンボル
- ``amount`` - ``Number``: 金額
- ``to_address`` - ``String``: 送金先アドレス
- ``withdraw_id`` - ``String``: 識別用のID

