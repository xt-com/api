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
  - code_block: "[\r\n {\r\n   \"name\":\"eth\",                   // coin\r\n   \"fullName\": \"Ethereum\",         // Full name of coin\r\n   \"chains\": [\r\n       {\r\n           \"name\": \"eth-eth\",      // Chain name\r\n           \"deposit\": 1,           // Whether to open deposit [0: No 1: Yes]\r\n           \"withdrawal\": 1         // Whether to open withdrawal [0: No 1: Yes]\r\n       },\r\n       {\r\n           \"name\": \"eth-fio\",\r\n           \"deposit\": 1,\r\n           \"withdrawal\": 1\r\n       },\r\n    ]\r\n  }\r\n ... \r\n]"
    title: Response
    language: json
---
