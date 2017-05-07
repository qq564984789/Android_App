### 1、控件布局的基本概念
所谓控件布局方法，是指控制控件在Activity当中的位置、大小、颜色及其他控件样式属性的方法。
### 2、控件布局的种类
使用布局文件完成控件布局：比较死板
Java代码完成控件布局：灵活，可动态添加/变化
### 3、各类布局方法的特点
LinearLayout：最简单
RelativeLayout:最常用
ListView:AdapterView的子类
GridView:AdapterView的子类
### 4、线性布局的基本使用方法
1、在layout文件夹右键，新建一个xml文件，选择LinerLayout布局
2、看到xml文件，xml文件中有且仅有一个根元素：<LinerLayout> .....</LinearLayout>，这是xml文件的语法，
   <TextView/>,<Button/>都是根元素LinerLayout里的子元素，所以遵守根元素的一些规则
   
   
距离单位值px,dp,sp
px：像素。假设屏幕分辨率为480*800，如果定义一个文本的宽度为240px，那么它会占据屏幕一半的宽度
dpi(dots per inch):分辨率，即每英寸上的点个数。计算公式：分辨率=对角线上像素的个数/对角线长度
                                            对角线上像素的个数等于长度像素数和宽度像素数开根号（勾股定理）
                                            4.3英寸的屏幕表示屏幕对角线长度为4.3英寸，两块同为4.3英寸的屏幕分辨率可能不同（细腻程度不同）
可以看出，px是一个绝对值（屏幕像素个数），而dpi是个相对值（屏幕像素个数/屏幕对角线）
dp=dip(Device Independent pixels):Android规定，在dpi为160的屏幕上，1dp =1 px.可得换算公式：px=dp*(dpi/160),带入相同的dp值，可得到不同的px值
sp:随着用户设置的字体大小而改变。
总结：一般设置控件的高度、宽度使用dp,字体大小用sp.
控件的外边距与内边距

padding:内边距(控件边缘和空间内容的距离)
layout_margin:外边距（控件边缘和另一个控件边缘的距离）

> setText(i + "");  setText本来只能显示字符串，这里使用了一个 + “”的技巧
布局文件(layout)中的每一个控件必然对应Java代码(MainActivity)中的一个对象，对象通过调用不同的方法来修

改控件。
setText
setBackground

wrap_content:包含自己的内容
match_parent:匹配父控件
