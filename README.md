# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=erweimaocr) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 二维码识别OCR
对图片中的二维码、条形码进行检测和识别，返回存储的文字内容。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/ocrbarcode/introduction](https://www.apispace.com/eolink/api/ocrbarcode/introduction?utm_source=github&utm_term=erweimaocr) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/ocrbarcode/guidence/](https://www.apispace.com/eolink/api/ocrbarcode/guidence/?utm_source=github&utm_term=erweimaocr)

### 功能介绍

1.  #### **二维码识别**

对图片中的文字进行检测和识别，支持多种语言。并且包含文字在图片中的位置信息，方便进行版式的二次处理。

2.  #### 条形码识别

支持对图片中的条形码进行检测和识别，返回存储的文字内容。

### 识别效果

识别图片：

![image](https://user-images.githubusercontent.com/36323798/223979607-8469dce5-44a5-499c-9fca-7caaf6d9f4e6.png)


识别效果：

```
{
    "result": [{
        "text": "https://www.apispace.com",
        "type": "QRCODE",
        "location": [
            [36, 36],
            [36, 332],
            [332, 332],
            [332, 36]
        ]
    }],
    "result_count": 1,
    "log_id": "15862053-bd9d-11ed-9b07-00000001623f"
}
```

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223979549-1202aae7-4dbd-4c49-8659-7e35d272c7ce.png)

### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/ocrbarcode/ocr/v1/barcode"

payload = {"image":"","url":"https://www.apispace.com/assets/images/contactCode.png"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/json"
}

response=requests.request("POST", url, data=json.dumps(payload), headers=headers)

print(response.text)

```
