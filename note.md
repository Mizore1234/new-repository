# Github三要素
* Repository仓库
  * 是项目管理的基本单位
  * 一个用户可以有多个仓库，但一个仓库存储一个项目
  * 仓库一般有public、private
* Commit提交
  * 在对代码进行迭代和修改后，可以通过commit方式来记录，可以回溯代码，有助于观察整个工程的开发流程以及设计流程
![提交记录](https://t.tutu.to/img/vaPq4)
* Branch 分支
  * 分支才是代码文件的第一存储单位，默认仓库主分支为`master`/`main`
![示意图](https://postimg.cc/DS6LtdYh)
以tiktok为例，其他两位协作人员完成所负责的功能后上传仓库，由主管管理 <br>
# 仓库内容
1. Code，资源存储，代码资源，二进制，项目管理脚本，许可证等
2. issues,使用时遇到bug或进行提交，等待反馈
3. README，用markdown语言编写，工程自述文件，开发进度，版本更新，使用介绍
4. LICENSE，许可证，GPL2.0,3.0。Apahce2.0,Mit
# Git软件，分布式版本控制系统
## 使用git管理私人代码或企业代码
本地内容 ------->  发布内容 <br>
          git

本地内容版本新于发布内容，通过git将本地内容上传，完成版本更新
# 设备认证
让网站的账户于设备绑定，后续完成代码的管理，上传下载： <br>
```bash
git init //创建本地仓库
git config --list //查看git配置文件
git config --global user.email "邮箱"
git config --global uer.name  "用户名"
ssh-keygen -t rsa -C "注册邮箱" //创建本地密文
ssh -T git@github.com //查看是否关联成功
```
# 给仓库起别名，定位目标仓库，方便后续上传
1. git remote add origin "ssh地址"  为ssh仓库地址创建origin这个别名 <br>
2. git remote remove origin   删除origin <br>
# 本地设备与云端仓库的交互逻辑
![示意图](https://t.tutu.to/img/vaIQP)
将代码提交到本地仓库后，本地仓库和云端的默认分支一样，则会合并，如果不一致，则会在云端创建出一个和本地仓库一致的分支，再进行合并 <br>
# 代码更新的依赖关系被破坏
本地内容比云端新，则可以完成更新替换，但是直接修改云端内容，会导致本地内容无法再次提交
## 可以采取先拉再推的方式解决
```bash
git pull --rebase origin master
git rebase --skip  //忽略新内容，但不能上传
git rebase --abort //忽略旧版，更新本地后可以上传
git rebase --continue  //版本合并
```
#下载开源代码
```bash
git clone "仓库地址"
```

