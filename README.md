# AutoIPChangeForDocker
自动将电信动态IP地址注册至阿里云托管的域名
# 存在的问题
网络运营商给定的IP地址是动态的并且每次断线或者一定的时间后IP地址均会改变，导致我们如果捆绑域名的IP地址无法准确解析到正确的域名。
# 希望解决的问题
希望能够通过脚本的方式，每隔一段时间检测当前的IP地址，如果与域名绑定的IP地址不一致则自动更新域名的IP地址。
# 解决方案
使用阿里云提供的API接口，每隔一段时间检测当前的IP地址，如果与域名绑定的IP地址不一致则自动更新域名的IP地址。
# 使用方法
1. 首先需要在阿里云申请一个域名，并且将域名解析到你的服务器上。
2. 在阿里云申请一个AccessKey，用于调用API接口。
3. 将脚本中的AccessKeyID和AccessKeySecret替换为你自己的AccessKey。
4. 将脚本中的DomainName替换为你自己的域名。
5. 将脚本中的RecordId替换为你自己的域名的RecordId。
6. 将脚本中的Interval替换为你自己的检测间隔时间。
7. 将脚本中的IPCheckUrl替换为你自己的IP地址检测地址。

# 实现方法
利用Docker的定时任务功能，每隔一段时间执行一次脚本。

具体用到的Docker镜像为：
