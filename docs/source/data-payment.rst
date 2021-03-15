
.. _data-payment:

====================
Deposits/Withdrawals
====================

NestaPlatform APIを通じてレポートする入出金ログのフォーマットを示す。

------------------------------------------------------------------------------


Deposit
===================

現在のDepositフォーマットの最新バージョンは ``dp-1`` である。

dp-1
-------------------

フォーマット
^^^^^^^^^^^^^^^^^^^^


.. code-block::

  { 
    "format":"dp-1",
    "licensee_id": "licensee_123",
    "customer_id": "customer_456",
    "transaction_time": 1598508145,
    "transaction_id":"TY8W84YQS329EG2XMVLTUH4T",
    "amount":123.45,
    "currency": "usd",
    "method": "credit card"
  }


- ``format`` - ``String``: フォーマットのカテゴリとバージョン
- ``licensee_id`` - ``String``: ライセンシーID
- ``customer_id`` - ``String``: カスタマーID(エンドユーザID)
- ``transaction_time`` - ``Number``: 入金日時のUnixTimestamp
- ``transaction_id`` - ``String``: トランザクション識別用のユニークID
- ``amount`` - ``Number``: 金額
- ``currency`` - ``String``: 通貨名, 通貨シンボル
- ``method`` - ``String``: 入金手段。以下の「対応手段」の中から1つ。


対応入金手段
^^^^^^^^^^^^^^^^^^^^

"credit card": クレジットカード
"crypto currency" : 暗号資産の送金
"payment agency" : 決済代行業者
"bank transfer" : 銀行振込
"cash" : 現金

------------------------------------------------------------------------------


Withdrawal
===================

現在のDepositフォーマットの最新バージョンは ``wd-1`` である。

wd-1
-------------------

フォーマット
^^^^^^^^^^^^^^^^^^^^

.. code-block::

  {
    "format":"wd-1",
    "licensee_id": "licensee_123",
    "customer_id": "customer_456",
    "transaction_time": 1598508145,
    "transaction_id":"TY8W84YQS329EG2XMVLTUH4T",
    "amount":123.45,
    "currency": "usd",
    "method": "credit card"
  }


- ``format`` - ``String``: フォーマットのカテゴリとバージョン
- ``licensee_id`` - ``String``: ライセンシーID
- ``customer_id`` - ``String``: カスタマーID(エンドユーザID)
- ``transaction_time`` - ``Number``: 出金日時のUnixTimestamp
- ``transaction_id`` - ``String``: トランザクション識別用のユニークID
- ``amount`` - ``Number``: 金額
- ``currency`` - ``String``: 通貨名, 通貨シンボル
- ``method`` - ``String``: 入金手段。以下の「対応手段」の中から1つ。


対応出金手段
^^^^^^^^^^^^^^^^^^^^

"crypto currency" : 暗号資産の送金
"bank transfer" : 銀行振込
"goods purchase" : 商品購入
"service purchase" : サービス購入 



