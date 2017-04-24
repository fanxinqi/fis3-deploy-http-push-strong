# fis3 http 部署插件加强版
扩展了FIS 默认的部署插件，主要提供了release后的不同目录的定制化发布功能，兼容ffis3内置上传服务写法

##  安装


###### 全局安装

npm install fis3-deploy-http-push-strong -g
###### 或者本地安装

npm install fis3-deploy-http-push-strong --save-dev


## 使用方法
###### care from 的使用示例
推荐写法：
```
 fis.media('qa').match('*',{
   deploy:[
     fis.plugin("http-push-strong",[{
           receiver: 'http://cq.01.p.p.baidu.com:8888/receiver.php',
           to: '/home/work/htdocs/static',
           from:"/static"
     },{
           receiver: 'http://cq.01.p.p.baidu.com:8888/receiver.php',
           to: '/home/work/jello',
           from:"/WEB-INF"
     },
     {
           receiver: 'http://cq.01.p.p.baidu.com:8888/receiver.php',
           to: '/home/work/img',
           from:"/img"
     }])
      ]
 })
```
###### 或

```
 fis.media('qa').match('*',{
   deploy:[
     fis.plugin("http-push-strong",{
           receiver: 'http://cq.01.p.p.baidu.com:8888/receiver.php',
           to: '/home/work/htdocs/static',
           from:"/static"
     }),
     fis.plugin("http-push-strong",{
           receiver: 'http://cq.01.p.p.baidu.com:8888/receiver.php',
           to: '/home/work/jello',
           from:"/WEB-INF"
     })，
     fis.plugin("http-push-strong",{
           receiver: 'http://cq.01.p.p.baidu.com:8888/receiver.php',
           to: '/home/work/img',
           from:"/img"
     })
  ]
 })
```
###### 整体发布不care from  （http-push fis原带功能）

```
 fis.media('qa').match('*',{
   deploy:[
     fis.plugin("http-push-strong",{
           receiver: 'http://cq.01.p.p.baidu.com:8888/receiver.php',
           to: '/home/work/'
     })
   ]
 })
```
## 其他详细用法和http-push一致
https://github.com/fex-team/fis3-deploy-http-push
