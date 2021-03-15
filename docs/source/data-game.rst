
.. _data-game:

====================
Game Reports
====================

NestaPlatform APIを通じてレポートするゲームログのフォーマットを示す。

------------------------------------------------------------------------------

ライブストリーミング
====================

現在のライブストリーミングフォーマットの最新バージョンは ``ls-1`` である。

ls-1
-------------------

フォーマット
^^^^^^^^^^^^^^^^^^^^


.. code-block::

  { 
    "format":"ls-1",
    "licensee_id": "licensee_123",
    "customer_id": "customer_456",
    "start_time": 1598508145,
    "end_time":1598508745,
    "game_id": "game_123",
    "session_id":"TY8W84YQS329EG2XMVLTUH4T",
    "total_bet":123.45,
    "total_payout":101.99,
    "currency": "usd",
    "game_details": [
       {"bet":10.0, "payout": 0, "start_time": 1598508150, "description": "Bet 3 lines and  missed" },
       {"bet":10.0, "payout": 3.5, "start_time": 1598508151, "description": "Bet 3 lines and  hit 1 line" },
       {"bet":10.0, "payout": 0, "start_time": 1598508153 , "description": "Bet 3 lines and  missed"},
      ...,
      ]
  }



- ``format`` - ``String``: フォーマットのカテゴリとバージョン
- ``licensee_id`` - ``String``: ライセンシーID
- ``customer_id`` - ``String``: カスタマーID(エンドユーザID)
- ``start_time`` - ``Number``: セッション開始日時のUnixTimestamp
- ``end_time`` - ``Number``: セッション終了日時のUnixTimestamp
- ``session_id`` - ``String``: セッションID
- ``total_bet`` - ``Number``: 総ベット額
- ``total_payout`` - ``Number``: 総ペイアウト額
- ``currency`` - ``String``: ベットの通貨単位
- ``game_details`` - ``Array``: ベット&ペイアウトのログの可変長リスト

ベット&ペイアウト 

- ``bet`` - ``Number``: 1つのゲームのベット額
- ``pauout`` - ``Number``: 1つのゲームのペイアウト額
- ``start_time`` - ``Number``: ベット日時のUnixTimestamp
- ``description`` - ``String``: ゲーム結果の自由記述

------------------------------------------------------------------------------



R and G
====================

現在のライブストリーミングフォーマットの最新バージョンは ``rg-1`` である。

rg-1
-------------------

フォーマット
^^^^^^^^^^^^^^^^^^^^


.. code-block::

  { 
    "format":"rg-1",
    "licensee_id": "licensee_123",
    "customer_id": "customer_456",
    "start_time": 1598508145,
    "end_time":1598508745,
    "game_id": "game_123",
    "session_id":"TY8W84YQS329EG2XMVLTUH4T",
    "total_bet":123.45,
    "total_payout":101.99,
    "currency": "usd",
    "game_details": [
       {"bet":10.0, "payout": 0, "start_time": 1598508150, "description": "Bet 3 lines and  missed" },
       {"bet":10.0, "payout": 3.5, "start_time": 1598508151, "description": "Bet 3 lines and  hit 1 line" },
       {"bet":10.0, "payout": 0, "start_time": 1598508153 , "description": "Bet 3 lines and  missed"},
      ...,
      ]
  }



- ``format`` - ``String``: フォーマットのカテゴリとバージョン
- ``licensee_id`` - ``String``: ライセンシーID
- ``customer_id`` - ``String``: カスタマーID(エンドユーザID)
- ``start_time`` - ``Number``: セッション開始日時のUnixTimestamp
- ``end_time`` - ``Number``: セッション終了日時のUnixTimestamp
- ``session_id`` - ``String``: セッションID
- ``total_bet`` - ``Number``: 総ベット額
- ``total_payout`` - ``Number``: 総ペイアウト額
- ``currency`` - ``String``: ベットの通貨単位
- ``game_details`` - ``Array``: ベット&ペイアウトのログの可変長リスト

ベット&ペイアウト 

- ``bet`` - ``Number``: 1つのゲームのベット額
- ``pauout`` - ``Number``: 1つのゲームのペイアウト額
- ``start_time`` - ``Number``: ベット日時のUnixTimestamp
- ``description`` - ``String``: ゲーム結果の自由記述

------------------------------------------------------------------------------

スポーツベッティング
====================

現時点で未定義

sp-1
-------------------

フォーマット
^^^^^^^^^^^^^^^^^^^^


.. code-block::

  { 
  }

------------------------------------------------------------------------------


eゲーム
====================

現時点で未定義

sp-1
-------------------

フォーマット
^^^^^^^^^^^^^^^^^^^^


.. code-block::

  { 
  }



