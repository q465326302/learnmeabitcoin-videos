1
00:00:00,230 --> 00:00:03,449
so in this lesson I'm gonna cover and

2
00:00:03,449 --> 00:00:06,210
Bitcoin transactions basically cover how

3
00:00:06,210 --> 00:00:09,480
they work so yeah but the end of

4
00:00:09,480 --> 00:00:11,580
presentation hopefully you'll understand

5
00:00:11,580 --> 00:00:14,219
how transactions work what they look

6
00:00:14,219 --> 00:00:18,510
like and how to construct your own so

7
00:00:18,510 --> 00:00:20,130
I've broken up this presentation like

8
00:00:20,130 --> 00:00:23,519
last time into three different parts I'm

9
00:00:23,519 --> 00:00:24,930
gonna start up with the basics of

10
00:00:24,930 --> 00:00:26,760
Bitcoin transactions so I'm gonna

11
00:00:26,760 --> 00:00:27,359
explain

12
00:00:27,359 --> 00:00:28,920
basically what they look like what the

13
00:00:28,920 --> 00:00:33,300
data is representing like so and I'll

14
00:00:33,300 --> 00:00:34,500
cover everything you need to know about

15
00:00:34,500 --> 00:00:37,440
the structure of transactions and how

16
00:00:37,440 --> 00:00:40,379
they work after that I'll move on to the

17
00:00:40,379 --> 00:00:43,680
data so instead of just giving you a

18
00:00:43,680 --> 00:00:46,340
visual representation of what the

19
00:00:46,340 --> 00:00:48,510
transactions actually doing I'll show

20
00:00:48,510 --> 00:00:50,100
you what the data looks like

21
00:00:50,100 --> 00:00:52,020
so if you were to look inside an actual

22
00:00:52,020 --> 00:00:55,289
transaction I'll show you how the data

23
00:00:55,289 --> 00:00:58,590
describes that and how it works and

24
00:00:58,590 --> 00:01:01,680
after I've covered you know how they

25
00:01:01,680 --> 00:01:04,229
work and what the data looks like I'll

26
00:01:04,229 --> 00:01:07,049
start doing some examples so I'll

27
00:01:07,049 --> 00:01:09,420
construct a transaction from scratch

28
00:01:09,420 --> 00:01:11,159
just to show you how you can create your

29
00:01:11,159 --> 00:01:16,799
own Bitcoin transactions like that so

30
00:01:16,799 --> 00:01:18,600
yeah so I'll start now the first part

31
00:01:18,600 --> 00:01:23,490
with the basics of how Bitcoin

32
00:01:23,490 --> 00:01:28,020
transactions work so carrying on from

33
00:01:28,020 --> 00:01:30,840
last time in the last video I covered

34
00:01:30,840 --> 00:01:34,350
how mining works so if you remember each

35
00:01:34,350 --> 00:01:36,090
of these computers represents a Bitcoin

36
00:01:36,090 --> 00:01:37,920
node on the network and this is the

37
00:01:37,920 --> 00:01:41,210
entire network and they are sharing this

38
00:01:41,210 --> 00:01:45,630
file here called the blockchain so what

39
00:01:45,630 --> 00:01:46,799
happens is when you wanna make a

40
00:01:46,799 --> 00:01:51,400
transaction and send someone some money

41
00:01:51,400 --> 00:01:55,300
what you do is you just create a single

42
00:01:55,300 --> 00:01:57,250
line of data and so this little green

43
00:01:57,250 --> 00:01:59,020
line here represents a Bitcoin

44
00:01:59,020 --> 00:02:00,280
transaction which is just a bunch of

45
00:02:00,280 --> 00:02:03,010
data and you'll insert that into any

46
00:02:03,010 --> 00:02:04,000
node on the network

47
00:02:04,000 --> 00:02:06,370
and then they will store it in their

48
00:02:06,370 --> 00:02:09,399
memory pool and then they'll pass it on

49
00:02:09,399 --> 00:02:12,340
to the nodes they're connected to and so

50
00:02:12,340 --> 00:02:14,500
on and so on until everyone's got a copy

51
00:02:14,500 --> 00:02:16,450
of that transaction in their memory pool

52
00:02:16,450 --> 00:02:20,670
and then all of these nodes then will

53
00:02:20,670 --> 00:02:23,650
compete to try mine the transactions

54
00:02:23,650 --> 00:02:25,420
from their memory pool onto this file

55
00:02:25,420 --> 00:02:27,370
called the blockchain so let's say this

56
00:02:27,370 --> 00:02:29,709
one does it and after they've done that

57
00:02:29,709 --> 00:02:32,260
they will pass on that block that they

58
00:02:32,260 --> 00:02:33,550
have mined to the knows they're

59
00:02:33,550 --> 00:02:35,500
connected to they will add it to their

60
00:02:35,500 --> 00:02:37,800
blockchain and so on and so on until

61
00:02:37,800 --> 00:02:41,110
everyone's got a copy of the latest

62
00:02:41,110 --> 00:02:44,890
block to be added on to their file when

63
00:02:44,890 --> 00:02:47,350
that's done then this person can look at

64
00:02:47,350 --> 00:02:48,820
this blockchain and see that the

65
00:02:48,820 --> 00:02:51,010
transactions in there and because that

66
00:02:51,010 --> 00:02:52,650
transaction is now part the blockchain

67
00:02:52,650 --> 00:02:55,600
the ownership of this bot this Bitcoin

68
00:02:55,600 --> 00:02:58,090
has change from this person to this

69
00:02:58,090 --> 00:03:03,370
person so today I'm going to cover how

70
00:03:03,370 --> 00:03:05,590
does this work how can you create a

71
00:03:05,590 --> 00:03:08,440
single line of data like this and how

72
00:03:08,440 --> 00:03:09,430
does that represent

73
00:03:09,430 --> 00:03:12,760
the change of ownership of bitcoins so

74
00:03:12,760 --> 00:03:16,209
I'll care for that now so the basics of

75
00:03:16,209 --> 00:03:19,870
Bitcoin transactions let's see this

76
00:03:19,870 --> 00:03:21,750
green line here represents the data and

77
00:03:21,750 --> 00:03:24,190
it's gonna send or change the ownership

78
00:03:24,190 --> 00:03:28,600
of this Bitcoin from me to you so if I

79
00:03:28,600 --> 00:03:30,940
blow that up this green line here still

80
00:03:30,940 --> 00:03:32,470
represents the transaction data I'm not

81
00:03:32,470 --> 00:03:34,000
going to show you the data yet this is

82
00:03:34,000 --> 00:03:35,110
just going to be a simple representation

83
00:03:35,110 --> 00:03:41,350
of the actual data first of all this is

84
00:03:41,350 --> 00:03:42,489
the blockchain let's say this represents

85
00:03:42,489 --> 00:03:47,950
the blockchain carrying on from the last

86
00:03:47,950 --> 00:03:50,290
presentation we know that it's just a

87
00:03:50,290 --> 00:03:51,700
bunch of blocks individual blocks

88
00:03:51,700 --> 00:03:54,040
containing transactions so the

89
00:03:54,040 --> 00:03:55,900
blockchain is just one big file of

90
00:03:55,900 --> 00:03:58,560
transaction data but

91
00:03:58,560 --> 00:04:00,150
because we're looking at transactions

92
00:04:00,150 --> 00:04:05,069
today a good way to visualize what that

93
00:04:05,069 --> 00:04:07,530
transaction data represents in the

94
00:04:07,530 --> 00:04:10,530
blockchain is a bunch of different

95
00:04:10,530 --> 00:04:13,230
batches of bitcoins so each of these

96
00:04:13,230 --> 00:04:15,440
little orange boxes here represents a

97
00:04:15,440 --> 00:04:19,829
individual batch of bitcoins and each of

98
00:04:19,829 --> 00:04:21,570
those batch of bitcoins has a lock on

99
00:04:21,570 --> 00:04:26,040
them and so that's how people can own

100
00:04:26,040 --> 00:04:28,889
bitcoins because a lock is placed on

101
00:04:28,889 --> 00:04:31,530
them so that only the people who can

102
00:04:31,530 --> 00:04:33,270
unlock them will be able to spend them

103
00:04:33,270 --> 00:04:35,550
and send them to someone else so

104
00:04:35,550 --> 00:04:39,030
basically the blockchain if you saw

105
00:04:39,030 --> 00:04:41,520
visualize what it's representing is a

106
00:04:41,520 --> 00:04:45,780
bunch of lock boxes like in a bank like

107
00:04:45,780 --> 00:04:49,440
this all different sizes of bitcoins so

108
00:04:49,440 --> 00:04:52,770
if I move out to the site now we're

109
00:04:52,770 --> 00:04:54,169
going to construct the transaction and

110
00:04:54,169 --> 00:04:59,400
move bitcoins from me to you so if I

111
00:04:59,400 --> 00:05:00,840
were to construct a transaction in the

112
00:05:00,840 --> 00:05:02,880
first part of the data so this is a data

113
00:05:02,880 --> 00:05:05,400
what we do is we select a batch of

114
00:05:05,400 --> 00:05:08,580
bitcoins from the blockchain each of

115
00:05:08,580 --> 00:05:10,380
these batches of bitcoins have their own

116
00:05:10,380 --> 00:05:12,720
unique reference number so you can

117
00:05:12,720 --> 00:05:16,260
select them so in this first part you

118
00:05:16,260 --> 00:05:17,850
will put some reference code in here to

119
00:05:17,850 --> 00:05:19,530
select the batch of bitcoins you want to

120
00:05:19,530 --> 00:05:24,570
send then in the second part or the

121
00:05:24,570 --> 00:05:26,130
second half of this first part of the

122
00:05:26,130 --> 00:05:29,220
transaction and you need to be able to

123
00:05:29,220 --> 00:05:33,300
unlock this batch of bitcoins so what

124
00:05:33,300 --> 00:05:35,640
you'll do is you'll put some unlocking

125
00:05:35,640 --> 00:05:38,760
code or use your private key to be able

126
00:05:38,760 --> 00:05:40,890
to prove that you can unlock this

127
00:05:40,890 --> 00:05:44,940
particular lock like so so that's the

128
00:05:44,940 --> 00:05:47,010
first half done just select a batch of

129
00:05:47,010 --> 00:05:49,110
bitcoins and unlock them and then the

130
00:05:49,110 --> 00:05:51,960
second half of the transaction you just

131
00:05:51,960 --> 00:05:54,630
create a new batch of bitcoins and you

132
00:05:54,630 --> 00:05:57,240
will put in the second half you'll put a

133
00:05:57,240 --> 00:05:59,340
new lock on it so this was the original

134
00:05:59,340 --> 00:06:01,800
the original batch of bitcoins that was

135
00:06:01,800 --> 00:06:04,800
locked to us and in this transaction

136
00:06:04,800 --> 00:06:07,440
we've taken that batch opened it up

137
00:06:07,440 --> 00:06:10,530
created a new batch from it and put a

138
00:06:10,530 --> 00:06:11,529
new lock on it

139
00:06:11,529 --> 00:06:14,649
and this lock is locked to this person's

140
00:06:14,649 --> 00:06:17,349
say address which is like an account

141
00:06:17,349 --> 00:06:21,519
number and so that is a very simple

142
00:06:21,519 --> 00:06:23,979
transaction just select some bitcoins

143
00:06:23,979 --> 00:06:26,709
unlock them quit a new batch and put a

144
00:06:26,709 --> 00:06:29,109
new lock on them and they are locked to

145
00:06:29,109 --> 00:06:34,299
this person here so when you think of

146
00:06:34,299 --> 00:06:37,209
making a transaction it's best not to

147
00:06:37,209 --> 00:06:39,069
think of it really as having some

148
00:06:39,069 --> 00:06:40,719
bitcoins and then transferring them

149
00:06:40,719 --> 00:06:41,979
across the internet to someone else

150
00:06:41,979 --> 00:06:44,559
that's not quite how it works what

151
00:06:44,559 --> 00:06:47,349
really happens is you have a set of keys

152
00:06:47,349 --> 00:06:49,719
like an address and a private key and

153
00:06:49,719 --> 00:06:51,729
someone else has their own address and

154
00:06:51,729 --> 00:06:53,979
private key and when you want to send

155
00:06:53,979 --> 00:06:55,959
them some bitcoins you just go into the

156
00:06:55,959 --> 00:06:58,419
blockchain select batches of bitcoins

157
00:06:58,419 --> 00:07:00,159
that you can unlock with your private

158
00:07:00,159 --> 00:07:03,969
key and then you will create a new batch

159
00:07:03,969 --> 00:07:06,099
of bitcoins locked the other person's

160
00:07:06,099 --> 00:07:08,409
address so that they can then send them

161
00:07:08,409 --> 00:07:12,129
on using their private key so again for

162
00:07:12,129 --> 00:07:13,449
example if they want to send this batch

163
00:07:13,449 --> 00:07:15,069
of bitcoins on to someone else they'll

164
00:07:15,069 --> 00:07:16,689
just use their private key to unlock

165
00:07:16,689 --> 00:07:18,339
this particular lock that we created for

166
00:07:18,339 --> 00:07:21,429
them and they'll send them on so as you

167
00:07:21,429 --> 00:07:23,949
can see bitcoins sort of form this chain

168
00:07:23,949 --> 00:07:26,469
of transactions as they move from one

169
00:07:26,469 --> 00:07:31,569
person to another up until now I've been

170
00:07:31,569 --> 00:07:33,999
calling these batches of bitcoins but

171
00:07:33,999 --> 00:07:36,459
their technical term is outputs so from

172
00:07:36,459 --> 00:07:37,929
now from here on out I'm gonna use the

173
00:07:37,929 --> 00:07:40,569
word output to describe what to call

174
00:07:40,569 --> 00:07:43,329
these batches of bitcoins so obviously

175
00:07:43,329 --> 00:07:45,159
all of these batches in here they are

176
00:07:45,159 --> 00:07:47,349
all called outputs that's what

177
00:07:47,349 --> 00:07:48,639
everything here all these orange boxes

178
00:07:48,639 --> 00:07:54,879
are outputs but to be clear when we

179
00:07:54,879 --> 00:07:57,239
refer to an output when we're spending

180
00:07:57,239 --> 00:08:00,609
an output in the transaction we refer to

181
00:08:00,609 --> 00:08:02,849
it as an input so every transaction

182
00:08:02,849 --> 00:08:07,619
takes an input and creates a new output

183
00:08:08,060 --> 00:08:10,110
what we do then we'll send that

184
00:08:10,110 --> 00:08:12,300
transaction into the Bitcoin network and

185
00:08:12,300 --> 00:08:15,509
hopefully it'll get mind onto the

186
00:08:15,509 --> 00:08:17,190
blockchain in a block so imagine this is

187
00:08:17,190 --> 00:08:19,169
a new block of transactions this is our

188
00:08:19,169 --> 00:08:20,910
transaction that got mind onto the pop

189
00:08:20,910 --> 00:08:23,400
chain and if we'd sort of visualize what

190
00:08:23,400 --> 00:08:28,139
just happened this output we spent so

191
00:08:28,139 --> 00:08:29,699
I've graded out it can't be spent again

192
00:08:29,699 --> 00:08:31,470
and in this new block

193
00:08:31,470 --> 00:08:35,250
thanks to my transaction I've created

194
00:08:35,250 --> 00:08:37,380
this new output this new output that

195
00:08:37,380 --> 00:08:41,070
belongs to this person here so that's

196
00:08:41,070 --> 00:08:42,750
how transactions work on a very basic

197
00:08:42,750 --> 00:08:49,470
level in the last example I sent an

198
00:08:49,470 --> 00:08:51,420
entire batch a whole batch of bitcoins

199
00:08:51,420 --> 00:08:54,300
and cry spent one a whole batch and

200
00:08:54,300 --> 00:08:57,060
create it and created ten bitcoins as

201
00:08:57,060 --> 00:08:59,490
the amount I'm sending but you don't

202
00:08:59,490 --> 00:09:02,250
actually have to use but what it sorry

203
00:09:02,250 --> 00:09:04,920
what if you want to send less than ten

204
00:09:04,920 --> 00:09:06,839
bitcoins so you have this batch ten

205
00:09:06,839 --> 00:09:08,820
wonder sound less well you can do that

206
00:09:08,820 --> 00:09:11,459
you create an output that sends you know

207
00:09:11,459 --> 00:09:14,580
a 10-8 to this person and but there's

208
00:09:14,580 --> 00:09:17,339
obviously two leftover so what you do is

209
00:09:17,339 --> 00:09:19,650
you will create another batch of

210
00:09:19,650 --> 00:09:24,570
bitcoins and as the change so we've

211
00:09:24,570 --> 00:09:27,779
taken this input here created an eight

212
00:09:27,779 --> 00:09:30,089
output from it this gets sent to this

213
00:09:30,089 --> 00:09:32,130
person and then we'll take care of our

214
00:09:32,130 --> 00:09:34,350
own change and we all lock that to an

215
00:09:34,350 --> 00:09:37,860
address that we own so that's how you

216
00:09:37,860 --> 00:09:39,959
take care of change you basically take

217
00:09:39,959 --> 00:09:41,070
care of your own change when you make a

218
00:09:41,070 --> 00:09:47,850
transaction up until now I've just been

219
00:09:47,850 --> 00:09:49,770
using whole round numbers of bitcoins

220
00:09:49,770 --> 00:09:51,990
but you can actually break bitcoins down

221
00:09:51,990 --> 00:09:55,380
into very small numbers so for example I

222
00:09:55,380 --> 00:09:57,360
could send them very small amounts and

223
00:09:57,360 --> 00:09:59,190
send myself the rest in change this is

224
00:09:59,190 --> 00:10:01,290
perfectly fine there's no you know real

225
00:10:01,290 --> 00:10:05,130
restrictions on odds no restrictions on

226
00:10:05,130 --> 00:10:08,370
breaking down the bitcoins this is the

227
00:10:08,370 --> 00:10:11,459
smallest unit of the currency is called

228
00:10:11,459 --> 00:10:14,010
when Satoshi and that is eight decimal

229
00:10:14,010 --> 00:10:17,040
places so this is how far you can break

230
00:10:17,040 --> 00:10:18,110
down a Bitcoin

231
00:10:18,110 --> 00:10:20,060
and can't break it down any further than

232
00:10:20,060 --> 00:10:22,090
that

233
00:10:23,500 --> 00:10:27,350
similarly say you have this batch of 10

234
00:10:27,350 --> 00:10:29,570
bitcoins here but you want to send 30

235
00:10:29,570 --> 00:10:33,250
bitcoins to someone what you can do

236
00:10:33,250 --> 00:10:35,810
instead of just creating two separate

237
00:10:35,810 --> 00:10:42,050
transactions if you own two well various

238
00:10:42,050 --> 00:10:45,260
outputs that belong to you you can

239
00:10:45,260 --> 00:10:47,120
collect them together as long as you can

240
00:10:47,120 --> 00:10:48,200
unlock them you can collect them

241
00:10:48,200 --> 00:10:51,770
together as inputs to create this much

242
00:10:51,770 --> 00:10:54,620
bigger output so there's no limit to how

243
00:10:54,620 --> 00:10:57,020
many inputs you can select from the

244
00:10:57,020 --> 00:10:59,450
blockchain in your transaction as long

245
00:10:59,450 --> 00:11:03,320
as you can unlock them that's fine and

246
00:11:03,320 --> 00:11:05,450
again this is ten and twenty five

247
00:11:05,450 --> 00:11:08,330
I sent thirty to this person so there's

248
00:11:08,330 --> 00:11:09,770
obviously five left over in this

249
00:11:09,770 --> 00:11:10,310
transaction

250
00:11:10,310 --> 00:11:12,200
so you want to take care of that as your

251
00:11:12,200 --> 00:11:14,840
own change so like I said with every

252
00:11:14,840 --> 00:11:16,820
transaction you have to take care of

253
00:11:16,820 --> 00:11:22,520
your own change and like before when

254
00:11:22,520 --> 00:11:24,200
this transaction gets mind onto the

255
00:11:24,200 --> 00:11:27,080
blockchain same again we all have this

256
00:11:27,080 --> 00:11:29,210
thirty output here lock to this person

257
00:11:29,210 --> 00:11:32,480
and then we'll have this output for

258
00:11:32,480 --> 00:11:34,310
ourselves that love to us and both of

259
00:11:34,310 --> 00:11:35,540
these that we selected from the

260
00:11:35,540 --> 00:11:37,400
blockchain have been greyed out because

261
00:11:37,400 --> 00:11:39,020
they've been spent in this transaction

262
00:11:39,020 --> 00:11:42,260
and that's how the blockchain and ISO

263
00:11:42,260 --> 00:11:47,960
transactions work in the blockchain so

264
00:11:47,960 --> 00:11:51,380
yeah so it's a quick question so in the

265
00:11:51,380 --> 00:11:53,810
last slide you're saying that one

266
00:11:53,810 --> 00:11:58,280
transaction can have inputs from

267
00:11:58,280 --> 00:12:00,560
multiple transactions exactly previous

268
00:12:00,560 --> 00:12:02,300
transactions okay you can have as many

269
00:12:02,300 --> 00:12:04,250
inputs as you want and create some in

270
00:12:04,250 --> 00:12:06,680
young boots do you like yep right and

271
00:12:06,680 --> 00:12:08,870
both these inputs need to be obviously

272
00:12:08,870 --> 00:12:11,510
owned by you yes right yes well I mean

273
00:12:11,510 --> 00:12:13,130
as long as you gonna lock them yes I

274
00:12:13,130 --> 00:12:14,210
mean if they're owned by you if you have

275
00:12:14,210 --> 00:12:16,010
the keys to unlock these that's fine

276
00:12:16,010 --> 00:12:18,350
yeah yeah the assumption is that if you

277
00:12:18,350 --> 00:12:23,030
have the keys they you Audion so okay so

278
00:12:23,030 --> 00:12:26,050
you can take multiple inputs from

279
00:12:26,050 --> 00:12:28,250
transactions that people have sent you

280
00:12:28,250 --> 00:12:31,340
let's say that three people sent me

281
00:12:31,340 --> 00:12:35,060
$5.00 each and I want to send someone 14

282
00:12:35,060 --> 00:12:38,480
yes I can use the inputs from do you see

283
00:12:38,480 --> 00:12:42,530
I can create one output for $14 and $1

284
00:12:42,530 --> 00:12:51,740
back to exactly right so that I just

285
00:12:51,740 --> 00:12:53,270
been showing you one individual

286
00:12:53,270 --> 00:12:55,250
transaction here this just you know is

287
00:12:55,250 --> 00:12:59,180
one individual transaction so if you

288
00:12:59,180 --> 00:13:01,630
were to go back in time and visualize

289
00:13:01,630 --> 00:13:04,010
all the transactions as they're being

290
00:13:04,010 --> 00:13:07,580
added to the blockchain so this is the

291
00:13:07,580 --> 00:13:11,420
first transaction here then we have

292
00:13:11,420 --> 00:13:14,030
another transaction that spends this

293
00:13:14,030 --> 00:13:16,730
output like so then we have another

294
00:13:16,730 --> 00:13:18,770
block transactions you have another

295
00:13:18,770 --> 00:13:21,290
transaction that gets spent and so on

296
00:13:21,290 --> 00:13:25,220
like this so with every new transaction

297
00:13:25,220 --> 00:13:28,370
that gets made it builds this sort of

298
00:13:28,370 --> 00:13:31,130
graph structure so like you asked just

299
00:13:31,130 --> 00:13:32,930
then you know you can take different

300
00:13:32,930 --> 00:13:35,540
outputs from different transactions and

301
00:13:35,540 --> 00:13:38,150
collect them together to create one

302
00:13:38,150 --> 00:13:42,580
single transaction but as you can see

303
00:13:42,580 --> 00:13:44,510
with every transaction they're all

304
00:13:44,510 --> 00:13:47,030
connected together and they create this

305
00:13:47,030 --> 00:13:50,030
straight chain of outputs so inputs

306
00:13:50,030 --> 00:13:55,640
outputs and so on and so on so when you

307
00:13:55,640 --> 00:13:57,530
make a Bitcoin transaction for yourself

308
00:13:57,530 --> 00:14:02,330
you just select any available outputs

309
00:14:02,330 --> 00:14:04,610
that you can spend from this graph in

310
00:14:04,610 --> 00:14:07,850
the blockchain and then you create new

311
00:14:07,850 --> 00:14:12,290
outputs from them so a single line a

312
00:14:12,290 --> 00:14:15,110
single transaction will have this effect

313
00:14:15,110 --> 00:14:20,810
on the Bitcoin transaction graph like so

314
00:14:20,810 --> 00:14:23,410
so this is probably the best way to

315
00:14:23,410 --> 00:14:25,580
visualize the blockchain

316
00:14:25,580 --> 00:14:26,990
I mean you could think of it as having

317
00:14:26,990 --> 00:14:30,470
just individual outputs but they are

318
00:14:30,470 --> 00:14:32,300
actually connected through series of

319
00:14:32,300 --> 00:14:35,060
transactions so the blockchain looks

320
00:14:35,060 --> 00:14:36,710
like this but obviously on a much much

321
00:14:36,710 --> 00:14:39,220
bigger scale

322
00:14:40,910 --> 00:14:43,800
these orange Oprah's here

323
00:14:43,800 --> 00:14:46,079
they haven't been spent yet so they're

324
00:14:46,079 --> 00:14:49,230
called unspent transaction outputs or

325
00:14:49,230 --> 00:14:52,740
they are referred to as Duty exo's so if

326
00:14:52,740 --> 00:14:54,839
you ever see the term UT exo's it's

327
00:14:54,839 --> 00:14:57,170
basically referring to these unspent

328
00:14:57,170 --> 00:15:00,120
bitcoins and these are important because

329
00:15:00,120 --> 00:15:04,470
these tend to get held in memory by your

330
00:15:04,470 --> 00:15:07,199
Bitcoin client so that there can be

331
00:15:07,199 --> 00:15:16,019
accessed more quickly coinbase so where

332
00:15:16,019 --> 00:15:19,709
do these original obviously with these

333
00:15:19,709 --> 00:15:21,300
transactions so far I've been referring

334
00:15:21,300 --> 00:15:23,850
to outputs that are already been made

335
00:15:23,850 --> 00:15:26,279
but where do these first ever bitcoins

336
00:15:26,279 --> 00:15:31,829
come from well with every block that

337
00:15:31,829 --> 00:15:34,500
gets mind onto the blockchain each block

338
00:15:34,500 --> 00:15:37,680
makes available a brand-new batch of

339
00:15:37,680 --> 00:15:39,510
bitcoins that a minor consent to

340
00:15:39,510 --> 00:15:41,399
themselves and this is called the block

341
00:15:41,399 --> 00:15:44,730
reward so when a minor mines a block

342
00:15:44,730 --> 00:15:48,110
they will send the block reward or

343
00:15:48,110 --> 00:15:50,399
create an output from the block reward

344
00:15:50,399 --> 00:15:52,949
and lock it to an address that they own

345
00:15:52,949 --> 00:15:56,760
and the way that they do this is in

346
00:15:56,760 --> 00:15:58,500
every single block of transactions a

347
00:15:58,500 --> 00:16:00,269
miner will construct a block of

348
00:16:00,269 --> 00:16:02,579
transactions but the very first

349
00:16:02,579 --> 00:16:04,170
transaction at the top of a block and

350
00:16:04,170 --> 00:16:06,480
that is a special transaction called the

351
00:16:06,480 --> 00:16:08,339
coinbase transaction and that is

352
00:16:08,339 --> 00:16:11,160
reserved for a miner and not and it it

353
00:16:11,160 --> 00:16:12,480
is through this coinbase transaction

354
00:16:12,480 --> 00:16:14,760
that a miner can collect the block

355
00:16:14,760 --> 00:16:18,000
reward so basically like like I said

356
00:16:18,000 --> 00:16:19,610
with every new block that gets added a

357
00:16:19,610 --> 00:16:22,980
miner will essentially create new

358
00:16:22,980 --> 00:16:25,170
bitcoins that did not exist before like

359
00:16:25,170 --> 00:16:27,350
so

360
00:16:27,690 --> 00:16:32,850
does that make sense yes so is it

361
00:16:32,850 --> 00:16:36,030
correct to say that you know the Bitcoin

362
00:16:36,030 --> 00:16:40,800
transaction tree the first level of the

363
00:16:40,800 --> 00:16:44,270
Bitcoin transaction tree consists of

364
00:16:44,270 --> 00:16:47,340
only coinbase transaction yes that that

365
00:16:47,340 --> 00:16:51,450
would be the route yeah yeah the first

366
00:16:51,450 --> 00:16:55,650
level ups like like every Bitcoin that's

367
00:16:55,650 --> 00:16:59,430
being spent today has its source to some

368
00:16:59,430 --> 00:17:01,500
coinbase transaction yes yes that's

369
00:17:01,500 --> 00:17:03,030
right so if you saw it in this graph on

370
00:17:03,030 --> 00:17:04,829
its site so this was at the bottom and

371
00:17:04,829 --> 00:17:06,540
all these transactions you're making

372
00:17:06,540 --> 00:17:08,700
they have a route going down to these

373
00:17:08,700 --> 00:17:14,490
source so you know that not all outputs

374
00:17:14,490 --> 00:17:16,020
are necessarily connected to each other

375
00:17:16,020 --> 00:17:18,569
but they will always be connected to a

376
00:17:18,569 --> 00:17:24,810
source block reward again yes finally in

377
00:17:24,810 --> 00:17:27,200
this first sort of basic introduction

378
00:17:27,200 --> 00:17:29,580
you probably might be interested in

379
00:17:29,580 --> 00:17:32,010
these transaction fees how they work so

380
00:17:32,010 --> 00:17:36,660
I'll cover that now when you make a

381
00:17:36,660 --> 00:17:40,260
transaction and if you want to put a fee

382
00:17:40,260 --> 00:17:44,190
on it well let me just start again

383
00:17:44,190 --> 00:17:45,420
basically when you make a transaction

384
00:17:45,420 --> 00:17:48,930
and if you want to put a fee on it you

385
00:17:48,930 --> 00:17:50,970
basically do not a user the whole amount

386
00:17:50,970 --> 00:17:53,760
that you're spending so this input is 10

387
00:17:53,760 --> 00:17:55,770
and if you created upwards of 8 until

388
00:17:55,770 --> 00:17:57,840
I'll be using the whole amount up but if

389
00:17:57,840 --> 00:18:00,510
you do not use it all up and so you

390
00:18:00,510 --> 00:18:02,850
create a remainder that remainder is the

391
00:18:02,850 --> 00:18:05,130
fee so when you wanna put a fee on a

392
00:18:05,130 --> 00:18:07,380
transaction you don't create a separate

393
00:18:07,380 --> 00:18:09,450
output for it you just leave a remainder

394
00:18:09,450 --> 00:18:13,710
of inputs they're not being used up

395
00:18:13,710 --> 00:18:16,830
so let's say this transaction has a fee

396
00:18:16,830 --> 00:18:18,720
of not point one bitcoins we'll send

397
00:18:18,720 --> 00:18:21,029
that into the network and eventually

398
00:18:21,029 --> 00:18:22,799
that'll hit come into the memory pools

399
00:18:22,799 --> 00:18:27,779
of all the nodes on the network so when

400
00:18:27,779 --> 00:18:30,690
you the reason you put a fee on a

401
00:18:30,690 --> 00:18:33,210
transaction is because a miner when they

402
00:18:33,210 --> 00:18:34,799
create a candidate block they can only

403
00:18:34,799 --> 00:18:38,730
fill it with a certain number of amount

404
00:18:38,730 --> 00:18:41,130
of transactions or certain size so

405
00:18:41,130 --> 00:18:42,600
basically used to be one megabytes worth

406
00:18:42,600 --> 00:18:45,059
of transactions the metric has changed

407
00:18:45,059 --> 00:18:48,390
to weight now but it's roughly about 1.7

408
00:18:48,390 --> 00:18:49,799
megabytes with the transactions at the

409
00:18:49,799 --> 00:18:52,500
moment so if there's more than 1.7

410
00:18:52,500 --> 00:18:54,240
megabytes in the memory pool of

411
00:18:54,240 --> 00:18:58,559
transactions a miner will select the

412
00:18:58,559 --> 00:19:00,140
transactions were the highest fees and

413
00:19:00,140 --> 00:19:04,200
the reason they do that is because so

414
00:19:04,200 --> 00:19:05,669
let's say these little yellow disks

415
00:19:05,669 --> 00:19:07,710
represent the fees use the highest fee

416
00:19:07,710 --> 00:19:09,720
transactions the reason they do that is

417
00:19:09,720 --> 00:19:11,820
because they can collect all these fees

418
00:19:11,820 --> 00:19:14,520
or recycle all of the remainder of these

419
00:19:14,520 --> 00:19:16,770
transactions into the coinbase

420
00:19:16,770 --> 00:19:19,620
transaction so instead of just sending

421
00:19:19,620 --> 00:19:21,600
themselves the the block reward which is

422
00:19:21,600 --> 00:19:24,870
currently 12.5 bitcoins to themselves in

423
00:19:24,870 --> 00:19:26,690
the climate transaction they will also

424
00:19:26,690 --> 00:19:29,000
include all the fees from the

425
00:19:29,000 --> 00:19:34,919
transactions they have included so there

426
00:19:34,919 --> 00:19:37,980
we are this block gets mined and this

427
00:19:37,980 --> 00:19:40,230
combination of that transaction recycles

428
00:19:40,230 --> 00:19:42,210
all the fees and creates a new batch of

429
00:19:42,210 --> 00:19:45,260
bitcoins with a block reward in it also

430
00:19:45,260 --> 00:19:48,720
does that make sense so far yes okay

431
00:19:48,720 --> 00:19:52,950
great so that's all the basics covered

432
00:19:52,950 --> 00:19:54,840
so that's all the structure of how

433
00:19:54,840 --> 00:19:56,399
transactions work like a visual

434
00:19:56,399 --> 00:19:58,200
representation you know taking inputs

435
00:19:58,200 --> 00:20:00,960
and creating outputs what I'm going to

436
00:20:00,960 --> 00:20:04,710
do now I'm gonna cover the data so if

437
00:20:04,710 --> 00:20:06,240
we're to look inside well basically how

438
00:20:06,240 --> 00:20:08,190
can you construct your own transactions

439
00:20:08,190 --> 00:20:10,960
from the data itself

440
00:20:10,960 --> 00:20:15,530
so this is gonna be a bit more technical

441
00:20:15,530 --> 00:20:17,450
so you know if you're not a technical

442
00:20:17,450 --> 00:20:19,910
person this should cover everything all

443
00:20:19,910 --> 00:20:21,680
that interesting you know end of the

444
00:20:21,680 --> 00:20:24,080
hood mechanics of transactions this is

445
00:20:24,080 --> 00:20:25,550
more for you know the programming and

446
00:20:25,550 --> 00:20:30,440
stuff right so the data this is the

447
00:20:30,440 --> 00:20:34,640
graph from before and so whereas before

448
00:20:34,640 --> 00:20:36,440
I had that green line to represent the

449
00:20:36,440 --> 00:20:38,540
data this black box here is like my

450
00:20:38,540 --> 00:20:40,460
editor we're kinda going to create a

451
00:20:40,460 --> 00:20:44,150
transaction can scratch so with every

452
00:20:44,150 --> 00:20:46,100
transaction the first thing it starts

453
00:20:46,100 --> 00:20:49,070
with is a version number not just sort

454
00:20:49,070 --> 00:20:50,510
of describes the structure of the

455
00:20:50,510 --> 00:20:52,580
outcome in transaction and that is

456
00:20:52,580 --> 00:20:54,590
currently one I'm pretty sure the

457
00:20:54,590 --> 00:20:57,560
majority of transactions use the version

458
00:20:57,560 --> 00:20:59,180
number one so to put the one in there

459
00:20:59,180 --> 00:21:04,510
and that's fine but because this is a

460
00:21:04,510 --> 00:21:06,650
transaction data it has a specific

461
00:21:06,650 --> 00:21:10,130
structure so this version number it's

462
00:21:10,130 --> 00:21:14,450
actually four bytes long so this version

463
00:21:14,450 --> 00:21:16,520
field sorry is four bytes long so we put

464
00:21:16,520 --> 00:21:17,690
the one in there but we need a paddle

465
00:21:17,690 --> 00:21:19,250
that with zeros so that's four bytes

466
00:21:19,250 --> 00:21:22,550
long and two characters is equal to one

467
00:21:22,550 --> 00:21:25,010
byte so this is eight characters long

468
00:21:25,010 --> 00:21:28,220
and that's four bytes the reason we have

469
00:21:28,220 --> 00:21:30,530
these sort of field sizes is well

470
00:21:30,530 --> 00:21:32,510
basically everything in the transaction

471
00:21:32,510 --> 00:21:36,980
has his own field site field size so

472
00:21:36,980 --> 00:21:38,240
that makes it easier to run through the

473
00:21:38,240 --> 00:21:43,580
transaction and decode yet secondly as

474
00:21:43,580 --> 00:21:45,050
well as being four bytes long it has to

475
00:21:45,050 --> 00:21:48,110
be X decimal so this is counting one so

476
00:21:48,110 --> 00:21:49,340
that's the same in hexadecimal

477
00:21:49,340 --> 00:21:53,570
and lastly probably most Awkward and

478
00:21:53,570 --> 00:21:56,390
from a human from a human perspective is

479
00:21:56,390 --> 00:21:58,520
that this data has to be a network byte

480
00:21:58,520 --> 00:22:00,890
byte order so you have to reverse the

481
00:22:00,890 --> 00:22:03,670
order of the bytes

482
00:22:05,479 --> 00:22:07,519
so that's the vision don't ask the first

483
00:22:07,519 --> 00:22:09,859
part second of all you have to put an

484
00:22:09,859 --> 00:22:12,889
input count so you have to say how many

485
00:22:12,889 --> 00:22:16,190
inputs we're going to be using in this

486
00:22:16,190 --> 00:22:18,320
transaction so if you had you know three

487
00:22:18,320 --> 00:22:21,349
we have got three in here in this one

488
00:22:21,349 --> 00:22:22,849
I'm just gonna use one output so I put

489
00:22:22,849 --> 00:22:24,769
the number one in there and this is one

490
00:22:24,769 --> 00:22:31,209
byte long however this is a special

491
00:22:31,209 --> 00:22:35,809
field called a variable integer and what

492
00:22:35,809 --> 00:22:38,389
that me or reduced or shortened to

493
00:22:38,389 --> 00:22:40,249
variant I think that's a technical term

494
00:22:40,249 --> 00:22:41,749
Freud I think it's sometimes called

495
00:22:41,749 --> 00:22:44,869
compact size but variable integer and

496
00:22:44,869 --> 00:22:48,729
variant is why I've been used to if this

497
00:22:48,729 --> 00:22:51,979
if the number of outputs you want to

498
00:22:51,979 --> 00:22:55,909
select is less than 252 or in other

499
00:22:55,909 --> 00:22:59,629
words in hexadecimal FC then you just

500
00:22:59,629 --> 00:23:02,149
leave as one byte so you just put it in

501
00:23:02,149 --> 00:23:04,159
there here but what if you want to send

502
00:23:04,159 --> 00:23:07,789
more than 200 we want to clack together

503
00:23:07,789 --> 00:23:12,169
more than 250 two inputs like so so

504
00:23:12,169 --> 00:23:14,599
greater than this but less than these

505
00:23:14,599 --> 00:23:17,389
four characters then you just prepend

506
00:23:17,389 --> 00:23:20,989
the letter F D to the front and then the

507
00:23:20,989 --> 00:23:24,709
next two bytes tell you how many inputs

508
00:23:24,709 --> 00:23:27,859
you using obviously in hexadecimal same

509
00:23:27,859 --> 00:23:29,959
again if you want do more than two bytes

510
00:23:29,959 --> 00:23:31,669
worth the cut you know a number that

511
00:23:31,669 --> 00:23:33,649
can't be held in two bites you prepend

512
00:23:33,649 --> 00:23:36,649
it with Fe and that gives you that means

513
00:23:36,649 --> 00:23:38,329
the next four bytes tell you the I've

514
00:23:38,329 --> 00:23:41,119
come in number of inputs and if it's

515
00:23:41,119 --> 00:23:42,379
even bigger that bigger than that again

516
00:23:42,379 --> 00:23:45,019
and then you yeah I think that's I don't

517
00:23:45,019 --> 00:23:46,579
think this is actually possible but it's

518
00:23:46,579 --> 00:23:49,429
used another P other places you just

519
00:23:49,429 --> 00:23:51,679
prepended with FF and the next eight

520
00:23:51,679 --> 00:23:53,479
bytes tell you how many inputs you want

521
00:23:53,479 --> 00:23:55,999
to collect together but for the vast

522
00:23:55,999 --> 00:23:57,589
majority of transactions you probably

523
00:23:57,589 --> 00:23:58,489
you're not going to be correcting

524
00:23:58,489 --> 00:24:00,289
together if you constructing them

525
00:24:00,289 --> 00:24:01,380
yourself

526
00:24:01,380 --> 00:24:03,299
you know you probably be using just one

527
00:24:03,299 --> 00:24:05,250
bite so the majority of the time this

528
00:24:05,250 --> 00:24:08,900
input field is one byte in size

529
00:24:08,960 --> 00:24:12,690
okay that's probably all the most

530
00:24:12,690 --> 00:24:14,850
technical part then now we just move on

531
00:24:14,850 --> 00:24:16,110
to the inputs this is should be a bit

532
00:24:16,110 --> 00:24:21,360
simpler so an input we have to select an

533
00:24:21,360 --> 00:24:24,059
input from the blockchain so the way we

534
00:24:24,059 --> 00:24:26,610
do that is first of all we need to get

535
00:24:26,610 --> 00:24:29,429
the transaction ID so every transaction

536
00:24:29,429 --> 00:24:32,460
has its own unique ID number koala

537
00:24:32,460 --> 00:24:34,440
transaction ID and you just shove that

538
00:24:34,440 --> 00:24:38,390
that's the first part of this input code

539
00:24:38,390 --> 00:24:42,470
to select it and that is 32 bytes long

540
00:24:42,470 --> 00:24:44,880
it's also gonna be hexadecimal X dot

541
00:24:44,880 --> 00:24:47,070
small ready and also again it's got to

542
00:24:47,070 --> 00:24:49,830
be network byte order so reverse this so

543
00:24:49,830 --> 00:24:52,260
if you just select this and input it

544
00:24:52,260 --> 00:24:54,419
into a blockchain Explorer you can be

545
00:24:54,419 --> 00:24:56,909
able to find it because it's been

546
00:24:56,909 --> 00:24:58,740
reversed if you just reverse it back and

547
00:24:58,740 --> 00:25:01,289
you'll be able to find it in a block

548
00:25:01,289 --> 00:25:05,010
Explorer so that gives you the

549
00:25:05,010 --> 00:25:07,520
transaction but we want a specific

550
00:25:07,520 --> 00:25:11,669
specific output so a transaction like I

551
00:25:11,669 --> 00:25:12,780
showed you earlier it can create

552
00:25:12,780 --> 00:25:15,570
multiple outputs so what you do you just

553
00:25:15,570 --> 00:25:19,559
use the V out which is short for vector

554
00:25:19,559 --> 00:25:21,780
output and so each of these outputs

555
00:25:21,780 --> 00:25:24,360
start from 0 has their own number so

556
00:25:24,360 --> 00:25:27,450
this one has just one output so I put 0

557
00:25:27,450 --> 00:25:30,110
here but again that's 4 bytes long

558
00:25:30,110 --> 00:25:34,100
hexadecimal and my daughter

559
00:25:34,580 --> 00:25:38,280
next up the next major part so basically

560
00:25:38,280 --> 00:25:41,340
we've gone yep so yeah just a quick

561
00:25:41,340 --> 00:25:44,630
question yes let's say that we had

562
00:25:44,630 --> 00:25:48,690
multiple transactions multiple outputs

563
00:25:48,690 --> 00:25:51,150
from multiple transactions that's that

564
00:25:51,150 --> 00:25:54,030
is possible right so let's say we have

565
00:25:54,030 --> 00:25:57,360
two transactions and two outputs each

566
00:25:57,360 --> 00:25:59,850
from each of those transactions so in

567
00:25:59,850 --> 00:26:04,230
the Z row one would become 0 for write

568
00:26:04,230 --> 00:26:11,490
the inputs field the the this the one

569
00:26:11,490 --> 00:26:14,130
before that the one in poker

570
00:26:14,130 --> 00:26:17,280
yes input count will become yeah 4 mm 8

571
00:26:17,280 --> 00:26:20,030
- how many inputs we using all

572
00:26:20,030 --> 00:26:24,630
transactions yeah yes yes yes and then

573
00:26:24,630 --> 00:26:27,780
would we list out all the transaction

574
00:26:27,780 --> 00:26:30,240
IDs which are the two one after the

575
00:26:30,240 --> 00:26:30,630
other

576
00:26:30,630 --> 00:26:32,610
okay yeah so what would happen is so you

577
00:26:32,610 --> 00:26:34,049
wanted to select two different outputs

578
00:26:34,049 --> 00:26:37,700
and exactly this one here this code here

579
00:26:37,700 --> 00:26:40,350
this is for we're not single output so

580
00:26:40,350 --> 00:26:42,840
if you if you had to you would just

581
00:26:42,840 --> 00:26:49,770
repeat this after this okay so there we

582
00:26:49,770 --> 00:26:51,659
are so we've selected this particular

583
00:26:51,659 --> 00:26:53,460
output from this transaction so the

584
00:26:53,460 --> 00:26:54,480
transaction ID gives you this

585
00:26:54,480 --> 00:26:56,309
transaction review out the particular

586
00:26:56,309 --> 00:27:00,900
button so that's referenced this output

587
00:27:00,900 --> 00:27:02,909
successfully but obviously it has a lock

588
00:27:02,909 --> 00:27:05,580
on it and to be able to spend this and

589
00:27:05,580 --> 00:27:07,140
send it on to another person you have to

590
00:27:07,140 --> 00:27:10,890
be able to unlock it but in Bitcoin

591
00:27:10,890 --> 00:27:12,780
transactions you actually have to

592
00:27:12,780 --> 00:27:15,360
construct the whole structure of the

593
00:27:15,360 --> 00:27:18,510
transaction before you unlock it so I'm

594
00:27:18,510 --> 00:27:19,950
gonna skip that for now and leave this

595
00:27:19,950 --> 00:27:22,590
blank this and this is called a script

596
00:27:22,590 --> 00:27:24,360
sig because you need to put your

597
00:27:24,360 --> 00:27:26,820
signature here and all the code in here

598
00:27:26,820 --> 00:27:28,770
will be what's called a script because

599
00:27:28,770 --> 00:27:30,270
it had his own soft scripting language

600
00:27:30,270 --> 00:27:33,720
it's just called a script second but if

601
00:27:33,720 --> 00:27:35,010
you want to give it a more friendly name

602
00:27:35,010 --> 00:27:39,600
you can call it unlocking code lastly

603
00:27:39,600 --> 00:27:44,100
each importer has a sequence number this

604
00:27:44,100 --> 00:27:46,470
isn't use very often I have never used

605
00:27:46,470 --> 00:27:51,090
myself but if you set this to a lower

606
00:27:51,090 --> 00:27:52,679
number than the maximum possible number

607
00:27:52,679 --> 00:27:55,950
it means that you can replace the

608
00:27:55,950 --> 00:27:58,169
transaction later on sir so you put a

609
00:27:58,169 --> 00:28:00,330
very low fee on this you can create a

610
00:28:00,330 --> 00:28:02,130
new transaction with a higher sequence

611
00:28:02,130 --> 00:28:04,740
number and it will be able to replace

612
00:28:04,740 --> 00:28:06,200
the one that's already on the network

613
00:28:06,200 --> 00:28:10,080
I've not done this myself so basically I

614
00:28:10,080 --> 00:28:11,460
always set this to the maximum value of

615
00:28:11,460 --> 00:28:13,770
all F's because that's the maximum

616
00:28:13,770 --> 00:28:17,580
excess hexadecimal value so yeah I'll

617
00:28:17,580 --> 00:28:18,870
just move on from there I usually just

618
00:28:18,870 --> 00:28:21,370
set this to all FS

619
00:28:21,370 --> 00:28:24,350
so that's when input done like you said

620
00:28:24,350 --> 00:28:25,850
earlier if you want to select another

621
00:28:25,850 --> 00:28:27,290
input I would just repeat this whole

622
00:28:27,290 --> 00:28:29,660
process just after this piece of code

623
00:28:29,660 --> 00:28:33,950
because you said to here you can parse

624
00:28:33,950 --> 00:28:34,990
it fast me

625
00:28:34,990 --> 00:28:37,400
next up so that's the input done we've

626
00:28:37,400 --> 00:28:38,930
selected this and I want to create some

627
00:28:38,930 --> 00:28:42,560
outputs from it seems can I same again

628
00:28:42,560 --> 00:28:44,330
this is a variable integer so if you

629
00:28:44,330 --> 00:28:46,070
wanted to you know quick lots of our

630
00:28:46,070 --> 00:28:48,500
words more than two hundred fifty two or

631
00:28:48,500 --> 00:28:50,540
whatever you just use the available

632
00:28:50,540 --> 00:28:52,430
integer code but because I'm only using

633
00:28:52,430 --> 00:28:55,270
two here I can it fits inside one byte

634
00:28:55,270 --> 00:28:57,680
and the reason for this I didn't mention

635
00:28:57,680 --> 00:28:59,240
earlier it's just a saw safe space in

636
00:28:59,240 --> 00:29:01,400
the in the data so that you can use that

637
00:29:01,400 --> 00:29:05,420
use that data way possible so an output

638
00:29:05,420 --> 00:29:08,840
this has a doin structure as well first

639
00:29:08,840 --> 00:29:11,030
of all you put the value how many

640
00:29:11,030 --> 00:29:13,490
bitcoins you want to send but you don't

641
00:29:13,490 --> 00:29:14,780
put it the Bitcoin amount you put the

642
00:29:14,780 --> 00:29:18,740
Satoshi's amount so say I want to send I

643
00:29:18,740 --> 00:29:20,300
think this is about no point naught to

644
00:29:20,300 --> 00:29:23,030
bitcoins you have to put into Satoshi's

645
00:29:23,030 --> 00:29:26,570
so the smallest possible unit so that's

646
00:29:26,570 --> 00:29:28,880
the first part for this output that has

647
00:29:28,880 --> 00:29:31,220
to be an actual decimal it has to be 8

648
00:29:31,220 --> 00:29:32,960
bytes now eight of bytes long this one

649
00:29:32,960 --> 00:29:36,500
and also in Reverse by daughter so when

650
00:29:36,500 --> 00:29:38,740
you look through code this looks like

651
00:29:38,740 --> 00:29:41,630
gobbledygook but if you just reverse the

652
00:29:41,630 --> 00:29:43,730
byte order and convert it to decimal it

653
00:29:43,730 --> 00:29:47,000
will give you the amount after that then

654
00:29:47,000 --> 00:29:50,210
after that this is yeah you mentioned

655
00:29:50,210 --> 00:29:53,150
missus eight bytes long so this tells me

656
00:29:53,150 --> 00:29:55,100
that there is probably some kind of

657
00:29:55,100 --> 00:29:58,880
limit to how much you can send in one

658
00:29:58,880 --> 00:30:01,700
transaction is that eight bytes

659
00:30:01,700 --> 00:30:03,470
hexadecimal I think is a very very large

660
00:30:03,470 --> 00:30:06,440
number I have a story idea that's that

661
00:30:06,440 --> 00:30:09,470
yeah I don't know I think I think you

662
00:30:09,470 --> 00:30:13,460
should cover most cases but it would be

663
00:30:13,460 --> 00:30:16,060
a good problem to have

664
00:30:17,500 --> 00:30:22,730
so after we've set the amount the next

665
00:30:22,730 --> 00:30:24,170
part then simple enough you just have to

666
00:30:24,170 --> 00:30:27,280
put the lock on it so again this has a

667
00:30:27,280 --> 00:30:30,440
the locks they have their own sort of

668
00:30:30,440 --> 00:30:32,240
scripting language too and they can be a

669
00:30:32,240 --> 00:30:34,450
very varied size

670
00:30:34,450 --> 00:30:36,159
so because they can vary in size then

671
00:30:36,159 --> 00:30:37,450
they don't have a set size you know like

672
00:30:37,450 --> 00:30:38,980
the transaction IDs or the version

673
00:30:38,980 --> 00:30:40,690
numbers we have to use this very

674
00:30:40,690 --> 00:30:42,330
variable integer again

675
00:30:42,330 --> 00:30:45,970
so most signatures typical signatures

676
00:30:45,970 --> 00:30:50,679
are about 19 I think that's 25 in

677
00:30:50,679 --> 00:30:53,619
decimal 25 bytes so this just tells you

678
00:30:53,619 --> 00:30:58,869
the upcoming size of the lock so you put

679
00:30:58,869 --> 00:31:00,759
the lock in there

680
00:31:00,759 --> 00:31:04,720
again this is full of some code that

681
00:31:04,720 --> 00:31:06,639
creates a script that locks it to a

682
00:31:06,639 --> 00:31:10,359
particular address so this is the

683
00:31:10,359 --> 00:31:13,269
address we've locked it to we've used

684
00:31:13,269 --> 00:31:16,869
the public key in here so I'm not gonna

685
00:31:16,869 --> 00:31:20,279
cover this too deeply but this code here

686
00:31:20,279 --> 00:31:22,029
corresponds to this particular address

687
00:31:22,029 --> 00:31:25,659
and these great things here they're just

688
00:31:25,659 --> 00:31:28,359
the locking codes the codes that lock it

689
00:31:28,359 --> 00:31:31,090
to this particular public key so if you

690
00:31:31,090 --> 00:31:32,769
wanted to create your own lock you can

691
00:31:32,769 --> 00:31:36,190
pretty much copy and paste this code

692
00:31:36,190 --> 00:31:38,289
here and just replace this public key

693
00:31:38,289 --> 00:31:41,830
with the public key of the person you

694
00:31:41,830 --> 00:31:43,809
want to send it to and this public key

695
00:31:43,809 --> 00:31:48,999
can be derived from this address so this

696
00:31:48,999 --> 00:31:51,129
locking code is obviously it will be

697
00:31:51,129 --> 00:31:54,059
different for different public right

698
00:31:54,059 --> 00:31:57,429
7609 encoding will change in a typical

699
00:31:57,429 --> 00:31:59,639
transaction is just this green part here

700
00:31:59,639 --> 00:32:03,759
this 76 a 914 a a C they refer to

701
00:32:03,759 --> 00:32:05,799
specific codes in the script and that

702
00:32:05,799 --> 00:32:07,600
basically basically basically just says

703
00:32:07,600 --> 00:32:10,690
when this address has been this output

704
00:32:10,690 --> 00:32:12,100
has been locked to this product public

705
00:32:12,100 --> 00:32:14,109
key and if you want to send it on I'll

706
00:32:14,109 --> 00:32:20,799
have to provide a signature this is

707
00:32:20,799 --> 00:32:25,559
basically the script that will run like

708
00:32:25,559 --> 00:32:27,909
you know you put it on the stack you

709
00:32:27,909 --> 00:32:32,769
check if it's equal are these I am

710
00:32:32,769 --> 00:32:34,570
Clawson oh yeah these are the op codes

711
00:32:34,570 --> 00:32:37,509
these refer to ask o P duplicates trust

712
00:32:37,509 --> 00:32:39,249
me I'm glossing over these because I

713
00:32:39,249 --> 00:32:42,279
think a signet the script the code

714
00:32:42,279 --> 00:32:44,450
deserved its own video to be explained

715
00:32:44,450 --> 00:32:48,379
yeah yeah so that's the locking code

716
00:32:48,379 --> 00:32:50,960
there I don't expect you to understand

717
00:32:50,960 --> 00:32:55,669
it's just yet and like before like you

718
00:32:55,669 --> 00:32:58,580
asked earlier because I said two outputs

719
00:32:58,580 --> 00:33:03,980
I just create another output here with

720
00:33:03,980 --> 00:33:06,320
the same structure as last time so this

721
00:33:06,320 --> 00:33:08,419
part here that's the amount I'm sending

722
00:33:08,419 --> 00:33:11,389
and then this is the size of this

723
00:33:11,389 --> 00:33:14,659
upcoming locking code and this is the

724
00:33:14,659 --> 00:33:16,190
actual locking code with a different

725
00:33:16,190 --> 00:33:18,230
address so as you can see this ends in

726
00:33:18,230 --> 00:33:20,359
8/8 AC just like that one and it starts

727
00:33:20,359 --> 00:33:24,859
with seven six eight nine so there we

728
00:33:24,859 --> 00:33:25,009
are

729
00:33:25,009 --> 00:33:26,720
so all has been changed here is the

730
00:33:26,720 --> 00:33:32,239
address that I'm rocking it to and then

731
00:33:32,239 --> 00:33:33,950
lastly we have what's called the lock

732
00:33:33,950 --> 00:33:35,809
time this is the final part of the

733
00:33:35,809 --> 00:33:38,929
transaction and the lock time basically

734
00:33:38,929 --> 00:33:41,090
allows you to solve post date the

735
00:33:41,090 --> 00:33:44,149
transaction so if you put a lock time in

736
00:33:44,149 --> 00:33:47,570
here of less than 500 million then

737
00:33:47,570 --> 00:33:49,460
that's referring to a particular block

738
00:33:49,460 --> 00:33:51,649
height so if you went back in time and

739
00:33:51,649 --> 00:33:54,320
we said we have company at the block 14

740
00:33:54,320 --> 00:33:56,629
and we put the lock time of 16 in here

741
00:33:56,629 --> 00:33:58,609
then that means that this transaction

742
00:33:58,609 --> 00:34:03,590
can only be mined after the by the block

743
00:34:03,590 --> 00:34:06,700
height which is 16 or greater

744
00:34:07,389 --> 00:34:10,699
similarly if you were to put the lock

745
00:34:10,699 --> 00:34:12,859
time of greater than 500 million so this

746
00:34:12,859 --> 00:34:14,960
500 million here accounts that I've you

747
00:34:14,960 --> 00:34:16,909
know up to five hundred millions five

748
00:34:16,909 --> 00:34:18,770
hundred million worth of blocks it was

749
00:34:18,770 --> 00:34:19,550
greater than that

750
00:34:19,550 --> 00:34:21,469
then that means that you are specifying

751
00:34:21,469 --> 00:34:23,960
a particular unix time which is just the

752
00:34:23,960 --> 00:34:25,280
number of seconds since the first

753
00:34:25,280 --> 00:34:29,330
january 1970 but either way this lock

754
00:34:29,330 --> 00:34:32,960
time locks the transaction up until a

755
00:34:32,960 --> 00:34:35,179
specific block or a specific point in

756
00:34:35,179 --> 00:34:38,449
time but if you don't use it which you

757
00:34:38,449 --> 00:34:42,050
probably don't it's really used just set

758
00:34:42,050 --> 00:34:44,060
it to zero so that means it can be mined

759
00:34:44,060 --> 00:34:47,889
immediately and there we have a

760
00:34:47,889 --> 00:34:52,790
transaction so just to go over it again

761
00:34:52,790 --> 00:34:55,099
it has four main parts you have a

762
00:34:55,099 --> 00:34:58,700
version number usually one so just

763
00:34:58,700 --> 00:35:01,130
usually one then you have the inputs you

764
00:35:01,130 --> 00:35:03,920
just select an input I haven't covered

765
00:35:03,920 --> 00:35:06,080
the unlocking code yet we will come back

766
00:35:06,080 --> 00:35:08,420
to that and after the inputs you have

767
00:35:08,420 --> 00:35:10,280
the outputs create the outputs from it

768
00:35:10,280 --> 00:35:12,530
and then you have a lock time and those

769
00:35:12,530 --> 00:35:14,960
are the four major parts of any

770
00:35:14,960 --> 00:35:17,589
transaction

771
00:35:17,660 --> 00:35:22,089
and some extensive oh yes okay

772
00:35:22,089 --> 00:35:24,619
going into the final part now of these

773
00:35:24,619 --> 00:35:27,019
slides I'm gonna cover this actual

774
00:35:27,019 --> 00:35:28,700
signing to click the signature to be

775
00:35:28,700 --> 00:35:31,640
able to unlock this output here this

776
00:35:31,640 --> 00:35:34,640
input in this part I'm definitely gonna

777
00:35:34,640 --> 00:35:37,309
go through some things very fast and I'm

778
00:35:37,309 --> 00:35:38,269
not gonna be able to explain them in

779
00:35:38,269 --> 00:35:39,740
time because I think sign in itself

780
00:35:39,740 --> 00:35:42,769
probably deserves some video but just in

781
00:35:42,769 --> 00:35:44,599
case your I know re watching this video

782
00:35:44,599 --> 00:35:47,269
and you want to you're building your own

783
00:35:47,269 --> 00:35:50,059
transactions from scratch and I just

784
00:35:50,059 --> 00:35:51,200
want to cover everything that you need

785
00:35:51,200 --> 00:35:52,750
to do to be able to create the signature

786
00:35:52,750 --> 00:35:57,380
just sign this transaction so be with me

787
00:35:57,380 --> 00:35:59,269
if everything doesn't make sense don't

788
00:35:59,269 --> 00:36:02,690
worry maybe it will when you come back

789
00:36:02,690 --> 00:36:07,670
to it so so we have this transaction and

790
00:36:07,670 --> 00:36:09,500
we have this input that we need to

791
00:36:09,500 --> 00:36:11,990
unlock so this has been locked to our

792
00:36:11,990 --> 00:36:16,400
address and we have our private key that

793
00:36:16,400 --> 00:36:21,170
corresponds to this address and we need

794
00:36:21,170 --> 00:36:23,000
to use the private key to basically

795
00:36:23,000 --> 00:36:25,430
prove that we are the owner of this

796
00:36:25,430 --> 00:36:28,940
address so about what you're doing this

797
00:36:28,940 --> 00:36:31,009
or very simple and bad way of doing this

798
00:36:31,009 --> 00:36:33,740
would be just to shove your private key

799
00:36:33,740 --> 00:36:37,369
into a transaction I mean that would

800
00:36:37,369 --> 00:36:38,720
prove that you know that you have the

801
00:36:38,720 --> 00:36:40,759
private key but the problem of that is

802
00:36:40,759 --> 00:36:42,289
when you send this into the network you

803
00:36:42,289 --> 00:36:43,819
basically given your private key to

804
00:36:43,819 --> 00:36:45,410
everyone on the network because your

805
00:36:45,410 --> 00:36:47,329
private key has been exposed so if you

806
00:36:47,329 --> 00:36:49,519
had any other outputs that were locked

807
00:36:49,519 --> 00:36:51,950
to this address they can use a private

808
00:36:51,950 --> 00:36:54,589
key to unlock them and spend them or

809
00:36:54,589 --> 00:36:56,359
they could just not relay this

810
00:36:56,359 --> 00:36:57,769
transaction they could just take your

811
00:36:57,769 --> 00:36:59,269
private key and create a new transaction

812
00:36:59,269 --> 00:37:03,410
and send it to their own addresses so

813
00:37:03,410 --> 00:37:05,839
that's bad so we need like a more

814
00:37:05,839 --> 00:37:08,390
intelligent way of using our private key

815
00:37:08,390 --> 00:37:11,509
to unlock this lock to prove that we own

816
00:37:11,509 --> 00:37:13,940
this address without actually giving

817
00:37:13,940 --> 00:37:16,279
away the private key itself and that's

818
00:37:16,279 --> 00:37:18,079
where signing comes in using digital

819
00:37:18,079 --> 00:37:19,880
signatures

820
00:37:19,880 --> 00:37:22,740
so like I says this private this private

821
00:37:22,740 --> 00:37:24,450
key and address there actually create

822
00:37:24,450 --> 00:37:27,000
connected the address is actually

823
00:37:27,000 --> 00:37:30,810
created from your private key I'm not

824
00:37:30,810 --> 00:37:32,070
going to cover how that works now but

825
00:37:32,070 --> 00:37:34,410
they are connected through some

826
00:37:34,410 --> 00:37:40,710
mathematics using an elliptic curve so

827
00:37:40,710 --> 00:37:41,820
what you can do because these are

828
00:37:41,820 --> 00:37:44,150
connected with an elliptic curve you can

829
00:37:44,150 --> 00:37:48,810
use some more mathematics to create a

830
00:37:48,810 --> 00:37:51,560
signature from your private key that'll

831
00:37:51,560 --> 00:37:53,970
prove that we'll be able to unlock this

832
00:37:53,970 --> 00:37:55,800
address so I'll just run through it

833
00:37:55,800 --> 00:37:57,480
quickly what you do to create a digital

834
00:37:57,480 --> 00:38:00,180
signature for this transaction is you

835
00:38:00,180 --> 00:38:02,370
take the private key along with the

836
00:38:02,370 --> 00:38:04,430
transaction that you want to sign and

837
00:38:04,430 --> 00:38:08,490
you'll put it into this addictive well

838
00:38:08,490 --> 00:38:10,470
you use some elliptic curve mathematics

839
00:38:10,470 --> 00:38:13,790
and that will give you a signature and

840
00:38:13,790 --> 00:38:16,320
so currently yeah currently the

841
00:38:16,320 --> 00:38:21,360
right-hand side input has just the

842
00:38:21,360 --> 00:38:23,310
information that is there on the screen

843
00:38:23,310 --> 00:38:27,030
right yeah like it's still the gap is

844
00:38:27,030 --> 00:38:30,840
still there right yes so what happened

845
00:38:30,840 --> 00:38:32,700
then you've used this of you know

846
00:38:32,700 --> 00:38:34,950
unsigned transaction and you put it into

847
00:38:34,950 --> 00:38:37,110
this function along with this your

848
00:38:37,110 --> 00:38:38,460
private key and that will give you a

849
00:38:38,460 --> 00:38:40,410
signature so this is a signature that

850
00:38:40,410 --> 00:38:44,040
will get put into the transaction there

851
00:38:44,040 --> 00:38:45,660
we are

852
00:38:45,660 --> 00:38:47,790
I've simplified this a little bit so

853
00:38:47,790 --> 00:38:48,840
this is probably the part that you want

854
00:38:48,840 --> 00:38:51,720
to gloss over because it's hard to keep

855
00:38:51,720 --> 00:38:53,040
up but I'm just just in case you're

856
00:38:53,040 --> 00:38:55,590
watching this with a technical mind or

857
00:38:55,590 --> 00:38:58,140
actual actually doing it what you need

858
00:38:58,140 --> 00:39:01,740
to do is first of all when you want to

859
00:39:01,740 --> 00:39:03,180
sign a transaction you have to kick out

860
00:39:03,180 --> 00:39:04,890
any existing signatures in there so if

861
00:39:04,890 --> 00:39:07,470
you've already signed and an input take

862
00:39:07,470 --> 00:39:10,470
out the signatures what you do then you

863
00:39:10,470 --> 00:39:13,080
need to put a placeholder some

864
00:39:13,080 --> 00:39:16,410
placeholder code in to where the script

865
00:39:16,410 --> 00:39:19,020
sig is going to be and that placeholder

866
00:39:19,020 --> 00:39:23,820
cone is the locking code or the script

867
00:39:23,820 --> 00:39:25,950
pub key of the input that we're trying

868
00:39:25,950 --> 00:39:27,720
to unlock this is just a placeholder so

869
00:39:27,720 --> 00:39:29,559
we know which input to sign

870
00:39:29,559 --> 00:39:32,480
wait till then you append what's called

871
00:39:32,480 --> 00:39:34,970
a sig hash type to the end of the

872
00:39:34,970 --> 00:39:38,239
transaction data not entirely sure what

873
00:39:38,239 --> 00:39:41,989
this used for but for typical signatures

874
00:39:41,989 --> 00:39:43,640
you just put number one this obviously a

875
00:39:43,640 --> 00:39:45,380
network byte or byte order and it's four

876
00:39:45,380 --> 00:39:45,980
bytes long

877
00:39:45,980 --> 00:39:48,619
then you hash all that together twice

878
00:39:48,619 --> 00:39:51,230
through hash two five six and that'll

879
00:39:51,230 --> 00:39:52,099
give you this

880
00:39:52,099 --> 00:39:54,980
digest which is the message and that's

881
00:39:54,980 --> 00:40:01,489
what goes into this elliptic curve then

882
00:40:01,489 --> 00:40:03,289
that'll spit out a signature that you

883
00:40:03,289 --> 00:40:05,690
have to have this in a de are encoded

884
00:40:05,690 --> 00:40:10,670
format and your I think most libraries

885
00:40:10,670 --> 00:40:12,890
will have you give this option of

886
00:40:12,890 --> 00:40:15,769
encoding the signature in this way and

887
00:40:15,769 --> 00:40:18,259
then finally you need to append the same

888
00:40:18,259 --> 00:40:20,329
stick hash type to the actual signature

889
00:40:20,329 --> 00:40:22,009
itself so this was just a cache type

890
00:40:22,009 --> 00:40:25,700
before we put into the mathematics and

891
00:40:25,700 --> 00:40:29,299
then we append the same number so this

892
00:40:29,299 --> 00:40:31,730
is 4 bytes this is one byte I think that

893
00:40:31,730 --> 00:40:32,599
was a mistake

894
00:40:32,599 --> 00:40:35,420
when the account was being developed to

895
00:40:35,420 --> 00:40:37,039
have these different sizes of bytes but

896
00:40:37,039 --> 00:40:40,460
they both the same number one and one so

897
00:40:40,460 --> 00:40:43,700
that goes on the end there so that's if

898
00:40:43,700 --> 00:40:44,930
you're doing technically but I just

899
00:40:44,930 --> 00:40:46,099
simplified this just to show you that

900
00:40:46,099 --> 00:40:48,079
the transaction data goes into this sort

901
00:40:48,079 --> 00:40:49,309
of two curve and that gives you a

902
00:40:49,309 --> 00:40:53,119
signature so when you create this

903
00:40:53,119 --> 00:40:55,789
signature because of the because you use

904
00:40:55,789 --> 00:40:58,609
it because we use this elliptic curve

905
00:40:58,609 --> 00:41:01,369
the address can basically look at this

906
00:41:01,369 --> 00:41:04,579
signature and say okay this signature

907
00:41:04,579 --> 00:41:06,890
could only have been created by the

908
00:41:06,890 --> 00:41:11,509
person who owns the public key that I

909
00:41:11,509 --> 00:41:14,630
made from so that is good enough

910
00:41:14,630 --> 00:41:16,249
distinction here is good enough to

911
00:41:16,249 --> 00:41:20,930
unlock this input and by doing that we

912
00:41:20,930 --> 00:41:22,640
can put this signature in here and we're

913
00:41:22,640 --> 00:41:24,529
not giving away our public our private

914
00:41:24,529 --> 00:41:30,289
key another benefit of this signing

915
00:41:30,289 --> 00:41:33,890
process is because this signature is

916
00:41:33,890 --> 00:41:37,430
made from this transaction structure

917
00:41:37,430 --> 00:41:39,890
that we created when we put this in here

918
00:41:39,890 --> 00:41:42,859
if we were to send this transaction into

919
00:41:42,859 --> 00:41:44,809
the network and someone was trying to

920
00:41:44,809 --> 00:41:46,609
modify the structure of the transaction

921
00:41:46,609 --> 00:41:51,380
like basically send change where the

922
00:41:51,380 --> 00:41:52,670
bitcoins are being sent to you know to

923
00:41:52,670 --> 00:41:55,309
try and steal your bitcoins like so

924
00:41:55,309 --> 00:41:58,549
they'll change the locking code then

925
00:41:58,549 --> 00:42:00,170
this signal this signature will no

926
00:42:00,170 --> 00:42:02,450
longer work and this transaction will no

927
00:42:02,450 --> 00:42:06,799
longer be valid because the signature

928
00:42:06,799 --> 00:42:08,989
signature will only work for the

929
00:42:08,989 --> 00:42:13,369
transaction that it's made from so this

930
00:42:13,369 --> 00:42:16,339
signature here protects the structure of

931
00:42:16,339 --> 00:42:19,069
the transaction you've created so that

932
00:42:19,069 --> 00:42:21,079
it'll only work for this particular

933
00:42:21,079 --> 00:42:28,509
transaction so that's basically how you

934
00:42:28,509 --> 00:42:32,710
create a signature to unlock an input

935
00:42:32,710 --> 00:42:35,619
this is called like I said a script sig

936
00:42:35,619 --> 00:42:38,359
but in a scripts take you don't just put

937
00:42:38,359 --> 00:42:41,569
the signature in there because of the

938
00:42:41,569 --> 00:42:43,220
locking code in here that I showed you

939
00:42:43,220 --> 00:42:45,920
earlier it also requires that you put

940
00:42:45,920 --> 00:42:48,799
the public key which is like basically

941
00:42:48,799 --> 00:42:52,400
the ugly version of the address you also

942
00:42:52,400 --> 00:42:57,829
have to put that into the script sig so

943
00:42:57,829 --> 00:42:59,749
it's called a script sig it's mostly a

944
00:42:59,749 --> 00:43:01,069
signature stuff but it also needs a

945
00:43:01,069 --> 00:43:03,650
public key for the unlocking code to

946
00:43:03,650 --> 00:43:07,430
work obviously this public key can be

947
00:43:07,430 --> 00:43:09,799
what I can vary in size so you need to

948
00:43:09,799 --> 00:43:11,509
put a view for your variable integer

949
00:43:11,509 --> 00:43:13,130
here to describe how long it's going to

950
00:43:13,130 --> 00:43:15,920
be same thing for a signature that can

951
00:43:15,920 --> 00:43:17,660
vary in size so that has its own

952
00:43:17,660 --> 00:43:21,200
variable integer and before the entire

953
00:43:21,200 --> 00:43:24,650
script sig you put a variable integer

954
00:43:24,650 --> 00:43:28,400
here so by doing this because we've put

955
00:43:28,400 --> 00:43:31,039
we have fixed field sizes and also very

956
00:43:31,039 --> 00:43:33,890
variable field sizes that means that you

957
00:43:33,890 --> 00:43:36,470
can decode this transaction and get the

958
00:43:36,470 --> 00:43:37,819
right amount of data so you know which

959
00:43:37,819 --> 00:43:40,420
part is which

960
00:43:41,050 --> 00:43:43,190
so again we'll just send that into the

961
00:43:43,190 --> 00:43:44,600
network because you've given it put the

962
00:43:44,600 --> 00:43:46,610
signature in there to unlock it

963
00:43:46,610 --> 00:43:47,960
they'll send onto the network and

964
00:43:47,960 --> 00:43:50,840
eventually the transaction will get mind

965
00:43:50,840 --> 00:43:55,040
and it will extend the graph like so yes

966
00:43:55,040 --> 00:43:58,130
so every node in the network actually is

967
00:43:58,130 --> 00:44:00,980
responsible for checking the validity of

968
00:44:00,980 --> 00:44:06,140
this every node will check yes it does

969
00:44:06,140 --> 00:44:07,460
that's correct a little check the violet

970
00:44:07,460 --> 00:44:09,050
it'll validate every single transaction

971
00:44:09,050 --> 00:44:14,000
it receives okay so if if I if I meddle

972
00:44:14,000 --> 00:44:18,530
with the script Cynthia it will flag it

973
00:44:18,530 --> 00:44:21,020
and the node itself will ignore that

974
00:44:21,020 --> 00:44:21,820
transaction

975
00:44:21,820 --> 00:44:25,660
yes so if you try to yeah if you sent a

976
00:44:25,660 --> 00:44:34,940
yeah wrong didn't yeah but scripts it is

977
00:44:34,940 --> 00:44:39,110
basically it's it's a digital signature

978
00:44:39,110 --> 00:44:44,570
which is nothing but even the hash of

979
00:44:44,570 --> 00:44:46,640
the transaction that's signed by the

980
00:44:46,640 --> 00:44:49,370
private key yes basically yes that's

981
00:44:49,370 --> 00:44:50,560
correct

982
00:44:50,560 --> 00:44:54,950
okay okay so my the intuition is that

983
00:44:54,950 --> 00:44:58,070
what the node might be doing is it will

984
00:44:58,070 --> 00:45:02,360
probably resign it using the public key

985
00:45:02,360 --> 00:45:07,940
and check if both are yes yeah yeah yeah

986
00:45:07,940 --> 00:45:10,010
then yeah that's correct yeah you

987
00:45:10,010 --> 00:45:15,920
figured it out yet yeah yeah and coming

988
00:45:15,920 --> 00:45:18,500
back to this slide so in the previous

989
00:45:18,500 --> 00:45:23,150
one so when you are actually so you were

990
00:45:23,150 --> 00:45:25,880
talking about the placeholder something

991
00:45:25,880 --> 00:45:28,130
about a placeholder could you just

992
00:45:28,130 --> 00:45:30,710
repeat that I mean is there like is

993
00:45:30,710 --> 00:45:33,020
there some placeholder text that's good

994
00:45:33,020 --> 00:45:34,550
all is it just and I know the

995
00:45:34,550 --> 00:45:37,930
placeholder is the so if we go back and

996
00:45:37,930 --> 00:45:43,040
quite far back when we created this lock

997
00:45:43,040 --> 00:45:45,920
here and we put some locking code so for

998
00:45:45,920 --> 00:45:49,010
example let's say you want to spend this

999
00:45:49,010 --> 00:45:50,299
input

1000
00:45:50,299 --> 00:45:54,270
so let's say we are spending this input

1001
00:45:54,270 --> 00:45:58,890
here and the place holder is the and is

1002
00:45:58,890 --> 00:46:05,789
the code inside this lock like so it's a

1003
00:46:05,789 --> 00:46:08,849
bit confusing I don't know

1004
00:46:08,849 --> 00:46:10,950
I don't sure why yeah I don't know why

1005
00:46:10,950 --> 00:46:12,569
it has to be the code inside lock I'm

1006
00:46:12,569 --> 00:46:14,670
sure it could be anything else but they

1007
00:46:14,670 --> 00:46:16,380
just needs to if anything is a bit

1008
00:46:16,380 --> 00:46:17,520
awkward to be honest it doesn't make

1009
00:46:17,520 --> 00:46:19,230
creating transactions a little bit more

1010
00:46:19,230 --> 00:46:21,690
awkward having to go back and get the

1011
00:46:21,690 --> 00:46:24,329
actual locking code for this input and

1012
00:46:24,329 --> 00:46:27,030
use that as a placeholder but that's

1013
00:46:27,030 --> 00:46:32,430
just the way it works and it's rehash

1014
00:46:32,430 --> 00:46:34,349
this basically the whole thing young

1015
00:46:34,349 --> 00:46:38,579
black and that's what we yes sign that's

1016
00:46:38,579 --> 00:46:40,200
what we sign yes I simplified it by

1017
00:46:40,200 --> 00:46:41,460
saying this you know you just put the

1018
00:46:41,460 --> 00:46:44,369
transaction data into the elliptic curve

1019
00:46:44,369 --> 00:46:46,680
which is kind of true but to be more

1020
00:46:46,680 --> 00:46:48,690
technical and correct you actually

1021
00:46:48,690 --> 00:46:51,180
append a sick hash type then you hash it

1022
00:46:51,180 --> 00:46:53,420
and the last what goes into this

1023
00:46:53,420 --> 00:46:58,099
elliptic curve mathematics and you can

1024
00:46:58,609 --> 00:47:01,170
usually find you can usually find a

1025
00:47:01,170 --> 00:47:05,940
library for for it's called ECDSA like

1026
00:47:05,940 --> 00:47:08,579
elliptic curve Dignitas signature

1027
00:47:08,579 --> 00:47:11,160
algorithm and this usually alike we can

1028
00:47:11,160 --> 00:47:16,529
use to do this signing and one more

1029
00:47:16,529 --> 00:47:19,470
question was that we do we keep doing

1030
00:47:19,470 --> 00:47:22,170
this for every output that we are trying

1031
00:47:22,170 --> 00:47:25,579
to spend right so for every we repeat

1032
00:47:25,579 --> 00:47:29,430
for every input why do is you will yes

1033
00:47:29,430 --> 00:47:32,609
like on yeah you basically don't forget

1034
00:47:32,609 --> 00:47:35,339
to remove all the existing signatures so

1035
00:47:35,339 --> 00:47:38,490
your site one and then for each one you

1036
00:47:38,490 --> 00:47:40,500
want to get the blank structure and then

1037
00:47:40,500 --> 00:47:45,930
sign that for each individual so we will

1038
00:47:45,930 --> 00:47:47,819
then at the end plug in all the

1039
00:47:47,819 --> 00:47:49,890
signatures one of the do just shove them

1040
00:47:49,890 --> 00:47:53,190
into into this oh yeah okay sorry

1041
00:47:53,190 --> 00:47:55,319
in this one I only had one so let's say

1042
00:47:55,319 --> 00:47:57,329
we had multiple you know Al this is this

1043
00:47:57,329 --> 00:48:00,119
is one then why do then if I had another

1044
00:48:00,119 --> 00:48:01,470
input I would just take all this

1045
00:48:01,470 --> 00:48:02,670
signature out

1046
00:48:02,670 --> 00:48:04,290
and I would just sign the next one I put

1047
00:48:04,290 --> 00:48:05,430
the placeholder into the next wouldn't

1048
00:48:05,430 --> 00:48:07,470
sign it to get the signature and so on

1049
00:48:07,470 --> 00:48:09,390
as the one got it and at the very end

1050
00:48:09,390 --> 00:48:12,390
you'll just plug in D and at the end at

1051
00:48:12,390 --> 00:48:14,280
the end you just will just shove in all

1052
00:48:14,280 --> 00:48:16,590
the script SIG's in the show back in

1053
00:48:16,590 --> 00:48:21,120
yeah I got it okay

1054
00:48:21,120 --> 00:48:23,160
so just to summarize this was our

1055
00:48:23,160 --> 00:48:25,350
transaction we created that signature

1056
00:48:25,350 --> 00:48:30,660
we'll put it put it in there so like I

1057
00:48:30,660 --> 00:48:32,730
said before a transaction has four major

1058
00:48:32,730 --> 00:48:35,460
parts you have the vision you have the

1059
00:48:35,460 --> 00:48:38,070
inputs and the input has their own sort

1060
00:48:38,070 --> 00:48:39,810
of mini structure thrown sub structure

1061
00:48:39,810 --> 00:48:41,700
so it has a track it refers to a

1062
00:48:41,700 --> 00:48:44,000
transaction ID then it refers to a

1063
00:48:44,000 --> 00:48:46,920
specific output then you have a variable

1064
00:48:46,920 --> 00:48:48,300
integer to tell you the size of that

1065
00:48:48,300 --> 00:48:51,330
come in script sig and then after that

1066
00:48:51,330 --> 00:48:54,360
you have a seeing it with a sequence and

1067
00:48:54,360 --> 00:48:56,730
that's an input next step we have

1068
00:48:56,730 --> 00:48:58,140
outputs and they have their own

1069
00:48:58,140 --> 00:49:00,510
structure again but they're quite simple

1070
00:49:00,510 --> 00:49:02,250
they just have a value which is 8 bytes

1071
00:49:02,250 --> 00:49:04,500
long then you have a very variable

1072
00:49:04,500 --> 00:49:06,420
integer to tell you the size of the

1073
00:49:06,420 --> 00:49:08,250
upcoming unlocking code which is called

1074
00:49:08,250 --> 00:49:11,310
the script pub key and then finally you

1075
00:49:11,310 --> 00:49:14,300
have the lock time and that is a

1076
00:49:14,300 --> 00:49:17,490
transaction and they're all the same the

1077
00:49:17,490 --> 00:49:19,260
only difference is they have varying

1078
00:49:19,260 --> 00:49:21,150
number of inputs varying number of

1079
00:49:21,150 --> 00:49:24,270
outputs and they obviously have referred

1080
00:49:24,270 --> 00:49:26,910
to different transactions and have

1081
00:49:26,910 --> 00:49:29,820
different signatures but you understand

1082
00:49:29,820 --> 00:49:31,620
the structure then you understand the

1083
00:49:31,620 --> 00:49:33,420
structure of every single Bitcoin

1084
00:49:33,420 --> 00:49:35,060
transaction that they could possibly be

1085
00:49:35,060 --> 00:49:39,570
except for a seg wit this is like an old

1086
00:49:39,570 --> 00:49:42,840
cell transaction you do have segregated

1087
00:49:42,840 --> 00:49:46,830
witness now which basically on a very

1088
00:49:46,830 --> 00:49:49,620
basic level all it does instead of

1089
00:49:49,620 --> 00:49:52,860
having this signature code in the middle

1090
00:49:52,860 --> 00:49:55,440
of transactions a base link it basically

1091
00:49:55,440 --> 00:49:57,240
gets moved to the end at the end of a

1092
00:49:57,240 --> 00:49:59,340
transaction and that's called the

1093
00:49:59,340 --> 00:50:02,100
witness so that's why it's called it's

1094
00:50:02,100 --> 00:50:04,740
basically like separating the signatures

1095
00:50:04,740 --> 00:50:07,950
from the transaction or sometimes a

1096
00:50:07,950 --> 00:50:10,860
signature is called a witness and that's

1097
00:50:10,860 --> 00:50:12,120
why it's called segregated witness

1098
00:50:12,120 --> 00:50:14,250
because it's at segregating the witness

1099
00:50:14,250 --> 00:50:14,430
day

1100
00:50:14,430 --> 00:50:17,369
two signatures from the structure of the

1101
00:50:17,369 --> 00:50:18,030
transaction

1102
00:50:18,030 --> 00:50:23,160
I think covering and segue witness would

1103
00:50:23,160 --> 00:50:26,339
be his own video but I want to do this

1104
00:50:26,339 --> 00:50:28,160
or at least this is a basic and

1105
00:50:28,160 --> 00:50:30,869
transaction and these are still valid

1106
00:50:30,869 --> 00:50:31,619
and you can still make these

1107
00:50:31,619 --> 00:50:32,970
transactions perfectly fine on the

1108
00:50:32,970 --> 00:50:42,920
network so maybe distant one line or

1109
00:50:44,300 --> 00:50:48,059
it's basically a Bitcoin proposal yes

1110
00:50:48,059 --> 00:50:51,390
oh yeah it's a segregated witness is a

1111
00:50:51,390 --> 00:50:53,849
change the transaction data structure

1112
00:50:53,849 --> 00:50:57,119
and it just okay okay it just moves the

1113
00:50:57,119 --> 00:50:59,339
so yeah as you have this is like the

1114
00:50:59,339 --> 00:51:02,520
typical basic transaction but I was

1115
00:51:02,520 --> 00:51:03,720
segregated witness will have another

1116
00:51:03,720 --> 00:51:06,450
field or section called the witness area

1117
00:51:06,450 --> 00:51:09,359
and the signatures basically get moved

1118
00:51:09,359 --> 00:51:11,130
to the end of the transaction and that's

1119
00:51:11,130 --> 00:51:15,359
called a witness area somewhat like let

1120
00:51:15,359 --> 00:51:16,740
me rephrase the question this is a

1121
00:51:16,740 --> 00:51:19,980
change in the Bitcoin core goodness or

1122
00:51:19,980 --> 00:51:23,970
is it a change that exchanges need to

1123
00:51:23,970 --> 00:51:30,390
make it's well it's because I keep

1124
00:51:30,390 --> 00:51:32,010
hearing this that you know this person

1125
00:51:32,010 --> 00:51:33,690
has to implement send witty and that

1126
00:51:33,690 --> 00:51:35,400
person has to implement said with yet

1127
00:51:35,400 --> 00:51:38,940
and they haven't done it and I'm still a

1128
00:51:38,940 --> 00:51:41,220
little confused but anyway we can hear

1129
00:51:41,220 --> 00:51:43,980
well if you didn't if you created your

1130
00:51:43,980 --> 00:51:46,049
own software and you've only have ever

1131
00:51:46,049 --> 00:51:47,849
been able to create to these kind of

1132
00:51:47,849 --> 00:51:50,520
structures transactions then you would

1133
00:51:50,520 --> 00:51:52,740
have to unless you are using the Bitcoin

1134
00:51:52,740 --> 00:51:53,790
core software to create your

1135
00:51:53,790 --> 00:51:56,640
transactions which you know if you've

1136
00:51:56,640 --> 00:51:57,720
made your own software to create these

1137
00:51:57,720 --> 00:51:59,910
then you need to write your own software

1138
00:51:59,910 --> 00:52:02,190
to create your own security witness

1139
00:52:02,190 --> 00:52:05,099
transactions guard yeah make sense in

1140
00:52:05,099 --> 00:52:06,900
fairness technically I don't think that

1141
00:52:06,900 --> 00:52:12,030
terribly different difficult so I don't

1142
00:52:12,030 --> 00:52:13,260
know why some places are taking so long

1143
00:52:13,260 --> 00:52:15,299
I think it might be just caution maybe

1144
00:52:15,299 --> 00:52:19,530
I'm not sure got it so at this point of

1145
00:52:19,530 --> 00:52:21,869
time if I send a transaction with with

1146
00:52:21,869 --> 00:52:24,059
segregated witness the Bitcoin core will

1147
00:52:24,059 --> 00:52:27,450
understand it yes okay

1148
00:52:27,450 --> 00:52:32,069
all right so that's the that's what

1149
00:52:32,069 --> 00:52:34,140
we're done so that's the basic stone and

1150
00:52:34,140 --> 00:52:36,329
that's the beta done so I'm gonna do an

1151
00:52:36,329 --> 00:52:37,859
out I'm going to do some examples just

1152
00:52:37,859 --> 00:52:40,859
to create a transaction transaction from

1153
00:52:40,859 --> 00:52:42,440
scratch

1154
00:52:42,440 --> 00:52:47,490
alright so this is my website before the

1155
00:52:47,490 --> 00:52:50,119
transaction transaction from scratch

1156
00:52:50,119 --> 00:52:54,240
what I would say is well here's a page

1157
00:52:54,240 --> 00:52:55,740
I've got to the glossary go to

1158
00:52:55,740 --> 00:52:59,880
transaction data I've broken down the

1159
00:52:59,880 --> 00:53:02,490
transactions here so if you wanted to

1160
00:53:02,490 --> 00:53:04,530
decode your own transaction which i

1161
00:53:04,530 --> 00:53:05,460
think is a good idea

1162
00:53:05,460 --> 00:53:07,530
I think decode in this transaction data

1163
00:53:07,530 --> 00:53:09,390
is a very good place to start I think

1164
00:53:09,390 --> 00:53:10,650
trying to build one because the

1165
00:53:10,650 --> 00:53:13,349
signatures is a bit tricky you might get

1166
00:53:13,349 --> 00:53:15,599
a bit stuck at some point but decoding

1167
00:53:15,599 --> 00:53:16,829
it I think would be a good place to

1168
00:53:16,829 --> 00:53:18,359
start for getting to grips with how

1169
00:53:18,359 --> 00:53:22,290
transactions work and I saw it was handy

1170
00:53:22,290 --> 00:53:24,150
to have your own decoder just for your

1171
00:53:24,150 --> 00:53:27,390
own reference purposes but if you wanted

1172
00:53:27,390 --> 00:53:30,030
to you know dig into the transaction

1173
00:53:30,030 --> 00:53:34,940
data here's the page on my website or

1174
00:53:34,940 --> 00:53:37,170
alternatively you could just look at any

1175
00:53:37,170 --> 00:53:40,650
block of transactions on the browser so

1176
00:53:40,650 --> 00:53:43,349
for example this one this is a bit of a

1177
00:53:43,349 --> 00:53:44,730
complex one there's taking loads of

1178
00:53:44,730 --> 00:53:46,230
inputs in and spitting rows of it the

1179
00:53:46,230 --> 00:53:48,480
outputs out but if you click on see

1180
00:53:48,480 --> 00:53:52,109
realized and you can break down the

1181
00:53:52,109 --> 00:53:55,380
transaction into its component parts so

1182
00:53:55,380 --> 00:53:58,049
that might be helpful when when you want

1183
00:53:58,049 --> 00:53:59,760
to understand the structure of a

1184
00:53:59,760 --> 00:54:03,900
transaction but what I'm going to now

1185
00:54:03,900 --> 00:54:05,420
what I'm gonna do now I'm going to

1186
00:54:05,420 --> 00:54:10,760
construct my own transaction

1187
00:54:11,450 --> 00:54:15,349
I swear I can't give it up get rid of

1188
00:54:15,349 --> 00:54:18,109
this little thing here sorry don't how

1189
00:54:18,109 --> 00:54:24,380
to do that brother so I've got some I've

1190
00:54:24,380 --> 00:54:27,799
made a little script called transaction

1191
00:54:27,799 --> 00:54:30,440
builder and I'm going to build my own

1192
00:54:30,440 --> 00:54:33,650
transaction so first thing I need is I

1193
00:54:33,650 --> 00:54:39,049
need to be able to know which outputs I

1194
00:54:39,049 --> 00:54:41,869
can spend so luckily for me I've created

1195
00:54:41,869 --> 00:54:46,430
a transaction beforehand and I've locked

1196
00:54:46,430 --> 00:54:49,910
these outputs to address his value so

1197
00:54:49,910 --> 00:54:54,380
I'm gonna spend one of these outputs so

1198
00:54:54,380 --> 00:54:55,849
I'll spend this one this is the one I

1199
00:54:55,849 --> 00:54:57,549
want to spend and send to somewhere else

1200
00:54:57,549 --> 00:55:00,170
so first of all in the transaction

1201
00:55:00,170 --> 00:55:01,549
builder facing a need it's a version

1202
00:55:01,549 --> 00:55:03,589
number so I'll stick the version 1 in

1203
00:55:03,589 --> 00:55:06,950
there and so that has turned that number

1204
00:55:06,950 --> 00:55:11,359
1 into hexadecimal network byte order

1205
00:55:11,359 --> 00:55:15,980
and it's turned into a 4 byte field next

1206
00:55:15,980 --> 00:55:17,930
step we need to select the inputs so I

1207
00:55:17,930 --> 00:55:20,720
need a transaction ID and a output

1208
00:55:20,720 --> 00:55:23,020
number so this is the transaction ID

1209
00:55:23,020 --> 00:55:26,270
I'll put that in there and I want this

1210
00:55:26,270 --> 00:55:30,280
one here that's output 0 so there we are

1211
00:55:30,280 --> 00:55:33,740
that's the only one I want to spend so

1212
00:55:33,740 --> 00:55:36,380
that's not done so if you look here

1213
00:55:36,380 --> 00:55:40,460
that's the number of inputs this here is

1214
00:55:40,460 --> 00:55:44,000
the transaction ID in Reverse byte order

1215
00:55:44,000 --> 00:55:50,530
so a 4 a 4 and this here is the 4 byte

1216
00:55:54,090 --> 00:55:59,460
it's the 4-byte output number this here

1217
00:55:59,460 --> 00:56:02,550
is the variable integer to see to tell

1218
00:56:02,550 --> 00:56:04,080
me the upcoming size of the signature

1219
00:56:04,080 --> 00:56:05,730
but I haven't put it in there yet so at

1220
00:56:05,730 --> 00:56:07,500
zero and this is the sequence number

1221
00:56:07,500 --> 00:56:11,120
done using so next up now I need to

1222
00:56:11,120 --> 00:56:13,650
choose my way I need to create my

1223
00:56:13,650 --> 00:56:16,970
outputs so this were here this is a

1224
00:56:16,970 --> 00:56:20,910
naught point naught 5 BTC but I want

1225
00:56:20,910 --> 00:56:23,520
this to be in satoshis so let me just

1226
00:56:23,520 --> 00:56:28,350
configure that yeah so that's not point

1227
00:56:28,350 --> 00:56:33,090
naught naught 5 1 so I put the value

1228
00:56:33,090 --> 00:56:36,840
here and the address I want to send it

1229
00:56:36,840 --> 00:56:40,230
to I think I'll send it to my donation

1230
00:56:40,230 --> 00:56:41,760
address here and the top of the website

1231
00:56:41,760 --> 00:56:47,310
so there we go and but because I want

1232
00:56:47,310 --> 00:56:51,630
this to get mind I haven't put a fee on

1233
00:56:51,630 --> 00:56:53,880
this so what I'll do instead of sending

1234
00:56:53,880 --> 00:56:54,660
the whole amount

1235
00:56:54,660 --> 00:57:00,990
I'll send c49 this this amount so that

1236
00:57:00,990 --> 00:57:02,490
puts a little fee on it I don't know

1237
00:57:02,490 --> 00:57:03,960
what that's gonna be in fee per byte

1238
00:57:03,960 --> 00:57:06,120
under guessing but that will leave a

1239
00:57:06,120 --> 00:57:09,570
remainder in the transaction and again

1240
00:57:09,570 --> 00:57:12,450
put the address there so that's a book

1241
00:57:12,450 --> 00:57:15,150
created last up then so this is output

1242
00:57:15,150 --> 00:57:17,910
been added to the transaction code when

1243
00:57:17,910 --> 00:57:22,190
I put and this is the is this right

1244
00:57:22,190 --> 00:57:25,940
yeah I'm sure here somewhere

1245
00:57:26,180 --> 00:57:28,680
so a quick question here so at this

1246
00:57:28,680 --> 00:57:31,260
point is it signed or it it still yes

1247
00:57:31,260 --> 00:57:32,880
Tony's resigned and you have to create

1248
00:57:32,880 --> 00:57:35,070
yeah okay the whole structure first

1249
00:57:35,070 --> 00:57:39,090
before it gets on alright got it so it

1250
00:57:39,090 --> 00:57:41,570
has your code just plugged in the place

1251
00:57:41,570 --> 00:57:46,020
he'll do that in a moment and so last up

1252
00:57:46,020 --> 00:57:48,510
is a long time so there we are so now

1253
00:57:48,510 --> 00:57:50,850
we've created the structure we've chosen

1254
00:57:50,850 --> 00:57:52,410
the inputs and we've creating the output

1255
00:57:52,410 --> 00:57:54,060
from it so now we've got the whole

1256
00:57:54,060 --> 00:57:56,010
structure this is you've got the data we

1257
00:57:56,010 --> 00:57:59,370
need to be able to sign it so to be able

1258
00:57:59,370 --> 00:58:00,330
to sign it

1259
00:58:00,330 --> 00:58:04,190
I need the private key for this address

1260
00:58:04,190 --> 00:58:06,300
you should never expose your private key

1261
00:58:06,300 --> 00:58:08,970
but in this example here it is this is

1262
00:58:08,970 --> 00:58:12,690
my private key for this output so there

1263
00:58:12,690 --> 00:58:13,710
we are that's the private key that

1264
00:58:13,710 --> 00:58:16,680
corresponds to this address but like I

1265
00:58:16,680 --> 00:58:21,180
said we need to get the locking code so

1266
00:58:21,180 --> 00:58:22,710
that we can use a placeholder when we

1267
00:58:22,710 --> 00:58:25,080
sign it it's a bit annoying but if you

1268
00:58:25,080 --> 00:58:26,250
click on this little lock here on the

1269
00:58:26,250 --> 00:58:29,970
browser this is the locking code as you

1270
00:58:29,970 --> 00:58:34,160
can see those you know it corresponds to

1271
00:58:34,160 --> 00:58:37,950
up codes and this is the public key

1272
00:58:37,950 --> 00:58:41,120
that's the address so I need this

1273
00:58:41,120 --> 00:58:43,470
locking code to be used as a placeholder

1274
00:58:43,470 --> 00:58:47,550
when I sign the transaction so there we

1275
00:58:47,550 --> 00:58:47,700
are

1276
00:58:47,700 --> 00:58:50,640
I'll sign this now and this is the D

1277
00:58:50,640 --> 00:58:54,330
completed transaction data so because

1278
00:58:54,330 --> 00:58:55,770
it's all signed this is ready to go I

1279
00:58:55,770 --> 00:58:59,370
can use I can if I want to I can just

1280
00:58:59,370 --> 00:59:01,760
quickly decode it so I've written my own

1281
00:59:01,760 --> 00:59:03,470
[Music]

1282
00:59:03,470 --> 00:59:05,700
transaction decoder is quite handy to

1283
00:59:05,700 --> 00:59:08,370
have so I can look at this and it's

1284
00:59:08,370 --> 00:59:11,370
showing me the inputs there's one here

1285
00:59:11,370 --> 00:59:15,000
the transaction ID and one output and to

1286
00:59:15,000 --> 00:59:16,440
be unlocked to this address here the

1287
00:59:16,440 --> 00:59:17,700
beer address which is my donation

1288
00:59:17,700 --> 00:59:21,600
address and if you do you get kind CLI

1289
00:59:21,600 --> 00:59:23,580
if you download a Bitcoin core it has

1290
00:59:23,580 --> 00:59:25,670
his own decoder

1291
00:59:25,670 --> 00:59:27,829
transaction you can do the same thing

1292
00:59:27,829 --> 00:59:32,650
and it will decode it for you as well so

1293
00:59:33,190 --> 00:59:35,450
now we've got the transaction it's all

1294
00:59:35,450 --> 00:59:37,609
been signed ready to go what I can do I

1295
00:59:37,609 --> 00:59:41,829
can go Bitcoin CLI send your transaction

1296
00:59:41,829 --> 00:59:45,200
so I'll put that in there and there we

1297
00:59:45,200 --> 00:59:45,349
are

1298
00:59:45,349 --> 00:59:48,589
it has just given me a transaction ID so

1299
00:59:48,589 --> 00:59:51,230
this is the transaction and this is the

1300
00:59:51,230 --> 00:59:54,079
transaction ID for it so I can take this

1301
00:59:54,079 --> 00:59:56,859
transaction ID and I can go into my

1302
00:59:56,859 --> 00:59:59,660
blockchain Explorer and I can enter the

1303
00:59:59,660 --> 01:00:01,640
transaction ID try and find it

1304
01:00:01,640 --> 01:00:03,950
okay hasn't found it yet it's probably

1305
01:00:03,950 --> 01:00:05,900
taking some time for to propagate the

1306
01:00:05,900 --> 01:00:12,589
network so I keep refreshing okay give

1307
01:00:12,589 --> 01:00:16,039
it good ten seconds gone so yeah we are

1308
01:00:16,039 --> 01:00:18,559
looking for this in the men buoy or in

1309
01:00:18,559 --> 01:00:20,450
the blacklist would have gone so I've

1310
01:00:20,450 --> 01:00:22,730
created this transaction I sent in to a

1311
01:00:22,730 --> 01:00:25,160
node and it's now gonna be being sent on

1312
01:00:25,160 --> 01:00:25,549
the network

1313
01:00:25,549 --> 01:00:28,809
and it's gonna enter this nodes mempool

1314
01:00:28,809 --> 01:00:31,759
so it it should be a plain ring if I

1315
01:00:31,759 --> 01:00:33,710
click on this memory pool it should be

1316
01:00:33,710 --> 01:00:36,470
appearing yeah somebody here I just

1317
01:00:36,470 --> 01:00:41,539
deleted the page it's there okay so they

1318
01:00:41,539 --> 01:00:42,890
release their art it's just received it

1319
01:00:42,890 --> 01:00:46,069
five seconds ago they are so I can click

1320
01:00:46,069 --> 01:00:48,319
on this now and there is the transaction

1321
01:00:48,319 --> 01:00:51,349
I just made I'm watching Explorer so now

1322
01:00:51,349 --> 01:00:53,089
it's on the network now I know it's been

1323
01:00:53,089 --> 01:00:56,059
sent on the network it's a very low fee

1324
01:00:56,059 --> 01:01:00,410
I don't think it's gonna get mind but

1325
01:01:00,410 --> 01:01:01,970
again I can just look at the code and

1326
01:01:01,970 --> 01:01:04,549
this should be the exact same code dye

1327
01:01:04,549 --> 01:01:07,519
created so basically you send code into

1328
01:01:07,519 --> 01:01:10,039
the network and that describes this

1329
01:01:10,039 --> 01:01:12,589
transaction with the movement of inputs

1330
01:01:12,589 --> 01:01:18,769
to outputs is that yeah it's better

1331
01:01:18,769 --> 01:01:21,170
converter two US dollars here I mean I

1332
01:01:21,170 --> 01:01:22,880
haven't no I guess I could request my

1333
01:01:22,880 --> 01:01:25,069
brother sir asked me the same thing I'm

1334
01:01:25,069 --> 01:01:26,420
still working I have to work on it yeah

1335
01:01:26,420 --> 01:01:30,559
I think this is about $80 at the moment

1336
01:01:30,559 --> 01:01:33,319
so I'm probably gonna want to make sure

1337
01:01:33,319 --> 01:01:35,569
this transaction gets mind before I put

1338
01:01:35,569 --> 01:01:38,890
the video out because exactly

1339
01:01:39,000 --> 01:01:42,150
private key and how yeah and what is the

1340
01:01:42,150 --> 01:01:49,440
fee like approximate 0.0002 well if the

1341
01:01:49,440 --> 01:01:52,950
works off a fee per bite because a node

1342
01:01:52,950 --> 01:01:55,230
can only fit up there block with so many

1343
01:01:55,230 --> 01:01:59,460
bytes exchanged small fee per weight but

1344
01:01:59,460 --> 01:02:00,600
I haven't updated the Explorer to use

1345
01:02:00,600 --> 01:02:02,010
weight and it's more of a complex thing

1346
01:02:02,010 --> 01:02:03,540
to use but if we look it over

1347
01:02:03,540 --> 01:02:05,400
if you look at all these transactions if

1348
01:02:05,400 --> 01:02:06,270
you go towards the bottom there

1349
01:02:06,270 --> 01:02:10,170
generally ordered by their fee per fee

1350
01:02:10,170 --> 01:02:13,290
per byte it's slow maybe ask them you

1351
01:02:13,290 --> 01:02:15,480
know the smallest ones about 100 odd you

1352
01:02:15,480 --> 01:02:17,490
know no point no not 100 to Satoshi's

1353
01:02:17,490 --> 01:02:19,530
right so well some of you get included

1354
01:02:19,530 --> 01:02:23,610
for Less but there's just a rough

1355
01:02:23,610 --> 01:02:24,780
estimate but it looks like my

1356
01:02:24,780 --> 01:02:28,620
transaction is just slightly too low the

1357
01:02:28,620 --> 01:02:32,130
fee to get mine just yet so I could

1358
01:02:32,130 --> 01:02:34,140
create another one just show you but I

1359
01:02:34,140 --> 01:02:35,760
mean that's good enough you know just to

1360
01:02:35,760 --> 01:02:36,990
show you that how when you get a

1361
01:02:36,990 --> 01:02:39,750
transaction it just gets goes into the

1362
01:02:39,750 --> 01:02:47,730
memory pool like so I've made this code

1363
01:02:47,730 --> 01:02:49,620
available on the website so if you go to

1364
01:02:49,620 --> 01:02:52,610
code transaction builder dot RB

1365
01:02:52,610 --> 01:02:55,650
the code is all here mm-hm I written it

1366
01:02:55,650 --> 01:02:59,280
in Ruby I tried to make it as simple as

1367
01:02:59,280 --> 01:03:00,440
possible I did want to do it

1368
01:03:00,440 --> 01:03:03,570
procedurally procedurally because I

1369
01:03:03,570 --> 01:03:04,680
thought that'd be an easier way to do I

1370
01:03:04,680 --> 01:03:06,630
couldn't do it that way I thought we it

1371
01:03:06,630 --> 01:03:08,250
seemed easier to do it in an

1372
01:03:08,250 --> 01:03:12,360
object-oriented way so okay it's not

1373
01:03:12,360 --> 01:03:14,460
terribly long it's about 300 lines long

1374
01:03:14,460 --> 01:03:18,870
at the code but the basic parts is you

1375
01:03:18,870 --> 01:03:21,060
have I start with some utilities just

1376
01:03:21,060 --> 01:03:22,410
for getting all the data in the correct

1377
01:03:22,410 --> 01:03:26,310
format then the main transaction class

1378
01:03:26,310 --> 01:03:28,920
that has version inputs outputs and lock

1379
01:03:28,920 --> 01:03:31,110
time so it has an array of inputs and a

1380
01:03:31,110 --> 01:03:34,350
real outputs so and then you have an

1381
01:03:34,350 --> 01:03:35,790
input class which has you know the

1382
01:03:35,790 --> 01:03:38,640
transaction ID the V out scripts ax

1383
01:03:38,640 --> 01:03:40,040
equals and then

1384
01:03:40,040 --> 01:03:43,550
then you have an output object which

1385
01:03:43,550 --> 01:03:45,320
just hasn't value and the script and the

1386
01:03:45,320 --> 01:03:49,700
script pub key and so if you want I

1387
01:03:49,700 --> 01:03:51,860
think he'd be good to create you you've

1388
01:03:51,860 --> 01:03:52,940
wanted to build your own name

1389
01:03:52,940 --> 01:03:54,560
transaction builder from scratch I think

1390
01:03:54,560 --> 01:03:55,790
it's a good way to do it you know in

1391
01:03:55,790 --> 01:03:57,650
your own programming language but if you

1392
01:03:57,650 --> 01:03:59,030
wanted to see if you're making some

1393
01:03:59,030 --> 01:04:00,110
mistakes you want to see what squares

1394
01:04:00,110 --> 01:04:01,700
going wrong and you could always come in

1395
01:04:01,700 --> 01:04:03,320
here for example probably the trick is

1396
01:04:03,320 --> 01:04:07,030
trickiest part is just this signing part

1397
01:04:07,030 --> 01:04:10,310
obviously here's the signing method and

1398
01:04:10,310 --> 01:04:12,860
it's a bit long but it's just basically

1399
01:04:12,860 --> 01:04:14,300
getting all the data in the right order

1400
01:04:14,300 --> 01:04:17,300
I'd have any common commented it so it

1401
01:04:17,300 --> 01:04:18,530
might be helpful for trying to figure

1402
01:04:18,530 --> 01:04:24,880
out which parts might be missing okay so

1403
01:04:24,940 --> 01:04:29,990
there's any questions with that no like

1404
01:04:29,990 --> 01:04:31,730
yeah I think that so I think that

1405
01:04:31,730 --> 01:04:33,230
basically tempers you know if you wanted

1406
01:04:33,230 --> 01:04:35,090
to create your own transaction you know

1407
01:04:35,090 --> 01:04:37,070
this should it's quite helped I think

1408
01:04:37,070 --> 01:04:38,360
this my websites quite helpful for

1409
01:04:38,360 --> 01:04:39,920
finding the correct data to be able to

1410
01:04:39,920 --> 01:04:41,300
you know create your own transactions

1411
01:04:41,300 --> 01:04:42,470
and just browse it and see what's going

1412
01:04:42,470 --> 01:04:45,320
on definitely definitely

1413
01:04:45,320 --> 01:04:47,750
are you using some sort of API or are is

1414
01:04:47,750 --> 01:04:49,850
this being pulled from like a real old

1415
01:04:49,850 --> 01:04:52,280
yeah this is an this is basically well

1416
01:04:52,280 --> 01:04:54,440
enough a Bitcoin core node and but what

1417
01:04:54,440 --> 01:04:58,060
I do I so I but I put it into my own

1418
01:04:58,060 --> 01:05:00,740
database but it's basically running live

1419
01:05:00,740 --> 01:05:02,990
off a Bitcoin core node so when you make

1420
01:05:02,990 --> 01:05:04,940
a transaction I said new block I've just

1421
01:05:04,940 --> 01:05:10,490
been added so yeah it's all life okay so

1422
01:05:10,490 --> 01:05:13,250
you're hosting the website on the same

1423
01:05:13,250 --> 01:05:17,180
node or it's on a different machine and

1424
01:05:17,180 --> 01:05:19,100
you just pull data into a database and

1425
01:05:19,100 --> 01:05:22,070
then have the website read data off it's

1426
01:05:22,070 --> 01:05:23,510
actually on the same machine it probably

1427
01:05:23,510 --> 01:05:25,010
would make sense to have the node on a

1428
01:05:25,010 --> 01:05:27,980
different machine and then how can they

1429
01:05:27,980 --> 01:05:29,150
- I'll have this website just mean the

1430
01:05:29,150 --> 01:05:33,170
database but I don't the machines needs

1431
01:05:33,170 --> 01:05:35,600
to be handling handling it okay so at

1432
01:05:35,600 --> 01:05:38,570
the moment Wow but this is running off a

1433
01:05:38,570 --> 01:05:40,640
machine in Switzerland so that's why

1434
01:05:40,640 --> 01:05:41,990
when I made this transaction I'm in the

1435
01:05:41,990 --> 01:05:44,579
UK at the moment I sent it from my

1436
01:05:44,579 --> 01:05:47,910
I sent this from my local node from the

1437
01:05:47,910 --> 01:05:50,279
UK so yeah but then again it only takes

1438
01:05:50,279 --> 01:05:53,640
a few seconds I think for a transaction

1439
01:05:53,640 --> 01:05:55,650
to propagate the entire network so it

1440
01:05:55,650 --> 01:05:57,119
might have been my website was a little

1441
01:05:57,119 --> 01:05:59,699
bit slow at decoding the transaction and

1442
01:05:59,699 --> 01:06:03,259
then and then storing it in the database

1443
01:06:04,039 --> 01:06:08,369
so that's the Bitcoin CLI give you

1444
01:06:08,369 --> 01:06:11,279
access to all this data like memory pool

1445
01:06:11,279 --> 01:06:13,679
and transactions in the memory pool or

1446
01:06:13,679 --> 01:06:16,199
you yeah and it does give you all the

1447
01:06:16,199 --> 01:06:19,019
data so I mean you could use the website

1448
01:06:19,019 --> 01:06:21,989
but you can actually get all this data

1449
01:06:21,989 --> 01:06:25,939
from Bitcoin CLI I'm not sure what is

1450
01:06:25,939 --> 01:06:28,650
are they okay that last the mempool so

1451
01:06:28,650 --> 01:06:31,469
Bitcoin CLI get more mempool these are

1452
01:06:31,469 --> 01:06:33,779
all the transactions ID transaction IDs

1453
01:06:33,779 --> 01:06:37,439
coming in there yeah and if you wanted

1454
01:06:37,439 --> 01:06:47,519
to get Bitcoin there we are so that's

1455
01:06:47,519 --> 01:06:48,809
the transaction data for that one I just

1456
01:06:48,809 --> 01:06:50,729
selected so it's all there you know you

1457
01:06:50,729 --> 01:06:52,229
can get all that out to the out of the

1458
01:06:52,229 --> 01:06:53,269
in politic

1459
01:06:53,269 --> 01:07:00,119
Bitcoin see like a nice yep so I think

1460
01:07:00,119 --> 01:07:03,630
that's everything I wanted to cover yes

1461
01:07:03,630 --> 01:07:07,859
at all before no no that's it great

1462
01:07:07,859 --> 01:07:13,670
thanks a lot sir yeah looking forward to

1463
01:07:13,670 --> 01:07:16,679
yeah I think the next what I'd like to

1464
01:07:16,679 --> 01:07:20,420
do is probably covering the keys and

1465
01:07:20,420 --> 01:07:24,209
addresses so these public keys probably

1466
01:07:24,209 --> 01:07:25,650
probably keep every key in address how

1467
01:07:25,650 --> 01:07:27,089
they all connect together through this

1468
01:07:27,089 --> 01:07:29,789
you know this lip decay of how they

1469
01:07:29,789 --> 01:07:33,059
created because that explained a lot

1470
01:07:33,059 --> 01:07:34,529
about how this signature stuff works

1471
01:07:34,529 --> 01:07:35,910
because at the moment I just saw said

1472
01:07:35,910 --> 01:07:38,489
this is a signature and it works but I

1473
01:07:38,489 --> 01:07:40,049
could explain how it actually does work

1474
01:07:40,049 --> 01:07:44,730
using this mathematics nice nicer

1475
01:07:44,730 --> 01:07:47,040
yeah looking forward to it yeah just

1476
01:07:47,040 --> 01:07:48,810
just let me know whenever yeah whenever

1477
01:07:48,810 --> 01:07:51,119
you're ready I'll stop I'll stop

1478
01:07:51,119 --> 01:07:52,500
chipping away at some keys and the

1479
01:07:52,500 --> 01:07:54,390
dresses stuff but if I give you an email

1480
01:07:54,390 --> 01:07:56,310
in a while to let you know when I think

1481
01:07:56,310 --> 01:07:59,550
you might be ready yeah so thank you

1482
01:07:59,550 --> 01:08:02,250
very much thanks a thanks for those

1483
01:08:02,250 --> 01:08:04,550
really good

