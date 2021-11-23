---
title: Latest Ticker of all Markets
position_number: 1.4
type: get
description: /data/api/v1/getTickers
parameters:
    -
        name:
        content:
content_markdown: Note：**This method does not require a signature.**
left_code_blocks:
    -
        code_block: "public void getTickers() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getTickers\");\r\n\tSystem.out.println(text);\r\n}"
        title: Java
        language: java
    -
        code_block: |-
            def get_tickers(self):
                return super(PublicRequestAPI, self).get_tickers('GET',Api.get_tickers, {})
        title: Python
        language: python
right_code_blocks:
    -
        code_block: "{\r\n  \"ltc_usdt\": {\r\n    \"high\": 106.99,\r\n    \"moneyVol\": 1589953.528784,\r\n    \"rate\": 4.3400,\r\n    \"low\": 97.51,\r\n    \"price\": 105.52,\r\n    \"ask\": 105.61,\r\n    \"bid\": 105.46,\r\n    \"coinVol\": 15507.7052\r\n  },\r\n  \"btc_usdt\": {\r\n    \"high\": 11776.93,\r\n    \"moneyVol\": 33765013.61761934,\r\n    \"rate\": 1.3900,                 \r\n    \"low\": 11012.17,\r\n    \"price\": 11609.92,\r\n    \"ask\": 11618.25,\r\n    \"bid\": 11604.08,\r\n    \"coinVol\": 2944.208780\r\n  }\r\n  ...\r\n}\r\n"
        title: Response
        language: json
---
