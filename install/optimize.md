---
layout: page
menu: install
title: "性能优化-Question2Answer完全开源免费的知识分享(问答)系统"
---

# 优化Question2Answer性能

一般情况下Question2Answer能够快速和高效地运行在您的网络和数据库服务器上.尽管如此，如果您的 Q2A 站点开始接收大量流量，您可能需要考虑以下其他步骤，以帮助其以最高速度运行：

1. 打开MySQL服务器中的[查询缓存](http://dev.mysql.com/doc/refman/5.7/en/query-cache.html) . 这允许 MySQL存储Question2Answer的查询结果,而不是每次重新查询数据。如果您的网站收到的视图比编辑多得多，则它尤其相关。请注意，此MySQL功能已在MySQL 8中删除

2. 升级到最新版本的PHP。较新的版本包含许多性能增强功能，特别是 PHP 7，其速度是 PHP 5.6 的两倍.

3. 如果您在 PHP 5.4 或以下，请安装[PHP加速器](http://en.wikipedia.org/wiki/PHP_accelerator) 如 [Opcache](https://pecl.php.net/package/ZendOpcache) 或 [Alternative PHP Cache (APC)](http://pecl.php.net/package/APC). 这将缓存您 Web 服务器上的Question2Answer PHP 脚本的编译字节代码，以避免它们被解析并为每个页面请求进行编译。PHP 5.5 及以后默认情况下与操作器捆绑.

4. Question2Answer 旨在最大限度地减少每页使用的MySQL查询数量. 这允许您分离您的数据库和网络服务器，而不会遭受太多的[延迟](http://en.wikipedia.org/wiki/Latency_(engineering)). 缺点是由此产生的查询可能相当复杂. 如果您的数据库和 Web 服务器在同一个框上运行，延迟不是问题, 因此设置 `QA_OPTIMIZE_LOCAL_DB` 为 `true` 和 `QA_OPTIMIZE_DISTANT_DB` 为 `false` 在 `qa-config.php`. 这将使用许多简单的MySQL查询，而不是更少的复杂查询.

5. 在`qa-config.php`结尾检查其他设置和随附注释 .
