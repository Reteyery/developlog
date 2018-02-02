1、webview使用记录
	1、拦截请求跳转有两个loding方法，shouldOverrideUrlLoading，参数方式不一样
	api < 24 使用 shouldOverrideUrlLoading(WebView view, final String url);
	api >= 24 使用 shouldOverrideUrlLoading(WebView view, final WebResourceRequest request)
	request提供获取uri的方法
	当返回值为false weview自己处理网络请求；返回值为true时,可以控制请求跳转至app原生界面或者消费掉下一次请求，使页面不再跳转
	2、webview加载页面和传递参数使用webview.loadUrl方法
	传递参数 eg: webView.loadUrl("javascript:setUserToken('" + token + "')");
	加载页面 eg：webView.loadUrl(url);
	
2、图片字节流转换图片
	new Thread(new Runnable() {
	            @Override
	            public void run() {
	                try {
	                    // 定义获取文件内容的URL
	                    URL myURL = new URL(url);
	                    // 打开URL链接
	                    URLConnection ucon = myURL.openConnection();
	                    // 使用InputStream，从URLConnection读取数据
	                    InputStream is = ucon.getInputStream();
	                    final Bitmap bitmap = BitmapFactory.decodeStream(is);
	                ImageUtils.saveImageToGallery(PrototypeContestActivity.this, bitmap);
	                }catch (Exception e){
	                    e.printStackTrace();
	                }
	            }
	        }).start();

3、图片字节流转图片容易出现信息丢失的问题（分辨率丢失后会被修改成默认的分辨率）

	因此建议直接保存文件到手机。其次在华为手机上保存到手机的图片不会自动显示到图库，所以需要发送广播通知图库更新照片。

	// 定义获取文件内容的URL
	URL myURL = new URL(url + "?token=" + token);
	// 打开URL链接
	URLConnection ucon = myURL.openConnection();
	// 使用InputStream，从URLConnection读取数据
	InputStream is = ucon.getInputStream();
	File appDir = new File(Environment.getExternalStorageDirectory(), "52TOYS");
		if (!appDir.exists()) {
		appDir.mkdir();
		}
	String fileName = System.currentTimeMillis() + ".png";
	File file = new File(appDir, fileName);
	FileOutputStream fos = new FileOutputStream(file);
	byte[] buffer = new byte[1024];
	int len1 = 0;
	while((len1 = is.read(buffer)) != -1){
		fos.write(buffer, 0, len1);
	}
	// 最后通知图库更新
	Uri uri = Uri.fromFile(file);
	sendBroadcast(new Intent(Intent.ACTION_MEDIA_SCANNER_SCAN_FILE, uri));

4、android版本号和系统
	Code name 	      Version(System Version) 	        API level(SdkVersion)

	Oreo					8.0								API level 26
	Nougat 	                7.1 	                        API level 25
	Nougat 	                7.0 	                        API level 24
	Marshmallow 	        6.0 	                        API level 23
	Lollipop 	            5.1 	                        API level 22
	Lollipop 	            5.0 	                        API level 21s
	KitKat 	                4.4 - 4.4.4 	                API level 19
	Jelly Bean 	            4.3.x 	                        API level 18
	Jelly Bean 	            4.2.x 	                        API level 17
	Jelly Bean 	            4.1.x 	                        API level 16
	Ice Cream Sandwich 	    4.0.3 - 4.0.4 	                API level 15, NDK 8
	Ice Cream Sandwich 	    4.0.1 - 4.0.2 	                API level 14, NDK 7
	Honeycomb 	            3.2.x 	                        API level 13
	Honeycomb 	            3.1 	                        API level 12, NDK 6
	Honeycomb 	            3.0 	                        API level 11
	Gingerbread 	        2.3.3 - 2.3.7 	                API level 10
	Gingerbread 	        2.3 - 2.3.2 	                API level 9, NDK 5
	Froyo 	                2.2.x 	                        API level 8, NDK 4
	Eclair 	                2.1 	                        API level 7, NDK 3
	Eclair 	                2.0.1 	                        API level 6
	Eclair 	                2.0 	                        API level 5
	Donut 	                1.6 	                        API level 4, NDK 2
	Cupcake 	            1.5 	                        API level 3, NDK 1
	(no code name) 	        1.1 	                        API level 2
	(no code name) 	        1.0 	                        API level 1

5、android studio 查看某个类的所有方法快捷键 ctrl + F12
