# vue-shop

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### 后端API地址
axios.defaults.baseURL = https://lianghj.top:8888/api/private/v1/

### 笔记
1. 退出功能实现原理:
```
//清空token
window.sessionStorage.clear()
//跳转到登录页
this.$router.push('/login')
```
2. 通过.prettierrc配置文件修改默认格式化配置
```
{
  "semi": false,
  "singleQuote": true
}
```
3. .eslintrc.js 修改语法校验规则
```
0 代表禁用, 1 代表提醒, 2 代表报错
"space-before-function-paren": [0, "always"], //函数定义时括号前面要不要有空格
```
4. css学习总结
```
justify-content: space-between;
padding-left: 0;
<!-- 水平居中 -->
align-items: center;
```