# margin 折叠

[margin系列之外边距折叠](http://blog.doyoe.com/2013/12/04/css/margin%E7%B3%BB%E5%88%97%E4%B9%8B%E5%A4%96%E8%BE%B9%E8%B7%9D%E6%8A%98%E5%8F%A0/)

外边距用来指定非浮动元素与其周围盒子边缘的最小距离。两个或两个以上的相邻的垂直外边距会被折叠并使用它们之间最大的那个外边距值。多数情况下，折叠垂直外边距可以在视觉上显得更美观，也更贴近设计师的预期。

发生折叠需要是相邻的非浮动元素；

折叠发生在垂直外边距上，即margin-top/margin-bottom；

折叠后取其中最大的那个margin值作为最终值；

在水平书写模式下，发生 margin 折叠的是垂直方向，即 margin-top/margin-bottom，在垂直书写模式下，margin 折叠发生在水平方向上，即 margin-right/margin-left。