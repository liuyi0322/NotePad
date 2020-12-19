# 这是一个我完成的期中项目———NotePad
这里我将会说明我的NotePad实现的一些功能和使用方法

## 首先是主页面
![img1](https://github.com/liuyi0322/NotePad/blob/master/img/%E4%B8%BB%E9%A1%B5%E9%9D%A2.png)
## 通过右上角的菜单中有可以新建note和搜索等功能
![img2](https://github.com/liuyi0322/NotePad/blob/master/img/菜单.png)
## 下面是每条笔记生成的同时生成时间戳

在noteslist_item的布局文件里添加一个TextView来显示时间戳
<TextView
        android:id="@+id/text2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingLeft="5dip"
        android:singleLine="true"
        android:gravity="center_vertical"
/>
然后修改时间戳的格式为yy.MM.dd HH:mm:ss

再在创建数据表和列的投影PROJECTION中添加上修改时间即可

效果如下

![img3](https://github.com/liuyi0322/NotePad/blob/master/img/时间戳.png)

## 下面是在该NotePad中实现搜索笔记功能





