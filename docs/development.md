# 开发指南

## 项目结构

```
leyou-manage-web/
├── build/            # webpack构建配置
├── config/           # 环境配置
├── src/              # 源代码
│   ├── assets/       # 静态资源
│   ├── components/   # 公共组件
│   ├── pages/        # 页面组件
│   ├── router/       # 路由配置
│   ├── App.vue       # 根组件
│   └── main.js       # 入口文件
├── static/           # 纯静态资源
└── docs/             # 项目文档
```

## 开发环境配置

1. 安装 Node.js (>=12.x)
2. 安装依赖：

```bash
npm install
```

## 开发规范

1. 组件命名：大驼峰式 (如 MyComponent)
2. 目录命名：小写字母，短横线分隔 (如 my-component)
3. 代码风格：遵循 ESLint 规则

## 常用命令

- 启动开发服务器：`npm run dev`
- 构建生产环境：`npm run build`
- 代码检查：`npm run lint`
