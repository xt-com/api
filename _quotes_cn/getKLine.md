---
title: K线数据
position_number: 1.3
type: get
description: /data/api/v1/getKLine
parameters:
    -
        name: market
        type: string
        mandatory: true
        default: N/A
        description: 交易市场
        ranges: btc_usdt, eth_usdt...
    -
        name: type
        type: string
        mandatory: true
        default: N/A
        description: K线类型
        ranges: 1min,5min,15min,30min,1hour,6hour,1day,7day,30day
    -
        name: since
        type: integer
        mandatory: true
        default: 0
        description: 时间条件，控制增量
        ranges: 第一次为0,之后为响应的since的值即可
content_markdown: 注：**此方法不需要签名**
left_code_blocks:
    -
        code_block: "public void getKLine() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getKLine?market=btc_usdt&type=1min&since=0\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
right_code_blocks:
    -
        code_block: "{\r\n  \"datas\": [\r\n    [\r\n      1562923200,       //时间戳\r\n      11634.64,         //开盘价\r\n      11637.22,         //最高价\r\n      11627.58,         //最低价\r\n      11631.43,         //收盘价\r\n      1.144578,         //成交量\r\n      13314.16264138    //成交额\r\n    ]\r\n  ],\r\n  \"since\": 1562923200\r\n}"
        title: Response
        language: json
---
