## springBoot集成freemarker
### 一 control类返回页面
1. @controler 
>可返回页面（@requestmapping（“/aaa”））
>返回json （@requestmapping（“/aaa”）+ @responseBody）
2. @restContrller
>返回json，相当于（@controler+ @responseBody）本来应该到success.jsp页面的，则其显示success.
