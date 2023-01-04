# @kinfuy/eslint-config

kinfuy eslint config 标准库

## 安装

```sh
pnpm add @kinfuy/eslint-config
```

## 使用

// .eslintrc.json

```json
{
  "extends": "@kinfuy/eslint-config"
}
```

## 常见问题

### 怎么配置 alias？

```sh
pnpm add eslint-import-resolver-alias
```

```js
module.exports = {
  extends: '@kinfuy/eslint-config',
  settings: {
    'import/resolver': {
      alias: {
        map: [
          ['@', './src'],
          ['@C', './src/components'],
          ['@V', './src/views'],
          ['@assets', './src/assets'],
          ['@libs', './src/libs'],
          ['@api', './src/api']
        ],
        extensions: ['.ts', '.js', '.jsx', '.tsx']
      }
    }
  }
};
```

### 如何仅使用 ts?

```sh
pnpm add @kinfuy/eslint-config-ts
```

### 如何仅使用 js?

```sh
pnpm add @kinfuy/eslint-config-basic
```

## 注意

### 仅使用 js 或者 ts 时,如果需要 prettier 需要自行配置

#### 推荐使用

```sh
pnpm add eslint-plugin-prettier
```

```json
{
  "extends": ["plugin:prettier/recommended"]
}
```

plugin:prettier/recommended 帮我们做了如下事情：

```json
{
  "extends": ["prettier"], // 使用eslinst-config-prettier中的配置项
  "plugins": ["prettier"], // 注册该prettier插件
  "rules": {
    "prettier/prettier": "error", // 在eslint中运行prettier，并启用该插件提供的规则
    "arrow-body-style": "off", // 关闭规则
    "prefer-arrow-callback": "off" // 关闭规则
  }
}
```
