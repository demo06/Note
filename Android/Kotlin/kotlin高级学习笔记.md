# Kotlin高级教程学习笔记

## 构造方法

- kt中构造方法可直接写再类名后
- init初始化与静态代码块不同

kotlin

```kotlin
constructor()

constructor(name:String?,age:String?){
    this.name=name
    this.age=age
}
```

或使用主构造器方法

```kotlin
class User constructor(name:String?,age:String?){	
    var name:String?=null
    var age:String?=null
    constructor():this()
    //初始代码块
    init {
        this.name=name
        this.age=age
	}
}
```

可进一步优化为

- 再构造方法的参数中直接声明var或val ,构造方法会自动生成对应的成员变量或常量

```
class UserInfo constructor(var name: String?, var age: String?) {
}
```

## DataClass

- 数据类
- 用户保存对象
- 使用data关键字声明
- 数据类重写了.equals()方法

kotlin

```kotlin
data class User constructor(var name: String?, var age: String?) {}
```

## Elvis 表达式

- 与if表达式类似,使用?:关键字 条件为true 则取?:前的值,false则取?:后的值

- 类似三元运算符

kotlin 

```kotlin
val l = b?.length ?: -1
```

## Filter函数

- 一般在for循环中使用,及其方便

kotlin

```kotlin
user.filter{
    it.name=User.name
}
```

java

```java
for (User user:users ){
    if(user.name==users.getname){
        xxx
    }
}
```

## 循环



kotlin

```kotlin
repeat(100){
    println(it)
}
```

## Lembda表达式

- 在 Kotlin 中有一个约定，如果函数的最后一个参数是一个函数，并且你传递一个 lambda 表达式作为相应的参数，你可以在圆括号之外指定它

未简化前

```kotlin
repeat (100,{
    println(it)
})
```

简化后

```kotlin
repeat(100){
    println(it)
}
```

## 函数参数默认值

- 当出现单参数函数调用多参数函数时可以给参数设置默认值达到一样的效果
- 调用单参数时,函数自动设置其他参数为默认值

```kotlin
fun toast(string:String?){
    toast(string,Toast.LENGTH_SHORT)
}
fun toast(string:String?,duration:Int){
    Toast.makeText(context,string,duration).show
}
```

此函数则可直接设置为

```kotlin
fun toast(string:String?,duration:Int =Toast.LENGTH_SHORT){
    Toast.makeText(context,string,duration).show
}
```

当在java中调用该方式的函数时将出现异常,则可以在使用默认值函数上添加@jvmOverloads注解即可解决

- @jvmOverloads 注解将会生成多个方法供java调用



学习到 59:37处

[Kotlin 进阶 (qq.com)](https://ke.qq.com/webcourse/404167/100481987#taid=3410358652250823&vid=5285890793310554963)

