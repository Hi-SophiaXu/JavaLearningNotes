# 1. Terminology
**黑客（hacker）**：e.g.Anonymous

**脚本小子**：

**白帽子**：渗透测试工程师。e.g.360补天、漏洞盒子、CNVD、CNNVD

**红帽黑客（红客）**：

**漏洞（vulnerable）**：硬件、软件、协议...存在安全缺陷。[国家信息安全漏洞库](www.cnnvd.org.cn)

**POC(Proof of Concept)**：能证明漏洞存在的代码。

**exp（Exploit利用）**：执行了这一段利用代码之后，就能达到攻击目的。msf

**payload（攻击载荷）**：具体攻击所输入的内容。e.g.SQL注入、XSS、log4j

**0day漏洞**：（在野）未公开，全部未修复。使用量非常大的通用产品漏洞已经被发现了（还没有公开），官方还没有发布补丁或者修复方法的漏洞。

**1day漏洞**：已公开，大量未修复。漏洞的POC和EXP已经被公开了，但很多人还来不及修复。

**Nday漏洞**：已经公开，大量修复。

**漏扫**：漏洞扫描工具。基于数据库对漏洞进行自动化扫描。漏洞扫描工具e.g.AppScan

**补丁（patch）**：漏洞修复程序

**渗透（penetration）**：（非法）黑客入侵了网站或计算机系统，获取到控制计算机权限的过程。

**渗透测试（penetration test）**：（合法）用黑客入侵的方式对系统进行安全测试。目的是找出和修复安全漏洞，在这个过程中不会影响系统的正常运行，也不会破坏数据。

**木马（Trojan horse）**：隐藏在计算机中的恶意程序。受控端、控制端。不会自己去运行的。

**病毒（Virus）**：恶意代码或程序。自我复制的特质。不需要控制端，能自我执行。e.g.熊猫烧香

**杀毒软件**：e.g.360、金山、McAfee、卡巴基斯、诺顿

**免杀**：绕过杀毒软件。e.g.加壳、编码混淆、捆绑。[virustotal](www.virustotal.com)检测

**肉鸡（傀儡机）**：已被黑客获得控制权限的机器。通常情况下因为使用者并不知道已经被入侵，所以黑客可以长期获得权限和控制。

**抓鸡**：利用出现概率非常高漏洞（e.g.log4j、永恒之蓝），使用自动化方式获取肉鸡的行为。

**跳板机(jumpserver)**：黑客为了防止被追溯和识别身份，一般都不会用自己的电脑发起攻击，而是利用获取的肉鸡来攻击其他目标，这个肉鸡就充当一个跳板的角色。

**DDos(Distribution Denial of Service，分布式拒绝服务攻击)**：发起大量恶意请求，导致正常用户无法访问。e.g.[webstresser卖DDos服务的](www.webstresser.org)

**后门（backdoor）**：黑客为了对主机进行长期的控制，在机器上种植的一段程序或留下的一个“入口”。

**中间人攻击（Man-in-the-Middle Attack，MITM攻击）**：运行中间服务器，拦截并篡改数据。

**网络钓鱼**：钓鱼网站，指冒充的网站，用来窃取用户的账号密码。社会工程学

**webshell**：shell是一种命令执行工具，可以对计算机的硬件进行控制。webshell，即asp、PHP、jsp之外的web代码文件，通过这些代码文件可以执行任意的命令，对计算机做任意操作。分类：小马（只有文件上传的功能），一句话木马（需要一些网站管理工具来连接它e.g.godzilla\behinder\ant sword），大马。浏览器插件：HackBar

**Getshell**：获得命令执行环境的操作。方式：Redis的持久化功能、MySQL的写文件功能，MySQL的日志记录功能、上传功能、数据备份功能、编辑器。

**提权（Privilege Escalation，权限提升）**：普通用户权限，把自己提升为管理员权限的操作。

**拿站**：得到一个网站的最高权限，即得到后台和管理员名字和密码。

**拖库（脱裤）**：网站被入侵以后，黑客把全部的数据都导出，窃取到了数据文件。裤子：脱裤产生的数据。--->社工库（违反了个人信息保护法和数据安全法）

**撞库**：用获得的裤子去批量登录其他网站。

**旁站入侵（攻击）**：入侵同服务器的其他网站。旁站（一台服务器上部署了很多网站。e.g.企业内部的服务器，节省成本、资源；外面买服务器，买的是共享服务器、虚拟主机）。

**横向移动（内网渗透）**：攻击者入侵一台服务器成功以后，基于内部网络。继续入侵同网段的其他机器。

**代理（Proxy）**：网络代理，帮我们发起网络请求的一台服务器。突破限制访问外网；访问内部资源；隐藏真实IP。e.g.访问国外网站

**VPN（Virtual Private Network）**：代理、加密通信、办公（在家里连接到公司内网）

**蜜罐（Honeypot）**：一种安全产品，吸引攻击者攻击的伪装系统，用来实现溯源和反制。国内免费蜜罐网站：HFish

**沙箱（Sandbox）**：一种按照安全策略限制程序行为的执行环境，就算有恶意代码，也只能影响沙箱环境而不会影响操作系统。e.g.微步云沙箱

**靶场**：模拟的有漏洞的环境。可以是网站、容器、操作系统。类型：
1. web综合靶场：DVMA、pikachu、bwapp；
2. web专用靶场：sqli-labs、upload-labs、xss-labs；
3. 漏洞复现靶场：CVE-44228、八方网城(bafangwy.com)；
4. 操作系统靶场：vulnhub靶场、；
5. CTF靶场：专门用来练习CTF题目，每个人都有一个独立的环境。

**堡垒机**：安全产品，运维时候的跳板机。运维审计系统，管理资源，审批、审计、访问控制、事件记录。[阿里云堡垒机](https://www.aliyun.com/product/bastionhost)、[开源免费的堡垒机](https://jumpserver.org/)

**WAF(Web Application Firewall，web应用防火墙)**：对HTTP/HTTPS的流量内容进行分析，拦截恶意攻击行为。硬件类WAF、云WAF、软件型WAF。

**绕WAF**：

**APT攻击（Advanced Persistent Threat）**：高级可持续威胁攻击。指某个组织在网络上对特定对象展开的持续有效的攻击活动。攻击对象：国家、政府、大型基础设施...【报告：2021深信服APT攻防趋势半年洞察】

**护网（HVV）**：国家组织牵头组织事业单位，国企单位，民企单位等开展攻防两方的网络安全演习。攻击方：红队；防守方：蓝队。

**CTF（Capture The Flag，夺旗赛）**：起源于1996年DEFCON全球黑客大会。一种黑客技术竞赛。
解题形式：Jeopardy；攻防形式：Attack-Defense
方向：Reverse（逆向）、Pwn（二进制）、Web（e.g.SQL注入、XSS、反序列化、密码暴力破解）、Crypto（加密）、Misc（杂项）、Mobile（移动端）
在线CTF：[bugku](https://ctf.bugku.com/challenges/index.html)、[北京联合大学](https://buuoj.cn/challenges)、[CTFHub](www.ctfhub.com)、[bmzCTF](bmzclub.cn/challenges)、[攻防世界](adworld.xctf.org.cn)、[CTFSHOW](ctf.show/challenges)

**CVE(Common Vulnerabilities and Exposures，通用漏洞披露)**:Mitre公司维护的漏洞数据库

**CNVD（国家信息安全漏洞共享平台）**：国家计算机应急响应中心（CNCERT）维护

**应急响应**：一个公司为了应对各种安全事件所做的准备和事后采取的措施

**SRC（企业的应急响应中心，security response center）**：Oxsafe.org

**公益SRC**:(vulbox.com)、(src.sjtu.edu.cn)

**网络空间测绘**:网络空间资源收录。网络空间搜索引擎(www.shodan.io)(fofa.so)[钟馗之眼](www.zoomeye.org)

**ATT&CK(Adversarial Tactics, Techniques, and Common Knowledge，对抗战术、技术和通用知识)**：攻击者战术的知识库。风险分析模型，收集威胁情报、模拟APT攻击。

**逆向（Reverse）**：把程序还原为源代码，分析程序的运行过程。

**DevOps（Development + Operations，开发测试运维一体）**：

**DevSecOps（Development + Security + Operations）**：安全开发与运维

**CICD**：具体技术（Git代码管理、Jenkins版本管理、代码扫描、自动化测试）。包括：持续集成（Continuous Integration）、持续交付（Continuous Delivery）、持续部署（Continuous Deployment）

**等保制度（网络安全等级保护）**：国家安全的一项基本制度，要求相关行业的单位和公司的信息系统必须进行定级（四级）。然后再公安机关备案。然后建设整改。然后由测评机构评级，并且维持维护和监督。