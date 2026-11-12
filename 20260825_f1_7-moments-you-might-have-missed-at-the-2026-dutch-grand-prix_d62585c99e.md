- id：`n_f1_20260825_d62585c99e`
- layout_code / type_code：`FEATURE` / `PADDOCK`（赞德沃特周末场外瞬间跨界盘点，沿用 #15《意大利大奖赛 7 个瞬间》同构先例）
- tag_text：围场边角料 / 2026 荷兰大奖赛的 7 个瞬间
- 标题：2026 年荷兰大奖赛中你可能错过的 7 个瞬间（原文 "7 moments you might have missed at the 2026 Dutch Grand Prix"）
- 作者：无（原文未署名）
- 发布时间：原文 Aug 24, 2026 4:59pm UTC → `published_at` 取北京时间 **2026-08-25T00:59:59.021+08:00（跨日，以 meta 的 beijing_date=20260825 为准）**
- 来源：https://www.formula1.com/en/latest/article/7-moments-you-might-have-missed-at-the-2026-dutch-grand-prix.4t3kCjgPEAW6I7xS6ILPT4
- 封面：**取正文首图（也是唯一图）** `GettyImages-2291711293.webp`（cover_from=body_first_image，`t_16by9Centre` w_3392 版，同 #09/#13/#16/#17/#18/#19/#22 情形）
- 抽取件：`extract2/23_4t3kCjgPEAW6I7xS6ILPT4.json`

抽取与转换备注：

- **cover_from=body_first_image**：诺里斯与马丁·盖瑞克斯合影为封面同值 src，json 中移至 nodes[0]，原位只保留图注段；hero 图（`2026%20dutch%20gp%20social%20moments.webp`，alt 空，URL 无 `t_` crop 前缀）与 og_image（`GettyImages-2291278120.webp`，`t_16by9North` w_2048 变体）均不入 json（#13/#16/#22 先例）。
- 正文第 3 段（导语收尾段）之后有 1 个 `video_slot`（原文嵌入视频位），不入库。
- Instagram 嵌入共 **10 处**，形态混合：`/reel/` 短链 5 处（DcQ7Qhford5、DcRTjBqoaDv、DcTHC_Asd92、DcTDKAfN41_、DcRAOt8oSNR），`/p/` 短链 5 处（DcRDpdySMEn、DcRFriODhKq、DcO4TPaiH_H、DcYQYZ6GvRp、DcZTnE9jNCF）；`igsi` 取值 `NTc4MTIwNjQ2YQ==`、`MzRlODBiNWFlZA==` 并存（各 2 处），末尾 2 处用 `?hl=en&img_index=2/5`。**原文 7 条 IG URL 带尾随空格（DcQ7Qhford5、DcRTjBqoaDv、DcRDpdySMEn、DcRFriODhKq、DcRAOt8oSNR、DcO4TPaiH_H、DcYQYZ6GvRp），括注中已去除空格、其余照原样。**
- 原文笔误 "Max Verstappen , after"（第 3 导语段，多余空格）按正译处理。
- 正文图 alt 为截断碎片，按先例**以 caption 全译**作 img alt 与图注段译文。
- 小标题 7 个 h3，全部保留原级别，无降级。h3 "Brick-o Hulkenberg" 为乐高（Brick）×霍克（Hock）双关，译作"'积木霍克'驾到"；"Was that…a T-Rex on track?" 中 T-Rex 保留英文。
- 结构统计：nodes 41 = img 1 + h3 7 + p 33（导语 3 + 正文 19 + IG 括注 10 + 图注 1；meta np=22 已含导语）；text 以 `\n\n` 分段，paras = 33 + 7 = **40**（#19 实证惯例：img 不占 text 段）。
- 引号处理：原文 3 处弯引号转 ASCII 单引号 `'…'`（#20 事故防范铁律）——弯双 "the summer break is over"→'夏休结束了'、"one-touch challenge"→'一脚出球挑战'，弯单 ‘Last Lap’ → 'Last Lap'（保留英文并入白名单）；"Trix" 原文无引号，译文加 'Trix' 标示致敬对象；正文各处弯撇号（Zandvoort’s、Saturday’s、drivers’ 等）位于原文引用部分，不受影响。
- tags：lifestyle / culture + 实体中文译名（荷兰大奖赛、赞德沃特、德米·福勒林、世爵、乐高、英超、马丁·盖瑞克斯、埃斯特班·奥康）+ 文中点名现役车手 slug+号码成对：norris/1、antonelli/12、russell/63、leclerc/16、verstappen/3、lawson/30、bearman/87、hulkenberg/27、bortoleto/5、hamilton/44（经车手号 API 核实）。**奥康不在 2026 车手号表中（哈斯二号为 Camara），故仅收中文名标签、不配对号码。**
- url_failures：空。校验：check_ingest.py 全绿（cover match True，badkey/children/MISMATCH 均空，无 SUSPECT）。

---

红、白、蓝三色的旗帜，在看台上那片令人难忘的橙色人潮中迎风挥舞——赞德沃特的'Last Lap'或许没能给主场车迷换来童话般的结局，但这场比赛绝对是一段跌宕起伏的过山车。

卫冕世界冠军兰多·诺里斯奉献了一堂策略大师课，外加数次干脆漂亮的超车，把大奖赛两连胜收入囊中；与他共享领奖台的是积分榜领跑者基米·安东内利和乔治·拉塞尔——拉塞尔刚在周六的冲刺赛中压过夏尔·勒克莱尔夺冠，诺里斯在冲刺赛里拿到第三。

马克斯·维斯塔潘没能等到在主场重返领奖台的那一刻——首圈末段一场严重撞车之后，这位荷兰车手自己走出了赛车。但赛道上的拼杀只是这个荷兰大奖赛周末特别之处的一部分——以下是你可能错过的场外瞬间……

### 当冠军遇上冠军

主场大奖赛永远是特别的，哪怕对维斯塔潘这样身经百战的车手也不例外——只不过这位四届世界冠军可能在两个轮子上遇到了真正的对手：周末的比赛开赛前，他接待了荷兰自行车明星德米·福勒林。

福勒林 2023 和 2026 年两夺环法女子赛总冠军，2026 年问鼎环意女子赛，还在 2024 和 2025 年两度赢得环西班牙赛冠军——在维斯塔潘于赞德沃特的最后一场主场比赛开始前，她在自己最新到手的黄衫上为这位红牛车手签下名字——她还体验了一整圈赛道的高速飞驰。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/DcQ7Qhford5/）

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/DcRTjBqoaDv/）

这还不是麦克斯这个周末唯一的签名球衣插曲。他和利亚姆·劳森一起登台与车迷共度时光时，主持人请他为一位过生日的小车迷签件球衣。唯一的问题：那是件法拉利球衣！

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/DcTHC_Asd92/?utm_source=ig_web_copy_link&igsi=NTc4MTIwNjQ2YQ==）

### 鸭子最爱的好天气

要说什么最能宣告'夏休结束了'，非回归围场首日的这场雨莫属。周四的赞德沃特和阳光毫无关系——那不如就着水坑和橡皮鸭找点乐子？

没错，就是橡皮鸭。迈凯伦可没放过这个机会，让两只鸭子在雨中完成了一场湿漉漉的'支线任务'。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcRDpdySMEn/）

显然，在这样的大雨里玩得开心的，不止迈凯伦的社媒运营。

奥利弗·贝尔曼和埃斯特班·奥康开着卡丁车在雨中刷了几圈热身，想把橡皮鸭的风头抢过来。两位哈斯车手看起来充满电，准备好迎接赛季下半程在赛道内外抛来的一切。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcRFriODhKq/）

### 足球重回围场

回到欧洲的不止 F1 的引擎，整个欧洲的足球赛季也已开踢。这个周末，英超球队重回绿茵场，F1 阵中的两位英国车手也决定试试自己的眼力和脚法。

乔治·拉塞尔已经证明了自己的预言功力吗？或者说，还没有？他给出了一份 2026/2027 赛季英超最终排名的完整预测。

下一个问题是：赛季收官时，他能猜对多少个？

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/DcTDKAfN41_/?utm_source=ig_web_copy_link&igsi=MzRlODBiNWFlZA==）

与此同时，刘易斯·汉密尔顿在法拉利房车里秀起了脚法，玩得不亦乐乎地来了一局'一脚出球挑战'——围场里谁能赢过刘易斯爵士？

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/DcRAOt8oSNR/?utm_source=ig_web_copy_link&igsi=NTc4MTIwNjQ2YQ==）

### '积木霍克'驾到

寿星尼科·霍肯伯格从夏休归来的时机恰到好处——他正好赶上在围场里，与奥迪车队众人以及队友加布里埃尔·博尔特罗一同庆祝自己的 39 岁生日。

在如潮的生日祝福和礼物中，'霍克'最开心的还是他的新玩具：一个特别的奥迪方向盘——还能是什么材料做的？当然是乐高。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcO4TPaiH_H/?utm_source=ig_web_copy_link&igsi=MzRlODBiNWFlZA==）

### 世爵重返发车格

最近几站，乐高凭迈阿密和银石车手游行的座驾抢尽了风头，但荷兰大奖赛的这场告别演出上，赛事组织者袖中还藏着一招漂亮的后手。

本土跑车品牌世爵曾在 2007 年征战 F1 一个赛季——赞德沃特的正赛巡游圈上，正是 22 辆 C8 Spyder 组成的车队载着车手们环绕赛道，稳稳站上了全场焦点。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcYQYZ6GvRp/?hl=en&img_index=2）

### 赛道上那是……一头霸王龙？

聚光灯固然打在车手身上，赛道工作人员也早已凭实力成为车迷心头好。在赞德沃特于 F1 赛历的最后一次亮相中，他们献上了又一场令人难忘的表演。

有人看到，巡游圈中有几位赛道工作人员穿着充气恐龙服向车手挥旗放行——大概是在向'Trix'致敬吧？这具霸王龙化石就收藏在邻近的莱顿，名字取自荷兰前女王贝娅特丽克丝。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DcZTnE9jNCF/?hl=en&img_index=5）

### 诺里斯的完美谢幕曲

兰多·诺里斯的夏休似乎达到了理想效果。这位卫冕世界冠军用匈牙利和荷兰的两连胜，把三周假期夹在了正中——而在赞德沃特帮他庆祝的，正是一张老熟人面孔。

假期里，诺里斯恰逢好友马丁·盖瑞克斯在伊维萨驻场演出，两人相约小聚；于是这位荷兰人也来到了现场——人到现场，也上了打碟台——用一场史诗般的赛后演出，向这条赛道作别 F1 的最后一舞。

![荷兰大奖赛冠军兰多·诺里斯与马丁·盖瑞克斯合影。（原图注：Dutch Grand Prix winner Lando Norris with Martin Garrix）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2291711293.webp)

图注：荷兰大奖赛冠军兰多·诺里斯与马丁·盖瑞克斯合影。（原图注：Dutch Grand Prix winner Lando Norris with Martin Garrix）
