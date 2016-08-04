[![Android Gems](http://www.android-gems.com/badge/saiwu-bigkoo/Android-AlertView.svg?branch=master)](http://www.android-gems.com/lib/saiwu-bigkoo/Android-AlertView)

# Android-AlertView
仿iOS的AlertViewController
几乎完美还原iOS 的 AlertViewController ，同时支持Alert和ActionSheet模式，每一个细节都是精雕细琢，并把api封装成懒到极致模式，一行代码就可以进行弹窗.

## Demo
![](https://github.com/saiwu-bigkoo/Android-AlertView/blob/master/preview/alertviewdemo.gif)

demo是用Module方式依赖，你也可以使用gradle 依赖:
```java
   compile 'com.bigkoo:alertview:1.0.3'
```

### config in java code
```java
new AlertView("上传头像", null, "取消", null,
                new String[]{"拍照", "从相册中选择"},
                this, AlertView.Style.ActionSheet, new OnItemClickListener(){
                    public void onItemClick(Object o,int position){
                        Toast.makeText(this, "点击了第" + position + "个", 
                        Toast.LENGTH_SHORT).show();
                    }
                }).show();
                
//或者builder模式创建
new AlertView.Builder().setContext(context)
                .setStyle(AlertView.Style.ActionSheet)
                .setTitle("选择操作")
                .setMessage(null)
                .setCancelText("取消")
                .setDestructive("拍照", "从相册中选择")
                .setOthers(null)
                .setOnItemClickListener(listener)
                .build()
                .show();
```
```java
new AlertView("标题", "内容", null, new String[]{"确定"}, null, this, 
                AlertView.Style.Alert, null).show();
```
另外还支持窗口界面拓展，更多操作请下载Demo看。
