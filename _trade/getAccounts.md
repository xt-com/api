---
title: Get the Account Type
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
content_markdown: Note：**This method does not require a signature.**
left_code_blocks:
-
    code_block: "public void getAccounts() {\r\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getAccounts\");\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "// Fixed system account, which can be directly written into the program without obtaining dynamically\r\n{\r\n  \"code\":200,\r\n  \"data\":[\r\n  \t{\"name\":\" wallet account \",\"id\":1},\r\n  \t{\"name\":\" Trading account \",\"id\":2},\r\n  \t{\"name\":\" Fiat account \",\"id\":3}\r\n  ],\r\n  \"info\":\"success\"\r\n}"
    title: Response
    language: json
---
