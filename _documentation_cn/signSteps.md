---
title: 签名步骤
position_number: 5
parameters:
- name:
content:
content_markdown: >-
    规范要计算签名的请求 因为使用 HMAC
    进行签名计算时，使用不同内容计算得到的结果会完全不同。所以在进行签名计算前，请先对请求进行规范化处理。下面以查询某订单详情请求为例进行说明：


    https://api.xt.com/trade/api/v1/getOrder?accesskey=\{AccessKey\}&market=\{Market\}&nonce=\{Timestamp\}&id=\{OrderId\}&signature=\{Signature\}


    按照ASCII码的顺序对参数名进行排序,将各参数使用字符 “&” 连接，例如下面就是排序之后结果：


    accesskey=myAccessKey&id=123&market=btc\_usdt&nonce=1562919832183


    需要注意的是nonce的值为13位毫秒数时间戳


    使用网站申请得到的Secret Key对上面生成的参数串进行 HmacSHA256 签名。例如上述参数进行签名的结果：


    97b7b71741ca0aec6e0404a5b1c7cb2a78e7bd6c2a8088dbd84a20129dee4fe7


    最后把签名赋值到参数名signature并提交到服务器
left_code_blocks:
- code_block:
  title:
  language:
right_code_blocks:
- code_block:
  title:
  language:
---
