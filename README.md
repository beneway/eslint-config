# @benewy/eslint-config

[![npm](https://img.shields.io/npm/v/@benewy/eslint-config?color=a1b858&label=)](https://npmjs.com/package/@benewy/eslint-config)

- 单引号，没有双引号
- 自动修复格式（在没有 Prettier 的情况下独立使用）
- 设计用于开箱即用的 TypeScript、Vue
- Lint 也适用于 json、yaml、markdown
- 排序的进口，悬挂逗号
- 合理的默认值，最佳实践，只需一行配置
- **风格原则**：阅读最小，差异稳定

## 使用

### 安装

```bash
pnpm add -D eslint @benewy/eslint-config
```

### 配置 `.eslintrc`

```json
{
  "extends": "@benewy"
}
```

> 您通常不需要 .eslintignore ，因为它已由预设提供。

### 为 package.json 添加脚本

例如：

```json
{
  "scripts": {
    "lint": "eslint .",
    "lint:fix": "eslint . --fix"
  }
}
```

### 配置 VS 代码自动修复

安装 [VS Code ESLint 扩展](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) 并创建 `.vscode/settings.json`

```json
{
  "prettier.enable": false,
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

### TypeScript 感知规则

当在项目根目录中找到 tsconfig.eslint.json 时，将启用类型感知规则，这将在您的项目中引入一些更严格的规则。 如果你想在项目根目录中没有 tsconfig.eslint.json 的情况下启用它，你可以通过修改 `ESLINT_TSCONFIG` env 来更改 tsconfig 名称。

```js
// .eslintrc.js
process.env.ESLINT_TSCONFIG = 'tsconfig.json'

module.exports = {
  extends: '@benewy'
}
```

## 扩展阅读

了解更多上下文 - [为什么我不推荐不使用 Prettier](https://antfu.me/posts/why-not-prettier)。

## License

[MIT](./LICENSE) License &copy; 2019-PRESENT [杭州融惠数据科技有限公司](https://github.com/benewy)
