# KNDragView
```

pod  KNDragView

🚀  KNDragView (1.0.3) successfully published
📅  June 24th, 19:57
🌎  https://cocoapods.org/pods/KNDragView
👍  Tell your friends!

```

####  pod trunk push

```
➜  AXWebViewController git:(master) ✗ kngit 0.7.4
➜  AXWebViewController git:(master) git tag -a 0.7.4 -m "0.7.4"                                           
➜  AXWebViewController git:(master) git push origin --tags                                                
➜  AXWebViewController git:(master) ✗ pod lib lint KNAXWebViewController.podspec --allow-warnings --no-clean

pod trunk push  KNAXWebViewController.podspec --allow-warnings


```




# WMDragView
拖吗？拖！拖就用WMDragView吧。WMDragView致力于让任意View都可以自由移动、悬浮、拖动、拖曳。WMDragView是可以自由拖曳的view，可以悬浮移动，也可以设置内部的图片，轻量级的控件。

## 功能
- [x] 可设置拖动的范围rect
- [x] 可获得拖曳回调和点击回调
- [x] 可选择是否有黏贴边缘的动画效果
- [x] 可设置网络图片
- [x] 支持自定义view




#WMDragView：用法和API

1、把需要拖曳view的父类从原本继承UIView，改成继承WMDragView就OK了。

2、dragEnable=YES，可拖曳

   dragEnable=NO，不可拖曳
   
3、freeRect可以任意设置活动范围，默认为活动范围为父视图大小frame，

4、回调block

	点击的回调		clickDragViewBlock
	
	开始拖动的回调		beginDragBlock
	
	拖动中回调		duringDragBlock
	
	结束拖动的回调 	endDragBlock
	
5、isKeepBounds是不是又自动黏贴边界效果

 isKeepBounds = YES，自动黏贴边界，而且是最近的边界
 isKeepBounds = NO， 不会黏贴在边界，它是free(自由)状态，跟随手指到任意位置，但是也不可以拖出规定的范围

6、可以设置网络图片

7、可以自定义view加到dragView中，比如一个视频，一个自定义按钮等等
# DragView
```
- (WMDragView *)orangeView{
if (nil == _orangeView) {
WMDragView *tmpView = [[WMDragView alloc] initWithFrame:CGRectMake(0, 0 , kAdjustRatio(60), kAdjustRatio(60))];

_orangeView = tmpView;
[self addSubview:_orangeView];
__weak __typeof__(self) weakSelf = self;


//        tmpView.button.titleLabel.font = [UIFont systemFontOfSize:15.0];
//        [tmpView.button setTitle:@"可拖曳" forState:UIControlStateNormal];
tmpView.backgroundColor = [UIColor clearColor];
//
//        tmpView.layer.cornerRadius = 14;// layoutsubview

//设置显示图片方式一：
tmpView.imageView.image = [UIImage imageNamed:@"icon_dayin"];
//设置显示图片方式二：
//    [logoView.button setBackgroundImage:[UIImage imageNamed:@"logo1024"] forState:UIControlStateNormal];



[_orangeView mas_makeConstraints:^(MASConstraintMaker *make) {
make.size.mas_equalTo(CGSizeMake(kAdjustRatio(60), kAdjustRatio(60)));

make.right.equalTo(weakSelf).offset(kAdjustRatio(-20));

make.bottom.equalTo(weakSelf).offset(kAdjustRatio(-90));

}];

tmpView.clickDragViewBlock = ^(WMDragView *dragView){

NSLog(@"处理记录打印");
//            [self.navigationController pushViewController:[TestViewController new] animated:YES];
};





}
return _orangeView;
}


```
