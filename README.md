NineGridView：九宫格图片显示器
====
类似微信朋友圈九宫格图片
------

### 使用方法:

**1.添加Gradle依赖：**
【最新版本号以[这里](https://github.com/Vanish136/NineGridView/releases)为准】

```
#last-verison请查看上面的最新版本号

#AndroidStudio3.0以下
dependencies{
         compile 'com.lwkandroid.widget:NineGridView:last-version'
    }

#AndroidStudio3.0以上
dependencies{
         implementation 'com.lwkandroid.widget:NineGridView:last-version'
    }
```
<br/>

**2.代码中使用[部分属性可直接在布局xml中定义]：**

```
//设置图片加载器，这个是必须的，不然图片无法显示
mNineGridView.setImageLoader(new GlideImageLoader());'
//设置显示列数，默认3列
mNineGridView.setColumnCount(4);
//设置是否为编辑模式，默认为false
mNineGridView.setIsEditMode(checkBox.isChecked());
//设置单张图片显示时的尺寸，默认100dp
mNineGridView.setSingleImageSize(150);
//设置单张图片显示时的宽高比，默认1.0f
mNineGridView.setSingleImageRatio(0.8f);
//设置最大显示数量，默认9张
mNineGridView.setMaxNum(16);
//设置图片显示间隔大小，默认3dp
mNineGridView.setSpcaeSize(4);
//设置删除图片
mNineGridView.setIcDeleteResId(R.drawable.ic_block_black_24dp);
//设置删除图片与父视图的大小比例，默认0.35f
mNineGridView.setRatioOfDeleteIcon(0.4f);
//设置“+”号的图片
mNineGridView.setIcAddMoreResId(R.drawable.ic_ninegrid_addmore);
//设置各类点击监听
mNineGridView.setOnItemClickListener(new NineGridView.onItemClickListener()
        {
            @Override
            public void onNineGirdAddMoreClick(int cha)
            {
                //编辑模式下，图片展示数量尚未达到最大数量时，会显示一个“+”号，点击后回调这里
            }

            @Override
            public void onNineGirdItemClick(int position, NineGridBean gridBean, NineGirdImageContainer imageContainer)
            {
                //点击图片的监听
            }

            @Override
            public void onNineGirdItemDeleted(int position, NineGridBean gridBean, NineGirdImageContainer imageContainer)
            {
                //编辑模式下，某张图片被删除后回调这里
            }
        });
```
<br/>

### 效果图:
![](https://github.com/Vanish136/NineGridView/raw/master/screenshoot/sample_pic_display.png) <br />
![](https://github.com/Vanish136/NineGridView/raw/master/screenshoot/sample_pic_edit.png)

### 混淆配置：

```
-dontwarn com.lwkandroid.widget.ninegridview.**
-keep class com.lwkandroid.widget.ninegridview.**{*;}
```

### 说明:
1.项目中有我写的另外一个库ImagePicker，用来选择手机里的图片，仅用做配合demo演示，实际开发可以去掉。<br/>
2.部分设计思路参考了github同名项目[NineGridView](https://github.com/jeasonlzy/NineGridView)，感谢为开源做出贡献的开发者们！
