- id：`n_f1_20260818_d8f4e067c2`
- layout_code / type_code：`FEATURE` / `PADDOCK`（夏休期车手社媒动态盘点，同 #09/#13/#15/#16/#17/#18/#19/#22/#23/#24 盘点体例）
- tag_text：围场边角料 / 泳池时光、求婚喜讯与围场备战——荷兰大奖赛前 F1 车手们都在忙什么
- 标题：泳池时光、求婚喜讯与围场备战——荷兰大奖赛前 F1 车手们都在忙什么（原文 h1 "Pool days, proposals and paddock preparations – what F1 drivers have been up to ahead of the Dutch Grand Prix"）
- 作者：无（原文未署名）
- 发布时间：原文 Aug 18, 2026 1:25pm UTC → `published_at` 取北京时间 **2026-08-18T21:25:36.878+08:00（不跨日，beijing_date=20260818）**
- 来源：https://www.formula1.com/en/latest/article/pool-days-proposals-and-paddock-preparations-what-f1-drivers-have-been-up-to-ahead-of-the-dutch-grand-prix.2KrA7OHtUqcWbCbym44NpT
- 封面：**取 hero 图** `Social%20recap%20week%2010-08_Hero.webp`（cover_from=hero_only，正文 nimg=0、无 `t_` crop 前缀的 c_lfill,w_3392 原图，同 #15 情形）
- 抽取件：`extract2/25_2KrA7OHtUqcWbCbym44NpT.json`

抽取与转换备注：

- **cover_from=hero_only**（#15 先例）：正文无图（nimg=0），hero 图置 nodes[0]、alt 保持空串 ""、URL 无 `t_` crop 前缀；og_image（`Social%20share%20image-%20drivers%20summer%20break.webp`，w_2048）不入库；md 正文不放图链。
- 抽取件页面字段 intro（导语 "With the summer break slowly coming to an end…"）非正文块，不入库；summary 取正文第 1 段译文。
- 正文导语两段之后有 1 个 `video_slot`（原文嵌入视频位），不入库；无 `other` 空块。
- Instagram 嵌入共 **22 处**，原文 URL 照原样括注：其中 `Db6T6ehkc0V` **无尾斜杠**、`/reel/Db8HErZM8Yj/` 与 `/reel/Db-N3HeulRw/` 为 reel、5 条带 `?igsh=`/`?img_index=` 查询串，均逐码保留。
- 小标题 8 个 h3，全部保留原级别，无降级。
- 结构统计：nodes 75 = img 1 + h3 8 + p 66（正文 44 + IG 括注 22；meta np=44 与实写一致）；text 以 `\n\n` 分段，paras = 66 + 8 = **74**（#19 实证惯例：img 不占 text 段）。
- 引号处理：原文 9 处弯双引号转 ASCII 单引号——'annual European summer dump'→'一年一度的欧洲夏日照片合集'、'summa'、'Life is better when nobody knows what you are doing.'→'没人知道你正在做什么的时候，生活更美好。'、'Touch grass'→'该去踩踩草地了'、'the usual suspects'→'那帮老熟人'、'found a mountain'→'找到了一座山'、'lazy hikers'→'懒汉徒步者'、'the partying is over'→'狂欢结束了'、'Training camp going well,'→'训练营进展顺利，'（#20 铁律）。
- tags：lifestyle / culture + 实体中文译名（荷兰大奖赛、赞德沃特、夏休期、埃斯特班·奥康、卡门·蒙特罗·蒙德特、何沐妮）+ 文中点名现役车手 slug+号码成对：verstappen/3、russell/63、antonelli/12、piastri/81、lawson/30、hadjar/6、leclerc/16、hamilton/44、hulkenberg/27、lindblad/41、colapinto/43、gasly/10、albon/23、bortoleto/5、stroll/18、sainz/55、bottas/77（经车手号 API 核实，session 11412）。**奥康不在 2026 车手号表（哈斯二号车号为 CAMARA/51），不可猜测，只收中文名（#23 先例）。**
- 译名考证：霍肯伯格（库内 13 处先例）、博尔托莱托（20260905/20260908 先例，弃"博托莱托"）、科拉平托（弃语料 1 处异体"科拉皮多"）、阿维德·林德布拉德（20260923 先例）、斯托尔、博塔斯、塞恩斯、伊萨克·哈贾尔（库内多处先例）；何沐妮沿用 20261008 阿尔本专访定名（Lily Muni He）；Alpine、Racing Bulls、Williams Jet Tenders、SportsJet 520、OP81、UNO 保留原文。**卡门·蒙特罗·蒙德特、基卡·戈麦斯、弗拉维·巴尔拉、蒂芙尼·克伦威尔、亚历山德拉、莱奥为本文首次出现，译名系本文首创。**
- url_failures：空。校验：check_ingest.py 全绿（cover match True，badkey/children/MISMATCH 均空，无 SUSPECT，paras=74）。

---

随着夏休期缓缓接近尾声、荷兰大奖赛已在眼前，F1 车手们开始把沙滩、游艇和自行车换成训练与比赛备战。不过在围场重聚之前，车手们可没让这段假期虚度分毫。

从浪漫的求婚、阳光充沛的度假，到卡丁车、山野探险，甚至还有一次日食——赛道之外的精彩一点不少。以下是车手们在夏休期里的最新动态……

### 拉塞尔订下终身

对乔治·拉塞尔来说，这个夏天格外难忘——他宣布与交往多年的伴侣卡门·蒙特罗·蒙德特订婚。

这位梅赛德斯车手在海滩上一场温馨的烛光晚餐中求婚，两人随后不久便在 Instagram 上公布了这一喜讯。自 2020 年相恋至今，这对恋人很快收获了 F1 围场各方的祝福。

对他们俩而言，这是一个格外特别的夏天——恭喜这对幸福的人！

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db0xe_Djana/?utm_source=ig_web_copy_link）

### 海边充电

要说夏休期的标配，非阳光与大海莫属，车阵中不少人把这份享受发挥到了极致。

夏尔·勒克莱尔正与伴侣亚历山德拉、家人，还有当然少不了的小狗莱奥共度优质时光。看如画的风景、在水边一待就是一整天、再大把大把地放松——这位法拉利车手看起来已完全沉浸于围场之外的生活。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db6T6ehkc0V）

皮埃尔·加斯利的度假配方也相差无几。他晒出与伴侣基卡·戈麦斯和朋友们的照片：一起游泳、在池边慵懒度日，甚至还抽空打了一场网球。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db8yGqMDOdU/）

基米·安东内利则与朋友们过起了撒丁岛式的生活。游艇出海、冲浪、潜水排满了他的白天，随后这位少年又把水上时光换成了音乐与 DJ 作伴的夜晚。远离赛车的这几周，过得着实不赖！

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db8YPCKiqIY/?igsh=b3luOHRhMGdoYWox&img_index=1）

奥斯卡·皮亚斯特里同样在享受一个经典的欧洲之夏，晒出了自己的'一年一度的欧洲夏日照片合集'：落日、海边晚餐，还有骑上两轮探索各地的时光——只不过中途一次机械故障，意外给他安排了一次'进站'。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcIsMqbjo0a/?img_index=1）

如果说在水上放松太过宁静，埃斯特班·奥康就找到了另一种获取速度感的方式。这位哈斯车手开着来自 Williams Jet Tenders 的全新个性化定制 SportsJet 520 驰骋在日内瓦湖上，与伴侣弗拉维·巴尔拉共度悠闲时光。

谁说夏休期非得慢节奏？

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbvxZxsDS70/）

### 朋友、家人和那帮老熟人

夏休期和冬休期为车手们提供了难得的契机，可以长时间陪伴最亲近的人——这个假期，围场内外的温馨时光随处可见。

兰斯·斯托尔忙着与好友叙旧，晒出聚餐和外出的夜生活照片，还有一段顶着阳光、开着敞篷的兜风。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcGKxQXjjYJ/）

看来，几乎每个大奖赛周末都形影不离，对尼科·霍肯伯格和加布里埃尔·博尔托莱托来说仍然不够。这对奥迪队友把相处时光延伸进了夏休期，和朋友们一起泳池戏水、集体午餐，还来了一场被壮丽山景环抱的旅行。

你可以把车手带离围场，但要把队友拆开，显然就是另一回事了。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcETHAsiLb0/）

阿维德·林德布拉德也在拥抱自己的'summa'（夏日）——用他自己的话说。这位 Racing Bulls 新秀在假期里度过了 19 岁生日，随后晒出一组假日合集：下厨尝试、水上时光、和朋友们在海边晚餐。一路还顺便贡献了几句夏日箴言：'没人知道你正在做什么的时候，生活更美好。'

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcEhFgJjuYj/）

他的 Racing Bulls 队友利亚姆·劳森切换休假模式的方式则相当不同。这位新西兰人给夏日动态配的文案只有一句'Touch grass'（该去踩踩草地了），行程却塞满了越野摩托、舅舅带娃、与林德布拉德的晚餐——最后还不知怎么在半夜坐上了挖掘机的驾驶位。

我们说不清这些活动是怎么凑进同一份假期行程的，但要说劳森虚度了假期，那绝对冤枉。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db3O_-wG5yD/?img_index=1）

另一边，他的前队友伊萨克·哈贾尔正在西班牙与'那帮老熟人'度假，日程上是 UNO 纸牌、晚餐和充足的阳光。不过他也没能彻底摆脱健身房——随着回归日愈近，还是见缝插针练了一堂。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcHPttnkcdV/）

对卡洛斯·塞恩斯而言，假期同样带来了一些珍贵的家人时光。这位西班牙人晒出与父亲和侄子的温馨合影，一张照片让我们看尽三代人的潇洒风流。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db3oUbxoVN8/）

### 走进大自然

并非所有人都直奔最近的海滩。亚历克斯·阿尔本和未婚妻何沐妮转身进山，记录下一趟满是徒步、湖泊、美食停靠点，以及大量一如既往地不正经解说的旅程。

在凯旋般地'找到了一座山'之后，两人又自封'懒汉徒步者'，找到了湖，最后一路走到了海边。沿途似乎还出现过几次现金流小危机，但什么都拦不住这场冒险。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db_Is2NimW0/）

瓦尔特利·博塔斯几乎不需要任何出门的理由：他假期的一部分时光重新跨上两轮，与伴侣蒂芙尼·克伦威尔穿行在蒙大拿的林海群山之间，随后两人把美式冒险延续到了黄石。

在那里，博塔斯终于把骑行鞋换成徒步鞋，两人探索这座国家公园和它壮观的地热景观。看来就连博塔斯，也有让自行车放假的时候。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcEjME9GNP7/）

弗朗哥·科拉平托的假期也保持活跃：出门骑行、会友小聚，随后还目睹了天空中格外震撼的一幕——一次日食。

不过听起来，这位 Alpine 车手已经休闲够了。科拉平托宣称'狂欢结束了'，告诉粉丝一切就绪，自己等不及要重回赛场。

我们猜想，手痒想重新坐进赛车的绝不会只有他一个……

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcEzwFqDKDF/）

### 夏日型格

这个假期可不只是度假：皮亚斯特里和勒克莱尔都抽出时间站到镜头前，为各自的最新系列站台。

皮亚斯特里脱下赛服，换上远为松弛的装扮，为自己全新 OP81 系列的单品担任模特。说到底，还有谁比名字缩写就印在衣服上的本人大更适合出镜代言呢？

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Dbuz-P7jsdJ/）

勒克莱尔也在打磨自己的模特履历——为自己的夏季系列发布，他把阵仗搬到了水上。

这位摩纳哥人在游艇上试穿了一组宽松的帽衫和运动套装，莱奥自然再度出镜；拍完照，他又把拍摄现场变成了尾波冲浪场。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcBY6p7gOXl/?img_index=1）

### 刘易斯和奥康马不停蹄

科拉平托或许宣布了狂欢收场，但刘易斯·汉密尔顿似乎早就切换进了工作模式。

这位七届世界冠军陆续晒出自己备战回归的片段：核心训练、上肢练习，外加大量强度十足的自重项目。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/Db8HErZM8Yj/）

奥康同样在苦练。他更新了训练营动态，练力量，还用弹力带完成了至关重要的颈部训练。

'训练营进展顺利，'他写道。随着假期后首场比赛临近，这位法国人看起来早已蓄势待发，就等重新握住方向盘。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcEeMGvjUus/）

### 离不开赛车

当然，有些人连夏休期都熬不过去，非要找点什么来开一开。

回到巴西老家，博尔托莱托回归本源去跑了一场卡丁车。他开玩笑说，回家之旅若不重新坐进卡丁车，那就不算完整。

这位奥迪车手晒出了训练照片——从一身全套比赛装备来看，他对这些夏日圈速相当认真。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Db_ms68Adts/）

皮亚斯特里选了一条截然不同的'赛道'。这位澳大利亚人没去赛场，而是发动模拟器，在家里试了一把拉力。

其间有过一些亮眼的瞬间，也不乏几次相当惨烈的失误——所以眼下，大概还是开 F1 更稳妥。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/Db-N3HeulRw/）

### 谢谢你，赞德沃特

夏休期临近收官，对马克斯·维斯塔潘而言，这次回归赛场多了一层不同寻常的意义。

这位四届世界冠军为自己在赞德沃特的最后一场本土大奖赛揭幕了特别版头盔——荷兰站将在 2026 赛季结束后退出赛历。这款醒目的蓝白涂装处处向他的祖国致敬。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcA19PTDsE4/）

假期接近尾声，车手们正陆续把沙滩、群山和健身房换成比赛备战。一级方程式蓄势待发，所有人的目光此刻都投向赞德沃特。
