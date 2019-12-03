### 《欺骗的艺术》阅读分享

&emsp;&emsp;《欺骗的艺术》是世界著名黑客凯文·米特尼克在2002年推出的一本公益性质的畅销书，全书主题是关于社会工程学，也就是他在整个黑客生涯中最著名的一个观点“人为因素才是安全的软肋”(The human factor is truly security's weakest link.)。

![封面](https://raw.githubusercontent.com/WindseekerBlade/the-art-of-deception/master/img/artofdeception.jpg)

&emsp;&emsp;在分享书中内容之前有必要先介绍一下作者的传奇人生，因为在上世纪八十到九十年代相当长的一段时间内，作者的名字Kevin D. Mitnick都是“黑客”的代名词。

&emsp;&emsp;摘录几个Mitnick的“光辉事迹”供大家参考：

&emsp;&emsp;15岁成功侵入北美空中防务指挥系统，17岁黑进美国洛杉矶电话中心，被捕后因为年龄小仅仅被判监禁3个月，成为世界上第一个因网络犯罪入狱的人。出狱后20岁的他再接再厉攻破美国五角大楼系统，之后在“翻阅”联邦调查局档案资料时无意中发现自己正在被FBI通缉，开始了长达数年的地下逃亡与网络反追踪生活，直到上世纪末才被FBI逮捕。入狱期间全世界黑客联合要求将其保释，并攻击了多个政府网站以施加压力。Mitnick在2000年假释出狱，并于两年后撰写出版了本书《欺骗的艺术》从新回到人们的视野。

&emsp;&emsp;尽管这本书出版的年代距离现在比较遥远，但个人认为很多社会工程学（Mitnick在计算机之外的另一个“天赋”）的观念和细节还是值得一读，虽然当时的互联网环境、网安技术、欺诈与反欺诈与当今不能同日而语，但Mitnick在其中描述的许多案例即使在今天看来也是非常有启发性的（在这本书出版前简直是防不胜防）。

---

&emsp;&emsp;书中总共16章分为四大部分，第一部分“幕后的故事”讲述了企业在社会工程师攻击下的薄弱环节，第二部分“攻击者的手段”用故事和案例的方式演示了各种社会工程师的面具与身份，第三部分“入侵警报”完整展示了一个社会工程师如何铤而走险进入企业内部盗取关键信息，并越过各种安防措施的过程，最后第四部分“加强防范”提供了一套安全策略来警惕及阻止上述攻击的发生。

![全书思维脑图](https://raw.githubusercontent.com/WindseekerBlade/the-art-of-deception/master/img/overview.jpg)

&emsp;&emsp;全书内容较多，我仅仅挑选其中几个具有代表性的小案例给大家分享一下，如果有兴趣可以找全版来看顺便支持正版。

---

**第一个案例**

&emsp;&emsp;本案例曾入选吉尼斯世界纪录，是当时最大的计算机诈骗案，也是一个非常小巧但经典的社会工程学案例，攻击者用两次电话骗取了上千万美金。

&emsp;&emsp;事情发生在1978年冬天，美国太平洋银行一位员工Rifkin获准维护电汇交易室的服务器，在了解了交易室完整的汇款细节后，某天早晨他借备份数据的机会从一位新员工的便签纸上“无意”瞥到了每天都会重新生成的交易口令，于是在当天快下班前走出公司大厦来到街边的一个投币电话机旁，开始了蓄谋已久的攻击。

&emsp;&emsp;首先Rifkin伪装成银行国际部的职员，并提供提前调查好的真实信息，请求电汇交易室工作人员发起一笔从纽约信托公司到瑞士苏黎世银行某账户的贷款。请求自然失败了，因为虽然Rifkin有交易口令，但却没有内部转账号。挂掉电话的Rifkin又立即打给银行系统部门，伪装成电汇交易室的员工查询转账号，由于了解交易室的所有内部流程，对方并未生疑。几天后，Rifkin乘飞机来到瑞士提取了现金，又通过俄罗斯一家代理处购置了一些钻石，然后把钻石封在腰带里通过海关飞回美国。

![极简但真实的社工案例](https://raw.githubusercontent.com/WindseekerBlade/the-art-of-deception/master/img/maninmiddle.jpg)

&emsp;&emsp;这个案例乍一看很荒诞，但细想之下其实其中用到了很多化繁为简的社会工程学技巧。

&emsp;&emsp;首先攻击者利用职务便利进入了需要严格准入权限才能进入的区域——电汇交易室，并收集了交易室重要的操作流程，这对于第二个电话中骗取对方信任至关重要。同时他还注意到交易口令规律性的生成时间，趁某位新员工尚未建立起安全意识前（也可能是口令过于复杂难记）默背下了当天的交易口令。仅凭这两个条件还不足以绕过层层安全关卡，于是他选择当天快下班前，被伪装对象正好不在办公室的时间发起交易，因为目标是精心选定，所以提前调查好的“员工信息”细节没有引起交易室的任何怀疑，准确的口令更是极大增加了可信度。遇到未知的内部转账号，也巧妙地通过反向伪装从另一个部门获取。换句话说，整个攻击过程的信息提供都是真实有效的，唯一的虚假信息，就是Rifkin用自己提前申请的苏黎世银行账号作为了交易目标账号。

&emsp;&emsp;这个欺骗过程的主体就是著名的中间人攻击（MITM），现今几乎是每个银行电子渠道做Vulnerability测试时的重点防控检测项目。

---

**第二个案例**

&emsp;&emsp;一个典型的“别针换别墅”的过程，描述了我们印象中那些毫无价值的信息是如何被社会工程师利用到淋漓尽致。

&emsp;&emsp;我们知道猎头公司经常需要了解很多目标公司的内部信息才能精确地挖到某些职位，这个案例中的攻击者首先打电话给公司的总机，伪装成一位公司员工在外工作，但急需联系资产部和收款部的分机号。鉴于攻击者对办公环境十分熟悉，而且分机号只属于普通的内部信息，总机服务员并未多想便提供了。攻击者随后联系收款部，假装填写报销单而查询成本中心代码，并获知其为“1A5N，N是Nancy的N”。

&emsp;&emsp;手握正确的成本中心代码作为筹码，攻击者给资产部打电话，索要一份企业通讯录，在对方表示最新电子版并未印刷后又请求查询了印刷部的联络人。在印刷部，攻击者终于通过一个令人焦急的谎言博得同情，可以提前申请一份略有些过期的旧版通讯录邮寄过去，当然，对于产生的费用攻击者毫不犹豫地告知对方：“1A5N，N是Nancy的N”。至此，攻击者已经获得了期望中的信息——企业人员名单及联系方式。

![“滚雪球”的无价值信息](https://raw.githubusercontent.com/WindseekerBlade/the-art-of-deception/master/img/hr.jpg)

&emsp;&emsp;这个案例中，工作环境描述-内部分机号-成本中心代码-印刷部联络人-企业通讯录，这些一开始被视为“无用”或“无害”的信息，如滚雪球一般被社会工程师利用，最终无用信息的价值在某一刻从碎片连成了一整片地图，勾勒出了完整的画面，成为打开企业最有价值的秘密信息的钥匙。

&emsp;&emsp;如果说我们无法想象无害信息的价值到底有多大，Mitnick当年在网络上获取的美国国家犯罪信息中心操作说明，可以让一个经验丰富的社会工程师完美地伪装成FBI内部员工。一旦对方相信了你的“内部”身份，人们心中的警惕值通常都会大幅下降，这个时候攻击者就可以运用综合手段来层层递进，最终达成攻破安全措施的目标。

---

&emsp;&emsp;篇幅原因，很多经典案例不再一一展开，比如素未谋面却“值得信赖”的音像店经理，利用同情心理攻破“软心糖安全”的外地人，连环使用情感刺激（害怕、压力、感激、心理落差）而被控制的公司新人，让被攻击者向攻击者寻求帮助的逆向骗局，甚至还有我们熟悉的一些知名公司如Oracle与微软当年沸沸扬扬的“垃圾搜寻”案例。

![音像店老板的信任](https://raw.githubusercontent.com/WindseekerBlade/the-art-of-deception/master/img/trust.jpg)

&emsp;&emsp;当然作者在最后一部分也完整地给出了应对社会工程学的策略，如何防范人的天性被利用、如何完整创建培训程序、怎样执行信息安全策略，毕竟这本公益书籍出版时，作者已经假释出狱并投身于信息安全行业，其目的也是警醒那些过于轻信的管理者，正如作者文中提到“安全不是技术问题，是人和管理的问题。社会工程学的攻击，成功于人们的愚蠢或更为普遍的对信息安全实践上的无知。”

&emsp;&emsp;之所以有这样的论断，似乎是因为作者本人也很信奉爱因斯坦的一句名言：“只有两种事物是无穷尽的――宇宙和人类的愚蠢。但对于前者，我不敢确定。” 

&emsp;&emsp;以此作为结尾。

---

题外：影视作品中此类题材也比较多，形式也比书籍更令年轻人接受，推荐两部其中的翘楚之作：

* 《猫鼠游戏》斯皮尔伯格执导，莱昂纳多、汤姆汉克斯主演
>IMDB http://www.imdb.com/title/tt0264464

![《猫鼠游戏》](https://raw.githubusercontent.com/WindseekerBlade/the-art-of-deception/master/img/catchmeifyoucan.jpg)

* 《我是谁：没有绝对安全的系统》第65届德国电影奖杰出故事片
>IMDB http://www.imdb.com/title/tt3042408/

![《我是谁：没有绝对安全的系统》](https://raw.githubusercontent.com/WindseekerBlade/the-art-of-deception/master/img/whoami.JPG)




