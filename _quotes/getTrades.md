---
title: Latest Market transactions record
position_number: 1.6
type: get
description: /data/api/v1/getTrades
parameters:
    -
        name: market
        type: string
        mandatory: true
        default: N/A
        description: Market pair
        ranges: btc_usdt, eth_usdt...
content_markdown:
left_code_blocks:
    -
        code_block: "public void getTrades() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getTrades?market=btc_usdt\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
    -
        code_block: |-
            def get_trades(self, kwargs):
                return super(PublicRequestAPI, self).get_trades('GET',Api.get_trades,kwargs)
        title: Python
        language: python
right_code_blocks:
    -
        code_block: "// [Timestamp, deal price, volume, Transaction type, Record ID]\r\n[\r\n  [\r\n    1562924059762,\r\n    11613.18,\r\n    0.044448,\r\n    \"bid\",\r\n    156292405956105\r\n  ],\r\n  [\r\n    1562924059006,      // Timestamp\r\n    11613.22,           // Turnover\r\n    0.000086,           // Volume\r\n    \"bid\",              // Trading type [bid:buy ask：sell]\r\n    156292405956104     // Record ID\r\n  ]\r\n]"
        title: Response
        language: json
---
