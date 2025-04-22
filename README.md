# HTML-Go Express 代码分享工具

这是一个基于Node.js Express的HTML代码分享工具，可以快速创建和分享HTML代码片段，支持密码保护和多种代码格式。

## 功能特点

- **HTML代码分享**：快速创建和分享HTML代码片段
- **密码保护**：可为分享内容设置密码保护
- **多格式支持**：支持HTML、Markdown、SVG、Mermaid等多种格式
- **响应式设计**：适配各种设备屏幕
- **会话管理**：支持用户登录和会话管理

## 快速开始

1. 安装依赖：
```bash
npm install
```

2. 配置环境变量：
复制.env.example为.env并修改配置：
```bash
cp .env.example .env
```

3. 启动开发服务器：
```bash
npm run dev
```

4. 访问应用：
```
http://localhost:3000
```

## 项目结构

```
html-go-express/
├── config.js            # 应用配置
├── app.js               # 主应用文件
├── package.json         # 项目依赖
├── public/              # 静态资源
│   ├── css/             # 样式文件
│   └── js/              # 客户端脚本
├── views/               # 视图模板
├── routes/              # 路由定义
├── models/              # 数据模型
├── middleware/          # 中间件
└── utils/               # 工具函数
```

## 环境要求

- Node.js 16+
- npm 8+
- SQLite3 (用于本地开发)

## 生产部署

1. 构建生产环境：
```bash
npm run prod
```

2. 使用Docker部署：
```bash
docker-compose up -d
```

## API接口

### 创建代码片段
```
POST /api/pages/create
参数:
- htmlContent: HTML内容
- isProtected: 是否密码保护
```

### 获取代码片段
```
GET /view/:id
参数:
- id: 片段ID
- password: 密码(如需)
```

## 常见问题

1. **会话存储失败**：
   检查`sessions`目录权限，确保应用有读写权限

2. **数据库连接问题**：
   检查SQLite数据库文件路径是否正确

3. **端口冲突**：
   修改config.js中的端口配置
