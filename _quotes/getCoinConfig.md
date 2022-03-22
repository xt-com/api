---
title: Trading Coin Configuration
position_number: 1.1
type: get
description: /data/api/v1/getCoinConfig
parameters:
  - name:
    content:
content_markdown: Note：**This method does not require a signature.**
left_code_blocks:
  - code_block: "public void getCoinConfig() {\r\n\tString text = HttpUtil.get(URL + \"/data/api/v1/getCoinConfig\");\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
  - code_block: "[\r\n  {\r\n    \"name\": \"btc\",            // Coin\r\n    \"fullName\": \"Bitcoin\",    // Full name of coin\r\n    \"chainName\": \"\",          // Chain name\r\n    \"isPayIn\": 1,             // Whether to open deposit [0: No 1: Yes]\r\n    \"isPayOut\": 1             // Whether to open withdrawal [0: No 1: Yes]\r\n  },\r\n  {\r\n    \"name\": \"eth\",            \r\n    \"fullName\": \"Ethereum\",    \r\n    \"chainName\": \"\",          \r\n    \"isPayIn\": 1,             \r\n    \"isPayOut\": 1            \r\n  }\r\n ...\r\n]"
    title: Response
    language: json
---
