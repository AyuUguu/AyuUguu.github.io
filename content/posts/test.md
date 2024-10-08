---
title: "麻雀もAIと対話するゲームになっている"
date: 2024-08-14T23:59:25+09:00
draft: false
toc: false
images:
tags:
  - mahjong
---

## はじめに

まず麻雀についての学習方法は一昔前まで、とにかく鬼打ちする、書籍を買って読むだとか、強い人に聞く、鳳凰卓上位陣の観戦・牌譜検討、プロの対局を見るだとかその程度しかなかったわけだが、昨今はAI検討が主流となっている。

麻雀AIサービスといえば有料で高品質の[NAGA](https://naga.dmv.nico/naga_report/top/)を筆頭に、無料の[mortal](https://mjai.ekyu.moe/ja.html)と今後も様々なAIが登場するのではないかと予想される。彼らAIがどの程度強いのかというと、おそらく長期の成績勝負で人間が敵うことはまずないということである。MリーグでAIチームがあったとしたら、高確率でプロを圧倒してしまうだろう。
またトリプル天鳳位でありAI研究の申し子である渡辺太(ないおトン)選手も、その勢いに拍車をかけることとなった存在だと思う。
彼はネット麻雀界における神のような存在であったが、今やプロ入りしMリーグにも参戦している。麻雀プロの悪い風習や凝り固まった戦略に、風穴を開けるような彼の打ち筋に期待したい。
麻雀という不確実性の強いゲームにおいて、ここまで超人的な成績を収めていると尊敬よりもむしろ恐怖心を抱いてしまう。


脱線したが私自身は無料で使いやすいmortalをよく使うので、自身への備忘録も含めその活用方法をまとめていく。


## moral ratingの推移記録を付けよう
実戦、つまり天鳳やじゃんたまで打った牌譜をまずはmortalにかける。これは牌譜URLを入れるだけでいいし、数秒で解析が完了するのですごい時代である。

![mortal1](/images/mortal1.png)

そうするとこのような感じでmortal ratingというのが表示される。これがなんなのかというと、評価値みたいなものでmortalとどれだけ打牌選択が一致していたかの精度数値みたいなものである。全体の一致率が高くても、とんでもない悪手をしている場合などはratingは下がる傾向にある。このratingが高ければ高いほど強いというわけではないのだけれど、どれだけミスらしいミスをしていないか、変なことをしていないかを確認する指標としては非常に優秀だと思う。ただ単に全体の一致率で自分の打ち方を評価するのもありだと思う。

で、この数値をスプレッドシートやexcel等で日付とratingを集計しまとめよう。そうするとどれだけ自分の麻雀が改善されていってるか、または勉強したけどratingは下がっているなど、自身の麻雀をある程度客観視できるのは便利だ。どうしても自分一人で振り返りをやっていると、気が付けない悪い癖や傾向は多いので、AIにどんどん指摘してもらおう。

イメージとしては  
**・mortal ratingが80未満**  
明らかなミスが多く、やばいことをやっている証拠なので改善が必要。おそらく初心者。

**・mortal ratingが80以上85未満**  
ミスは多いがある程度は打てている。ただ押し引きや降り方などが雑な可能性あり。

**・mortal ratingが85以上90未満**  
結構精度高く打てている。細かい部分でちょっとしたミスや下位互換の選択をしている可能性あり。

**・mortal ratingが90以上**  
かなり精度高く打てている。細かい降り方の手順や字牌の切り順、手牌構成の細かな部分などで減点されていることが多い。概ね問題ない。

私自身は現在93～90くらいが平均値で、強引な混一色やアシスト・差し込みみたいなことをやった半荘は89,88になることもたまにあるという具合。それよりいい時は明らかに手牌が良く分かりやすい展開が続いたり、95以上出るときはそもそも途中で誰かが飛んだみたいな局数が短い時だけである。

一昔前は88～85辺りが平均値であったので、かなり麻雀が改善されているのが分かる。

ただもちろんmortalにも弱点というか、こっちのがよくね？みたいなのもたまにあるのでそこら辺はまあブレる要素なのかなと言う感じ。mortal ratingが低くてもNAGAにかけたら高得点もらえるみたいなこともあるし。
ratingを適切に理解し使いこなすことは難しいから、なんとなく高い方がいいくらいに捉えておくのが寛容だ。AIがいう悪手もモデルによって異なるし、今後学習が進んで変わるかもしれない。

mortalでやはり最も有用なのは守備面で降り判断、手順、無駄押し、単純なミスを発見できることだと思う。

## 悪手を徹底的に振り返る

![mortal2](/images/mortal2.png)

振り返りでいう悪手というのは、このように赤色で表示される。#4/13というのはmortalの13候補あるなかの4位の選択をしていますよということである。ここでいう1m切りというのはmortalからすると全体の100あるうちの0.43しか選びようがないですよという無慈悲なお言葉になっている。要するに悪手。

今回の場合、3位までの選択は52、35、11と割れているので別にそれらのどれかを選べていれば悪手ということにはならないと個人的には思う。ただ4位のような1を切っているようなものは明らかな悪手になる。

たぶんmortal的にはドラも赤もない手から、手役に絡む牌、ここでいうと純全帯や三色に必要ない牌から切っていきましょうということだと思う。もちろん6sや4mを切るデメリットもあるんだけど、そもそも手も悪いし安全度を担保しつつ打点も狙える6sや4m以外に切りようながないと感じる。後からは何とでも言えるけど。雰囲気で切ってしまったがよくない。

このように振り返る。

振り返りを長くやっているとmortalならこれ切らなそうだなーとか、降りそうだなーみたいな感覚がなんとなく身についてきてratingもだんだんと上がっていく。

## 麻雀が強い＝ミスが少ない

この考え方は非常に重要である。特別な才能だとか、読みだとか、そういうのは基本的に必要なくとにかく見えている情報を使ってAIに怒られない打ち方を身に着けるだけで、ある程度は強くなることができる。ただ注意すべきなのはAIやトッププロと同じ牌を選んだとしても、その選択の解像度が全く違うケースは多い。だからこそ生涯勉強であり、一生最強にはなれないし、AIには勝てないという意識をもって考えることをやめてはいけないと思う。

## AIと一緒に楽しむゲーム
私自身の経験になるが、最近はも対局云々よりももはやAIとの差異を楽しむゲームになっていると感じる。AI一致度やratingが高ければラスっても別に嬉しいし、トップを取った半荘でもミスが多くratingが低ければうーん、と落ち込んでしまう。そんなことも増えてきたように感じる。
将棋はもっと評価値ディストピア状態ではあるが、麻雀についても今後同じような事態になっていくのではないかと予想される。

これには良い面もあり悪い面もある。例えばAI検討はメンタルケアには非常に適している。手痛い放銃でラスってもAIも同じ放銃をしているなら、間違ってないじゃん！と強気になれるからだ。正しい手順だったのに疑心暗鬼になることを避けることができるのは素晴らしいだろう。

何にせよ、麻雀は千差万別で答えがない。でもこっちの選択の方が長期的に見て優れている、というのは常に存在している。





