# 乐优商城管理系统 - 前端界面

基于 Vue.js 的乐优商城管理系统前端界面，提供电商运营管理功能。

## 功能特性

- 用户认证与权限管理
- 商品目录管理（品牌、分类、规格）
- 库存管理
- 订单处理
- 数据看板与分析

## 环境要求

- Node.js 14.x 或更高版本
- npm 6.x 或更高版本
- Vue CLI (可选)

## 安装指南

```bash
# 克隆仓库
git clone https://github.com/leyou-system/leyou-manage-web.git
cd leyou-manage-web

# 安装依赖
npm install

# 配置环境变量（见下方配置说明）
cp config/dev.env.js.example config/dev.env.js
```

## 配置说明

根据需要修改以下文件：

- `config/dev.env.js` - 开发环境变量
- `config/prod.env.js` - 生产环境变量
- `src/config.js` - API 端点等前端配置

## 项目结构

```
leyou-manage-web/
├── build/              # Webpack构建配置
├── config/             # 环境配置
├── src/                # 主要源代码
│   ├── assets/         # 静态资源
│   ├── components/     # 可复用组件
│   ├── pages/          # 页面组件
│   ├── router/         # 路由配置
│   ├── App.vue         # 主应用组件
│   └── main.js         # 应用入口
├── static/             # 纯静态资源
└── package.json        # 项目依赖和脚本
```

## 开发运行

```bash
# 启动开发服务器（热重载）
npm run dev

# 应用将运行在：
http://localhost:8080
```

## 生产构建

```bash
# 生产环境构建（压缩优化）
npm run build

# 构建并分析包大小
npm run build --report
```

## API 文档

前端界面与乐优后端 API 通信，详见[API 文档](https://api.leyou-system.com/docs)。

## 贡献指南

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/你的特性`)
3. 提交修改 (`git commit -am '添加新特性'`)
4. 推送分支 (`git push origin feature/你的特性`)
5. 创建 Pull Request

## 开源协议

[MIT](https://opensource.org/licenses/MIT)
