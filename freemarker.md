## springBoot集成freemarker

引入freemarker包，配置属性spring.freemarker.cache=false charset=UTF-8 request-context-attribute=request settings.number_format=#

### 一 control类返回页面
1. @controler 
>可返回页面（@requestmapping（“/aaa”））
1. 返回页面传参数：在方法中增加Model model对象参数，采用model.addAttribute("参数名",参数值)方法来传入，freemarker页面通过${参数名}取值
>返回json （@requestmapping（“/aaa”）+ @responseBody）
2. @restContrller
>返回json，相当于（@controler+ @responseBody）本来应该到success.jsp页面的，则其显示success.

### 二 freemarker基础语法

1. list：该标签主要是进行迭代服务器端传递过来的List集合，比如：
><#list nameList as names>    
  ${names}   
</#list> 

>相当于

>for (String names : nameList) {  
    System.out.println(names);  
}  
2. if：该标签主要是做if判断用的，比如：
><#if (names=="陈靖仇")>  
 他的武器是: 十五 
</#if>

>相当于

>if(names.equals("陈靖仇")){  
    System.out.println("他的武器是: 十五");
}

><#if (names=="陈靖仇")>  
 他的武器是: 十五~~  
<#elseif (names=="宇文拓")>       <#--注意这里没有返回而是在最后面-->   
 他的武器是: 轩辕剑~·  
<#else>  
她的绝招是：蛊毒~~  
</#if>  
3. include：该标签用于导入文件用的。
><#include "include.html"/>  

>这个导入标签非常好用，特别是页面的重用。另外在静态文件中可以使用${} 获取值，取值方式和el表达式一样，非常方便。

