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
        code_block: |-
            // [Timestamp, deal price, volume, Transaction type, Record ID]
            [
                [
                    1562924059762,
                    11613.18,
                    0.044448,
                    "bid",
                    156292405956105
                ],
                [
                    1562924059006,
                    11613.22,
                    0.000086,
                    "bid",
                    156292405956104
                ]
            ]
        title: Response
        language: json
---
