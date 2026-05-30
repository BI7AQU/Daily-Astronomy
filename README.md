# 每日天文
使用quasar框架搭建的一个每日天文发布网站。

用cc0jj的项目魔改的：[35000ft/AUNU-Daily-Astronomy](https://github.com/35000ft/AUNU-Daily-Astronomy)

------

### 安装依赖

```
pnpm install
```

### 测试

```
pnpm run dev
```

### 生产

```
pnpm run build
```

------

### 需要修改的一些配置

- quasar.config.js 中第52行 publicPath:发布页面路径
- \src\boot\load-config.js 中第6行 config.json 文件路径
- \src\pages\IndexPage.vue 中第38行 known-archive-files.json 文件路径
- \src\layouts\MainLayout.vue 中第53行 linksList 页面左侧边栏配置
