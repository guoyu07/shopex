### ShopEx48前端数据仓储接口 ###
**ShopEx48前端数据仓储,利用不同浏览器的客户端缓存特性,可以构建一个比COOKIES更加强大的,客户端状态存取机制**
### 实例： ###
```
<!--page1.html-->
<script>
   window.withUStatus(function(status){
              //status 就是客户端存储仓库对象。
              
             /*forSave 构建一个JSON，并且decode为存储仓库可接受的String类型*/ 
             var forSave=JSON.encode({
                    name:'Lily',
                    age:'18'
            });

              status.set('mykey',forSave);
           });
</script>
<!--page2.html-->
<script>
   window.withUStatus(function(status){
            
              status.get('mykey',function(value){
                      var _value=JSON.decode(value);
                      alert('Hi,Your name is:'+value.name+',you are'+value.age+' years old.');
                });
           });
</script>
```

_在ShopEx48中的近期浏览功能中,正是用到了这个_


---
