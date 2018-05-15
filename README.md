# pom.xmlProblem
>基于maven仓库创建的SpringBoot项目问题总结

## 1.pom.xml错误：org.codehaus.plexus.archiver.jar.Manifest.write(java.io.PrintWriter)的解决方法
> 原因：eclipse自带的maven插件版本太低

> 解决方法：点击：help ->  Install New Software -> add ->  
1. https://otto.takari.io/content/sites/m2e.extras/m2eclipse-mavenarchiver/0.17.2/N/LATEST
2. http://repo1.maven.org/maven2/.m2e/connectors/m2eclipse-mavenarchiver/0.17.2/N/LATEST/
#### 注：第一个国内访问时可能访问不通，尝试使用vpn代理，第二个地址可以正常使用，
#### 详细可参考：[网址](https://stackoverflow.com/questions/37555557/m2e-error-in-mavenarchiver-getmanifest)
