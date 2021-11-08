---
title: 市场深度数据
position_number: 1.5
type: get
description: /data/api/v1/getDepth
parameters:
    -
        name: market
        type: string
        mandatory: true
        default: N/A
        description: 交易市场
        ranges: btc_usdt, eth_usdt...
content_markdown:
left_code_blocks:
    -
        code_block: "public void getDepth() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getDepth?market=btc_usdt\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
right_code_blocks:
    -
        code_block: "{\r\n  \"last\": 11591.26,     //最新成交价\r\n  \"asks\": [             //卖方\r\n    [\r\n      11594.80,         //成交额\r\n      0.049472          //成交量\r\n    ],\r\n    [\r\n      11594.86,\r\n      0.048462\r\n    ]\r\n  ],\r\n  \"bids\": [             //买方\r\n       [\r\n         11590.06,      //成交额\r\n         0.188749       //成交量\r\n       ],\r\n       [\r\n         11588.42,\r\n         0.030403\r\n       ]\r\n   ]\r\n}\r\n"
        title: Response
        language: json
---
