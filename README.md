
- [x]网络层

***
###3.Android常用开源库
网络层： Retrofit或者Volley＋OkHttp，async-http-lib尽量就别用了，比较老。另外这些都需要再进一步扩展的，可以自己搜下，有用的就集成进去。  

数据库： GreenDao, Ormlite或者Realm，要加密的话用SqlCipher    
图片缓存： Fresco， glide，如果集成的效果不理想，多看看配置参数是否正确  

工具： 查内存泄漏（leakcanary）异步通知（RxJava谨慎使用）数学计算表达式（expression4j）日期处理（joda time android）

***
### 2.Exception常见异常及分析
一、IllegalStateException   内部错误  
jdk5.0文档中很清楚地介绍了出现IllegalStateException异常的可能情况:（程序遇到了内部错误）  
1）同一个页面中再次调用response.sendRedirect()方法。  
2）提交的URL错误，即不是个有效的URL。  
3）adapter内容改变但未进行NotifyDataSetChanged（）;  
二、java.lang.NullPointerException        空指针  
三、OutOfMemoryError                      内存溢出。  
Caused by: java.lang.OutOfMemoryError: Failed to allocate a 1504012 byte allocation with 1009122 free bytes and 985KB until OOM  

四、RuntimeException                          运行时异常。是所有Java虚拟机正常操作期间可以被抛出的异常的父类。
java.lang.RuntimeException: stop failed  

五、WindowManager$BadTokenException   当前View已经销毁。
Caused by: android.view.WindowManager$BadTokenException: Unable to add window -- token android.app.LocalActivityManager$LocalActivityRecord@412559c0 is not valid; is your activity running?  

六、IndexOutOfBoundsException         数组越界
java.lang.IndexOutOfBoundsException: Invalid index 12, size is 0

七、ClassCastException                     类型转换异常
java.lang.ClassCastException: java.lang.Object cannot be cast to com.actions.ibluz.manager.BluzManagerData$OnPListEntryReadyListener  类型转换异常

<font color=#0099ff size=5 face="黑体">八、ConcurrentModificationException</font>
在java中, 在对一些集合迭代的过程中对集合进行一些修改的操作, 比如说add,remove之类的操作, 搞不好就会抛ConcurrentModificationException, 这一点在API文档上也有说的!   在迭代时只可以用迭代器进行删除!
1.可使用CopyOnWriteArrayList。注意批量添加，减少内存开销，不能保证数据的实时一致性。
2.使用Iterator迭代器本身的remove。

***
### 1.Android 6.0系统注意事项(硬件设备)
1.根据Android官方文档：Android 6.0设备通过蓝牙和Wi-Fi扫描访问外部硬件设备时，你的应用需要添加ACCESS_FINE_LOCATION或者ACCESS_COARSE_LOCATION权限。
![](https://raw.githubusercontent.com/misparking/Daily-record/master/resources/images/hardware_20151107.png)
