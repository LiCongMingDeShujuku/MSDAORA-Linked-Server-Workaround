![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# MSDAORA链接服务器解决方法
#### MSDAORA Linked Server Workaround
**发布-日期: 2007年10月10日 (评论)**

![#](images/##############?raw=true "#")

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
我最终安装了32位Oracle客户端来获取Provider：OraOLEDB.Oracle。在64位SQL Server与32位Oracle服务器之间的链接效果很好。
下面是我所有的链接脚本。
希望对你有用。



## English
I ended up installing the 32bit Oracle Client to get the Provider: OraOLEDB.Oracle
my link between 64bit SQL Server to a 32bit Oracle server works great.
here’s my full link scripted out.
hope it’s useful


---
## Logic
```SQL
EXEC master.dbo.sp_addlinkedserver @server = N’OraLinkServer’, @srvproduct=N’Oracle’, @provider=N’OraOLEDB.Oracle’, @datasrc=N’MyServer.MyDomain.COM‘
EXEC master.dbo.sp_addlinkedsrvlogin @rmtsrvname=N’OraLinkServer’,@useself=N’False’,@locallogin=NULL,@rmtuser=N’MyUser’,@rmtpassword=’MyPassword’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’collation compatible’, @optvalue=N’true’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’data access’, @optvalue=N’true’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’dist’, @optvalue=N’false’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’pub’, @optvalue=N’false’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’rpc’, @optvalue=N’false’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’rpc out’, @optvalue=N’false’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’sub’, @optvalue=N’false’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’connect timeout’, @optvalue=N’0′
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’collation name’, @optvalue=null
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’lazy schema validation’, @optvalue=N’false’
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’query timeout’, @optvalue=N’0′
GO
EXEC master.dbo.sp_serveroption @server=N’OraLinkServer’, @optname=N’use remote collation’, @optvalue=N’true’


```


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

