## Javascript

基本概念、页面引入方式、获取页面元素和操作元素属性的技巧，学习函数的基本定义方法和使用方法。

#### JavaScript对象

JavaScript中的变量和函数也可以组成一个对象。对象的变量即属性，对象的函数即方法，只不过JavaScript的对象类似于方法。

#### 创建对象的方法

1.单体

```
<script type="text/javasript">
    var Tom={
        name:"tom",
        age:18,
        showname:function(){
            alert(this.name);
        },
        showage:function(){
            alert(this.age);
        }
    }
</script>
```

2.工厂模式

```
<script type="text/javasript">
    function Person(name,age,job){
        var o = new Object();
        o.name = name;
        o.age = age;
        o.job = job;
        o.showname = function(){
            alert(this.name);
        };
        o.showage = function(){
            alert(this.age);
        };
        o.showjob = function(){
            alert(this.job);
        };
        return o;
    }
    
    var tom = Person('tom',18,'程序猿');
    tom.showname;
</script>
```

3.构造函数

```
<script type="text/javascript">
    function Person(name,age,job){            
        this.name = name;
        this.age = age;
        this.job = job;
        this.showname = function(){
            alert('我的名字叫'+this.name);    
        };
        this.showage = function(){
            alert('我今年'+this.age+'岁');    
        };
        this.showjob = function(){
            alert('我的工作是'+this.job);    
        };
    }
    var tom = new Person('tom',18,'程序员');
    var jack = new Person('jack',19,'销售');
    alert(tom.showjob==jack.showjob);
</script>
```

4.原型模式

```
<script type="text/javascript">
    function Person(name,age,job){        
        this.name = name;
        this.age = age;
        this.job = job;
    }
    //方法以原型的方式进行添加
    Person.prototype.showname = function(){
        alert('我的名字叫'+this.name);    
    };
    Person.prototype.showage = function(){
        alert('我今年'+this.age+'岁');    
    };
    Person.prototype.showjob = function(){
        alert('我的工作是'+this.job);    
    };
    var tom = new Person('tom',18,'程序员');
    var jack = new Person('jack',19,'销售');
    alert(tom.showjob==jack.showjob);
</script>
```

5.继承

```
<script type="text/javascript">
        //父类只有姓名和年龄
        function fclass(name,age){
            this.name = name;
            this.age = age;
        }
        fclass.prototype.showname = function(){
            alert(this.name);
        }
        fclass.prototype.showage = function(){
            alert(this.age);
        }
        
        //子类继承父类的属性，添加工作属性
        function sclass(name,age,job)
        {
            //继承父类属性
            fclass.call(this,name,age);
            this.job = job;
        }
        //继承父类方法
        sclass.prototype = new fclass();
        //添加子类的方法
        sclass.prototype.showjob = function(){
            alert(this.job);
        }
        var tom = new sclass('tom',19,'全栈工程师');
        tom.showname();
        tom.showage();
        tom.showjob();
    </script>
```



