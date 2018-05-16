# pom.xmlProblem
>基于maven仓库创建的SpringBoot项目问题总结

## 1.pom.xml错误：org.codehaus.plexus.archiver.jar.Manifest.write(java.io.PrintWriter)的解决方法
> 原因：eclipse自带的maven插件版本太低

> 解决方法：点击：help ->  Install New Software -> add ->  
1. https://otto.takari.io/content/sites/m2e.extras/m2eclipse-mavenarchiver/0.17.2/N/LATEST
2. http://repo1.maven.org/maven2/.m2e/connectors/m2eclipse-mavenarchiver/0.17.2/N/LATEST/
#### 注：第一个国内访问时可能访问不通，尝试使用vpn代理，第二个地址可以正常使用，
#### 详细可参考：[网址](https://stackoverflow.com/questions/37555557/m2e-error-in-mavenarchiver-getmanifest)

# 浏览器输入127.0.0.1:8080/hello访问异常
>问题描述：Whitelabel Error Page
This application has no explicit mapping for /error, so you are seeing this as a fallback.
Wed May 16 08:52:18 CST 2018
There was an unexpected error (type=Not Found, status=404).
No message available

>原因：项目入口启动类SpringApplication未置于最外层

>解决方法：这个类要放在groupId对应的包下，其他自己新建的包都应该是它的一个子包，例：启动类位于com.zx;其他项目类是com.zx.demo.

# springboot整合Mybatis application.properties 没有提示

>解决方法
1. Help->Eclipse Marketplace
2. 安装spring tools   popular下
