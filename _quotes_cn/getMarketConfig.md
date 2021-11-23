---
title: 交易市场配置
position_number: 1.1
type: get
description: /data/api/v1/getMarketConfig
parameters:
  - name:
    content:
content_markdown: 注：**此方法不需要签名**
left_code_blocks:
  - code_block: "public void getMarketConfig() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getMarketConfig\");\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
  - code_block: "{\r\n  \"ltc_usdt\": {\r\n    \"minAmount\": 0.00010,       // 最小下单数量\r\n    \"minMoney\": 5,       \t// 最小下单金额\r\n    \"pricePoint\": 2,            // 价格小数点(价格精度，不能大于此精度)\r\n    \"coinPoint\": 4,             // 数量小数点(数量精度，不能大于此精度)\r\n    \"maker\": 0.00100000,        // 主动单交易手续费\r\n    \"taker\": 0.00100000         // 被动单交易手续费\r\n  }\r\n  \"eth_usdt\": {\r\n    \"minAmount\": 0.00010,\r\n    \"pricePoint\": 2,\r\n    \"coinPoint\": 4,\r\n    \"maker\": 0.00100000,\r\n    \"taker\": 0.00100000\r\n  },\r\n  \"btc_usdt\": {\r\n    \"minAmount\": 0.0000010,\r\n    \"pricePoint\": 2,\r\n    \"coinPoint\": 6,\r\n    \"maker\": 0.00100000,\r\n    \"taker\": 0.00100000\r\n  }\r\n  ...\r\n}"
    title: Response
    language: json
---
