.. include:: header.rst

.. _api-utils:

====================
Utility
====================

その他のAPI

------------------------------------------------------------------------------

[POST] /exchange_rate/{timestamp}
=================================

暗号通貨のレートを参照する。指定されたTimestampより以前の情報の中で最新のレートを返す。

- ``timestamp``: 指定日時(UnixTimestamp) 

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
    "btc_usd": 60228.6417,
    "eth_usd": 1887.14,
    "nesta_usd": 5.1,
    "timestamp": 1615778747
  }

- ``btc_usd`` - ``Number``: BTC-USDレート
- ``eth_usd`` - ``Number``: ETH-USDレート
- ``nesta_usd`` - ``Number``: Nesta-USDレート
- ``timestamp`` - ``Number``: レート情報のUnixTimestamp

