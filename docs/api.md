# API 文档

## 基础信息

- 基础路径：`/api`
- 认证方式：JWT

## 商品服务

- 品牌管理

  - GET /brands - 获取品牌列表
  - POST /brands - 新增品牌
  - PUT /brands/{id} - 修改品牌
  - DELETE /brands/{id} - 删除品牌

- 分类管理
  - GET /categories - 获取分类树
  - POST /categories - 新增分类
  - PUT /categories/{id} - 修改分类
  - DELETE /categories/{id} - 删除分类

## 用户服务

- 用户管理
  - POST /login - 用户登录
  - GET /users - 获取用户列表
  - POST /users - 新增用户
  - PUT /users/{id} - 修改用户信息
