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
2. 