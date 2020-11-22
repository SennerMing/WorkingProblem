#### GitHub上面的图片看不到了o(╥﹏╥)o

如果看不见我千辛万苦搜集或者制作的图片，不要着急不要着急哇，其实我也是百度来的法子，请参考以下操作步骤（本人mac试过了，可行👍；还有老哥推荐switch hosts软件，说是超级好用，大家可以下载来试试哇）：

MacOS：

​	sudo vim /etc/hosts

​	按i键，在末尾添加：

```text
# GitHub Start 
192.30.253.112    Build software better, together 
192.30.253.119    gist.github.com
151.101.184.133    assets-cdn.github.com
151.101.184.133    raw.githubusercontent.com
151.101.184.133    gist.githubusercontent.com
151.101.184.133    cloud.githubusercontent.com
151.101.184.133    camo.githubusercontent.com
151.101.184.133    avatars0.githubusercontent.com
151.101.184.133    avatars1.githubusercontent.com
151.101.184.133    avatars2.githubusercontent.com
151.101.184.133    avatars3.githubusercontent.com
151.101.184.133    avatars4.githubusercontent.com
151.101.184.133    avatars5.githubusercontent.com
151.101.184.133    avatars6.githubusercontent.com
151.101.184.133    avatars7.githubusercontent.com
151.101.184.133    avatars8.githubusercontent.com
 # GitHub End
```

Windows:

​	C:\Windows\System32\drivers\etc（印象中是这个路径蛤，没找到的话对应win版本去百度一下蛤，添加的hosts应该是和上面的一样的）