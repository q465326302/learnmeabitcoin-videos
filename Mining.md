1
00:00:00,640 --> 00:00:01,520
so

2
00:00:01,520 --> 00:00:02,720
uh in this presentation i'm going to

3
00:00:02,720 --> 00:00:04,880
cover how bitcoin mining works

4
00:00:04,880 --> 00:00:06,720
um

5
00:00:06,720 --> 00:00:08,480
i'll start out with what is mining and

6
00:00:08,480 --> 00:00:11,200
i'll cover what it is and why it exists

7
00:00:11,200 --> 00:00:12,240
um

8
00:00:12,240 --> 00:00:13,599
and then after that i'll cover how it

9
00:00:13,599 --> 00:00:14,559
works

10
00:00:14,559 --> 00:00:16,640
um but before i can cover how it works i

11
00:00:16,640 --> 00:00:19,119
need to explain what a hash function is

12
00:00:19,119 --> 00:00:20,880
um because that's like an integral part

13
00:00:20,880 --> 00:00:23,279
of how bitcoin works

14
00:00:23,279 --> 00:00:25,119
uh then i'll cover

15
00:00:25,119 --> 00:00:27,199
the basics of how it works and then i'll

16
00:00:27,199 --> 00:00:28,480
go through it again

17
00:00:28,480 --> 00:00:30,240
but i'll explain in a more technical way

18
00:00:30,240 --> 00:00:31,599
so if you're a programmer you'll find

19
00:00:31,599 --> 00:00:33,360
that more interesting

20
00:00:33,360 --> 00:00:35,120
um then after that i'll start doing some

21
00:00:35,120 --> 00:00:37,280
examples and i'll try and show you how

22
00:00:37,280 --> 00:00:39,760
um you could actually mine a live block

23
00:00:39,760 --> 00:00:43,200
um in a very small amount of code

24
00:00:43,200 --> 00:00:44,879
so that's what the presentation is going

25
00:00:44,879 --> 00:00:47,440
to be so i'll get started with then

26
00:00:47,440 --> 00:00:49,600
what mining is

27
00:00:49,600 --> 00:00:51,680
so what is mining

28
00:00:51,680 --> 00:00:53,120
um well imagine this is the bitcoin

29
00:00:53,120 --> 00:00:54,160
network

30
00:00:54,160 --> 00:00:56,079
and these were all the computers uh

31
00:00:56,079 --> 00:00:57,840
connected together running the bitcoin

32
00:00:57,840 --> 00:00:59,039
program

33
00:00:59,039 --> 00:01:01,840
and sharing the same file which is this

34
00:01:01,840 --> 00:01:04,000
blockchain

35
00:01:04,000 --> 00:01:06,400
um the way bitcoin works um if you want

36
00:01:06,400 --> 00:01:09,040
to send a bitcoin to someone

37
00:01:09,040 --> 00:01:09,760
or

38
00:01:09,760 --> 00:01:11,760
transfer ownership of a bitcoin

39
00:01:11,760 --> 00:01:13,040
to someone else

40
00:01:13,040 --> 00:01:14,320
the way you do that is you create a

41
00:01:14,320 --> 00:01:16,320
transaction with just a little line of

42
00:01:16,320 --> 00:01:17,280
data

43
00:01:17,280 --> 00:01:19,200
and then you'll insert that into a node

44
00:01:19,200 --> 00:01:21,040
on the network

45
00:01:21,040 --> 00:01:23,840
um and then

46
00:01:23,840 --> 00:01:25,759
if we didn't have mining the way this

47
00:01:25,759 --> 00:01:27,840
would work was that computer would write

48
00:01:27,840 --> 00:01:30,400
it straight to the blockchain

49
00:01:30,400 --> 00:01:31,840
to the shared file

50
00:01:31,840 --> 00:01:33,439
and then what they would do they would

51
00:01:33,439 --> 00:01:34,960
pass on that

52
00:01:34,960 --> 00:01:37,119
transaction that piece of data onto the

53
00:01:37,119 --> 00:01:38,960
nodes they're connected to and they will

54
00:01:38,960 --> 00:01:40,640
write it to their file

55
00:01:40,640 --> 00:01:42,880
and so on and so on until that

56
00:01:42,880 --> 00:01:45,680
transaction has propagated

57
00:01:45,680 --> 00:01:48,320
uh the entire network

58
00:01:48,320 --> 00:01:50,159
and written it to their shared file so

59
00:01:50,159 --> 00:01:52,159
that would be a simple way of you know

60
00:01:52,159 --> 00:01:54,079
having a shared file or shared ledger

61
00:01:54,079 --> 00:01:56,079
transactions

62
00:01:56,079 --> 00:01:57,439
and then

63
00:01:57,439 --> 00:01:58,799
when everyone's updated their copy of

64
00:01:58,799 --> 00:02:01,200
the file you know um

65
00:02:01,200 --> 00:02:02,960
the ownership then as that of that

66
00:02:02,960 --> 00:02:05,280
bitcoin has changed from one person to

67
00:02:05,280 --> 00:02:06,719
the next person

68
00:02:06,719 --> 00:02:09,038
and that'll be a simple transaction

69
00:02:09,038 --> 00:02:11,120
um but there's a problem um that needs

70
00:02:11,120 --> 00:02:14,000
to be solved if you do it this way

71
00:02:14,000 --> 00:02:15,200
um

72
00:02:15,200 --> 00:02:17,440
let's color this man in green um what

73
00:02:17,440 --> 00:02:18,560
you can do

74
00:02:18,560 --> 00:02:20,959
is you can create a transaction to send

75
00:02:20,959 --> 00:02:22,560
the bitcoin to this person

76
00:02:22,560 --> 00:02:24,239
and insert it into a node on this side

77
00:02:24,239 --> 00:02:25,440
of the network

78
00:02:25,440 --> 00:02:27,599
um but what you can do because it's a

79
00:02:27,599 --> 00:02:29,599
network of connected computers

80
00:02:29,599 --> 00:02:32,720
um you could create a second transaction

81
00:02:32,720 --> 00:02:36,400
um that sends the very same bitcoin

82
00:02:36,400 --> 00:02:38,160
to a different person

83
00:02:38,160 --> 00:02:39,200
so

84
00:02:39,200 --> 00:02:40,720
you've just inserted

85
00:02:40,720 --> 00:02:42,319
two separate transactions into the

86
00:02:42,319 --> 00:02:46,080
network trying to spend the same bitcoin

87
00:02:46,080 --> 00:02:47,360
and you can do this because it's a

88
00:02:47,360 --> 00:02:49,200
network

89
00:02:49,200 --> 00:02:50,959
so what will happen from there

90
00:02:50,959 --> 00:02:53,280
is these two transactions will start

91
00:02:53,280 --> 00:02:55,200
propagating the network

92
00:02:55,200 --> 00:02:56,480
and the computers on this side as you

93
00:02:56,480 --> 00:02:57,280
can see

94
00:02:57,280 --> 00:02:59,760
they have received this red transaction

95
00:02:59,760 --> 00:03:01,599
and the second one but the committee's

96
00:03:01,599 --> 00:03:03,120
on this side they've received the green

97
00:03:03,120 --> 00:03:04,640
transaction

98
00:03:04,640 --> 00:03:05,920
uh when

99
00:03:05,920 --> 00:03:08,239
this computer here tries to pass on the

100
00:03:08,239 --> 00:03:10,400
green transaction to this computer um

101
00:03:10,400 --> 00:03:12,239
this computer has already received the

102
00:03:12,239 --> 00:03:14,400
red transaction spending that this

103
00:03:14,400 --> 00:03:15,440
bitcoin

104
00:03:15,440 --> 00:03:17,840
so they would reject it which is good

105
00:03:17,840 --> 00:03:19,360
but then you still have the problem then

106
00:03:19,360 --> 00:03:20,239
of

107
00:03:20,239 --> 00:03:22,800
um these two conflicting transactions on

108
00:03:22,800 --> 00:03:24,800
the network or basically

109
00:03:24,800 --> 00:03:26,560
um if you look at the network as a whole

110
00:03:26,560 --> 00:03:28,720
or this file as a whole

111
00:03:28,720 --> 00:03:31,360
um who does this bitcoin belong to now

112
00:03:31,360 --> 00:03:34,640
so if you were to run bitcoin this way

113
00:03:34,640 --> 00:03:35,680
and

114
00:03:35,680 --> 00:03:36,640
write

115
00:03:36,640 --> 00:03:38,720
transactions directly to the file you

116
00:03:38,720 --> 00:03:42,400
could create this double spend problem

117
00:03:42,400 --> 00:03:45,360
so basically bitcoin solves this problem

118
00:03:45,360 --> 00:03:47,280
of not having

119
00:03:47,280 --> 00:03:49,120
conflicting transactions written to the

120
00:03:49,120 --> 00:03:51,599
blockchain or to this shared file

121
00:03:51,599 --> 00:03:53,280
and that is what mining is

122
00:03:53,280 --> 00:03:56,319
so the way bitcoin solves this

123
00:03:56,319 --> 00:03:58,239
and this is really this solution now is

124
00:03:58,239 --> 00:04:00,159
what makes bitcoin interesting because

125
00:04:00,159 --> 00:04:02,000
we've had this technology before we're

126
00:04:02,000 --> 00:04:04,000
going to have gone

127
00:04:04,000 --> 00:04:06,720
do a question

128
00:04:10,640 --> 00:04:15,480
okay okay did you miss anything

129
00:04:17,279 --> 00:04:18,880
okay

130
00:04:18,880 --> 00:04:20,000
okay

131
00:04:20,000 --> 00:04:21,199
um

132
00:04:21,199 --> 00:04:24,560
so bitcoin solves this uh problem

133
00:04:24,560 --> 00:04:26,240
of having

134
00:04:26,240 --> 00:04:28,320
you know um writing two conflicting

135
00:04:28,320 --> 00:04:30,880
transactions to a shared file

136
00:04:30,880 --> 00:04:33,199
uh and this is what makes bitcoin um

137
00:04:33,199 --> 00:04:34,720
interesting and this is what the sort of

138
00:04:34,720 --> 00:04:37,199
i suppose the invention of bitcoin is

139
00:04:37,199 --> 00:04:38,960
um so the way bitcoin solves this double

140
00:04:38,960 --> 00:04:42,800
spend um problem is that it gives um

141
00:04:42,800 --> 00:04:44,479
every computer running the bitcoin

142
00:04:44,479 --> 00:04:47,280
program um some temporary memory uh

143
00:04:47,280 --> 00:04:49,280
called the memory pool

144
00:04:49,280 --> 00:04:50,960
so what will happen is

145
00:04:50,960 --> 00:04:53,280
you can't stop this double spend attack

146
00:04:53,280 --> 00:04:56,000
but what will happen is um the person

147
00:04:56,000 --> 00:04:57,759
will insert a transaction into this

148
00:04:57,759 --> 00:05:00,720
computer this green transaction

149
00:05:00,720 --> 00:05:02,400
and then they can go over here and do

150
00:05:02,400 --> 00:05:04,000
the same you know double spend attack

151
00:05:04,000 --> 00:05:05,680
again and insert this second red

152
00:05:05,680 --> 00:05:07,600
transaction into this computer

153
00:05:07,600 --> 00:05:08,400
um

154
00:05:08,400 --> 00:05:11,199
but obviously these two transactions

155
00:05:11,199 --> 00:05:12,880
aren't written directly to the file they

156
00:05:12,880 --> 00:05:15,759
get stored in temporary memory first

157
00:05:15,759 --> 00:05:16,479
so

158
00:05:16,479 --> 00:05:18,400
um again the same thing happens both

159
00:05:18,400 --> 00:05:20,560
transactions propagate the network and

160
00:05:20,560 --> 00:05:23,039
this one will eject the green one

161
00:05:23,039 --> 00:05:24,639
because they have already received the

162
00:05:24,639 --> 00:05:25,919
red one

163
00:05:25,919 --> 00:05:28,800
um and so there we are um

164
00:05:28,800 --> 00:05:30,639
both transactions on the network but

165
00:05:30,639 --> 00:05:32,000
they're not written to the file yet so

166
00:05:32,000 --> 00:05:34,560
the file is still secure

167
00:05:34,560 --> 00:05:36,880
um what will happen then is um all of

168
00:05:36,880 --> 00:05:40,080
these computers um will work to try and

169
00:05:40,080 --> 00:05:42,080
get the transactions from their memory

170
00:05:42,080 --> 00:05:42,880
pool

171
00:05:42,880 --> 00:05:44,880
onto the file

172
00:05:44,880 --> 00:05:46,720
um so they're all competing basically to

173
00:05:46,720 --> 00:05:49,120
be the first one to get their memory

174
00:05:49,120 --> 00:05:51,440
pool transactions added

175
00:05:51,440 --> 00:05:53,199
onto the top of the file

176
00:05:53,199 --> 00:05:55,280
so let's say this one is the first one

177
00:05:55,280 --> 00:05:56,880
that's able to do it

178
00:05:56,880 --> 00:05:58,800
and they add their transactions

179
00:05:58,800 --> 00:06:00,400
from their memory pool onto the file

180
00:06:00,400 --> 00:06:03,360
like so and when they've done that

181
00:06:03,360 --> 00:06:05,840
and they will pass on the updated copy

182
00:06:05,840 --> 00:06:07,759
of the file to everyone else they're

183
00:06:07,759 --> 00:06:08,880
connected to

184
00:06:08,880 --> 00:06:11,039
and they will update their copies

185
00:06:11,039 --> 00:06:13,280
and this node here

186
00:06:13,280 --> 00:06:14,800
because they've got this conflicting

187
00:06:14,800 --> 00:06:16,560
green transaction in their memory pool

188
00:06:16,560 --> 00:06:18,560
but they've just received this red

189
00:06:18,560 --> 00:06:19,680
transaction

190
00:06:19,680 --> 00:06:22,000
spending the same bitcoins um they will

191
00:06:22,000 --> 00:06:23,520
kick out the screen transaction from

192
00:06:23,520 --> 00:06:25,440
their memory pool so this memory pool is

193
00:06:25,440 --> 00:06:27,280
like a waiting area or like a clearing

194
00:06:27,280 --> 00:06:28,880
house

195
00:06:28,880 --> 00:06:30,880
and they've received this

196
00:06:30,880 --> 00:06:33,120
red transaction in in the in the updated

197
00:06:33,120 --> 00:06:34,560
file so i'll kick out this conflicting

198
00:06:34,560 --> 00:06:35,360
one

199
00:06:35,360 --> 00:06:37,199
and then this node will pass on the

200
00:06:37,199 --> 00:06:39,520
updated copy to these nodes also and

201
00:06:39,520 --> 00:06:41,199
they will do the same thing they'll kick

202
00:06:41,199 --> 00:06:43,360
out any conflicting transactions

203
00:06:43,360 --> 00:06:46,000
from their memory pool

204
00:06:46,000 --> 00:06:48,240
so that's how you solve the the problem

205
00:06:48,240 --> 00:06:50,080
of having two conflicting transactions

206
00:06:50,080 --> 00:06:52,319
on the network you just literally have

207
00:06:52,319 --> 00:06:54,080
uh a waiting area

208
00:06:54,080 --> 00:06:56,720
and all of the nodes compete to try and

209
00:06:56,720 --> 00:06:59,759
add their transactions onto the file

210
00:06:59,759 --> 00:07:01,039
um

211
00:07:01,039 --> 00:07:04,560
like so and there we are this person now

212
00:07:04,560 --> 00:07:06,080
has the bitcoin

213
00:07:06,080 --> 00:07:07,759
and so this proceed there's basically

214
00:07:07,759 --> 00:07:10,800
this process of every node competing to

215
00:07:10,800 --> 00:07:12,080
try and get their transactions from

216
00:07:12,080 --> 00:07:14,240
their memory pool onto the file is

217
00:07:14,240 --> 00:07:15,759
called mining and that's why i'm going

218
00:07:15,759 --> 00:07:17,280
to explain how it works now this you

219
00:07:17,280 --> 00:07:18,639
know getting these transactions onto

220
00:07:18,639 --> 00:07:20,800
here

221
00:07:20,800 --> 00:07:23,039
is any questions about that so far

222
00:07:23,039 --> 00:07:24,880
not really but one thing to note here is

223
00:07:24,880 --> 00:07:25,759
that

224
00:07:25,759 --> 00:07:27,840
every node in the network is not

225
00:07:27,840 --> 00:07:29,840
necessarily mining oh yes that's true

226
00:07:29,840 --> 00:07:32,240
yeah yeah i just made a very simple like

227
00:07:32,240 --> 00:07:33,840
diagram trying to

228
00:07:33,840 --> 00:07:36,080
um yeah but

229
00:07:36,080 --> 00:07:37,280
yes so

230
00:07:37,280 --> 00:07:39,360
some of these might not be mining

231
00:07:39,360 --> 00:07:40,720
um you can just run a node that will

232
00:07:40,720 --> 00:07:43,360
relay the blocks and transactions

233
00:07:43,360 --> 00:07:45,840
um yeah but in this particular

234
00:07:45,840 --> 00:07:47,680
simplified diagram everyone's trying to

235
00:07:47,680 --> 00:07:50,400
mine but obviously

236
00:07:50,400 --> 00:07:53,360
yeah so yeah let's say we have a node

237
00:07:53,360 --> 00:07:56,160
that is not binding so if it gets a

238
00:07:56,160 --> 00:07:58,479
block

239
00:07:58,720 --> 00:08:01,280
which has a transaction

240
00:08:01,280 --> 00:08:03,039
and a conflicting transaction in the

241
00:08:03,039 --> 00:08:05,520
memory pool it will take it out um yeah

242
00:08:05,520 --> 00:08:07,120
all this relaying of blocks and

243
00:08:07,120 --> 00:08:09,360
transactions a node will do this

244
00:08:09,360 --> 00:08:11,520
but a minor just as this

245
00:08:11,520 --> 00:08:13,199
latter part of trying to add the

246
00:08:13,199 --> 00:08:15,599
transactions from the memory pool that

247
00:08:15,599 --> 00:08:17,759
that is a minor this part here but you

248
00:08:17,759 --> 00:08:21,440
can be a node but you don't have to mine

249
00:08:21,440 --> 00:08:25,639
um okay is that right

250
00:08:26,319 --> 00:08:29,599
okay so that's the intro done

251
00:08:29,599 --> 00:08:31,840
so the next part now is explaining what

252
00:08:31,840 --> 00:08:33,519
this um

253
00:08:33,519 --> 00:08:35,919
hash function is so then i'll cover how

254
00:08:35,919 --> 00:08:38,880
bitcoin mining works

255
00:08:38,880 --> 00:08:41,279
um right so a hash function

256
00:08:41,279 --> 00:08:43,279
but a hash function is just like a small

257
00:08:43,279 --> 00:08:45,920
um computer program um that does

258
00:08:45,920 --> 00:08:48,320
that's quite useful um but the way it

259
00:08:48,320 --> 00:08:51,200
works is you you can have some data so

260
00:08:51,200 --> 00:08:53,360
this is letter a and number one and you

261
00:08:53,360 --> 00:08:55,600
can insert it into the hash function

262
00:08:55,600 --> 00:08:58,000
and the hash function will basically

263
00:08:58,000 --> 00:08:59,200
scramble it

264
00:08:59,200 --> 00:09:02,560
and produce a random

265
00:09:02,560 --> 00:09:06,160
string of data as a result

266
00:09:06,320 --> 00:09:07,360
and

267
00:09:07,360 --> 00:09:08,800
the useful property about the hash

268
00:09:08,800 --> 00:09:10,560
function is that you can put the same

269
00:09:10,560 --> 00:09:12,640
data into it and it will always spit out

270
00:09:12,640 --> 00:09:14,240
the same result so basically it will

271
00:09:14,240 --> 00:09:16,480
scramble it in the same way to produce

272
00:09:16,480 --> 00:09:17,279
this

273
00:09:17,279 --> 00:09:19,600
random

274
00:09:19,600 --> 00:09:22,080
string of data

275
00:09:22,080 --> 00:09:23,600
and this string of data will always be

276
00:09:23,600 --> 00:09:26,880
the same size which is 32 bytes or 64

277
00:09:26,880 --> 00:09:28,480
characters because there are two

278
00:09:28,480 --> 00:09:31,360
characters per byte

279
00:09:31,360 --> 00:09:32,560
um so

280
00:09:32,560 --> 00:09:34,640
if you were to make a tiny adjustment to

281
00:09:34,640 --> 00:09:36,080
the

282
00:09:36,080 --> 00:09:37,279
data you're putting into the hash

283
00:09:37,279 --> 00:09:38,160
function

284
00:09:38,160 --> 00:09:40,560
so from here just go from a one to a two

285
00:09:40,560 --> 00:09:43,200
just a tiny adjustment put that in and

286
00:09:43,200 --> 00:09:45,519
the result would be completely different

287
00:09:45,519 --> 00:09:47,600
so we've only made a tiny adjustment but

288
00:09:47,600 --> 00:09:49,360
the result of the hash function is

289
00:09:49,360 --> 00:09:51,440
wildly different

290
00:09:51,440 --> 00:09:54,399
um and again put a3 into it

291
00:09:54,399 --> 00:09:55,839
tiny adjustment again

292
00:09:55,839 --> 00:09:57,440
but the result is completely different

293
00:09:57,440 --> 00:09:58,640
again

294
00:09:58,640 --> 00:10:00,240
and an important part about a hash

295
00:10:00,240 --> 00:10:01,839
function as well

296
00:10:01,839 --> 00:10:03,120
is that if you don't know what the

297
00:10:03,120 --> 00:10:06,880
result um is beforehand there's no way

298
00:10:06,880 --> 00:10:09,600
you can predict what you know a2 is

299
00:10:09,600 --> 00:10:11,200
going to spit out

300
00:10:11,200 --> 00:10:11,920
so

301
00:10:11,920 --> 00:10:13,600
if you don't know what this is already

302
00:10:13,600 --> 00:10:15,760
is then there's no way you can sort of

303
00:10:15,760 --> 00:10:18,399
figure out what the results going to be

304
00:10:18,399 --> 00:10:19,440
which is

305
00:10:19,440 --> 00:10:20,640
useful

306
00:10:20,640 --> 00:10:22,959
as we'll come to see in a moment

307
00:10:22,959 --> 00:10:24,160
um

308
00:10:24,160 --> 00:10:25,760
also lastly

309
00:10:25,760 --> 00:10:26,800
even though

310
00:10:26,800 --> 00:10:28,160
this looks like a random well it's a

311
00:10:28,160 --> 00:10:30,079
random string of data it's got like the

312
00:10:30,079 --> 00:10:31,440
letters f

313
00:10:31,440 --> 00:10:34,959
e a basically a b c d e and f in there

314
00:10:34,959 --> 00:10:36,720
and these can actually be converted into

315
00:10:36,720 --> 00:10:37,760
numbers

316
00:10:37,760 --> 00:10:39,519
um and that's because

317
00:10:39,519 --> 00:10:41,920
um we are used to using the

318
00:10:41,920 --> 00:10:44,839
decimal uh format for numbers which uses

319
00:10:44,839 --> 00:10:48,320
the numbers zero to nine

320
00:10:48,320 --> 00:10:51,279
but you also have a number number format

321
00:10:51,279 --> 00:10:52,880
called hexadecimal which is just the

322
00:10:52,880 --> 00:10:55,760
same numbers but also with a b c d e and

323
00:10:55,760 --> 00:10:57,920
f and they are

324
00:10:57,920 --> 00:10:59,360
when you translate them over when you

325
00:10:59,360 --> 00:11:01,680
convert them over they just

326
00:11:01,680 --> 00:11:04,240
looks like this

327
00:11:04,480 --> 00:11:05,519
so

328
00:11:05,519 --> 00:11:07,279
this is called decimal because it uses

329
00:11:07,279 --> 00:11:08,160
um

330
00:11:08,160 --> 00:11:12,720
10 and deci in means 10 i think in latin

331
00:11:12,720 --> 00:11:15,040
then hexadecimal hexa like a hexagon six

332
00:11:15,040 --> 00:11:18,800
sides deci 10 6 10 16.

333
00:11:18,800 --> 00:11:19,519
so

334
00:11:19,519 --> 00:11:21,920
basically this is what we use as humans

335
00:11:21,920 --> 00:11:23,920
but computers are very happy to read

336
00:11:23,920 --> 00:11:26,560
numbers in hexadecimal format

337
00:11:26,560 --> 00:11:28,560
so basically um

338
00:11:28,560 --> 00:11:30,800
with a hash function you put data in and

339
00:11:30,800 --> 00:11:34,640
it spits out a random number as a result

340
00:11:34,640 --> 00:11:36,000
but

341
00:11:36,000 --> 00:11:37,920
so if you see um

342
00:11:37,920 --> 00:11:41,920
an like a string like this nope in um

343
00:11:41,920 --> 00:11:43,760
hex decimal format just remember that

344
00:11:43,760 --> 00:11:46,480
it's a random number

345
00:11:46,480 --> 00:11:47,760
does that make sense everything makes

346
00:11:47,760 --> 00:11:49,680
sense there

347
00:11:49,680 --> 00:11:51,360
all right brilliant so that was a hash

348
00:11:51,360 --> 00:11:52,240
function

349
00:11:52,240 --> 00:11:54,399
um just a little tool that spits out

350
00:11:54,399 --> 00:11:58,240
random data um if i quickly show you

351
00:11:58,240 --> 00:11:59,760
i don't think you see this

352
00:11:59,760 --> 00:12:02,800
if you can read the text but um

353
00:12:02,800 --> 00:12:03,760
if you can

354
00:12:03,760 --> 00:12:06,959
like a hash function is available in um

355
00:12:06,959 --> 00:12:08,720
lots of programming languages so for

356
00:12:08,720 --> 00:12:11,360
example in php um there's a function

357
00:12:11,360 --> 00:12:12,800
called hash

358
00:12:12,800 --> 00:12:15,200
and then you can tell it um that's gonna

359
00:12:15,200 --> 00:12:16,720
be wrong there

360
00:12:16,720 --> 00:12:18,800
and then you can tell it um

361
00:12:18,800 --> 00:12:20,560
which hash function you wanna use so

362
00:12:20,560 --> 00:12:22,079
sha256

363
00:12:22,079 --> 00:12:23,920
that is the one that's used in bitcoin

364
00:12:23,920 --> 00:12:26,000
um which stands for simple hashing

365
00:12:26,000 --> 00:12:27,920
algorithm 256

366
00:12:27,920 --> 00:12:29,959
or 265

367
00:12:29,959 --> 00:12:32,800
256 bits which is like the size of the

368
00:12:32,800 --> 00:12:34,480
result it spits out and then you can

369
00:12:34,480 --> 00:12:36,560
just put the

370
00:12:36,560 --> 00:12:38,800
uh what you want to hash into it

371
00:12:38,800 --> 00:12:41,440
what's going on

372
00:12:51,200 --> 00:12:53,680
there we are so that's the result there

373
00:12:53,680 --> 00:12:55,279
so you can use a hash function in any

374
00:12:55,279 --> 00:12:57,440
programming language um i've just showed

375
00:12:57,440 --> 00:12:59,920
how to use it here in php

376
00:12:59,920 --> 00:13:00,959
um

377
00:13:00,959 --> 00:13:04,000
in ruby just for

378
00:13:04,000 --> 00:13:05,680
uh

379
00:13:05,680 --> 00:13:08,240
be complete um

380
00:13:08,240 --> 00:13:10,160
it's included in the digest

381
00:13:10,160 --> 00:13:13,040
library so you can go and put

382
00:13:13,040 --> 00:13:15,519
digest

383
00:13:15,519 --> 00:13:18,480
256 then we want the hexadecimal

384
00:13:18,480 --> 00:13:21,839
digest digest is just another um term

385
00:13:21,839 --> 00:13:24,240
for the result that gets spat out from a

386
00:13:24,240 --> 00:13:26,000
hash function

387
00:13:26,000 --> 00:13:28,560
so we're gonna put a1 into there

388
00:13:28,560 --> 00:13:30,639
and there we have the same thing

389
00:13:30,639 --> 00:13:31,839
so

390
00:13:31,839 --> 00:13:33,760
hash function just available in lots of

391
00:13:33,760 --> 00:13:36,560
programming languages

392
00:13:37,279 --> 00:13:39,279
um okay

393
00:13:39,279 --> 00:13:40,720
now i'll move on to

394
00:13:40,720 --> 00:13:41,839
um

395
00:13:41,839 --> 00:13:44,079
the basics of how mining works so i'll

396
00:13:44,079 --> 00:13:45,760
just run through giving a quick example

397
00:13:45,760 --> 00:13:47,279
of how

398
00:13:47,279 --> 00:13:49,360
this

399
00:13:49,360 --> 00:13:51,279
process here of getting the transactions

400
00:13:51,279 --> 00:13:53,040
from the memory pool onto the blockchain

401
00:13:53,040 --> 00:13:54,880
works

402
00:13:54,880 --> 00:13:56,320
right

403
00:13:56,320 --> 00:13:58,639
so basics are mining

404
00:13:58,639 --> 00:14:00,320
here we have the net here we have the

405
00:14:00,320 --> 00:14:02,079
network again all the transactions the

406
00:14:02,079 --> 00:14:05,279
memory pool yep sorry

407
00:14:07,440 --> 00:14:09,440
okay um okay

408
00:14:09,440 --> 00:14:11,199
thanks just if it happens again just let

409
00:14:11,199 --> 00:14:13,680
me know and i'll

410
00:14:13,680 --> 00:14:15,600
um so again

411
00:14:15,600 --> 00:14:16,399
um

412
00:14:16,399 --> 00:14:17,600
we're going to look inside now this

413
00:14:17,600 --> 00:14:19,199
computer this um

414
00:14:19,199 --> 00:14:20,880
node here is a minor so we're going to

415
00:14:20,880 --> 00:14:22,800
look inside it and see how it mines the

416
00:14:22,800 --> 00:14:25,120
transactions from its memory pool onto

417
00:14:25,120 --> 00:14:27,600
its file

418
00:14:28,480 --> 00:14:31,839
right so

419
00:14:32,240 --> 00:14:34,880
you still there

420
00:14:38,160 --> 00:14:39,600
hello

421
00:14:39,600 --> 00:14:41,680
are you still okay right yeah okay right

422
00:14:41,680 --> 00:14:44,639
um so this is looking inside a bitcoin

423
00:14:44,639 --> 00:14:46,079
miner

424
00:14:46,079 --> 00:14:47,680
so this is the memory pool it's got the

425
00:14:47,680 --> 00:14:49,680
red transaction in there

426
00:14:49,680 --> 00:14:52,240
transaction in there um but with a

427
00:14:52,240 --> 00:14:54,240
memory pool you can have much more than

428
00:14:54,240 --> 00:14:56,639
one transaction in there so let's say

429
00:14:56,639 --> 00:14:58,399
this memory pool has got like you know

430
00:14:58,399 --> 00:14:59,920
quite a few transactions already in

431
00:14:59,920 --> 00:15:00,959
there

432
00:15:00,959 --> 00:15:03,839
and so what a miner will do um they will

433
00:15:03,839 --> 00:15:05,279
create a

434
00:15:05,279 --> 00:15:08,079
container called a candidate candidate

435
00:15:08,079 --> 00:15:09,040
block

436
00:15:09,040 --> 00:15:10,560
um which is just a container for

437
00:15:10,560 --> 00:15:12,240
transactions

438
00:15:12,240 --> 00:15:13,680
so what they'll do

439
00:15:13,680 --> 00:15:16,000
they will fill this candidate block

440
00:15:16,000 --> 00:15:17,920
up with transactions from their memory

441
00:15:17,920 --> 00:15:18,800
pool

442
00:15:18,800 --> 00:15:21,519
and like so

443
00:15:21,519 --> 00:15:23,680
and then they will try and add this

444
00:15:23,680 --> 00:15:26,480
block of transactions onto the file onto

445
00:15:26,480 --> 00:15:29,040
the blockchain

446
00:15:29,040 --> 00:15:30,480
so

447
00:15:30,480 --> 00:15:32,240
how do they get this block of this

448
00:15:32,240 --> 00:15:34,560
candidate block that they've built onto

449
00:15:34,560 --> 00:15:36,880
the blockchain

450
00:15:36,880 --> 00:15:38,880
well the first thing they do

451
00:15:38,880 --> 00:15:40,560
they construct what's called a block

452
00:15:40,560 --> 00:15:41,839
header

453
00:15:41,839 --> 00:15:44,000
um which is just like a summary of all

454
00:15:44,000 --> 00:15:45,600
the data inside the block all the

455
00:15:45,600 --> 00:15:47,839
transactions in the block

456
00:15:47,839 --> 00:15:49,680
um so in that block header you have

457
00:15:49,680 --> 00:15:51,199
something called a version which is like

458
00:15:51,199 --> 00:15:52,959
a version number for the block for the

459
00:15:52,959 --> 00:15:54,800
structure of the data so let's say

460
00:15:54,800 --> 00:15:56,639
that's one

461
00:15:56,639 --> 00:15:59,199
and they will also have

462
00:15:59,199 --> 00:16:00,560
some information

463
00:16:00,560 --> 00:16:01,920
called the previous block or the

464
00:16:01,920 --> 00:16:03,680
previous block hash

465
00:16:03,680 --> 00:16:05,600
and the way that works is

466
00:16:05,600 --> 00:16:08,800
let's say this is the blockchain um

467
00:16:08,800 --> 00:16:10,639
this block this candidate block they're

468
00:16:10,639 --> 00:16:12,959
building it has to build on top of one

469
00:16:12,959 --> 00:16:14,320
of these blocks

470
00:16:14,320 --> 00:16:18,639
so what a miner will do is they will um

471
00:16:18,639 --> 00:16:20,160
include the

472
00:16:20,160 --> 00:16:22,399
hash or the block hash which is like an

473
00:16:22,399 --> 00:16:23,680
id number

474
00:16:23,680 --> 00:16:25,040
for a block

475
00:16:25,040 --> 00:16:28,079
of the one they want to build on top of

476
00:16:28,079 --> 00:16:29,360
so like so

477
00:16:29,360 --> 00:16:30,240
so

478
00:16:30,240 --> 00:16:32,800
in here they will this is the block hash

479
00:16:32,800 --> 00:16:34,000
for this block

480
00:16:34,000 --> 00:16:35,519
so this just says which block they want

481
00:16:35,519 --> 00:16:37,360
to build on top of because every miner

482
00:16:37,360 --> 00:16:39,120
basically wants to build onto the top of

483
00:16:39,120 --> 00:16:41,759
the blockchain

484
00:16:42,320 --> 00:16:43,279
um

485
00:16:43,279 --> 00:16:45,839
merkel route now a miracle route is just

486
00:16:45,839 --> 00:16:47,040
the

487
00:16:47,040 --> 00:16:48,720
basically if your hash

488
00:16:48,720 --> 00:16:52,639
um all the transaction ids together

489
00:16:52,639 --> 00:16:55,199
um over and over again you'll end up

490
00:16:55,199 --> 00:16:57,440
with a single hash at the end and this

491
00:16:57,440 --> 00:16:59,120
is called the merkle root

492
00:16:59,120 --> 00:17:00,240
like so

493
00:17:00,240 --> 00:17:02,639
and basically this is like a

494
00:17:02,639 --> 00:17:04,959
fingerprint like a

495
00:17:04,959 --> 00:17:07,599
digital fingerprint that summarizes all

496
00:17:07,599 --> 00:17:11,199
the transactions in the block

497
00:17:11,199 --> 00:17:12,160
um

498
00:17:12,160 --> 00:17:14,319
so again you know this block header it's

499
00:17:14,319 --> 00:17:17,119
like a creates a unique

500
00:17:17,119 --> 00:17:18,720
fingerprint for all the data in the

501
00:17:18,720 --> 00:17:21,839
block but using a lot less data than all

502
00:17:21,839 --> 00:17:24,160
of the transaction data combined so

503
00:17:24,160 --> 00:17:26,959
maybe uh if you can

504
00:17:26,959 --> 00:17:28,720
you know speak a little about the

505
00:17:28,720 --> 00:17:30,720
miracle road because i've

506
00:17:30,720 --> 00:17:32,799
not really heard too much about it yeah

507
00:17:32,799 --> 00:17:34,160
yeah um

508
00:17:34,160 --> 00:17:36,400
are you like hashing like

509
00:17:36,400 --> 00:17:38,240
every other transaction together and

510
00:17:38,240 --> 00:17:39,360
then

511
00:17:39,360 --> 00:17:40,640
hashing

512
00:17:40,640 --> 00:17:42,960
that those results it looks like um i'm

513
00:17:42,960 --> 00:17:44,720
gonna actually cover that in the next

514
00:17:44,720 --> 00:17:47,440
technical part here but just for now as

515
00:17:47,440 --> 00:17:48,880
long as it makes sense that this merkel

516
00:17:48,880 --> 00:17:50,799
route provides you with like a

517
00:17:50,799 --> 00:17:52,720
unique short summary of all the

518
00:17:52,720 --> 00:17:54,720
transactions in the block

519
00:17:54,720 --> 00:17:56,160
okay and i'll cover how that works and

520
00:17:56,160 --> 00:17:57,520
why

521
00:17:57,520 --> 00:18:00,000
america is used in a moment but a good

522
00:18:00,000 --> 00:18:00,880
question

523
00:18:00,880 --> 00:18:02,240
anyway so

524
00:18:02,240 --> 00:18:04,000
there we have

525
00:18:04,000 --> 00:18:05,440
the block header i haven't covered all

526
00:18:05,440 --> 00:18:07,600
the block header data but this is the

527
00:18:07,600 --> 00:18:09,520
most important stuff

528
00:18:09,520 --> 00:18:12,400
um so there we have a block header

529
00:18:12,400 --> 00:18:14,880
the next step then is to put this block

530
00:18:14,880 --> 00:18:17,039
header data into a hash function into

531
00:18:17,039 --> 00:18:19,919
the sha 250 56 hash function

532
00:18:19,919 --> 00:18:21,919
and then that will presume

533
00:18:21,919 --> 00:18:23,200
produce

534
00:18:23,200 --> 00:18:24,240
um

535
00:18:24,240 --> 00:18:24,960
a

536
00:18:24,960 --> 00:18:27,600
random number as a result

537
00:18:27,600 --> 00:18:29,440
and this is called the block hash a

538
00:18:29,440 --> 00:18:31,919
block hash

539
00:18:32,000 --> 00:18:34,480
um any questions so far

540
00:18:34,480 --> 00:18:35,919
okay um

541
00:18:35,919 --> 00:18:38,559
and so okay that's all well and good but

542
00:18:38,559 --> 00:18:40,320
why would a minor do this

543
00:18:40,320 --> 00:18:42,400
um well um

544
00:18:42,400 --> 00:18:43,760
or how

545
00:18:43,760 --> 00:18:46,240
does this help to get the block mined

546
00:18:46,240 --> 00:18:47,600
onto the blockchain

547
00:18:47,600 --> 00:18:50,320
well if this block hash the result of

548
00:18:50,320 --> 00:18:52,320
this putting the block header into the

549
00:18:52,320 --> 00:18:54,960
hash function produces a block hash that

550
00:18:54,960 --> 00:18:58,080
is below a target value

551
00:18:58,080 --> 00:19:00,160
um

552
00:19:00,160 --> 00:19:02,320
like so so let's say this is the current

553
00:19:02,320 --> 00:19:03,280
target

554
00:19:03,280 --> 00:19:06,640
value which is a

555
00:19:07,200 --> 00:19:09,280
number which is like a number internal

556
00:19:09,280 --> 00:19:12,480
to every uh bitcoin

557
00:19:12,480 --> 00:19:15,120
node and they all have a they all

558
00:19:15,120 --> 00:19:16,480
calculate their own

559
00:19:16,480 --> 00:19:19,600
it's like a shared target value that is

560
00:19:19,600 --> 00:19:22,880
calculated in sync with every other node

561
00:19:22,880 --> 00:19:23,840
um

562
00:19:23,840 --> 00:19:25,679
if they can get

563
00:19:25,679 --> 00:19:28,720
their block hash to be below this then

564
00:19:28,720 --> 00:19:30,320
the block will get added onto the

565
00:19:30,320 --> 00:19:32,480
blockchain and the block is solved

566
00:19:32,480 --> 00:19:34,320
basically

567
00:19:34,320 --> 00:19:35,919
so

568
00:19:35,919 --> 00:19:38,480
so far with this a first attempt

569
00:19:38,480 --> 00:19:40,160
um this number here

570
00:19:40,160 --> 00:19:41,919
as you can see this target value starts

571
00:19:41,919 --> 00:19:43,840
with a certain number of zeros but this

572
00:19:43,840 --> 00:19:45,600
one is obviously a bigger number than

573
00:19:45,600 --> 00:19:48,160
that so it's not below the target so

574
00:19:48,160 --> 00:19:50,080
this first attempt at trying to add this

575
00:19:50,080 --> 00:19:51,039
block

576
00:19:51,039 --> 00:19:54,160
onto the blockchain has failed like so

577
00:19:54,160 --> 00:19:55,039
so

578
00:19:55,039 --> 00:19:57,280
um what happens then is a miner doesn't

579
00:19:57,280 --> 00:19:58,240
give up

580
00:19:58,240 --> 00:19:59,200
um

581
00:19:59,200 --> 00:20:00,880
in the block header

582
00:20:00,880 --> 00:20:02,880
there's space

583
00:20:02,880 --> 00:20:04,080
um

584
00:20:04,080 --> 00:20:06,480
there's an extra field called the nonce

585
00:20:06,480 --> 00:20:08,320
which stands for um

586
00:20:08,320 --> 00:20:11,039
a number used once

587
00:20:11,039 --> 00:20:12,400
um

588
00:20:12,400 --> 00:20:13,840
and this is like sort of like an open

589
00:20:13,840 --> 00:20:16,240
field that a miner is free to put their

590
00:20:16,240 --> 00:20:20,240
own um number in or data in so what that

591
00:20:20,240 --> 00:20:22,960
means is if this first attempt of the

592
00:20:22,960 --> 00:20:24,480
block header fails

593
00:20:24,480 --> 00:20:26,799
they can change the nonce value or

594
00:20:26,799 --> 00:20:28,559
change the data in the nonce so for

595
00:20:28,559 --> 00:20:31,120
example um the first attempt might they

596
00:20:31,120 --> 00:20:33,520
might have had the number zero in there

597
00:20:33,520 --> 00:20:35,600
then if that fails they'll change the

598
00:20:35,600 --> 00:20:37,840
nonce and then push the block header

599
00:20:37,840 --> 00:20:39,600
through the hash function again

600
00:20:39,600 --> 00:20:41,919
and because we've only made even though

601
00:20:41,919 --> 00:20:43,919
we've only made a small adjustment like

602
00:20:43,919 --> 00:20:44,880
i showed you earlier with a hash

603
00:20:44,880 --> 00:20:47,039
function um small adjustments can

604
00:20:47,039 --> 00:20:50,080
produce completely different results

605
00:20:50,080 --> 00:20:52,559
so a minor basically will construct a

606
00:20:52,559 --> 00:20:54,720
bloodhead block header and keep changing

607
00:20:54,720 --> 00:20:57,200
this nonce value and hoping that the

608
00:20:57,200 --> 00:20:58,720
result

609
00:20:58,720 --> 00:21:01,280
will find will produce

610
00:21:01,280 --> 00:21:04,159
a block hash below the target value

611
00:21:04,159 --> 00:21:06,880
so literally a minor creates a block

612
00:21:06,880 --> 00:21:08,080
header

613
00:21:08,080 --> 00:21:09,919
adds an answer to the end and it doesn't

614
00:21:09,919 --> 00:21:12,400
work they'll keep incrementing it hoping

615
00:21:12,400 --> 00:21:14,840
to get a low enough block

616
00:21:14,840 --> 00:21:17,679
hash eventually um

617
00:21:17,679 --> 00:21:19,200
if they're lucky just it's just this is

618
00:21:19,200 --> 00:21:21,600
just pure randomness and pure luck

619
00:21:21,600 --> 00:21:22,480
um

620
00:21:22,480 --> 00:21:23,520
they might

621
00:21:23,520 --> 00:21:25,440
um be able to

622
00:21:25,440 --> 00:21:27,520
guess and a nonce

623
00:21:27,520 --> 00:21:29,360
that works that'll produce a block hash

624
00:21:29,360 --> 00:21:30,400
below the target

625
00:21:30,400 --> 00:21:32,640
so here this particular

626
00:21:32,640 --> 00:21:34,640
very high nonce has produced a

627
00:21:34,640 --> 00:21:38,000
successful block hash result

628
00:21:38,000 --> 00:21:39,280
so there we are

629
00:21:39,280 --> 00:21:41,440
so what will happen and then is this

630
00:21:41,440 --> 00:21:43,120
node will add that block onto their

631
00:21:43,120 --> 00:21:46,000
blockchain and they will pass on this

632
00:21:46,000 --> 00:21:48,159
candidate block or this solved candidate

633
00:21:48,159 --> 00:21:49,360
block onto all the nodes they're

634
00:21:49,360 --> 00:21:50,640
connected to

635
00:21:50,640 --> 00:21:52,640
they'll check it and verify it to make

636
00:21:52,640 --> 00:21:54,559
sure that the block header you know

637
00:21:54,559 --> 00:21:55,840
produces a

638
00:21:55,840 --> 00:21:58,000
target below a block cash blow the

639
00:21:58,000 --> 00:21:59,039
target

640
00:21:59,039 --> 00:22:00,880
they'll add it to the file

641
00:22:00,880 --> 00:22:03,280
kick out any conflicting transactions um

642
00:22:03,280 --> 00:22:05,360
that are included in that block

643
00:22:05,360 --> 00:22:06,240
and then

644
00:22:06,240 --> 00:22:08,240
pass on the block like so and they'll do

645
00:22:08,240 --> 00:22:09,360
the same thing

646
00:22:09,360 --> 00:22:10,320
so

647
00:22:10,320 --> 00:22:13,679
that's how um mining works on a basic

648
00:22:13,679 --> 00:22:16,240
level so i had a quick question here

649
00:22:16,240 --> 00:22:18,720
um

650
00:22:18,720 --> 00:22:19,440
so

651
00:22:19,440 --> 00:22:22,240
you're saying that the target value

652
00:22:22,240 --> 00:22:24,559
is

653
00:22:24,840 --> 00:22:28,559
a each node has its own value for the

654
00:22:28,559 --> 00:22:30,480
target value right so

655
00:22:30,480 --> 00:22:32,400
i've thought of this but there is a

656
00:22:32,400 --> 00:22:35,039
possibility that i mine a block which is

657
00:22:35,039 --> 00:22:37,200
below my target value

658
00:22:37,200 --> 00:22:37,919
but

659
00:22:37,919 --> 00:22:40,080
and i give it to my neighboring nodes

660
00:22:40,080 --> 00:22:40,960
and

661
00:22:40,960 --> 00:22:44,400
maybe the target value has changed or

662
00:22:44,400 --> 00:22:46,799
for some reason the other nodes don't

663
00:22:46,799 --> 00:22:49,039
have the same target value

664
00:22:49,039 --> 00:22:51,600
uh is that is that a possibility and how

665
00:22:51,600 --> 00:22:52,559
does that

666
00:22:52,559 --> 00:22:53,760
yeah well i understand the question i

667
00:22:53,760 --> 00:22:55,600
think i am i think i explained the

668
00:22:55,600 --> 00:22:57,600
target um not

669
00:22:57,600 --> 00:22:59,360
great um

670
00:22:59,360 --> 00:23:02,159
let me find out if i

671
00:23:02,159 --> 00:23:03,520
uh

672
00:23:03,520 --> 00:23:06,880
the target um

673
00:23:06,880 --> 00:23:09,760
right um

674
00:23:09,760 --> 00:23:11,919
the target um i'll explain it now

675
00:23:11,919 --> 00:23:13,840
basically the target is there

676
00:23:13,840 --> 00:23:15,039
um

677
00:23:15,039 --> 00:23:17,440
so that

678
00:23:17,520 --> 00:23:19,760
um every 10 minutes

679
00:23:19,760 --> 00:23:23,360
um a new block will be mined

680
00:23:23,360 --> 00:23:24,320
but

681
00:23:24,320 --> 00:23:25,280
if

682
00:23:25,280 --> 00:23:26,559
uh

683
00:23:26,559 --> 00:23:29,600
more computers are hashing a lot faster

684
00:23:29,600 --> 00:23:32,880
um then a block is likely to be mined in

685
00:23:32,880 --> 00:23:34,240
under 10 minutes

686
00:23:34,240 --> 00:23:36,159
so this target value obviously moves up

687
00:23:36,159 --> 00:23:37,760
and down

688
00:23:37,760 --> 00:23:38,559
um

689
00:23:38,559 --> 00:23:40,720
so that a new block is mined every 10

690
00:23:40,720 --> 00:23:42,400
minutes

691
00:23:42,400 --> 00:23:44,480
um yeah

692
00:23:44,480 --> 00:23:46,400
yeah so um so

693
00:23:46,400 --> 00:23:48,080
the target for the very first block when

694
00:23:48,080 --> 00:23:49,679
you first start running bitcoin and the

695
00:23:49,679 --> 00:23:51,600
very first block it was hard coded in at

696
00:23:51,600 --> 00:23:53,919
this value

697
00:23:53,919 --> 00:23:57,039
and then after every uh 2016 blocks or

698
00:23:57,039 --> 00:23:59,200
roughly every two weeks

699
00:23:59,200 --> 00:24:02,000
what will happen is your every

700
00:24:02,000 --> 00:24:02,880
node

701
00:24:02,880 --> 00:24:06,159
they will look at the time it took um

702
00:24:06,159 --> 00:24:09,120
for all the last 2016 blocks to be mined

703
00:24:09,120 --> 00:24:11,200
so the expected time for that is

704
00:24:11,200 --> 00:24:12,559
obviously

705
00:24:12,559 --> 00:24:14,559
20 160

706
00:24:14,559 --> 00:24:16,559
but if the actual time for those blocks

707
00:24:16,559 --> 00:24:18,880
demand was less than that

708
00:24:18,880 --> 00:24:21,120
then the target would adjust

709
00:24:21,120 --> 00:24:25,200
so the target will adjust by this ratio

710
00:24:25,200 --> 00:24:26,000
so

711
00:24:26,000 --> 00:24:27,840
there we are so

712
00:24:27,840 --> 00:24:29,679
this ratio because it was mined all the

713
00:24:29,679 --> 00:24:32,960
blocks of mine faster is 0.9

714
00:24:32,960 --> 00:24:34,880
and so this target as you can see will

715
00:24:34,880 --> 00:24:36,720
adjust downwards

716
00:24:36,720 --> 00:24:38,880
so every single node when they receive a

717
00:24:38,880 --> 00:24:41,279
new block after every 2016 blocks they

718
00:24:41,279 --> 00:24:44,640
will all do this exact same calculation

719
00:24:44,640 --> 00:24:45,360
so

720
00:24:45,360 --> 00:24:47,520
every node started with this value but

721
00:24:47,520 --> 00:24:49,520
if everyone's on the same block

722
00:24:49,520 --> 00:24:52,480
then everyone will have calculated the

723
00:24:52,480 --> 00:24:53,840
same target

724
00:24:53,840 --> 00:24:55,279
so it's basically everyone shares the

725
00:24:55,279 --> 00:24:56,720
same target they all calculate it

726
00:24:56,720 --> 00:24:59,840
themselves but

727
00:24:59,840 --> 00:25:01,039
because they're receiving all the same

728
00:25:01,039 --> 00:25:02,000
blocks

729
00:25:02,000 --> 00:25:04,159
um they'll calculate everyone will have

730
00:25:04,159 --> 00:25:05,919
the same target value so not everyone

731
00:25:05,919 --> 00:25:07,520
has different target values everyone has

732
00:25:07,520 --> 00:25:10,799
the same calculated target

733
00:25:10,799 --> 00:25:13,360
so again this happens every 2016 blocks

734
00:25:13,360 --> 00:25:14,880
the same thing happens how long did they

735
00:25:14,880 --> 00:25:18,240
take what's the ratio okay that was

736
00:25:18,240 --> 00:25:19,440
mine faster

737
00:25:19,440 --> 00:25:22,720
move it down again like so

738
00:25:23,360 --> 00:25:24,240
okay

739
00:25:24,240 --> 00:25:26,559
um

740
00:25:26,960 --> 00:25:29,120
so that's how the target works

741
00:25:29,120 --> 00:25:29,900
um

742
00:25:29,900 --> 00:25:31,279
[Music]

743
00:25:31,279 --> 00:25:36,159
also up until now and just to clarify um

744
00:25:36,159 --> 00:25:37,440
i've referred to this blockchain as a

745
00:25:37,440 --> 00:25:39,520
shared file um the shared file is a

746
00:25:39,520 --> 00:25:41,919
blockchain um basically the shared file

747
00:25:41,919 --> 00:25:45,440
is full of transactions but um because

748
00:25:45,440 --> 00:25:48,559
um the transactions are added in blocks

749
00:25:48,559 --> 00:25:50,240
like so um the file is called the

750
00:25:50,240 --> 00:25:52,480
blockchain because each block builds on

751
00:25:52,480 --> 00:25:54,559
top of each other so with bitcoin it is

752
00:25:54,559 --> 00:25:56,240
a shared file and this shared file is

753
00:25:56,240 --> 00:25:57,919
called the blockchain

754
00:25:57,919 --> 00:26:00,320
so if i just update the diagram you can

755
00:26:00,320 --> 00:26:01,760
think of the shared file as you know

756
00:26:01,760 --> 00:26:04,720
just blocks built on top of each other

757
00:26:04,720 --> 00:26:06,000
finally

758
00:26:06,000 --> 00:26:07,520
why would anyone mine what's the

759
00:26:07,520 --> 00:26:09,679
incentive for a miner to

760
00:26:09,679 --> 00:26:11,279
use all this hashing power on their

761
00:26:11,279 --> 00:26:13,200
computer to try and

762
00:26:13,200 --> 00:26:14,240
um

763
00:26:14,240 --> 00:26:15,679
mine the transactions from the memory

764
00:26:15,679 --> 00:26:17,600
pool onto the blockchain

765
00:26:17,600 --> 00:26:20,799
well every time a miner

766
00:26:20,799 --> 00:26:22,960
mines a block it was successful

767
00:26:22,960 --> 00:26:25,520
to my in mind in a block and they will

768
00:26:25,520 --> 00:26:27,919
receive what's called a block reward

769
00:26:27,919 --> 00:26:30,159
um it started out at 50

770
00:26:30,159 --> 00:26:34,559
but it halves roughly every four years

771
00:26:34,799 --> 00:26:37,600
so that's the incentive to minor block

772
00:26:37,600 --> 00:26:39,520
and the way a miner receives this block

773
00:26:39,520 --> 00:26:40,640
reward

774
00:26:40,640 --> 00:26:42,880
um

775
00:26:42,880 --> 00:26:45,120
when they construct the candidate block

776
00:26:45,120 --> 00:26:47,279
um the very first transaction

777
00:26:47,279 --> 00:26:49,440
is reserved um

778
00:26:49,440 --> 00:26:53,600
for them to put there so a known a miner

779
00:26:53,600 --> 00:26:55,600
will put their own

780
00:26:55,600 --> 00:26:57,039
transaction at the top

781
00:26:57,039 --> 00:26:59,360
called a coinbase transaction

782
00:26:59,360 --> 00:27:01,440
and this is a special transaction

783
00:27:01,440 --> 00:27:03,679
because it allows them to

784
00:27:03,679 --> 00:27:05,440
send themselves or

785
00:27:05,440 --> 00:27:07,440
send themselves a set amount of bitcoins

786
00:27:07,440 --> 00:27:11,200
that had not previously existed

787
00:27:11,200 --> 00:27:12,240
um

788
00:27:12,240 --> 00:27:13,039
so

789
00:27:13,039 --> 00:27:14,480
if this block does get mined onto the

790
00:27:14,480 --> 00:27:16,320
blockchain

791
00:27:16,320 --> 00:27:18,400
they will be able to receive new

792
00:27:18,400 --> 00:27:19,600
bitcoins

793
00:27:19,600 --> 00:27:21,440
thanks to this coinbase transaction that

794
00:27:21,440 --> 00:27:23,200
they put there they put their sort of

795
00:27:23,200 --> 00:27:25,360
bitcoin address in here so that they can

796
00:27:25,360 --> 00:27:26,559
receive the

797
00:27:26,559 --> 00:27:28,960
the block reward

798
00:27:28,960 --> 00:27:30,640
so just to summarize the basics of

799
00:27:30,640 --> 00:27:32,720
mining um a miner will get the

800
00:27:32,720 --> 00:27:34,480
transactions from the memory pool

801
00:27:34,480 --> 00:27:36,000
then they'll put their coinbase

802
00:27:36,000 --> 00:27:37,200
transaction at the top so they can

803
00:27:37,200 --> 00:27:38,400
receive a block award if they're

804
00:27:38,400 --> 00:27:40,080
successful in mining this this block

805
00:27:40,080 --> 00:27:41,600
onto the blockchain

806
00:27:41,600 --> 00:27:43,760
then they'll create a block header

807
00:27:43,760 --> 00:27:45,679
then they'll hash it

808
00:27:45,679 --> 00:27:48,000
hope that it's below the target value if

809
00:27:48,000 --> 00:27:49,679
it's not they'll keep adjusting the

810
00:27:49,679 --> 00:27:52,000
nonce over and over again

811
00:27:52,000 --> 00:27:54,480
until and if they're lucky um they'll

812
00:27:54,480 --> 00:27:56,480
find a nonce before anyone else that

813
00:27:56,480 --> 00:27:58,159
produces a block hash that's below the

814
00:27:58,159 --> 00:27:59,200
target

815
00:27:59,200 --> 00:28:01,440
and then they outline the block

816
00:28:01,440 --> 00:28:03,840
like so

817
00:28:04,080 --> 00:28:06,320
uh does that make sense

818
00:28:06,320 --> 00:28:08,159
okay um

819
00:28:08,159 --> 00:28:09,919
i think what i'll do now i'll just show

820
00:28:09,919 --> 00:28:11,600
you um

821
00:28:11,600 --> 00:28:16,240
a little mining simulator um

822
00:28:16,240 --> 00:28:19,120
yeah a little mining simulator

823
00:28:19,120 --> 00:28:20,799
um

824
00:28:20,799 --> 00:28:22,960
so this is what um

825
00:28:22,960 --> 00:28:25,760
a bitcoin might bitcoin miner might look

826
00:28:25,760 --> 00:28:27,279
like if you like under the hood

827
00:28:27,279 --> 00:28:28,559
basically

828
00:28:28,559 --> 00:28:30,399
so what they'll do um they'll go into

829
00:28:30,399 --> 00:28:31,600
their memory pool

830
00:28:31,600 --> 00:28:32,960
they'll get the transactions from their

831
00:28:32,960 --> 00:28:34,080
memory pool

832
00:28:34,080 --> 00:28:34,880
um

833
00:28:34,880 --> 00:28:37,200
this mining simulator simulator is mined

834
00:28:37,200 --> 00:28:40,000
in a block that's already been mined um

835
00:28:40,000 --> 00:28:41,679
so this is a long time ago there's only

836
00:28:41,679 --> 00:28:43,279
13 transactions in the memory pool

837
00:28:43,279 --> 00:28:44,559
there's obviously a lot more in there

838
00:28:44,559 --> 00:28:45,440
now

839
00:28:45,440 --> 00:28:46,720
uh what they'll do then they'll

840
00:28:46,720 --> 00:28:48,240
construct the block header

841
00:28:48,240 --> 00:28:50,559
um i haven't covered these last

842
00:28:50,559 --> 00:28:52,399
two bits of the block header yet but

843
00:28:52,399 --> 00:28:53,679
don't worry i'll cover them in a moment

844
00:28:53,679 --> 00:28:54,640
moment

845
00:28:54,640 --> 00:28:56,399
but obviously this all this data refers

846
00:28:56,399 --> 00:28:57,919
to the previous block has the miracle

847
00:28:57,919 --> 00:28:59,840
root the version number

848
00:28:59,840 --> 00:29:00,640
um

849
00:29:00,640 --> 00:29:03,440
and what they'll do they will squish all

850
00:29:03,440 --> 00:29:04,399
of that

851
00:29:04,399 --> 00:29:06,720
data together into one line of data and

852
00:29:06,720 --> 00:29:08,480
i've left some space here for the nonce

853
00:29:08,480 --> 00:29:11,520
so this is a block header data

854
00:29:11,520 --> 00:29:13,840
this is the target and then what miner

855
00:29:13,840 --> 00:29:16,320
will do now is they will take this block

856
00:29:16,320 --> 00:29:18,080
header

857
00:29:18,080 --> 00:29:19,760
and put a nonce in there keep

858
00:29:19,760 --> 00:29:22,640
incrementing it and these are

859
00:29:22,640 --> 00:29:24,399
the results as you can see now this is a

860
00:29:24,399 --> 00:29:26,240
very slow minor so as you can see these

861
00:29:26,240 --> 00:29:28,399
are the nonce values on the left and

862
00:29:28,399 --> 00:29:30,720
this these are the different hash values

863
00:29:30,720 --> 00:29:32,320
that that

864
00:29:32,320 --> 00:29:33,919
block header is producing okay so this

865
00:29:33,919 --> 00:29:35,760
is uh so

866
00:29:35,760 --> 00:29:37,679
when you created that

867
00:29:37,679 --> 00:29:39,120
string

868
00:29:39,120 --> 00:29:42,080
uh on top that did not include the

869
00:29:42,080 --> 00:29:45,440
transactions it included only the header

870
00:29:45,440 --> 00:29:46,159
yes

871
00:29:46,159 --> 00:29:49,760
oh okay okay okay yes also so um

872
00:29:49,760 --> 00:29:50,480
what

873
00:29:50,480 --> 00:29:51,279
um

874
00:29:51,279 --> 00:29:53,200
the transactions i suppose are included

875
00:29:53,200 --> 00:29:55,600
in this merkel route this merker yeah

876
00:29:55,600 --> 00:29:57,200
this mercury route is the summary of all

877
00:29:57,200 --> 00:29:58,720
the transact this sort of refers to all

878
00:29:58,720 --> 00:30:01,279
the transactions in the block

879
00:30:01,279 --> 00:30:03,039
um

880
00:30:03,039 --> 00:30:05,760
here also i've here's the code for this

881
00:30:05,760 --> 00:30:08,480
miner it just basically just mines a

882
00:30:08,480 --> 00:30:10,000
um

883
00:30:10,000 --> 00:30:11,600
block header

884
00:30:11,600 --> 00:30:13,600
it just hashes a block header um i've

885
00:30:13,600 --> 00:30:15,200
made this code available on the website

886
00:30:15,200 --> 00:30:17,200
i'll give you a link to in a moment

887
00:30:17,200 --> 00:30:20,000
um but for this particular miner i know

888
00:30:20,000 --> 00:30:21,440
um

889
00:30:21,440 --> 00:30:24,799
what the successful hashtag

890
00:30:25,600 --> 00:30:29,200
hey there let's grab this

891
00:30:29,520 --> 00:30:31,360
there we are so

892
00:30:31,360 --> 00:30:34,000
let's reduce this down by 100.

893
00:30:34,000 --> 00:30:37,200
so if i start this again

894
00:30:37,200 --> 00:30:39,840
um i've increased the starting nonce

895
00:30:39,840 --> 00:30:41,520
value

896
00:30:41,520 --> 00:30:43,840
so again this is the block header

897
00:30:43,840 --> 00:30:45,200
the nonce is going to start not from

898
00:30:45,200 --> 00:30:47,360
zero this time but a much higher number

899
00:30:47,360 --> 00:30:49,679
and if i let it run now um hopefully

900
00:30:49,679 --> 00:30:53,919
after about 100 it'll stop when it finds

901
00:30:53,919 --> 00:30:57,760
a block hash below the target value

902
00:30:57,919 --> 00:31:01,200
there we are don't if you see this

903
00:31:01,200 --> 00:31:02,880
so there we are and the block has been

904
00:31:02,880 --> 00:31:04,480
mined so

905
00:31:04,480 --> 00:31:06,559
this particular blush block hash purely

906
00:31:06,559 --> 00:31:08,000
random

907
00:31:08,000 --> 00:31:10,720
and just pure luck produced a block hash

908
00:31:10,720 --> 00:31:12,320
starting with this many zeros and that

909
00:31:12,320 --> 00:31:14,240
was below the target and so that's what

910
00:31:14,240 --> 00:31:16,080
the miner does is they just

911
00:31:16,080 --> 00:31:18,640
grab a block header change the nonce

912
00:31:18,640 --> 00:31:21,360
hash as fast they can

913
00:31:21,360 --> 00:31:23,279
does that make sense

914
00:31:23,279 --> 00:31:24,880
okay um if

915
00:31:24,880 --> 00:31:26,559
i'll kev i'll add i'll put these links

916
00:31:26,559 --> 00:31:28,640
at the end um

917
00:31:28,640 --> 00:31:29,440
but

918
00:31:29,440 --> 00:31:30,799
if you go on the website on to

919
00:31:30,799 --> 00:31:32,720
learnmebitcoin.com

920
00:31:32,720 --> 00:31:35,520
forward slash code and i've put the

921
00:31:35,520 --> 00:31:37,519
mining simulator

922
00:31:37,519 --> 00:31:39,440
code up here

923
00:31:39,440 --> 00:31:40,320
it's

924
00:31:40,320 --> 00:31:43,039
i've made it it's written in ruby

925
00:31:43,039 --> 00:31:44,799
just because i think it's a simple and

926
00:31:44,799 --> 00:31:47,440
easy to read language similar to python

927
00:31:47,440 --> 00:31:49,200
um i tried to make this as simple as

928
00:31:49,200 --> 00:31:51,120
possible so if you want to start you

929
00:31:51,120 --> 00:31:53,120
know hashing your own block headers

930
00:31:53,120 --> 00:31:55,039
um you can

931
00:31:55,039 --> 00:31:57,360
so on the website as well on limia

932
00:31:57,360 --> 00:32:00,080
bitcoin if you go into the browser

933
00:32:00,080 --> 00:32:02,000
and you'll be able to see

934
00:32:02,000 --> 00:32:04,480
these these latest blocks

935
00:32:04,480 --> 00:32:07,200
and these are the block headers

936
00:32:07,200 --> 00:32:10,640
and if you click on serialized

937
00:32:10,880 --> 00:32:13,120
it'll show you the

938
00:32:13,120 --> 00:32:14,399
civilized code

939
00:32:14,399 --> 00:32:16,399
and if you were to hash this

940
00:32:16,399 --> 00:32:19,919
um it would produce this block header

941
00:32:19,919 --> 00:32:21,919
and so this is a

942
00:32:21,919 --> 00:32:23,679
this is a candidate block basically i'm

943
00:32:23,679 --> 00:32:25,279
just you know trying to do the same

944
00:32:25,279 --> 00:32:26,559
thing

945
00:32:26,559 --> 00:32:30,159
right so just curious i mean this uh is

946
00:32:30,159 --> 00:32:32,720
this running off like a

947
00:32:32,720 --> 00:32:33,840
machine

948
00:32:33,840 --> 00:32:35,679
that you have i mean learn me a bit is

949
00:32:35,679 --> 00:32:38,159
this live yeah this is live

950
00:32:38,159 --> 00:32:39,919
yeah so this is um

951
00:32:39,919 --> 00:32:41,840
a live candidate block these are all

952
00:32:41,840 --> 00:32:43,519
live transactions

953
00:32:43,519 --> 00:32:45,760
uh

954
00:32:46,000 --> 00:32:49,200
so it's all on the browser

955
00:32:49,760 --> 00:32:51,120
let me go back

956
00:32:51,120 --> 00:32:54,080
all right okay um

957
00:32:54,559 --> 00:32:57,679
uh okay so that's the basics

958
00:32:57,679 --> 00:32:58,480
oh

959
00:32:58,480 --> 00:33:01,200
intro right so that was the basics

960
00:33:01,200 --> 00:33:04,559
of um now i'll go on to the technical

961
00:33:04,559 --> 00:33:06,159
um basically i'm gonna run through the

962
00:33:06,159 --> 00:33:08,799
exact same thing but uh do it in a

963
00:33:08,799 --> 00:33:10,559
technical way

964
00:33:10,559 --> 00:33:13,679
so if you're interested in programming

965
00:33:13,679 --> 00:33:16,720
um and actually mining the block uh this

966
00:33:16,720 --> 00:33:19,039
is basically the same stuff just from a

967
00:33:19,039 --> 00:33:21,120
programmer's perspective

968
00:33:21,120 --> 00:33:23,120
right so so again

969
00:33:23,120 --> 00:33:25,039
just repetition gonna repeat the same

970
00:33:25,039 --> 00:33:27,200
stuff uh

971
00:33:27,200 --> 00:33:29,039
same thing memory pool

972
00:33:29,039 --> 00:33:30,240
grab the transact uh grab the

973
00:33:30,240 --> 00:33:31,840
transactions to main pool fill up your

974
00:33:31,840 --> 00:33:34,000
block uh then you'll

975
00:33:34,000 --> 00:33:36,159
there we are this is the candidate block

976
00:33:36,159 --> 00:33:38,159
then you put your coinbase transaction

977
00:33:38,159 --> 00:33:40,320
at the top the first transaction in a

978
00:33:40,320 --> 00:33:41,840
block is always a coinbase transaction

979
00:33:41,840 --> 00:33:43,840
that a miner was put there

980
00:33:43,840 --> 00:33:45,120
um

981
00:33:45,120 --> 00:33:46,960
and so that allows you to claim the

982
00:33:46,960 --> 00:33:48,960
block reward which is currently 12.5

983
00:33:48,960 --> 00:33:50,159
bitcoins

984
00:33:50,159 --> 00:33:51,600
and the reason you would put the

985
00:33:51,600 --> 00:33:53,919
coinbase transaction um at the top of

986
00:33:53,919 --> 00:33:56,080
the block after selecting all these

987
00:33:56,080 --> 00:33:57,360
transactions

988
00:33:57,360 --> 00:33:58,960
is because each of these transactions

989
00:33:58,960 --> 00:34:00,720
will have a fee

990
00:34:00,720 --> 00:34:02,559
and uh

991
00:34:02,559 --> 00:34:04,799
through your coinbase transaction

992
00:34:04,799 --> 00:34:07,760
you can collect all of these fees

993
00:34:07,760 --> 00:34:10,079
um so instead of the coinbase

994
00:34:10,079 --> 00:34:12,560
transaction just receiving the 12.5

995
00:34:12,560 --> 00:34:14,239
block reward you'll be able to send

996
00:34:14,239 --> 00:34:17,040
yourself something like 13 or more maybe

997
00:34:17,040 --> 00:34:19,040
depending on how much the fees are worth

998
00:34:19,040 --> 00:34:20,239
uh depends how much you can send

999
00:34:20,239 --> 00:34:22,000
yourself in this coinbase transaction

1000
00:34:22,000 --> 00:34:23,520
okay so the coinbase transaction

1001
00:34:23,520 --> 00:34:25,280
includes the fees yes

1002
00:34:25,280 --> 00:34:27,599
yes it's not only the the

1003
00:34:27,599 --> 00:34:29,599
mining reward okay so basically you have

1004
00:34:29,599 --> 00:34:31,520
the base level which is the block reward

1005
00:34:31,520 --> 00:34:33,760
but then you can send yourself however

1006
00:34:33,760 --> 00:34:35,359
much all these fees

1007
00:34:35,359 --> 00:34:38,239
from each transaction

1008
00:34:38,239 --> 00:34:40,560
so this means that miners will tend to

1009
00:34:40,560 --> 00:34:41,760
pick uh

1010
00:34:41,760 --> 00:34:42,800
uh

1011
00:34:42,800 --> 00:34:47,040
transactions with a higher exactly yes

1012
00:34:47,040 --> 00:34:48,639
uh so there we are we've got the

1013
00:34:48,639 --> 00:34:50,800
transfer one more question on that uh

1014
00:34:50,800 --> 00:34:53,040
yeah so i i remember seeing a graph

1015
00:34:53,040 --> 00:34:54,879
where uh

1016
00:34:54,879 --> 00:34:57,760
you know it showed me like uh

1017
00:34:57,760 --> 00:34:59,839
on the left the fees and on the right

1018
00:34:59,839 --> 00:35:02,079
like kind of how much time it will take

1019
00:35:02,079 --> 00:35:05,760
to mine that block yeah so uh

1020
00:35:05,760 --> 00:35:08,160
uh does this mean that

1021
00:35:08,160 --> 00:35:09,119
you know

1022
00:35:09,119 --> 00:35:12,000
if we put a very very low fee is it ever

1023
00:35:12,000 --> 00:35:14,400
possible that our transaction will never

1024
00:35:14,400 --> 00:35:16,880
get uh

1025
00:35:16,880 --> 00:35:19,040
never be part of a block is that ever

1026
00:35:19,040 --> 00:35:21,280
possible in your experience or what can

1027
00:35:21,280 --> 00:35:23,359
happen is so say you make a transaction

1028
00:35:23,359 --> 00:35:26,079
it'll go into the memory pool first um

1029
00:35:26,079 --> 00:35:27,359
if there's a lot of transactions in the

1030
00:35:27,359 --> 00:35:28,640
memory pool

1031
00:35:28,640 --> 00:35:30,640
um then you basically basically your

1032
00:35:30,640 --> 00:35:32,560
transaction is competing with all these

1033
00:35:32,560 --> 00:35:35,200
other transactions for space in a block

1034
00:35:35,200 --> 00:35:36,640
because a block

1035
00:35:36,640 --> 00:35:38,720
it's the way a block is

1036
00:35:38,720 --> 00:35:40,720
it used to be one megabytes worth of

1037
00:35:40,720 --> 00:35:43,839
transactions um it's roughly about 1.7

1038
00:35:43,839 --> 00:35:44,880
now

1039
00:35:44,880 --> 00:35:46,640
it uses a different metric called weight

1040
00:35:46,640 --> 00:35:48,320
but don't i'm not going to cover that

1041
00:35:48,320 --> 00:35:50,160
just now but um

1042
00:35:50,160 --> 00:35:51,760
what will happen is say you put such a

1043
00:35:51,760 --> 00:35:53,040
low fee on there

1044
00:35:53,040 --> 00:35:54,960
that um it doesn't make it into the

1045
00:35:54,960 --> 00:35:56,560
blocks are still hanging around in the

1046
00:35:56,560 --> 00:35:58,800
memory pool um

1047
00:35:58,800 --> 00:36:00,640
if your transaction stays in the memory

1048
00:36:00,640 --> 00:36:03,440
pool memory pool for longer than 72

1049
00:36:03,440 --> 00:36:05,520
hours

1050
00:36:05,520 --> 00:36:07,200
on average um

1051
00:36:07,200 --> 00:36:08,160
your

1052
00:36:08,160 --> 00:36:09,359
transaction will just get kicked out the

1053
00:36:09,359 --> 00:36:10,640
memory pool

1054
00:36:10,640 --> 00:36:11,440
so

1055
00:36:11,440 --> 00:36:13,440
you if you put a very low transaction a

1056
00:36:13,440 --> 00:36:15,440
fee on a transaction there's a chance

1057
00:36:15,440 --> 00:36:18,000
that it will never make it um one into a

1058
00:36:18,000 --> 00:36:20,640
into a candidate block or even it or

1059
00:36:20,640 --> 00:36:22,320
onto the blockchain right

1060
00:36:22,320 --> 00:36:24,320
so again in your experience what's like

1061
00:36:24,320 --> 00:36:26,480
the like the bare minimum let's say if i

1062
00:36:26,480 --> 00:36:28,320
want to send like five bucks to someone

1063
00:36:28,320 --> 00:36:29,839
you know or buy a coffee like three

1064
00:36:29,839 --> 00:36:30,720
bucks

1065
00:36:30,720 --> 00:36:33,920
uh what's what's the minimum

1066
00:36:33,920 --> 00:36:35,839
fee that i have to pay i mean

1067
00:36:35,839 --> 00:36:40,560
um i think wallets generally um

1068
00:36:40,560 --> 00:36:41,680
tend to

1069
00:36:41,680 --> 00:36:42,960
um

1070
00:36:42,960 --> 00:36:44,240
help you out with that but i don't think

1071
00:36:44,240 --> 00:36:46,320
they created it but

1072
00:36:46,320 --> 00:36:48,480
um

1073
00:36:48,480 --> 00:36:49,839
one way

1074
00:36:49,839 --> 00:36:52,079
what i would do is i would look at a cat

1075
00:36:52,079 --> 00:36:54,960
this candidate block and

1076
00:36:54,960 --> 00:36:56,960
transactions in general are ordered in a

1077
00:36:56,960 --> 00:36:58,640
candidate block from highest to lowest

1078
00:36:58,640 --> 00:37:01,359
fees not strictly but i would head

1079
00:37:01,359 --> 00:37:02,560
towards the bottom of this candidate

1080
00:37:02,560 --> 00:37:04,960
block and have a look at each of the fee

1081
00:37:04,960 --> 00:37:07,040
the fees on them and

1082
00:37:07,040 --> 00:37:08,560
um

1083
00:37:08,560 --> 00:37:09,920
uh

1084
00:37:09,920 --> 00:37:12,400
you can just basically add a fee that's

1085
00:37:12,400 --> 00:37:15,119
greater than the lowest fees yeah

1086
00:37:15,119 --> 00:37:16,960
exactly that's a

1087
00:37:16,960 --> 00:37:18,880
rough i mean that's like the simplest

1088
00:37:18,880 --> 00:37:22,000
way to do it in my opinion um

1089
00:37:22,000 --> 00:37:23,040
so

1090
00:37:23,040 --> 00:37:25,599
yeah yeah so again this is per byte i

1091
00:37:25,599 --> 00:37:28,480
think when you hovered over uh yeah so

1092
00:37:28,480 --> 00:37:32,400
fee per byte so this is uh

1093
00:37:32,400 --> 00:37:34,320
so the average

1094
00:37:34,320 --> 00:37:37,119
byte size of a transaction is that what

1095
00:37:37,119 --> 00:37:39,200
this is yeah so

1096
00:37:39,200 --> 00:37:40,000
um

1097
00:37:40,000 --> 00:37:42,720
so this this is a transaction

1098
00:37:42,720 --> 00:37:44,000
and um this

1099
00:37:44,000 --> 00:37:47,359
yeah this takes up um space in a block

1100
00:37:47,359 --> 00:37:50,560
so um then you set a fee on it but

1101
00:37:50,560 --> 00:37:51,839
you're basically paying for each

1102
00:37:51,839 --> 00:37:53,839
individual bytes so that the the bigger

1103
00:37:53,839 --> 00:37:54,960
the um

1104
00:37:54,960 --> 00:37:57,520
the transaction is in data wise uh the

1105
00:37:57,520 --> 00:37:59,200
more of a higher fee you want to put on

1106
00:37:59,200 --> 00:38:01,119
it to give you because

1107
00:38:01,119 --> 00:38:02,880
a miner but they will

1108
00:38:02,880 --> 00:38:05,839
select transactions um based on fee per

1109
00:38:05,839 --> 00:38:07,520
byte so basically which transactions are

1110
00:38:07,520 --> 00:38:09,440
giving them the most fee for the space

1111
00:38:09,440 --> 00:38:10,720
they're going to take up in the

1112
00:38:10,720 --> 00:38:12,480
candidate block

1113
00:38:12,480 --> 00:38:13,599
okay

1114
00:38:13,599 --> 00:38:15,119
um

1115
00:38:15,119 --> 00:38:16,720
so again just going to went through

1116
00:38:16,720 --> 00:38:17,920
mining again put your coinbase

1117
00:38:17,920 --> 00:38:19,839
transaction at the top

1118
00:38:19,839 --> 00:38:21,359
and then you can check the block header

1119
00:38:21,359 --> 00:38:23,680
same again you have a version number

1120
00:38:23,680 --> 00:38:24,560
um

1121
00:38:24,560 --> 00:38:26,480
this was like this null block and the

1122
00:38:26,480 --> 00:38:29,440
version of was one uh the way versions

1123
00:38:29,440 --> 00:38:32,160
numbers has cha the way version numbers

1124
00:38:32,160 --> 00:38:34,160
uh work now is different to how it used

1125
00:38:34,160 --> 00:38:36,960
to be they can be used for um voting um

1126
00:38:36,960 --> 00:38:38,079
i'm not going to cover that just now

1127
00:38:38,079 --> 00:38:40,640
it's going to run through um

1128
00:38:40,640 --> 00:38:42,400
simple block header then you have the

1129
00:38:42,400 --> 00:38:44,160
previous block name again just refer to

1130
00:38:44,160 --> 00:38:45,200
the block you're going to build on top

1131
00:38:45,200 --> 00:38:47,119
of build on top of which is basically

1132
00:38:47,119 --> 00:38:49,599
the tip of the blockchain

1133
00:38:49,599 --> 00:38:51,599
uh then you have the merkle root

1134
00:38:51,599 --> 00:38:54,079
so the way that works is um you have all

1135
00:38:54,079 --> 00:38:55,920
the transactions uh

1136
00:38:55,920 --> 00:38:57,119
in the block

1137
00:38:57,119 --> 00:38:58,560
i'm just moving these to the side just

1138
00:38:58,560 --> 00:39:00,480
for illustration purposes

1139
00:39:00,480 --> 00:39:02,320
and what you do you just run through

1140
00:39:02,320 --> 00:39:04,240
every single pair of transactions and

1141
00:39:04,240 --> 00:39:05,839
you hash them together

1142
00:39:05,839 --> 00:39:08,720
so remember the hash function and you

1143
00:39:08,720 --> 00:39:10,560
basically line these up

1144
00:39:10,560 --> 00:39:12,240
so one and two just line them up

1145
00:39:12,240 --> 00:39:14,079
together and hash them together and

1146
00:39:14,079 --> 00:39:15,760
they'll produce a

1147
00:39:15,760 --> 00:39:17,920
digest or hash result

1148
00:39:17,920 --> 00:39:19,359
and they do that for every single pair

1149
00:39:19,359 --> 00:39:21,200
of transactions

1150
00:39:21,200 --> 00:39:22,240
in the block

1151
00:39:22,240 --> 00:39:24,960
um if you end up with a transaction on

1152
00:39:24,960 --> 00:39:26,720
his own that doesn't have a pair all you

1153
00:39:26,720 --> 00:39:29,440
do is you just hash it with itself

1154
00:39:29,440 --> 00:39:31,680
and then that's the first round done you

1155
00:39:31,680 --> 00:39:33,599
have these four hashes from all these

1156
00:39:33,599 --> 00:39:34,800
pairs

1157
00:39:34,800 --> 00:39:36,560
then you just run through again

1158
00:39:36,560 --> 00:39:38,320
hash them all together hash each pair

1159
00:39:38,320 --> 00:39:40,400
together and you keep going on and

1160
00:39:40,400 --> 00:39:43,680
you'll end up with a single um

1161
00:39:43,680 --> 00:39:44,880
hash result

1162
00:39:44,880 --> 00:39:46,960
called the merkle root

1163
00:39:46,960 --> 00:39:47,760
now

1164
00:39:47,760 --> 00:39:49,839
the question is um

1165
00:39:49,839 --> 00:39:51,119
why

1166
00:39:51,119 --> 00:39:53,599
if you want to create a summary of all

1167
00:39:53,599 --> 00:39:56,480
the transactions in the block you're

1168
00:39:56,480 --> 00:39:57,839
hashing the transaction ids here

1169
00:39:57,839 --> 00:40:00,160
together by the way but um

1170
00:40:00,160 --> 00:40:01,359
if you want to create a summary or a

1171
00:40:01,359 --> 00:40:02,720
fingerprint for all the transactions in

1172
00:40:02,720 --> 00:40:04,560
the block why wouldn't you just hash

1173
00:40:04,560 --> 00:40:06,320
them all together like this in a more

1174
00:40:06,320 --> 00:40:07,760
simple way why would you do it in this

1175
00:40:07,760 --> 00:40:09,280
more elaborate

1176
00:40:09,280 --> 00:40:11,599
um tree structure

1177
00:40:11,599 --> 00:40:13,520
and the reason for that is

1178
00:40:13,520 --> 00:40:16,720
um say you you were given a merkle root

1179
00:40:16,720 --> 00:40:17,839
um

1180
00:40:17,839 --> 00:40:21,359
a merkel root and you want to check if

1181
00:40:21,359 --> 00:40:23,599
this transaction id

1182
00:40:23,599 --> 00:40:26,480
is present in this block

1183
00:40:26,480 --> 00:40:29,359
um the only way you could check it

1184
00:40:29,359 --> 00:40:30,800
would be to take

1185
00:40:30,800 --> 00:40:32,400
all of the other

1186
00:40:32,400 --> 00:40:34,160
transaction ids you need all the other

1187
00:40:34,160 --> 00:40:36,079
ones including the one you want to check

1188
00:40:36,079 --> 00:40:38,720
and then hash them together to get the

1189
00:40:38,720 --> 00:40:40,400
miracle root

1190
00:40:40,400 --> 00:40:41,680
um

1191
00:40:41,680 --> 00:40:44,000
to get the to get the hash sorry

1192
00:40:44,000 --> 00:40:44,800
um

1193
00:40:44,800 --> 00:40:45,920
but

1194
00:40:45,920 --> 00:40:47,760
with a miracle root um so you want to

1195
00:40:47,760 --> 00:40:50,000
check the presence of this hash here all

1196
00:40:50,000 --> 00:40:52,320
you actually need is you need this one

1197
00:40:52,320 --> 00:40:54,000
to create this one

1198
00:40:54,000 --> 00:40:55,760
and then if you've got that one and then

1199
00:40:55,760 --> 00:40:57,599
all you need is that one

1200
00:40:57,599 --> 00:40:59,280
and then you can create that one

1201
00:40:59,280 --> 00:41:01,440
and then only then is this one up here

1202
00:41:01,440 --> 00:41:03,920
and that will give you this miracle root

1203
00:41:03,920 --> 00:41:06,480
so the other one needed was it one two

1204
00:41:06,480 --> 00:41:10,240
three four five seven six um

1205
00:41:10,240 --> 00:41:12,720
transaction ids but this one only needed

1206
00:41:12,720 --> 00:41:13,920
uh three

1207
00:41:13,920 --> 00:41:14,960
so obviously it doesn't look like a

1208
00:41:14,960 --> 00:41:16,319
massive improvement but this is just a

1209
00:41:16,319 --> 00:41:18,880
simple block that if this is a lot

1210
00:41:18,880 --> 00:41:20,560
longer block with

1211
00:41:20,560 --> 00:41:22,240
thousands of transactions

1212
00:41:22,240 --> 00:41:23,520
then

1213
00:41:23,520 --> 00:41:25,040
you're needing a lot less transaction

1214
00:41:25,040 --> 00:41:26,480
ids to

1215
00:41:26,480 --> 00:41:28,079
check the presence of a single

1216
00:41:28,079 --> 00:41:30,079
transaction

1217
00:41:30,079 --> 00:41:32,079
i've not done this myself but

1218
00:41:32,079 --> 00:41:34,160
apparently this is useful and efficient

1219
00:41:34,160 --> 00:41:35,599
to um

1220
00:41:35,599 --> 00:41:37,280
do it this way so that's why we have

1221
00:41:37,280 --> 00:41:38,640
this tree structure for hashing because

1222
00:41:38,640 --> 00:41:41,520
it saves on checking for the presence of

1223
00:41:41,520 --> 00:41:43,839
transactions in our block yeah just one

1224
00:41:43,839 --> 00:41:46,400
question when you say that we we hash

1225
00:41:46,400 --> 00:41:48,880
like two transactions you're saying that

1226
00:41:48,880 --> 00:41:51,520
we just concatenate them and hash do a

1227
00:41:51,520 --> 00:41:53,839
chat yeah 256. exactly you just

1228
00:41:53,839 --> 00:41:57,760
concatenate the transaction ids

1229
00:41:57,920 --> 00:41:59,440
which are basically the hashes of the

1230
00:41:59,440 --> 00:42:01,040
time yeah so

1231
00:42:01,040 --> 00:42:02,960
you basically hash transaction data to

1232
00:42:02,960 --> 00:42:04,880
give you a transaction id and then you

1233
00:42:04,880 --> 00:42:05,420
yeah yeah

1234
00:42:05,420 --> 00:42:06,800
[Music]

1235
00:42:06,800 --> 00:42:07,170
um

1236
00:42:07,170 --> 00:42:08,319
[Music]

1237
00:42:08,319 --> 00:42:10,319
so there we go um that's the merkel

1238
00:42:10,319 --> 00:42:11,280
route

1239
00:42:11,280 --> 00:42:13,760
uh time also in the block header

1240
00:42:13,760 --> 00:42:15,359
you have something called but you just

1241
00:42:15,359 --> 00:42:17,520
have the time which is a timestamp

1242
00:42:17,520 --> 00:42:19,280
um like so

1243
00:42:19,280 --> 00:42:21,839
but you don't the way the

1244
00:42:21,839 --> 00:42:23,760
time is encoded in the block header is

1245
00:42:23,760 --> 00:42:25,440
using unix time

1246
00:42:25,440 --> 00:42:27,280
which is the number of seconds since the

1247
00:42:27,280 --> 00:42:29,359
1st january 1970.

1248
00:42:29,359 --> 00:42:30,880
so this

1249
00:42:30,880 --> 00:42:34,480
blocks times timestamping so the human

1250
00:42:34,480 --> 00:42:36,880
representation is 12 may 2011 but in

1251
00:42:36,880 --> 00:42:38,960
unix time that would be this many

1252
00:42:38,960 --> 00:42:41,040
seconds

1253
00:42:41,040 --> 00:42:42,319
um

1254
00:42:42,319 --> 00:42:43,599
a quick note

1255
00:42:43,599 --> 00:42:45,680
on the time um these don't have to be

1256
00:42:45,680 --> 00:42:46,720
accurate

1257
00:42:46,720 --> 00:42:48,560
um they just have to be between a

1258
00:42:48,560 --> 00:42:51,280
certain minimum and maximum value

1259
00:42:51,280 --> 00:42:52,400
so um

1260
00:42:52,400 --> 00:42:53,920
the minimum value

1261
00:42:53,920 --> 00:42:55,520
you can set as the time for your block

1262
00:42:55,520 --> 00:42:58,960
header is the median time of the last 11

1263
00:42:58,960 --> 00:43:00,079
blocks

1264
00:43:00,079 --> 00:43:03,359
or basically the the time set that's

1265
00:43:03,359 --> 00:43:06,160
been the time of in the block header of

1266
00:43:06,160 --> 00:43:08,800
the sixth block down

1267
00:43:08,800 --> 00:43:10,800
so you can't have a time

1268
00:43:10,800 --> 00:43:12,400
uh any lower than that

1269
00:43:12,400 --> 00:43:14,000
that's the minimum bound

1270
00:43:14,000 --> 00:43:15,599
and then the maximum

1271
00:43:15,599 --> 00:43:17,839
um

1272
00:43:17,839 --> 00:43:19,119
the maximum

1273
00:43:19,119 --> 00:43:22,720
basically your node has its own time

1274
00:43:22,720 --> 00:43:24,160
uh when you run it it just uses your

1275
00:43:24,160 --> 00:43:26,000
computer's time and then when other

1276
00:43:26,000 --> 00:43:28,000
nodes connect to you they will send you

1277
00:43:28,000 --> 00:43:30,000
what their time is on their computer and

1278
00:43:30,000 --> 00:43:31,760
so your node will keep track of the

1279
00:43:31,760 --> 00:43:33,760
difference between

1280
00:43:33,760 --> 00:43:35,119
all of the times of the nodes you're

1281
00:43:35,119 --> 00:43:36,560
connected to

1282
00:43:36,560 --> 00:43:38,560
and if you put them in order and you

1283
00:43:38,560 --> 00:43:40,400
take the median time

1284
00:43:40,400 --> 00:43:42,319
of all the nodes you're connected to

1285
00:43:42,319 --> 00:43:44,319
um that's called the network average

1286
00:43:44,319 --> 00:43:45,760
time

1287
00:43:45,760 --> 00:43:47,280
so um

1288
00:43:47,280 --> 00:43:50,079
the maximum value of this time is the

1289
00:43:50,079 --> 00:43:53,680
network average time plus two hours

1290
00:43:53,680 --> 00:43:55,520
so can you repeat this

1291
00:43:55,520 --> 00:43:57,839
like quickly i mean i just got a little

1292
00:43:57,839 --> 00:44:00,800
confused so why is this time used and uh

1293
00:44:00,800 --> 00:44:02,480
is this the time to mine a block or

1294
00:44:02,480 --> 00:44:04,480
something i mean uh no uh no this is

1295
00:44:04,480 --> 00:44:07,280
this this time um i think this is i

1296
00:44:07,280 --> 00:44:08,560
think this is quite a bit unnecessary

1297
00:44:08,560 --> 00:44:11,200
necessary for me to explain um basically

1298
00:44:11,200 --> 00:44:12,960
the time is just you just stick the

1299
00:44:12,960 --> 00:44:14,960
current time of your computer um in the

1300
00:44:14,960 --> 00:44:18,000
block header but it's but it's not um

1301
00:44:18,000 --> 00:44:20,560
it doesn't have to be precise um

1302
00:44:20,560 --> 00:44:23,200
it's not yeah so basically it just has

1303
00:44:23,200 --> 00:44:25,760
to be between two certain values um as

1304
00:44:25,760 --> 00:44:28,720
long as it's a greater than um the time

1305
00:44:28,720 --> 00:44:29,599
of

1306
00:44:29,599 --> 00:44:32,480
the sixth block down

1307
00:44:32,480 --> 00:44:35,280
yeah or the meat of the median time of

1308
00:44:35,280 --> 00:44:36,880
the last 11 blocks

1309
00:44:36,880 --> 00:44:38,400
um it can't be any lower than that

1310
00:44:38,400 --> 00:44:40,240
because if you were to put a time lower

1311
00:44:40,240 --> 00:44:42,160
than that then it would get rejected by

1312
00:44:42,160 --> 00:44:43,920
the nodes you send it to and also the

1313
00:44:43,920 --> 00:44:45,760
maximum time is basically the current

1314
00:44:45,760 --> 00:44:47,119
time

1315
00:44:47,119 --> 00:44:49,280
plus two hours

1316
00:44:49,280 --> 00:44:51,440
but it's we used

1317
00:44:51,440 --> 00:44:53,920
um network average time is used which is

1318
00:44:53,920 --> 00:44:56,000
just the average time

1319
00:44:56,000 --> 00:44:57,359
of all the nodes that are connected to

1320
00:44:57,359 --> 00:44:58,800
you

1321
00:44:58,800 --> 00:44:59,680
um

1322
00:44:59,680 --> 00:45:01,839
so don't worry about that um but it's

1323
00:45:01,839 --> 00:45:03,599
basically all i'm saying is the time can

1324
00:45:03,599 --> 00:45:04,640
be

1325
00:45:04,640 --> 00:45:07,200
roughly an hour behind one or two hours

1326
00:45:07,200 --> 00:45:08,079
ahead

1327
00:45:08,079 --> 00:45:09,920
so it's not really if you see if a block

1328
00:45:09,920 --> 00:45:12,079
comes comes through and it has a time

1329
00:45:12,079 --> 00:45:13,359
like

1330
00:45:13,359 --> 00:45:15,280
before or ahead of like a different

1331
00:45:15,280 --> 00:45:16,240
block

1332
00:45:16,240 --> 00:45:17,839
it doesn't really matter it has this

1333
00:45:17,839 --> 00:45:20,240
sort of flexible sort of upper and lower

1334
00:45:20,240 --> 00:45:22,240
boundary

1335
00:45:22,240 --> 00:45:25,359
all right so that's the time um bits um

1336
00:45:25,359 --> 00:45:27,440
bits remember the target

1337
00:45:27,440 --> 00:45:29,599
bits is just a compact representation of

1338
00:45:29,599 --> 00:45:30,800
the target

1339
00:45:30,800 --> 00:45:33,359
so instead of putting the the current

1340
00:45:33,359 --> 00:45:35,200
target um

1341
00:45:35,200 --> 00:45:37,760
the entire target in the block header

1342
00:45:37,760 --> 00:45:40,000
what you what you do

1343
00:45:40,000 --> 00:45:42,880
is you just grab um the first three

1344
00:45:42,880 --> 00:45:45,520
significant bytes or the first six you

1345
00:45:45,520 --> 00:45:47,599
know significant characters after the

1346
00:45:47,599 --> 00:45:49,680
leading zeros and then you put that

1347
00:45:49,680 --> 00:45:50,560
there

1348
00:45:50,560 --> 00:45:51,599
and then

1349
00:45:51,599 --> 00:45:54,960
um you just grab the offset so how far

1350
00:45:54,960 --> 00:45:55,760
these

1351
00:45:55,760 --> 00:45:58,560
um three bytes are from the right

1352
00:45:58,560 --> 00:46:00,880
uh and that is there are 26 bytes from

1353
00:46:00,880 --> 00:46:02,240
the right here

1354
00:46:02,240 --> 00:46:06,160
or in hexadecimal 26 is 1a

1355
00:46:06,160 --> 00:46:08,640
so you just put that start there so bits

1356
00:46:08,640 --> 00:46:10,800
is just this compact representation of

1357
00:46:10,800 --> 00:46:13,280
the target

1358
00:46:13,440 --> 00:46:15,040
um

1359
00:46:15,040 --> 00:46:16,400
then that's it then then you just have

1360
00:46:16,400 --> 00:46:18,800
the nonce and you can set that to zero

1361
00:46:18,800 --> 00:46:22,400
and so this is all the basic data now um

1362
00:46:22,400 --> 00:46:23,839
for the block header

1363
00:46:23,839 --> 00:46:25,839
does that does it all these fields make

1364
00:46:25,839 --> 00:46:28,720
sense each part okay good um so now

1365
00:46:28,720 --> 00:46:30,160
we've got all the fields ready to be

1366
00:46:30,160 --> 00:46:31,599
mined

1367
00:46:31,599 --> 00:46:34,319
um we just have to get all the data into

1368
00:46:34,319 --> 00:46:35,760
the correct format

1369
00:46:35,760 --> 00:46:37,839
uh so this is just a bit of programming

1370
00:46:37,839 --> 00:46:39,040
just to make sure everything's in the

1371
00:46:39,040 --> 00:46:41,520
right order and format

1372
00:46:41,520 --> 00:46:44,400
each field um should be in hexa put it

1373
00:46:44,400 --> 00:46:46,640
all into hexadecimal

1374
00:46:46,640 --> 00:46:47,680
so

1375
00:46:47,680 --> 00:46:49,440
one is one in hexadecimal so this is

1376
00:46:49,440 --> 00:46:51,040
going to change but you just go through

1377
00:46:51,040 --> 00:46:52,560
every single field making sure that it's

1378
00:46:52,560 --> 00:46:54,160
all hexadecimal so

1379
00:46:54,160 --> 00:46:56,640
these two hexadecimal the time this is

1380
00:46:56,640 --> 00:46:58,079
in decimal at the moment so we just

1381
00:46:58,079 --> 00:47:00,079
convert that hex decimal and you do the

1382
00:47:00,079 --> 00:47:02,800
same for every other field

1383
00:47:02,800 --> 00:47:03,839
secondly

1384
00:47:03,839 --> 00:47:05,359
each field

1385
00:47:05,359 --> 00:47:07,040
must be a

1386
00:47:07,040 --> 00:47:09,599
fixed number of bytes

1387
00:47:09,599 --> 00:47:11,040
so there's only got one character in

1388
00:47:11,040 --> 00:47:13,760
here but the version field is four bytes

1389
00:47:13,760 --> 00:47:16,160
so if we convert that to four bytes it

1390
00:47:16,160 --> 00:47:17,839
looks like this

1391
00:47:17,839 --> 00:47:20,720
so one byte is two characters so zero

1392
00:47:20,720 --> 00:47:23,119
zero that's one byte and there are four

1393
00:47:23,119 --> 00:47:25,680
bytes in the version

1394
00:47:25,680 --> 00:47:26,640
um

1395
00:47:26,640 --> 00:47:27,680
then you just go through every single

1396
00:47:27,680 --> 00:47:29,599
field giving it

1397
00:47:29,599 --> 00:47:32,000
putting it into the correct um

1398
00:47:32,000 --> 00:47:34,480
size so this is already 32 bytes that's

1399
00:47:34,480 --> 00:47:36,319
already 32 bytes

1400
00:47:36,319 --> 00:47:37,760
the time's gonna be four bytes it's

1401
00:47:37,760 --> 00:47:40,400
already four bits same again four the

1402
00:47:40,400 --> 00:47:42,640
nonce then that's four bytes as well

1403
00:47:42,640 --> 00:47:45,119
so just for each field make sure that

1404
00:47:45,119 --> 00:47:47,440
you've padded it out padded it out

1405
00:47:47,440 --> 00:47:49,760
with the right number of bytes so this

1406
00:47:49,760 --> 00:47:52,720
basically means that when a computer can

1407
00:47:52,720 --> 00:47:54,079
read through each individual fields

1408
00:47:54,079 --> 00:47:56,480
easily

1409
00:47:56,960 --> 00:47:58,880
so that's all the

1410
00:47:58,880 --> 00:48:00,640
data in the right

1411
00:48:00,640 --> 00:48:03,359
format and the right field size

1412
00:48:03,359 --> 00:48:05,280
lastly the only

1413
00:48:05,280 --> 00:48:07,440
slightly frustrating thing with bitcoin

1414
00:48:07,440 --> 00:48:10,160
is that when you send

1415
00:48:10,160 --> 00:48:12,400
data to

1416
00:48:12,400 --> 00:48:15,440
um the nodes um

1417
00:48:15,440 --> 00:48:17,599
across the wire

1418
00:48:17,599 --> 00:48:19,680
you have to send the data in reverse

1419
00:48:19,680 --> 00:48:22,160
byte order which is called network byte

1420
00:48:22,160 --> 00:48:23,200
order

1421
00:48:23,200 --> 00:48:26,079
so um obviously we've got all this in

1422
00:48:26,079 --> 00:48:29,200
human readable human human readable byte

1423
00:48:29,200 --> 00:48:31,520
order but when you

1424
00:48:31,520 --> 00:48:33,520
hash and work with bitcoin data it has

1425
00:48:33,520 --> 00:48:35,680
to be in reverse byte order so you just

1426
00:48:35,680 --> 00:48:37,200
go through every single field and put it

1427
00:48:37,200 --> 00:48:39,440
into network byte order

1428
00:48:39,440 --> 00:48:43,040
which is just reversing each byte

1429
00:48:43,040 --> 00:48:45,599
so that's something that

1430
00:48:45,599 --> 00:48:47,280
well they tripped me up when i first

1431
00:48:47,280 --> 00:48:48,800
started mining i was like i was trying

1432
00:48:48,800 --> 00:48:50,000
to hash these block headers and i was

1433
00:48:50,000 --> 00:48:51,040
like why am i not getting the same

1434
00:48:51,040 --> 00:48:52,800
results it's because

1435
00:48:52,800 --> 00:48:54,559
you want to get everything in network

1436
00:48:54,559 --> 00:48:56,240
byte order

1437
00:48:56,240 --> 00:48:58,000
and just to show you i've made like a

1438
00:48:58,000 --> 00:49:00,559
little quick um

1439
00:49:00,559 --> 00:49:01,839
uh

1440
00:49:01,839 --> 00:49:02,880
script

1441
00:49:02,880 --> 00:49:06,480
so reverse bytes so if i put the

1442
00:49:06,480 --> 00:49:08,160
a b c d e

1443
00:49:08,160 --> 00:49:10,800
f one two three four

1444
00:49:10,800 --> 00:49:13,200
let me see

1445
00:49:13,839 --> 00:49:15,359
um the way that works is reverse byte

1446
00:49:15,359 --> 00:49:17,520
order you just split it all into each

1447
00:49:17,520 --> 00:49:19,839
individual byte so one byte is two

1448
00:49:19,839 --> 00:49:23,200
characters and then you just um reverse

1449
00:49:23,200 --> 00:49:24,720
the order of the bytes and that gives

1450
00:49:24,720 --> 00:49:26,480
you that so that's how it works so

1451
00:49:26,480 --> 00:49:28,480
you're not just reversing the string

1452
00:49:28,480 --> 00:49:31,680
you are um reversing each byte

1453
00:49:31,680 --> 00:49:34,800
so this might be a basic question but uh

1454
00:49:34,800 --> 00:49:35,920
one

1455
00:49:35,920 --> 00:49:38,720
so two characters is one byte yes yes

1456
00:49:38,720 --> 00:49:40,400
yeah

1457
00:49:40,400 --> 00:49:41,680
yep

1458
00:49:41,680 --> 00:49:42,800
um

1459
00:49:42,800 --> 00:49:45,200
that's just something i've learned

1460
00:49:45,200 --> 00:49:47,359
uh

1461
00:49:47,359 --> 00:49:51,520
i'm just looking at the c plus plus

1462
00:49:51,520 --> 00:49:53,520
uh i've not done c plus plus in a long

1463
00:49:53,520 --> 00:49:54,480
time

1464
00:49:54,480 --> 00:49:59,520
so character type size is one byte um

1465
00:50:01,599 --> 00:50:04,079
yeah no i i don't i don't know that much

1466
00:50:04,079 --> 00:50:06,640
deep about computer science um but all i

1467
00:50:06,640 --> 00:50:08,800
know is yeah

1468
00:50:08,800 --> 00:50:10,880
i'm doing this more like a top down sort

1469
00:50:10,880 --> 00:50:12,720
of level i i've just learned that um two

1470
00:50:12,720 --> 00:50:15,359
characters translates as one byte so

1471
00:50:15,359 --> 00:50:17,440
yeah

1472
00:50:17,440 --> 00:50:19,599
um so there we are now we've got all the

1473
00:50:19,599 --> 00:50:22,160
data finally in the right order um all

1474
00:50:22,160 --> 00:50:23,839
you do then you just concatenate each

1475
00:50:23,839 --> 00:50:26,559
individual field together like that so

1476
00:50:26,559 --> 00:50:28,319
this is the block header

1477
00:50:28,319 --> 00:50:30,559
now it's ready to put inside to put into

1478
00:50:30,559 --> 00:50:32,240
the hash function

1479
00:50:32,240 --> 00:50:35,440
um as i mentioned um sha-256 simple

1480
00:50:35,440 --> 00:50:38,480
hashing algorithm 256

1481
00:50:38,480 --> 00:50:39,520
is used

1482
00:50:39,520 --> 00:50:41,839
um but in bitcoin everything gets hashed

1483
00:50:41,839 --> 00:50:42,800
twice

1484
00:50:42,800 --> 00:50:44,319
um

1485
00:50:44,319 --> 00:50:46,400
it's just the way it was designed i

1486
00:50:46,400 --> 00:50:48,240
don't think it provides any massive

1487
00:50:48,240 --> 00:50:50,800
benefits it's just the way that

1488
00:50:50,800 --> 00:50:52,640
bitcoin hashes things

1489
00:50:52,640 --> 00:50:53,520
um

1490
00:50:53,520 --> 00:50:55,760
so you just put this into hash function

1491
00:50:55,760 --> 00:50:58,480
spits our result and then spits out then

1492
00:50:58,480 --> 00:50:59,920
you hash the result to get you another

1493
00:50:59,920 --> 00:51:01,359
result and that's the

1494
00:51:01,359 --> 00:51:02,800
final hash

1495
00:51:02,800 --> 00:51:05,520
um quick note um

1496
00:51:05,520 --> 00:51:07,680
when when you hash things in bitcoin um

1497
00:51:07,680 --> 00:51:10,000
this is in hexadecimal but you convert

1498
00:51:10,000 --> 00:51:12,000
it into binary first so you put binary

1499
00:51:12,000 --> 00:51:14,800
data into the hashing function

1500
00:51:14,800 --> 00:51:15,920
and then

1501
00:51:15,920 --> 00:51:17,520
that'll spit out a binding result then

1502
00:51:17,520 --> 00:51:19,280
you put the binary result into the

1503
00:51:19,280 --> 00:51:20,079
second

1504
00:51:20,079 --> 00:51:21,440
hashing function

1505
00:51:21,440 --> 00:51:24,880
that'll spit out a second binary digest

1506
00:51:24,880 --> 00:51:27,839
and then when you convert that

1507
00:51:27,839 --> 00:51:29,359
second digest

1508
00:51:29,359 --> 00:51:31,200
back into hexadecimal

1509
00:51:31,200 --> 00:51:33,040
that'll give you the

1510
00:51:33,040 --> 00:51:35,119
um

1511
00:51:35,119 --> 00:51:38,319
block hash but obviously this is in

1512
00:51:38,319 --> 00:51:39,359
reverse

1513
00:51:39,359 --> 00:51:41,680
uh network byte order again so if you

1514
00:51:41,680 --> 00:51:42,880
reverse it

1515
00:51:42,880 --> 00:51:45,760
then that's in the more human

1516
00:51:45,760 --> 00:51:49,040
uh format so if you compare this

1517
00:51:49,040 --> 00:51:50,559
to the target you want to make sure it's

1518
00:51:50,559 --> 00:51:53,520
in you want to reverse it back into

1519
00:51:53,520 --> 00:51:55,359
uh

1520
00:51:55,359 --> 00:51:58,079
non-network byte order

1521
00:51:58,079 --> 00:51:58,880
so

1522
00:51:58,880 --> 00:52:01,359
so there we go um so this i've only

1523
00:52:01,359 --> 00:52:03,119
covered these things because they just

1524
00:52:03,119 --> 00:52:05,599
trip you up i mean get in the fields

1525
00:52:05,599 --> 00:52:07,200
it's quite simple but then get anything

1526
00:52:07,200 --> 00:52:08,960
into the right order then converting it

1527
00:52:08,960 --> 00:52:11,040
to binary and then switching it back

1528
00:52:11,040 --> 00:52:11,839
again

1529
00:52:11,839 --> 00:52:14,240
um that's what'll trip you up if you're

1530
00:52:14,240 --> 00:52:15,920
trying to minor block header or hash a

1531
00:52:15,920 --> 00:52:18,240
block header for yourself

1532
00:52:18,240 --> 00:52:20,640
all right so this was the block header

1533
00:52:20,640 --> 00:52:23,760
on the left which already had the fields

1534
00:52:23,760 --> 00:52:26,319
in reverse network order right

1535
00:52:26,319 --> 00:52:28,240
uh yes yes

1536
00:52:28,240 --> 00:52:30,400
okay then you

1537
00:52:30,400 --> 00:52:31,359
uh

1538
00:52:31,359 --> 00:52:34,319
do a double hash of that yeah and you

1539
00:52:34,319 --> 00:52:36,720
convert it to hex and

1540
00:52:36,720 --> 00:52:40,160
you converted that again in reverse

1541
00:52:40,160 --> 00:52:43,599
i reversed it i reversed it back

1542
00:52:44,000 --> 00:52:44,839
okay

1543
00:52:44,839 --> 00:52:48,319
um yeah and this is how this is

1544
00:52:48,319 --> 00:52:50,559
like if you mind the block this is the

1545
00:52:50,559 --> 00:52:52,319
hash that you would send on to the

1546
00:52:52,319 --> 00:52:54,880
network is that uh

1547
00:52:54,880 --> 00:52:56,720
um let's say that you end up mining a

1548
00:52:56,720 --> 00:52:58,880
block and let's say you get a nuance

1549
00:52:58,880 --> 00:53:01,599
that is like below a target value yeah

1550
00:53:01,599 --> 00:53:02,880
uh

1551
00:53:02,880 --> 00:53:04,720
what do you do next yeah i mean okay i

1552
00:53:04,720 --> 00:53:06,800
think i should cover that now i think um

1553
00:53:06,800 --> 00:53:08,480
so okay um

1554
00:53:08,480 --> 00:53:09,920
you don't actually send the block hash

1555
00:53:09,920 --> 00:53:11,280
um you just send basically the block

1556
00:53:11,280 --> 00:53:12,880
header and the transactions

1557
00:53:12,880 --> 00:53:13,599
so

1558
00:53:13,599 --> 00:53:15,440
okay but i'm just i don't think you have

1559
00:53:15,440 --> 00:53:16,720
to if you're programming you wouldn't

1560
00:53:16,720 --> 00:53:18,319
you might not have to reverse it this is

1561
00:53:18,319 --> 00:53:19,599
just so i can

1562
00:53:19,599 --> 00:53:23,040
display the results correctly uh in a

1563
00:53:23,040 --> 00:53:24,720
sort of a human way

1564
00:53:24,720 --> 00:53:27,359
so again so now like a minor you just

1565
00:53:27,359 --> 00:53:29,520
change the nonce now i'm incrementing it

1566
00:53:29,520 --> 00:53:30,240
from

1567
00:53:30,240 --> 00:53:32,720
um zero one two three four five and so

1568
00:53:32,720 --> 00:53:35,359
on so there you are obviously this is in

1569
00:53:35,359 --> 00:53:36,880
network byte order

1570
00:53:36,880 --> 00:53:40,319
and so on eventually you'll get a

1571
00:53:40,319 --> 00:53:41,359
uh

1572
00:53:41,359 --> 00:53:43,280
hash uh this below the target if you're

1573
00:53:43,280 --> 00:53:44,160
lucky

1574
00:53:44,160 --> 00:53:46,319
then that's mind so when you mind the

1575
00:53:46,319 --> 00:53:47,839
actual block

1576
00:53:47,839 --> 00:53:49,280
so this is done now so this is a

1577
00:53:49,280 --> 00:53:51,280
successful block header

1578
00:53:51,280 --> 00:53:52,000
so

1579
00:53:52,000 --> 00:53:54,319
if you send this block header to anyone

1580
00:53:54,319 --> 00:53:55,760
else they can hash it for themselves and

1581
00:53:55,760 --> 00:53:57,200
they get the same result

1582
00:53:57,200 --> 00:53:58,559
that's what i think that's what they

1583
00:53:58,559 --> 00:54:00,400
call proof of work because you can just

1584
00:54:00,400 --> 00:54:01,599
send this block header to anyone and

1585
00:54:01,599 --> 00:54:03,440
they can prove for themselves that the

1586
00:54:03,440 --> 00:54:05,359
hash is below the target so what you

1587
00:54:05,359 --> 00:54:08,240
what you do then is you send this block

1588
00:54:08,240 --> 00:54:10,480
uh to all the nodes you're connected to

1589
00:54:10,480 --> 00:54:12,400
and what you're actually sending them is

1590
00:54:12,400 --> 00:54:14,480
all of the transaction data concatenated

1591
00:54:14,480 --> 00:54:16,480
together for each transaction

1592
00:54:16,480 --> 00:54:17,440
um

1593
00:54:17,440 --> 00:54:18,880
before that you put like a little

1594
00:54:18,880 --> 00:54:20,559
transaction counter

1595
00:54:20,559 --> 00:54:22,559
which is just a byte

1596
00:54:22,559 --> 00:54:25,200
it's a it's a very very variable sized

1597
00:54:25,200 --> 00:54:26,960
byte i haven't covered it but it's on

1598
00:54:26,960 --> 00:54:28,720
the website um

1599
00:54:28,720 --> 00:54:30,079
just tells you how many transactions are

1600
00:54:30,079 --> 00:54:31,839
in the block and then before that you

1601
00:54:31,839 --> 00:54:33,520
have the block header so this is what

1602
00:54:33,520 --> 00:54:35,359
gets sent to

1603
00:54:35,359 --> 00:54:37,599
um all the nodes so you don't have to

1604
00:54:37,599 --> 00:54:38,480
send the

1605
00:54:38,480 --> 00:54:39,839
block hash because they can calculate it

1606
00:54:39,839 --> 00:54:42,400
for themselves

1607
00:54:43,119 --> 00:54:44,800
so um

1608
00:54:44,800 --> 00:54:47,599
that's how mining works um what i

1609
00:54:47,599 --> 00:54:50,079
thought i would do now is um try and

1610
00:54:50,079 --> 00:54:53,200
show you how you could uh

1611
00:54:53,200 --> 00:54:56,800
mine a actual live block

1612
00:54:56,800 --> 00:54:58,160
so yeah

1613
00:54:58,160 --> 00:55:01,359
right so um if you run a bitcoin node

1614
00:55:01,359 --> 00:55:05,040
um you have the um bitcoin cli um

1615
00:55:05,040 --> 00:55:06,880
command which allows you to ask the

1616
00:55:06,880 --> 00:55:08,640
bitcoin no questions and one of them you

1617
00:55:08,640 --> 00:55:12,480
can ask them is to get block template

1618
00:55:12,480 --> 00:55:14,559
so what that will do that will take your

1619
00:55:14,559 --> 00:55:16,800
current memory pool and

1620
00:55:16,800 --> 00:55:20,240
gather the highest value transactions

1621
00:55:20,240 --> 00:55:21,839
that would fill up a

1622
00:55:21,839 --> 00:55:22,720
block

1623
00:55:22,720 --> 00:55:24,960
and

1624
00:55:25,119 --> 00:55:27,680
give them to you so this is showing me

1625
00:55:27,680 --> 00:55:29,119
all of the transactions that would make

1626
00:55:29,119 --> 00:55:30,400
a

1627
00:55:30,400 --> 00:55:32,319
candidate block

1628
00:55:32,319 --> 00:55:37,520
so um let me just move this down sorry

1629
00:55:38,000 --> 00:55:38,880
um

1630
00:55:38,880 --> 00:55:40,720
so

1631
00:55:40,720 --> 00:55:44,079
uh if we to if i just quickly examine um

1632
00:55:44,079 --> 00:55:45,359
the information

1633
00:55:45,359 --> 00:55:48,079
inside here if you if you um use bitcoin

1634
00:55:48,079 --> 00:55:50,640
cli help get block template that will

1635
00:55:50,640 --> 00:55:52,640
show you um all the fields that will

1636
00:55:52,640 --> 00:55:55,119
give you all the fields they'll produce

1637
00:55:55,119 --> 00:55:57,920
um but if i just quickly

1638
00:55:57,920 --> 00:55:59,520
um

1639
00:55:59,520 --> 00:56:02,319
what we want to see basically to minor

1640
00:56:02,319 --> 00:56:04,319
block is to create a block header from

1641
00:56:04,319 --> 00:56:06,240
all these transactions

1642
00:56:06,240 --> 00:56:09,680
so bitcoin cli get block template

1643
00:56:09,680 --> 00:56:11,520
and i'm going to use um

1644
00:56:11,520 --> 00:56:14,319
grep just to search for the fields that

1645
00:56:14,319 --> 00:56:15,680
we want

1646
00:56:15,680 --> 00:56:19,200
i'm using rg which is a variant of grep

1647
00:56:19,200 --> 00:56:21,760
and so we want to find we want to have a

1648
00:56:21,760 --> 00:56:22,720
version

1649
00:56:22,720 --> 00:56:24,160
number

1650
00:56:24,160 --> 00:56:27,599
we want the previous block

1651
00:56:27,920 --> 00:56:30,480
then we want the merkle root

1652
00:56:30,480 --> 00:56:31,359
um

1653
00:56:31,359 --> 00:56:32,559
then we want

1654
00:56:32,559 --> 00:56:33,440
time

1655
00:56:33,440 --> 00:56:34,799
then bits

1656
00:56:34,799 --> 00:56:36,400
then there's a nonce but

1657
00:56:36,400 --> 00:56:37,920
we're going to provide our own nuns so

1658
00:56:37,920 --> 00:56:39,440
we don't need that

1659
00:56:39,440 --> 00:56:41,359
so looking at the

1660
00:56:41,359 --> 00:56:45,000
i spelt that wrong

1661
00:56:45,200 --> 00:56:47,520
there we are so

1662
00:56:47,520 --> 00:56:49,280
looking at the results of block get

1663
00:56:49,280 --> 00:56:51,200
block template it's given us the version

1664
00:56:51,200 --> 00:56:52,960
the previous block hash it's also giving

1665
00:56:52,960 --> 00:56:56,160
us the time current time and bits

1666
00:56:56,160 --> 00:56:58,480
so it's changing the current time

1667
00:56:58,480 --> 00:57:00,000
so what it's not giving us is a miracle

1668
00:57:00,000 --> 00:57:01,440
root

1669
00:57:01,440 --> 00:57:02,880
um

1670
00:57:02,880 --> 00:57:05,520
for some i don't know why it's not um

1671
00:57:05,520 --> 00:57:07,440
but what you can do

1672
00:57:07,440 --> 00:57:12,160
um what it is giving you is um

1673
00:57:12,160 --> 00:57:13,520
this is just a

1674
00:57:13,520 --> 00:57:15,440
json parser

1675
00:57:15,440 --> 00:57:17,520
it has given you um

1676
00:57:17,520 --> 00:57:19,440
a list of

1677
00:57:19,440 --> 00:57:20,799
transactions

1678
00:57:20,799 --> 00:57:22,400
and it has given you all the transaction

1679
00:57:22,400 --> 00:57:25,040
ids so if we just go through each one

1680
00:57:25,040 --> 00:57:27,040
and say give us

1681
00:57:27,040 --> 00:57:29,599
the transaction ids

1682
00:57:29,599 --> 00:57:33,920
now let's need to put that in quotes

1683
00:57:36,240 --> 00:57:37,599
there we are so these are all the

1684
00:57:37,599 --> 00:57:39,680
transaction ids

1685
00:57:39,680 --> 00:57:41,760
in this candidate block

1686
00:57:41,760 --> 00:57:43,200
so now we've got all those transaction

1687
00:57:43,200 --> 00:57:44,400
ids we just need to create our own

1688
00:57:44,400 --> 00:57:46,480
merkle route for them

1689
00:57:46,480 --> 00:57:47,200
so

1690
00:57:47,200 --> 00:57:49,839
um luckily i've written my own script

1691
00:57:49,839 --> 00:57:51,760
and that will take in a list of

1692
00:57:51,760 --> 00:57:53,599
transactions and create a miracle route

1693
00:57:53,599 --> 00:57:55,359
from them

1694
00:57:55,359 --> 00:57:56,960
um i've made this available on the

1695
00:57:56,960 --> 00:57:58,960
website i'll show it in the moment

1696
00:57:58,960 --> 00:58:00,720
so if i just do that

1697
00:58:00,720 --> 00:58:02,880
then we have a miracle root

1698
00:58:02,880 --> 00:58:05,839
so now um we've got all the data we need

1699
00:58:05,839 --> 00:58:07,280
to mine a

1700
00:58:07,280 --> 00:58:08,799
both or basically to construct a block

1701
00:58:08,799 --> 00:58:10,640
header

1702
00:58:10,640 --> 00:58:12,480
so if you just bare with me for five

1703
00:58:12,480 --> 00:58:14,400
minutes i'm gonna go through each field

1704
00:58:14,400 --> 00:58:16,079
and um

1705
00:58:16,079 --> 00:58:18,720
yeah so first of all uh we need to get

1706
00:58:18,720 --> 00:58:20,640
the version

1707
00:58:20,640 --> 00:58:23,119
oh that's done wrong

1708
00:58:23,119 --> 00:58:25,200
okay

1709
00:58:25,200 --> 00:58:27,440
so there we are using get a get block

1710
00:58:27,440 --> 00:58:29,119
template this is the current version uh

1711
00:58:29,119 --> 00:58:32,079
like i said they've changed a bit so um

1712
00:58:32,079 --> 00:58:33,040
this is

1713
00:58:33,040 --> 00:58:34,640
they've been used to vote for voting so

1714
00:58:34,640 --> 00:58:36,960
this is why it's a very high number but

1715
00:58:36,960 --> 00:58:38,160
i'm not going to spend it now just take

1716
00:58:38,160 --> 00:58:39,680
it as it is

1717
00:58:39,680 --> 00:58:40,480
um

1718
00:58:40,480 --> 00:58:41,920
so this is the version number but

1719
00:58:41,920 --> 00:58:44,559
obviously it's in uh decimal so to

1720
00:58:44,559 --> 00:58:46,240
convert that into

1721
00:58:46,240 --> 00:58:49,440
hexadecimal first first so there we are

1722
00:58:49,440 --> 00:58:50,400
and then

1723
00:58:50,400 --> 00:58:52,480
now it's in hexadecimal this is already

1724
00:58:52,480 --> 00:58:54,559
um four bytes

1725
00:58:54,559 --> 00:58:57,119
so i just swap the byte order or swap

1726
00:58:57,119 --> 00:58:59,920
the endianness because sometimes

1727
00:58:59,920 --> 00:59:01,280
um

1728
00:59:01,280 --> 00:59:03,119
the byte order is referred to referred

1729
00:59:03,119 --> 00:59:05,359
to as endianness

1730
00:59:05,359 --> 00:59:06,720
um

1731
00:59:06,720 --> 00:59:09,359
so there we are so this is the

1732
00:59:09,359 --> 00:59:10,160
uh

1733
00:59:10,160 --> 00:59:12,480
version all set up and ready to go so

1734
00:59:12,480 --> 00:59:13,599
i'll just

1735
00:59:13,599 --> 00:59:15,119
trim the end off that

1736
00:59:15,119 --> 00:59:16,640
because i'm going to concatenate it all

1737
00:59:16,640 --> 00:59:20,160
together so if i save this as a

1738
00:59:20,160 --> 00:59:22,640
variable

1739
00:59:25,680 --> 00:59:26,880
there we have so just

1740
00:59:26,880 --> 00:59:29,359
echo that out to check

1741
00:59:29,359 --> 00:59:31,520
so that's the version done so next up

1742
00:59:31,520 --> 00:59:33,839
after the version is the

1743
00:59:33,839 --> 00:59:37,520
version previous block

1744
00:59:37,599 --> 00:59:39,599
so previous block

1745
00:59:39,599 --> 00:59:40,799
hash

1746
00:59:40,799 --> 00:59:42,559
so this is the block hash for the

1747
00:59:42,559 --> 00:59:44,559
previous block

1748
00:59:44,559 --> 00:59:47,119
let me just trim off the

1749
00:59:47,119 --> 00:59:49,520
uh quotes

1750
00:59:49,520 --> 00:59:51,040
and then

1751
00:59:51,040 --> 00:59:52,640
uh it's already in hex decimal it's

1752
00:59:52,640 --> 00:59:55,440
already 32 bytes so what i need to do is

1753
00:59:55,440 --> 00:59:57,680
sort the byte order or put it into

1754
00:59:57,680 --> 00:59:59,040
little endian

1755
00:59:59,040 --> 01:00:01,760
so there we are and then i can save this

1756
01:00:01,760 --> 01:00:03,599
then

1757
01:00:03,599 --> 01:00:07,200
as the previous block variable

1758
01:00:11,119 --> 01:00:15,040
next up then is the miracle root

1759
01:00:15,040 --> 01:00:16,000
uh

1760
01:00:16,000 --> 01:00:18,400
obviously we don't get a miracle root

1761
01:00:18,400 --> 01:00:21,359
um from the get block template um

1762
01:00:21,359 --> 01:00:23,839
command but what does give us is the

1763
01:00:23,839 --> 01:00:25,440
list of transactions

1764
01:00:25,440 --> 01:00:28,559
and for each of those it will give us um

1765
01:00:28,559 --> 01:00:30,480
a transaction id

1766
01:00:30,480 --> 01:00:31,440
oops

1767
01:00:31,440 --> 01:00:33,599
oh well i just lost that

1768
01:00:33,599 --> 01:00:35,280
oh there it is

1769
01:00:35,280 --> 01:00:37,440
so there we go

1770
01:00:37,440 --> 01:00:41,760
and from these i can get the merkle root

1771
01:00:41,760 --> 01:00:44,000
there we are and then it's already in

1772
01:00:44,000 --> 01:00:46,079
hexadecimal it's already in

1773
01:00:46,079 --> 01:00:48,079
32 bytes i just need to sort the byte

1774
01:00:48,079 --> 01:00:49,599
order

1775
01:00:49,599 --> 01:00:50,960
again

1776
01:00:50,960 --> 01:00:52,960
uh there we are i'll save that as a

1777
01:00:52,960 --> 01:00:54,240
variable

1778
01:00:54,240 --> 01:00:56,799
i'm going to call

1779
01:00:58,640 --> 01:01:00,559
nearly there i know it's a bit laborious

1780
01:01:00,559 --> 01:01:03,680
but uh so that's yeah so version

1781
01:01:03,680 --> 01:01:05,920
previous block miracle root uh then we

1782
01:01:05,920 --> 01:01:07,040
have the time

1783
01:01:07,040 --> 01:01:08,839
um for some reason

1784
01:01:08,839 --> 01:01:10,480
um

1785
01:01:10,480 --> 01:01:12,640
even though the get plot template

1786
01:01:12,640 --> 01:01:14,000
doesn't give you the merkel route it

1787
01:01:14,000 --> 01:01:15,119
does give you

1788
01:01:15,119 --> 01:01:17,520
the current time on your computer

1789
01:01:17,520 --> 01:01:19,280
um

1790
01:01:19,280 --> 01:01:21,200
actually it gives you a

1791
01:01:21,200 --> 01:01:24,880
valid time i'm not sure if this is um

1792
01:01:24,880 --> 01:01:25,839
i don't know but this is definitely a

1793
01:01:25,839 --> 01:01:27,760
valid time but what you could do if you

1794
01:01:27,760 --> 01:01:29,440
want to use that if you want to use the

1795
01:01:29,440 --> 01:01:30,480
get blocked

1796
01:01:30,480 --> 01:01:32,079
template time you can use the date

1797
01:01:32,079 --> 01:01:34,400
function from a programming language

1798
01:01:34,400 --> 01:01:36,240
so if you just this gives you the number

1799
01:01:36,240 --> 01:01:37,599
of seconds

1800
01:01:37,599 --> 01:01:39,680
in unix times if i just use that

1801
01:01:39,680 --> 01:01:42,799
um just need to get it into hexadecimal

1802
01:01:42,799 --> 01:01:44,000
like so

1803
01:01:44,000 --> 01:01:46,720
one two three four five six seven so 24

1804
01:01:46,720 --> 01:01:47,920
bytes

1805
01:01:47,920 --> 01:01:48,799
uh

1806
01:01:48,799 --> 01:01:51,960
then we

1807
01:01:52,079 --> 01:01:53,599
it to and

1808
01:01:53,599 --> 01:01:56,319
uh reverse bite order

1809
01:01:56,319 --> 01:01:58,160
there we are so there is that's the time

1810
01:01:58,160 --> 01:01:59,040
ready

1811
01:01:59,040 --> 01:02:00,799
enough

1812
01:02:00,799 --> 01:02:02,240
and

1813
01:02:02,240 --> 01:02:04,480
that's the time done

1814
01:02:04,480 --> 01:02:07,440
lastly uh bits

1815
01:02:07,440 --> 01:02:09,119
which is the compact version of the

1816
01:02:09,119 --> 01:02:11,359
target

1817
01:02:11,359 --> 01:02:14,079
there it is you just trim off the

1818
01:02:14,079 --> 01:02:16,240
uh

1819
01:02:16,960 --> 01:02:18,079
quotes

1820
01:02:18,079 --> 01:02:21,839
and then put into reverse byte order

1821
01:02:22,400 --> 01:02:24,720
and there it is so now we've got all the

1822
01:02:24,720 --> 01:02:28,160
basic block header data

1823
01:02:28,160 --> 01:02:29,200
uh

1824
01:02:29,200 --> 01:02:31,599
ready

1825
01:02:32,160 --> 01:02:36,160
in the right format so if i

1826
01:02:36,160 --> 01:02:38,240
just construct the block header from

1827
01:02:38,240 --> 01:02:39,839
each individ each of those individual

1828
01:02:39,839 --> 01:02:40,960
fields

1829
01:02:40,960 --> 01:02:43,359
that is the version

1830
01:02:43,359 --> 01:02:46,799
the previous block

1831
01:02:46,839 --> 01:02:50,400
the miracle root

1832
01:02:50,400 --> 01:02:52,000
then

1833
01:02:52,000 --> 01:02:53,119
time

1834
01:02:53,119 --> 01:02:55,280
and then bits

1835
01:02:55,280 --> 01:02:58,640
so check what that looks like

1836
01:02:58,960 --> 01:03:00,640
there it is there's our block header and

1837
01:03:00,640 --> 01:03:02,480
so all we have all we haven't put there

1838
01:03:02,480 --> 01:03:04,160
now is the nonce

1839
01:03:04,160 --> 01:03:05,040
so

1840
01:03:05,040 --> 01:03:06,960
if we wanted to

1841
01:03:06,960 --> 01:03:08,960
mine this we just need to create a loop

1842
01:03:08,960 --> 01:03:10,079
that will

1843
01:03:10,079 --> 01:03:12,400
keep hashing this

1844
01:03:12,400 --> 01:03:13,280
uh

1845
01:03:13,280 --> 01:03:15,520
block header and we'll adjust the nonce

1846
01:03:15,520 --> 01:03:17,599
increment it with every attempt

1847
01:03:17,599 --> 01:03:20,480
so the nonce um will look like we'll

1848
01:03:20,480 --> 01:03:22,640
start off with zero

1849
01:03:22,640 --> 01:03:24,000
um but obviously we need to get this in

1850
01:03:24,000 --> 01:03:25,920
the right format um so we need to

1851
01:03:25,920 --> 01:03:28,839
convert that to um

1852
01:03:28,839 --> 01:03:30,960
uh extradition

1853
01:03:30,960 --> 01:03:32,240
sorry thank you

1854
01:03:32,240 --> 01:03:36,319
uh then at least so like so

1855
01:03:37,119 --> 01:03:38,880
uh but obviously this needs to be um

1856
01:03:38,880 --> 01:03:40,640
four bytes in length so i made a little

1857
01:03:40,640 --> 01:03:42,000
function that will just make sure it's

1858
01:03:42,000 --> 01:03:43,359
the right size

1859
01:03:43,359 --> 01:03:45,280
and then convert the swap end in

1860
01:03:45,280 --> 01:03:46,720
obviously it's not very interesting

1861
01:03:46,720 --> 01:03:48,559
because i've used the number zero but if

1862
01:03:48,559 --> 01:03:50,000
i wish to use like a much higher nonce

1863
01:03:50,000 --> 01:03:50,960
value

1864
01:03:50,960 --> 01:03:52,559
uh like that

1865
01:03:52,559 --> 01:03:55,039
then like so it's prepared it for me

1866
01:03:55,039 --> 01:03:56,319
so i'm not going to append this to it

1867
01:03:56,319 --> 01:03:57,440
yet what i'm going to do i'm going to

1868
01:03:57,440 --> 01:04:00,640
create a loop so while true

1869
01:04:00,640 --> 01:04:02,000
do

1870
01:04:02,000 --> 01:04:03,760
you want to

1871
01:04:03,760 --> 01:04:05,440
oh wait there before that i want to set

1872
01:04:05,440 --> 01:04:08,400
a variable to

1873
01:04:08,400 --> 01:04:11,680
an increment incremented variable ready

1874
01:04:11,680 --> 01:04:14,559
so while true

1875
01:04:14,559 --> 01:04:15,599
uh

1876
01:04:15,599 --> 01:04:16,960
do

1877
01:04:16,960 --> 01:04:18,079
want to

1878
01:04:18,079 --> 01:04:19,760
create the nonce

1879
01:04:19,760 --> 01:04:21,839
which is going to be like i just showed

1880
01:04:21,839 --> 01:04:23,280
you um

1881
01:04:23,280 --> 01:04:25,039
echo

1882
01:04:25,039 --> 01:04:26,400
i

1883
01:04:26,400 --> 01:04:28,960
uh they want to get it in deck

1884
01:04:28,960 --> 01:04:31,039
hex decimal

1885
01:04:31,039 --> 01:04:34,559
four byte field size swap endian

1886
01:04:34,559 --> 01:04:35,359
uh

1887
01:04:35,359 --> 01:04:37,760
trim off the end

1888
01:04:37,760 --> 01:04:39,440
uh so that's the non stun

1889
01:04:39,440 --> 01:04:42,319
then our attempt at

1890
01:04:42,319 --> 01:04:44,319
trying to mine the block will be just

1891
01:04:44,319 --> 01:04:45,280
the

1892
01:04:45,280 --> 01:04:48,000
uh block header we created

1893
01:04:48,000 --> 01:04:51,039
plus the nonce at the end

1894
01:04:51,039 --> 01:04:52,160
and then what we want to do is we want

1895
01:04:52,160 --> 01:04:53,440
to hash that

1896
01:04:53,440 --> 01:04:55,039
um all together so i've made a little

1897
01:04:55,039 --> 01:04:57,760
function that will hash for me um

1898
01:04:57,760 --> 01:05:00,319
called hash 256 because this

1899
01:05:00,319 --> 01:05:02,480
is just the the double hash converts the

1900
01:05:02,480 --> 01:05:04,480
binary then double hashes it i'm going

1901
01:05:04,480 --> 01:05:08,960
to hash 256 um the attempt

1902
01:05:08,960 --> 01:05:09,839
and

1903
01:05:09,839 --> 01:05:12,400
every after every attempt we want to

1904
01:05:12,400 --> 01:05:15,920
uh increment the nonce so let

1905
01:05:15,920 --> 01:05:18,559
uh i must plus so just increment the

1906
01:05:18,559 --> 01:05:20,559
notes from

1907
01:05:20,559 --> 01:05:21,680
this

1908
01:05:21,680 --> 01:05:23,760
number here actually

1909
01:05:23,760 --> 01:05:25,599
uh and then done so hopefully this will

1910
01:05:25,599 --> 01:05:27,920
work there we are so now

1911
01:05:27,920 --> 01:05:30,240
this is hashing

1912
01:05:30,240 --> 01:05:31,200
um

1913
01:05:31,200 --> 01:05:33,839
very slowly uh a block header the

1914
01:05:33,839 --> 01:05:36,000
current block header obviously it's very

1915
01:05:36,000 --> 01:05:37,680
slow it took me a long time but this is

1916
01:05:37,680 --> 01:05:40,559
actually mine trying to mine a block

1917
01:05:40,559 --> 01:05:42,319
um

1918
01:05:42,319 --> 01:05:44,000
so if that was

1919
01:05:44,000 --> 01:05:44,960
lucky

1920
01:05:44,960 --> 01:05:46,400
what you'd probably do you'd have some

1921
01:05:46,400 --> 01:05:48,480
code in there that would stop

1922
01:05:48,480 --> 01:05:51,119
um when you if yeah if it reaches the

1923
01:05:51,119 --> 01:05:52,799
target target yeah and then what you do

1924
01:05:52,799 --> 01:05:55,839
then there's a function and bitcoin cli

1925
01:05:55,839 --> 01:05:59,280
called um submit block

1926
01:05:59,520 --> 01:06:01,760
and you would just submit

1927
01:06:01,760 --> 01:06:05,839
the header the transaction count

1928
01:06:06,400 --> 01:06:08,960
and all the transaction data so if you

1929
01:06:08,960 --> 01:06:10,799
constructed a successful block header

1930
01:06:10,799 --> 01:06:12,000
you would send that to all the nodes

1931
01:06:12,000 --> 01:06:13,760
you're connected to and you'd use that

1932
01:06:13,760 --> 01:06:15,280
do that using the

1933
01:06:15,280 --> 01:06:17,280
submit block um

1934
01:06:17,280 --> 01:06:19,599
bitcoin cli command

1935
01:06:19,599 --> 01:06:21,839
is there a way to uh get the target

1936
01:06:21,839 --> 01:06:24,559
value from the bitcoin cli

1937
01:06:24,559 --> 01:06:27,039
uh yeah so um i think it's included in

1938
01:06:27,039 --> 01:06:31,680
um bitcoin cli get block template

1939
01:06:31,680 --> 01:06:35,119
yeah so um i think it's it's

1940
01:06:35,119 --> 01:06:36,480
extending the block

1941
01:06:36,480 --> 01:06:37,520
yeah so there it is so this is the

1942
01:06:37,520 --> 01:06:39,599
current target so you could grab that

1943
01:06:39,599 --> 01:06:42,160
target and then stick that summer into

1944
01:06:42,160 --> 01:06:44,079
yeah into the for loop

1945
01:06:44,079 --> 01:06:46,480
yeah but obviously um

1946
01:06:46,480 --> 01:06:48,400
that that hashing there was very very

1947
01:06:48,400 --> 01:06:49,200
slow

1948
01:06:49,200 --> 01:06:51,599
oh yeah yeah i i totally get it yeah you

1949
01:06:51,599 --> 01:06:53,200
probably want to do that yeah

1950
01:06:53,200 --> 01:06:55,039
in a single programming language this is

1951
01:06:55,039 --> 01:06:57,280
just on bash just for quick sort of

1952
01:06:57,280 --> 01:06:58,960
illustration purposes but that just goes

1953
01:06:58,960 --> 01:07:01,520
to show like how basically how simple uh

1954
01:07:01,520 --> 01:07:03,599
mining is really the hardest part is

1955
01:07:03,599 --> 01:07:05,520
just getting the data in the right order

1956
01:07:05,520 --> 01:07:07,440
um but after that it's just you just

1957
01:07:07,440 --> 01:07:09,680
increment a nonsense hash it and

1958
01:07:09,680 --> 01:07:11,119
hopefully you get a result a lucky

1959
01:07:11,119 --> 01:07:14,119
result

1960
01:07:14,319 --> 01:07:15,760
um

1961
01:07:15,760 --> 01:07:18,480
i think yeah so that's everything i

1962
01:07:18,480 --> 01:07:21,039
wanted to explain about how mining works

1963
01:07:21,039 --> 01:07:22,480
um

1964
01:07:22,480 --> 01:07:23,839
that's all the technical stuff but

1965
01:07:23,839 --> 01:07:25,119
obviously is

1966
01:07:25,119 --> 01:07:27,440
probably a lot simpler than it's made

1967
01:07:27,440 --> 01:07:29,760
out to be

1968
01:07:29,760 --> 01:07:30,559
um

1969
01:07:30,559 --> 01:07:32,400
on the website i've made all this code

1970
01:07:32,400 --> 01:07:35,119
available so each those little um hex

1971
01:07:35,119 --> 01:07:36,640
decimal converters and decimal

1972
01:07:36,640 --> 01:07:37,760
converters

1973
01:07:37,760 --> 01:07:40,960
and the swap endianness they're all here

1974
01:07:40,960 --> 01:07:42,559
there's a miracle root function on here

1975
01:07:42,559 --> 01:07:44,240
written in php

1976
01:07:44,240 --> 01:07:46,960
um it's not the prettiest um but it will

1977
01:07:46,960 --> 01:07:48,160
take a

1978
01:07:48,160 --> 01:07:49,200
list of

1979
01:07:49,200 --> 01:07:50,880
transaction ids and create american

1980
01:07:50,880 --> 01:07:52,400
route for you

1981
01:07:52,400 --> 01:07:54,400
i might not want to use it in production

1982
01:07:54,400 --> 01:07:55,599
you might want to use a different

1983
01:07:55,599 --> 01:07:57,760
library i'm sure there's loads of

1984
01:07:57,760 --> 01:07:59,039
bitcoin libraries out there with their

1985
01:07:59,039 --> 01:08:01,520
own merkle root um functions for you to

1986
01:08:01,520 --> 01:08:03,760
use

1987
01:08:04,559 --> 01:08:05,760
um

1988
01:08:05,760 --> 01:08:07,760
is there any questions about

1989
01:08:07,760 --> 01:08:09,920
that sort of mining process no i mean

1990
01:08:09,920 --> 01:08:11,520
this this was really awesome great

1991
01:08:11,520 --> 01:08:13,200
thanks a lot

1992
01:08:13,200 --> 01:08:15,359
uh

1993
01:08:16,000 --> 01:08:18,479
just curious any any experience with

1994
01:08:18,479 --> 01:08:21,198
those heavy duty miners

1995
01:08:21,198 --> 01:08:23,198
no i've not actually mined myself

1996
01:08:23,198 --> 01:08:25,359
because like we said like it's so

1997
01:08:25,359 --> 01:08:27,120
inefficient to mine on your laptop if

1998
01:08:27,120 --> 01:08:28,960
you wanted to mine now it's not a hobby

1999
01:08:28,960 --> 01:08:30,399
thing you have to sort of

2000
01:08:30,399 --> 01:08:33,120
you know buy a professional mining rig

2001
01:08:33,120 --> 01:08:34,640
and run it like a proper business which

2002
01:08:34,640 --> 01:08:37,040
is a shame because that takes mining out

2003
01:08:37,040 --> 01:08:38,880
of the hands of the average person then

2004
01:08:38,880 --> 01:08:40,560
so

2005
01:08:40,560 --> 01:08:41,920
um

2006
01:08:41,920 --> 01:08:43,359
yeah so i think if you want to get into

2007
01:08:43,359 --> 01:08:44,880
mind you you would have to really commit

2008
01:08:44,880 --> 01:08:46,319
to it

2009
01:08:46,319 --> 01:08:48,238
it's not just right gone yeah right

2010
01:08:48,238 --> 01:08:50,080
right even those guys would be doing

2011
01:08:50,080 --> 01:08:51,759
like at a fundamental level they would

2012
01:08:51,759 --> 01:08:53,759
be doing the same thing right just

2013
01:08:53,759 --> 01:08:54,799
faster

2014
01:08:54,799 --> 01:08:56,158
yes so they're just doing the exact same

2015
01:08:56,158 --> 01:08:57,600
thing constructing block header and just

2016
01:08:57,600 --> 01:08:58,960
hashing it as fast as you can like this

2017
01:08:58,960 --> 01:09:00,560
whole construction of the block header

2018
01:09:00,560 --> 01:09:02,880
is simple and takes a

2019
01:09:02,880 --> 01:09:05,359
absolute fraction of a second to do and

2020
01:09:05,359 --> 01:09:08,080
then the whole mining then the whole

2021
01:09:08,080 --> 01:09:10,080
meat of mining is hashing as fast as

2022
01:09:10,080 --> 01:09:12,400
possible

2023
01:09:13,600 --> 01:09:14,000
um

2024
01:09:14,000 --> 01:09:15,359
[Music]

2025
01:09:15,359 --> 01:09:16,640
i think i've

2026
01:09:16,640 --> 01:09:18,238
don't think i've missed anything i think

2027
01:09:18,238 --> 01:09:19,839
i've covered everything i wanted to

2028
01:09:19,839 --> 01:09:21,759
sorry i know that's a bit repetitive in

2029
01:09:21,759 --> 01:09:24,960
parts uh no no no this was a great

2030
01:09:24,960 --> 01:09:26,960
explanation again yeah thanks a lot for

2031
01:09:26,960 --> 01:09:28,000
this yeah

2032
01:09:28,000 --> 01:09:29,600
but i think if you're starting out with

2033
01:09:29,600 --> 01:09:31,679
bitcoin um

2034
01:09:31,679 --> 01:09:33,279
one of the best ways to learn i think is

2035
01:09:33,279 --> 01:09:34,880
to try and

2036
01:09:34,880 --> 01:09:36,479
mine your own block header i think it's

2037
01:09:36,479 --> 01:09:38,158
quite simple to do and i think mining is

2038
01:09:38,158 --> 01:09:40,000
one of the sort of first fundamental

2039
01:09:40,000 --> 01:09:41,839
parts of how bitcoin works so if you can

2040
01:09:41,839 --> 01:09:44,479
figure out how to mine a block header

2041
01:09:44,479 --> 01:09:46,158
or hash a block header that's a great

2042
01:09:46,158 --> 01:09:47,839
stepping stone i'll give you the tools

2043
01:09:47,839 --> 01:09:50,158
then to figure out about the all the um

2044
01:09:50,158 --> 01:09:52,960
hexadecimal and network byte order and

2045
01:09:52,960 --> 01:09:54,960
how to hash and then you can take those

2046
01:09:54,960 --> 01:09:56,560
tools then and use them in other parts

2047
01:09:56,560 --> 01:09:58,000
of bitcoin like in you know with

2048
01:09:58,000 --> 01:10:01,040
transactions and all that

2049
01:10:01,040 --> 01:10:02,719
so this would be my first place to start

2050
01:10:02,719 --> 01:10:04,960
if you were to try coding with

2051
01:10:04,960 --> 01:10:06,000
bitcoin

2052
01:10:06,000 --> 01:10:07,600
i mean you you're obviously probably not

2053
01:10:07,600 --> 01:10:08,560
going to

2054
01:10:08,560 --> 01:10:10,560
set up your minor but as a sort of

2055
01:10:10,560 --> 01:10:11,679
learning experience this is a great

2056
01:10:11,679 --> 01:10:14,320
place to start

2057
01:10:15,280 --> 01:10:17,199
so yeah if you want to browse block

2058
01:10:17,199 --> 01:10:18,880
headers just go into livia bitcoin this

2059
01:10:18,880 --> 01:10:20,560
is the blockchain

2060
01:10:20,560 --> 01:10:21,920
and you can browse to each individual

2061
01:10:21,920 --> 01:10:23,600
block and see all the different block

2062
01:10:23,600 --> 01:10:25,520
headers and test for yourself

2063
01:10:25,520 --> 01:10:27,520
then you can get the same

2064
01:10:27,520 --> 01:10:28,960
block cache results

2065
01:10:28,960 --> 01:10:31,280
nice

2066
01:10:31,280 --> 01:10:32,400
yep

2067
01:10:32,400 --> 01:10:35,280
so uh thank you very much for that uh

2068
01:10:35,280 --> 01:10:37,120
that was good to do

2069
01:10:37,120 --> 01:10:38,320
thanks

2070
01:10:38,320 --> 01:10:42,520
no worries so yeah

