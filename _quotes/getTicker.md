---
title: Aggregated Markets （Ticker）
position_number: 1.3
type: get
description: /data/api/v1/getTicker
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
        code_block: "public void getTicker() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getTicker?market=btc_usdt\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
    -
        code_block: |-
            def get_ticker(self, kwargs):
                return super(PublicRequestAPI, self).get_ticker('GET',Api.get_ticker,kwargs)
        title: Python
        language: python
right_code_blocks:
    -
        code_block: |
            {
              "high": 11776.93,                 // Highest price in 24 hours
              "low": 11012.17,                  // Lowest price in 24 hours
              "rate": 1.3900,                   // Changes within 24 hours
              "price": 11609.92,                // Last traded price
              "ask": 11618.25,                  // First sell order
              "bid": 11604.08,                  // First buy order
              "coinVol": 2944.208780,           // Volume
              "moneyVol": 33765013.61761934     // Turnover
            }
        title: Response
        language: json
---
