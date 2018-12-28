##DART记录##

一、小记

    1.Dart 没有 public、 protected、 和 private 关键字。如果一个标识符以 (_) 开头，则该标识符 在库内是私有的

    2.使用 final 或者 const。 一个 final 变量只能赋值一次；一个 const 变量是编译时常量。 （Const 变量同时也是 final 变量。）

    3.Flutter UI

        1.Container: 一个拥有绘制、定位、调整大小的 widget
        2.Row: 在水平方向上排列子widget的列表
        3.Column: 在垂直方向上排列子widget的列表
        4.RaisedButton: Material Design中的button， 一个凸起的材质矩形按钮
        5.Scaffold：Material Design布局结构的基本实现。此类提供了用于显示drawer、snackbar和底部sheet的API
        6.Appbar：一个Material Design应用程序栏，由工具栏和其他可能的widget（如TabBar和FlexibleSpaceBar）组成
        7. 其它：
            Text: 单一格式的文本 
            Image: 一个显示图片的widget

二、问题

    1.在DART中如何反转一个字符串

        https://stackoverflow.com/questions/21521729/how-do-i-reverse-a-string-in-dart
