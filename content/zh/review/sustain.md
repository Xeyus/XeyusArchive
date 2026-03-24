---
title: sustain+++
date: 2024-08-13T00:44:47+08:00
tags: ["applied-arts/critique"]
series: [其他文艺作品评论]
---
## 基本情况

sustain++ 的 MV 左侧在代码注释中给出乐曲基本信息和歌词，模拟的 Java 代码本身“讲述故事”。

MV 的背景采用高饱和度配色和轻微像素化处理。

本曲为 Ghost In The Shell: SAC_2045 的 Ending Theme

我并未完整看过攻壳机动队（Ghost In The Shell）系列动画。以下所有解读不联系其内容及设定。

## 背景

整体有失真感。来源：高饱和度配色，像素化、不自然的光线变化，最前方半调风格的粉色薄雾，元素安排。

背景无限循环。

![PixPin_2024-08-13_01-13-38.png](https://s2.loli.net/2024/09/12/g5uk3QwpLCUhP4t.png)

![PixPin_2024-08-13_01-21-56.png](https://s2.loli.net/2024/09/12/gefLkwQP5THsVNC.png)

![PixPin_2024-08-13_01-22-25.png](https://s2.loli.net/2024/09/12/BkpPryoX6sctvaq.png)

1 图顶端是“Justice Kills Freedom”滚动灯牌的下半部分，与 3 图中段对应。

这里我们设 2 图顶部中心的笑脸灯牌为循环端点。

### 主体

画面主体部分的机械结构类似人体胸腔 - 盆骨的结构。

2 图中手臂位置、后方类似肋骨的线缆，可“证明”这一猜想。

大脑/肠子位于腹部。

机械主色调为蓝白，附有大量附属结构和红色灯。

附属结构包括：

1. 包含类似 DNA 双螺旋结构的黄色管道。两根被蛇缠绕的连接身体两侧的附属结构，一根充当脊椎。
2. 手臂两侧类似监控的设备
3. 手臂左上方的灯牌，根据后方直角向下的金属支架推测直接与机械本体相连。其上下均有“ARE YOU LIFE?”字样，中间为“烦”和一个表情。
4. 手臂右上方的灯牌，同样推测与本体相连。其左右均有“MELLO”字样，中间为滴血（粉红色液体）的像素小刀。
5. 胸腔下方、腹部两侧对称的机器人和它们上方的配电箱。
6. 机器人上方外红内白的圆形结构。
7. 腹部左侧的灯牌，为双手挤压笑脸 emoji 的动图。
8. 腹部下方的灯牌，循环滚动“Justice Kills Freedom”。
9. 盆骨两侧类似探照灯和喇叭的结构。
10. 探照灯左侧的灯牌。其展示一双眼睛。
11. 盆骨下方的笑脸 emoji 灯牌。
12. 笑脸灯牌上方类似王冠和塔楼的结构。

#### 肉质

集中在机械中段的一大一小两处肉质都有“剥离并展现”的意味，突出生物性。

#### 象征（按照附属结构 - 整体排序）

1. 高饱和且与整体配色相异的黄色相当吸睛，起强调作用：机械外壳内依然为生物。蛇应该有基督教方面的暗示，也起强调作用（并未真正通过某些行为获得，超越人性？）
2. 其他机械结构应该在强调“监视”和文本上的哲学问题。

### 前景

### 其他

## 歌词与代码

`package extraLarge`，创建包。应该是为了额外补充世界的内容。

注释：

```
/**
 * The goal of this program is to obtain a HEALTHY
 * and SUSTAINABLE relationship, darling.
 *
 * @author Cassie Wei from Mili
 */
```

> 这个程序的目的是发展一段**健康**且**可持续**的关系，亲爱的。
> 以及作者信息。看看创建该程序的人/我眼中这样的关系是什么样的。

代码：

`public class sustainPlusPlus`，十分正常的声明公共类和驼峰命名法。不能在类名中使用“+”，所以使用了“plus”。

```
public static void main(String[] args) {
        World world = new World();
        Life me = new Ghost();
        Life you = new Ghost();
```

定义了世界，赋予了你我两个 Ghost 生命。

```
       /**
         * If abstraction is the definition of beauty
         * Are those of us chasing after clarity
         * A representation of ugly?
         */
        world.getObject().sortByAttribute("beauty");
        if (world.getObject().getFirst().getArtTags().indexOf("abstract") != -1) {
            me.addPhysicalAttribute("ugly");
            you.addPhysicalAttribute("ugly");
        }
        world.giveBestAward("ugly", me);
        world.giveBestAward("ugly", you);
```

> indexOf() 用于查找字符串
> !=即为不等于
> =-1，则为“无”。这里指搜索的字符串在列表中不存在。
> =0，则为“空”。这里指该字符串位于首位。
> 其他整数代表位次。假设有一个字符串 str = "abstract art";str.indexOf("abstract") 将返回 0，因为 "abstract" 是字符串的第一个子字符串。str.indexOf("art") 将返回 9，因为 "art" 是从第 10 个字符开始的，索引从 0 开始计数。

代码为将包含“美”属性的对象排序，并检查处于第一位的对象是否有“抽象”标签。如果有，则为我和你添加物理属性“丑”。且“丑”是你我的最高奖励。

结合注释可得，你我的行为是不正确（程序的抽象即为美）却正当的。

```
 /**
         * CALL ME MOMMY
         * JUST LIKE YOUR FANTASY
         * There is no crime in ideality
         */
        if (you.getFetishes().searchByType("name calling", "mommy") != -1) {
            you.addToMemory(me);
            you.setNicknameFor(you.getMemory(me), "mommy");
        }
        Rule r = new Rule("Oedipus complex is okay", true);
        world.addRule(r);
```

理论上来讲，俄狄浦斯情结不必被特意“set rule”。但这里需要特别声明，说明对象不是“人类”（确实，之前声明了是“Ghost”），最开始不能直接套用精神分析的理论。

另一方面来看，“我”接受了“你”的俄狄浦斯情结，接受“你”将我认作母亲。因为代码是“你的癖好是称呼（▀▀▀为）母亲，你获取了关于我的记忆，于是称我为母亲。设置俄狄浦斯情结没有问题为世界的规则。”

```
        /**
         * CALL ME DADDY
         * WHERE'S YOUR "YES SIR" & "PLEASE"?
         * That's the only vocabulary you need
         */
        you.setNicknameFor(you.getMemory(me), "daddy");
        String[] vocab = {"sir", "yes", "no", "please", "thank you", "master",
            "red", "green", "yellow"};
        you.setVocabulary(vocab);
```

同一个格式的“Call me Daddy”处，色彩饱和度恢复正常。代码意为“你获得了我的记忆，你称我为父亲，你只能说 sir,yes,no,please,thank you,master,red,green,yellow。”

这两段的顺序和主体对自我认知的整合顺序相符。看来“你”的人格发展和这段关系一样，相当……HEALTHY and SUSTAINABLE 啊。

回到这段，这里的词都指向服从（敬语、红绿灯 - 规则）。这里的“no”偏向否定原先自我的对应关系，否定身体与以“我”的象征秩序为基础的自我的不和谐，让自己完全服从/归属于“我”。

> That's the only vocabulary you need

回到俄狄浦斯情结那段继续。

```
        /**
         * MUX>>>DEMUX
         * Can't you understand me?
         * I'm not mine NAND I'm not yours
         * Ah
         */
        try {
            you.decodeMessage(me.codeMessage("I'm not mine NAND I'm not yours.", "mux"), "mux");
        } catch(InsufficientIntelligenceQuotientException e) {
            world.sendMessage("Oh you dummy.", you);
            me.announce("Ah");
        }
```

编码>>>另一种算法解码 = 乱码，所以询问“Can't you understand me”。

> Java 异常处理：最具代表的检查性异常是用户错误或问题引起的异常，这些异常在编译时强制要求程序员处理。例如要打开一个不存在文件时，一个异常就发生了，这些异常在编译时不能被简单地忽略。
> 语法结构：try{
> 情况} catch(IOException e) {
> 解决方法
> }

代码部分：检查并处理异常：若检测到你解码了我已编码的消息（而且，当然是解码错误，没读出来 "I'm not mine NAND I'm not yours."），则对你说 "Oh you dummy.""Ah"

catch 后括号内的语句表明“我”认为“你”犯这个错误是因为智商不足。

"I'm not mine NAND I'm not yours." 两个输入/输出 + 与非门让这句话没有了 clairity 的标签。

> 与非门：输入有一为真，则不输出。
> 所以这句话压根没说明白，“我”还说“你”没看懂是因为智商低下。这里就能看出“我”不想面对这个自我归属的问题，以及“我”和“你”的这段关系……相当的“健康”啊。

```
        /**
         * This could end right here if you don't let it out
         * Let it out
         */
        if (you.getThoughts().size() != 0) {
            try {
                you.sayTo(you.getThoughts(), me);
                you.clearThoughts();
            } catch(TooMuchOfAPussyException e) {
                world.getRelationship(me, you).end();
            }
        }
```

代码部分是，检测“你”的思想是否为空，若否，则处理检查性异常：你向我传达思想，你清除了自己的想法，捕获到“这对一只小猫来说太多了”异常，结束你我的关系。

挺“健康”的。没的说。

```
        /**
         * Give up or give me your all
         * tell me now
         * tell me now
         */
        if (you.getMemories(me).getLove() < 0.5) {
            world.getRelationship(me, you).setSustain(0);
        } else {
            you.transferThoughs(me);
            you.transferAttributes(me);
  
            // sustain++;
            world.getRelationship(me, you).increaseSustain();
        }
```

代码本意是根据“你”对“我”的爱来决定是削弱还是增强两者之间的关系。爱低于 0.5 时，关系的可持续性清零；高于或等于 0.5 时，分享思想和属性，并增加关系的可持续性。但 sustain++，也就是增加可持续性的代码被注释掉了，不起作用。

```
        /**
          * If we can be completely simulated
          * Do we need a real reality?
         */
        Simulation s = new Simulation(me, world, 1993, 227760);
        if (s.compareToOriginal(me) == 100) {
            world.execute(me);
        }

```

> 彩蛋：1993 是主唱兼作词，cassie wei 的出生年份。

设置新的模拟，如果和原本的我完全相同，则——world.execute(me);!（另一首歌的名字）

```
        /**
         * Don't let words die, let love run dry
         * Like what we did to the rivers we killed off in our near future
         * Ah
         */
        for (int sustain = 0; sustain < world.getRiver().size(); sustain++) {
            me.sayTo("I love you.", you);
            you.sayTo("I love you.", me);
        }
```

如果可持续性为 0，且可持续性小于河流的大小，可持续性增长，那么我和你互相说“我爱你”。解释了“注释”的逻辑。

```
        /**
         * And mumble some stupid stuff
         * Like
         * "I saw it coming"
         * Pretend it's not happening
         * Us losers do nothing so winners keep winning
         */
        String[] tags = {"stupid", "dump", "petty", "ignorant"};
        world.mute(me, tags);
        world.mute(you, tags);
        for (Life them : world.getLifeTopOnePercent()) {
            me.fight(them);
            you.fight(them);
        }
```

为什么会如此？因为世界用“愚蠢”之类的标签让我们噤声。我们和生活在最顶端的人战斗。

```
   /**
         * Sit
         * Fetch your leash
         * DICTATED ECONOMY
         */
        me.command(you, "sit");
        me.command(you, "fetch");
        you.pay(me, you.getFinanceProperties(), "educational purposes");



        /**
         * Show me
         * Your belly
         * FORGOTTEN ECOLOGY
         */
        me.command(you, "strip");
        me.command(you, "exhibit");
        world.addPollution("environmental", "indecency", you);



        /**
         * Stay
         * Okay, eat
         * Human PSYCHOLOGY
         */
        me.command(you, "stay");
        me.command(you, "eat");
        you.love(me);



        /**
         * g 0 0 d   b o i
         * Here's a treat
         * HUNGRY FOR ENERGY
         */
        me.praise(you, "Good boy.");
        me.gift(you, "meat");
        you.consumeLast();
```

我命令你坐下、取东西，你付给我财产，用于教育目的。我命令你脱衣、展示，你被世界定义为一种环境污染，流氓。我命令你停下、吃东西，你爱我。我夸赞你，给你肉作为奖励，你的消费还在继续。

训狗、控制财产、消费确实能达成“健康而可持续”的关系。

```
  /**
         * We are searching
         * Following our human instincts
         * Looking for ghosts of the non-existing kind
         * Who make us whole from the very beginning
         */
        Ghost[] findings = world.search(me, "ghost");
        Ghost[] parents = new Ghost[2];
        for (Ghost g : findings) {
            me.addFamily(g);
            if (me.isHappy()) {
                if (parents[0] == null) {
                    parents[0] = g;
                }
                else if (parents[1] == null) {
                    parents[1] = g;
                }
                else {
                    //IGNORED because 'me' is never happy
                    //and will never be happy anyway
                }
            }
            me.removeFamily(g);
        }
```

如果我是开心的，却没有父母，则添加父母；若……不，前提不成立，因为“我”不会开心。所以这段以从家庭中移除父母结束。

```
   /**
         * We keep chasing
         * Dreaming about the perfect being
         * Perfect parents who are non-existing
         * Our bodies grew, our minds stayed the same
         */
        if (me.getDreamParents().equals(parents)) {
            me.setParents(parents);
        }
        else {
            me.throwTantrum();
        }
```

如果找到了梦想中的父母，则让他们成为自己的父母，否则感到不满。

```
        /**
         * Now darling, where do we go from here?
         */
        me.ask(you, "Where do we go from here?");



        /**
         * Now darling, where do we go from here?
         */
        me.ask(you, "Where do we go from here?");



        /**
         * Now darling, where do we go from here?
         */
        me.ask(you, "Where do we go from here?");



        /**
         * Darling, darling
         */
        me.callFor(you);
        me.callFor(you);

```

“我”询问“你”。

```
        /**
         * Hey honey, where do we go from here?
         */
        you.ask(me, "Where do we go from here?");



        /**
         * Hey honey, where do we go from here?
         */
        you.ask(me, "Where do we go from here?");
```

“你”询问“我”。

```
   /**
         * Now darling, where do we go from here?
         */
        me.ask(you, "Where do we go from here?");



        /**
         * Now darling, where do we go from here?
         */
        me.ask(you, "Where do we go from here?");
```

“我”询问“你”。

```
    /**
         * To where?
         */
        me.ask(world, "To where?");
```

“我”询问世界，该前往何方。

下一段已经解释过了，跳过。

```
        /**
         * MUX>>>DEMUX
         * Can't you understand me?
         * You turn my screen #0000ff
         */
        you.disorient(me);
```

“你”依然无法理解“我”，但这次你让我感到疑惑（所以蓝屏了）。

```
        /**
         * We could end right here if you'd just let us fall
         * Let us fall
         */
        for (War w : you.getOngoingFights()) {
            if (w.getScore(you) < 0.5) {
                world.execute(me);
                world.execute(you);
            }
        }
```

如果你在斗争中的得分小于 0.5（堕落了），你我会被世界执行死刑（关系自然也结束了）。

```
   /**
         * No tears, no regrets
         * No zero-days at our fault
         */
        me.setMemory("sad", null);
        you.setMemory("sad", null);
        me.setMemory("regretful", null);
        you.setMemory("regretful", null);
        Vulnerability zeroDays = world.getVulnerabilities().getZeroDays();
        for (Vulnerability v : zeroDays) {
            v.setAuthors(null);
        }
```

删除了悲伤和悔恨的记忆，如果有零日漏洞，则删除作者。

```
        /**
         * Hear me out
         * It's a perfect plan
         */
        me.command(you, "listen");
        me.sayTo("Anything inconvenient, I shall erase for you.", you);
```

“听着。我会为你抹除一切不方便的事物。”

```
/**
         * If you'd just
         * Shut up
         * Shut up
         * Then maybe you'll see what I've endured now
         */
        me.command(you, "be quite");
        me.command(you, "be quite");
        try {
            you.listenTelepathically(me, world);
        } catch (NotAMindReaderException e) {
            world.getRelationship(me, you).challenge();
        }
```

但“你”没有听。我命令你安静。因为如果你能通过“心灵感应”听到我的话，但你不能读心，那么，我们的关系会受到挑战（你欺骗了我、不关心我）。

```
/**
         * Hear me out
         * LILULILALULALULA
         */
        me.command(you, "listen");
        me.sayTo("I did it all for you.", you);
        you.ignoreCommands();
        you.setMessages(null);
```

我命令你听着，我说“我为了你做了这一切”。你没有听我的命令，删除了我的话。

这段关系已经受到挑战。

“你”终于进入了俄狄浦斯情结的下一阶段。

```
/**
         * It's all just sunk cost, I know
         * But I'm not ready to stop
         */
        me.manipulate(you, "beg");
        me.manipulate(you, "gaslight");
        me.manipulate(you, "blame");
        me.manipulate(you, "tears");
        world.getRelationship(me, you).end();
        you.setMemory(me, null);
```

看看这四个词。真是健康的手段啊。乞求，煤气灯，斥责，眼泪。

我们的关系终止。

你删除了关于我的记忆。

```
/**
         * I don't want to stop
         */
        me.getMemory(you, "positive");
        me.getMemory(you, "date");
        me.getMemory(you, "fun");
        me.getMemory(you, "travel");
        me.getMemory(you, "wedding");
        me.getMemory(you, "pregnancy");
        me.getMemory(you, "kids");
        me.getMemory(you, "snuggle");
        me.getMemory(you, "netflix&chill");
        me.getMemory(you, "gaming");
        me.getMemory(you, "birthday");
        me.getMemory(you, "cooking");
        me.getMemory(you, "exercising");
        me.getMemory(you, "studying");
        me.getMemory(you, "gardening");
        me.getMemory(you, "chores");
        me.getMemory(you, "shopping");
        me.getMemory(you, "driving");
        me.getMemory(you, "daily");
        me.getMemory(you, "sad");
        me.getMemory(you, "angry");
        me.getMemory(you, "fight");
        me.getMemory(you, "forgiveness");
        me.getMemory(you, "makeup");
        me.getMemory(you);
        world.setRelationship(me, you, null);
      
        //    a
        // u
        //     i
        //  s
        //         ;
        //     i
        //   t
        //  s      ;
        //    a n +
        //  s    +
        //s  t
        //  s a  +
        // u   in +
        //s        ;
        //   ta n+
        //       ++
        // u t  n +
        //s    in
        //   t  n+ ;
        //  s a
        //s  t i  +
        // u   i + ;
        //s   a n +
        //  s    + ;
        // u t i +
        //s st i  +
        // us a n +;
        //  s ain+
        //su  ai  +;
        //s  tain  ;
        // ust  n +
        //s stai + ;
        //su t in +;
        // ustain++
        //sustain++;
        //sustain++;
        //sustain++;
        //sustain++;
        //sustain++;
        //sustain++;
        //sustain++;
    }
}
```

我回忆你我相处的经历。但我们的关系还是破裂了。

所以最后，sustain++ 仍只存在于注释中。

参考：https://www.reddit.com/r/mili/comments/sjhn5o/code_analysis_sustain/
