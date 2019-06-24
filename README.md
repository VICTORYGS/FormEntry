# FormEntry
录入类型表单自动绑定到Vue的工具 产出一个经过Vue绑定后的table标签  
首先要将要做的表单 录入到excel中 并根据配置要求 在Excel文件中进行相应的设置 最后执行exe文件即可


 ![image](https://github.com/VICTORYGS/FormEntry/blob/master/explain.png?raw=true)  
 每个自动绑定的标签的值 将会双向绑定到一个数组中(索引会自动递增) 并绑定了一个点击事件(方便一些特殊内容的点击输入)  

***下面是配置的说明***  
    
[conf]  
#注意  
#*程序会自动读取当前目录下的xlsx文件  
#*数据处理完成会自动拷贝到系统的剪贴面板中  
#*没有任何数据的单元格 请space一个空格占位  
#*替代符号不要和所在单元格中的内容有冲突  
#*替换符号也不能出现在另一个替换符号中(分别处于独占和混用模式下的替换符可以无视此规则)  


#存储的数组名称  
SaveList= andyList  

#----------独占模式 start------------  
#替代符号独自占据一个单元格的情况(存在单元格合并的情况&m=2 也是可以生效的)  
#其实混用模式已经足够实现功能了,为了某些情况下方便可使用独占模式  
#复选框  
Checkbox=  C  
#输入框  
Text= I  
#时间控件  
TimeComponent= T  
#textarea输入框  
TextArea= A  
#----------独占模式 end------------  


#----------混用模式 start------------  
#替代符号和其他内容混用时候  
#复选框  
CheckboxMixin=□  
#输入框  
TextMixin= $I  
#时间控件  
TimeComponentMixin= $T  
#textarea输入框  
TextAreaMixin= $A  
#----------混用模式 end------------  

#合并数据的分隔符(必须写在内容的最后面) xxxxx&m=2 值为正数则为横向合并 负数则为竖向合并  
MergerSplit= &  


#这里使用的elementUI的时间控件 el-date-picker  
TimeComponentContent= is="el-date-picker" type="datetime" format="yyyy-MM-dd HH:mm" value-format="yyyy-MM-dd HH:mm"  
