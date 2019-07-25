#### css技巧解析：

>1、在div中使用contenteditable="plaintext-only"时，如果想要输入的文本不会出现奇怪的换行符，css中添加样式white-space: pre-wrap；

>2、任意高度元素实现高度过渡效果：使用max-height实现，

>3、非替换元素的before和after为元素才会生效，img没有src属性时，为元素可以用作展示替换字符，具体实现如下：

```
  img::after{
    content:attr(alt);
    position:absolte;
    bottom:0;
    width:100%;
    background-color:rgba(0,0,0,0.5);
    transform:translateY(100%);
    transition:transform .2s;
  }
  img:hover::after{
    transform:translateY(0);
  }
``` 
 >4、
 ``` 
 浮动float属性：
    1、设计初衷？：文字环绕效果
    2、float的取值？：Left：Right：None：Inherit：
    3、特性？；1）包裹性：2）破坏性：表现形式：父元素的高度塌陷
    4、如何清除浮动？：1）元素后加入clear：both的block水平元素；2）父元素触发BFC
    5、触发BFC的几种方式？：1）、float的值不为none；2）、overflow的值不为visible；3）、display的值为table-cell、tabble-caption和inline-       block之一；4）、position的值不为static或releative
    6、BFC特性？：1）BFC 阻止边距折叠（margin）2）BFC 阻止元素被浮动元素覆盖；3）BFC 包含浮动的元素：触发浮动元素的父元素的 BFC 特性，从而可以包     含浮动元素，清除浮动
    7、BFC应用？：1）自适应两栏布局；2）阻止margin重叠


    margin属性：
    1、取值类型？：1）数值型；2）百分比
    2、margin 属性百分比计算依据？：相对于元素的宽度计算
    3、margin合并场景？：1）上下相邻兄弟元素；2）副元素和第一个／随后一个字元素；3）空块级元素
    4、margin合并的计算规则？：1）符号相同，（正正取最大，负负取最小）；2）正负相加


    vertical-align属性；
    1、vertical-align作用元素？；内联元素／tabel-cell元素
    2、解析现象：
    为什么块级元素包含图片时 ，一般块级元素都会比图片的高度高一些？：与x文字基线有关，存在幽灵空白节点
    3、vertical-align：middle？：处置居中？只是近似垂直居中（由于幽灵空白节点占位）实际偏上，消除幽灵空白节点：font-size：0
``` 

