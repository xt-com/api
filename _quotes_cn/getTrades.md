---
title: 最近市场成交记录
position_number: 1.7
type: get
description: /data/api/v1/getTrades
parameters:
    -
        name: market
        type: string
        mandatory: true
        default: N/A
        description: 交易市场
        ranges: btc_usdt, eth_usdt...
content_markdown: 注：**此方法不需要签名**
left_code_blocks:
    -
        code_block: "public void getTrades() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getTrades?market=btc_usdt\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
right_code_blocks:
    -
        code_block: "[\r\n  [\r\n    1562924059762,      //时间戳\r\n    11613.18,           //成交价\r\n    0.044448,           //成交量\r\n    \"bid\",              //交易类型 [bid:买 ask：卖]\r\n    156292405956105     //记录ID\r\n  ],\r\n  [\r\n    1562924059006,\r\n    11613.22,\r\n    0.000086,\r\n    \"ask\",\r\n    156292405956104\r\n  ]\r\n  ...\r\n]\r\n"
        title: Response
        language: json
---
