---
title: Kline/Candlestick Data
position_number: 1.2
type: get
description: /data/api/v1/getKLine
parameters:
    -
        name: market
        type: string
        mandatory: true
        default: N/A
        description: Market pair
        ranges: btc_usdt, eth_usdt...
    -
        name: type
        type: string
        mandatory: true
        default: N/A
        description: Kline type
        ranges: 1min,5min,15min,30min,1hour,6hour,1day,7day,30day
    -
        name: since
        type: integer
        mandatory: true
        default: 0
        description: Time condition. Control increment
        ranges: The first time is 0, after that follow the value of the since
content_markdown: Note：**This method does not require a signature.**
left_code_blocks:
    -
        code_block: "public void getKLine() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getKLine?market=btc_usdt&type=1min&since=0\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
    -
        code_block: |-
            def get_klines(self, kwargs:dict):
                return super(PublicRequestAPI, self).get_klines('GET',Api.get_kline, kwargs)
        title: Python
        language: python
right_code_blocks:
    -
        code_block: "// [Timestamp, Open price, Highest price, Lowest price, Close price, Volume, Turnover]\r\n{\r\n  \"datas\": [\r\n    [\r\n      1562923200,\r\n      11634.64,  \r\n      11637.22,\r\n      11627.58,\r\n      11631.43,\r\n      1.144578,\r\n      13314.16264138\r\n    ]\r\n  ],\r\n  \"since\": 1562923200\r\n}"
        title: Response
        language: json
---
