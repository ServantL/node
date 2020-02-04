# SpringBoot 当前端form表单为put或delete提交方式的那点事

##  了解组合注解：

* **@PutMapping(" ")  =  @RequestMapping（value=" ",method = RequestMethod.PUT)**

* **@PutMapping(" ")  =  @RequestMapping（value=" ",method = RequestMethod.PUT)**

* **@PutMapping(" ")  =  @RequestMapping（value=" ",method = RequestMethod.PUT)**

* **@PutMapping(" ")  =  @RequestMapping（value=" ",method = RequestMethod.PUT)**

## 问题由来：将普通的CRUD改为Restful风格

![image-20191120224503736](C:\Users\Servant\AppData\Roaming\Typora\typora-user-images\image-20191120224503736.png)



#### 后台controller代码

![image-20191120223818732](C:\Users\Servant\AppData\Roaming\Typora\typora-user-images\image-20191120223818732.png)



#### 前端form表单代码（以put提交方式为例）

![image-20191120225357927](C:\Users\Servant\AppData\Roaming\Typora\typora-user-images\image-20191120225357927.png)

* 因为前端只支持 get 和 post 两种方式，所以需要加入一个隐藏域来修改表单的提交方式（这样就可以起到饶过浏览器不符合，即欺骗浏览器的意思）
* **注意：**该隐藏域的 name 必须为 _method ，而 value 值即为表单的提交方式，且form的提交方式要为post
* **原理：**
  * 1）、springboot 为我们配置了 ==HiddenHttpMethodFilter== 
  * 2）、==HiddenHttpMethodFilter== 为我们进行了浏览器表单提交方式的修改
    * 源码：
      * ![image-20191120230147072](D:\Typora\data\springboot\images\image-20191120230147072.png)
      * ![image-20191120230709365](D:\Typora\data\springboot\images\image-20191120230709365.png)



## 所以只要经过上面简单的设置就可以修改from表单的提交方式了，但是我这里依然还是报错了

后来再查看了源码才发现**版本**原因引起的

**springboot   2**以上的版本==HiddenHttpMethodFilter== 默认没有开启

后在这补充源码图！！！！







