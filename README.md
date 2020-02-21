# share-terminal

[share](https://share.whoisnian.com) in terminal，

## install
Require:
 - zsh
 - xmllint
 - curl
 - wget

```
git clone https://github.com/xuranus/share-terminal
cd share-terminal
./install
```
reload your zsh, if `command not fount:complete` occured, you need to add the following lines to top of `~/.zshrc`:
```
autoload bashcompinit
bashcompinit
```

## uninstall
remove "source ~/.share/bash.rc" from `~/.zshrc` (may be the end line), then `rm -rf ~/.share`

## usage:
```
share [option] <filename>
Options:
  sync: update local file list from server
    ls: show files from local list
     d: download file
     u: upload local file
   del: delete file from server
```
Example:
```
╭─xuranus@Thanos ~ 
╰─$ share sync                                                                                                                                                                                              130 ↵
local file list synchronizing.....
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 10098    0 10098    0     0   1315      0 --:--:--  0:00:07 --:--:--  2237
Done.

╭─xuranus@Thanos ~ 
╰─$ share ls
Screenshot_2020-02-05-20-28-47.jpg
beijing_all_20200101.csv
统计学习方法.pdf
trpl-zh-cn.pdf
Wallpaper.jpg
Proxy-SwitchyOmega-Chromium-2.5.15.crx
Shadowsocks-Qt5-3.0.1-x86_64.AppImage
macOSPublicBetaAccessUtility.dmg
jmeter.png
IdeaProjects.rar

╭─xuranus@Thanos ~ 
╰─$ share d 统计学习方法.pdf 
href: https://share.whoisnian.com/upload/统计学习方法.pdf
--2020-02-21 10:46:59--  https://share.whoisnian.com/upload/%E7%BB%9F%E8%AE%A1%E5%AD%A6%E4%B9%A0%E6%96%B9%E6%B3%95.pdf
Loaded CA certificate '/etc/ssl/certs/ca-certificates.crt'
Resolving share.whoisnian.com (share.whoisnian.com)... 45.77.145.72, 2001:19f0:5:6c2a:5400:2ff:fe1b:7404
Connecting to share.whoisnian.com (share.whoisnian.com)|45.77.145.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18415263 (18M) [application/pdf]
Saving to: ‘统计学习方法.pdf’

统计学习方法.pdf                                     100%[====================================================================================================================>]  17.56M   819KB/s    in 49s     

2020-02-21 10:47:52 (369 KB/s) - ‘统计学习方法.pdf’ saved [18415263/18415263]

╭─xuranus@Thanos ~/Downloads 
╰─$ share u shiyan.json  
upload: shiyan.json
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 25313    0 10797  100 14516   3591   4829  0:00:03  0:00:03 --:--:--  8420

╭─xuranus@Thanos ~ 
╰─$ share del shiyan.json
delete: shiyan.json
local file list synchronizing.....
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 10098    0 10098    0     0  11108      0 --:--:-- --:--:-- --:--:-- 11096
Done.
```

## feature
`share d <filename>`support auto completement after running `share sync` to update local list.
```
╭─xuranus@Thanos ~ 
╰─$ share d
beijing_all_20200101.csv                macOSPublicBetaAccessUtility.dmg        Shadowsocks-Qt5-3.0.1-x86_64.AppImage   深入浅出React和Redux                                                          
IdeaProjects.rar                        Proxy-SwitchyOmega-Chromium-2.5.15.crx  trpl-zh-cn.pdf                          统计学习方法.pdf                                                              
jmeter.png                              Screenshot_2020-02-05-20-28-47.jpg      Wallpaper.jpg    
```

