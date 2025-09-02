---
{"dg-publish":true,"permalink":"/🧑🏻‍💻CS/速查表/Scoop备忘录/","created":"2024-10-12T10:25:21.000+08:00","updated":"2024-10-12T10:25:21.000+08:00"}
---

## Scoop 安装

```powershell
#允许powershell执行本地脚本
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

#自定义安装目录-用户软件（管理员）
$env:SCOOP='D:\ProgramFiles\Scoop'
[environment]::setEnvironmentVariable('SCOOP',$env:SCOOP,'User')

#自定义安装目录-全局软件
#需要admin权限的软件才会进行全局安装，可以不改
#$env:SCOOP_GLOBAL='D:\ProgramFiles\Scoop_global'
#[environment]::setEnvironmentVariable('SCOOP_GLOBAL',$env:SCOOP_GLOBAL,'Machine')

#安装Scoop
irm get.scoop.sh | iex
#*检查环境问题（酌情解决）
scoop checkup

#添加软件源
scoop bucket add extras
scoop bucket add nerd-fonts
scoop bucket add dorado https://github.com/chawyehsu/dorado

#*使用代理（clash）
scoop config proxy 127.0.0.1:7890

#*开启aria2加速
scoop install aria2
scoop config aira2-enable ture

#搜索和安装
scoop search <app>
scoop home <app> #查看软件主页
scoop install <app>
scoop install dorado/<app> #安装dorado中的软件

#盘点和卸载
scoop list
scoop uinstall <app>

#软件更新
scoop status #检查更新
scoop update #更新自身
scoop update <app>
scoop update * #更新所有
scoop hold <app> #禁止更新
scoop unhold <app> #允许更新

#软件维护
scoop cache show #缓存信息
scoop cache rm <app> # 清除指定程序的下载缓存
scoop cache rm * # 清除所有缓存
scoop cleanup * # 删除所有软件的旧版本
scoop cleanup <app> # 删除某软件的旧版本
scoop cleanup * -k # 删除过期的下载缓存
```

## 重装系统后重新链接Scoop

[How to use scoop after reinstalling the system](https://github.com/ScoopInstaller/Scoop/issues/2894)

```cmd
#还原安装软件的环境变量（管理员）
$env:SCOOP='D:\ProgramFiles\Scoop'
[environment]::setEnvironmentVariable('SCOOP',$env:SCOOP,'User')

#将D:\ProgramFiles\Scoop\shims加入Path（管理员）
[environment]::setEnvironmentVariable('PATH',$env:PATH + ';D:\ProgramFiles\Scoop\shims','Machine')
```



## 参考资料

[Scoop](https://scoop.sh/)

[dorado](https://github.com/chawyehsu/dorado/blob/master/README.zh-Hans.md)

[scoopet](https://github.com/ivaquero/scoopet)

[Scoop buckets by Github score](https://rasa.github.io/scoop-directory/by-score)

[Scoop包管理器的相关技巧和知识 – 就是这个范儿 (thisfaner.com)](https://www.thisfaner.com/p/scoop/)

[Scoop——也许是Windows平台最好用的软件（包）管理器](https://zhuanlan.zhihu.com/p/463284082)