css技巧解析：

1、在div中使用contenteditable="plaintext-only"时，如果想要输入的文本不会出现奇怪的换行符，css中添加样式white-space: pre-wrap；

2、任意高度元素实现高度过渡效果：使用max-height实现，

3、非替换元素的before和after为元素才会生效，img没有src属性时，为元素可以用作展示替换字符，具体实现如下：
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
