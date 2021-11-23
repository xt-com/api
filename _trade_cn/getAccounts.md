---
title: 获取账户类型
position_number: 3
type: get
description: /trade/api/v1/getAccounts
parameters:
-
    name:
    type:
    mandatory: false
    default:
    description:
    ranges:
content_markdown: 注：**此方法不需要签名**
left_code_blocks:
-
    code_block: "public void getAccounts() {\r\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getAccounts\");\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\":200,\r\n  \"data\":[\r\n  \t{\"name\":\"钱包账户\",\"id\":1},\r\n  \t{\"name\":\"交易账户\",\"id\":2},\r\n  \t{\"name\":\"法币账户\",\"id\":3},\r\n        ...\r\n  ],\r\n  \"info\":\"success\"\r\n}"
    title: Response
    language: json
---
