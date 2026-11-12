- id：`n_f1_20260820_2c458ed16d`
- layout_code / type_code：`FEATURE` / `PADDOCK`（赞德沃特重返赛历以来的 7 个难忘瞬间回顾，同 #09/#13/#15/#16/#17/#18/#19/#22/#23 盘点体例）
- tag_text：围场边角料 / 赞德沃特荷兰大奖赛的 7 个难忘瞬间
- 标题：摔碎的奖杯、库比卡复出与 F1 首秀——赞德沃特荷兰大奖赛的 7 个难忘瞬间（原文 h1 "Broken trophies, Kubica's comeback and F1 debuts – 7 memorable Dutch GP moments from Zandvoort"）
- 作者：无（原文未署名）
- 发布时间：原文 Aug 20, 2026 3:51pm UTC → `published_at` 取北京时间 **2026-08-20T23:51:52.245+08:00（不跨日，beijing_date=20260820）**
- 来源：https://www.formula1.com/en/latest/article/broken-trophies-kubicas-comeback-and-f1-debuts-7-memorable-dutch-gp-moments-from-zandvoort.4aUcZo2R5XMjxHUOIx9jfo
- 封面：**取正文首图（三图之首）** `GettyImages-2172554752.webp`（cover_from=body_first_image，`t_16by9North` w_3392 版，同 #09/#13/#16/#17/#18/#19/#22/#23 情形）
- 抽取件：`extract2/24_4aUcZo2R5XMjxHUOIx9jfo.json`

抽取与转换备注：

- **cover_from=body_first_image**：库比卡与乔维纳奇走进围场图为封面同值 src，json 中移至 nodes[0]，原位只保留图注段；hero 图（`dutch%20gp%20memorable%20moments.webp`，alt 空，URL 无 `t_` crop 前缀）与 og_image（`GettyImages-2233030115.webp`，`t_16by9South` w_2048 变体）均不入 json（#13/#16/#22/#23 先例）。
- 正文导语收尾段（第 3 段）之后有 1 个 `video_slot`（原文嵌入视频位），不入库。
- 维斯塔潘领奖台纪录末段与"库比卡重返赛场"小标题之间有 1 个 `other` 块（空 `<div>`，text 为空串），**不入库**——空容器无正文信息，与 video_slot 同口径处置（本条为该口径首次实证）。
- Instagram 嵌入共 **3 处**，原文 URL 均无尾随空格，照原样括注：`/p/DOB-yiLjnio/`、`/reel/DOBsNNXCevW/?hl=en`、`/p/DOCAT7ME1t6/?img_index=1`。
- 三张正文图 caption 完整，按先例**以 caption 全译**作 img alt 与图注段译文（alt 与图注译文一致，原图注英文括注保留）。
- 小标题 7 个 h3，全部保留原级别，无降级。
- 结构统计：nodes 39 = img 3 + h3 7 + p 29（导语 3 + 正文 20 + IG 括注 3 + 图注 3；meta np=23 已含导语）；text 以 `\n\n` 分段，paras = 29 + 7 = **36**（#19 实证惯例：img 不占 text 段）。
- 引号处理：原文 1 处弯双引号转 ASCII 单引号——里卡多自述 "either hit [Oscar] Piastri or hit the wall"→'要么撞上皮亚斯特里，要么撞墙'（#20 事故防范铁律）；三处"原图注"英文（Ricciardo's、Alonso's、driver's 等）均为直撇号，原样保留。
- tags：lifestyle / culture + 实体中文译名（荷兰大奖赛、赞德沃特、罗伯特·库比卡、安东尼奥·乔维纳奇、基米·莱科宁、塞巴斯蒂安·维特尔、迈克尔·舒马赫、丹尼尔·里卡多、罗比·威廉姆斯、皇家代尔夫特、代尔夫特蓝陶）+ 文中点名现役车手 slug+号码成对：verstappen/3、piastri/81、antonelli/12、norris/1、lawson/30、hadjar/6、alonso/14、gasly/10、leclerc/16（经车手号 API 核实）。**库比卡、莱科宁、维特尔、舒马赫、里卡多、乔维纳奇均不在 2026 车手号表（退役或离场），只收中文名、不配对号码。**
- 译名考证：维特尔（库内 34 处先例，弃"瓦特尔"）、阿尔法·罗密欧（20260904 先例）、AlphaTauri 与 Racing Bulls 保留英文（既有先例）；**安东尼奥·乔维纳奇、罗比·威廉姆斯、皇家代尔夫特、代尔夫特蓝陶为本文首创译名**；"大满贯"首次出现处括注原文 Grand Chelem / Grand Slam。
- url_failures：空。校验：check_ingest.py 全绿（cover match True，badkey/children/MISMATCH 均空，无 SUSPECT，paras=36）。

---

本周末，荷兰大奖赛将迎来最后一战，但自 2021 年重返赛历以来，赞德沃特早已为我们写下无数重磅剧情线。从大奖赛首秀、生涯首个领奖台到不可思议的复出——以下是我们最近几度造访荷兰时值得铭记的七个瞬间。

赞德沃特的回归原定于 2020 赛季，却因新冠疫情推迟；2021 年，这座赛道在阔别 36 年后重返赛历。这条独特的赛道浸润着 F1 历史，紧邻小镇的海滩，从阿姆斯特丹乘火车前来也只需 25 分钟。

从 3 号弯的倾斜坡度到海畔的地理位置，种种因素让这条老派赛道在 F1 的现代史中显得格外特别。

### 维斯塔潘的领奖台纪录

作为当今围场里唯一的荷兰籍车手，本周末的赞德沃特无疑又将迎来倾巢而出的橙色军团，为红牛车队的马克斯·维斯塔潘呐喊。自荷兰大奖赛重返赛历以来的头三场比赛全部由维斯塔潘获胜，而过去五届比赛他也从未缺席领奖台。

2021 年，维斯塔潘首次把杆位转化为胜利，看台上的声浪堪称惊人——接下来的两个赛季，他以同样的统治性表现连下两城。事实上，2023 年他在这里夺冠，追平了一位车手连续获胜场数的历史纪录——与塞巴斯蒂安·维特尔并列的九连胜；而下一场比赛这位荷兰人便超越了这一纪录：在 2023 年意大利大奖赛上，他成为 Formula 1 历史上首位达成 10 连胜的车手。

### 库比卡重返赛场

忙碌喧嚣的 2021 赛季里，有一条剧情线常常被人遗忘：罗伯特·库比卡代表阿尔法·罗密欧出战了两个比赛周末。这位波兰车手当时担任车队预备车手，在荷兰大奖赛周六清晨基米·莱科宁的新冠检测呈阳性后，被提拔顶替进入正赛车手阵容。

他从练习赛第三节便直接坐进驾驶舱——这位 2006 年匈牙利大奖赛完成 F1 首秀的车手，重返的却是赛历上对车手要求最苛刻的赛道之一——更了不起的是，多年前的拉力赛事故让库比卡的右臂至今活动受限。

![2021 年，罗伯特·库比卡与阿尔法·罗密欧队友安东尼奥·乔维纳奇走进赞德沃特围场。（原图注：Robert Kubica and his Alfa Romeo team mate Antonio Giovinazzi enter the Zandvoort paddock in 2021）](https://media.formula1.com/image/upload/t_16by9North/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2172554752.webp)

图注：2021 年，罗伯特·库比卡与阿尔法·罗密欧队友安东尼奥·乔维纳奇走进赞德沃特围场。（原图注：Robert Kubica and his Alfa Romeo team mate Antonio Giovinazzi enter the Zandvoort paddock in 2021）

同一个周末，库比卡在阿尔法·罗密欧的队友安东尼奥·乔维纳奇——如今和他一样也是勒芒 24 小时耐力赛冠军得主——做出了自己 F1 排位赛成绩并列最佳的表现，从第七位发车。

### 皮亚斯特里的生涯首个大满贯

在竞争激烈无比的 F1 世界，达成大满贯（Grand Chelem，更常见的说法是 Grand Slam）绝非易事：要在一个周末里同时拿下胜利、领跑全部圈数、杆位和最快圈速——世界锦标赛历史上只有 28 位车手做到过，而迈凯伦的奥斯卡·皮亚斯特里在上赛季的赞德沃特把自己的名字写进了这份名单。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DOB-yiLjnio/）

以 24 岁 4 个月零 25 天，他成为完成大满贯的历史第三年轻车手——直到本赛季早些时候，基米·安东内利在摩纳哥以 19 岁之身打破这一纪录，把皮亚斯特里挤了下去。这位澳大利亚人还为迈凯伦赢得了自 1998 年摩纳哥大奖赛以来的首个大满贯。

迈凯伦已经连赢两届赞德沃特——2024 年兰多·诺里斯在这里终结了维斯塔潘的统治，拿下生涯第二胜。本周末他们能实现三连冠吗？

### 利亚姆·劳森完成首秀

Racing Bulls 的利亚姆·劳森在 2023 年于此地完成了一场相当意外的大奖赛首秀：丹尼尔·里卡多在练习赛第二节撞墙后手部骨折。当时的情况是，里卡多前方先是他那位澳大利亚同胞奥斯卡·皮亚斯特里发生撞车，用他自己的话说，接下来只剩'要么撞上皮亚斯特里，要么撞墙'两个选项——这位当时的 AlphaTauri 车手最终碰到了护墙。来不及任何反应，方向盘砸中了他的左手，导致掌骨骨折——他因此缺席了接下来的五场比赛。

![2023 年荷兰大奖赛丹尼尔·里卡多受伤后，一脸稚气的利亚姆·劳森坐进了 AlphaTauri 赛车。（原图注：A fresh-faced Liam Lawson jumped into the AlphaTauri following Daniel Ricciardo's injury in the 2023 Dutch Grand Prix）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-1639634144.webp)

图注：2023 年荷兰大奖赛丹尼尔·里卡多受伤后，一脸稚气的利亚姆·劳森坐进了 AlphaTauri 赛车。（原图注：A fresh-faced Liam Lawson jumped into the AlphaTauri following Daniel Ricciardo's injury in the 2023 Dutch Grand Prix）

对当时担任车队预备车手的劳森而言，这是一次向红牛高层证明自己有能力胜任全职席位的绝佳机会。他在那场比赛中以第 13 名完赛，两场之后的新加坡大奖赛便拿下了生涯首波积分。

因为其他车手受伤而获得征召上场从来算不上愉快的事，但劳森证明了自己适应力强、早已准备好更上层楼——如今他已累积 46 场大奖赛参赛经历，最好成绩为第五名。

### 哈贾尔摔碎 F1 首座奖杯

历年荷兰大奖赛的奖杯都相当别致：从 2021 年的绿色玻璃高脚杯，到 2024 年印有关于心理健康鼓励语的古典款设计——后者灵感来自歌手罗比·威廉姆斯在阿姆斯特丹 Moco 博物馆的展览。

赛道主办方总能拿出令人难忘的物件，近两年更引入了皇家代尔夫特——这家荷兰历史名厂制作代尔夫特蓝陶已有数百年经验。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/DOBsNNXCevW/?hl=en）

上赛季，伊萨克·哈贾尔随 Racing Bulls 庆祝生涯首个领奖台时，上演了令人难以置信的一幕：在车队庆祝合影时，他的第三名奖杯底座磕到维修区地面，断成了两截。

哈贾尔那惊恐万状的表情让这一幕既滑稽又相当心碎——但别担心，赛事主办方火速备好了替补。奖杯撞毁仅仅一周后，荷兰大奖赛就把一座一模一样的复制品交到他手上，破碎的那座也归他保留，作为 F1 首个领奖台的纪念。

### 阿隆索打破舒马赫纪录

凭借 2023 年荷兰大奖赛的第二名，阿斯顿·马丁的费尔南多·阿隆索继续把名字写进纪录簿——那是他该赛季第七次登上领奖台，也打破了此前由迈克尔·舒马赫保持的一项纪录。

![费尔南多·阿隆索在 2023 年荷兰大奖赛获得的第二名，刷新了车手首次登台与最近一次登台之间间隔最久的纪录。（原图注：Fernando Alonso's second in the 2023 Dutch Grand Prix took the record for the longest gap between a driver's first and most recent F1 podium）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/trackside-images/2023/F1_Grand_Prix_of_The_Netherlands/1642486495.webp)

图注：费尔南多·阿隆索在 2023 年荷兰大奖赛获得的第二名，刷新了车手首次登台与最近一次登台之间间隔最久的纪录。（原图注：Fernando Alonso's second in the 2023 Dutch Grand Prix took the record for the longest gap between a driver's first and most recent F1 podium）

这位七届世界冠军曾保持着首次登台与最后一次登台之间间隔最久的纪录，而阿隆索把这一间隔拉长到了整整 7,463 天——从 2003 年马来西亚大奖赛初尝领奖台滋味，一直到 2023 年荷兰大奖赛。同年稍后，这位西班牙人在新加坡拿到了最近一次登台，使他首次与最后一次领奖台之间的最终间隔定格在 7,533 天。

那场比赛与维斯塔潘和阿隆索一同登上领奖台的是皮埃尔·加斯利——那是他作为 Alpine 车手的首次登台。

### 沙丘上的勒克莱尔

法拉利的夏尔·勒克莱尔只能退到旁边的沙丘顶上，坐看 2025 年荷兰大奖赛的剩余比赛——那幅画面简直像是会出现在文艺复兴油画里的场景。在 3 号弯与梅赛德斯的基米·安东内利发生接触后，比赛只剩最后几圈，勒克莱尔却无奈止步。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DOCAT7ME1t6/?img_index=1）

当电视镜头扫到他时，这位神情低落的摩纳哥车手很快弄到了一部手机——多半来自身边的赛道工作人员——好看看比赛余下的进程。没能完赛的不止他一个：迈凯伦的兰多·诺里斯同样在赛道的另一处滞留——他的赛车在比赛后段突发引擎故障。
