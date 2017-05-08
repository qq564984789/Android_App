
### 工具说明
Source Insight-> 阅读Liunx源码、驱动、写应用程序，但Android太多庞大，使用Android Studio来阅读源码、开发.

### 快捷方法
Ctrl+ Shift+ n:打开一个文件
Ctrl+ 单击：跳到定义处

### 第一个Android App:Hello world!

### 第二个Android App:显示www.ccit.js.cn
> 将activity_main.xml文件中TextView下的Hello world修改为www.ccit.js.cn
> activity_main.xml文件有两种模式：Design(显示效果、拖拽控件)、Text
> activity_main.xml在Android->app->res->layout下

layout（布局）：各种控件摆在一起
控件：按钮、复选框
activity:整个可视化界面

TextView：首字母大写，表示这是个类对象。控件的首字母都是大写
ctrl + h:查看类的继承关系  Button ，CheckBox都是View的子类
 android:layout_width="wrap_content"     （wrap_content：控件的宽度取决于里面的内容）

放入一个按键，方法：
输入<B，直接按下Tab键，这样可以自动输出开发者要设置的内容

fill_parent：大小填充整个窗口

TextView和Button的相对位置关系由Layout的属性决定，将RelativeLayout改成LinearLayout（线性布局），那么是水平线性还是垂直线性呢？
默认采用水平线性，可以先看效果。如何让它垂直排列呢？ 在`android:paddingBottom="@dimen/activity_vertical_margin" tools:context=".MainActivity"`后添加`android:orientation="vertical"`。

复选框：CheckBox
添加文字android:text="..."

### 第三个Android App:一个按钮、四个复选框
复选框内容分别为LED1,LED2,LED3,LED4
按钮的初始内容为ALL ON,按下按钮后，文字内容变成ALL OFF，同时四个LED复选框全部没有被选中。
再次按下，文字内容变成ALL ON，同时四个LED复选框全部被选中。

双击(Button)+ shift+ f1：搜索某一个类的使用（Button,CheckBox）

在MainActivity下添加私有属性 private Button button = null;接下来要将button对象和我们界面上的Button控件关联起来：在onCreate方法中输入;
button = (Button) findViewById(R.id.BUTTON);

在activity_main.xml下的Button下添加id属性：BUTTON,也就是下面一行
android:id="@+id/BUTTON"
在MainActivity下的BUUTON双击，alt+F7：查找引用，查看是否可以跳到BUTTON的定义处









TextView:首字母大写，表示这个控件是个类对象
res->layout->activity_main.xml
ctrl + h:查看类的继承关系  Button ，CheckBox都是View的子类
 android:layout_width="wrap_content"     （wrap_content：取决于内容）

fill_parent：宽度填充整个窗口
LinearLayout：线性布局

android:orientation="vertical">




双击+ ctrl+b:


make project:根据xml文件生成一些java源代码





View.OnClickListener是一个接口，因此我们可以自己来实现这个接口，在MainActivity类下输入
`class myButtonListener implements View.OnClickListener｛｝`,接下来在大括号中使用快捷键`ctrl+ i`,该快捷键会将需要实现的方法列出来，然后将前面`onClick`下的代码拷贝过来，放到这里的`onClick`下。
同时，我们还需要在onCreate方法中设置监听器`button.setOnClickListener(new myButtonListener());`
总结办法：1、创建一个类来实现监听器接口：View.OnClickListener   2、实例化这个类，并作为参数放入监听器


要选中某个控件，首先要获得这个控件的实例化对象，先定义：
`private CheckBox checkBoxled1 = null;`

接下来使用`findViewById`方法得到这个实例化对象
`checkBoxled1 = (CheckBox)findViewById(R.id.LED1);`

在前面的括号中使用`ctrl+shift+空格`来获得强制类型转换，而要获得实例化对象，必须首先知道这个控件的ID`LED1`,该id必须去activity_main.xml文件设置。

checkBoxled1.setChecked(）用于设置复选框是否被选中，


## 复选框单独被(非)选中时，调用某一个方法
首先，双击(CheckBox)+ shift+ f1，以此来查看CheckBox的使用，看到`See the Checkboxes guide.`点击`Checkboxes`后，参考实现。
我们这里使用一个Toast方法，当复选框被选中时，调用Toast方法`Toast.makeText(getApplicationContext(), "LED1 ON", Toast.LENGTH_SHORT).show();`





