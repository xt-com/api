---
title: Trading market configuration
position_number: 1.1
type: get
description: /data/api/v1/getMarketConfig
parameters:
  - name:
    content:
content_markdown:
left_code_blocks:
  - code_block: "public void getMarketConfig() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getMarketConfig\");\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
  - code_block: "def get_all_market_config(self):\r\n    return super(PublicRequestAPI, self).get_all_market_config('GET',Api.get_market_config, {})"
    title: Python
    language: python
right_code_blocks:
  - code_block: "{\n  \"ltc_usdt\": {\n    \"minAmount\": 0.00010,       // minimum order quantity\n    \"minMoney\": 5,       \t      // minimum order money\n    \"pricePoint\": 2,            // price decimal point\n    \"coinPoint\": 4,             // number decimal point\n    \"maker\": 0.00100000,        // Active transaction fee\n    \"taker\": 0.00100000         // Passive transaction fee\n  }\n  \"eth_usdt\": {\n    \"minAmount\": 0.00010,\n    \"pricePoint\": 2,\n    \"coinPoint\": 4,\n    \"maker\": 0.00100000,\n    \"taker\": 0.00100000\n  },\n  \"btc_usdt\": {\n    \"minAmount\": 0.0000010,\n    \"pricePoint\": 2,\n    \"coinPoint\": 6,\n    \"maker\": 0.00100000,\n    \"taker\": 0.00100000\n  }\n  ...\n}"
    title: Response
    language: json
---
