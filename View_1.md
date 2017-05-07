## View初步（一）
### 1、什么是View?
在Activity上面显示的所有控件，在Android中的学名都叫View。为什么Android里这么称呼呢？因为Android中的控件都对应一个对象，而对象都是由类生成的，Android中的所有控件：如TextView、Button这些都是View的子
类。各种控件那么多，如何了解呢？古语“有其父必有其子”的启示就是，要了解子类必须先了解父类！先从历史的起点开始！

### 2、如何在Activity当中获取代表View的对象?
   `TextView textView = (TextView)findViewById(R.id.textView);`
   
注意：这个textView控件对象不是我们新建（new）的哦！为什么呢？实际上，Activity读取布局文件的时候会自动创建这样一个对象，我们不过是通过这个对象的ID（R.id.textView），使用findViewById这个方法把这个控件
对象找出来而已！为什么要向下类型转换(TextView)呢？因为一个布局文件中有各种各样的View,通过findViewById(）方法可以将不同类型控件的对象都找到，所以返回值统一成View类型。

### 3、设置View的属性
a.在布局文件中修改       b.在Java代码中修改   textView.setText();           textView.setBackground();

### 4、为View设置监听器
什么是监听器呢？一种对象：监控控件对象状态的变化。什么是监控控件对象状态的变化呢？比如当一个按钮被点击、长点击、滑动等事件发生，这样控件就会通知监听器，监听器得到通知后，就会执行一定操作。一个控件可以有多个监听器，因为有多种事件可能发生在某个控件上。那么如何为某个控件设置监听器呢？
> 1.获取控件对象
`Button button = (Button)findViewById(R.id.button);`

> 2.自定义一个监听器类、实现监听器接口

```java
class MyButtonListener implements OnClickListener{
   public void onClick(void){     //覆写 onClickListener中的方法
   }
}
```

注意：onClickListener导入的是android.view.View.OnClickLitener.

> 3.生成监听器对象
`MyButtonListener myButtonListener = new MyButtonListener()`

> 4.为控件绑定监听器对象
`button.setOnClickListener(myButtonListener)`
