- id：`n_f1_20260828_61c5365f7b`
- layout_code / type_code：`FEATURE` / `PADDOCK`（退役车手生涯盘点+生活方式文化向，沿用 #11/#13/#16/#17/#18/#19 先例）
- tag_text：围场边角料 / 飞机、意面与残奥金牌
- 标题：飞机、意面与残奥金牌：10 位 F1 车手在赛道之外开启的意外生涯（原文 "Planes, pasta and Paralympic gold: 10 unexpected careers Formula 1 drivers pursued away from the racetrack"）
- 作者：无（抽取件 author=null，不记录）
- 发布时间：Aug 28, 2026 2:47pm UTC → `published_at` 取北京时间 `2026-08-28T22:47:24.557+08:00`
- 来源：https://www.formula1.com/en/latest/article/planes-pasta-and-paralympic-gold-10-unexpected-careers-f1-drivers-pursued-away-from-the-track.4PNphB91H0zG4aRsfHKC5r
- 封面：**取正文首图** `GettyImages-2172141603.webp`（cover_from=body_first_image，`t_16by9North` w_3392 版，同 #09/#13/#16/#17/#18/#19 情形）
- 抽取件：`extract2/22_4PNphB91H0zG4aRsfHKC5r.json`

抽取与转换备注：

- **cover_from=body_first_image**：劳达图（`GettyImages-2172141603.webp`）为封面同值 src，json 中移至 nodes[0]，原位只保留图注段；hero 图（`f1%20alterative%20careers%20header.webp`，alt 空）与 og_image（w_2048 变体）均不入 json（#13/#16 先例）。
- 导语 3 段之后有 1 个 `video_slot`（meta `non_body_blocks` 已记），不入库；正文无 skip_promo。
- 11 图 alt 均为截断碎片，按先例**一律以 caption 全译**作 img alt 与图注段译文；crop 模式：North（劳达、约翰松）、South（里贝罗、曼塞尔）、Centre×7；巴里拉图路径为 `2025/Miscellaneous/Barilla%20Pasta%20and%20Formula%201.webp`，其余皆 `2026/Lifestyle/ADHOC/`。
- 小标题 11 个 h3 全部保留原级别（末节为 "Honorary mention: Nigel Mansell" 译"荣誉提名：奈杰尔·曼塞尔——'魔术圈'会员"，仍作 h3）。
- 结构统计：nodes 80 = img 11 + h3 11 + p 58（导语 3 + 正文 44 + 图注 11；meta np=47 已含导语）；text 以 `\n\n` 分段，paras = 58 + 11 = **69**（#19 实证惯例：img 不占 text 段）。
- 引号处理：巴里拉引语原文弯双引号 `“…”`，json/md 均转 ASCII 单引号 `'…'`（#20 事故防范铁律）；'Jesus Saves' 原文即 ASCII 单引号保留；曼塞尔原图注 `world’s` 弯撇号在"原图注"内保留原字符。
- tags：lifestyle / culture + 退役车手 + 11 位车手中文名。全部为历史退役车手，**无现役车手 slug+号码成对 tags**（#16/#18/#19 先例）。
- summary 取正文首段译文（#19/#21 实证惯例：summary == nodes[1] 文本，不为 intro 字段另设节点）。
- url_failures：空。校验：check_ingest.py 全绿（nodes=80 img=11 h3=11 p=58、cover match True、badkey/children/MISMATCH 均空、paras=69）。
- 译名：Niki Lauda → 尼基·劳达；James Hunt → 詹姆斯·亨特；Paolo Barilla → 保罗·巴里拉；Minardi → 米纳尔迪；Carlos Reutemann → 卡洛斯·罗伊特曼；Nelson Piquet → 尼尔森·皮奎特；Juan Manuel Fangio → 胡安·曼努埃尔·方吉奥；Santa Fe → 圣菲省；Alex Ribeiro → 亚历克斯·里贝罗；Hesketh → 赫斯基斯；March → 马奇；Copersucar-Fittipaldi → 科普斯卡尔-菲蒂帕尔迪；Jaime Alguersuari → 海梅·阿尔格耶鲁阿里；Toro Rosso → 红牛二队；Jody Scheckter → 乔迪·谢克特；Laverstoke Park Farm → 拉弗斯托克公园农场；Hampshire → 汉普郡；Jacques Villeneuve → 雅克·维伦纽夫；Gilles Villeneuve → 吉尔·维伦纽夫；Alex Zanardi → 亚历山德罗·扎尔迪（正文用全名亚历山德罗）；Lausitzring → 劳希茨环形赛道；Brands Hatch → 品牌斯赫奇赛道；Stefan Johansson → 斯特凡·约翰松；Elio de Angelis → 埃利奥·德·安杰利斯；Innes Ireland → 伊内斯·爱尔兰；Watkins Glen → 沃特金斯格伦；Kirkcudbright → 库克达特；Nigel Mansell → 奈杰尔·曼塞尔；The Magic Circle → '魔术圈'。专名保留原文：Lauda Air 译名后附注 Niki、Laudamotion、Squire、DJ、'Jesus Saves'、Atletas de Cristo、CART、GT、TAG、Vetrung、《Private Paradise》《Father》、Indianapolis 500（印第 500 / 印第安纳波利斯 500 大赛）。

---

对 F1 车手来说，退役并不一定意味着离开这项运动。许多人离开驾驶舱坐进解说席，也有人成为车队领队、大使或车手经纪人——一只脚始终稳稳留在围场里。

但对另一些人而言，离开 F1 之后的生活转向了相当不同的方向。几十年来，前车手们放下赛车，拿起的可能是捕鱼拖网船、农场、DJ 打碟台，甚至是政治职务。

以下是 10 位 F1 车手，赛道之外的生涯把他们带去了相当意想不到的地方……

### 尼基·劳达——航空公司企业家

尼基·劳达在 F1 里没做成的事并不多。这位奥地利人在他两度效力这项运动的期间拿下三个世界冠军，与詹姆斯·亨特的 1976 年世界冠军之争早已载入史册；多年后他又以高层身份回到围场，先后在法拉利、捷豹和梅赛德斯任职。

但即便在驾驶生涯仍在展开的时候，劳达就已经有了另一份痴迷——航空。1979 年，也就是他第一次离开 F1 的那一年，他创立了劳达航空，着手打造一家最终在全球运营长途航线的国际航空公司。1982 年他加盟迈凯伦重返 F1 并夺得第三个世界冠军，三年后彻底挂盔，把全部精力转向航空业，此后又通过 Niki、Laudamotion 等创业项目不断扩大自己在航空领域的版图。

三届世界冠军得主，又在梅赛德斯日后的统治中扮演关键角色——对大多数人来说，这大概已经抵得上好几段生涯。但劳达还是不知怎地抽出了时间，同时成了一位成功的航空公司企业家。

![三届世界冠军尼基·劳达证明了自己在航空业同样成功，退役后创办并执掌了多家航空公司。（原图注：Three-time World Champion Niki Lauda proved just as successful in aviation, founding and leading multiple airlines after his racing career）](https://media.formula1.com/image/upload/t_16by9North/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2172141603.webp)

图注：三届世界冠军尼基·劳达证明了自己在航空业同样成功，退役后创办并执掌了多家航空公司。（原图注：Three-time World Champion Niki Lauda proved just as successful in aviation, founding and leading multiple airlines after his racing career）

### 保罗·巴里拉——意面企业高管

保罗·巴里拉的 F1 岁月相对短暂。这位意大利人 1989 年在日本大奖赛上代表米纳尔迪首秀，随后在两个赛季里参加了 15 场大奖赛，其中 9 场登上发车格，最佳完赛名次是第 11 名。不过他的赛车履历远不止 F1——最醒目的当属 1985 年勒芒 24 小时耐力赛的全场总冠军。

到 1991 年，巴里拉已经准备好换点新东西。幸运的是，一份相当有名的家族企业正等着他。

他先加入巴里拉法国公司，1994 年被任命为巴里拉集团副董事长，这个职位他一直担任至今。离开 F1 发车格三十多年后，当巴里拉在 2025 年成为 F1 官方合作伙伴时，他的两段生涯甚至撞到了一起。

在发布会上，巴里拉说：'一辆快如闪电的 F1 赛车和一盘美味的意面，它们有什么共同点？起初也许看不出来，但在两者背后，在打造它们所付出的努力里，都站着技艺精湛、满怀激情又意志坚定的专业人士，被不断精进的渴望推着往前走。'

也许赛车和意面的共同之处，比乍看之下要多……

![随着巴里拉在 2025 年成为官方意面合作伙伴，保罗·巴里拉把意面带进了 F1 围场。（原图注：Paolo Barilla brought pasta to the Formula 1 paddock, as Barilla became the Official Pasta Partner in 2025）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2025/Miscellaneous/Barilla%20Pasta%20and%20Formula%201.webp)

图注：随着巴里拉在 2025 年成为官方意面合作伙伴，保罗·巴里拉把意面带进了 F1 围场。（原图注：Paolo Barilla brought pasta to the Formula 1 paddock, as Barilla became the Official Pasta Partner in 2025）

### 卡洛斯·罗伊特曼——政治家

卡洛斯·罗伊特曼曾离 F1 世界冠军近在咫尺：他带着积分榜榜首的位置来到拉斯维加斯参加赛季收官战，却最终以一分之差把 1981 年的头衔输给了尼尔森·皮奎特。

到 1982 年离开 F1 时，这位阿根廷人已累积 12 个大奖赛分站冠军，确立了自己作为阿根廷史上最伟大车手之一的地位，仅次于五冠王胡安·曼努埃尔·方吉奥。短暂复出跑了一段拉力赛后，罗伊特曼踏入了一个竞争程度可以说丝毫不亚于 F1 的战场——政坛。

1991 年，他当选家乡圣菲省省长，任职至 1995 年，随后在 1999 年至 2003 年间再度出任省长。之后他进入阿根廷参议院，2009 年和 2015 年两度连任，一直担任参议员直到 2021 年去世。

罗伊特曼的政治声望高涨到被视为阿根廷总统的有力潜在候选人——但他在 2002 年拒绝参选。从争夺 F1 世界冠军到可能角逐国家最高职位，他的竞技人生显然没有终结在方格旗下。

![12 次 F1 分站冠军得主卡洛斯·罗伊特曼放下赛车，转身投入政坛。（原图注：A 12-time F1 race winner, Carlos Reutemann swapped racing for politics）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2229331368.webp)

图注：12 次 F1 分站冠军得主卡洛斯·罗伊特曼放下赛车，转身投入政坛。（原图注：A 12-time F1 race winner, Carlos Reutemann swapped racing for politics）

### 亚历克斯·里贝罗——体育牧师

熟悉亚历克斯·里贝罗赛车的人，对他人生最终的走向大概不会太惊讶。

这位巴西人上世纪 70 年代效力赫斯基斯、马奇和科普斯卡尔-菲蒂帕尔迪征战 F1，但同样让人过目不忘的，是他 F2 赛车上那句巨大的 'Jesus Saves'。基督教信仰贯穿他整个职业生涯，是他身份的重要部分；离开 F1 之后，更成为他生活中愈发庞大的组成部分。

里贝罗深度参与了基督运动员组织（Atletas de Cristo），支持全巴西的体育工作者，并担任其执行董事。这份工作把他带得远超赛车圈：他在多届世界杯期间为巴西国家足球队中的基督徒成员担任随队牧师，其中包括 1994 年在美国夺冠的那一届。

值得一提的是，第二段生涯竟又把他带回了 F1 围场。里贝罗后来既驾驶这项运动的医疗车，也继续从事牧灵工作——也就是说，即便大奖赛生涯结束几十年后，他依然找到了一个截然不同的方式，继续在最顶层帮助运动员。

![对成为体育牧师的亚历克斯·里贝罗而言，'Jesus Saves' 从来不只是一句标语。（原图注：'Jesus Saves' was more than a slogan on Alex Ribeiro's car as he became a sports chaplain）](https://media.formula1.com/image/upload/t_16by9South/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2249971322.webp)

图注：对成为体育牧师的亚历克斯·里贝罗而言，'Jesus Saves' 从来不只是一句标语。（原图注：'Jesus Saves' was more than a slogan on Alex Ribeiro's car as he became a sports chaplain）

### 海梅·阿尔格耶鲁阿里——DJ 与音乐制作人

海梅·阿尔格耶鲁阿里 2009 年匈牙利大奖赛上代表红牛二队完成 F1 首秀时年仅 19 岁，在当时成为这项运动历史上最年轻的车手。

但仅仅几年后，他的生活就面目全非。2011 年底失去红牛二队席位后，阿尔格耶鲁阿里继续征战电动方程式、GT 赛事等其他组别。然而他对赛车的热情渐渐消退，还只有二十五六岁的西班牙人最终决定彻底离开赛场。

幸运的是，另一份热情一直在同步生长。阿尔格耶鲁阿里在 F1 生涯期间就开始制作电子音乐，最终全职投入其中，以 Squire 之名演出——这个名字是向他的第二姓氏埃斯库德罗致意。此后，他以 DJ 和制作人的身份在全球发行音乐、登台表演。

很多车手都说过，离开 F1 之后需要找到新的节奏。阿尔格耶鲁阿里把这句话落实得相当字面化。

![海梅·阿尔格耶鲁阿里放下方向盘，以 DJ Squire 的身份转起了打碟台。（原图注：Jaime Alguersuari swapped steering wheels to spinning the decks as DJ Squire）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-92597276.webp)

图注：海梅·阿尔格耶鲁阿里放下方向盘，以 DJ Squire 的身份转起了打碟台。（原图注：Jaime Alguersuari swapped steering wheels to spinning the decks as DJ Squire）

### 乔迪·谢克特——农场主

乔迪·谢克特的 F1 生涯落幕时，已经握有一项至高成就。这位南非人为法拉利赢得 1979 年世界冠军，随后在 1980 年跑完效力车队的最后一个赛季后退役。

他离开赛车后的第一步就已颇不寻常。谢克特在美国创办了一家成功的射击训练技术公司——但就连这份事业，最终也让位于又一次惊人的转向……务农。

谢克特在汉普郡建立了拉弗斯托克公园农场，依照自然农耕与生物动力理念开发数千英亩土地。农场里养着绵羊、牛群，以及规模尤其庞大的水牛群，水牛奶被用来制作马苏里拉奶酪。农场还出产从肉类、冰淇淋到起泡酒等各种产品。

![世界冠军乔迪·谢克特离开了法拉利车库，走进了农家院落。（原图注：World Champion Jody Scheckter swapped the Ferrari garage for the farmyard）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2201438167.webp)

图注：世界冠军乔迪·谢克特离开了法拉利车库，走进了农家院落。（原图注：World Champion Jody Scheckter swapped the Ferrari garage for the farmyard）

### 雅克·维伦纽夫——唱作人

雅克·维伦纽夫在 27 岁生日之前，就收获了大多数赛车手梦寐以求的一切。1995 年他赢得印第安纳波利斯 500 大赛和 CART 年度总冠军，次年进入 F1，仅在第二个赛季就随威廉姆斯加冕世界冠军。

但在幕后，维伦纽夫还有另一份创作热情在悄然酝酿。多年来他一直写词、弹吉他，2006 年最后一次现身 F1 之后，他终于能给音乐分出多得多的精力。

成果就是 2007 年发行的《Private Paradise》，一张收录 13 首歌曲的原声专辑，曲目法语、英语皆有。其中 6 首由维伦纽夫亲自创作，包括致敬他已故父亲、法拉利传奇吉尔·维伦纽夫的《Father》。

公平地说，维伦纽夫的音乐生涯从未达到过他赛车生涯的高度——《Private Paradise》并没有冲进排行榜前列。但能有几位 F1 世界冠军敢说，自己在夺冠封王的赛车生涯之后，还发行过一张双语原声摇滚专辑？

![从世界冠军到唱作人，雅克·维伦纽夫放下方格旗，投身音乐。（原图注：From World Champion to songwriter, Jacques Villeneuve traded chequered flags for music）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2184723055.webp)

图注：从世界冠军到唱作人，雅克·维伦纽夫放下方格旗，投身音乐。（原图注：From World Champion to songwriter, Jacques Villeneuve traded chequered flags for music）

### 亚历山德罗·扎尔迪——残奥冠军

亚历山德罗·扎尔迪在 F1 之后的人生旅程，与这份名单上的任何其他人都不同。

这位意大利人在 90 年代征战 F1，但最辉煌的成就留在美国：1997 和 1998 年两度问鼎 CART 总冠军。2001 年，在德国劳希茨环形赛道的一场 CART 比赛中，扎尔迪遭遇惨烈事故，失去了双腿。

令人惊叹的是，他的赛车生涯并没有就此终结。扎尔迪驾驶加装改装操控装置的赛车重返竞技场，随后接触到手摇自行车——先参加马拉松，继而把目标锁定在残奥会。

2012 年伦敦残奥会，他在品牌斯赫奇赛道夺得两枚个人金牌——二十多年前他曾在这里比赛过——另收获团体接力银牌。四年后的里约，他又添两金一银，将残奥生涯奖牌总数提升至六枚。

扎尔迪于 2026 年 5 月去世，享年 59 岁，是同时代荣誉最卓著的残障自行车手之一。

![亚历山德罗·扎尔迪成为全球坚韧精神的图腾，赢得四枚残奥金牌。（原图注：Alex Zanardi became a global icon of resilience, winning four Paralympic gold medals）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-151458659.webp)

图注：亚历山德罗·扎尔迪成为全球坚韧精神的图腾，赢得四枚残奥金牌。（原图注：Alex Zanardi became a global icon of resilience, winning four Paralympic gold medals）

### 斯特凡·约翰松——艺术家

斯特凡·约翰松的赛车生涯几乎带他去了所有地方。这位瑞典人开过法拉利和迈凯伦的 F1 赛车，参加过印第卡系列赛，最终在 1997 年赢得勒芒 24 小时耐力赛。

但在这一切赛事之余，约翰松悄悄开始打磨一项截然不同的技艺。

1986 年，他的挚友、同为 F1 车手的埃利奥·德·安杰利斯意外离世，他此后开始作画，并曾解释说绘画帮助他消化了那段伤痛。

淡出驾驶后，约翰松把更多精力投入艺术与设计。他的作品常常直接取材于赛车——包括捕捉速度感的抽象画作、描绘他职业生涯瞬间的油画，甚至有一辆以搭载源自 F1 的 TAG 涡轮引擎的保时捷为原型打造的艺术车。

![斯特凡·约翰松离开赛车后的生活，将艺术与赛车融为一体。（原图注：Stefan Johansson's life after motorsport blended art and racing）](https://media.formula1.com/image/upload/t_16by9North/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2242876864.webp)

图注：斯特凡·约翰松离开赛车后的生活，将艺术与赛车融为一体。（原图注：Stefan Johansson's life after motorsport blended art and racing）

### 伊内斯·爱尔兰——职业渔民

伊内斯·爱尔兰本来就不太可能选择一份特别传统的退休生活。

进入 F1 之前，爱尔兰当过伞兵和工程师；在 50 年代末到 60 年代，他成了这项运动里最令人难忘的个性人物之一。1961 年，他在沃特金斯格伦赛道赢得美国大奖赛——那是莲花车队在世界锦标赛大奖赛中的首场胜利——由此也在车队史册上占据重要一页。

赛车生涯走到尾声后，爱尔兰回到苏格兰，把赛车换成了渔船。他以库克达特为基地，经营拖网渔船并亲自出海。当地记录显示，他买下并改装了一艘老旧的挪威拖网船 Vetrung，还另购一艘挪威船，将其改装用于捕龙虾。

不过，尽管驾驶的'机器'换了个天翻地覆，有些老习惯显然还在。上世纪 70 年代，一家知名赛车杂志前去探访爱尔兰，他出海归来后，当着岸上记者的面，驾驶渔船在狭窄的港湾里原地转了两圈。

换了载具，还是那个伊内斯·爱尔兰。

![退役之后，伊内斯·爱尔兰把大奖赛赛车换成了渔船。（原图注：Innes Ireland traded Grand Prix cars for fishing boats after retirement）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2232084038.webp)

图注：退役之后，伊内斯·爱尔兰把大奖赛赛车换成了渔船。（原图注：Innes Ireland traded Grand Prix cars for fishing boats after retirement）

### 荣誉提名：奈杰尔·曼塞尔——'魔术圈'会员

奈杰尔·曼塞尔也许没有把魔术变成第二职业，但这位 1992 年世界冠军确实把这个爱好认真到了足以成为'魔术圈'（The Magic Circle）会员的程度——这是世界上声誉最高的魔术师社团之一。

曼塞尔到了一定年纪才开始接触魔术。他说过，学习戏法如何帮助他挑战并重新训练大脑；在展示了技艺之后，他最终赢得了在这个著名社团中的一席之地。

这算不上转行——但成为货真价实的'魔术圈'会员，已经是一份相当了得的退休爱好了。

![奈杰尔·曼塞尔在赛车之外找到意外热情，跻身世界顶尖魔术师之列。（原图注：Nigel Mansell found an unexpected passion away from motorsport, earning his place among the world’s leading magicians）](https://media.formula1.com/image/upload/t_16by9South/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2193073997.webp)

图注：奈杰尔·曼塞尔在赛车之外找到意外热情，跻身世界顶尖魔术师之列。（原图注：Nigel Mansell found an unexpected passion away from motorsport, earning his place among the world’s leading magicians）
