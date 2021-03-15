.. include:: header.rst

.. _api-user:

====================
User
====================

ユーザ情報を管理するAPI群です。

------------------------------------------------------------------------------

[POST] /user
====================

新しいカスタマー(エンドユーザ)を登録する。登録すると、

- 暗号資産入金用アドレスが発行される
- 当該カスタマーの各種レポートをPOSTできるようになる

-------------
Request Body
-------------

.. code-block::

  {
    "customer_id": "customer_123"
  }

- ``customer_id`` - ``String``: 新規作成するカスタマーID(エンドユーザID)


-------------
Response[200]
-------------

.. code-block::

  {
    "result": true,
    "customer_id": "customer_123",
    "licensee_id": "licensee_999",
    "nesta_address": "0xb8e59da60370a32dc7898ed0981387600af591d1",
    "btc_address": "3N9PHFbQuCsgNk9qW6Ynj18RxodBDamqX4g"
  }


- ``result`` - ``Boolean``: 実行結果
- ``customer_id`` - ``String``: 新規作成されたカスタマーID(エンドユーザID)
- ``licensee_id`` - ``String``: ライセンシーID
- ``nesta_address`` - ``String``: 当該ユーザのNESTA入金用アドレス
- ``btc_address`` - ``String``: 当該ユーザのBITCOIN入金用アドレス

------------------------------------------------------------------------------

[GET] /user_list
====================

ライセンシー自身が登録したユーザの一覧を取得する。

-------------
Request Body
-------------

.. code-block::

  Bodyなし


-------------
Response[200]
-------------

.. code-block::

  {
    "user_list": [
      "customer_123",
      "customer_456",
      "customer_789"
    ]
  }

- ``user_list`` - ``Array(String)``: 登録済みカスタマーIDのリスト

------------------------------------------------------------------------------

[GET] /user_info/{id}
=====================

登録済みカスタマー(エンドユーザ)の情報を参照する。

- ``id``: 参照するカスタマーID(エンドユーザID)

-------------
Request Body
-------------

.. code-block::

  Bodyなし


-------------
Response[200]
-------------

.. code-block::

  {
    "customer_id": "customer_123",
    "nesta_address": "0xb8e59da60370a32dc7898ed0981387600af591d1",
    "btc_address": "3N9PHFbQuCsgNk9qW6Ynj18RxodBDamqX4g"
  }

- ``customer_id`` - ``String``: カスタマーID(エンドユーザID)
- ``nesta_address`` - ``String``: 当該ユーザのNESTA入金用アドレス
- ``btc_address`` - ``String``: 当該ユーザのBITCOIN入金用アドレス



------------------------------------------------------------------------------

[POST] /user_delete
====================

既存のカスタマー(エンドユーザ)を削除する。
削除されたユーザについては、各種レポートをPOSTできなくなる。
削除されたカスタマーIDは再利用できない。

-------------
Request Body
-------------

.. code-block::

  {
    "customer_id": "customer_123"
  }

- ``customer_id`` - ``String``: 削除するカスタマーID(エンドユーザID)


-------------
Response[200]
-------------

.. code-block::

  {
    "result": true,
    "customer_id": "customer_123"
  }

- ``result`` - ``Boolean``: 実行結果
- ``customer_id`` - ``String``: 削除されたカスタマーID(エンドユーザID)
