## 一、 安装 VScode 插件

打开 vscode prettier

## 二、项目根目录新增 .prettierrc.cjs 文件，内容如下

```JS
module.exports = {
  // 使用 prettier 的配置 schema。
  $schema: 'https://json.schemastore.org/prettierrc',
  arrowParens: 'always', // 将箭头函数的参数始终用括号包裹起来。
  bracketSameLine: true, // 在同一行中书写对象大括号和数组大括号。
  bracketSpacing: false, // 在对象大括号内不添加空格。
  embeddedLanguageFormatting: 'auto', // 根据需要自动格式化嵌入式语言，如在模板字符串中的 JavaScript 代码。
  htmlWhitespaceSensitivity: 'css', // HTML 空格敏感性使用 css。
  jsxSingleQuote: false, // 不使用单引号而是使用双引号来包裹 JSX 属性。
  printWidth: 120, // 设置每行的字符数限制，超过则格式化。
  proseWrap: 'preserve', // 不在 markdown 文件中强制断行。
  quoteProps: 'as-needed', // 只有在必要时才将属性名称用引号包裹起来，例如包含空格或保留关键字的属性名。
  insertPragma: false, // 不插入任何格式化代码，例如 Prettier 的特殊注释。
  requirePragma: false, // 不要在格式化的文件中要求使用特殊注释。
  semi: true, // 在语句末尾添加分号。
  singleQuote: true, // 使用单引号而不是双引号。
  tabWidth: 2, // 设置一个 tab 的宽度。
  trailingComma: 'none', // 不在多行的末尾添加逗号。
  useTabs: false, // 使用空格而不是制表符来缩进。
  vueIndentScriptAndStyle: false // 不缩进 .vue 文件中的 <script> 和 <style> 标签。
};

```

## 三、修改 .eslintrc.js 内容如下

```js
module.exports = {
  root: true,
  env: {
    node: true
  },
  extends: ['plugin:vue/essential', '@vue/standard'],
  parserOptions: {
    parser: '@babel/eslint-parser'
  },
  rules: {
    // 指定规则
    'vue/no-parsing-error': [
      // 禁止Vue.js错误
      2, // 错误级别为error
      {
        'x-invalid-end-tag': false // x-invalid-end-tag这个错误不会报错
      }
    ],
    'no-regex-spaces': 'error', // 禁止正则表达式中的空格
    'no-multi-spaces': 'error', // 禁止多个空格
    'array-bracket-spacing': [
      // 数组方括号内的空格
      'error',
      'never'
    ],
    'object-curly-spacing': [
      // 对象花括号内的空格
      'error',
      'never'
    ],
    'block-spacing': [
      // 代码块花括号内的空格
      'error',
      'never'
    ],
    'comma-spacing': [
      // 逗号后面的空格
      'error',
      {
        before: false, // 逗号前没有空格
        after: true // 逗号后有空格
      }
    ],
    'semi-spacing': [
      // 分号后面的空格
      'error',
      {
        before: false, // 分号前没有空格
        after: true // 分号后有空格
      }
    ],
    'computed-property-spacing': [
      // 计算属性内部的空格
      'error',
      'never'
    ],
    'no-trailing-spaces': 'off', // 禁止行末有空格，但是不作为错误级别
    'no-spaced-func': 'error', // 禁止函数名和括号之间有空格
    'space-before-function-paren': [
      // 函数括号前的空格
      'error',
      {
        anonymous: 'ignore', // 匿名函数括号前忽略
        named: 'ignore' // 命名函数括号前忽略
      }
    ],
    'space-before-blocks': [
      // 代码块括号前的空格
      'error',
      'always'
    ],
    'space-in-parens': [
      // 括号内的空格
      'error',
      'never'
    ],
    'space-infix-ops': [
      // 操作符中的空格
      'error',
      {
        int32Hint: false // 指定是否在位运算符号前后插入空格
      }
    ],
    'space-unary-ops': 'error', // 一元运算符前后不留空格
    'spaced-comment': ['error', 'always'], // 注释前后留一个空格
    'arrow-spacing': 'error', // 箭头函数的箭头前后留一个空格
    'yield-star-spacing': [
      // yield* 后面不留空格，前面留一个空格
      'error',
      {
        before: true,
        after: false
      }
    ],
    'no-irregular-whitespace': 'error', // 禁止使用不规则的空白符
    'template-curly-spacing': ['error', 'never'], // 模板字符串内部不留空格
    'max-len': ['error', 120], // 单行最大长度为120
    'no-multiple-empty-lines': 'error', // 不允许多个空行
    'eol-last': 'off', // 不强制文件末尾有空行
    'lines-around-comment': [
      // 注释前后各保留一行空行
      'error',
      {
        beforeBlockComment: false
      }
    ],
    curly: ['error', 'multi-line'], // 单行代码块两侧不加空格，多行代码块两侧加空格
    camelcase: [
      // 使用驼峰命名法，但是属性名可以不用
      'error',
      {
        properties: 'never'
      }
    ],
    'no-unused-vars': 0, // 允许定义未使用的变量
    'arrow-parens': 0, // 箭头函数参数可以不用括号
    indent: [
      // 使用2个空格作为一个缩进层级
      'error',
      2,
      {
        SwitchCase: 1 // switch 语句中的 case 子句增加一个缩进层级
      }
    ],
    'no-console': 0, // 允许使用 console
    'generator-star-spacing': 0, // generator 函数的 * 号前后不留空格
    'no-var': 1, // 尽量使用 let 或 const，不使用 var
    eqeqeq: ['error', 'smart'], // 使用严格相等运算符（===）或不严格相等运算符（==）的情况下需要进行类型转换时可以使用 ==，例如将字符串转为数字
    semi: [1, 'always'], // 语句末尾必须加分号，但可以使用 ASI 自动插入分号
    'operator-linebreak': [
      // 在操作符前换行，除非操作符位于行末或者下一行开头
      2,
      'before',
      {
        overrides: {
          '?': 'after'
        }
      }
    ],
    'no-debugger': 2, // 禁止使用 debugger
    quotes: [1, 'single'] // 字符串必须使用单引号
  }
};
```

## 四、修改 package.json lint-fix 命令

`"lint-fix": "eslint . --ext .vue,.js,.jsx,.cjs,.mjs,.ts,.tsx,.cts,.mts --fix --ignore-path .gitignore"`

```json
"scripts": {
  "start": "npm run serve",
  "serve": "vue-cli-service serve",
  "build": "vue-cli-service build",
  "lint": "vue-cli-service lint",
  "lint-fix": "eslint . --ext .vue,.js,.jsx,.cjs,.mjs,.ts,.tsx,.cts,.mts --fix --ignore-path .gitignore"
},
```

## 五、自动修复代码

```
npm run lint-fix
```

## 六、配置默认格式化使用 prettier

打开一个文件 - 鼠标右键 - `使用...格式化文档` - 配置默认格式化程序 - 选择 prettier

然后就可以 Shift + Alt + F 来格式化代码，并且没有错误了
