---
title: Market Depth Data
position_number: 1.6
type: get
description: /data/api/v1/getDepth
parameters:
    -
        name: market
        type: string
        mandatory: true
        default: N/A
        description: Market pair
        ranges: btc_usdt, eth_usdt...
content_markdown: Note：**This method does not require a signature.**
left_code_blocks:
    -
        code_block: "public void getDepth() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getDepth?market=btc_usdt\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
    -
        code_block: |-
            def get_depth(self, kwargs):
                return super(PublicRequestAPI, self).get_depth('GET',Api.get_depth,kwargs)
        title: Python
        language: python
right_code_blocks:
    -
        code_block: "{\r\n  \"last\": 11591.26,     // Latest transaction price\r\n  \"asks\": [             // Seller\r\n    [\r\n      11594.80,         //Turnover\r\n      0.049472          //Volume\r\n    ],\r\n    [\r\n      11594.86,\r\n      0.048462\r\n    ]\r\n  ],\r\n  \"bids\": [             //Buyer\r\n       [\r\n         11590.06,\r\n         0.188749\r\n       ],\r\n       [\r\n         11588.42,\r\n         0.030403\r\n       ]\r\n   ]\r\n}"
        title: Response
        language: json
---
