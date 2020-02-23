**一. 游戏手柄支持**  
我使用的是Samsung Gear VR Gamepad，蓝牙手柄两只。据网上搜索信息，很多无线，有线手柄都支持的。欢迎大家把手上测试能用的手柄报告一下，我更新在帖子里。  

**二. 原生游戏推荐**  
优点：运行流畅，画质佳。对手柄支持好，几乎直接使用，不用修改键位。  
缺点：不能修改存储位置，全部放在内置存储。内置空间有限，需要扩展存储可以看我这个帖子，完美解决存储问题。  
[https://www.hi-pda.com/forum/viewthread.php?tid=2671247](https://www.hi-pda.com/forum/viewthread.php?tid=2671247)  

1. BombSquad （炸弹小分队）  
   强烈推荐，从Amazon APP Store下载，支持本地多人游戏。  
   不但支持实体手柄，还支持安装在手机平板上的虚拟手柄，家庭玩乐首选。  

2. Asphalt 8 （狂野飙车8）  
   赛车游戏，从Amazon APP Store下载，我儿子玩的很High.  
   但只支持联网多人，不支持本地多人游戏。  

**三. 模拟器游戏，跟原生游戏的优缺点刚好相反。**  
优点：可以修改存储位置在外接U盘。外接存储需要OTG线，具体看我下一部分的说明。  
缺点：画质差，几乎全屏马赛克，但适合怀旧。对手柄支持不太佳，在模拟器内需要修改键位才能正常操作。  

1. MAME4droid (0.139u1)  
   [https://sourceforge.net/projects/mame4droid/](https://sourceforge.net/projects/mame4droid/)  
   街机模拟器，可以玩三国志，恐龙快打，街霸，惩罚者等等怀旧街机游戏。  

2.PPSSPP  
[http://www.ppsspp.org](http://www.ppsspp.org/)  
PSP模拟器，装好了，还没有测试过，目前游戏已经够了。有好玩的请推荐。  

3. 小鸡模拟器，实测不能切换到外接存储，不推荐。  

4. 地板发的天龙前端模拟器，实测在FireTV不能运行。  

**四. OTG线 (不接OTG线，也可以玩上面的原生游戏,或者需要空间较小的模拟游戏)**  
FireTV Stick 内部空间有限，为了扩展存储，或者支持USB游戏手柄，OTG线还是需要的。可以买成品OTG线或者自制。自制步骤如下。  

1）某东自营买一条，Micro USB的OTG线，注意一定要带线的，不要买直接只有两头插的那种（不方便另接线)。我买的是下面这种。

![](https://github.com/openwrt166/firetv/blob/master/images/07.jpg)

2）把靠近USB母头的那一段线表皮剥开，里面红色和黑色线破开，另外焊接2条线连到一个USB公头对应的DC正负端子。接好后最好打胶，如果确信自己手艺不会短路，不打胶也是可行的。做好的成品如下图。

![](https://github.com/openwrt166/firetv/blob/master/images/08.jpg)
