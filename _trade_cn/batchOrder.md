---
title: 批量委托
position_number: 6
type: post
description: /trade/api/v1/batchOrder
parameters:
-
    name: accesskey
    type: string
    mandatory: true
    default: N/A
    description: 访问密钥
    ranges:
-
    name: nonce
    type: integer
    mandatory: true
    default: N/A
    description: 13位毫秒数
    ranges:
-
    name: market
    type: string
    mandatory: true
    default: N/A
    description: 交易市场
    ranges: btc_usdt, eth_usdt...
-
    name: data
    type: string
    mandatory: true
    default: N/A
    description: 订单数据
    ranges:
content_markdown: |-
    只支持限价委托，一次事务，要么都成功，要么都失败

    data 是一个JSON数组，数组长度最大只支持100个，超出100的会被忽略100个以外的元素，数组元素格式为：

    {
      "price": 1000, //委托价格
      "amount": 1, //委托数量
      "type" : 1 // 1、买 0、卖
    }
  
    组装完成之后，把JSON数组转为STRING，再进行Base64.encode()才是最终要提交的数据

    请注意，data参与签名的不是JSON数据本身，而是Base64.decode()之后的STRING

left_code_blocks:
-
    code_block: "public void batchOrder() {\r\n\tMap<String, Object> map = new HashMap<String, Object>();\r\n\tmap.put(\"accesskey\", accessKey);\r\n\tmap.put(\"nonce\", System.currentTimeMillis());\r\n\tmap.put(\"market\", \"btc_usdt\");\r\n\t\r\n\tJSONArray array = new JSONArray();\r\n\tfor(int i = 0; i < 10; i++) {\r\n\t\tJSONObject bid = new JSONObject();\r\n\t\tbid.put(\"price\", \"10000.123\");\r\n\t\tbid.put(\"amount\", \"0.1\");\r\n\t\tbid.put(\"type\", 1);\r\n\t\tarray.add(bid);\r\n\t\tJSONObject ask = new JSONObject();\r\n\t\task.put(\"price\", \"10001.123\");\r\n\t\task.put(\"amount\", \"0.1\");\r\n\t\task.put(\"type\", 0);\r\n\t\tarray.add(ask);\r\n\t}\r\n\t// put data\r\n\tString data = Base64CoderC.encode(array.toJSONString());\r\n\t\r\n\tmap.put(\"data\", data);\r\n\t\r\n\t// 签名(en:Signature)\r\n\tString signature = HttpUtil.getSignature(map, secretKey);\r\n\tmap.put(\"signature\", signature);\r\n\t// \r\n\tString text = HttpUtil.post(URL + \"/trade/api/v1/batchOrder\", map);\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": [\r\n    {\r\n      \"amount\": 0.0010,         //委托数量\r\n      \"price\": 5000.0000,       //委托价格\r\n      \"id\": 156292972664756,\r\n      \"type\": 1                 // 1、买 0、卖\r\n    },\r\n    {\r\n      \"amount\": 0.0020,\r\n      \"price\": 5000.0000,\r\n      \"id\": 156292972664757,\r\n      \"type\": 1\r\n    }\r\n  ],\r\n  \"info\": \"An order has been placed successfully\"\r\n}"
    title: Response
    language: json
---
