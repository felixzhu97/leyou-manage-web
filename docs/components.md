# 组件文档

## 公共组件列表

1. Cascader - 级联选择器
2. Tree - 树形控件
3. Upload - 文件上传组件
4. Editor - 富文本编辑器

## 组件使用说明

### Cascader 级联选择器

```vue
<template>
  <cascader :options="options" v-model="selected"></cascader>
</template>

<script>
export default {
  data() {
    return {
      options: [], // 级联数据
      selected: [], // 选中值
    };
  },
};
</script>
```

### Tree 树形控件

```vue
<template>
  <tree :data="treeData" @node-click="handleNodeClick"></tree>
</template>
```

## 组件 API

### Upload 组件

| 属性     | 说明           | 类型    | 默认值 |
| -------- | -------------- | ------- | ------ |
| action   | 上传地址       | string  | -      |
| multiple | 是否多选       | boolean | false  |
| accept   | 接受的文件类型 | string  | -      |
