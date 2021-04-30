# kt学习笔记

## 继承

- 继承类可用: 直接调用类名()
- 实现接口可直接在继承后写需要实现的类名即可,也可放在:后,继承和实现的顺序对程序功能无影响

```kotlin
class MainActivity:AppcompatActivity(),View.OnClickListener{}
```

## 变量

- kotlin中变量可以省略变量类型

  kotlin

```kotlin
var name="张三"
```

​	java

```java
String name="张三";
```

## 常量

- 只能赋值一次

  kotlin

```kotlin
val name="张三"
```

​	java

```java
final String name="张三";
```

## 延迟初始化

kt

```kotlin
lateinit var etName:EditText
initView(){
    etName=findviewById(id)
}
```

java

```java
EditText etName =null;
initView(){
    etName=findviewById(id)
}
```

## 非空类型

kotlin

```kotlin
//默认情况常规初始化意味参数非空
var name:String ="zhangsan"
//编译错误
name=null  
//可空类型
var name:String?="lisi"
//编译正常
name=null 
```

java

```java
String name;
```



## 关键字instanceof

- 是否属于某个类型的实例

  kotlin

```kotlin
 if(v is View)
```

​		java

```java
 if(v instanceof View)
```

## 强转

​	kt

 ```kotlin
 var codeView = v as ImageView
 ```

​	java

```java
View v=(ImageView)v;
```

## 大于等于

kt 

```kotlin
if(code in 200..299)
```

java

```java
if(code >= 200 &&code <300 )
```

## 字符串拼接

kt

```kotlin
fun url(params:String?){
    utl="baidu.com$params"
}
```

java

```java
public void  url(String params){
    utl="baidu.com"+params
}
```

## When

kt 

```kotlin
when(code){
    in 200..299 ->{
        ...
    }
    in 300..399 ->funX()
   	else ->fun()
}
```



## 创建对象

- kotlin中调用其他类时,如果调用kotlin类则使用::即可
- 如果在kotlin中调用java类,则需要 在kotlin类后使用.java

​	kotlin

```kotlin
//kotlin中调用kt类
Intent(this,MainActivity::class)
//kt中调用java类
Intent(this,MainActivity::class.java)
```

​	java

```java
new Intent(this,MainActivity.class)
```

## 访问函数

- Model 类中的get和set方法一般情况下都可以使用 参数名来直接调用

kt

```kotlin
var user:User=User()
user.name="zhangsan"
```

java

```java
User user= new User();
user.setName("zhangsan");

## 构造函数

kt

​```kotlin
//空参构造函数
constructor(){}
//带参构造函数
constructor(username:String?){this.username=username}
//调用父类构造器
constructor(context: Context,attrs:AttributeSet?) : super(context,attrs)
```

java

``` java
//空参构造函数
public MainActivity(){}
//带参构造函数
public MainActivity(username:String?){this.username=username}
//调用父类构造器
public MainActivity(Context context){super(content,null)}
```

## 数组

-  数组最好指定好数据类型避免装箱拆箱操作
- 直接使用ByteArray, CharArray, ShortArray, IntArray, LongArray, BooleanArray, FloatArray, and DoubleArray而避免使用arrayOf(),造成额外开销

kt

```kotlin
var codeList=intArrayOf(1,2,3,4)
```

java

```java
int[] codeList=new int[]{1,2,3,4}
```

## 静态函数

- kt中没有静态函数的叫法,但是取而代之的是顶层函数和高级函数,有以下几种实现类名调用函数的办法

  - 第一种

     在.kt文件中直接写方法,不需要写class ,调用时 直接用函数名,导入该函数所在的类名即可

    ```kotlin
    //Utils.kt
    //class{
    fun1(){}
    fun2(){}
    fun3(){}
    fun4(){}
    //}
    ```

    kt使用

    ```kotlin
    import xx.xx.utils.UtilsKt
    var ff=fun1()
    ```

    java 种使用

    - 在java中调用顶层函数时需要用类名+Kt调用

    ```java
    UtilsKt.fun1(x);
    ```

  - 第二种

    - 可以使用 object 修饰类名使其作为一个静态工具类
    - 使用object修饰类名表示自动给该类创建一个单例对象,并通过单例对象来调用该类中的函数

    ```kotlin
    object Utils{
        fun1(){}
    }
    ```

    kt调用时

    ```java
     Utils.fun();
    ```

    java调用

    ```java
     Utils.INSTANCE.fun();
    ```

    

  - 第三种

    - 伴生对象(内部单例)

      ```kotlin
      class BaseApplication:Application(){
          companion object{
          	fun(){...}
      	}
      }
      
      ```

      kt调用时

      BaseApplication.fun()

      java调用时使用

      ```kotlin
      BaseApplication.Companion.fun()
      ```

  - 第四种

    - 通过注解实现(这个注解只能在object声明的类或伴生对象中使用)

      ```kotlin
      object className{
          @JvmStatic
          fun1(){...}
      }
      ```

      java调用

      ```java
      ClassName.fun1();
      ```

  - 第五种

    - 通过在文件头添加注解实现(该注解表示针对该文件生成在Jvm中的引用名)

      ```kotlin
      @file:JvmName(Utils)
      package xxx
      import xxx
      
      object Utils{
          fun1(){...}
      }
      ```

      java调用

      ```java
      Utils.fun1();
      ```

      

## 枚举

kt

``` kotlin
enum class State{
    PLAYBACK{
       override fun  StateName():String{
           return "有回放"
       }
    },
    LIVE{
       override fun  StateName():String{
           return "正在直播"
       }
    },
    WAIT{
       override fun  StateName():String{
           return "等待中"
       }
    }
    abstract fun stateName():String
}
```

java

```java
public enum State{
    PLAYBACK{
       public String StateName(){
           return "有回放"
       }
    },
    LIVE{
       public String StateName(){
           return "正在直播"
       }
    },
    WAIT{
       public String StateName(){
           return "等待中"
       }
    }
    public abstract String stateName();
}
```

## 注解

kt 

```kotlin
annotation class className(){}
```

java

```java
@interface
public class className(){}
```





[Kotlin 上手 (qq.com)](https://ke.qq.com/webcourse/404167/100481987#taid=3410354357283527&vid=5285890793361958565)

01:54:35