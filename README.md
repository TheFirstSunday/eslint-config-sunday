# eslint-config-sunday

---
A eslint rule applies to React、Vue3.0、ReactNative、TS.

## 使用方法

```shell
    npm install --save-dev eslint babel-eslint eslint-config-alloy
  
    or

    yarn add eslint babel-eslint eslint-config-sunday -D
```

在你的项目的根目录下创建一个 .eslintrc.js 文件，并将以下内容复制进去：

```javascript
    module.exports = {
      extends: [
        'sunday',
      ],
      env: {
        // 你的环境变量（包含多个预定义的全局变量）
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
      },
      globals: {
        // 你的全局变量（设置为 false 表示它不允许被重新赋值）
        //
        // myGlobal: false
      },
      rules: {
        // 自定义你的规则
      },
    };
```
## React/ReactNative

```shell
    npm install --save-dev eslint babel-eslint eslint-plugin-react eslint-config-sunday
    
    or
    
    yarn add eslint babel-eslint eslint-plugin-react eslint-config-sunday
```

在你的项目的根目录下创建一个 .eslintrc.js 文件，并将以下内容复制进去：

```javascript
    module.exports = {
      extends: [
        'sunday',
        'sunday/react',
      ],
      env: {
        // 你的环境变量（包含多个预定义的全局变量）
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
      },
      globals: {
        // 你的全局变量（设置为 false 表示它不允许被重新赋值）
        //
        // myGlobal: false
      },
      rules: {
        // 自定义你的规则
      },
    };
```
## Vue

```shell
    npm install --save-dev eslint babel-eslint vue-eslint-parser eslint-plugin-vue eslint-config-sunday

    or
    
    yarn add eslint babel-eslint vue-eslint-parser eslint-plugin-vue eslint-config-sunday
```

在你的项目的根目录下创建一个 .eslintrc.js 文件，并将以下内容复制进去：

```javascript
    module.exports = {
      extends: [
        'sunday',
        'sunday/vue',
      ],
      env: {
        // 你的环境变量（包含多个预定义的全局变量）
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
      },
      globals: {
        // 你的全局变量（设置为 false 表示它不允许被重新赋值）
        //
        // myGlobal: false
      },
      rules: {
        // 自定义你的规则
      },
    };
```

## TypeScript

```shell
    npm install --save-dev eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-config-sunday
    
    or
    
    yarn add --save-dev eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-config-sunday
```

在你的项目的根目录下创建一个 .eslintrc.js 文件，并将以下内容复制进去：

```javascript
    module.exports = {
      extends: [
        'sunday',
        'sunday/typescript',
      ],
      env: {
        // 你的环境变量（包含多个预定义的全局变量）
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
      },
      globals: {
        // 你的全局变量（设置为 false 表示它不允许被重新赋值）
        //
        // myGlobal: false
      },
      rules: {
        // 自定义你的规则
      },
    };
```

## TypeScript React/ReactNative

```shell
    npm install --save-dev eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-plugin-react eslint-config-sunday
    
    or 
    
    yarn add --save-dev eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-plugin-react eslint-config-sunday
```

在你的项目的根目录下创建一个 .eslintrc.js 文件，并将以下内容复制进去：

```javascript
    module.exports = {
      extends: [
        'sunday',
        'sunday/react',
        'sunday/typescript',
      ],
      env: {
        // 你的环境变量（包含多个预定义的全局变量）
        //
        // browser: true,
        // node: true,
        // mocha: true,
        // jest: true,
        // jquery: true
      },
      globals: {
        // 你的全局变量（设置为 false 表示它不允许被重新赋值）
        //
        // myGlobal: false
      },
      rules: {
        // 自定义你的规则
      },
    };
```

## 常见问题
- 在 VSCode 中使用

在 VSCode 中，默认 ESLint 并不能识别 .vue、.ts 或 .tsx 文件，需要在「文件 => 首选项 => 设置」里做如下配置：

```json
    
```

- 保存时自动修复 ESLint 错误

如果想要开启「保存时自动修复」的功能，你需要配置 .vscode/settings.json：
```json
    {
      "eslint.validate": ["javascript", "javascriptreact", "vue", "typescript", "typescriptreact"],
      "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
      }
    }
```
- VSCode 中的 autoFixOnSave 没有效果
  如果需要针对 .vue、.ts 和 .tsx 文件开启 ESLint 的 autoFix，则需要配置成：

```json
    {
      "eslint.autoFixOnSave": true,
      "eslint.validate": [
        "javascript",
        "javascriptreact",
        {
          "language": "vue",
          "autoFix": true
        },
        {
          "language": "typescript",
          "autoFix": true
        },
        {
          "language": "typescriptreact",
          "autoFix": true
        }
      ]
    }
```

- 如何结合 Prettier 使用
  
只需要安装 prettier 及相关 VSCode 插件即可。
下面给出一个 .prettierrc.js 配置，仅供参考：

```javascript
    // .prettierrc.js
    module.exports = {
      // 一行最多 120 字符
      printWidth: 120,
      // 使用 2 个空格缩进
      tabWidth: 2,
      // 不使用缩进符，而使用空格
      useTabs: false,
      // 行尾需要有分号
      semi: true,
      // 使用单引号
      singleQuote: true,
      // 对象的 key 仅在必要时用引号
      quoteProps: 'as-needed',
      // jsx 不使用单引号，而使用双引号
      jsxSingleQuote: false,
      // 末尾需要有逗号
      trailingComma: 'all',
      // 大括号内的首尾需要空格
      bracketSpacing: true,
      // jsx 标签的反尖括号需要换行
      jsxBracketSameLine: false,
      // 箭头函数，只有一个参数的时候，也需要括号
      arrowParens: 'always',
      // 每个文件格式化的范围是文件的全部内容
      rangeStart: 0,
      rangeEnd: Infinity,
      // 不需要写文件开头的 @prettier
      requirePragma: false,
      // 不需要自动在文件开头插入 @prettier
      insertPragma: false,
      // 使用默认的折行标准
      proseWrap: 'preserve',
      // 根据显示样式决定 html 要不要折行
      htmlWhitespaceSensitivity: 'css',
      // vue 文件中的 script 和 style 内不用缩进
      vueIndentScriptAndStyle: false,
      // 换行符使用 lf
      endOfLine: 'lf',
      // 格式化嵌入的内容
      embeddedLanguageFormatting: 'auto',
    };
```

VSCode 的一个最佳实践就是通过配置 .vscode/settings.json 来支持自动修复 Prettier 和 ESLint 错误：

```json
    {
      "files.eol": "\n",
      "editor.tabSize": 2,
      "editor.formatOnSave": true,
      "editor.defaultFormatter": "esbenp.prettier-vscode",
      "eslint.validate": ["javascript", "javascriptreact", "vue", "typescript", "typescriptreact"],
      "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
      }
    }
```


