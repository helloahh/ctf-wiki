R### 对目标主机进行nmap扫描

![image-20240612092243695](image\1.png)

### 对21端口进行暴力破解

![image-20240613093947648](image\2.png)

匿名登陆

![image-20240613094317868](image\3.png)

下载三个文件

![image-20240613094437916](image\4.png)

在备份文件中发现ftp用户提示

![image-20240613102241506](image\5.png)



hydra 暴力破解获取到账号密码

![image-20240613104941071](image\7.png)

登录

![image-20240613112955243](image\8.png)

查看提示

![image-20240613113024052](image\9.png)

### 对80端口进行渗透测试

访问

![image-20240613142848289](image\10.png)

修改hosts文件

![image-20240613143036803](image\11.png)

重新访问

![image-20240613143128459](image\12.png)

目录暴力破解

![image-20240613154235162](image\13.png)

发现robots.txt，在robots.txt中发现子域名

![image-20240613154358127](image\14.png)

修改hosts文件

![image-20240613154456526](image\15.png)

访问发现wordpress站点

![image-20240613154552512](image\16.png)

利用wpscan 进行漏洞扫描

![image-20240613160606756](image\17.png)

![image-20240613161206705](image\18.png)

结合前面note.txt中的提示，怀疑test为弱口令，利用test 123456登录成功

![image-20240613161501099](image\19.png)

逐级翻找文章，发现私密文章

![image-20240613161851778](image\20.png)

![image-20240613162007391](image\21.png)

结合发现的11211端口，进行测试，根据提示获取到scmcc密码

![image-20240613171201334](image\22.png)

登录到smcc用户，发现有插件

![image-20240613171340654](image\23.png)

在插件处发现疑似命令执行

![image-20240613171443169](image\24.png)

成功执行命令

![image-20240613172032278](image\25.png)

存在nc命令

![image-20240613172220695](image\26.png)

反弹shell

![image-20240613172408022](image\27.png)

成功反弹

![image-20240613172454535](image\28.png)

获取交互式shell

![image-20240613172604350](image\29.png)

在网站目录发现flag 目录

![image-20240613172858116](image\30.png)

查找suid权限，发现find

![image-20240613173725883](image\31.png)

提权

![image-20240613173808714](image\32.png)







发现flag

![image-20240613173904098](image\33.png)
