# zdyzj

Lesson98 自定义组件
1. 自定义组件的三种实现方式：
   --组合现有Android默认提供的组件：继承ViewGroup或其子Layout类等布局进行组合；
   --调整现有Android默认提供的组件：继承View的子类具体类;
   --完全自定义组件：继承View基类，里面界面及事件完全由自己控制。

2.实现自定义组件
  --配合XML属性资源文件的方式：
    --第一步：attrs.xml文件。首先当然是要写出自定义组件的类文件了，然后将这个类里需要外界传入值的属性定义成一个属性资源文件，在工           程里的../res/values目录下创建一个attrs.xml文件，文件名并不是只能写成这样，这样写只有一个目的，别人一看就知道这个文
              件是属性资源文件，具体写法如下：
              <?xml version="1.0" encoding="utf-8"?>
              <resources> //values目录下的所有xml的根标签是resources
              <declare-styleable name ="MyView">   //定义一个可能的样式，并取个名称
                  <attr name="textColor" format="color"/> //定义提供的属性名称，format是属性值的格式,格式在anroid中是固定的
                  <attr name="textSize" format="dimension"/>
                  <attr name="text" format="string"/>
              </resources>
        --attr子元素：定义具体的属性，format表示这个属性的值的类型，类型有以下几种：
          --reference:参考指定Theme中的资源ID，这个类型的意思是你传的值可以是引用资源；
          --string:字符串，如果你想别人既能直接写值也可以用类似”@string/test/"引用资源的方式,可以写成format="string|refence"；
          --Color:颜色
          --boolean:布尔值
          --dimension:尺寸值
          --float:浮点型
          --integer:整形
          --fraction:百分数
          --enum:枚举,表示只能在几个值中选一个
                <attr name="language">
                  <attr name="china" value="1"/> //value是具体定义的值
                  <attr name="English" value="2"/>
                </attr>
          --flag:位或运算
        
