1、git拉取远程分支到本地

    git clone 远程分支.git
    git branch -a  //查看远程分支
    git checkout -b name remote/name //拉取远程分支代码并切换到当前分支下工作，name为本地新建分支名， remote为远程分支
    
    git push mojing HEAD:refs/for/suningos1.0

2、CollapsingToolbarLayout与AppBarLayout使用是高度问题处理

    在使用嵌套布局做动效的时候会出现AppBarLayout高度多出来一块的情况，处理方式  android:fitsSystemWindows="false" 或者true, 两者的fitsSystemWindows属性需要同为true 或者false
    <android.support.design.widget.CoordinatorLayout
        android:id="@+id/main_content"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        app:layout_constraintTop_toBottomOf="@id/iv_search"
        app:layout_constraintBottom_toBottomOf="parent"
        android:fitsSystemWindows="false">

        <android.support.design.widget.AppBarLayout
            android:id="@+id/appbar"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:fitsSystemWindows="false"
            android:background="@color/os_all_page_bg"
            android:theme="@style/AppBarThemes.NoBar">

3、使用support design包时报错 需要给相应的design组件设置theme   

    比如布局中使用TabLayout，则需要给TabLayout设置theme属性

4、使用amend追加提交信息

    在代码还没有merge到仓库时，使用git commit --amend -m "" 追加提交信息


    
    