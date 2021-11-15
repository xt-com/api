---
title: 获取指定账户资产
position_number: 4
type: get
description: /trade/api/v1/getFunds
parameters:
-
    name: accesskey
    type: string
    mandatory: true
    default: N/A
    description: 访问密钥
    ranges:
-
    name: account
    type: integer
    mandatory: true
    default: N/A
    description: 账户ID
    ranges: 参考getAccounts接口
-
    name: nonce
    type: integer
    mandatory: true
    default: N/A
    description: 13位毫秒数
    ranges:
content_markdown:
left_code_blocks:
-
    code_block: "public void getFunds() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"account\", 2);\t// 现货账户(en:Spot account)\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\t// 签名(en:Signature)\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getFunds\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": {\r\n    \"btc\": {\r\n      \"freeze\": \"0.00\",     // 冻结\r\n      \"available\": \"0.00\"   // 可用\r\n    },\r\n    \"eth\": {\r\n      \"freeze\": \"0.00\",\r\n      \"available\": \"0.00\"\r\n    },\r\n    \"usdt\": {\r\n      \"freeze\": \"3062.17437341\",\r\n      \"available\": \"3867.43650012\"\r\n    },\r\n    \"ltc\": {\r\n      \"freeze\": \"0.00\",\r\n      \"available\": \"0.00\"\r\n    }\r\n    ...\r\n  },\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
