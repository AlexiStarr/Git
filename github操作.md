## 创建远程库
略
## 远程库操作
- 查看当前有什么别名
  ```
  git remote -v
  ```
- 创建远程库别名
  ```
  git remote add xxx(别名) xxx(远程库地址)
  ```
  ![image](https://github.com/user-attachments/assets/c1665996-c64e-44e0-92f0-ee460bd96b34)
  意思是推送和拉取（fetch包括clone和pull）都可以使用这个别名。  
  PS:clone是本地没有时用的，pull是本地有了的时候用的；  
     clone是完整拿来远程库内容，pull是拉取特定一个远程分支过来。
## 推送本地分支到远程库
- 推送
  ```
  git push xxx(别名/链接) xxx(分支)
  ```
  此时如果推送不了，运行命令
  ```
  git config --global http.sslverify false
  ```
  ![image](https://github.com/user-attachments/assets/5b5a762a-5ffc-4669-be8d-f231048955b3)
  推送成功！
## 拉取远程库代码到本地
- 拉取
  ```
  git pull xxx(别名/网址) xxx(分支)
  ```
  我们先在github上修改文件，再拉取，此时提示一个文件被修改：1行新增。
  ![image](https://github.com/user-attachments/assets/ba4f5980-805d-4a63-a248-11ab4332e8f7)
  拉取会自动提交本地库。
## 克隆代码
- 克隆
  ```
  git clone xxx(代码)
  ```
  克隆代码不需要登录github账号，因为公共库的读权限开放给所有人，不需要登录。    
  克隆会帮你拉取代码，初始化本地库，创建别名。（别名默认是origin）
## 团队协作
1. 令狐冲在本地修改代码之后，加入暂存库，提交至本地库，然后推送到远程库。
2. 此时需要师父给权限才能推送：  
   - settings里面的collaborators，点击add people，即可给push权限
     ![image](https://github.com/user-attachments/assets/012d4bfc-1cc8-447e-a966-cef959f7785d)
   - 把成员加入之后会有一个pending invite（邀请函），要把这个邀请函发给成员（其实是一个链接地址）  。
   - 此时令狐冲打开邀请函链接，接受邀请即可。（另外一个decline选项是婉拒）
     ![image](https://github.com/user-attachments/assets/5f9193f4-118b-4ec3-b261-c2806e8d9051)
3. 加入后就可以成功推送了
（如果一个人登录几个github账号，不同账户拉取和推送都需要在凭据管理器里面删掉相应账号凭据，否则都会默认为一个账号的操作。）
## 跨团队协作
团队外的如何实现协同
1. 把别人的项目fork叉一份到自己账户下，此时就可以进行修改
2. 叉过来的修改不会影响原来库有影响
3. 点击pull request拉取请求，点new pull request，create pull request，可以写一些话给岳不群
4. 此时岳不群就可以看到拉取请求，还可以给东方不败说话，里面可以随时聊天。
5. merge pull request就可以合并代码
## SSH免密登录
将前面的https链接换成ssh链接，每次需要输密码。如果push/pull不了，就先把加速器关了，就可以正常操作。
