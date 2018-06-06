# PrintUpcomingViewcontrollerName
工程中添加一个分类文件，可以打印出当前页面控制器的类名称

将demo中的UIviewController+Swizzling直接拖在项目中即可。

如果有控制器不需要打印，可以在过滤方法中添加类过滤
```
- (void)logViewWillAppear:(BOOL)animated {

NSString *className = NSStringFromClass([self class]);

//在这里，你可以进行过滤操作，指定哪些viewController需要打印，哪些不需要打印
// if ([className hasPrefix:@"AL"] == YES) {
NSLog(@"%@ will appear",className);
// }

//下面方法的调用，其实是调用viewWillAppear
[self logViewWillAppear:animated];
}


```
