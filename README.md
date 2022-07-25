# qiankun-example


## 一、项目特色
### 1. 开发环境，父级用vite秒级更新，
### 2. 子应用也有为vite的vite加入子应用需使用vite-plugin-qiankun, 注意父级应用不用加
为什么不加?
因为官方qiankun没有兼容vite做为子应用,vite启动方式为module, 而其他的启动为script, 或许后面vite官方兼容了vite做为其子应用后就可以去掉该插件了；

## 二、开始
一键安装所有主子应用的依赖
```
npm i
```

一键启动所有所有应用
```
npm start
```
通过 [http://localhost:8080/](http://localhost:8080/) 访问主应用。
