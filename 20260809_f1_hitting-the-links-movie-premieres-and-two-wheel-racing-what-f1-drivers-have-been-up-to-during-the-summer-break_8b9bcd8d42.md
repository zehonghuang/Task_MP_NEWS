- id：`n_f1_20260809_8b9bcd8d42`
- layout_code / type_code：`FEATURE` / `PADDOCK`（夏休期车手动态综述，同 #15/#25/#27 盘点体例）
- tag_text：围场边角料 / 挥杆、首映礼与两轮竞速——夏休期里 F1 车手们都在忙什么
- 标题：挥杆、首映礼与两轮竞速——夏休期里 F1 车手们都在忙什么（原文 h1 "Hitting the links, movie premieres and two-wheel racing – what F1 drivers have been up to during the summer break"）
- 作者：无（原文未署名）
- 发布时间：原文 Aug 9, 2026 8:38:08.560 UTC → `published_at` 取北京时间 **2026-08-09T16:38:08.560+08:00（不跨日，beijing_date=20260809）**
- 来源：https://www.formula1.com/en/latest/article/hitting-the-links-movie-premieres-and-two-wheel-racing-what-f1-drivers-have-been-up-to-during-the-summer-break.2XCoVGOnOdeDCUq5aymzwB
- 封面：**取 hero 图** `SummerSocialRecap_HERO.webp`（cover_from=hero_only，正文 nimg=0、无 `t_` 前缀的 c_lfill,w_3392 原图，同 #15/#25/#27 情形）
- 抽取件：`extract2/28_2XCoVGOnOdeDCUq5aymzwB.json`

抽取与转换备注：

- **cover_from=hero_only**（#15/#25/#27 先例）：正文无图（nimg=0），hero 图置 nodes[0]、alt 保持空串 ""；og_image（`Screenshot%202026-08-06%20at%2012.04.32.webp`）不入库；md 正文不放图链。
- 抽取件页面字段 intro（导语）非正文块，不入库；summary 取正文第 1 段译文。
- 正文导语两段之后有 1 个 `video_slot`（原文嵌入视频位），不入库。
- Instagram 嵌入共 **13 处**（奥康 1、阿尔本 1、博塔斯 2、高尔夫 2、水上 3、挚爱时光 2、测试 2），全部为裸 `/p/<码>/` 形态、无查询串，均逐码保留。
- 小标题 7 个 h3（奥康踏上红毯／阿尔本的南非'进站'／博塔斯重返赛场……只是换了两个轮子／绿茵之上……／……碧波之间／与挚爱共度的时光／测试圈、圈、还是圈），全部保留原级别。
- 结构统计：nodes 44 = img 1 + h3 7 + p 36（正文 23 + IG 括注 13；meta np=23 与实写一致）；text 以 `\n\n` 分段，paras = 36 + 7 = **43**（#19 实证惯例：img 不占 text 段）。
- 引号处理：正文无弯双引号（Grep 零命中）；两处主动加的 ASCII 单引号——h3"南非'进站'"（双关 pit stop/进站）与"'Estie' 客串"（奥康昵称转写保留）。
- tags：lifestyle / culture + 实体中文词（南非、高尔夫、UCI 碎石骑行世界系列赛、詹姆斯·邦德、车队名等）+ 文中点名现役车手 slug+号码成对：albon/23、bottas/77、hamilton/44、piastri/81、antonelli/12、russell/63、bortoleto/5、colapinto/43（经车手号 API 核实，session 11412）；奥康与预备车手杰克·克劳福德不在号码名单，仅中文名。
- 译名考证：奥康、弗拉维、蒂芙尼·克伦威尔、阿尔本、博塔斯、汉密尔顿、皮亚斯特里、安东内利、拉塞尔、博尔托莱托、科拉平托、《蜘蛛侠：全新一天》（#26 片名沿用）均有库内先例；**本文首创**：西里尔·拉马福萨（Cyril Ramaphosa）、阿兰·普罗斯特（Alain Prost）、贾斯汀·罗斯（Justin Rose）、杰克·克劳福德（Jack Crawford）、伊莎贝拉（Isabella）、赫林索（Hlinsko）、UCI 碎石骑行世界系列赛（括注原名 UCI Gravel World Series）、詹姆斯·邦德（James Bond）、凯迪拉克（车队名）。保留英文：Min Woo Lee（澳大利亚 PGA 球手）、Pirelli（#26 品牌保留先例）、'Estie'。
- url_failures：空。校验：check_ingest.py 全绿（cover match True，badkey/children/MISMATCH 均空，白名单 Estie/Min Woo Lee/UCI/Pirelli/Tiffany/"Gravel World Series" 后无 SUSPECT，paras=43）。

---

赛季前半程忙碌收官之后，F1 各车队与车手们正享受着当之无愧的休整。许多人选择在这段时间彻底断联、把放松进行到底；也有一些车手一路记录着自己的夏日动态。

从在电影首映礼上走上红毯，到把宝贵时光交给爱好与休憩，甚至重新回到赛道——车手们显然都乐在其中。以下是发车格上的各位在夏休期里的动向……

### 奥康踏上红毯

F1 里的资深漫威粉埃斯特班·奥康的夏休期，也许从第一分钟起就攀上了巅峰——这位哈斯车手受邀与伴侣弗拉维一起，在伦敦为《蜘蛛侠：全新一天》的首映礼走上红毯。

对这位法国人来说，过去几周早已是蜘蛛侠含量拉满。奥康不仅挑头做了与这一漫画 IP 的官方联名——在比利时和匈牙利大奖赛上戴出专属定制的蜘蛛侠头盔——还联手蜘蛛侠本人汤姆·赫兰德完成了它的揭幕。

最后再炫一把：奥康把这顶头盔当作独一无二的配饰带进了首映礼。无论在哪个宇宙，它都是一件艺术品！我们会继续期待未来在银幕上看到 'Estie' 客串……

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbaQOxUCJe1/）

### 阿尔本的南非'进站'

F1 车手早已习惯背靠背、三连赛比赛周里的跨国极限周转——但 10 小时的闪电往返完全是另一个量级！当大多数车手大概都在回家补觉、享受应得的休息时，亚历克斯·阿尔本却对南非做了一次短暂到访，参加威廉姆斯的车迷活动。

这趟行程他塞得满满当当：会见南非总统西里尔·拉马福萨，在威廉姆斯合作伙伴活动上同数千名车迷交流，还品尝了南非美食。

凭这趟短差，阿尔本成为自阿兰·普罗斯特 1993 年赢得南非大奖赛以来，首位踏上南非的威廉姆斯现役车手。有种预感他还想回来——也许下次待得久一点。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbTm5kLimes/）

### 博塔斯重返赛场……只是换了两个轮子

把竞速手请出 F1 赛车，也拦不住他去挠那处痒！瓦尔特利·博塔斯把夏休期前段投入了在赫林索举行的 UCI 碎石骑行世界系列赛（UCI Gravel World Series）。在 131 公里的角逐中，他不仅顶着众多老练职业选手拿下年龄组第五——这位多才多艺的芬兰人还拿到了世界锦标赛的入场券。

他的伴侣蒂芙尼·克伦威尔也在自己的组别中收获第七——恭喜这对骑行超级明星！

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Dbim91Tgma8/）

要是你担心博塔斯不懂得松弛，那么大可放心：到 8 月底赛季重启时，他一定已经休整到位。这位凯迪拉克车手还蒸了桑拿、游了公开水域，手持一杯彻底躺平——毕竟，生活讲究的就是平衡。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Dbbnb88ieDm/）

### 绿茵之上……

要是没有车手们涌向高尔夫球场，那还算休赛吗？如今的车手阵容里，很难找到一个不享受开几杆的人——这份从容让车手们在假期得以减压，同时也给了他们打磨心理强度与专注力的机会。

车手们在分享、比较各自差点时也相当好胜，因此有人去向行内顶尖高手讨教，也就不足为奇。刘易斯·汉密尔顿就在球场上与澳大利亚 PGA 球手 Min Woo Lee 同场交流——也许我们还能看到两人在赛道上联动？

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbhTvfOG4m4/）

F1 是如此讲究装备的运动，车手们想在高尔夫球场上也用最好的装备也就不奇怪了。迈凯伦今年早些时候宣布进军高尔夫之后，奥斯卡·皮亚斯特里看起来正设法与贾斯汀·罗斯一起跻身他们的职业队——真想看到这对组合！

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Dbp0GkxDkX8/）

### ……碧波之间

夏休期的另一大热门消遣是出海。不管是去海滩躺着，还是在船上消磨好时光，你几乎可以打包票：车手们泡在水里的时间一定比待在旱地上多。

不信请看。基米·安东内利在自己的社交账号晒出了夏休期的晨间日常——这位意大利人冲起了浪。而皮亚斯特里的水上夏日安排看起来更恬静些——但车手们已经开始怀念赛车的刺激，也完全情有可原。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbnwKETqTew/）

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbcsFElAnHN/）

另一位在海面尽兴的是乔治·拉塞尔。这位梅赛德斯车手没花多少功夫就把匈牙利的失落抛在身后，玩起了夏休期花样。他的假期以一场摩托艇兜风开场——配乐自然用的是詹姆斯·邦德的主题曲。

而这个系列眼下正在寻找饰演这一标志性角色的新演员——邦德？乔治·邦德，如何？

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbVqHPUtCoY/）

### 与挚爱共度的时光

夏休期和冬休期是车手们远离比赛周的兵荒马乱、与亲友共度优质时光的难得机会，他们自然会把这份时光用足。

加布里埃尔·博尔托莱托与朋友和伴侣伊莎贝拉在海边享受了惬意时光；奥康也在《蜘蛛侠》首映冒险之后，顺势当了几日游客。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DboL_qBIA4S/）

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/Dbs8rbijSC7/）

### 测试圈、圈、还是圈

匈牙利比赛收官之后，并非所有人都与围场一刀两断。远的不说，弗朗哥·科拉平托就在亨格罗宁多留了几天，作为 Pirelli 轮胎测试的一部分完成关键圈数。

与他同场的还有博尔托莱托，以及阿斯顿·马丁的预备车手杰克·克劳福德——三人围绕各种 C3 轮胎配方完成了一系列筛选测试。随后又跑了大量长距离，以评估最有潜力的性能与衰减特性。

这算不上休息，但车手们一听能多开几圈依然乐意之至，倒也毫不意外——科拉平托这几天还顺便在社交媒体上小展身手。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbVMxvlSNXg/）

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DbYuLmzjCLf/）

---

计数：nodes 44 = img 1 + h3 7 + p 36（正文 23 + IG 括注 13）；paras = 43；check_ingest.py 全绿。
