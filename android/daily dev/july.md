1、Fragment、pagerAdapter使用问题

    fragment在使用pagerAdapter管理时会出现数据无法显示的问题，这种情况在动态加载fragment时会出现
    eg:在做搜索功能时，根据关键字会查询出许多栏目。第一次查询可以显示所有栏目及内容；再次查询会出现部分栏目不显示内容的情况，问题出在pagerAdapter, 处理方式: pagerAdapter继承FragmentStatePagerAdapter，同时重写
    @Override
    public int getItemPosition(@NonNull Object object) {
        return POSITION_NONE;
    }

    返回值为PagerAdapter.POSITION_NONE
    