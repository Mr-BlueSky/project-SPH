1.vue-cli脚手架初始化项目
node + webpack + 淘宝镜像

sudo vue create app 

node_modules文件夹：项目依赖

public文件夹：一般放置一些静态文件（图片），注意，放在public中的静态资源，在webpack进行打包时，会原封不动打包到dist文件夹中

src文件夹：程序员源代码文件夹

    assets文件夹：一般也是放在静态资源（一般放置多个组件公用的静态资源），注意，放置在assets文件夹中的静态资源，webpack打包时，会将静态资源打包成一个模块，放置在JS文件夹中

    components文件夹:一般放置的是非路由组件（全局组件）

    App.vue；唯一的根组件，Vue当中的组件（.vue）
    main.js：程序入口文件，也是程序中最先执行的文件

babel.config.js:配置文件（bebel相关）

package.json：项目的“身份证”，记录项目叫什么，项目中有哪些依赖，项目如何运行

package-lock.json：缓存性文件 

2.其他配置
2.1 项目运行时，浏览器自动打开
package.json文件下
"scripts": {
    "serve": "vue-cli-service serve --open",
    "build": "vue-cli-service build",
    "lint": "vue-cli-service lint"
  },

2.2 eslint校验功能关闭
  module.exports = defineConfig({
  //关闭eslint
  lintOnSave:false
})

2.3 src文件夹简写，配置别名为 @
根目录下新建jsconfig.json
{
  "compilerOptions": {
    "baseUrl": "./",
    "paths": {
      "@/*": [
        "src/*"
      ]
    }
  },
  "exclude":["node_modules","dist"]
}



3.项目的路由分析
vue-router
前端所谓路由：KV键值对
key:URL(地址栏中的路径)
value：相应的路由组件
注意：项目上中下结构

路由组件：
Home首页路由组件、Search路由组件、Login登录路由、Register注册路由
非路由组件
Header
Footer

4.完成非路由组件Header与Footer业务
不以HTML + CSS为主，主要搞业务、逻辑
开发项目时：
1、书写静态页面（HTML + CSS）
2、拆分组件
3、获取服务器数据动态展示
4、完成相应的动态业务逻辑

注意1：创建组件时，组件结构 + 组件样式 + 图片资源

注意2：项目采用less样式，浏览器不识别less样式，需通过less,less-loader【安装5版本】进行处理less，把less样式变为css样式，浏览器才能识别