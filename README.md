# serviceWorker
原址：http://www.zhangxinxu.com/wordpress/2017/07/service-worker-cachestorage-offline-develop/


预览：https://yangliomg.github.io/serviceWorker/start.html

说明：

1.三级缓存原理：  1.先去内存看，如果有，直接加载
                2.如果内存没有，择取硬盘获取，如果有直接加载
                3.如果硬盘也没有，那么就进行网络请求
                4.加载到的资源缓存到硬盘和内存
                
2.serviceWorker提供了新的缓存位置（缓存在serviceWorker中）

3.前端浏览器缓存及代码部署：http://www.haorooms.com/post/qianduan_cache_bushu

效果：

1.在离线状态（控制台network-offline），页面可以加载出来（因为被缓存在serviceWorker中）。

2.无论修改了html还是img，只有当sw-demo-cache.js中的版本号v改变了，才会重新加载，否则资源一直从serviceWorker中读取。

疑问：

1.开启sw模式以后，所有资源，无论html、img全都得在cache.addAll中声明？

2.sw-demo-cache.js直接修改了也不会直接重新加载，得从浏览器控制台Application-ServiceWorkers中找到正在队列中的js，点击skip wait（必需操作，刷新无效？？？），跳出等待，才会重新加载。

