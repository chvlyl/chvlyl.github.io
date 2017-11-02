---
layout: post
title: "Capital One interview questions"
date: 2016-01-30
---


## Python
num1 = input()
input_string = raw_input()
raw_input() takes exactly what the user typed and passes it back as a string. input() takes the raw_input() and performs an eval() on it as well. The main difference is that input() expects a syntactically correct python statement where raw_input() does not.

pow(a,b) a**b

print '%0.2f' % num1

arr.extend([10,11])
insert(i,x) 
remove(x) 

Lambda functions cannot use the return statement and can only have a single expression. Unlike def, which creates a function and assigns it a name, lambda creates a function and returns the function itself. Lambda can be used inside lists and dictionaries.





### MITBBS 2007

case：
1.信用卡问题，基本一模一样. 计算利润.

credit limit            5000
account balance         2000
Interest rate(customer) 16%
cost per card           40
annual fee              20
interest rate(C1)       6%
defalult rate           2%

[20-40+2000*(16%-6%)]-5000*2%
=180-100
=80

If credit limit drop from 5000 to 3000

1>other things been equal, what will the profit change
80＋(5000-3000)*2%=80+40=120

2>if profitable stay the same, 
1. how much can account balance change
120-80=(A/B-A'/B'-(16%-6%)
A/B CHANGE=400


2. how many customer may leave
120N'=80N
N'=2/3N


X轴 customer loss  Y轴 account balance change
一弧线 profit=80 问与X Y轴的交点坐标
问线外点是有利还是无利
which is the 最优点
原点

问 原点时 profit  多少
同question 1 >120

2.信用卡，revolver和transactor的问题
revolver就是有很高balance的用户，transactor就是每月按时还全部钱的用户，对两种不同的账户分别算算利润是多少，然后说一下如果你有钱做marketing，你会怎么选择把你的钱分配给这两种客户


behavior：
1. 冲突怎么解决
2. 学习新东西解决问题
3. 记不清楚了




### MITBBS Dec. 2010
今天去面试statistician,背景刚毕业的master，各个东西都懂一点但是都没有实战经验。这边的主要是auto和Ｍorgage的，然后也在建立CRM.

第一个是behavior，是里面的一个统计phd来问的:问过去的project有没有去问别人来学习东西一起合作的经历，并阐述。文过去项目里面有没有需要学习新的方法来搞定项目，并阐述过程。然后就随便扯了一下简历上面的一个如何predict yield curve 的time series model问题。

第二个是case study,一个犹太人来问的。现在有信用卡，平均balance B,利息x,还有平均的purchase amount S, 然后对于purchase你可以从商家手1.5％的回扣。然后问你如何去提高收益。我当时说的是加入不考虑default那些的东西，我们但从收入来看，可以比如给大家cash back rebate,然后大家会增加购买，同时也可以提高credit limit这样有可能可以提高balance然后收更多的利息。然后他就举了几个数字说如果我们给cash back rebate 1%我们如何办，然后就是有一个break even linｅ(ｘ坐标是 increased purchase,y坐标是increased balance)，然后分析上面有些区域是实际不可操作的,然后该如何办（一下是他提示下搞出来）那么我们就不要看平均，而分segment分析，。比如如果某人以前Purchase＝０的，只要有increase purchase我们都等于额外赚钱了，所以对他们我们可以推行这个计划。差不多就是这种类似的东西了，大家可以发挥。

第３个是role play.分析如何把航空公司晚点的概率降低。给了一个regression的数据和图表，从correlation　matrix看里面有些东西有strong correlation,然后他们直接去fit regression，然后你自己我去看这个东西有没有问题以及如何用它来指导business　unit，我分析的问题有。１，它把day of the week(mon,tue...)当成了continuous variable,肯定不行，改成categorical,２。公司只关心delay<8分钟与否，不care具体时间，所以这个就把regression改为了logistic regression.３。它把温度作为contiuous　variable，其实没有必要，你只要看是不是温度很差就可以了，所以自己设threhold把温度也变成categorical vraible.４。起飞地点他没有区分，后面有一个图可以看出不同起飞地方增加地面服务人员影响不一样，所以可以分开做两个logistic regression　model，因为一个是la,一个是nyc，他们的温度变化会很不一样。５。没有加入飞机上面实际座位的影响，加这个进入predictor就可以了。６，还有就是他的图表有可能有些数字不合理，比如座位书＝－１，你有空就看一下。然后就照着上面的这些东西自己重新建ｍｏｄｅｌ就完了。然后他还顺便问了一下有那个strong correlation你咋办，都是标准答案，然后有补充了一句如果你一定要把拿两个factor都放在Model里面你该如何搞和如何解释，都可以从书上找到答案的，就不贴出来给大家一点悬念了。

午饭和一个白人吃饭随便聊一下股市和其它东西，感觉capitalone做统计模型还是可以，他们还偶尔请外面的大牛像friedman之类的给他们讲一些model，以前面试的公司基本上都用logistic就完了，他们也有人在搞classification tree, ada boost, ensemble, neural network那些statistical learning的东西。

４。case interview.老印，啊老印。sun啊sun。东西很简单，就是信用卡有balance,有default rate，然后算利润，我的失误就在于经常忘记把利息放进去。然后你做假设老印又说这不对那不对的，靠。不过基本上大家对待老印心平气和一点就可以把它的问题搞定虽然他很装13.


### 1p3a  Mar. 2015
HR面：问问简历问题，还有你会些什么语言擅长什么。

OA：在hackerrank做的，所有题都要自己写Scanner in = new Scanner(System.in)来读入。
1. 读入m和n，m个coins，有n个heads的概率是多少。有一个test case一直过不了，不知道是哪个边界条件。
2. 和Leetcode的anagrams类似，读入一个String，所有单词以空格隔开，除了数字和字母以外的字符都要去掉，大小写也不算。比如"R&D","dR"这种也算anagrams，最后每一行输出一组anagrams 
s1 = raw_input().lower()
arr = s1.split(' ')
lt = 'abcdefghijklmnopqrstuvwxyz'
word2anagrams = {}
for wd in arr:
	new_wd = []
	for le in wd:
		if le in lt:
			new_wd.append(le)
	new_wd.sort()
	new_wd_string = ('').join(new_wd)
	if new_wd_string not in word2anagrams:
		word2anagrams[new_wd_string] = []
	word2anagrams[new_wd_string].append(wd)
for wd in word2anagrams:
	print word2anagrams[wd]

import re 
inputVal = raw_input()
inputArr = inputVal.split(' ')
regex = re.compile('[^a-zA-Z0-9 ]')
dict = {}
for word in inputArr:
    key = regex.sub('', word)
    key = ('').join(sorted(key))
    if key not in dict:
        dict[key] = []
    dict[key].append(word)
print dict
for ky in dict:
    print dict[ky]
3. 读入一个数字，还有多个面值，这些面值能组成这个数字的方法有多少个。比如读入数字是10，面值是(10, 5, 1)，应该有4种。，我用了LC上的NP套路来做，也就是combinations, subset这种题的套路。

两天后被通知电面。
电面我真蛋疼，人生的第一个印度面试官，人其实不错的。一开始打电话过来我完全听不懂，我以为是我听力不好，差点都哭出来了，后来他换了个电话，我瞬间听得很清楚了，超级清楚完全没杂音，所以想问一下大家啊！是不是不同移动公司会有这种情况，因为我电面很多次了，大部分都是听得很清楚，有些时候就会出现这种听上去有点嘈杂，而且会有1 2秒的延迟。

1. 简历问题，问的非常细致，我之前做过一个推荐系统，这个面试官对这一块非常擅长，所以问得很细很专业，我没答好，加上一开始的确听不懂。所以建议大家可以先linkedin面试官，看看他擅长什么，我遇到过几次面试官喜欢问自己擅长的东西。
2. 一个超市，有100个顾客的list，70个男的，30个女的，如果用这个数据做数据分析会有什么statistical issues，问这个100个顾客会是什么样的distribution
3. walk through一个mapreduce问题，一组数据，四个columns: name, category, # of transactions in 2014, dollar values of transaction in 2014，需要知道每个category的average dollar values per transaction，怎么用mapreduce做，其实就specify一下mapper和reducer的input和output，然后在reducer里求一下平均值什么的。
def mapper(self,line):
	(name,category,num_transactions,dollars) = line.split('\t')
	yield category,(num_transactions,dollars)

def reducer(self, category, transactions):
	totalnum = 0
	totaldollars = 0
	for num_transactions,dollars in transactions:
		totalnum = totalnum+num_transactions
		totaldollars = totaldollars + dollars
	yield category, float(totaldollars)/totalnum

不会开摄像头，我一开始Scanner就不会写，就google了。


### MITBBS Jan. 2015
去年12月份拿到了Capital One 2015 暑期实习的电面，然后这周一去了VA参加他们的onsite。之前在准备面试的时候在mitbbs上找到很多有用的信息，所以面完后来此汇报一下面经，希望对其他同学有帮助。

面试一共有四轮，从早晨八点到中午十二点，然后公司派人一起吃午饭，不过午饭不算入面试。面试包括两轮的case interview,一轮role play还有一轮behavioral question。其中role play是比较经典的飞机是否晚点的模型汇报，在jobhunting版精华区前人已有很详细的总结。我个人的感觉是因为在假定的情景里之前的work是同事做的，所以一方面可以说一下模型中的问题（其实问题挺多的），另一方面可以讲讲工作的意义，最后跟对方请求更多时间来improve这个模型。

两个case interview都比较简单，一个是算conditional probability，但是要和信用卡的business联系起来，所以要对信用卡整个的盈利情况（收入，支出）有一定了解。另一个case是关于人寿保险的，告诉你收入和固定支出，以及客户挂掉后的支出，然后问客户挂掉的概率是多少可以达到break even。然后又假定了如果客户挂掉的一定概率，然后如何基于数据分析结果做一些商业决定。感觉整个问题难度和中学数学差不多，只要能够完整理解整个题目，解答还比较简单。

Behavioral question问了三个问题，第一个是描述一个完整的project，第二个是讲讲你是怎么说服别人同意你的观点的，第三个是讲讲你在一个project中面对重大变化是是怎么处理的。个人觉得behavioral question对于我们中国人来说相对难一些，毕竟是个讲故事的环节，我们在语言和从小的教育上有一定劣势。所以我提前准备了一些小故事，每个故事中都旁敲侧击的提到一些自己的优点，然后根据不同的问题套不同的故事。不过最后一个问题还是让我蒙了一下，不过还好反应算快，临时想出了一个例子来应对。

面完后吃了午饭，在capital one逛了一下，感觉这里的人都很nice，硬件设备也很好，做统计的中国人很多，重要的是这个公司非常注重data对于商务决策的影响，因此一个面试官提到这里的statistician都是很核心的岗位而不是一些辅助的岗位。另外一个信息是他们的实习招的基本都是还有一年毕业的学生，其实相当于将来全职工作的预备役，所以一些低年级的PhD学生一般机会不大。还有就是他们提到在这个公司PhD和master工作性质没有很大差别（不存在master被用作sas programmer的情况），只是title和薪水可能不大一样。我个人准备接受这的offer了，如果版上有其他要去Capital one做暑期实习的，欢迎站内联系我。另外在我找实习的过程中，遇到了很多中国面试官，感觉大家都非常nice和热心，有些问题实际我答的并不好，但是对方就很 耐心的引导我回答正确答案。我个人非常感激这些公司里的前辈，以后有机会我也会这样去帮助自己人，也希望所有的国人能够在职场上多帮助自己的同胞。

信用卡那个就是他们用model预测用户是否会出现还不了钱的情况。他们define还不了钱就是坏用户（y=1），否则就是好用户（y=0)。这样每个顾客都有一个实际的y值，同时也会有一个model预测的y值，我们的目标是降低classification error。他们的问题就是给你真实的y和预测的y的marginal分布，然后给你一个条件概率（具体的不大记得了），然后让你推导其他几组条件概率，其实利用条件概率的定义就很容易的解出来了。这个问题用Venn Diagram感觉会简单一些。人寿保险的题目很简单，简化的题目就相当于，每个人投保要交1块钱，然后如果挂掉要付100元的赔偿金，那么当死亡率多少时可以实现breakeven，答案就是1%（实际题目中数字不同，但是解法是大致一样的）。

### MITBBS Oct. 2014
One question I remember is given a set of words, tell which words are made of same letters. The idea is to use hash table and check the collision lists. 

Bonus point is if you use bitarray to store the words, then no hashing is needed.

The other questions are insultingly simple, such as if the revenue is X, the cost is Y, what is the profit.

The case study is to find most popular stores, given some SQL tables.

It was for a senior associate position. 


### MITBBS Oct. 2014
面试一共四部分，senior statistician role

1. Airplane delay case，请自行考古。不过注意下，面试的时候资料已经变成v1.1版本了，所以在细节上（比如温度已经对晚点不影响了）跟帖子里写的稍有出处。最后问了multicolinearity。还有就是如果你重建模，假设原有的glm没有问题，这个glm模型该如何使用？

2. 考条件概率，内容是credit card delinquency risk。最后算出来的概率需要总结出cutoff line需要往下挪（原有的假设95%的人都是good risk）

3. Behavioral questions. 就是你遇到过什么挑战啊，学习新知识啊。面试官拿了一张纸，貌似他们用STAR (situation, task, action, results)的方式给你打分，所以最好都讲到。

4. Americana (the Brazil Walmart) credit card case. 就是算revenue, fix cost,variable cost和market share的。有空我把这个具体写一写

### Mar. 2014
再聊聊capitalone吧，capitalone楼主拿到了onsite。系里发了一个邮件，说capitalone 在plano的campus招statistician了，大家可以试试，我就投了，然后就开始电话面试。

第一轮电话面试是个美国人，statistician。技术面，问了什么是mean，standard deviaton，p－value，还有简单的logistic regression的知识，还有一些模型建立知识。我发现技术面是美国人都不会太难，遇到中国人你就自求多福吧。。。面试进行的很愉快，当时楼主已经拿到了offer，所以无压力，发挥的也比较好。然后刚面完hr就打电话给我约onsite了，一切都很美好，他们顶好机票和酒店，我飞到达拉斯去，公司约了limo来机场接我送到酒店去。酒店也很好，吃饭什么的都可以报销。然后第二天去面试了，就发现搞笑了，那天一共八个人去面，发现除了我和一个stanford的master，别的都是phd啊摔，当时楼主就心虚了。。。然后还有一个phd同学告诉我，capitalone的statistician是phd们的dream job。

开始面试，一共四轮，每轮一个小时。两个case，一个role play和一个behavioral questions。role play很有意思，就是一个statistician假装不懂统计，给你一堆数据一堆sas output和一堆图，给你十五分钟，让你给他讲讲整个project做了啥，有啥结论，有什么政策性意见。主要是看你统计学的好不好，能不能和不懂统计的人沟通，反应快不快，有regression，anova和correlation table之类的。最后再提一个模型改进。case第一个很简单，算break－even。第二个比较难，你要知道home loan怎么赚钱，怎么简历模型，怎么算条件概率，最后还要画一个奇葩的图。中午吃了饭参观了capitalone的campus，campus很大餐厅很豪华办公室很漂亮，但是参观的时候我就在想算了，这个地方这么好不属于我，我再努力两年再来吧。。。然后下午的时候他们留下了一个phd同学继续面试，把我和其他的同学送到了机场。我还弄丢了我的ipad，texas真是一个充满了伤心的地方啊。。。

### Mar. 2013
Technical question: 

1, presidential poll. Obama 52%, Romney 49%, margin error 3%. What is your conclusion? 

2, Hypothesis testing. New mailing campaign vs. old mailing campaign 

3, What is p-value? 

4, What is alpha level? 

其他的问题会穿插在你的回答中间，记不太清楚了。 

Business case: 
一个大学需要拉赞助，但只有有限的budget，改如何建模？可以向interview你的人随 便问问题，获取你建模所需要的信息。我问的是有关Alumni的问题，估计应该是朝这个方向回答。 建模的时候会问到有关logistic regression, detect outlier, model validation, multicollinearity等等的问题。 

### Jun. 2015
先是电面，问了一些基本的统计知识，比如什么是P值，3SIGMA原则等等比较基础的知识，最后会有一个案例分析，记得是如何预测校友会不会对学校捐款，问可以用什么模型来解决（这个好像是比较经典的问题，CAPITAL ONE好像用了多年了）。电面过后，是ON SITE面试，有两个地方可以选，一个是达拉斯一个是忘了~~~最后我去的达拉斯。现场面试共四轮，第一轮是一个印度哥哥，有案例分析，比如一个信用卡公司有两种宣传手段，一个是打电话，一个是写信，但是打电话便宜写信贵，但是写信效果好，然后给你一些成本情况等等，让你选择一个宣传策略。第二轮是比较经典的回归分析，就是给你一个SAS输出的回归结果，让你分析一下（经典面试题。）。第三轮是一个中国人（中科大的），会让你计算一些后验概率啥的。第四个人，会问一些behavior question. 

### Nov. 2011
Behavioral interviews:

Describe one complex problem you have solve, give example.
Show how you separate one general question to parts and handle it in detail
Give the example about your leadership on one project/issue

They followed these questions with some small questions based on your 
answers. I feel they want to know what you did in detail to check if there 
are some matches between your experience and the position. So,please get 
familiar with your previous projects and relate them to the role. 

Case Interviews:
1. the credit card case. Below is the link and some numbers were changed 
when I was interviewed.

http://www.mitbbs.com/bbsann2/life.faq/JobHunting/mianshiexp/C1

2. New Case (cannot be found online based on my search)

It looks a little like role play. Assume you are the president of One 
Company now ( Cannot remember exactly, let's call it Good)

The revenue and two costs are gave first, you need to check if it is 
profitable? (easy). Answer is No,

Show you ideas to make it profitable.

Next, give some info about sale force ( sale persons) and other more 
efficient firm, let's call it Better. Ask you the profit of Good if the sale
persons have the efficiency as Better. In addition, it involve some kind of
break even analysis. ( Not too difficult but it is better to clarify every 
number).

Good Luck to everyone and feel free to contact me if you need more info. 

### 1p3a Mar. 2013
测试分三部分，第一部分性格测试，没有时间限制，答一些strongly disagree ... strongly agree之类的问题，比如“在没有人lead的时候你会跳出来lead”之类的。
第二部分，verbal，19分钟，几个段子，几个题我忘了，十几个题吧。。true/false/cannot say的问题。.1point3acres缃�
第三部分，数学，25分钟，18个题好像。给个图或者表格，算各种增长率啊什么的，我脚的读题有点困难，有点绕。。。题读懂了就不难。

据说除了性格测试部分，其他的题都是随机的，近期做过的同学反映题都不一样，开始test前会有practice


### Mar. 2013
上来对方先介绍了自己 09年在C1 Intern 结束之后C1给了fulltime offer 10年毕业留
在C1.
没有让我自我介绍 但是根据我的resume提了几个简单的问题 跟统计没啥关系

下面就是technical的问题 问了我四个
1. 之前我们的mail credit card广告得到的response rate是10% 最近我们又统计了一次 response rate变成了18% 让设计一个hypothesis test 来确定是response rate确实提高了还是只是randomly happen

2. What does a p-value=0.02 indicate

3. Two consumption of multiple regression
我就回答了errors are independent with each other and errors have same variances.

4. 有两个个predictor 每个和response variable都是positive correlated 问为什么放在一起在model里就成了negative了
我回答的是因为multicollinearity

然后business case是 phone call campaign. 问怎么在不增加cost的情况下使得response rate增加
我回答我们有categorical variable可以用logistic regression. 然后把怎么做大致说了一遍

再然后就问了他几个问题 全程一共32分钟 有点紧张 但对方很nice 问题不是特别明白
的地方问他都很耐心并且详细的解释. 所以题目不懂就放心问 祝大家顺利


###
Behavioral interviews:
Describe one complex problem you have solve, give example.
Show how you separate one general question to parts and handle it in detail
Give the example about your leadership on one project/issue
They followed these questions with some small questions based on your
answers. I feel they want to know what you did in detail to check if there
are some matches between your experience and the position. So,pleas get
familiar with your previous projects and relate the




### 1p3a Jane 2015
找工季在版上潜水N久，发现本版是目前北美求职最好的bbs，没有之一，干货很多，大伙之间气氛也很和谐~~今天发个处女贴回报下大家
这个C1的Data Scientist position是linkedin上的recruiter主动联系我电话交谈后给的OA机会，之前投过他们家quant没有回应。板上之前的面经见：
http://www.1point3acres.com/bbs/thread-124946-1-1.html

test是在hackerrank做的，一共四道题，限时2.5小时。难度总体不是很大，感觉考的算法很基本，主要是要对C++基本库要了解。That said，如果给你4h让你有足够的时间慢悠悠google 基本库的话，十有八九是可以都搞定的。敝人以为，刷题是王道！目前我主要是在LC刷题~
四道题依次为：
1. 求组合数C(M,N),和niubixing兄弟一样，有一个test始终过不了，不知为何。。
2. 给一个字符串，对其进行一些文本编辑处理：除去非字母character，每个单词按音序排序，整个句子按音序排序，blabla
3. collatz经典问题，即所有自然数回归到1
def collatz(n):
    res = []
    while n > 1:
        res.append(n)
        if n % 2 == 0:
            n = n / 2
            continue
        elif n % 2 != 0:
            n = 3*n +1
            continue
    return len(res)+1

n = 20
print(collatz(n))
4. logistic regression，给出了回归系数，要求利用系数给出simoid function的值。

之后(如果有之后)应该是电面+onsite，本人从phy转行做DS，基本是零编程基础起步，还望板上诸位大牛多多指教~~谢谢！

### July 2012
周四面试的，C1招人还是挺狠的，中午到公司的时候看到一帮上午面试BA,OA和DA的，
大概2,30个。面试Statistician的只有6个人，5个都是同胞。
标准流程，2个case, 1个role play,1个behavioral. Role play就是精华区那个
airline的model,问了下别人也是，很简单。Behavioral也很普通，3个问题，1. How 
did you collaborate 2. Example of innovation, 3. How did you learn sth new.
出来后和大家聊case,发现可能case是换新的了，至少和以前完全一样的的case基本没
有。听到的比较类似的是比如C1和walmart合作推出walmart信用卡，问pros and cons,
给了一些条件求break even market share并问是否doable.

我就比较悲剧了，两个case都没见过，第一个是关于debt write-off，比如现在
customer average outstanding balance 是$2000, 其中只有15%的人能完全付清，问
能收回多少钱（假设剩下的人什么都不付）。接着如果现在给所有欠款的人一个offer
，让他们只付60%的钱，然后10%的人接受了这个offer，但是其实这10%的人里面有50%
能够完全付清，问能收回多少钱。接着又换了一个情况，现在9%的人能够完全付清，然
后make 60% settlement offer,所有人中10%接受这个offer，这其中包括9%原来的1/3
人数，问这样能收回多少钱。这个case实在是很乱 在glassdoor上也有一段 可能我理
解和他理解的有些出入，也贴在这里”Recovering Written-off Past Due Balances 6
months past due, avg $2000 balance, 15% pay in full, profitable? If 
introduce settlement option, ask for 60% of balance, 10% pay settlement but 
5% of them don’t pay in full, better choice? With new model, now 9% pay in 
full, but with settlement option now 10% take settlement but a third of 
original payers don’t pay in full, better? etc. (poorly worded and 
confusing case. unhelpful vague interviewer, arggg, cost me the job)”
只不过问到最后还多问了我一些break-even的问题 比如9%里面要有多人接受
settlement offer才会和不offer settlement时候一样，并且画了一个图，纵坐标是多
少人pay钱，横坐标是每个人pay多少，然后在图上标出之前scenario里面的店。

虽然在interviewer的引导下好歹做完了 但细想觉得这个case还是不清楚，关注的童鞋
可以自己讨论下，能记起来的只有这么多了。不过如果碰到这个case,我觉得最好自己
可以画一些饼图，标出来哪些人pay了多少，一定要和interviewer clarify清楚，不要
怕在clarifying上面多花时间。

第二个case是关于预测good customer vs bad customer. 刚开始他会给你% of actual
good credit customer, 以及p(actual good credit customer|predict to be good 
credit customer)， 然后让你算三个probability比如p(predict to be bad credit 
customer|actual good credit customer)，就用conditional probability的公式算就
好no-brainer。然后interpret下每个value代表什么对business有什么影响。

接着interviewer画了个图，x-predict credit score, y- actual credit score,设定
一个threshold,x,小于这个x的都是bad customer,然后他画了条单调递增曲线，表示是
他们现在做的model,告诉你曲线下面的面积代表the probability of being a good 
customer, 然后要你说明x左边，在曲线下的面积代表什么，其实就是p(actual good 
customer|predict to be a bad customer)，以及x右边曲线下面积代表什么，就是p(
actual good customer|predict to be a good customer)。 接着问如果要design一个
better model，better model的曲线如何，那就画一条曲线，在x左边这个线要比原来
的线低，x右边这个线要比原来的线高。
一天面试感觉还是挺兴奋的，但是第一个case实在让人郁闷，在这里求bless了~ 周四
面试，今天公司还放假，还要周一才能知道消息…煎熬的周末啊


### 2014
前景提要：3月份某天（具体时间忘了）接到电面邀请，约在18号。面完当天下午接到onsite邀请，选在4月7号。第二天收到一封邮件，包括面试时间，地点，面试环节介绍和行程准备。Capital One财大气粗，Travel Agent会帮你预定好酒店和机票，还包括机场至酒店，酒店至总部，总部至机场的专车接送。当然，你也可以自己开车，他们会帮你报销一部分有钱。
正题：
我的面试从早上8点到中午12点 Case-Behavior-Case-Role play。 但每个人都不一样，最好提前发邮件问一下Recruiter.
每个环节长度在45分钟到1小时左右，如果有多余的时间你可以选择问面试官问题也可以休息。
下面具体介绍下每个环节：

Case1:
两个面试官，一个是负责面试的，另外一个负责记录。（这是个特殊情况，负责面试的那个人正在接受面试培训，负责记录的那个人会记录我的表现，也会在面试后对这个实习面试官进行培训。之后的三个面试都只有一个面试官）
每个环节之前面试官都会自我介绍，这时候个人建议可以和面试官搭搭话，放松心情。

提醒：一下都是中文翻译，具体专业词汇可以上网多看些Case。
第一题的背景是：有一家新银行要进入某个新的信用卡市场，问你会考虑哪些要素。
我答曰考虑成本和收益。之后具体分析信用卡有哪些成本和收益。
成本：管理成本，制作成本，贷款成本，推销成本和违约损失。
收益：交易提成和利息。
然后给了面试官给了我管理成本，贷款成本，制作成本，Average Balance和Default Rate,让我算Break Even的市场份额，实际面试的时候不会都给，比如有时不考虑推销成本和交易提成等。
但是我列给她式子说算市场份额，必须要市场总人数才能算。
然后她又加了一个市场总人数，于是我开始动笔+计算器算，算完给她结果。（注意如果你算得慢，记得一遍算一遍保持沟通，不要沉默太久）
接着她改了某个参数，让我再算一遍。（大多数题都是这样，让你加个条件减个条件重新算）
最后让我给她些建议。
我就扯了些减少成本，增加顾客数量，同时要注意应对竞争者之类的。
总结，第一个因为面试官不成熟，总体感觉有些不流畅。

Behavior:
面试官是个美国人，一进来就问我的名字怎么发音，然后又和他聊到糟糕的天气和刚开的樱花。（再重复一次，每个面试官都很好，不需要有压力）
接着是三个常见的问题：

1.让我描述我完成一项任务
2.让我描述我怎么劝说别人
3.让我描述怎么应对变化
这些问题你都可以在他发你的参考文件和接下来我会给的网址里找到

Case2:
还是关于信用卡的案例，不过这次无关关市场份额。只要算一下达到利益均衡的时候Default Rate最高能到多少。
最后一个问题我卡了很久，一直没反应过来。他问我做之前计算的基本假设是什么，答案是所有的Default都在一年年末的时候发生。越早发生的话收到的利息就越少，因为一旦Default，我们的客户就会减少。

Role Play:
Statistcian特有的一个环节。面试官会给你10张左右的SAS输出表格，是关于航班延误的预测模型。
参数有：温度，飞机类型，座位数，旅客数，地勤人数，登机口工作人员人数，星期几
需要预测的是：延误时间
报告里的模型用了温度，地勤人数，登记口工作人员人数，旅客数，星期几
Response=1 如果延误时间大于0，反之 Response=0
但是在资料里写着，旅客不会在意延迟时间在8分钟以内的延迟。所以这个模型是不好的。
还有一个correlation table和一些各个参数之间的点图。
面试官给你15分钟时间准备，然后回来让你做个report，她扮演客户，只有基本的统计知识。
我在这里犯了一个错误，因为我在网上看到过会面这个，也知道这个模型不好，所以在report阶段就说了这个模型不好，应该用logistic而且应该把0和1的限制设在8分钟。
但后来仔细想想，report的时候应该认真做report，模型的好坏应该时候再论。

### MITBBS Mar. 2008
我学的是工程专业，和金融统计基本不沾边，不过有朋友在capital one帮我推荐，而
且平时也用了不少统计的东西，所以就去试了一把。
开始是性格测试，看这里的精华区说要consistent，不过我的感觉就是“跟着感觉走”
就对了。测试是每题给你5个选项，让你选择最适合你的和最不像你的，比如“你喜欢
数字”，“你渴望胜利”，“你喜欢和别人打交道”，等等。要注意的是有可能问题是
根据你的选择变化的。比如你前面有五道题，你选了五个不同的最适合你的选项，有可
能后面就出一道题，五个选项都是你前面已经选过的最适合你的，然后让你在其中选最
适合和最不适合的，这个时候不用多想，直接点吧。
性格测试完了以后是机考，考之前recruiter会给你一些link，有一些example让你练习
。就是看图表，然后根据图表的内容答题。小学应用题的水平，但是要仔细，而且有时
间限制，注意在正确率和完成率之间找平衡。recruiter告诉我说通过标准是看正确答
案的数目，仅供参考。
之后是面试，很奇怪的是有的人到这一步就可以直接onsite面试了，我偏偏要phone 
interview，也许因为我的专业吧。
面试过程很简单，开始自我介绍，然后说假装自己不懂统计，让你解释一些统计名词，
比如p-value，confidence interval，alpha等等。
之后根据你的resume，问一些统计方面的问题，我被问到的有：
1. 公司要做一个model，有1000个可能的predicter，10000个observition,问你用什么
方法可以挑选出合适的predicter可以做一个比较好的model。
2. 有两个group，我们知道mean和variance，想知道他们的区别是否significant，两
种办法test，一个是用t test，一个是用model Y=group，问两种方法的区别。
3. 问了我一个统计的名词，c开头的，我当时就没听清楚，后来讲了一下，大概是
multicollinearity之类的意思，然后问这样的情况出现在model里会有什么问题。
4. (听别人说的，这次面试没有被问到）关于logistic regression，公司发广告，有
一定的人会回应广告，回应定义为1，否则为0，问你如何建model分析这种情况，为什
么不用linear regression。
整个面试30分钟，最后我随便问了一个问题，就结束了。
上午电话面试，下午就收到消息不用继续onsite面试了,很遗憾。不过在面试之前就有
征兆，从朋友那里知道了这个面试官以前的表现，所以也不那么郁闷了。


### DataScientist
2015-11: Then comes a case interview about how to detect the credit card fraud. Asked about how to do validation, about specific method and specifically how to implement that. Asked a lot of possible problems with the model and how should you deal with that when time is limited.


2015-08: I was contacted by a recruiter on LinkedIn. She was absolutely the best part of the process. The interview consists of four parts: a hacker rank challenge, a phone screen with a current data scientist, a data set challenge, and an on-site interview. If you feel nervous about the hacker rank challenge, you can practice on other areas of the site. The test involves dynamic programming, natural language processing, some combinatorics and a simple regression problem. I found some of the wording confusing but comparing your answers to the test cases is helpful. You won't get to see all the test cases. The recruiter contacted me within an hour of submitting the test to let me know I passed to the next round. The phone screen was scheduled very quickly for a conference call. The interviewer never showed up to the conference call though. I let the recruiter know after waiting on hold for 15 minutes and she quickly resolved the problem. The nice thing about their phone interview is that there are no trick questions (think: how many ping pong balls fit in a 747?). Most of the questions are open-ended: if you were given this data set, what do you think the possible problems are? How confident would you be in your answers? There is one map-reduce question if you have experience with that. There will also be some behavioral questions (use the STAR technique to answer). The recruiter contacted me later in the day to let me know I had a very positive response from the interviewer. The on-site interviews are set on a fixed schedule (Fridays every two weeks). She gave me the option of taking the data test right away or waiting a week because I had some scheduling conflicts. I was told that there were still a few slots available to interview and that if I finished within a few days I might be able to get one. The data set challenge is one basic machine learning question on an anonymous data set and then a descriptive analysis plus an open-ended question about baby names. They say it's designed to take about 4 hours but that you can take as much time as you feel you need. You're supposed to wait 2 to 3 business days to hear back. The recruiter contacted me at the end of 2 business days. She had been delaying e-mailing me because she thought she would have had news earlier. She said she would get back to me at the latest the next morning. A day passed and I didn't hear anything. Then I got the bad news that I didn't get the interview. The biggest highlight of the whole process was the recruiter. She's really fantastic at her job.
Interview Questions
If you're trying to predict the gender of your customers and you only have 100 data points, what are possible problems?  (cross validation?)

2015-09: They are quite comprehensive in their evaluation. First round is a 2 hour coding exercise, it has just the right mix of programming/nltk/math skills. After you pass this, there is a phone interview consisting of mainly statistics related questions, map reduce and a case study (short one). This is followed by a couple of datasets you need to work on and answer questions. If you pass all of this, you will get an onsite call. I was told I was not a fit after the 3rd round, did not get any feedback despite asking for one.
Show Less

Interview Questions
Baby names dataset  

2015-09:
Went through the same process - recruiter call, hacker rank, technical phone, data science coding challenge and finally on site. Enjoyed thoroughly every step of the way including all the people I spoke (recruiter, interviewers - very nice people). For my onsite, there was 2 case, one behavioral, 1 role play and one meeting with Head of DS (felt conversational). Unlike others, my interviews definitely felt more like data science than as a developer - so that should be a good thing for some of you. I thought I did OK but not great so no offer was made - they are looking for near perfect candidates.
Show Less

Interview Questions
Probability, decision tree 


2015-07:
I was approached by a corporate recruiter by phone. The interview process consisted of an initial phone call with recruiter. The recruiter was pleasant and explained the job responsibilities a bit and asked if I had preference in location. The interview consists of 1) online coding challenge, 2) phone interview with a data scientist, 3) a data challenge problem, 4) onsite interview at Capital One's office. The technical interview was easy and uses Hackerrank. The phone interview was kind of confusing to me the data scientist didn't seem to have read my resume at all and didn't know I was applying to a different office. I was asked questions about basic regression models, map reduce and some data quality, biasing and munging questions. Overall I thought I did good.
Show Less

Interview Questions
String manipulation, permutations and dynamic programming on coding test. Phone interview was shaky as the interview didn't seem to have even read my file, preferences etc.  


2015-05:
Very professional and clearly laid out process. The data scientist interview comprises of 4 stages. Stage 1 is a coding test using Hackerrank and you have about 2.5 hours to complete it. Stage 2 is a phone interview - partly behavioral and partly technical thinking. Stage 3 is a data science challenge to showcase your data munging and analysis skills. The 4th stage is series of 7-8 one-one interviews comprising of case studies and behavioral interviews. This job was for the Capital one labs. The people seem to be really nice and professional. The HR was very systematic and helpful in keeping you updated. The only thing is that although a startup within a big firm they seem to have the problem of a large firm. Also, they seem to test you on many technology seems like they are not used and a bit unclear as to what I will be doing once I get the offer. Overall great experience and very good interview process for a large firm. Had a better offer so did not accept offer.
The case questions were different. It should be noted that the case questions are not similar to those for management consulting firms like McKisney or BCG. Both questions eventually lead to some form of break even analysis as one component of the case study. They provide you with a simple calculator. feel free to use it.


2015-03:
Interview
I was contacted by a recruiter in March to submit an application. The process was similar as described in some of the newer posts: there are 3 rounds before the on-site interview: first a HackerRank online coding test, then a technical phone screen by a data scientist, lastly a data analysis coding challenge containing a small machine learning question and a larger data analysis question. The bar in those 3 rounds were not very high and you likely would pass by not getting all the correct answers. I for one didn't get full credit for the HackerRank test. I think I did pretty well on the phone screen(the interviewer told me on the spot that I passed) and the coding challenge (recruiter said that the senior data scientist reviewing my work was "impressed"). But that's where my luck ended. The onsite interview was a full day, 6 sessions with 2 case interviews, 2 behavioral interviews and 2 job fit/technical interviews. The problems in the case interviews and the behavioral interviews were in line with what everybody else shared here. My performance was definitely not perfect in any of them, but I was able to generally finish all the questions in time with minor assistance from the interviewers. The 4 interviewers in the mourning were all nice and encouraging. Where I failed miserably was the two technical interviews in the afternoon. I assumed that based on my work experiences as a data scientist I'd be asked about more practical problem-solving or machine-learning related problems, but both interviewers still gave me very stylized, hit-or-miss trick questions (one about string manipulation and one about dynamic programming. those you would find on technical interview books, but would rarely use in a real-world setting, especially as a Data Scientist) which is more suitable for software engineers and/or wall street quants. I'd probably do much better when I was still in school and can dedicate my time for interview-prep, but at this point I was severely exhausted (not given any rest between interviews) and shocked I basically gave up. Thinking back, I was probably too naive to think that my work experience has exempted me from brain teasers. As long as there are too many people applying for the job, those questions will always have their places as justifications to eliminate candidates. The attitude of the two interviewers in the afternoon was also a bit strange. The first interviewer spent the first 10 minutes of the interview to basically suggest that since I mainly used R and SQL for my current job, I will not be able to quickly pick up newer tools like Python, Hadoop, Scala, etc. The second interviewer spent his first 10 minutes suggesting that he had never heard of the small company I work for now and that my modeling approach has some obvious flaws. After the tone of the interview was set, my failure in the technical questions became nothing but self-fulfilling prophecies. During my conversation with them I indeed found out my background to not be a perfect fit for the position, and I think they probably know it before the interview. However, rather than communicating it as a plain mismatch of expectations, they acted in a manner that made me feel professionally inferior and thus very uncomfortable. It's overall a very informative process and I got a very interesting glimpse on how big data will strategically play into the daily operation of a very large company, and what big data technologies are currently in demand. I just don't understand how I was able to advance so deeply into the interview process with such a misalignment of qualifications (I did both my HackeRank test and my coding challenge in R, which was enough hint for them to reject me if the choice of data analysis tool is really important). It's a waste of everybody's time.
Show Less

Interview Questions
Dynamic programming/backward induction on a multi-stage decision making problem 


2015-09:
Interview
same as explained by others - hackerrank, phone screen, coding on 2 data sets, face 2 face. The recruiter was from DC and did a very poor job. She sent only BCC emails so I knew that they were doing mass recruiting. Moreover, she always had a rude tone/attitude when talking over phone

Interview Questions
hackerrank - string manipulation, reverting them, logistic regression, binomial and for loops...nothing too difficult. no dynamic programming. You can practice coding challenges on hackerrank and you could crack the test. Phone interview was not at all interesting. Questions were open ended. The coding challenge is very interesting and fun to work on 


2015-03:
Interview
They mentioned that they are working on the data scientist interview process and figuring out how they want to do it so it may change, but this is how it went for me. I applied online to a listed opening. Phone call with HR-30 minutes, just reviewing my resume, and asking what languages I prefer. Phone call with current data scientist: about 45 minutes. Asked some questions to see if you knew what you were talking about with statistics (what sort of distribution would this be, explain SD/mean, etc.). Then a question about a data set and what some problems with it could be. Lastly walk through how you would solve a simple problem with map reduce. Data set-they sent a data set and said take about 24 hours to turn it around to them with some analysis using any language you like, and justify your answers. Some very basic questions (mode of data set, max/min, those sorts), then open-ended, "tell us something interesting". Never got feedback on this. On site: 2 case interviews: similar to what every other interview report has said. One was over Skype which was somewhat awkward as math had to be done on an iPad that they were watching from their end. 2 behavioral interviews: typical "tell me about a time when" questions. Only somewhat awkward as they take lots of notes which leaves some awkward silences. Lunch: they clearly set me up to eat with someone like me (age/background). Fine, good food! 2 technical interviews: one asking about how to conceptually solve a probability problem, one asking for pseudocode and then eventually actual code (language of choice) for a simple string manipulation problem. Overall a fine process.
Show Less

Interview Questions
Tell me about a time when you took a risk  
http://interviewquestionsanswers.org/forum/topic-2151-31-statistics-interview-questions-and-answers-page-1.html 



2015-07
nterview
first phone call, 30 minutes, then a coding quiz, then next. The total is 4 rounds. The coding quiz include coin change, machine learning, NLP problems, and logistic problems related to python or R. The recruiter is very nice, but the test is not easy to pass.

Interview Questions
What is your career plan?


2015-10
Interview
The recruiter explained that it was a 4-step process. First there was a 2-1/2 hour hackarank coding test. I passed that, though didn't at the time know that you can practice on the website to help prepare. Then there is a technical phone interview, which I passed. After that came a coding challenge, which had one exploratory data analysis problem and one machine learning problem. They were planning to change that section so it should be different now, but when I took it, but they had tricks such as giving you a link on the SSA website that points to corrupt data and see what you do with that. I did not pass that section unfortunately, and it was frustrating to have spent an entire weekend working on that project and have zero explanation why it did not pass. The fourth stage would have been an all-day in-person interview at their facilities.
Show Less

Interview Questions
How would you structure a basic MapReduce problem?  

2015-04
Interview
The interview process was very extensive. The first task was to complete an online coding challenge, consisting of three programming questions of varying difficulty, with a 3 hour time limit. The second task was a technical phone screening with a Capital One data scientist. The third task was a data science challenge consisting of two problems, the first involved creating a model trained on a large set of data, and the second involved reading in a large amount of data on baby names and drawing insights from it. After these tasks were completed successfully, I was brought in for an in-person interview. The in-person interview was an all-day affair beginning at 9am, and it consisted of five one-hour interviews. Two of the interviews were behavioral interviews, two were case interviews, and one was a technical interview. The case interviews weren't true consulting-style case interviews (as I was afraid they would be), but instead were a series of math problems related to Capital One's ventures. Also, in my case, most of the interviews were done over video conferencing. There was also a lunch hour where I met with a current data scientist at Capital One, but that was more informal. After performing well on the all-day in-person interviews (as I was told I did), I was brought in a second time for two hours to meet with two data science team managers. I was told these were "job fit" interviews. Both managers decided I was not a good fit on their teams. The entire process, from initial contact by the recruiter to ultimate rejection, was about 6 weeks.
Show Less

Interview Questions
Behavioral interview questions: "Tell me about a time you sought out somebody else's expertise." "Tell me about a time you persuaded somebody to implement a solution when they didn't think there was a problem." 


2015-04
Interview
Received a quick phone call from HR and then a coding test on HackerRank. The HackerRank test consisted of the following: Coin change problem, a coin flipping problem, and a NLP problem,

Interview Questions
Write an algorithm for the following: Coin change problem, a coin flipping problem, and a NLP problem,  


2015-03
Interview
First I had a call from the recruiter, who gave me an overview of JD and responsibilities. Next I solved 3 questions on Hackerrank which were a difficulty level of above average to hard. Next round was an interview with a senior Data Scientist who gave me questions on Statistics and MapReduce. After a bit of tinkering, I got to the required answer. Right now waiting n the Case interview… 
Show More

Interview Questions
Sample vs Population parameters, Mapper and Reducer functions  

2015-03
Interview
Coding online then if you pass, statistics and big data questions with a data scientist. Coding interview on hackerank is difficult. I believe that it is only suitable for a software engineer position; you have to use concepts from dynamic programming etc to solve the questions. Really irrelevant. After which you go on to be interviewed on stats and data analysis then if you pass you get invited to the… 
Show More

Interview Questions
online hackerank coding  

2015-05
Interview
The process was pretty involved with a number of steps, spanning about 4 weeks. The recruiter did a good job of preparing me for what to expect at each step. I like the fact that much of the process centered around things that assessed my aptitude for the job rather than just talking about myself in behavioral type interviews. 1) Phone screen 2) Online quiz (programming, stats, and probability) 3)… 
Show More

Interview Questions
Behavioral: Tell me about a time when you were involved in project / assignment that was heading in the wrong direction and how you turned it around.  
Heavy on combinatorics(how many ways of doing something) and algorithm related things. In general, it takes a long time to think through the problem before coding it, and after coding, if you do it naively you would not get all the test cases right. As I mentioned earlier, this was entirely inappropriate for anything other than a software engineer
anagrams, coin flips, json, change machine problem
coin flips: How many ways to get M heads if you have N coins? Manually Logistic regression problem: (coefficients * data) in a logistic regression function


2015-07
Interview
1. A recruiter called who said they mainly hire Ph.D's. I think it was something like 60/30/10 Ph.D/MS/BS. 2. Initial simple technical online quiz 3. Two separate interviews (one case study) and one technical (stats/coding) where each was 30 minutes long. All the questions were pretty standard though not necessarily indicative of data science performance.

Interview Questions
Case study - what features would you use to determine credit risk given transaction history from the past two years. Explain a simple map reduce problem Read in a very large file of tab delimited numbers using python and count frequency of each number (don’t overthink this. Use python done in a few lines) Whats more likely: Getting at least one six in 6 rolls, at least two sixes in 12 rolls or at least 100 sixes in 600 rolls? Find all the combinations of change you can for a given amount 


2015-03
Interview
The interview process was very structured and well documented. You complete online tests first and then go through two rounds of business case & behavioral interviews. The business case topics can be related or external to Capital One. Be sure to prepare work anecdotes for behavioral interviews as they will ask for lots of examples.

Interview Questions
What was the most complex work project you've worked on?  

2014-10
Interview
There are 2 stages of interviews. The first includes a 30 minute case, which was essentially about profitability and break-even analysis. The math is not difficult, just be sure to ask questions about information that might not be directly given to you initially. Afterwards was a 30 minute behavioral interview consisting of 2 questions related to teamwork and project work and challenges/difficulties associated with them.

Interview Questions
Business Case 

2015-03
Interview
HR call, online test, job fit phone call, onsite- power day interviews(2 behavioural rounds and 2 case interviews). overall they do not ask any difficult questions, and that is what sets Capital One apart from the rest of the industry. The focus is on problem solving skills, leadership skills and communication. They are majorly focussed on finding individuals who can step in and solve any business challenge where a lot might be unknown.


Interview Questions
behavioral interviews often have questions which are complicated or about really complicated real life work situations: eg: tell me about a time you did not agree with the managements decision/stratgey? 


2015-06
Interview
Efficient and thorough. They are definitely looking for nearly flawless candidates. Two case-style questions that involved working through profit/loss maximizing and minimizing. Two "behavioral" sessions which are more conversational about your background and motivations. I was not given an offer, nor told why I wasn't a good fit. I felt good about my background, case answers, and overall discussion with the team members. I suspect the position was ultimately given to someone less expensive or that was local as I would have needed a relocation package.


Interview Questions
Determine average daily cost or profit, then tweak the initial set of variables for new scenarios and finally determine a break even point.