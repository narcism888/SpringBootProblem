在同一项目文件下，可以通过@ComponentScan(basePackages = {"com.zenchn.dam","com.zenchn.dam"})
#1.@Resource（按名称）
如果使用name属性，则使用byName的自动注入策略，而使用type属性时则使用byType自动注入策略。如果既不制定name也不制定type属性，这时将通过反射机制使用byName自动注入策略。
①如果同时指定了name和type，则从Spring上下文中找到唯一匹配的bean进行装配，找不到则抛出异常。
②如果指定了name，则从上下文中查找名称（id）匹配的bean进行装配，找不到则抛出异常。
③如果指定了type，则从上下文中找到类似匹配的唯一bean进行装配，找不到或是找到多个，都会抛出异常。
④如果既没有指定name，又没有指定type，则自动按照byName方式进行装配；如果没有匹配，则回退为一个原始类型进行匹配，如果匹配则自动装配。
#2.@Resource的作用相当于@Autowired，只不过@Autowired按照byType自动注入。
@Autowired（按类型）必须存在，允许为空（required =false）
按名称结合@Qualifier("userDao")
#3.dubbo的多模块@reference注解(其余两个注解找不到文件)
针对同一项目下 @service注入

#4.@MapperScan(basePackages = {“com.cybertron.barcode.service.dao”“})//扫描mapper.java和mapper.xml文件。

如果Mapper.xml与Mapper.class在同一个包下且同名，spring扫描Mapper.class的同时会自动扫描同名的Mapper.xml并装配到Mapper.class。

如果Mapper.xml与Mapper.class不在同一个包下或者不同名，就必须使用配置mapperLocations指定mapper.xml的位置。 
application.yml中配置mybatis: 
application.yml配置 
此时spring是通过识别mapper.xml中的 namespace的值来确定对应的Mapper.class的
