---
title: 签名说明
position_number: 4
parameters:
- name:
content:
content_markdown: >-
    使用API请求在通过 internet 传输的过程中极有可能被篡改，为了确保请求未被更改，除公共接口（基础信息，行情数据）外的私有接口均必须使用您的 API
    Key 做签名认证，以校验参数或参数值在传输途中是否发生了更改。每一个API Key需要有适当的权限才能访问相应的接口。每个新创建的API
    Key都需要分配权限。权限类型分为：读取，交易，提币。在使用接口前，请查看每个接口的权限类型，并确认你的API Key有相应的权限。


    一个合法的请求由以下几部分组成：
    
    
    方法请求地址：即访问服务器地址&nbsp;**api.xt.com**，比如&nbsp;**api.xt.com/trade/api/v1/order**。
    
    
    API 访问密钥（accesskey）：您申请的 API Key 中的 Access Key。
    
    
    时间戳（nonce）：您应用程序发出请求的时间戳，13位毫秒数，将根据这个时间戳检验您API请求的有效性。
    
    
    签名(signature)：签名计算得出的值，用于确保签名有效和未被篡改，使用 HmacSHA256。
left_code_blocks:
- code_block:
  title:
  language:
  right_code_blocks:
- code_block:
  title:
  language:
---


