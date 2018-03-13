# serviceWorker
原址：http://www.zhangxinxu.com/wordpress/2017/07/service-worker-cachestorage-offline-develop/


预览：https://yangliomg.github.io/serviceWorker/start.html


效果：
1.在离线状态（控制台network-offline），页面可以加载出来（因为被缓存在serviceWorker中）。

2.无论修改了html还是img，只有当sw-demo-cache.js中的版本号v改变了，才会重新加载，否则资源一直从serviceWorker中读取。

疑问：
1.开启sw模式以后，所有资源，无论html、img全都得在cache.addAll中声明？

2.sw-demo-cache.js直接修改了也不会直接重新加载，得从浏览器控制台Application-ServiceWorkers中找到正在队列中的js，点击skip wait（必需操作，刷新无效？？？），跳出等待，才会重新加载。

