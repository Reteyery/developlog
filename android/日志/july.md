1、Fragment、pagerAdapter使用问题

    fragment在使用pagerAdapter管理时会出现数据无法显示的问题，这种情况在动态加载fragment时会出现
    eg:在做搜索功能时，根据关键字会查询出许多栏目。第一次查询可以显示所有栏目及内容；再次查询会出现部分栏目不显示内容的情况，问题出在pagerAdapter, 处理方式: pagerAdapter继承FragmentStatePagerAdapter，同时重写
    @Override
    public int getItemPosition(@NonNull Object object) {
        return POSITION_NONE;
    }

    返回值为PagerAdapter.POSITION_NONE
    
2、gradle连接外网访问依赖库失败问题

    访问外网如果失败，可以借助aliyun国内镜像，eg:

    repositories {
        google()
        jcenter()
    }

    以访问jcenter()为例，将其替换为镜像地址 
    jcenter {url 'https://maven.aliyun.com/repository/jcenter'}

    阿里云镜像地址: http://maven.aliyun.com/mvn/view