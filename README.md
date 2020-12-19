# 这是一个我完成的期中项目———NotePad
## 这里我将会说明我的NotePad实现的一些功能和使用方法

### 首先是主页面
![img1](https://github.com/liuyi0322/NotePad/blob/master/img/%E4%B8%BB%E9%A1%B5%E9%9D%A2.png)
### 通过右上角的菜单中有可以新建note和搜索等功能
![img2](https://github.com/liuyi0322/NotePad/blob/master/img/菜单.png)

![img5](https://github.com/liuyi0322/NotePad/blob/master/img/新建note.png)

### 下面是每条笔记生成的同时生成时间戳

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

### 下面是在该NotePad中实现搜索笔记的功能

#### 首先我们应该在菜单的.xml文件中添加一个搜索图标

#### 然后新建一个实现SearchView.OnQueryTextListener接口的NoteSearch的Activity和其对应的布局文件来实现搜索功能
主要通过以下代码对数据表中的数据进行查询

public boolean onQueryTextChange(String string) {
        String selection1 = NotePad.Notes.COLUMN_NAME_TITLE+" like ? or "+NotePad.Notes.COLUMN_NAME_NOTE+" like ?";
        String[] selection2 = {"%"+string+"%","%"+string+"%"};
        Cursor cursor = sqLiteDatabase.query(
                NotePad.Notes.TABLE_NAME,
                PROJECTION, 
                selection1, 
                selection2, 
                null,          
                null,         
                NotePad.Notes.DEFAULT_SORT_ORDER 
        );
        String[] dataColumns = {
                NotePad.Notes.COLUMN_NAME_TITLE,
                NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE,

#### 然后在NoteList类中的onOptionsItemSelected方法中添加search查询的处理(跳转)

#### 搜索功能实现截图：

![img4](https://github.com/liuyi0322/NotePad/blob/master/img/搜索.png)








