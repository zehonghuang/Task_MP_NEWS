- id：`n_f1_20260904_c959748235`
- layout_code / type_code：`FEATURE` / `PADDOCK`（历史科普+生活方式文化向，沿用 #11/#13/#14/#15/#16/#17/#18 先例）
- tag_text：围场边角料 / 法拉利涂装史：Rosso Corsa 与那些不红色的年代
- 标题：法拉利传奇 F1 涂装史：'Rosso Corsa'，以及他们不红色参赛的那些年代（原文 "A history of Ferrari's iconic racing liveries in F1: 'Rosso Corsa' and all the times they haven't raced in red"）
- 作者：Special Contributor Katy Fairman（json 无作者字段，仅此处记录）
- 发布时间：Sep 04, 2026 9:58am UTC → `published_at` 取北京时间 `2026-09-04T17:58:15.341+08:00`
- 来源：https://www.formula1.com/en/latest/article/a-history-of-ferraris-iconic-racing-liveries-in-f1-rosso-corsa-and-all-the-times-they-havent-raced-in-red.5gK8REBWYiX2h36Hv2Jcir
- 封面：**取正文首图** `GettyImages-2229476247.webp`（cover_from=body_first_image，同 #09/#13/#16/#17/#18 情形）
- 抽取件：`extract2/19_5gK8REBWYiX2h36Hv2Jcir.json`

抽取与转换备注：

- **cover_from=body_first_image**：json 中封面 img 节点移至 nodes[0]（`cover_url` 与之同值，取正文图完整 src，`t_16by9South` w_3392 版），原位只保留图注段。
- 第 2 图（`ferrari-monza-livery-2026-4.webp`）**alt 为空**（meta `image_alt_missing=1`）；另外三图 alt 均为截断碎片。按先例**四图一律以 caption 全译**作为图注段文本与 img alt。
- hero 图（`Italian%20Grand%20Prix%20Header%20Image.webp`，alt 空）与 `og_image`（`Italian%20Grand%20Prix%20Thumbnail.webp` w_2048 变体）均**不入 json**（#13/#16 先例）。
- 正文"法拉利是 Formula 1 历史上最成功的车队…"段之后有 1 个 `video_slot`，不入库；`skip_promo` 1 处（Internal link：马拉内罗第一台机器段后）不入库。
- 小标题 3 个 h3，全部保留原级别。原文三处"法拉利以蓝/黄/绿色参赛的时候"为加粗引导句，抽取件记作普通 p，**照抽取件保留 p 类型**，不作 h3。
- 结构统计：nodes 33 = img 4 + h3 3 + p 26（导语 1 + 正文 21 + 图注 4）；text 以 `\n\n` 分段，paras = 26 + 3 = **29**。
- 译名：Enzo Ferrari → 恩佐·法拉利；John Surtees → 约翰·苏尔斯；Olivier Gendebien → 奥利维耶·让德比安；Alfa Romeo → 阿尔法·罗密欧；Maserati → 玛莎拉蒂；North American Racing Team → 北美赛车队；Spa-Francorchamps → 斯帕-弗朗科尔尚；Maranello → 马拉内罗。专名保留原文：Rosso Corsa、Rosso Scuderia、Scuderia、Alpine、Vanwall、Formula Libre、法拉利 125 S、'鲨鱼鼻'（sharknose 意译）。
- tags：lifestyle / culture + 实体词（法拉利、Rosso Corsa、F1 涂装、意大利大奖赛、蒙扎）。文中车手（苏尔斯、让德比安）均为历史退役车手，不入现役车手 slug+号码成对 tags（#16/#18 先例）。
- url_failures：空。校验：check_ingest.py 全绿（nodes=33 img=4 h3=3 p=26、cover match True、badkey/children/MISMATCH 均空、SUSPECT 空）。

---

法拉利为什么用红色参赛？答案藏在那段久远的历史里——其中既有这一标志性颜色的不同深浅，也有对 Scuderia 传统形象几次出人意料的背离。

传说，恩佐·法拉利说过：'随便让一个孩子画一辆车，他一定会把它涂成红色。'Scuderia Ferrari 与 'Rosso Corsa' 的猩红，是赛车运动里最具标志性的色彩组合之一——而这段缘分是从哪里开始的？蒙扎的意大利大奖赛在即，法拉利又恰好在速度圣殿启用那套致敬舒马赫的特别涂装，我们不妨一起坐上时光机回顾一番。

法拉利是 Formula 1 历史上最成功的车队，握有创纪录的 16 座车队世界冠军，也从来都与那一身鲜红涂装绑定在一起。

本周末，车队正带着一套特殊涂装参赛，纪念迈克尔·舒马赫 1996 年在蒙扎的胜利——车头鼻翼上缀着七颗星，对应这位传奇的七个车手世界冠军。

### 为什么法拉利是红色的？

在车队还能像今天这样大规模定制涂装之前，赛车的颜色是按国籍分配的。这些标准化颜色让一支车队或一位车手来自哪个国家一目了然，而其中一些被分配到的颜色，今天仍留在今代的赛车上。

![早在赛车运动的初创年代，红色就成了法拉利的代名词。（原图注：Red has become synonymous with Ferrari from the very early days of motorsport）](https://media.formula1.com/image/upload/t_16by9South/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2229476247.webp)

图注：早在赛车运动的初创年代，红色就成了法拉利的代名词。（原图注：Red has become synonymous with Ferrari from the very early days of motorsport）

意大利是红色。在 F1 世界锦标赛的最初几个赛季，这个颜色由法拉利和其他意大利厂商共享——比如阿尔法·罗密欧和玛莎拉蒂。法国是蓝色，就像今天的 Alpine；英国是绿色，如今阿斯顿·马丁的赛车上就能看到；德国则是白色。

这些颜色渊源统统可以追溯到 1900 年代初，但 1968 赛季放宽了赛车上赞助标识的规定，这项运动的商业面貌从此永远改变。

法拉利创始人恩佐·法拉利是个极其炽热的意大利人，他希望让赛车披上法规指定的国家颜色，以此彰显这份身份。从马拉内罗工厂走出的第一台机器——1947 年 5 月首秀的法拉利 125 S——就是竞赛红。

### 什么是 Rosso Corsa？

Rosso Corsa 是一种漂亮的红色调，车迷想象法拉利时往往会立刻想到它。本周末车队使用的正是这个色号，几乎带着一种复古的味道。

它的字面意思是'赛车红'。这种颜色的设计初衷是平涂、不加任何金属闪片，好让车看起来更快、让车身线条更加夺目。

不过，车队如今通常使用的是一个更亮一些的红色调，名为 'Rosso Scuderia'——它被创造出来，就是为了在电视画面里更跳、更显眼。

法拉利在 F1 里也用过更深的红色调，包括他们第 1000 场大奖赛的涂装：那一版拥抱了酒红色，向 1950 年摩纳哥大奖赛上法拉利赛车几近相同的颜色致意。

![法拉利将在意大利大奖赛上使用致敬迈克尔·舒马赫的涂装参赛。（原图注：Ferrari will race with a Michael Schumacher tribute livery at the Italian Grand Prix）](https://media.formula1.com/image/upload/t_16by9Centre/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Miscellaneous/ferrari-monza-livery-2026-4.webp)

图注：法拉利将在意大利大奖赛上使用致敬迈克尔·舒马赫的涂装参赛。（原图注：Ferrari will race with a Michael Schumacher tribute livery at the Italian Grand Prix）

### 法拉利有没有不红色参赛的时候？

这是个常见的问题，答案是：有。尽管法拉利近年给涂装点缀过别的亮色——比如 2022 年意大利大奖赛上的黄色、2024 年迈阿密大奖赛上的蓝色——但厂商车队最后一次整套赛车完全不带红色，还要追溯到 1964 年。

法拉利以蓝色参赛的时候

相传，1964 赛季的最后两场比赛，恩佐·法拉利下令给赛车喷上蓝白涂装以示抗议——原因是当时的管理机构拒绝让他为当年世界跑车锦标赛打造的新车通过认证。

失去标志性的招牌红色，在围场里掀起轩然大波。而这套蓝白的灵感来自北美赛车队——正是把法拉利引进美国市场的那个团队。

![1964 年，约翰·苏尔斯效力法拉利拿下 Formula 1 世界冠军，成为史上唯一一位两轮和四轮都夺过世界冠军的人。（原图注：1964 saw John Surtees clinch the Formula 1 title with Ferrari, becoming the only person to win world titles on two wheels and four）](https://media.formula1.com/image/upload/t_16by9South/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2233965042.webp)

图注：1964 年，约翰·苏尔斯效力法拉利拿下 Formula 1 世界冠军，成为史上唯一一位两轮和四轮都夺过世界冠军的人。（原图注：1964 saw John Surtees clinch the Formula 1 title with Ferrari, becoming the only person to win world titles on two wheels and four）

法拉利以黄色参赛的时候

私人报名的赛车也曾披过黄色，最出色的例子或许要数奥利维耶·让德比安在 1961 年斯帕-弗朗科尔尚比利时大奖赛上的那次。这位比利时车手驾驶着一台著名的'鲨鱼鼻'造型厂队法拉利 156，但那是一次私人参赛，车身用了黄色——比利时的国家赛车色。

让德比安最终第四名完赛，也帮助法拉利收获了一场历史性的 1-2-3-4 包揽——那是任何厂商在 F1 里最后一次做到这件事。

法拉利以绿色参赛的时候

最后，法拉利挂名的赛车还曾以英国赛车绿出赛——这要归功于 Vanwall——不过那从未出现在 F1 世界锦标赛的分站上。

这支车队此前曾带着改装过的法拉利参加 Formula Libre 赛事。虽然法拉利提供了大量关键部件，但赛车主要由 Vanwall 团队改装、组装。

![比利时人奥利维耶·让德比安在 1961 年斯帕-弗朗科尔尚比利时大奖赛上，驾驶一台披着比利时国家赛车色的黄色法拉利。（原图注：Belgian Olivier Gendebien drove a yellow Ferrari in Belgium's national racing colours in the 1961 Belgian Grand Prix at Spa-Francorchamps）](https://media.formula1.com/image/upload/t_16by9North/c_lfill,w_3392/q_auto/v1740000001/fom-website/2026/Lifestyle/ADHOC/GettyImages-2231597763.webp)

图注：比利时人奥利维耶·让德比安在 1961 年斯帕-弗朗科尔尚比利时大奖赛上，驾驶一台披着比利时国家赛车色的黄色法拉利。（原图注：Belgian Olivier Gendebien drove a yellow Ferrari in Belgium's national racing colours in the 1961 Belgian Grand Prix at Spa-Francorchamps）
