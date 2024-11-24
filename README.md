# PDF Parse Service

一个基于FastAPI的PDF解析服务，支持将PDF转换为JSON和Markdown格式。

## 功能特性

- 支持多种解析方式：自动(auto)、OCR(ocr)、文本(txt)
- 支持JSON和Markdown格式输出
- 支持图片提取
- RESTful API接口

## 快速开始

1. 安装依赖
```bash
pip install -r requirements.txt
```

2. 启动服务
```bash
python main.py
```

服务将在 http://localhost:6006 启动

## API使用

访问 http://localhost:6006/docs 查看完整API文档

### 基础示例

```python
import requests

url = "http://localhost:6006/pdf_parse"
files = {
    'pdf_file': open('example.pdf', 'rb')
}
data = {
    'parse_method': 'auto',
    'output_dir': 'output'
}

response = requests.post(url, files=files, data=data)
print(response.json())
```
、