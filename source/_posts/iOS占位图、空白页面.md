---
title: iOS占位图、空白页面
categories: [iOS]
---
# [iOS占位图、空白页面 Github直达](https://github.com/xxxIxxxx/XXXPlaceholder)
# iOS占位图、空白页面 适用于view、tableView、collectionView、scrollvew
# 😄😄😄
![tableView使用效果](http://upload-images.jianshu.io/upload_images/2331323-337781e6ecaac4ae.gif?imageMogr2/auto-orient/strip)

 ![view使用效果](http://upload-images.jianshu.io/upload_images/2331323-37d81ba5477c72c3.gif?imageMogr2/auto-orient/strip)
 
# *注意*
##### 1.当tableView、collectionView 有数据时（row>0，item>0）不显示占位图
##### 2.当scrollView.contentSize.height > scrollView.frame.size.height 时临时禁用滑动属性（tableView、collectionView优先遵循第一条）
##### 3.建议导入demo中的XXXPlaceholderEX文件夹
##### 4.占位图中的button会自动添加点击事件，无需添加。没有button会给整个占位图添加点击事件
##### 5.我觉得用法还是挺简单的，看下demo吧😂

### 使用
```
pod repo update
rm ~/Library/Caches/CocoaPods/search_index.json  (清除搜索缓存)
pod 'XXXPlaceholder', '~> 0.0.1'
```
1. 参照demo创建占位图

 ```
  //self为tableView
  self.xxx_emptyView = [XXXPlaceholderView emptyView];
  self.xxx_noNetworkView = [XXXPlaceholderView noNetworkView];
  //占位图会自动添加点击事件

 ```
2. tableView、collectionView 展示占位图调用

    ```
    /**
    刷新数据源 tableView、collectionView专用
    */
    - (void)xxx_reloadData;
 
    /**
    刷新数据源 tableView、collectionView专用
    @param clickBlock 占位图点击事件Block
    */
    - (void)xxx_reloadDataWithClickBlock:  (nullable   XXXPlaceholderClickBlock)clickBlock;
    
    [self.tableView xxx_reloadDataWithClickBlock:^{
               //这里做再次请求
            }];
    ```
3. view使用 

    ```
    /**
    展示无数据占位图
    */
   - (void)xxx_showEmptyView;

    /**
   展示无数据占位图
   @param clickBlock 占位图点击事件Block
   */
   - (void)xxx_showEmptyViewWithClickBlock:(nullable XXXPlaceholderClickBlock)clickBlock;

    /**
   展示无网络占位图
   */
   - (void)xxx_showNoNetWorkView;

    /**
   展示无网络占位图
   @param clickBlock 占位图点击事件Block
   */
   - (void)xxx_showNoNetWorkViewWithClickBlock:(nullable XXXPlaceholderClickBlock)clickBlock;

    /**
    移出所有占位图
    */
   - (void)xxx_removePlaceholderView;
    
    ```
# [Github直达](https://github.com/xxxIxxxx/XXXPlaceholder)
