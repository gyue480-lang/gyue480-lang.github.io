This is a humorous personality test website
Let's have a test
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
    <title>underti · 地下室人格测试</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: #f4ede4;
            font-family: system-ui, -apple-system, 'Segoe UI', 'PingFang SC', Roboto, 'Helvetica Neue', sans-serif;
            padding: 1.5rem 1rem;
            color: #2c241a;
        }
        .test-card {
            max-width: 900px;
            margin: 0 auto;
            background: #fffef7;
            border-radius: 2rem;
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.15);
            overflow: hidden;
        }
        .header {
            background: #2b2b2b;
            color: #f5e7d9;
            padding: 1.8rem 1.8rem 1.2rem;
            text-align: center;
        }
        .header h1 {
            font-size: 1.9rem;
            font-weight: 700;
            letter-spacing: -0.5px;
        }
        .header p {
            margin-top: 0.5rem;
            opacity: 0.75;
            font-size: 0.9rem;
        }
        .progress-area {
            background: #f2ebe1;
            padding: 0.7rem 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 0.8rem;
            font-size: 0.85rem;
            font-weight: 500;
            border-bottom: 1px solid #e2d5c8;
        }
        .progress-bar {
            flex: 1;
            height: 7px;
            background: #d9cdbc;
            border-radius: 10px;
            overflow: hidden;
        }
        .progress-fill {
            width: 0%;
            height: 100%;
            background: #8b5a2b;
            transition: width 0.2s ease;
        }
        .question-item {
            background: #ffffff;
            margin: 1.2rem 1.5rem;
            padding: 1.2rem 1.2rem;
            border-radius: 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.03), 0 1px 2px rgba(0, 0, 0, 0.05);
            border: 1px solid #f0e4d8;
        }
        .q-text {
            font-weight: 600;
            font-size: 1rem;
            line-height: 1.4;
            margin-bottom: 1rem;
            padding-left: 0.2rem;
        }
        .options {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }
        .opt-label {
            flex: 1;
            background: #faf7f2;
            border-radius: 1.2rem;
            padding: 0.7rem 0.9rem;
            display: flex;
            align-items: center;
            gap: 0.6rem;
            cursor: pointer;
            border: 1px solid #e7dfd5;
            transition: 0.1s;
        }
        .opt-label:hover {
            background: #f3ede5;
            border-color: #c9b99f;
        }
        input[type="radio"] {
            accent-color: #8b5a2b;
            width: 1.1rem;
            height: 1.1rem;
            flex-shrink: 0;
            cursor: pointer;
        }
        .opt-text {
            font-size: 0.9rem;
            line-height: 1.35;
        }
        .actions {
            display: flex;
            gap: 1rem;
            justify-content: center;
            padding: 0.8rem 1.5rem 2rem;
            flex-wrap: wrap;
        }
        button {
            border: none;
            background: #2b2b2b;
            color: white;
            font-weight: 600;
            padding: 0.7rem 1.6rem;
            border-radius: 2rem;
            font-size: 0.9rem;
            cursor: pointer;
            transition: 0.15s;
            font-family: inherit;
        }
        button.btn-primary {
            background: #a66b38;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
        }
        button.btn-primary:hover {
            background: #8b562b;
            transform: translateY(-2px);
        }
        button.btn-secondary {
            background: #bcab95;
        }
        button.btn-secondary:hover {
            background: #a69078;
        }
        .result-box {
            background: #fef8f0;
            margin: 0 1.5rem 1.8rem;
            border-radius: 1.5rem;
            padding: 1.5rem;
            border-left: 6px solid #a66b38;
        }
        .character-images {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
        }
        .img-card {
            text-align: center;
            width: 140px;
        }
        .img-card img {
            width: 100%;
            height: auto;
            max-height: 140px;
            object-fit: contain;
            background: #f0e4d8;
            border-radius: 12px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
            transition: transform 0.2s;
        }
        .img-card img:hover {
            transform: scale(1.02);
        }
        .img-card .label {
            font-size: 0.8rem;
            margin-top: 0.5rem;
            color: #5a3e28;
            font-weight: 500;
        }
        .art-name {
            text-align: center;
            font-size: 2.4rem;
            font-weight: 800;
            letter-spacing: 2px;
            background: linear-gradient(135deg, #a66b38, #6b3e1a);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.05);
            margin: 0.5rem 0 1rem 0;
        }
        .art-name span {
            font-size: 2rem;
        }
        .quote-left, .quote-right {
            font-size: 3rem;
            color: #c9b99f;
            font-family: serif;
            vertical-align: middle;
        }
        .result-title {
            font-size: 1.2rem;
            font-weight: 700;
            margin: 1rem 0 0.5rem;
            text-align: center;
            color: #5a3e28;
        }
        .result-desc {
            font-size: 0.95rem;
            line-height: 1.55;
            color: #2c241a;
            margin-top: 1rem;
            border-top: 1px dashed #e2d5c8;
            padding-top: 1rem;
        }
        .analysis-section {
            background: #faf3e8;
            border-radius: 1rem;
            padding: 0.8rem 1rem;
            margin: 0.8rem 0;
            font-size: 0.9rem;
        }
        .footer {
            font-size: 0.7rem;
            text-align: center;
            padding: 1rem;
            color: #ad9a82;
            border-top: 1px solid #f0e2d4;
        }
        @media (max-width: 550px) {
            .question-item { margin: 1rem; }
            .opt-label { flex: 100%; }
            .art-name { font-size: 1.8rem; }
            .quote-left, .quote-right { font-size: 2rem; }
            .img-card { width: 110px; }
        }
    </style>
</head>
<body>
<div class="test-card">
    <div class="header">
        <h1>测测你的地下室人格</h1>
        <p>大学生限定 · 你的体面人设 vs 地下室真我</p>
    </div>
    <div class="progress-area">
        <span>答题进度</span>
        <div class="progress-bar"><div class="progress-fill" id="progressFill"></div></div>
        <span id="counter">0 / 18</span>
    </div>
    <div id="questionsContainer"></div>
    <div class="actions">
        <button class="btn-primary" id="submitBtn">揭穿双重身份</button>
        <button class="btn-secondary" id="resetBtn">重新开局</button>
    </div>
    <div id="resultArea" class="result-box" style="display: none;"></div>
    <div class="footer">每个问题凭直觉选 · 无对错 · 你的暗面正在偷看</div>
</div>

<script>
    // ---------- 题目库 ----------
    const QUESTIONS = [
        { text: "期末周你在图书馆占了个座，去接个水回来发现有人坐在你的位置上，还把你的水杯挪到一边。你会？", left: "礼貌但坚定地说“同学这是我的位置”", right: "算了，反正还有其他空位，不浪费时间" },
        { text: "你的室友在宿舍群里发了一段偷拍的别人出糗的视频，大家笑得很开心。你会？", left: "觉得不太合适，会私聊室友让他删掉", right: "跟着哈哈哈，反正也不是我出糗" },
        { text: "小组作业有人划水，最后你们组分数不高。你会？", left: "下次分组会明确拒绝再和划水的人一组", right: "心里不爽，但嘴上不说，下次再悄悄避开" },
        { text: "你发了一条朋友圈，半小时没人点赞评论。你会？", left: "心里咯噔一下，怀疑是不是内容太无聊了", right: "没注意到，忙着刷短视频呢" },
        { text: "室友晚上叹气了一声，你会？", left: "心里琢磨ta怎么了，但不会直接问", right: "不太在意，等室友主动提及再说" },
        { text: "上课时你听到后排同学在小声说笑，偶尔还提到你的名字。你会？", left: "忍不住想他们是不是在议论我什么", right: "大概率在聊别的，懒得管" },
        { text: "回顾这学期，你的整体感受是？", left: "还行，有几件开心的事", right: "挺累的，倒霉事一桩接一桩" },
        { text: "看到别人保研/拿奖/脱单，你通常？", left: "替ta高兴，顺便激励自己", right: "有点酸，压制不住比较心" },
        { text: "你觉得自己大学生活的底色是？", left: "虽然有小烦恼，但总体挺快乐的", right: "总有哪里不太对劲，说不上来" },
        { text: "你翻到自己以前QQ空间里的中二发言，现在看的感觉是？", left: "想死，但留着嘲笑自己", right: "早就锁起来了，那不是真正的我" },
        { text: "如果有一个功能强迫你看自己过去所有蠢话记录，你会？", left: "痛苦但看完，也许能长记性", right: "坚决不看，过去的就过去" },
        { text: "你跟室友因为小事闹别扭，冷静下来后你会怎么想？", left: "我可能也有责任", right: "如果不是对方先那样，不会闹到这一步" },
        { text: "假如这个学期突然取消所有考试和截止日期，全部改成“自行安排”，你最可能的状态是？", left: "爽了几天，然后开始焦虑该从哪开始", right: "立刻给自己列个表，不然心里发慌" },
        { text: "你更同意哪种说法？", left: "学校的很多规矩就是折腾人的，只是没人敢反抗", right: "规矩虽然烦，但没有的话会更乱" },
        { text: "你更习惯哪种小组作业分工？", left: "大家各自认领，灵活调整，最后再拼起来", right: "一开始就明确每个人做什么，按表执行" },
        { text: "早上八点有课，但昨晚熬夜了，你会？", left: "纠结要不要翘课，想半天最后还是决定去（或没去但内疚）", right: "直接关闹钟继续睡，不纠结" },
        { text: "你觉得自己是“心里什么都懂，但行动上就是摆烂”的人吗？", left: "哦？", right: "嗯" },
        { text: "你曾经为了逃避写论文而花了三小时整理桌面/刷短视频/研究奇怪的知识吗？", left: "经常，逃避可耻但有用", right: "不太会，我一般会先做完再玩" }
    ];

    // 维度映射（左高右低）
    const DIM_MAP = [
        { dim: "justice", high: "J", low: "E" }, { dim: "justice", high: "J", low: "E" }, { dim: "justice", high: "J", low: "E" },
        { dim: "sensitivity", high: "S", low: "D" }, { dim: "sensitivity", high: "S", low: "D" }, { dim: "sensitivity", high: "S", low: "D" },
        { dim: "happiness", high: "H", low: "U" }, { dim: "happiness", high: "H", low: "U" }, { dim: "happiness", high: "H", low: "U" },
        { dim: "reality", high: "R", low: "P" }, { dim: "reality", high: "R", low: "P" }, { dim: "reality", high: "R", low: "P" },
        { dim: "freedom", high: "F", low: "T" }, { dim: "freedom", high: "F", low: "T" }, { dim: "freedom", high: "F", low: "T" },
        { dim: "think", high: "L", low: "I" }, { dim: "think", high: "L", low: "I" }, { dim: "think", high: "L", low: "I" }
    ];

    const LIGHT_NAMES = {
        "JSH": "持圣光者", "JSU": "悲悯法官", "JDH": "干脆好人", "JDU": "守矩行者",
        "ESH": "随心市民", "ESU": "清醒流民", "EDH": "大务实家", "EDU": "现实中人"
    };
    const DARK_NAMES = {
        "RFL": "暗处判官", "RFI": "躁动演员", "RTL": "清醒囚徒", "RTI": "木偶哲人",
        "PFL": "做梦逃兵", "PFI": "快乐傻子", "PTL": "大资本家", "PTI": "空心化石"
    };

    // ======================== 图片绝对路径（GitHub Pages） ========================
    // 基础 URL：你的 GitHub Pages 根目录下的 underti 文件夹
    const BASE_URL = "https://gyue480-lang.github.io/underti/";
    
    const LIGHT_IMAGES = {
        "持圣光者": BASE_URL + "持圣光者.jpg",
        "悲悯法官": BASE_URL + "悲悯法官.jpg",
        "干脆好人": BASE_URL + "干脆好人.jpg",
        "守矩行者": BASE_URL + "守矩行者.jpg",
        "随心市民": BASE_URL + "随心市民.jpg",
        "清醒流民": BASE_URL + "清醒流民.jpg",
        "大务实家": BASE_URL + "大务实家.jpg",
        "现实中人": BASE_URL + "现实中人.jpg"
    };
    const DARK_IMAGES = {
        "暗处判官": BASE_URL + "暗处判官.jpg",
        "躁动演员": BASE_URL + "躁动演员.jpg",
        "清醒囚徒": BASE_URL + "清醒囚徒.jpg",
        "木偶哲人": BASE_URL + "木偶哲人.jpg",
        "做梦逃兵": BASE_URL + "做梦逃兵.jpg",
        "快乐傻子": BASE_URL + "快乐傻子.jpg",
        "大资本家": BASE_URL + "大资本家.jpg",
        "空心化石": BASE_URL + "空心化石.jpg"
    };
    // ========================================================================

    // 光明形象独立分析
    const LIGHT_ANALYSIS = {
        "持圣光者": "你觉得自己是个讲原则、懂人心、还活得挺开心的人。正义感是你的旗帜，敏感是你的雷达，乐观是你的底色。你相信世界会因为你的存在而稍微亮一点。即使偶尔被人说“圣母”，你也觉得那是夸奖。",
        "悲悯法官": "你认为自己是个道德感强但从不盲目的清醒者。你看到了世界的苦难，也承受着比别人更多的情绪重量。你痛苦，但你觉得这种痛苦让你更深刻、更高级。你是个好人，只是不太快乐。",
        "干脆好人": "你自认为干脆利落、不拖泥带水。你讲原则，也讲效率；你善良，但绝不内耗。你觉得那些纠结来纠结去的人太蠢了。你活得清爽，是个让人羡慕的“好人模板”。",
        "守矩行者": "你觉得自己是个规则守护者，不惹事也不怕事。你讲道理，抓重点，只是偶尔觉得世界太吵。你不追求快乐，只追求正确。别人觉得你冷，你觉得那是清醒。",
        "随心市民": "你觉得自己随性、不较真、天生乐观。你不爱管闲事，也不喜欢被规则束缚。你觉得人生苦短，何必给自己加戏。你是个温暖但不粘人的存在，大家都觉得你好相处。",
        "清醒流民": "你觉得自己是个现实主义者，不骗自己，也不骗别人。你敏感但不矫情，你痛苦但不说。你看透了生活的本质，然后选择继续混着。你不算快乐，但你觉得自己很酷。",
        "大务实家": "你觉得自己是个彻底的务实派。不争对错，只争利益；不谈感情，只谈结果。你快乐，因为你要求低。你觉得自己比那些理想主义者聪明多了。",
        "现实中人": "你觉得自己是个冷酷的理性人。不内耗，不期待，不抱怨。你只看事实，只做计算。你不快乐，但你觉得快乐是蠢人的专利。你活着，仅此而已。"
    };

    // 阴暗形象独立分析
    const DARK_ANALYSIS = {
        "暗处判官": "你比你以为的更敢面对自己的不堪。你不怕脏，不怕丑，甚至有点享受挖开伤疤的快感。但你从来不说，只是偷偷在暗处审判自己，也审判别人。你的地下室坐着一个沉默的法官，手起刀落，从不留情。",
        "躁动演员": "你渴望自由，也渴望被看见。但你又懒又怂，只敢在幻想里演一出叛逆大戏。你表面上无所谓，背地里却把每一句台词都排练了八百遍。你的地下室是个空荡荡的舞台，你一个人，对着空气疯狂谢幕。",
        "清醒囚徒": "你画地为牢，把自己锁得死死的。但你什么都看得清——你知道笼子没上锁，你也知道钥匙就在脚边。你就是不出去。你的地下室是个透明的监狱，你坐在里面，和每一个路过的人说：“我自愿的。”",
        "木偶哲人": "你不敢动，也不想动。你以为自己在思考人生，其实只是在发呆。你觉得自由太重背不动，真相太烫拿不了。你的地下室是一堆生锈的齿轮，偶尔转一下，发出咯吱咯吱的响声，像是在叹气。",
        "做梦逃兵": "你把自己美化成一个怀才不遇的流浪诗人。你幻想着自由，幻想着反抗，幻想着有一天突然爆发。但你从来没有迈出过一步。你的地下室堆满了未拆封的梦想，落灰了，你也不看一眼。",
        "快乐傻子": "你自欺欺人，并且乐在其中。你不愿意面对任何不舒服的事情，你把自己的脑袋埋进沙子里，然后告诉自己“外面天气真好”。你的地下室是个欢乐的疯人院，你当院长，也当唯一的病人。",
        "大资本家": "你精于算计，善于找借口。你嘴上讲规矩，心里全盘算的是“我能得到什么”。你把自己包装成理性的守护者，其实只是贪婪又胆小。你的地下室是一座冷库，里面挂满了你标好价签的道德。",
        "空心化石": "你画地为牢，放弃思考，安静地腐烂。你以为自己很安全，其实只是死得比较慢。你不挣扎，不抱怨，甚至不觉得自己有问题。你的地下室是一块化石，曾经有心跳，现在只剩形状。"
    };

    // 64个组合专有分析（完整版）
    const COMBO_ANALYSIS = {
        "持圣光者_暗处判官": "你的道德感是用来照别人的，照自己的时候就调成柔光。你审判全世界，唯独给自己留了后门。虚伪的最高境界是自己都信了。",
        "持圣光者_躁动演员": "你想当圣人又舍不得凡人的快活，于是发明了“内心挣扎”这个人设。你的挣扎只是表演，因为你从没真的选过。",
        "持圣光者_清醒囚徒": "你的原则不是信仰，是借口——用“我有底线”来掩饰“我不敢越界”。你知道笼子没锁，但出去就要自己走路，算了。",
        "持圣光者_木偶哲人": "你伸张正义的样子像在背台词，因为那根本不是你的想法，是你妈、老师、社会塞给你的。你连讨厌什么都分不清是自己的还是别人的。",
        "持圣光者_做梦逃兵": "你幻想自己是大英雄，但真有人需要你时，你比谁跑得都快。你的正义感只存在于朋友圈转发里。",
        "持圣光者_快乐傻子": "你把自己活成了一张道德海报，海报后面是空的。你不敢照镜子，怕看见里面那个自私又冷漠的东西。",
        "持圣光者_大资本家": "你做每一件好事都要折算成“福报”，然后等着利息。你不是善良，你是放高利贷的，只是债主是老天爷。",
        "持圣光者_空心化石": "你的圣光早就灭了，只剩一层薄薄的荧光粉。别人夸你善良的时候，你心里在笑：他们真好骗。",
        "悲悯法官_暗处判官": "你同情弱者，但更同情自己——因为你是最惨的受害者。你把自己的痛苦当成勋章，挂在胸前给每个人看。",
        "悲悯法官_躁动演员": "你的悲伤是精心编排的舞台剧。你哭的时候还会偷看观众的反应，眼泪流得恰到好处。奥斯卡欠你一座奖杯。",
        "悲悯法官_清醒囚徒": "你什么都看透了，看透了就不动了。你的“清醒”只是懒惰的美化版，像一头躺平的猪说“猪圈外面也是泥”。",
        "悲悯法官_木偶哲人": "你思考人生的时间够别人读完三个学位，但你唯一的结论是“算了”。你的哲学就是高级拖延术。",
        "悲悯法官_做梦逃兵": "你痛恨这个世界的不公，但你从不改变任何事，因为改变会弄脏你的手。你的悲悯是远程遥控的，不用付电费。",
        "悲悯法官_快乐傻子": "你觉得自己是悲剧主角，其实你连配角都算不上。你的痛苦和你这个人一样平庸，不值得被写成诗。",
        "悲悯法官_大资本家": "你的同情心是按需生产的，就像你只在打折时才会爱别人。你帮助别人是因为那让你觉得自己比他们高级。",
        "悲悯法官_空心化石": "你说你痛苦，但你已经麻木到分不清疼和不疼。你的悲悯是化石上的花纹，看着像，一摸是石头。",
        "干脆好人_暗处判官": "你做事快，是因为你根本不在乎。你的“好人”是流水线产品，快速出厂，从不质检。谁得到都一样。",
        "干脆好人_躁动演员": "你雷厉风行的样子像极了广告里的成功人士——全是演的。你心里慌得要死，只是不敢让别人看出来。",
        "干脆好人_清醒囚徒": "你的效率是笼子里的跑步机，跑得再快也在原地。你不敢停下来，因为停下来就会发现自己哪也去不了。",
        "干脆好人_木偶哲人": "你从不纠结，因为你从不思考。你的“干脆”就是放弃思考的快捷键，按一下，问题消失——在你脑子里。",
        "干脆好人_做梦逃兵": "你帮别人忙时总是很爽快，因为那都是些不痛不痒的小事。真正需要你两肋插刀的时候，你的刀总是刚送去保养。",
        "干脆好人_快乐傻子": "你的快乐来自你的钝感。你感受不到别人的痛苦，也感受不到自己的。你是一块行走的麻木，还觉得自己很酷。",
        "干脆好人_大资本家": "你的每一次“好”都在心里记了账。你以为别人不知道，但你的眼神已经出卖了你，那里面写着“你欠我的”。",
        "干脆好人_空心化石": "你的好没有温度，像自动售货机的找零。你给出去的时候从不心疼，因为你根本没什么可给的。",
        "守矩行者_暗处判官": "你守规矩，然后用规矩当鞭子抽别人。你是规则的走狗，还是那种主动把项圈递给主人的。",
        "守矩行者_躁动演员": "你表面上是最乖的绵羊，心里却养着一头狼——但那头狼是纸糊的。你的叛逆只存在于深夜的幻想里，天亮就怂。",
        "守矩行者_清醒囚徒": "你知道规则是狗屎，但你不敢踩出去。你宁愿闻狗屎也不愿呼吸新鲜空气，因为新鲜空气没有路标。",
        "守矩行者_木偶哲人": "你的规则是别人写的，你只是照着念。你觉得自己在守护秩序，其实你只是一台复读机，还是盗版的。",
        "守矩行者_做梦逃兵": "你梦想一个没有规则的世界，但你不敢去。你怕在那样的世界里，你连怎么站都不知道。",
        "守矩行者_快乐傻子": "你遵守规则，然后嘲笑那些不遵守的人。你的优越感来自你脖子上的项圈——你觉得那是领带。",
        "守矩行者_大资本家": "你维护规则，因为规则让你占便宜。你是最忠心的看门狗，因为主人给的骨头最大。",
        "守矩行者_空心化石": "你的规矩已经长进肉里了，变成你的脊椎。你不是守矩，你就是规矩——一具行走的条文，没有骨髓。",
        "随心市民_暗处判官": "你说“随便”，是因为你懒得争，不是因为你宽容。你心里早就给每个人打了分，只是不公布成绩单。",
        "随心市民_躁动演员": "你的随性是表演给朋友圈看的。你连发呆都要摆出好看的姿势，真松弛是什么样，你早就忘了。",
        "随心市民_清醒囚徒": "你觉得你很自由，因为你每天都在换外卖。你的活动半径不超过宿舍楼，你的“随心”是笼子里的踱步。",
        "随心市民_木偶哲人": "你的“无所谓”不是豁达，是放弃。你懒得选择，就把选择权扔给别人，然后安慰自己说“我随性”。",
        "随心市民_做梦逃兵": "你幻想一场说走就走的旅行，然后打开手机继续刷。你的随性就是“想想就好”，反正不用花钱。",
        "随心市民_快乐傻子": "你快乐是因为你不敏感。你不觉得疼，不觉得脏，不觉得丢人。你的快乐和猪的快乐是同一个配方。",
        "随心市民_大资本家": "你的“随心”只对便宜的东西大方。真遇到需要你付出代价的事，你算得比谁都精。你的随性是穷大方。",
        "随心市民_空心化石": "你没有想要的东西，因为你没有心。你的随性不是选择，是空壳的默认状态。",
        "清醒流民_暗处判官": "你看透了一切，所以你什么都不做。你的清醒是最高级的懒惰——用“看透了”当借口，躺得理直气壮。",
        "清醒流民_躁动演员": "你把自己演成一个忧郁的诗人，但你连一首诗都写不出来。你的痛苦是二手的，从网上抄来的。",
        "清醒流民_清醒囚徒": "你知道笼子是敞开的，你也知道外面是什么样。你不出去，因为你怕外面比笼子里还差。你的清醒是胆小鬼的遮羞布。",
        "清醒流民_木偶哲人": "你思考人生的意义，结论是“没意义”。然后你就满意了——你的思考只是为了让自己不用行动。",
        "清醒流民_做梦逃兵": "你梦想一个理想世界，但你从不参与建设。你的清醒是站着说话不腰疼，而且是站在很远的地方说。",
        "清醒流民_快乐傻子": "你觉得自己很酷，因为你痛苦。但你的痛苦和别人的快乐一样廉价，只是你给它贴了个“深刻”的标签。",
        "清醒流民_大资本家": "你出卖你的“清醒”换取优越感。你觉得别人都是傻子，只有你懂。但你懂的东西一文不值，因为你不用。",
        "清醒流民_空心化石": "你的清醒没有内容，就像空房间里的回音。你喊一声，听到的只有自己的空洞。",
        "大务实家_暗处判官": "你只讲利益，但你偷偷嫉妒那些不讲利益的人。你鄙视理想主义，但你在深夜会问自己：我是不是活得太像一台机器？",
        "大务实家_躁动演员": "你演一个冷酷的理性人，演得太像，把自己都骗了。但你的梦出卖了你——你梦见自己在大喊“我想要”。",
        "大务实家_清醒囚徒": "你的务实是你的笼子。你不敢做梦，因为梦醒了会更疼。你把所有可能都算死了，然后死在计算器上。",
        "大务实家_木偶哲人": "你从来不问“为什么”，只问“多少钱”。你的务实是放弃思考的高级形式，因为你连想都嫌累。",
        "大务实家_做梦逃兵": "你梦想一夜暴富，然后就可以不务实了。你的务实是穷人的务实，不是选择，是没得选。",
        "大务实家_快乐傻子": "你的快乐来自你要求低。你不痛苦，因为你把自己调成了震动模式，所有情绪都变模糊了。",
        "大务实家_大资本家": "你是务实界的资本家，每一分力气都要见到回报。你不欠任何人，但你也不爱任何人。你是精确的，也是空的。",
        "大务实家_空心化石": "你的务实已经钙化了。你不计算了，因为所有数字都刻在你骨头里。你是活着的Excel表格，没有公式，只有死数。",
        "现实中人_暗处判官": "你嘲笑一切理想，但你也嘲笑自己。你觉得自己是唯一清醒的人，其实你是唯一不敢醉的人。",
        "现实中人_躁动演员": "你演一个没有感情的杀手，但你的眼神偶尔会慌。你怕被人看穿你其实还有一点点温度，那点温度让你恶心。",
        "现实中人_清醒囚徒": "你知道所有残酷的真相，然后你选择闭嘴。你的现实不是勇敢，是不敢。你把自己锁在“没办法”这三个字里。",
        "现实中人_木偶哲人": "你从不思考，因为思考会带来痛苦。你的“现实”就是拒绝思考的借口，像一只把头埋进沙子的鸵鸟，还说自己务实。",
        "现实中人_做梦逃兵": "你偷偷做过很多梦，然后你把它们都杀死了。你告诉自己“现实点”，其实是怕梦醒了会哭。",
        "现实中人_快乐傻子": "你的快乐来自麻木。你不在乎了，因为你把自己训练成了一块石头。石头不疼，石头也不活。",
        "现实中人_大资本家": "你是最精明的利己主义者，每一口呼吸都要算成本。你的现实是吸血鬼的现实，只进不出。",
        "现实中人_空心化石": "你已经不是人了，是一个社会达尔文主义的标本。你挂在墙上，对所有活着的人说：“看，这才是现实。”"
    };

    const ROAST_EXTRA = [
        "你的地下室人格档案已更新。建议别锁门，它迟早要出来。",
        "两面夹击，你还能撑多久？",
        "你的矛盾很值钱，但没人付账。",
        "做人嘛，最重要的就是双标。",
        "你比你自己以为的有趣多了，可惜你不敢承认。"
    ];

    let answers = new Array(18).fill(null);
    let total = 18;

    function renderQuestions() {
        const container = document.getElementById('questionsContainer');
        if (!container) return;
        let html = '';
        QUESTIONS.forEach((q, idx) => {
            html += `
                <div class="question-item" data-qidx="${idx}">
                    <div class="q-text">${idx+1}. ${escapeHtml(q.text)}</div>
                    <div class="options">
                        <label class="opt-label">
                            <input type="radio" name="q${idx}" value="left" data-qidx="${idx}">
                            <span class="opt-text">${escapeHtml(q.left)}</span>
                        </label>
                        <label class="opt-label">
                            <input type="radio" name="q${idx}" value="right" data-qidx="${idx}">
                            <span class="opt-text">${escapeHtml(q.right)}</span>
                        </label>
                    </div>
                </div>
            `;
        });
        container.innerHTML = html;
        for (let i = 0; i < total; i++) {
            const radios = document.querySelectorAll(`input[name="q${i}"]`);
            radios.forEach(radio => {
                radio.addEventListener('change', (e) => {
                    const qIdx = parseInt(e.target.getAttribute('data-qidx'));
                    answers[qIdx] = e.target.value;
                    updateProgress();
                });
            });
        }
        updateProgress();
    }

    function updateProgress() {
        const answered = answers.filter(a => a !== null).length;
        const percent = (answered / total) * 100;
        document.getElementById('progressFill').style.width = `${percent}%`;
        document.getElementById('counter').innerText = `${answered} / ${total}`;
    }

    function computeResult() {
        const stats = {
            justice: { highCount: 0 }, sensitivity: { highCount: 0 }, happiness: { highCount: 0 },
            reality: { highCount: 0 }, freedom: { highCount: 0 }, think: { highCount: 0 }
        };
        for (let i = 0; i < total; i++) {
            const dimInfo = DIM_MAP[i];
            const dim = dimInfo.dim;
            const answer = answers[i];
            if (answer === 'left') stats[dim].highCount++;
        }
        let light = '';
        light += stats.justice.highCount >= 2 ? 'J' : 'E';
        light += stats.sensitivity.highCount >= 2 ? 'S' : 'D';
        light += stats.happiness.highCount >= 2 ? 'H' : 'U';
        let dark = '';
        dark += stats.reality.highCount >= 2 ? 'R' : 'P';
        dark += stats.freedom.highCount >= 2 ? 'F' : 'T';
        dark += stats.think.highCount >= 2 ? 'L' : 'I';
        return { lightCode: light, darkCode: dark };
    }

    function showToast(msg, bg = '#8b5a2b') {
        let toast = document.getElementById('liveToast');
        if (!toast) {
            toast = document.createElement('div');
            toast.id = 'liveToast';
            toast.style.position = 'fixed';
            toast.style.bottom = '25px';
            toast.style.left = '50%';
            toast.style.transform = 'translateX(-50%)';
            toast.style.backgroundColor = bg;
            toast.style.color = 'white';
            toast.style.padding = '8px 20px';
            toast.style.borderRadius = '40px';
            toast.style.fontSize = '0.85rem';
            toast.style.zIndex = '999';
            toast.style.fontWeight = '500';
            toast.style.boxShadow = '0 4px 12px rgba(0,0,0,0.2)';
            toast.style.whiteSpace = 'nowrap';
            document.body.appendChild(toast);
        }
        toast.style.backgroundColor = bg;
        toast.innerText = msg;
        toast.style.opacity = '1';
        clearTimeout(window.toastTimer);
        window.toastTimer = setTimeout(() => {
            toast.style.opacity = '0';
            setTimeout(() => toast.remove(), 300);
        }, 2000);
    }

    function onSubmit() {
        const unanswered = answers.some(a => a === null);
        if (unanswered) {
            const leftCount = answers.filter(a => a === null).length;
            showToast(`还差 ${leftCount} 道题没选，你的暗面在嘲笑你逃避`, '#b66b3a');
            return;
        }
        const { lightCode, darkCode } = computeResult();
        const lightName = LIGHT_NAMES[lightCode];
        const darkName = DARK_NAMES[darkCode];
        if (!lightName || !darkName) {
            showToast("组合异常，刷新重试", '#8b5a2b');
            return;
        }

        const lightAnalysis = LIGHT_ANALYSIS[lightName] || "你对自己有看法，但说不清楚。";
        const darkAnalysis = DARK_ANALYSIS[darkName] || "你的地下室住着谁，你心里有数。";
        const comboKey = `${lightName}_${darkName}`;
        const comboText = COMBO_ANALYSIS[comboKey] || "这一对组合，你自己品吧。";
        const randomRoast = ROAST_EXTRA[Math.floor(Math.random() * ROAST_EXTRA.length)];

        const lightImg = LIGHT_IMAGES[lightName] || "";
        const darkImg = DARK_IMAGES[darkName] || "";
        const placeholder = "data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='140' height='140' viewBox='0 0 140 140'%3E%3Crect width='140' height='140' fill='%23d9cdbc'/%3E%3Ctext x='50%25' y='50%25' dominant-baseline='middle' text-anchor='middle' fill='%238b5a2b' font-size='14'%3E?%3C/text%3E%3C/svg%3E";

        const resultDiv = document.getElementById('resultArea');
        resultDiv.style.display = 'block';
        resultDiv.innerHTML = `
            <div class="character-images">
                <div class="img-card">
                    <img src="${lightImg}" alt="${lightName}" onerror="this.src='${placeholder}'">
                    <div class="label">光明面</div>
                </div>
                <div class="img-card">
                    <img src="${darkImg}" alt="${darkName}" onerror="this.src='${placeholder}'">
                    <div class="label">地下室人格</div>
                </div>
            </div>
            <div class="art-name">
                <span class="quote-left">“</span>${lightName}<span class="quote-right">”</span><br>
                <span style="font-size:1.8rem;">但</span><br>
                <span class="quote-left">“</span>${darkName}<span class="quote-right">”</span>
            </div>
            <div class="result-title">你的双重人格档案</div>
            <div class="result-desc">
                <div class="analysis-section"><strong>你自认为</strong><br>${lightAnalysis}</div>
                <div class="analysis-section"><strong>你的地下室</strong><br>${darkAnalysis}</div>
                <div class="analysis-section"><strong>组合特写</strong><br>${comboText}</div>
                <div style="margin-top: 0.8rem; font-style: italic; border-top: 1px solid #e2d5c8; padding-top: 0.6rem;">
                    锐评：${randomRoast}
                </div>
                <div style="margin-top: 0.6rem; font-size:0.75rem; opacity:0.7;">地下室人格档案已更新 · 欢迎常来窥探</div>
            </div>
        `;
        resultDiv.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
    }

    function resetTest() {
        for (let i = 0; i < total; i++) {
            const radios = document.querySelectorAll(`input[name="q${i}"]`);
            radios.forEach(r => r.checked = false);
            answers[i] = null;
        }
        updateProgress();
        document.getElementById('resultArea').style.display = 'none';
        showToast('已重置，重新面对你的双重人格吧', '#8b5a2b');
    }

    function escapeHtml(str) {
        if (!str) return '';
        return str.replace(/[&<>]/g, function(m) {
            if (m === '&') return '&amp;';
            if (m === '<') return '&lt;';
            if (m === '>') return '&gt;';
            return m;
        });
    }

    renderQuestions();
    document.getElementById('submitBtn').addEventListener('click', onSubmit);
    document.getElementById('resetBtn').addEventListener('click', resetTest);
</script>
</body>
</html>
