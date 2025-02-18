<p align="center">
    <h2 align="center">学习强国——挑战答题题库</h2>
    <p align="center">
        <a href="https://github.com/mondayfirst/XXQG_TiKu/blob/main/LICENSE" target="blank">
            <img src="https://img.shields.io/github/license/mondayfirst/XXQG_TiKu" alt="license"/>
        </a>
        <a href="https://hub.docker.com/r/mondayfirst/xxqgtiku-server" target="blank">
            <img src="https://img.shields.io/badge/docker-xxqgtiku--server-blue" alt="docker"/>
        </a>
        <a href="https://github.com/mondayfirst/XXQG_TiKu/search?l=javascript" target="blank">
            <img src="https://img.shields.io/github/languages/top/mondayfirst/XXQG_TiKu" alt="languages"/>
        </a>
    </p>
</p>

---
##### 从服务器每小时上传一次网络题库，欢迎star。
###### &emsp;&emsp;请各位自取挑战答题部分代码。
###### &emsp;&emsp;对服务器端进行完善，以实现自动化上传github题库。
###### &emsp;&emsp;识别正确答案的代码已在脚本中，请以此尽量向服务器增加题目，可加快题库的更新速度。

---
##### 一、注意：  
1. 格式：  
&emsp;&emsp;json文件中的格式是：`问题|答案1|答案2|...:正确答案`。问题(去除空格)，与可选答案之间以`|`符号分隔。  
&emsp;&emsp;`题库_排序版.json`为保证题目的唯一性，先去除可选答案的序号，再对几个选项进行列表排序。  
2. 预览  
&emsp;&emsp;首页不再显示题目，可点击`题库_排序版.md`文件全览题目  
3. 数据来源  
&emsp;&emsp;根据安卓手机无障碍服务获取控件内容，并在`挑战答题`页面自动答题获得全部题目与正确答案。  
&emsp;&emsp;因获取时间跨度较长，同一题目可能存在不同版本，一并保留。
1. 脚本  
&emsp;&emsp;详情见`xxqg_tiku_client/建立题库_autoJS.js`代码文件，注释个人认为比较清楚。有问题提issue。  
1. 服务器  
&emsp;&emsp;服务器端代码已给出，并封装成库。程序使用flask框架编写，使用pytest进行测试，较为简单，诸位可依此自建服务器端题库。代码默认使用JSON方式查询。  
&emsp;&emsp;已在Dockerhub上传[镜像](https://hub.docker.com/r/mondayfirst/xxqgtiku-server)，可自行构建服务
1. 隐私模式  
&emsp;&emsp;隐私安全模式下无法截屏，只能通过随机选项点击后观察答案是否正确的步骤来获取正确答案。  

##### 二、免责声明  
&emsp;&emsp;本题库及相关代码仅用于个人学习，下载后请勿用于商业或违法活动。

##### 三、更新日志  
###### 20230106  
1. 修改服务器程序代码，服务器端存储方式改为SQL数据库
2. 修改仓库代码结构，使架构更合理  
3. 修改Dockerhub镜像文件，使其更易部署
###### 20221013  
1. 添加js脚本，可从Autox.js(Autox.js为Auto.js的分支, 应当支持Auto.js)创建db数据库(PutinYpa)。  
###### 20220920  
1. 缩短等待时间（2s->0.1s），来加快答题速度。可自行修改  
###### 20220918
1. 修复一处逻辑Bug(Tq7)并对截图识别区域进行限制(wangwang-code)
###### 20220917
1. 适配隐私安全版本，无法截屏时采用试错法  
2. 自动点击访问异常（借鉴） 
3. 减少答题错误再次答题的等待时间。  
&emsp;&emsp;等待时间从固定时间间隔变为距该轮答题开始10秒。当连续答对较多时，发起的新一轮挑战答题不会再等待。  
1. 避免错误选项提交，当截图没有找到正确答案时退出脚本  
2. 问题先去除空格，因空格的增减出现的题目现在唯一  
3. 答案错误自动修复，从题库中获取的答案也检查正确性  
###### 更早
...
