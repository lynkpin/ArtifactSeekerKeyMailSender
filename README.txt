神器行者自动发key工作流


帖子
https://steamcommunity.com/app/2510720/eventcomments/4411921426155806174

如果要具体到某一页，则带上ctp参数，比如117页
https://steamcommunity.com/app/2510720/eventcomments/4411921426155806174?ctp=117


使用BrowserSkill


本工作流每次操作完都形成记忆文档，方便有序在此基础上继续执行
最后执行git命令
git add .
git commit -m "发送key邮件"
git push origin master


从帖子中读取玩家的留言（从第指定页开始，从#编号之后开始，比如从#1744之后开始）
把“拥有 神器行者”的玩家筛选出来，把玩家的留言的邮箱也解析出来，填入key post.xlsm的第二个sheet中（也就是待发key的sheet），C列填"回帖"两个字，D列填玩家具体的邮箱
注意已填写的格子不要覆盖，往下找到未填写的格子然后填进去


如果是额外命令说录入一些邮箱，比如
jacobwhitlock77@gmail.com
nickperez27@gmail.com
ninaizong@qq.com
3666592802@qq.com
Daniel.Masser@outlook.de
这种就是C列填"邮箱"两个字


录入时，如果邮箱重复，则不要录入
但是要记录下来，邮箱重复的，要找到它早先那条记录的B列（兑换码）
没有重复的，则直接对应的B列就是它的兑换码
最终生成一个 list.txt（文件名带日期后缀，比如list_2026_11_3.txt），这个list的每条记录是三个值：
兑换码、邮箱、是否重复的


根据list，使用使用BrowserSkill，操作浏览器，访问Gmail: https://mail.google.com/mail/u/0/?hl=zh-TW#inbox/FMfcgzQbdrSjgkZFxWTlFTQSSWBzpbSC (本地浏览器已登录账号，确认账号是：lynkpingame@gmail.com)
挨个发送邮件，邮件模板：
邮件标题：Artifact Seeker: Resurrection key，神器行者：重生 激活码
邮件正文：
We are the "Artifact Seeker" team. We are extremely grateful for your support of our game. At the same time, we sincerely apologize for the inconvenience caused to you! Now, we are sending you a Steam CD key. Have a great time playing the game:      


我们是《神器行者》团队，十分感谢您对我们游戏的支持，同时为给您带来的不便深表歉意！现向您发送补偿游戏Steam激活码一枚，祝您游戏愉快： 


具体的兑换码【此处需要替换】


Thank you for the support!
感谢支持！


Presented by the  Artifact Seeker Team
    神器行者团队奉上 