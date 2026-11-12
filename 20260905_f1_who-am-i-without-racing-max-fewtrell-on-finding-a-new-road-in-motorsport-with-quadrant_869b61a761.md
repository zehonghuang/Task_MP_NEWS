- id：`n_f1_20260905_869b61a761`
- layout_code / type_code：`FEATURE` / `PADDOCK`（车手专访+生活方式文化向，沿用 #11/#13/#14/#15/#16 先例）
- tag_text：围场边角料 / '没有了赛车，我是谁？'——菲斯特雷尔与 Quadrant 的新道路
- 标题：'没有了赛车，我是谁？'——马克斯·菲斯特雷尔与挚友兰多·诺里斯并肩，借 Quadrant 找到赛车运动的新道路（原文 "'Who am I without racing?' Max Fewtrell on finding a new road in motorsport with Quadrant alongside best friend Lando Norris"）
- 作者：Special Contributor Lucy Dover（json 无作者字段，仅此处记录）
- 发布时间：Sep 05, 2026 1:44pm UTC → `published_at` 取北京时间 `2026-09-05T21:44:25.791+08:00`
- 来源：https://www.formula1.com/en/latest/article/who-am-i-without-racing-max-fewtrell-on-finding-a-new-road-in-motorsport-with-quadrant-alongside-best-friend-lando-norris.4isCzJHIwZqh4H3adT7CFe
- 封面：**取正文首图** `LE%20MANS%20SHIRT%20IMAGE.webp`（cover_from=body_first_image，同 #09/#13/#16 情形）
- 抽取件：`extract2/17_4isCzJHIwZqh4H3adT7CFe.json`

抽取与转换备注：

- **cover_from=body_first_image**：json 中封面 img 节点移至 nodes[0]（`cover_url` 与之同值，取正文图完整 src，w_3392 版），原位只保留图注段。
- 正文首图 **caption 为空但 alt 有值**（"Max Fewtrell (Credit: Quadrant)"，meta `image_caption_missing=1`）：按先例以 alt 为图注源，图注段与 img alt 均取该句全译。
- hero 图（`DISPLAY%20IMAGE%20OPTION%202.webp`，alt 空）与 `og_image`（`OPTION%201.webp` w_2048 变体）均**不入 json**（#13/#16 先例）。
- 第 4 图（`MAX%20AT%20SILVERSTONE.webp`）的 alt 比 caption 多出 "in both 2025 and 2026" 表述，**以 caption 为准全译**，alt 采用 caption 译文。
- 正文"…同场较量过"段之后有 1 个 `video_slot`，不入库；`skip_promo` 3 处（Internal link×2、LAS VEGAS 票务卡）不入库。
- Instagram 嵌入 **2 处**（`https://www.instagram.com/p/DR-VIPUDpj4/`、`https://www.instagram.com/reel/DN5ysqaiBqf/`），均以括注段入库。
- 小标题 7 个 h3，全部保留原级别。
- 结构统计：nodes 78 = img 5 + h3 7 + p 66（导语 1 + 正文 58 + IG 括注 2 + 图注 5）；text 以 `\n\n` 分段，paras = 66 + 7 = **73**。
- 译名：Max Fewtrell → 马克斯·菲斯特雷尔；Lando Norris → 兰多·诺里斯。品牌/场地专名保留原文：Quadrant、F1 Arcade、Eurocup、Made at Vale / Made in Vale（原文两种拼写并存，照原文保留）、Quadrant Live、Viagogo、YouTube。
- tags：lifestyle / culture + 实体专名（Quadrant、F1 Arcade）+ 文中点名现役车手 slug+号码成对：norris/1、sainz/55、bearman/87、bortoleto/5、albon/23（经车手号 API 核实）。菲斯特雷尔为非现役车手，不入车手 tags。
- url_failures：空。校验：check_ingest.py 全绿（nodes=78 img=5 h3=7 p=66、cover match True、badkey/children/MISMATCH 均空、SUSPECT 仅 Made at/in Vale 刻意保留）。

---

马克斯·菲斯特雷尔接受 F1.com 专访，谈他在赛车运动中如何找到新的道路、与兰多·诺里斯一起打造 Quadrant，以及为什么他依然怀念手握方向盘的日子。

每有一位车手抵达 Formula 1，就有无数人的青训之路在半途戛然而止。而对于那些几乎把整个人生都交给赛车的人来说，离开意味着要想清楚的不只是接下来做什么，还有没有了赛车，自己究竟是谁。

在马克斯·菲斯特雷尔童年的大部分时间里，生活都踩着赛历的节奏走。永远有下一个周末要准备，永远有下一个成绩要追逐，而心中最终的目的地只有一个——Formula 1。

如今，菲斯特雷尔依然通过 Quadrant 留在 F1 的世界里。意大利大奖赛前夕，他会到伦敦的 F1 Arcade 与车迷一起现场观赛——但他的赛车之旅曾经指向一个截然不同的方向。

菲斯特雷尔曾加冕英国 F4 总冠军，随后又拿下雷诺方程式 Eurocup 冠军，与一些最终闯进 F1 的年轻车手同场较量过。

但他自己的路在 2020 年 F3 赛季中途走到了尽头——只不过对菲斯特雷尔来说，起初这一点都不像是结束。

'我们到处跟车队谈，一点点意识到下一赛季的门正在一扇扇关上，'菲斯特雷尔在接受 F1.com 独家专访时说，'我们当时的想法是：“好吧，这一整年可能算是废了，但可以试着做点测试，明年再在 F2 找一支车队。”可时间一长，在缺少赞助商的情况下，这条路也不现实了。'

'甚至没有那样一个决定性的日子，让我意识到“哦，我再也赛不了车了”。它就是自然而然地，再也没有发生。'

![马克斯·菲斯特雷尔（图片来源：Quadrant）](https://media.formula1.com/image/upload/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/LE%20MANS%20SHIRT%20IMAGE.webp)

图注：马克斯·菲斯特雷尔（图片来源：Quadrant）。（原图注：Max Fewtrell (Credit: Quadrant)）

### 适应赛道之外的生活

对一个从九岁起就在赛车的人来说，失去比赛周末的节奏，意味着失去他生活赖以搭建的大半框架。当一个月一个月变成一年一年，菲斯特雷尔发现自己不得不直面一个难题：没有了赛车，他是谁？

'这个答案我到现在都还在摸索，'他承认，'没有可以期待、可以为之训练的比赛周末，真的太奇怪了，因为我从九岁起就一直过着那种日子。那是天翻地覆的变化。'

起初像是短暂的暂停，渐渐变成了某种更永久的事，迫使菲斯特雷尔重新审视自己的未来。'拖得越久，就越难接受、越难应对，'他说，'就是在那时，我真的开始追问：“不赛车的话，我是谁？我到底要做什么？”'

在 F3 赛季中途抽身离开已有六年，菲斯特雷尔如今能更从容地回望那个决定，却仍不免留下几点悬而未决的疑问。'对这个决定，我现在是一半一半，'他复盘道，'也许我当时应该把那个赛季熬完，留在圈子里，让大家看得见我。谁知道那样最终会打开哪些门呢。事后诸葛亮总是容易的。'

尽管游戏、高尔夫和板式网球仍能满足他的好胜心，菲斯特雷尔坦言，没有任何东西能复刻他在方向盘后经历过的情绪。'没有什么能复刻取得好成绩时的那种感觉。我再也没体会到坐在发车格上时那种心潮翻涌的紧张感。我不知道该怎么再找回它。这是我很难迈过去的一道坎。我太想念它了。'

### 见证诺里斯成为世界冠军

菲斯特雷尔赛车之后的生活里还有一个特别的注脚——他的挚友，是现任世界冠军兰多·诺里斯。

早在 Formula 1 的成功到来之前，菲斯特雷尔和诺里斯就已经是朋友。两人在卡丁车时代就是队友，走过几乎相似的青训道路，都拿过英国 F4 和雷诺方程式 Eurocup 冠军，之后职业生涯才分道扬镳。

![菲斯特雷尔与诺里斯的友谊，可以追溯到两人在青年组别同场竞技的岁月（图片来源：Quadrant）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/MAX%20AND%20LANDO.webp)

图注：菲斯特雷尔与诺里斯的友谊，可以追溯到两人在青年组别同场竞技的岁月（图片来源：Quadrant）。（原图注：Fewtrell’s friendship with Norris dates back to their years racing together in the junior categories (Credit: Quadrant)）

菲斯特雷尔一直保持着足够近的距离：奔赴各站比赛、看着诺里斯竞技，第一手地看到 Formula 1 的现实。不出所料，这偶尔会让他设想自己的职业生涯本可能走上的那条路。

'从来谈不上嫉妒，'他说，'我一直特别特别为他骄傲，能看到他用这样的水准持续发挥，真的太美妙了。'

'心里总会有那个“要是我也成功了会怎样？”——你能看到他的生活发生了怎样的变化。我就在第一现场，看得一清二楚。那就是梦想。'

'但能离 F1 那个世界这么近，某种程度上借回车手的眼睛去看它，真的很酷。跟他这么熟，我知道了当一名车手是什么滋味。我从来不用去猜……我现在知道了。我借着他看过了。'

2025 年，当诺里斯实现两人当年共同追逐的目标、首次加冕 Formula 1 世界冠军时，这种视角变得格外让人感慨。

'我觉得要跨过那道坎，他在心理上要迈出巨大的一步，'菲斯特雷尔说，'我不知道那种压力会是什么样子，因为我从没走到那一步，所以能看着他做到这一切，真的太棒了。'

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/p/DR-VIPUDpj4/）

不过菲斯特雷尔说，那个和他一起长大的人还是老样子。

'我个人没看到他有多大的变化，'他解释道，'显然，从 13 岁到现在 27 岁，我们都长大了。我们已经是很不一样的人，但我觉得内心里的那个兰多肯定没变。'

'他很大方，很善良。也许很多人没有看到他完整的一面，这没关系。他把那一面当作私事，但他绝对还是我从小一起长大的那个人，还是那家伙。'

### 菲斯特雷尔如何成为 Quadrant 的管理合伙人

2020 年兰多·诺里斯创立 Quadrant 时，菲斯特雷尔参与其中纯粹是作为朋友。已经不再赛车、但心里还盼着重返发车格的他，加入了诺里斯的内容创作。

'首先，我闲得发慌！'菲斯特雷尔大笑，'我已经不赛车了，所以没事可做。这事看起来很有意思，他就说：“我想找个朋友来跟我一起做，因为这活儿当时他一个人在扛。”'

'当时他拍片合作的人，未必都熟，所以他说：“来吧，跟我一起做。来拍几条视频，看看能走到哪。”……然后一切就像滚雪球，滚成了我们今天的样子。'

这颗雪球最终把菲斯特雷尔推到了 Quadrant 管理合伙人的位置上；随着诺里斯的重心越来越转向 Formula 1，他承担的角色也越来越重。'当兰多开始进入争冠的节奏……我就必须站出来，'他解释道。

'因为我们关系够近，他可以直接跟我沟通，然后我再进到公司里去推动。所以由我来接手这个角色是合理的——在他、我，还有品牌之间，做那个连接点。'

菲斯特雷尔认为，两人长期的友谊是这段合伙关系成立的关键。'我们认识的时间足够长，长到可以非常坦诚。所以如果对某件事有分歧，我会当下直说，事情就解决得快一些。'

'我们的沟通可以非常清楚直接，所以不用绕弯子，也不会有那种生怕踩到对方、处处小心翼翼的感觉。'

![除了幕后的职责，菲斯特雷尔在 Quadrant 承担的台前角色也越来越重（图片来源：Quadrant）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/MAX%20AND%20LANDO%20FILMING.webp)

图注：除了幕后的职责，菲斯特雷尔在 Quadrant 承担的台前角色也越来越重（图片来源：Quadrant）。（原图注：Fewtrell has taken on a growing public role within Quadrant alongside his responsibilities behind the scenes (Credit: Quadrant)）

### 把更多 F1 车手带进 Quadrant 的世界

诺里斯依然是 Quadrant 的中心，但他越来越不是唯一出现在其中的 F1 车手。

卡洛斯·塞恩斯、奥利弗·贝尔曼、加布里埃尔·博尔托莱托和亚历山大·阿尔本，都是已经出现在其内容里的熟面孔——Quadrant 想要触达的，是早已支持创始人的那群人之外的赛车迷。

'我们并不希望它变成“兰多是唯一上我们节目的车手”，'菲斯特雷尔说。

'我觉得其他车手来到这里，对我们意义巨大——正是这样，我们才能成长为一个赛车枢纽，建起一个由热爱赛车的人组成的庞大社区。'

'你不必非要是兰多的粉丝，也能享受我们做的内容。我觉得这才是关键：让所有其他车手都来过，这样其他人也能走进 Quadrant、融入这个社区，可能是因为他们的偶像来过，而不只是因为一切都围着兰多转。'

他们的目标不是复刻车手们与自己的车队已经在制作的内容。菲斯特雷尔说，理念其实很简单：'我们就单纯地享受这件事。'凭借超过一百万的 YouTube 订阅者，Quadrant 也让车手得以触达传统比赛周末之外的大量观众。

（原文此处嵌入 Instagram 帖子：https://www.instagram.com/reel/DN5ysqaiBqf/）

'对那些刚登上发车格的年轻人来说，来频道做客是有好处的，因为我们已经有这批观众在，这里能帮他们搭建自己的平台，'菲斯特雷尔说。

'所以这是皆大欢喜的事，而且我们还能收获一个愉快的下午！'

### 从百万播放，到与车迷面对面

随着 Quadrant 在 F1 的存在感不断扩大，它与车迷互动的方式也在扩展。

这个曾经几乎完全面向线上的品牌，越来越多地走进实体空间：先后在墨尔本和伦敦开出快闪店，随后又在 2026 年英国大奖赛周末，登上银石 Made at Vale 舞台办起 Quadrant Live。

'简直难以置信，'菲斯特雷尔谈起 Made in Vale 时说，'我不知道该怎么形容……看到那么多人到场来看你，或者来看这个品牌，实在太不可思议了。'

'有时候你会迷失在屏幕上的数字里，意识不到真人到底有多少。你看到视频拿到 5,000,000 次播放……但到了现场，一切都突然有了具体的分量。'

![在英国大奖赛周末的 Made in Vale 现场，菲斯特雷尔亲身感受到了 Quadrant 社区的规模（图片来源：Quadrant）](https://media.formula1.com/image/upload/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/MAX%20AT%20SILVERSTONE.webp)

图注：在英国大奖赛周末的 Made in Vale 现场，菲斯特雷尔亲身感受到了 Quadrant 社区的规模（图片来源：Quadrant）。（原图注：Fewtrell experienced the scale of Quadrant’s community first-hand at Made in Vale during the British Grand Prix weekend (Credit: Quadrant)）

这些互动也让菲斯特雷尔看到，围绕 F1 建立的社区，完全可以超出'看赛道上发生了什么'的范畴。

'我从追随我们的人那里听到了太多故事——他们通过 Quadrant 交到了朋友，'他解释道。

'就是那种社区感，让人觉得自己是我们在做的事情的一部分，有一种归属。这是一个大家可以来享受的地方，一个安全的空间。'

'人们走进快闪店，跟我们聊天、叙旧，问问上一条视频，顺便带走一件 T 恤。大家身上穿的都是同一套东西。我觉得正是这样的小事，其实承载着很多意义。'

### 为什么 F1 Arcade 是下一步

这份专注会在意大利大奖赛期间延续：Quadrant 与 Viagogo 合作，把一场赛车观赛活动搬进 F1 Arcade 的线下。

这场活动包含 F1 Arcade 的模拟器、赠品和互动式比赛预测，赛前还有菲斯特雷尔与 Quadrant 团队其他成员参与的问答环节。这个赛车品牌此前已经试水过线上观赛活动，把其中一场带进实体的 F1 空间，像是顺理成章的演进。

'我们在线上办过不少次观赛活动，而面对面、有真人到场，绝对是我们接下来可以发力的地方，'菲斯特雷尔说。

'还是那个社区属性。我们真的在专注建设这个社区，尽可能多地做线下、面对面的活动。'

'所以我觉得，办一场线下观赛活动就是下一步。'

离开赛车六年后，菲斯特雷尔走到了一个颇有意味的位置。他没能以童年想象的方式抵达 F1，但这项运动依然贯穿着他的工作、友情，以及那门把车迷带向车手的生意。

![卡洛斯·塞恩斯是参加过 Quadrant 活动的 F1 车手之一（图片来源：Quadrant）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/New1.webp)

图注：卡洛斯·塞恩斯是参加过 Quadrant 活动的 F1 车手之一（图片来源：Quadrant）。（原图注：Carlos Sainz is one of the F1 drivers who has been part of Quadrant events (Credit: Quadrant)）

### 菲斯特雷尔对未来的期许

菲斯特雷尔说，现在的他对自己未能进入 Formula 1 已经释然，不再耿耿于怀……大多数时候是这样。

'只是偶尔在某个夜里，它会悄悄爬上来，'他承认，'你知道那种感觉——躺在床上，某个糟糕的念头突然冒出来。'

他也并没有完全关上再次成为赛车手的那扇门。当被问及接下来想成就什么，答案很快就回到了座舱。

'我很确定，总有一天我想去跑勒芒——勒芒或者代托纳。我想回到车里，'他说，'那大概是个很大的梦想，但我真的很想去做。'

'我只想要快乐。这就是一切的意义。我以前对很多事情想太多、压力很大，所以我真的有在努力把生活做减法，而那些最重要的东西都已经在了。'

'真正重要的，其实就只有这些。'
