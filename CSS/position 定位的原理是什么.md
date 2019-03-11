# position 定位的原理是什么?

absolute: 生成绝对定位的元素，相对于static定位以外的第一个父元素进行定位。元素的位置通过left,top,right以及bottom属性进行规定。

fixed: 生成绝对定位的元素，相对于浏览器窗口进行定位。元素的位置通过left、top、right以及bottom属性进行规定。

relative: 生成相对定位的元素，相对于其正常位置进行定位。

static: 默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。

inherit: 规定应该从父元素继承 position 属性的值。