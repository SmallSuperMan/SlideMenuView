# SlideMenuView
简单的侧滑抽屉效果封装
简书文章分享---> http://www.jianshu.com/p/f710e85115d9   

1： 将需要的关键数据初始化的时候获取（需要顶部每个页面对应的标题，还要知道要展示的页面，各自作为一个数组存入）。  

2： 在自定义的 View 上添加平移手势，当手指滑动的时候根据平移量，去具体判断要展示的视图是哪一个。

    2.1 左（右）滑动的时候，从数组中找到对应的下（上）一个展示的页面添加到自定义视图上（位置在当前页面的右（左）侧），并随着滑动一起滑动展现出来。
    2.2 停止滑动的时候判断是要展示哪一个页面，并将不展示的那一个移除掉。（使用动画）。
    2.3 这样的话最多的时候，我们需要两个展示页面！最后是只留一个我们看的那个页面。

3：顶部标题我是用了一个比较笨拙的方法，根据展示的页面数，创建对应的 Button 根据标题数组对应的给 Title，然后放在一个 ScrollView 上面。（有时间可以思考一下，可以对应的去改变展示 Button 名字不必创建那么多，好像一般也不会太多！）

    3.1 Button 点击时候操作逻辑不难，就是移除当前展示的页面，添加 Button 对应的页面即可。
    3.2 滑动手势结束的时候根据展示的页面，把对应的 Button 字体颜色和大小改掉即可（遍历 ScrollView 的子视图找到 Button 选中的特殊对待，其他另做对待就好）。

4：滑块是个 View，利用动画对应改变 Frame 就好了！
