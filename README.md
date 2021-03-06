# XPQRotateMenu
## 由来
这个扇形菜单是从仿照ZQLRotateMenu（https://github.com/zangqilong198812/ZQLRotateMenu ）开始的，然后慢慢的完善扩展。
## 效果图

![Flipboard playing multiple GIFs](https://github.com/xiepanqi/XPQRotateMenu/blob/master/Dome.gif)
## 使用
使用此菜单只需把（XPQRotateItem.h/XPQRotateItem.m/XPQRotateMenu.h/XPQRotateMenu.m/XPQRotateMenuDelegate.h）5个文件导入工程，再在需要的试图控制器类中添加

    #import "XPQRotateMenu.h"
然后再在viewDidLoad中添加以下3句代码就行了。

    NSArray *arr = @[@"菜单1",@"菜单2",@"菜单3",@"菜单4",@"菜单5",@"菜单6",@"菜单7",@"菜单8",@"菜单9"];
    XPQRotateMenu *menu = [[XPQRotateMenu alloc] initWithTitleArray:arr];
    [self.view addSubview:menu];

##属性详解
当然，如果想使菜单具有更好的效果就需要设置相应的属性，下面就来详细介绍XPQRotateMenu中的属性。
###time
菜单展开或收缩动画的耗时，单位秒，默认值0.75s。
###backgroundColor
菜单展开时背景色。展开过程中背景色由透明慢慢变成backgroundColor，收缩过程背景色则由backgroundColor慢慢变成透明。
默认值是灰色（r:0.5 g:0.5 r:0.5 a:1.0）。
###expand（isExpand）
菜单是否展开，只读属性。展开时为YES，收缩时为NO。
###isUpToTop
是否上方菜单放上面。这个文字有点表达不清楚，下面贴两张效果图。默认值是YES。

![Flipboard playing multiple GIFs](https://github.com/xiepanqi/XPQRotateMenu/blob/master/ReadMeImage/isUpToTop_YES.png)
![Flipboard playing multiple GIFs](https://github.com/xiepanqi/XPQRotateMenu/blob/master/ReadMeImage/isUpToTop_NO.png)
###intersectionImage
交汇按钮图片，如果为nil则显示字符“➕”。默认为nil。
###backgroundImage
菜单展开时的背景图片，展开过程中背景图慢慢显示，收缩过程中慢慢消失。默认为nil。
###showClockwise
菜单展开动画是否沿顺时针。YES顺时针展开，NO逆时针展开。默认YES。
###hideClockwise
菜单收缩动画是否沿顺时针。YES顺时针展开，NO逆时针展开。默认NO。
###handleHideEnable
是否启用手势收缩菜单。启用后上下滑动手势可以收缩菜单，上滑逆时针收缩，下滑顺时针收缩。默认YES。
###dependPosition
菜单吸附的位置。枚举XPQRotateMenuDependPosition类型，暂只支持XPQRotateMenuDependPositionLeft和XPQRotateMenuDependPositionRight。效果如下：
![Flipboard playing multiple GIFs](https://github.com/xiepanqi/XPQRotateMenu/blob/master/ReadMeImage/XPQRotateMenuDependPositionLeft.png)
![Flipboard playing multiple GIFs](https://github.com/xiepanqi/XPQRotateMenu/blob/master/ReadMeImage/XPQRotateMenuDependPositionRight.png)
###delegate
代理
