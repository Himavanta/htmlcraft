# htmlcraft

一个极简的 JavaScript 服务端渲染（SSR）框架，提供优雅的开发体验和原生 JavaScript 特性支持。

## 🌟 特性

- **模板字符串与标签函数**：使用原生 JavaScript 模板字面量进行 HTML 模板开发
- **增强的开发体验**：与 VSCode 和 `lit-html` 插件完美配合，提供 `css-in-js` 和 `html-in-js` 语法高亮
- **CSS 自动作用域**：CSS 类名自动生成和作用域隔离，解决样式污染问题
- **统一脚本环境**：客户端和服务端脚本可在同一 JavaScript 文件中编写，互不干扰
- **类 JSX 组件**：自组织的组件开发方式，类似 JSX 但使用原生 JavaScript

## 🚀 快速开始

1. **安装依赖**（如有需要）：

   ```bash
   npm install
   ```

2. **启动开发服务器**：

   ```bash
   node index.mjs
   ```

3. **打开浏览器**访问：
   ```
   http://localhost:8080
   ```

## 📁 项目结构

```
htmlcraft/
├── index.mjs      # 主服务器入口文件
├── render.mjs     # SSR 渲染逻辑和组件
├── utils.mjs      # 核心工具函数（html 和 css 标签函数）
├── readme.md      # 项目文档
└── readme.zh.md   # 中文文档
```

## 🛠️ 工作原理

### HTML 模板函数

`html` 标签函数处理模板字面量并将其转换为 HTML 字符串：

- 通过连接处理数组
- 将函数转换为内联脚本
- 支持自闭合标签语法

### CSS-in-JS 作用域样式

`css` 标签函数提供作用域样式：

- 自动生成唯一类名
- 将 `&` 选择器替换为作用域类名
- 将样式注入到文档头部

### 组件示例

```javascript
const Header = () =>
  html`<header>
    <${style} />
    <${navs.map(item)} />
    <${handle} />
  </header>`;
```

## 🎯 使用场景

- **快速原型开发**：小型 SSR 应用的快速搭建
- **学习 SSR 概念**：在没有框架复杂性的情况下理解 SSR 基础
- **轻量级应用**：适合需要服务端渲染的简单网站
- **模板引擎替代**：重型模板引擎的轻量级替代方案

## 🔧 自定义扩展

您可以通过以下方式扩展框架：

- 在 `utils.mjs` 中添加新的工具函数
- 在 `render.mjs` 中创建可复用组件
- 在 `index.mjs` 中实现额外的服务器逻辑

## 📝 许可证

本项目采用 [MIT 许可证](LICENSE) 开源。
