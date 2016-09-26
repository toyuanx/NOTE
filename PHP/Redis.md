大纲
=====
* [Redis数据类型命令]()
* [Redis进阶命令](#Redis与PHP)
* [Redis与PHP]()
    * windows下的安装与配置
    * hello world！
    * 常用代码示例
    
* [Redis应用]()
    * 高并发架构
    
###Redis与PHP
* windows下的安装与配置
* hello world！
* 常用代码示例
    * getMultiple(array(key1, key2....,keyn)), 获取所有指定键的值。对应redis命令为 `MGET key1 key2...keyn`

###Redis应用
####高并发架构
*   服务器架构
*   并发测试
*   实战方案
    *   通用方案：优先查询缓存，如果缓存不存在，再进行DB查询，将查询结果缓存起来(hash)
    *   消息队列：将参与用户的信息添加到消息队列中，然后再写个多线程程序去消耗队列(list)
    *   一级缓存：使用站点服务器缓存去存储数据，注意只存储部分请求量大的数据，并且缓存的数据量要控制，需要设置过期时间
    *   静态化数据：将JSON，XML,HTML等数据文件上传CDN，在拉取数据的时候优先到CDN拉取，如果没有获取到数据再从缓存，数据库中获取
    *   其他方案：缓存数据到本地
    
           NOTE: [大话程序猿眼里的高并发架构](http://www.phpchina.com/portal.php?mod=view&aid=40241)
