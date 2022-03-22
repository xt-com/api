---
title: 交易币种配置
position_number: 1.1
type: get
description: /data/api/v1/getCoinConfig
parameters:
  - name:
    content:
content_markdown: 注：**此方法不需要签名**
left_code_blocks:
  - code_block: "public void getCoinConfig() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getCoinConfig\");\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
  - code_block: "[\r\n  {\r\n    \"name\": \"btc\",            // 币种名称\r\n    \"fullName\": \"Bitcoin\",    // 币种全称\r\n    \"chainName\": \"\",          // 链名\r\n    \"isPayIn\": 1,             // 是否开放充值 [0：否 1：是]\r\n    \"isPayOut\": 1             // 是否开放提币 [0：否 1：是]\r\n  },\r\n  {\r\n    \"name\": \"eth\",            \r\n    \"fullName\": \"Ethereum\",    \r\n    \"chainName\": \"\",          \r\n    \"isPayIn\": 1,             \r\n    \"isPayOut\": 1            \r\n  }\r\n ...\r\n]"
    title: Response
    language: json
---
