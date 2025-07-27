# 个人主页

一个简洁美观的个人主页，包含天气显示功能。

## 功能特性

- 响应式设计，支持移动端
- 实时时间显示
- 基于高德地图API的天气信息
- 自动定位用户位置
- 手动刷新天气功能

## 配置说明

### 高德地图API配置

1. 访问 [高德开放平台](https://lbs.amap.com/)
2. 注册账号并登录
3. **重要**：创建应用时选择 **"服务端"** 类型（不是"Web端(JS API)"）
4. 获取API Key
5. 在 `index.html` 文件中找到以下代码：
   ```javascript
   const key = '你的高德地图API_KEY'; // TODO: 替换为你自己的key
   ```
6. 将 `你的高德地图API_KEY` 替换为你获取到的实际API Key

### API权限配置

确保你的高德地图应用已开通以下服务：
- IP定位
- 天气查询

### 常见问题解决

#### 错误：USERKEY_PLAT_NOMATCH
如果遇到此错误，说明你的API Key类型不正确：
- **原因**：创建应用时选择了"Web端(JS API)"而不是"服务端"
- **解决**：重新创建应用，选择"服务端"类型

### 安全密钥说明

**注意**：本项目使用的是高德地图的REST API，只需要API Key即可，不需要安全密钥。安全密钥主要用于JavaScript SDK（如地图组件等）。

如果你需要使用高德地图的JavaScript SDK（如显示地图），则需要同时使用API Key和安全密钥：

```html
<script src="https://webapi.amap.com/maps?v=2.0&key=您的API_KEY&securityJsCode=您的安全密钥"></script>
```

## 文件结构

```
home/
├── css/
│   └── style.css
├── images/
│   ├── home.jpg
│   ├── 博客园.svg
│   ├── 搜索 (1).svg
│   └── 音乐.svg
├── index.html
└── README.md
```

## 使用说明

1. 配置好API Key和安全密钥后，直接在浏览器中打开 `index.html`
2. 页面会自动获取你的位置并显示当地天气
3. 点击天气旁边的刷新按钮可以手动更新天气信息
4. 刷新功能有60秒冷却时间，防止频繁请求

## 注意事项

- 请确保网络连接正常
- API Key和安全密钥请妥善保管，不要泄露给他人
- 高德地图API有使用限制，请参考官方文档
- 安全密钥是必需的，没有安全密钥的API调用可能会失败 