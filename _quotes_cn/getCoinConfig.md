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
  - code_block: "[\r\n {\r\n   \"name\":\"eth\",                   // 币种名称\r\n   \"fullName\": \"Ethereum\",         // 币种全称\r\n   \"chains\": [\r\n       {\r\n           \"name\": \"eth-eth\",      // 链名\r\n           \"deposit\": 1,           // 是否开放充值 [0：否 1：是]\r\n           \"withdrawal\": 1         // 是否开放提币 [0：否 1：是]\r\n       },\r\n       {\r\n           \"name\": \"eth-fio\",\r\n           \"deposit\": 1,\r\n           \"withdrawal\": 1\r\n       },\r\n    ]\r\n  }\r\n ... \r\n]"
    title: Response
    language: json
---
