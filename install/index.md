---
layout: page
menu: install
title: "安装Question2Answer-Question2Answer完全开源免费的知识分享(问答)系统"
---

# Question2Answer只需5分钟就能完成安装

在大多数情况下，网站安装Question2Answer是十分容易的。您可以按照下面的步骤操作。

## 安装Question2Answer之前准备

- Web服务器 [FTP](http://en.wikipedia.org/wiki/File_Transfer_Protocol) or [SFTP](http://en.wikipedia.org/wiki/SSH_file_transfer_protocol).
- [文本编辑器](http://en.wikipedia.org/wiki/Text_editor).
- 浏览器.

并确保你的网络服务器能够正常运行以下软件:

- 网络服务器软件，如[Apache](http://httpd.apache.org/) 或 [Nginx](http://nginx.org/).
- [PHP](http://www.php.net/) 5.2 或者更高版本, 并且安装了[MySQLi](http://en.wikipedia.org/wiki/MySQLi) 扩展程序.
- [MySQL](http://www.mysql.com/) 4.1 更高版本.

如果您不确定您的Web服务器是否安装了这些软件，请咨询您的网络托管提供商。

## 首次安装Question2Answer(无单点登录)

下面简要说明如何安装Question2Answer。如果您希望Question2Answer 与现有用户数据库和帐户系统集成，请参阅[单点登录](/install/single-sign-on/) 安装的说明。从版本 1.4， Question2Answer也提供了与[WordPress 3.x](/install/wordpress/) 网站和用户数据的简单集成.

1. 下载[最新版本Question2Answer](https://github.com/q2a/question2answer/releases) 到本地或者web服务器上 ( 也可以从[GitHub](https://github.com/q2a/question2answer) 下载).

2. 使用诸如[WinZip](http://www.winzip.com/) 等解压软件解压安装包 (或者使用 `unzip` 命令解压).

3. 如果您想运行非英语网站，请检查是否可用适当的 [语言文件](/addons/translate) .如果有, 下载并上传这些国际化文件到web服务器的 `qa-lang` 目录中. 如果没有，您可以自己 [翻译](/translate/) Question2Answer 国际化文件.

4. 创建 MySQL 数据库和具有该数据库完整权限的 MySQL 用户.
    <small>如果您有兴趣，实际需要的[权限](http://dev.mysql.com/doc/mysql/en/privilege-system.html) 为: 创建、更改、删除、插入、选择、更新、锁定表</small>

5. 记下 MySQL 详细信息：用户名、密码、数据库名称和服务器主机名称。如果 MySQL 与您的网站在同一台服务器上运行，则服务器主机名称可能是或 `127.0.0.1` 或 `localhost`.

6. 在解压后的文件夹中找到 `qa-config-example.php` 和 `.htaccess-example`, 将他们分别重命名为 `qa-config.php` 何 `.htaccess`.

7. 使用文本编辑器打开 `qa-config.php` , 在顶部插入 MySQL 详细信息，然后保存文件. 不要使用Microsoft Word 等编辑器, 而是使用 [文本编辑程序](http://en.wikipedia.org/wiki/List_of_text_editors).

8. 将所有Question2Answer文件上传到您的服务器中:
    - 如果想用根域名来作为主站，将Question2Answer所有文件放到域名根目录即可 (例如 `http://www.mysite.com/`)
    - 如果想使用子域作为问答系统 (例如 `http://www.mysite.com/qa/`),在根目录下创建`qa`子目录, 并将所有文件上传到该子目录即可.

9. 在浏览器中打开 Question2Answer, 例如:
    - 使用根域名, `http://www.mysite.com/`
    - 使用子目录, `http://www.mysite.com/qa/`

10. 按照屏幕上的说明设置您的数据库和管理员帐户即可

另见： [升级Question2Answer](/install/upgrade/)

## Add-Ons

有关本地化语言、主题、插件等问题可以参考[扩展](/addons/) .
