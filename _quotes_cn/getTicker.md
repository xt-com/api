---
title: 聚合行情
position_number: 1.3
type: get
description: /data/api/v1/getTicker
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
        code_block: "public void getTicker() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getTicker?market=btc_usdt\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
right_code_blocks:
    -
        code_block: "{\r\n  \"high\": 11776.93,\t\t\t// 24最高\t\t\r\n  \"low\": 11012.17,\t\t\t// 24最低\r\n  \"rate\": 1.3900,                       // 24涨跌幅\r\n  \"price\": 11609.92,                    // 最新成交价\r\n  \"ask\": 11618.25,\t\t    \t// 卖一\r\n  \"bid\": 11604.08,\t\t    \t// 买一\r\n  \"coinVol\": 2944.208780,            \t//成交量\r\n  \"moneyVol\": 33765013.61761934    \t//成交额\r\n}\r\n"
        title: Response
        language: json
---
