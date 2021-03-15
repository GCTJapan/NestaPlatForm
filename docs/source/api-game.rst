.. include:: header.rst

.. _api-game:

====================
Reporting Games
====================

ゲームレポートに関するAPI

------------------------------------------------------------------------------

[POST] /game
====================

ゲームの結果を報告する。(ライセンス上の必須要件)

-------------
Request Body
-------------

.. code-block::

  {
    "customer_id": "customer_123",
    "session_id": "session123123",
    "log": "{ \n  \"format\":\"rg-1\",\n  \"licensee_id\": \"licensee_123\",\n  \"customer_id\": \"customer_456\",\n  \"start_time\": 1598508145,\n  \"end_time\":1598508745,\n  \"game_id\": \"game_123\",\n  \"session_id\":\"TY8W84YQS329EG2XMVLTUH4T\",\n  \"total_bet\":123.45,\n  \"total_payout\":101.99,\n  \"currency\": \"usd\",\n  \"game_details\": [\n     {\"bet\":10.0, \"payout\": 0, \"start_time\": 1598508150, \"description\": \"Bet 3 lines and  missed\" },\n     {\"bet\":10.0, \"payout\": 3.5, \"start_time\": 1598508151, \"description\": \"Bet 3 lines and  hit 1 line\" },\n     {\"bet\":10.0, \"payout\": 0, \"start_time\": 1598508153 , \"description\": \"Bet 3 lines and  missed\"}\n    ]}"
  }

- ``customer_id`` - ``String``: 当該ゲームのプレイヤーのカスタマーID(エンドユーザID)
- ``licensee_id`` - ``String``: ライセンシーID
- ``log`` - ``String(json)``: ゲームの詳細ログ。 :doc:`書式はこちらを参照</data-game>`


-------------
Response[200]
-------------

.. code-block::

  {
    "result": true,
    "customer_id": "customer_123",
    "session_id": "session12312345",
    "log_hash": "2426ada588ce1de6e18bec9793a6f4d4c175433ad634f93274fabef0a7188950aa85d87081a8972bd578e2997390e1dfbe2b4c719f6edddac4139bd6502ce420"
  }

- ``result`` - ``Boolean``: 実行結果
- ``customer_id`` - ``String``: 新規作成されたカスタマーID(エンドユーザID)
- ``session_id`` - ``String``: セッションID
- ``log_hash`` - ``String``: 算出されたログハッシュ(ブロックチェーンに保存される)

