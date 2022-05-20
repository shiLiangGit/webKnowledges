###  script标签defer和async的区别：

    图解 script 标签中的 async 和 defer 属性 (https://juejin.cn/post/6894629999215640583)

> **1.script**: 会阻碍HTML解析，只有下载并执行完script文件才能继续解析HTML；
>
> ***2.async script***: `异步加载：解析HTML过程中进行脚本的异步加载，加载过程中不影响html解析，但等脚本文件加载完成，立马执行脚本时，会组合html解析，等脚本执行完成后，html才能接着往后解析`。
>
> ***3.defer script***: `延迟加载，解析HTML过程中进行脚本的异步加载，加载过程中不影响html解析，加载完成会等待html解析后，才会执行脚本`。
>
> * 当浏览器遇到带有 defer 属性的 script 时，获取该脚本的网络请求也是异步的，不会阻塞浏览器解析 HTML，一旦网络请求回来之后，如果此时 HTML 还没有解析完，浏览器不会暂停解析并执行 JS 代码，而是等待 HTML 解析完毕再执行 JS 代码
>
> * 如果存在多个 defer script 标签，浏览器（IE9及以下除外）会保证它们按照在 HTML 中出现的顺序执行，不会破坏 JS 脚本之间的依赖关系

------

如图展示了三种script的加载过程

![](http://rc0nh980a.hn-bkt.clouddn.com/images/image-20220520165851114.png)