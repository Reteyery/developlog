1、模块功能

    FragmentMagicMirror、FragmentRecommend、FragmentCommon、FragmentShop

2、HttpVolleyBase完成网络请求

    功能通过相应的Factory完成请求创建
    通过parseNetworkResponse方法拿到网络请求返回数据，数据存在则三级缓存，不存在就返回异常

3、FragmentRecommend首页推荐

    HomeCateDataCms:显示当前推荐页有几个模块，每个模块占几行，每个模块含有多少个子模块
    screen_name='今日热播', screen_index='1', screen_line_number=1, screen_type='0', block_number='8'
    screen_name='强档推荐', screen_index='2', screen_line_number=2, screen_type='0', block_number='11'
    eg:今日热播模块是第一个模块占一行，子模块有八个；强档推荐模块是第二个模块占两行，子模块有十一个

    HomeItemCms{
        begin_time='', nav_id='null', category_id='', 
        content_id='10314841', content_type='102', corner_marks='http://img.ottnew.cp61.ott.cibntv.net/image/11/40f0ae8c602248f3a9a677c5724b1537.png', element_index='1', element_style='1', element_sub_title='', element_title='忍者神龟：破影而出', end_time='', link_package=JumpPrams{action='', package_name='com.pptv.launcher', class_name='com.pptv.launcher.ChannelDetailActivity', params={fromtag=54, DETAIL_ID_EXTRA=10314841}}, live_id='', live_supportad='0', package_name='', recommend_h_pic='', recommend_pic='http://img.ottnew.cp61.ott.cibntv.net/image/c2/9b/c29bf3cc628cae81c7d5af18b31d4031.jpg', recommend_s_pic='', recommend_v_pic='', vod_id='', vt='0', vs_title='', vs_value='', dou_ban_score='', goodsnumber='null', shopCode='null', goodsprice='null', goodsimage='null', goodsname='null', is_goods='null', isFrequentedApp='null', page_url='null', appver='', block_name='null', program_source='PPTV'}

    HomeItemCms是内容数据，recommend_pic为封面图片，corner_marks为封面角标，角标内容eg:会员用券、SVIP

