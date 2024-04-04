# 🔑 Api Key 使用与鉴权

**使用说明：**

AI画师 OpenAPI 接口允许你使用 Api Key 进行鉴权，从而操作AI画师上的相关服务和资源，例如：调用应用对话接口、上传知识库数据、搜索测试等等。出于兼容性和安全考虑，并不是所有的接口都允许通过 Api Key 访问。

**API根地址：**

```
ttps://api.fastgpt.in/api
```

**获取API KEY：**

请联系客服申请API KEY。

{% hint style="danger" %}
请妥善保存好您的密钥，后台一旦发现违规使用行为将进行安全风控！
{% endhint %}

**基本配置**

OpenAPI 中，所有的接口都通过 Header.Authorization 进行鉴权。

```
baseUrl: "https://api.fastgpt.in/api"
headers: {
    Authorization: "Bearer {{apikey}}"
}
```

发起应用对话示例

```
curl --location --request POST 'https://api.fastgpt.in/api/v1/chat/completions' \
--header 'Authorization: Bearer fastgpt-xxxxxx' \
--header 'Content-Type: application/json' \
--data-raw '{
    "chatId": "111",
    "stream": false,
    "detail": false,
    "messages": [
        {
            "content": "导演是谁",
            "role": "user"
        }
    ]
}'
```

