# QuickIndexBar
这是一个快速索引的自定义控件
1.应用场景:联系人，好友列表，商品等列表的快速定位和搜索
2.实现逻辑:
	a.右边是自定义QuickIndexBar,它能获取触摸它的时候当前所触摸到的字母;
	  绘制文本x坐标: width/2;
	  绘制文本y坐标: 格子高度的一半 + 文本高度的一半 + position*格子高度
	  计算触摸点对应的字母:根据触摸点的y坐标除以cellHeight,得到的值就是字母对应的索引;
	  
	b.左边是listview，它根据当前触摸的字母，去自己列表找首字母和触摸字母相同的那个
	item，然后让item放置到屏幕顶端(setSelection(position));
	
	c.需要用到获取汉字的拼音,借助类库pinyin4j.jar实现;