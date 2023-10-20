00:00:00,640 --> 00:00:01,520
so

00:00:01,520 --> 00:00:02,720
uh in this presentation i'm going to

00:00:02,720 --> 00:00:04,880
cover how bitcoin mining works

00:00:04,880 --> 00:00:06,720
um

00:00:06,720 --> 00:00:08,480
i'll start out with what is mining and

00:00:08,480 --> 00:00:11,200
i'll cover what it is and why it exists

00:00:11,200 --> 00:00:12,240
um

00:00:12,240 --> 00:00:13,599
and then after that i'll cover how it

00:00:13,599 --> 00:00:14,559
works

00:00:14,559 --> 00:00:16,640
um but before i can cover how it works i

00:00:16,640 --> 00:00:19,119
need to explain what a hash function is

00:00:19,119 --> 00:00:20,880
um because that's like an integral part

00:00:20,880 --> 00:00:23,279
of how bitcoin works

00:00:23,279 --> 00:00:25,119
uh then i'll cover

00:00:25,119 --> 00:00:27,199
the basics of how it works and then i'll

00:00:27,199 --> 00:00:28,480
go through it again

00:00:28,480 --> 00:00:30,240
but i'll explain in a more technical way

00:00:30,240 --> 00:00:31,599
so if you're a programmer you'll find

00:00:31,599 --> 00:00:33,360
that more interesting

00:00:33,360 --> 00:00:35,120
um then after that i'll start doing some

00:00:35,120 --> 00:00:37,280
examples and i'll try and show you how

00:00:37,280 --> 00:00:39,760
um you could actually mine a live block

00:00:39,760 --> 00:00:43,200
um in a very small amount of code

00:00:43,200 --> 00:00:44,879
so that's what the presentation is going

00:00:44,879 --> 00:00:47,440
to be so i'll get started with then

00:00:47,440 --> 00:00:49,600
what mining is

00:00:49,600 --> 00:00:51,680
so what is mining

00:00:51,680 --> 00:00:53,120
um well imagine this is the bitcoin

00:00:53,120 --> 00:00:54,160
network

00:00:54,160 --> 00:00:56,079
and these were all the computers uh

00:00:56,079 --> 00:00:57,840
connected together running the bitcoin

00:00:57,840 --> 00:00:59,039
program

00:00:59,039 --> 00:01:01,840
and sharing the same file which is this

00:01:01,840 --> 00:01:04,000
blockchain

00:01:04,000 --> 00:01:06,400
um the way bitcoin works um if you want

00:01:06,400 --> 00:01:09,040
to send a bitcoin to someone

00:01:09,040 --> 00:01:09,760
or

00:01:09,760 --> 00:01:11,760
transfer ownership of a bitcoin

00:01:11,760 --> 00:01:13,040
to someone else

00:01:13,040 --> 00:01:14,320
the way you do that is you create a

00:01:14,320 --> 00:01:16,320
transaction with just a little line of

00:01:16,320 --> 00:01:17,280
data

00:01:17,280 --> 00:01:19,200
and then you'll insert that into a node

00:01:19,200 --> 00:01:21,040
on the network

00:01:21,040 --> 00:01:23,840
um and then

00:01:23,840 --> 00:01:25,759
if we didn't have mining the way this

00:01:25,759 --> 00:01:27,840
would work was that computer would write

00:01:27,840 --> 00:01:30,400
it straight to the blockchain

00:01:30,400 --> 00:01:31,840
to the shared file

00:01:31,840 --> 00:01:33,439
and then what they would do they would

00:01:33,439 --> 00:01:34,960
pass on that

00:01:34,960 --> 00:01:37,119
transaction that piece of data onto the

00:01:37,119 --> 00:01:38,960
nodes they're connected to and they will

00:01:38,960 --> 00:01:40,640
write it to their file

00:01:40,640 --> 00:01:42,880
and so on and so on until that

00:01:42,880 --> 00:01:45,680
transaction has propagated

00:01:45,680 --> 00:01:48,320
uh the entire network

00:01:48,320 --> 00:01:50,159
and written it to their shared file so

00:01:50,159 --> 00:01:52,159
that would be a simple way of you know

00:01:52,159 --> 00:01:54,079
having a shared file or shared ledger

00:01:54,079 --> 00:01:56,079
transactions

00:01:56,079 --> 00:01:57,439
and then

00:01:57,439 --> 00:01:58,799
when everyone's updated their copy of

00:01:58,799 --> 00:02:01,200
the file you know um

00:02:01,200 --> 00:02:02,960
the ownership then as that of that

00:02:02,960 --> 00:02:05,280
bitcoin has changed from one person to

00:02:05,280 --> 00:02:06,719
the next person

00:02:06,719 --> 00:02:09,038
and that'll be a simple transaction

00:02:09,038 --> 00:02:11,120
um but there's a problem um that needs

00:02:11,120 --> 00:02:14,000
to be solved if you do it this way

00:02:14,000 --> 00:02:15,200
um

00:02:15,200 --> 00:02:17,440
let's color this man in green um what

00:02:17,440 --> 00:02:18,560
you can do

00:02:18,560 --> 00:02:20,959
is you can create a transaction to send

00:02:20,959 --> 00:02:22,560
the bitcoin to this person

00:02:22,560 --> 00:02:24,239
and insert it into a node on this side

00:02:24,239 --> 00:02:25,440
of the network

00:02:25,440 --> 00:02:27,599
um but what you can do because it's a

00:02:27,599 --> 00:02:29,599
network of connected computers

00:02:29,599 --> 00:02:32,720
um you could create a second transaction

00:02:32,720 --> 00:02:36,400
um that sends the very same bitcoin

00:02:36,400 --> 00:02:38,160
to a different person

00:02:38,160 --> 00:02:39,200
so

00:02:39,200 --> 00:02:40,720
you've just inserted

00:02:40,720 --> 00:02:42,319
two separate transactions into the

00:02:42,319 --> 00:02:46,080
network trying to spend the same bitcoin

00:02:46,080 --> 00:02:47,360
and you can do this because it's a

00:02:47,360 --> 00:02:49,200
network

00:02:49,200 --> 00:02:50,959
so what will happen from there

00:02:50,959 --> 00:02:53,280
is these two transactions will start

00:02:53,280 --> 00:02:55,200
propagating the network

00:02:55,200 --> 00:02:56,480
and the computers on this side as you

00:02:56,480 --> 00:02:57,280
can see

00:02:57,280 --> 00:02:59,760
they have received this red transaction

00:02:59,760 --> 00:03:01,599
and the second one but the committee's

00:03:01,599 --> 00:03:03,120
on this side they've received the green

00:03:03,120 --> 00:03:04,640
transaction

00:03:04,640 --> 00:03:05,920
uh when

00:03:05,920 --> 00:03:08,239
this computer here tries to pass on the

00:03:08,239 --> 00:03:10,400
green transaction to this computer um

00:03:10,400 --> 00:03:12,239
this computer has already received the

00:03:12,239 --> 00:03:14,400
red transaction spending that this

00:03:14,400 --> 00:03:15,440
bitcoin

00:03:15,440 --> 00:03:17,840
so they would reject it which is good

00:03:17,840 --> 00:03:19,360
but then you still have the problem then

00:03:19,360 --> 00:03:20,239
of

00:03:20,239 --> 00:03:22,800
um these two conflicting transactions on

00:03:22,800 --> 00:03:24,800
the network or basically

00:03:24,800 --> 00:03:26,560
um if you look at the network as a whole

00:03:26,560 --> 00:03:28,720
or this file as a whole

00:03:28,720 --> 00:03:31,360
um who does this bitcoin belong to now

00:03:31,360 --> 00:03:34,640
so if you were to run bitcoin this way

00:03:34,640 --> 00:03:35,680
and

00:03:35,680 --> 00:03:36,640
write

00:03:36,640 --> 00:03:38,720
transactions directly to the file you

00:03:38,720 --> 00:03:42,400
could create this double spend problem

00:03:42,400 --> 00:03:45,360
so basically bitcoin solves this problem

00:03:45,360 --> 00:03:47,280
of not having

00:03:47,280 --> 00:03:49,120
conflicting transactions written to the

00:03:49,120 --> 00:03:51,599
blockchain or to this shared file

00:03:51,599 --> 00:03:53,280
and that is what mining is

00:03:53,280 --> 00:03:56,319
so the way bitcoin solves this

00:03:56,319 --> 00:03:58,239
and this is really this solution now is

00:03:58,239 --> 00:04:00,159
what makes bitcoin interesting because

00:04:00,159 --> 00:04:02,000
we've had this technology before we're

00:04:02,000 --> 00:04:04,000
going to have gone

00:04:04,000 --> 00:04:06,720
do a question

00:04:10,640 --> 00:04:15,480
okay okay did you miss anything

00:04:17,279 --> 00:04:18,880
okay

00:04:18,880 --> 00:04:20,000
okay

00:04:20,000 --> 00:04:21,199
um

00:04:21,199 --> 00:04:24,560
so bitcoin solves this uh problem

00:04:24,560 --> 00:04:26,240
of having

00:04:26,240 --> 00:04:28,320
you know um writing two conflicting

00:04:28,320 --> 00:04:30,880
transactions to a shared file

00:04:30,880 --> 00:04:33,199
uh and this is what makes bitcoin um

00:04:33,199 --> 00:04:34,720
interesting and this is what the sort of

00:04:34,720 --> 00:04:37,199
i suppose the invention of bitcoin is

00:04:37,199 --> 00:04:38,960
um so the way bitcoin solves this double

00:04:38,960 --> 00:04:42,800
spend um problem is that it gives um

00:04:42,800 --> 00:04:44,479
every computer running the bitcoin

00:04:44,479 --> 00:04:47,280
program um some temporary memory uh

00:04:47,280 --> 00:04:49,280
called the memory pool

00:04:49,280 --> 00:04:50,960
so what will happen is

00:04:50,960 --> 00:04:53,280
you can't stop this double spend attack

00:04:53,280 --> 00:04:56,000
but what will happen is um the person

00:04:56,000 --> 00:04:57,759
will insert a transaction into this

00:04:57,759 --> 00:05:00,720
computer this green transaction

00:05:00,720 --> 00:05:02,400
and then they can go over here and do

00:05:02,400 --> 00:05:04,000
the same you know double spend attack

00:05:04,000 --> 00:05:05,680
again and insert this second red

00:05:05,680 --> 00:05:07,600
transaction into this computer

00:05:07,600 --> 00:05:08,400
um

00:05:08,400 --> 00:05:11,199
but obviously these two transactions

00:05:11,199 --> 00:05:12,880
aren't written directly to the file they

00:05:12,880 --> 00:05:15,759
get stored in temporary memory first

00:05:15,759 --> 00:05:16,479
so

00:05:16,479 --> 00:05:18,400
um again the same thing happens both

00:05:18,400 --> 00:05:20,560
transactions propagate the network and

00:05:20,560 --> 00:05:23,039
this one will eject the green one

00:05:23,039 --> 00:05:24,639
because they have already received the

00:05:24,639 --> 00:05:25,919
red one

00:05:25,919 --> 00:05:28,800
um and so there we are um

00:05:28,800 --> 00:05:30,639
both transactions on the network but

00:05:30,639 --> 00:05:32,000
they're not written to the file yet so

00:05:32,000 --> 00:05:34,560
the file is still secure

00:05:34,560 --> 00:05:36,880
um what will happen then is um all of

00:05:36,880 --> 00:05:40,080
these computers um will work to try and

00:05:40,080 --> 00:05:42,080
get the transactions from their memory

00:05:42,080 --> 00:05:42,880
pool

00:05:42,880 --> 00:05:44,880
onto the file

00:05:44,880 --> 00:05:46,720
um so they're all competing basically to

00:05:46,720 --> 00:05:49,120
be the first one to get their memory

00:05:49,120 --> 00:05:51,440
pool transactions added

00:05:51,440 --> 00:05:53,199
onto the top of the file

00:05:53,199 --> 00:05:55,280
so let's say this one is the first one

00:05:55,280 --> 00:05:56,880
that's able to do it

00:05:56,880 --> 00:05:58,800
and they add their transactions

00:05:58,800 --> 00:06:00,400
from their memory pool onto the file

00:06:00,400 --> 00:06:03,360
like so and when they've done that

00:06:03,360 --> 00:06:05,840
and they will pass on the updated copy

00:06:05,840 --> 00:06:07,759
of the file to everyone else they're

00:06:07,759 --> 00:06:08,880
connected to

00:06:08,880 --> 00:06:11,039
and they will update their copies

00:06:11,039 --> 00:06:13,280
and this node here

00:06:13,280 --> 00:06:14,800
because they've got this conflicting

00:06:14,800 --> 00:06:16,560
green transaction in their memory pool

00:06:16,560 --> 00:06:18,560
but they've just received this red

00:06:18,560 --> 00:06:19,680
transaction

00:06:19,680 --> 00:06:22,000
spending the same bitcoins um they will

00:06:22,000 --> 00:06:23,520
kick out the screen transaction from

00:06:23,520 --> 00:06:25,440
their memory pool so this memory pool is

00:06:25,440 --> 00:06:27,280
like a waiting area or like a clearing

00:06:27,280 --> 00:06:28,880
house

00:06:28,880 --> 00:06:30,880
and they've received this

00:06:30,880 --> 00:06:33,120
red transaction in in the in the updated

00:06:33,120 --> 00:06:34,560
file so i'll kick out this conflicting

00:06:34,560 --> 00:06:35,360
one

00:06:35,360 --> 00:06:37,199
and then this node will pass on the

00:06:37,199 --> 00:06:39,520
updated copy to these nodes also and

00:06:39,520 --> 00:06:41,199
they will do the same thing they'll kick

00:06:41,199 --> 00:06:43,360
out any conflicting transactions

00:06:43,360 --> 00:06:46,000
from their memory pool

00:06:46,000 --> 00:06:48,240
so that's how you solve the the problem

00:06:48,240 --> 00:06:50,080
of having two conflicting transactions

00:06:50,080 --> 00:06:52,319
on the network you just literally have

00:06:52,319 --> 00:06:54,080
uh a waiting area

00:06:54,080 --> 00:06:56,720
and all of the nodes compete to try and

00:06:56,720 --> 00:06:59,759
add their transactions onto the file

00:06:59,759 --> 00:07:01,039
um

00:07:01,039 --> 00:07:04,560
like so and there we are this person now

00:07:04,560 --> 00:07:06,080
has the bitcoin

00:07:06,080 --> 00:07:07,759
and so this proceed there's basically

00:07:07,759 --> 00:07:10,800
this process of every node competing to

00:07:10,800 --> 00:07:12,080
try and get their transactions from

00:07:12,080 --> 00:07:14,240
their memory pool onto the file is

00:07:14,240 --> 00:07:15,759
called mining and that's why i'm going

00:07:15,759 --> 00:07:17,280
to explain how it works now this you

00:07:17,280 --> 00:07:18,639
know getting these transactions onto

00:07:18,639 --> 00:07:20,800
here

00:07:20,800 --> 00:07:23,039
is any questions about that so far

00:07:23,039 --> 00:07:24,880
not really but one thing to note here is

00:07:24,880 --> 00:07:25,759
that

00:07:25,759 --> 00:07:27,840
every node in the network is not

00:07:27,840 --> 00:07:29,840
necessarily mining oh yes that's true

00:07:29,840 --> 00:07:32,240
yeah yeah i just made a very simple like

00:07:32,240 --> 00:07:33,840
diagram trying to

00:07:33,840 --> 00:07:36,080
um yeah but

00:07:36,080 --> 00:07:37,280
yes so

00:07:37,280 --> 00:07:39,360
some of these might not be mining

00:07:39,360 --> 00:07:40,720
um you can just run a node that will

00:07:40,720 --> 00:07:43,360
relay the blocks and transactions

00:07:43,360 --> 00:07:45,840
um yeah but in this particular

00:07:45,840 --> 00:07:47,680
simplified diagram everyone's trying to

00:07:47,680 --> 00:07:50,400
mine but obviously

00:07:50,400 --> 00:07:53,360
yeah so yeah let's say we have a node

00:07:53,360 --> 00:07:56,160
that is not binding so if it gets a

00:07:56,160 --> 00:07:58,479
block

00:07:58,720 --> 00:08:01,280
which has a transaction

00:08:01,280 --> 00:08:03,039
and a conflicting transaction in the

00:08:03,039 --> 00:08:05,520
memory pool it will take it out um yeah

00:08:05,520 --> 00:08:07,120
all this relaying of blocks and

00:08:07,120 --> 00:08:09,360
transactions a node will do this

00:08:09,360 --> 00:08:11,520
but a minor just as this

00:08:11,520 --> 00:08:13,199
latter part of trying to add the

00:08:13,199 --> 00:08:15,599
transactions from the memory pool that

00:08:15,599 --> 00:08:17,759
that is a minor this part here but you

00:08:17,759 --> 00:08:21,440
can be a node but you don't have to mine

00:08:21,440 --> 00:08:25,639
um okay is that right

00:08:26,319 --> 00:08:29,599
okay so that's the intro done

00:08:29,599 --> 00:08:31,840
so the next part now is explaining what

00:08:31,840 --> 00:08:33,519
this um

00:08:33,519 --> 00:08:35,919
hash function is so then i'll cover how

00:08:35,919 --> 00:08:38,880
bitcoin mining works

00:08:38,880 --> 00:08:41,279
um right so a hash function

00:08:41,279 --> 00:08:43,279
but a hash function is just like a small

00:08:43,279 --> 00:08:45,920
um computer program um that does

00:08:45,920 --> 00:08:48,320
that's quite useful um but the way it

00:08:48,320 --> 00:08:51,200
works is you you can have some data so

00:08:51,200 --> 00:08:53,360
this is letter a and number one and you

00:08:53,360 --> 00:08:55,600
can insert it into the hash function

00:08:55,600 --> 00:08:58,000
and the hash function will basically

00:08:58,000 --> 00:08:59,200
scramble it

00:08:59,200 --> 00:09:02,560
and produce a random

00:09:02,560 --> 00:09:06,160
string of data as a result

00:09:06,320 --> 00:09:07,360
and

00:09:07,360 --> 00:09:08,800
the useful property about the hash

00:09:08,800 --> 00:09:10,560
function is that you can put the same

00:09:10,560 --> 00:09:12,640
data into it and it will always spit out

00:09:12,640 --> 00:09:14,240
the same result so basically it will

00:09:14,240 --> 00:09:16,480
scramble it in the same way to produce

00:09:16,480 --> 00:09:17,279
this

00:09:17,279 --> 00:09:19,600
random

00:09:19,600 --> 00:09:22,080
string of data

00:09:22,080 --> 00:09:23,600
and this string of data will always be

00:09:23,600 --> 00:09:26,880
the same size which is 32 bytes or 64

00:09:26,880 --> 00:09:28,480
characters because there are two

00:09:28,480 --> 00:09:31,360
characters per byte

00:09:31,360 --> 00:09:32,560
um so

00:09:32,560 --> 00:09:34,640
if you were to make a tiny adjustment to

00:09:34,640 --> 00:09:36,080
the

00:09:36,080 --> 00:09:37,279
data you're putting into the hash

00:09:37,279 --> 00:09:38,160
function

00:09:38,160 --> 00:09:40,560
so from here just go from a one to a two

00:09:40,560 --> 00:09:43,200
just a tiny adjustment put that in and

00:09:43,200 --> 00:09:45,519
the result would be completely different

00:09:45,519 --> 00:09:47,600
so we've only made a tiny adjustment but

00:09:47,600 --> 00:09:49,360
the result of the hash function is

00:09:49,360 --> 00:09:51,440
wildly different

00:09:51,440 --> 00:09:54,399
um and again put a3 into it

00:09:54,399 --> 00:09:55,839
tiny adjustment again

00:09:55,839 --> 00:09:57,440
but the result is completely different

00:09:57,440 --> 00:09:58,640
again

00:09:58,640 --> 00:10:00,240
and an important part about a hash

00:10:00,240 --> 00:10:01,839
function as well

00:10:01,839 --> 00:10:03,120
is that if you don't know what the

00:10:03,120 --> 00:10:06,880
result um is beforehand there's no way

00:10:06,880 --> 00:10:09,600
you can predict what you know a2 is

00:10:09,600 --> 00:10:11,200
going to spit out

00:10:11,200 --> 00:10:11,920
so

00:10:11,920 --> 00:10:13,600
if you don't know what this is already

00:10:13,600 --> 00:10:15,760
is then there's no way you can sort of

00:10:15,760 --> 00:10:18,399
figure out what the results going to be

00:10:18,399 --> 00:10:19,440
which is

00:10:19,440 --> 00:10:20,640
useful

00:10:20,640 --> 00:10:22,959
as we'll come to see in a moment

00:10:22,959 --> 00:10:24,160
um

00:10:24,160 --> 00:10:25,760
also lastly

00:10:25,760 --> 00:10:26,800
even though

00:10:26,800 --> 00:10:28,160
this looks like a random well it's a

00:10:28,160 --> 00:10:30,079
random string of data it's got like the

00:10:30,079 --> 00:10:31,440
letters f

00:10:31,440 --> 00:10:34,959
e a basically a b c d e and f in there

00:10:34,959 --> 00:10:36,720
and these can actually be converted into

00:10:36,720 --> 00:10:37,760
numbers

00:10:37,760 --> 00:10:39,519
um and that's because

00:10:39,519 --> 00:10:41,920
um we are used to using the

00:10:41,920 --> 00:10:44,839
decimal uh format for numbers which uses

00:10:44,839 --> 00:10:48,320
the numbers zero to nine

00:10:48,320 --> 00:10:51,279
but you also have a number number format

00:10:51,279 --> 00:10:52,880
called hexadecimal which is just the

00:10:52,880 --> 00:10:55,760
same numbers but also with a b c d e and

00:10:55,760 --> 00:10:57,920
f and they are

00:10:57,920 --> 00:10:59,360
when you translate them over when you

00:10:59,360 --> 00:11:01,680
convert them over they just

00:11:01,680 --> 00:11:04,240
looks like this

00:11:04,480 --> 00:11:05,519
so

00:11:05,519 --> 00:11:07,279
this is called decimal because it uses

00:11:07,279 --> 00:11:08,160
um

00:11:08,160 --> 00:11:12,720
10 and deci in means 10 i think in latin

00:11:12,720 --> 00:11:15,040
then hexadecimal hexa like a hexagon six

00:11:15,040 --> 00:11:18,800
sides deci 10 6 10 16.

00:11:18,800 --> 00:11:19,519
so

00:11:19,519 --> 00:11:21,920
basically this is what we use as humans

00:11:21,920 --> 00:11:23,920
but computers are very happy to read

00:11:23,920 --> 00:11:26,560
numbers in hexadecimal format

00:11:26,560 --> 00:11:28,560
so basically um

00:11:28,560 --> 00:11:30,800
with a hash function you put data in and

00:11:30,800 --> 00:11:34,640
it spits out a random number as a result

00:11:34,640 --> 00:11:36,000
but

00:11:36,000 --> 00:11:37,920
so if you see um

00:11:37,920 --> 00:11:41,920
an like a string like this nope in um

00:11:41,920 --> 00:11:43,760
hex decimal format just remember that

00:11:43,760 --> 00:11:46,480
it's a random number

00:11:46,480 --> 00:11:47,760
does that make sense everything makes

00:11:47,760 --> 00:11:49,680
sense there

00:11:49,680 --> 00:11:51,360
all right brilliant so that was a hash

00:11:51,360 --> 00:11:52,240
function

00:11:52,240 --> 00:11:54,399
um just a little tool that spits out

00:11:54,399 --> 00:11:58,240
random data um if i quickly show you

00:11:58,240 --> 00:11:59,760
i don't think you see this

00:11:59,760 --> 00:12:02,800
if you can read the text but um

00:12:02,800 --> 00:12:03,760
if you can

00:12:03,760 --> 00:12:06,959
like a hash function is available in um

00:12:06,959 --> 00:12:08,720
lots of programming languages so for

00:12:08,720 --> 00:12:11,360
example in php um there's a function

00:12:11,360 --> 00:12:12,800
called hash

00:12:12,800 --> 00:12:15,200
and then you can tell it um that's gonna

00:12:15,200 --> 00:12:16,720
be wrong there

00:12:16,720 --> 00:12:18,800
and then you can tell it um

00:12:18,800 --> 00:12:20,560
which hash function you wanna use so

00:12:20,560 --> 00:12:22,079
sha256

00:12:22,079 --> 00:12:23,920
that is the one that's used in bitcoin

00:12:23,920 --> 00:12:26,000
um which stands for simple hashing

00:12:26,000 --> 00:12:27,920
algorithm 256

00:12:27,920 --> 00:12:29,959
or 265

00:12:29,959 --> 00:12:32,800
256 bits which is like the size of the

00:12:32,800 --> 00:12:34,480
result it spits out and then you can

00:12:34,480 --> 00:12:36,560
just put the

00:12:36,560 --> 00:12:38,800
uh what you want to hash into it

00:12:38,800 --> 00:12:41,440
what's going on

00:12:51,200 --> 00:12:53,680
there we are so that's the result there

00:12:53,680 --> 00:12:55,279
so you can use a hash function in any

00:12:55,279 --> 00:12:57,440
programming language um i've just showed

00:12:57,440 --> 00:12:59,920
how to use it here in php

00:12:59,920 --> 00:13:00,959
um

00:13:00,959 --> 00:13:04,000
in ruby just for

00:13:04,000 --> 00:13:05,680
uh

00:13:05,680 --> 00:13:08,240
be complete um

00:13:08,240 --> 00:13:10,160
it's included in the digest

00:13:10,160 --> 00:13:13,040
library so you can go and put

00:13:13,040 --> 00:13:15,519
digest

00:13:15,519 --> 00:13:18,480
256 then we want the hexadecimal

00:13:18,480 --> 00:13:21,839
digest digest is just another um term

00:13:21,839 --> 00:13:24,240
for the result that gets spat out from a

00:13:24,240 --> 00:13:26,000
hash function

00:13:26,000 --> 00:13:28,560
so we're gonna put a1 into there

00:13:28,560 --> 00:13:30,639
and there we have the same thing

00:13:30,639 --> 00:13:31,839
so

00:13:31,839 --> 00:13:33,760
hash function just available in lots of

00:13:33,760 --> 00:13:36,560
programming languages

00:13:37,279 --> 00:13:39,279
um okay

00:13:39,279 --> 00:13:40,720
now i'll move on to

00:13:40,720 --> 00:13:41,839
um

00:13:41,839 --> 00:13:44,079
the basics of how mining works so i'll

00:13:44,079 --> 00:13:45,760
just run through giving a quick example

00:13:45,760 --> 00:13:47,279
of how

00:13:47,279 --> 00:13:49,360
this

00:13:49,360 --> 00:13:51,279
process here of getting the transactions

00:13:51,279 --> 00:13:53,040
from the memory pool onto the blockchain

00:13:53,040 --> 00:13:54,880
works

00:13:54,880 --> 00:13:56,320
right

00:13:56,320 --> 00:13:58,639
so basics are mining

00:13:58,639 --> 00:14:00,320
here we have the net here we have the

00:14:00,320 --> 00:14:02,079
network again all the transactions the

00:14:02,079 --> 00:14:05,279
memory pool yep sorry

00:14:07,440 --> 00:14:09,440
okay um okay

00:14:09,440 --> 00:14:11,199
thanks just if it happens again just let

00:14:11,199 --> 00:14:13,680
me know and i'll

00:14:13,680 --> 00:14:15,600
um so again

00:14:15,600 --> 00:14:16,399
um

00:14:16,399 --> 00:14:17,600
we're going to look inside now this

00:14:17,600 --> 00:14:19,199
computer this um

00:14:19,199 --> 00:14:20,880
node here is a minor so we're going to

00:14:20,880 --> 00:14:22,800
look inside it and see how it mines the

00:14:22,800 --> 00:14:25,120
transactions from its memory pool onto

00:14:25,120 --> 00:14:27,600
its file

00:14:28,480 --> 00:14:31,839
right so

00:14:32,240 --> 00:14:34,880
you still there

00:14:38,160 --> 00:14:39,600
hello

00:14:39,600 --> 00:14:41,680
are you still okay right yeah okay right

00:14:41,680 --> 00:14:44,639
um so this is looking inside a bitcoin

00:14:44,639 --> 00:14:46,079
miner

00:14:46,079 --> 00:14:47,680
so this is the memory pool it's got the

00:14:47,680 --> 00:14:49,680
red transaction in there

00:14:49,680 --> 00:14:52,240
transaction in there um but with a

00:14:52,240 --> 00:14:54,240
memory pool you can have much more than

00:14:54,240 --> 00:14:56,639
one transaction in there so let's say

00:14:56,639 --> 00:14:58,399
this memory pool has got like you know

00:14:58,399 --> 00:14:59,920
quite a few transactions already in

00:14:59,920 --> 00:15:00,959
there

00:15:00,959 --> 00:15:03,839
and so what a miner will do um they will

00:15:03,839 --> 00:15:05,279
create a

00:15:05,279 --> 00:15:08,079
container called a candidate candidate

00:15:08,079 --> 00:15:09,040
block

00:15:09,040 --> 00:15:10,560
um which is just a container for

00:15:10,560 --> 00:15:12,240
transactions

00:15:12,240 --> 00:15:13,680
so what they'll do

00:15:13,680 --> 00:15:16,000
they will fill this candidate block

00:15:16,000 --> 00:15:17,920
up with transactions from their memory

00:15:17,920 --> 00:15:18,800
pool

00:15:18,800 --> 00:15:21,519
and like so

00:15:21,519 --> 00:15:23,680
and then they will try and add this

00:15:23,680 --> 00:15:26,480
block of transactions onto the file onto

00:15:26,480 --> 00:15:29,040
the blockchain

00:15:29,040 --> 00:15:30,480
so

00:15:30,480 --> 00:15:32,240
how do they get this block of this

00:15:32,240 --> 00:15:34,560
candidate block that they've built onto

00:15:34,560 --> 00:15:36,880
the blockchain

00:15:36,880 --> 00:15:38,880
well the first thing they do

00:15:38,880 --> 00:15:40,560
they construct what's called a block

00:15:40,560 --> 00:15:41,839
header

00:15:41,839 --> 00:15:44,000
um which is just like a summary of all

00:15:44,000 --> 00:15:45,600
the data inside the block all the

00:15:45,600 --> 00:15:47,839
transactions in the block

00:15:47,839 --> 00:15:49,680
um so in that block header you have

00:15:49,680 --> 00:15:51,199
something called a version which is like

00:15:51,199 --> 00:15:52,959
a version number for the block for the

00:15:52,959 --> 00:15:54,800
structure of the data so let's say

00:15:54,800 --> 00:15:56,639
that's one

00:15:56,639 --> 00:15:59,199
and they will also have

00:15:59,199 --> 00:16:00,560
some information

00:16:00,560 --> 00:16:01,920
called the previous block or the

00:16:01,920 --> 00:16:03,680
previous block hash

00:16:03,680 --> 00:16:05,600
and the way that works is

00:16:05,600 --> 00:16:08,800
let's say this is the blockchain um

00:16:08,800 --> 00:16:10,639
this block this candidate block they're

00:16:10,639 --> 00:16:12,959
building it has to build on top of one

00:16:12,959 --> 00:16:14,320
of these blocks

00:16:14,320 --> 00:16:18,639
so what a miner will do is they will um

00:16:18,639 --> 00:16:20,160
include the

00:16:20,160 --> 00:16:22,399
hash or the block hash which is like an

00:16:22,399 --> 00:16:23,680
id number

00:16:23,680 --> 00:16:25,040
for a block

00:16:25,040 --> 00:16:28,079
of the one they want to build on top of

00:16:28,079 --> 00:16:29,360
so like so

00:16:29,360 --> 00:16:30,240
so

00:16:30,240 --> 00:16:32,800
in here they will this is the block hash

00:16:32,800 --> 00:16:34,000
for this block

00:16:34,000 --> 00:16:35,519
so this just says which block they want

00:16:35,519 --> 00:16:37,360
to build on top of because every miner

00:16:37,360 --> 00:16:39,120
basically wants to build onto the top of

00:16:39,120 --> 00:16:41,759
the blockchain

00:16:42,320 --> 00:16:43,279
um

00:16:43,279 --> 00:16:45,839
merkel route now a miracle route is just

00:16:45,839 --> 00:16:47,040
the

00:16:47,040 --> 00:16:48,720
basically if your hash

00:16:48,720 --> 00:16:52,639
um all the transaction ids together

00:16:52,639 --> 00:16:55,199
um over and over again you'll end up

00:16:55,199 --> 00:16:57,440
with a single hash at the end and this

00:16:57,440 --> 00:16:59,120
is called the merkle root

00:16:59,120 --> 00:17:00,240
like so

00:17:00,240 --> 00:17:02,639
and basically this is like a

00:17:02,639 --> 00:17:04,959
fingerprint like a

00:17:04,959 --> 00:17:07,599
digital fingerprint that summarizes all

00:17:07,599 --> 00:17:11,199
the transactions in the block

00:17:11,199 --> 00:17:12,160
um

00:17:12,160 --> 00:17:14,319
so again you know this block header it's

00:17:14,319 --> 00:17:17,119
like a creates a unique

00:17:17,119 --> 00:17:18,720
fingerprint for all the data in the

00:17:18,720 --> 00:17:21,839
block but using a lot less data than all

00:17:21,839 --> 00:17:24,160
of the transaction data combined so

00:17:24,160 --> 00:17:26,959
maybe uh if you can

00:17:26,959 --> 00:17:28,720
you know speak a little about the

00:17:28,720 --> 00:17:30,720
miracle road because i've

00:17:30,720 --> 00:17:32,799
not really heard too much about it yeah

00:17:32,799 --> 00:17:34,160
yeah um

00:17:34,160 --> 00:17:36,400
are you like hashing like

00:17:36,400 --> 00:17:38,240
every other transaction together and

00:17:38,240 --> 00:17:39,360
then

00:17:39,360 --> 00:17:40,640
hashing

00:17:40,640 --> 00:17:42,960
that those results it looks like um i'm

00:17:42,960 --> 00:17:44,720
gonna actually cover that in the next

00:17:44,720 --> 00:17:47,440
technical part here but just for now as

00:17:47,440 --> 00:17:48,880
long as it makes sense that this merkel

00:17:48,880 --> 00:17:50,799
route provides you with like a

00:17:50,799 --> 00:17:52,720
unique short summary of all the

00:17:52,720 --> 00:17:54,720
transactions in the block

00:17:54,720 --> 00:17:56,160
okay and i'll cover how that works and

00:17:56,160 --> 00:17:57,520
why

00:17:57,520 --> 00:18:00,000
america is used in a moment but a good

00:18:00,000 --> 00:18:00,880
question

00:18:00,880 --> 00:18:02,240
anyway so

00:18:02,240 --> 00:18:04,000
there we have

00:18:04,000 --> 00:18:05,440
the block header i haven't covered all

00:18:05,440 --> 00:18:07,600
the block header data but this is the

00:18:07,600 --> 00:18:09,520
most important stuff

00:18:09,520 --> 00:18:12,400
um so there we have a block header

00:18:12,400 --> 00:18:14,880
the next step then is to put this block

00:18:14,880 --> 00:18:17,039
header data into a hash function into

00:18:17,039 --> 00:18:19,919
the sha 250 56 hash function

00:18:19,919 --> 00:18:21,919
and then that will presume

00:18:21,919 --> 00:18:23,200
produce

00:18:23,200 --> 00:18:24,240
um

00:18:24,240 --> 00:18:24,960
a

00:18:24,960 --> 00:18:27,600
random number as a result

00:18:27,600 --> 00:18:29,440
and this is called the block hash a

00:18:29,440 --> 00:18:31,919
block hash

00:18:32,000 --> 00:18:34,480
um any questions so far

00:18:34,480 --> 00:18:35,919
okay um

00:18:35,919 --> 00:18:38,559
and so okay that's all well and good but

00:18:38,559 --> 00:18:40,320
why would a minor do this

00:18:40,320 --> 00:18:42,400
um well um

00:18:42,400 --> 00:18:43,760
or how

00:18:43,760 --> 00:18:46,240
does this help to get the block mined

00:18:46,240 --> 00:18:47,600
onto the blockchain

00:18:47,600 --> 00:18:50,320
well if this block hash the result of

00:18:50,320 --> 00:18:52,320
this putting the block header into the

00:18:52,320 --> 00:18:54,960
hash function produces a block hash that

00:18:54,960 --> 00:18:58,080
is below a target value

00:18:58,080 --> 00:19:00,160
um

00:19:00,160 --> 00:19:02,320
like so so let's say this is the current

00:19:02,320 --> 00:19:03,280
target

00:19:03,280 --> 00:19:06,640
value which is a

00:19:07,200 --> 00:19:09,280
number which is like a number internal

00:19:09,280 --> 00:19:12,480
to every uh bitcoin

00:19:12,480 --> 00:19:15,120
node and they all have a they all

00:19:15,120 --> 00:19:16,480
calculate their own

00:19:16,480 --> 00:19:19,600
it's like a shared target value that is

00:19:19,600 --> 00:19:22,880
calculated in sync with every other node

00:19:22,880 --> 00:19:23,840
um

00:19:23,840 --> 00:19:25,679
if they can get

00:19:25,679 --> 00:19:28,720
their block hash to be below this then

00:19:28,720 --> 00:19:30,320
the block will get added onto the

00:19:30,320 --> 00:19:32,480
blockchain and the block is solved

00:19:32,480 --> 00:19:34,320
basically

00:19:34,320 --> 00:19:35,919
so

00:19:35,919 --> 00:19:38,480
so far with this a first attempt

00:19:38,480 --> 00:19:40,160
um this number here

00:19:40,160 --> 00:19:41,919
as you can see this target value starts

00:19:41,919 --> 00:19:43,840
with a certain number of zeros but this

00:19:43,840 --> 00:19:45,600
one is obviously a bigger number than

00:19:45,600 --> 00:19:48,160
that so it's not below the target so

00:19:48,160 --> 00:19:50,080
this first attempt at trying to add this

00:19:50,080 --> 00:19:51,039
block

00:19:51,039 --> 00:19:54,160
onto the blockchain has failed like so

00:19:54,160 --> 00:19:55,039
so

00:19:55,039 --> 00:19:57,280
um what happens then is a miner doesn't

00:19:57,280 --> 00:19:58,240
give up

00:19:58,240 --> 00:19:59,200
um

00:19:59,200 --> 00:20:00,880
in the block header

00:20:00,880 --> 00:20:02,880
there's space

00:20:02,880 --> 00:20:04,080
um

00:20:04,080 --> 00:20:06,480
there's an extra field called the nonce

00:20:06,480 --> 00:20:08,320
which stands for um

00:20:08,320 --> 00:20:11,039
a number used once

00:20:11,039 --> 00:20:12,400
um

00:20:12,400 --> 00:20:13,840
and this is like sort of like an open

00:20:13,840 --> 00:20:16,240
field that a miner is free to put their

00:20:16,240 --> 00:20:20,240
own um number in or data in so what that

00:20:20,240 --> 00:20:22,960
means is if this first attempt of the

00:20:22,960 --> 00:20:24,480
block header fails

00:20:24,480 --> 00:20:26,799
they can change the nonce value or

00:20:26,799 --> 00:20:28,559
change the data in the nonce so for

00:20:28,559 --> 00:20:31,120
example um the first attempt might they

00:20:31,120 --> 00:20:33,520
might have had the number zero in there

00:20:33,520 --> 00:20:35,600
then if that fails they'll change the

00:20:35,600 --> 00:20:37,840
nonce and then push the block header

00:20:37,840 --> 00:20:39,600
through the hash function again

00:20:39,600 --> 00:20:41,919
and because we've only made even though

00:20:41,919 --> 00:20:43,919
we've only made a small adjustment like

00:20:43,919 --> 00:20:44,880
i showed you earlier with a hash

00:20:44,880 --> 00:20:47,039
function um small adjustments can

00:20:47,039 --> 00:20:50,080
produce completely different results

00:20:50,080 --> 00:20:52,559
so a minor basically will construct a

00:20:52,559 --> 00:20:54,720
bloodhead block header and keep changing

00:20:54,720 --> 00:20:57,200
this nonce value and hoping that the

00:20:57,200 --> 00:20:58,720
result

00:20:58,720 --> 00:21:01,280
will find will produce

00:21:01,280 --> 00:21:04,159
a block hash below the target value

00:21:04,159 --> 00:21:06,880
so literally a minor creates a block

00:21:06,880 --> 00:21:08,080
header

00:21:08,080 --> 00:21:09,919
adds an answer to the end and it doesn't

00:21:09,919 --> 00:21:12,400
work they'll keep incrementing it hoping

00:21:12,400 --> 00:21:14,840
to get a low enough block

00:21:14,840 --> 00:21:17,679
hash eventually um

00:21:17,679 --> 00:21:19,200
if they're lucky just it's just this is

00:21:19,200 --> 00:21:21,600
just pure randomness and pure luck

00:21:21,600 --> 00:21:22,480
um

00:21:22,480 --> 00:21:23,520
they might

00:21:23,520 --> 00:21:25,440
um be able to

00:21:25,440 --> 00:21:27,520
guess and a nonce

00:21:27,520 --> 00:21:29,360
that works that'll produce a block hash

00:21:29,360 --> 00:21:30,400
below the target

00:21:30,400 --> 00:21:32,640
so here this particular

00:21:32,640 --> 00:21:34,640
very high nonce has produced a

00:21:34,640 --> 00:21:38,000
successful block hash result

00:21:38,000 --> 00:21:39,280
so there we are

00:21:39,280 --> 00:21:41,440
so what will happen and then is this

00:21:41,440 --> 00:21:43,120
node will add that block onto their

00:21:43,120 --> 00:21:46,000
blockchain and they will pass on this

00:21:46,000 --> 00:21:48,159
candidate block or this solved candidate

00:21:48,159 --> 00:21:49,360
block onto all the nodes they're

00:21:49,360 --> 00:21:50,640
connected to

00:21:50,640 --> 00:21:52,640
they'll check it and verify it to make

00:21:52,640 --> 00:21:54,559
sure that the block header you know

00:21:54,559 --> 00:21:55,840
produces a

00:21:55,840 --> 00:21:58,000
target below a block cash blow the

00:21:58,000 --> 00:21:59,039
target

00:21:59,039 --> 00:22:00,880
they'll add it to the file

00:22:00,880 --> 00:22:03,280
kick out any conflicting transactions um

00:22:03,280 --> 00:22:05,360
that are included in that block

00:22:05,360 --> 00:22:06,240
and then

00:22:06,240 --> 00:22:08,240
pass on the block like so and they'll do

00:22:08,240 --> 00:22:09,360
the same thing

00:22:09,360 --> 00:22:10,320
so

00:22:10,320 --> 00:22:13,679
that's how um mining works on a basic

00:22:13,679 --> 00:22:16,240
level so i had a quick question here

00:22:16,240 --> 00:22:18,720
um

00:22:18,720 --> 00:22:19,440
so

00:22:19,440 --> 00:22:22,240
you're saying that the target value

00:22:22,240 --> 00:22:24,559
is

00:22:24,840 --> 00:22:28,559
a each node has its own value for the

00:22:28,559 --> 00:22:30,480
target value right so

00:22:30,480 --> 00:22:32,400
i've thought of this but there is a

00:22:32,400 --> 00:22:35,039
possibility that i mine a block which is

00:22:35,039 --> 00:22:37,200
below my target value

00:22:37,200 --> 00:22:37,919
but

00:22:37,919 --> 00:22:40,080
and i give it to my neighboring nodes

00:22:40,080 --> 00:22:40,960
and

00:22:40,960 --> 00:22:44,400
maybe the target value has changed or

00:22:44,400 --> 00:22:46,799
for some reason the other nodes don't

00:22:46,799 --> 00:22:49,039
have the same target value

00:22:49,039 --> 00:22:51,600
uh is that is that a possibility and how

00:22:51,600 --> 00:22:52,559
does that

00:22:52,559 --> 00:22:53,760
yeah well i understand the question i

00:22:53,760 --> 00:22:55,600
think i am i think i explained the

00:22:55,600 --> 00:22:57,600
target um not

00:22:57,600 --> 00:22:59,360
great um

00:22:59,360 --> 00:23:02,159
let me find out if i

00:23:02,159 --> 00:23:03,520
uh

00:23:03,520 --> 00:23:06,880
the target um

00:23:06,880 --> 00:23:09,760
right um

00:23:09,760 --> 00:23:11,919
the target um i'll explain it now

00:23:11,919 --> 00:23:13,840
basically the target is there

00:23:13,840 --> 00:23:15,039
um

00:23:15,039 --> 00:23:17,440
so that

00:23:17,520 --> 00:23:19,760
um every 10 minutes

00:23:19,760 --> 00:23:23,360
um a new block will be mined

00:23:23,360 --> 00:23:24,320
but

00:23:24,320 --> 00:23:25,280
if

00:23:25,280 --> 00:23:26,559
uh

00:23:26,559 --> 00:23:29,600
more computers are hashing a lot faster

00:23:29,600 --> 00:23:32,880
um then a block is likely to be mined in

00:23:32,880 --> 00:23:34,240
under 10 minutes

00:23:34,240 --> 00:23:36,159
so this target value obviously moves up

00:23:36,159 --> 00:23:37,760
and down

00:23:37,760 --> 00:23:38,559
um

00:23:38,559 --> 00:23:40,720
so that a new block is mined every 10

00:23:40,720 --> 00:23:42,400
minutes

00:23:42,400 --> 00:23:44,480
um yeah

00:23:44,480 --> 00:23:46,400
yeah so um so

00:23:46,400 --> 00:23:48,080
the target for the very first block when

00:23:48,080 --> 00:23:49,679
you first start running bitcoin and the

00:23:49,679 --> 00:23:51,600
very first block it was hard coded in at

00:23:51,600 --> 00:23:53,919
this value

00:23:53,919 --> 00:23:57,039
and then after every uh 2016 blocks or

00:23:57,039 --> 00:23:59,200
roughly every two weeks

00:23:59,200 --> 00:24:02,000
what will happen is your every

00:24:02,000 --> 00:24:02,880
node

00:24:02,880 --> 00:24:06,159
they will look at the time it took um

00:24:06,159 --> 00:24:09,120
for all the last 2016 blocks to be mined

00:24:09,120 --> 00:24:11,200
so the expected time for that is

00:24:11,200 --> 00:24:12,559
obviously

00:24:12,559 --> 00:24:14,559
20 160

00:24:14,559 --> 00:24:16,559
but if the actual time for those blocks

00:24:16,559 --> 00:24:18,880
demand was less than that

00:24:18,880 --> 00:24:21,120
then the target would adjust

00:24:21,120 --> 00:24:25,200
so the target will adjust by this ratio

00:24:25,200 --> 00:24:26,000
so

00:24:26,000 --> 00:24:27,840
there we are so

00:24:27,840 --> 00:24:29,679
this ratio because it was mined all the

00:24:29,679 --> 00:24:32,960
blocks of mine faster is 0.9

00:24:32,960 --> 00:24:34,880
and so this target as you can see will

00:24:34,880 --> 00:24:36,720
adjust downwards

00:24:36,720 --> 00:24:38,880
so every single node when they receive a

00:24:38,880 --> 00:24:41,279
new block after every 2016 blocks they

00:24:41,279 --> 00:24:44,640
will all do this exact same calculation

00:24:44,640 --> 00:24:45,360
so

00:24:45,360 --> 00:24:47,520
every node started with this value but

00:24:47,520 --> 00:24:49,520
if everyone's on the same block

00:24:49,520 --> 00:24:52,480
then everyone will have calculated the

00:24:52,480 --> 00:24:53,840
same target

00:24:53,840 --> 00:24:55,279
so it's basically everyone shares the

00:24:55,279 --> 00:24:56,720
same target they all calculate it

00:24:56,720 --> 00:24:59,840
themselves but

00:24:59,840 --> 00:25:01,039
because they're receiving all the same

00:25:01,039 --> 00:25:02,000
blocks

00:25:02,000 --> 00:25:04,159
um they'll calculate everyone will have

00:25:04,159 --> 00:25:05,919
the same target value so not everyone

00:25:05,919 --> 00:25:07,520
has different target values everyone has

00:25:07,520 --> 00:25:10,799
the same calculated target

00:25:10,799 --> 00:25:13,360
so again this happens every 2016 blocks

00:25:13,360 --> 00:25:14,880
the same thing happens how long did they

00:25:14,880 --> 00:25:18,240
take what's the ratio okay that was

00:25:18,240 --> 00:25:19,440
mine faster

00:25:19,440 --> 00:25:22,720
move it down again like so

00:25:23,360 --> 00:25:24,240
okay

00:25:24,240 --> 00:25:26,559
um

00:25:26,960 --> 00:25:29,120
so that's how the target works

00:25:29,120 --> 00:25:29,900
um

00:25:29,900 --> 00:25:31,279
[Music]

00:25:31,279 --> 00:25:36,159
also up until now and just to clarify um

00:25:36,159 --> 00:25:37,440
i've referred to this blockchain as a

00:25:37,440 --> 00:25:39,520
shared file um the shared file is a

00:25:39,520 --> 00:25:41,919
blockchain um basically the shared file

00:25:41,919 --> 00:25:45,440
is full of transactions but um because

00:25:45,440 --> 00:25:48,559
um the transactions are added in blocks

00:25:48,559 --> 00:25:50,240
like so um the file is called the

00:25:50,240 --> 00:25:52,480
blockchain because each block builds on

00:25:52,480 --> 00:25:54,559
top of each other so with bitcoin it is

00:25:54,559 --> 00:25:56,240
a shared file and this shared file is

00:25:56,240 --> 00:25:57,919
called the blockchain

00:25:57,919 --> 00:26:00,320
so if i just update the diagram you can

00:26:00,320 --> 00:26:01,760
think of the shared file as you know

00:26:01,760 --> 00:26:04,720
just blocks built on top of each other

00:26:04,720 --> 00:26:06,000
finally

00:26:06,000 --> 00:26:07,520
why would anyone mine what's the

00:26:07,520 --> 00:26:09,679
incentive for a miner to

00:26:09,679 --> 00:26:11,279
use all this hashing power on their

00:26:11,279 --> 00:26:13,200
computer to try and

00:26:13,200 --> 00:26:14,240
um

00:26:14,240 --> 00:26:15,679
mine the transactions from the memory

00:26:15,679 --> 00:26:17,600
pool onto the blockchain

00:26:17,600 --> 00:26:20,799
well every time a miner

00:26:20,799 --> 00:26:22,960
mines a block it was successful

00:26:22,960 --> 00:26:25,520
to my in mind in a block and they will

00:26:25,520 --> 00:26:27,919
receive what's called a block reward

00:26:27,919 --> 00:26:30,159
um it started out at 50

00:26:30,159 --> 00:26:34,559
but it halves roughly every four years

00:26:34,799 --> 00:26:37,600
so that's the incentive to minor block

00:26:37,600 --> 00:26:39,520
and the way a miner receives this block

00:26:39,520 --> 00:26:40,640
reward

00:26:40,640 --> 00:26:42,880
um

00:26:42,880 --> 00:26:45,120
when they construct the candidate block

00:26:45,120 --> 00:26:47,279
um the very first transaction

00:26:47,279 --> 00:26:49,440
is reserved um

00:26:49,440 --> 00:26:53,600
for them to put there so a known a miner

00:26:53,600 --> 00:26:55,600
will put their own

00:26:55,600 --> 00:26:57,039
transaction at the top

00:26:57,039 --> 00:26:59,360
called a coinbase transaction

00:26:59,360 --> 00:27:01,440
and this is a special transaction

00:27:01,440 --> 00:27:03,679
because it allows them to

00:27:03,679 --> 00:27:05,440
send themselves or

00:27:05,440 --> 00:27:07,440
send themselves a set amount of bitcoins

00:27:07,440 --> 00:27:11,200
that had not previously existed

00:27:11,200 --> 00:27:12,240
um

00:27:12,240 --> 00:27:13,039
so

00:27:13,039 --> 00:27:14,480
if this block does get mined onto the

00:27:14,480 --> 00:27:16,320
blockchain

00:27:16,320 --> 00:27:18,400
they will be able to receive new

00:27:18,400 --> 00:27:19,600
bitcoins

00:27:19,600 --> 00:27:21,440
thanks to this coinbase transaction that

00:27:21,440 --> 00:27:23,200
they put there they put their sort of

00:27:23,200 --> 00:27:25,360
bitcoin address in here so that they can

00:27:25,360 --> 00:27:26,559
receive the

00:27:26,559 --> 00:27:28,960
the block reward

00:27:28,960 --> 00:27:30,640
so just to summarize the basics of

00:27:30,640 --> 00:27:32,720
mining um a miner will get the

00:27:32,720 --> 00:27:34,480
transactions from the memory pool

00:27:34,480 --> 00:27:36,000
then they'll put their coinbase

00:27:36,000 --> 00:27:37,200
transaction at the top so they can

00:27:37,200 --> 00:27:38,400
receive a block award if they're

00:27:38,400 --> 00:27:40,080
successful in mining this this block

00:27:40,080 --> 00:27:41,600
onto the blockchain

00:27:41,600 --> 00:27:43,760
then they'll create a block header

00:27:43,760 --> 00:27:45,679
then they'll hash it

00:27:45,679 --> 00:27:48,000
hope that it's below the target value if

00:27:48,000 --> 00:27:49,679
it's not they'll keep adjusting the

00:27:49,679 --> 00:27:52,000
nonce over and over again

00:27:52,000 --> 00:27:54,480
until and if they're lucky um they'll

00:27:54,480 --> 00:27:56,480
find a nonce before anyone else that

00:27:56,480 --> 00:27:58,159
produces a block hash that's below the

00:27:58,159 --> 00:27:59,200
target

00:27:59,200 --> 00:28:01,440
and then they outline the block

00:28:01,440 --> 00:28:03,840
like so

00:28:04,080 --> 00:28:06,320
uh does that make sense

00:28:06,320 --> 00:28:08,159
okay um

00:28:08,159 --> 00:28:09,919
i think what i'll do now i'll just show

00:28:09,919 --> 00:28:11,600
you um

00:28:11,600 --> 00:28:16,240
a little mining simulator um

00:28:16,240 --> 00:28:19,120
yeah a little mining simulator

00:28:19,120 --> 00:28:20,799
um

00:28:20,799 --> 00:28:22,960
so this is what um

00:28:22,960 --> 00:28:25,760
a bitcoin might bitcoin miner might look

00:28:25,760 --> 00:28:27,279
like if you like under the hood

00:28:27,279 --> 00:28:28,559
basically

00:28:28,559 --> 00:28:30,399
so what they'll do um they'll go into

00:28:30,399 --> 00:28:31,600
their memory pool

00:28:31,600 --> 00:28:32,960
they'll get the transactions from their

00:28:32,960 --> 00:28:34,080
memory pool

00:28:34,080 --> 00:28:34,880
um

00:28:34,880 --> 00:28:37,200
this mining simulator simulator is mined

00:28:37,200 --> 00:28:40,000
in a block that's already been mined um

00:28:40,000 --> 00:28:41,679
so this is a long time ago there's only

00:28:41,679 --> 00:28:43,279
13 transactions in the memory pool

00:28:43,279 --> 00:28:44,559
there's obviously a lot more in there

00:28:44,559 --> 00:28:45,440
now

00:28:45,440 --> 00:28:46,720
uh what they'll do then they'll

00:28:46,720 --> 00:28:48,240
construct the block header

00:28:48,240 --> 00:28:50,559
um i haven't covered these last

00:28:50,559 --> 00:28:52,399
two bits of the block header yet but

00:28:52,399 --> 00:28:53,679
don't worry i'll cover them in a moment

00:28:53,679 --> 00:28:54,640
moment

00:28:54,640 --> 00:28:56,399
but obviously this all this data refers

00:28:56,399 --> 00:28:57,919
to the previous block has the miracle

00:28:57,919 --> 00:28:59,840
root the version number

00:28:59,840 --> 00:29:00,640
um

00:29:00,640 --> 00:29:03,440
and what they'll do they will squish all

00:29:03,440 --> 00:29:04,399
of that

00:29:04,399 --> 00:29:06,720
data together into one line of data and

00:29:06,720 --> 00:29:08,480
i've left some space here for the nonce

00:29:08,480 --> 00:29:11,520
so this is a block header data

00:29:11,520 --> 00:29:13,840
this is the target and then what miner

00:29:13,840 --> 00:29:16,320
will do now is they will take this block

00:29:16,320 --> 00:29:18,080
header

00:29:18,080 --> 00:29:19,760
and put a nonce in there keep

00:29:19,760 --> 00:29:22,640
incrementing it and these are

00:29:22,640 --> 00:29:24,399
the results as you can see now this is a

00:29:24,399 --> 00:29:26,240
very slow minor so as you can see these

00:29:26,240 --> 00:29:28,399
are the nonce values on the left and

00:29:28,399 --> 00:29:30,720
this these are the different hash values

00:29:30,720 --> 00:29:32,320
that that

00:29:32,320 --> 00:29:33,919
block header is producing okay so this

00:29:33,919 --> 00:29:35,760
is uh so

00:29:35,760 --> 00:29:37,679
when you created that

00:29:37,679 --> 00:29:39,120
string

00:29:39,120 --> 00:29:42,080
uh on top that did not include the

00:29:42,080 --> 00:29:45,440
transactions it included only the header

00:29:45,440 --> 00:29:46,159
yes

00:29:46,159 --> 00:29:49,760
oh okay okay okay yes also so um

00:29:49,760 --> 00:29:50,480
what

00:29:50,480 --> 00:29:51,279
um

00:29:51,279 --> 00:29:53,200
the transactions i suppose are included

00:29:53,200 --> 00:29:55,600
in this merkel route this merker yeah

00:29:55,600 --> 00:29:57,200
this mercury route is the summary of all

00:29:57,200 --> 00:29:58,720
the transact this sort of refers to all

00:29:58,720 --> 00:30:01,279
the transactions in the block

00:30:01,279 --> 00:30:03,039
um

00:30:03,039 --> 00:30:05,760
here also i've here's the code for this

00:30:05,760 --> 00:30:08,480
miner it just basically just mines a

00:30:08,480 --> 00:30:10,000
um

00:30:10,000 --> 00:30:11,600
block header

00:30:11,600 --> 00:30:13,600
it just hashes a block header um i've

00:30:13,600 --> 00:30:15,200
made this code available on the website

00:30:15,200 --> 00:30:17,200
i'll give you a link to in a moment

00:30:17,200 --> 00:30:20,000
um but for this particular miner i know

00:30:20,000 --> 00:30:21,440
um

00:30:21,440 --> 00:30:24,799
what the successful hashtag

00:30:25,600 --> 00:30:29,200
hey there let's grab this

00:30:29,520 --> 00:30:31,360
there we are so

00:30:31,360 --> 00:30:34,000
let's reduce this down by 100.

00:30:34,000 --> 00:30:37,200
so if i start this again

00:30:37,200 --> 00:30:39,840
um i've increased the starting nonce

00:30:39,840 --> 00:30:41,520
value

00:30:41,520 --> 00:30:43,840
so again this is the block header

00:30:43,840 --> 00:30:45,200
the nonce is going to start not from

00:30:45,200 --> 00:30:47,360
zero this time but a much higher number

00:30:47,360 --> 00:30:49,679
and if i let it run now um hopefully

00:30:49,679 --> 00:30:53,919
after about 100 it'll stop when it finds

00:30:53,919 --> 00:30:57,760
a block hash below the target value

00:30:57,919 --> 00:31:01,200
there we are don't if you see this

00:31:01,200 --> 00:31:02,880
so there we are and the block has been

00:31:02,880 --> 00:31:04,480
mined so

00:31:04,480 --> 00:31:06,559
this particular blush block hash purely

00:31:06,559 --> 00:31:08,000
random

00:31:08,000 --> 00:31:10,720
and just pure luck produced a block hash

00:31:10,720 --> 00:31:12,320
starting with this many zeros and that

00:31:12,320 --> 00:31:14,240
was below the target and so that's what

00:31:14,240 --> 00:31:16,080
the miner does is they just

00:31:16,080 --> 00:31:18,640
grab a block header change the nonce

00:31:18,640 --> 00:31:21,360
hash as fast they can

00:31:21,360 --> 00:31:23,279
does that make sense

00:31:23,279 --> 00:31:24,880
okay um if

00:31:24,880 --> 00:31:26,559
i'll kev i'll add i'll put these links

00:31:26,559 --> 00:31:28,640
at the end um

00:31:28,640 --> 00:31:29,440
but

00:31:29,440 --> 00:31:30,799
if you go on the website on to

00:31:30,799 --> 00:31:32,720
learnmebitcoin.com

00:31:32,720 --> 00:31:35,520
forward slash code and i've put the

00:31:35,520 --> 00:31:37,519
mining simulator

00:31:37,519 --> 00:31:39,440
code up here

00:31:39,440 --> 00:31:40,320
it's

00:31:40,320 --> 00:31:43,039
i've made it it's written in ruby

00:31:43,039 --> 00:31:44,799
just because i think it's a simple and

00:31:44,799 --> 00:31:47,440
easy to read language similar to python

00:31:47,440 --> 00:31:49,200
um i tried to make this as simple as

00:31:49,200 --> 00:31:51,120
possible so if you want to start you

00:31:51,120 --> 00:31:53,120
know hashing your own block headers

00:31:53,120 --> 00:31:55,039
um you can

00:31:55,039 --> 00:31:57,360
so on the website as well on limia

00:31:57,360 --> 00:32:00,080
bitcoin if you go into the browser

00:32:00,080 --> 00:32:02,000
and you'll be able to see

00:32:02,000 --> 00:32:04,480
these these latest blocks

00:32:04,480 --> 00:32:07,200
and these are the block headers

00:32:07,200 --> 00:32:10,640
and if you click on serialized

00:32:10,880 --> 00:32:13,120
it'll show you the

00:32:13,120 --> 00:32:14,399
civilized code

00:32:14,399 --> 00:32:16,399
and if you were to hash this

00:32:16,399 --> 00:32:19,919
um it would produce this block header

00:32:19,919 --> 00:32:21,919
and so this is a

00:32:21,919 --> 00:32:23,679
this is a candidate block basically i'm

00:32:23,679 --> 00:32:25,279
just you know trying to do the same

00:32:25,279 --> 00:32:26,559
thing

00:32:26,559 --> 00:32:30,159
right so just curious i mean this uh is

00:32:30,159 --> 00:32:32,720
this running off like a

00:32:32,720 --> 00:32:33,840
machine

00:32:33,840 --> 00:32:35,679
that you have i mean learn me a bit is

00:32:35,679 --> 00:32:38,159
this live yeah this is live

00:32:38,159 --> 00:32:39,919
yeah so this is um

00:32:39,919 --> 00:32:41,840
a live candidate block these are all

00:32:41,840 --> 00:32:43,519
live transactions

00:32:43,519 --> 00:32:45,760
uh

00:32:46,000 --> 00:32:49,200
so it's all on the browser

00:32:49,760 --> 00:32:51,120
let me go back

00:32:51,120 --> 00:32:54,080
all right okay um

00:32:54,559 --> 00:32:57,679
uh okay so that's the basics

00:32:57,679 --> 00:32:58,480
oh

00:32:58,480 --> 00:33:01,200
intro right so that was the basics

00:33:01,200 --> 00:33:04,559
of um now i'll go on to the technical

00:33:04,559 --> 00:33:06,159
um basically i'm gonna run through the

00:33:06,159 --> 00:33:08,799
exact same thing but uh do it in a

00:33:08,799 --> 00:33:10,559
technical way

00:33:10,559 --> 00:33:13,679
so if you're interested in programming

00:33:13,679 --> 00:33:16,720
um and actually mining the block uh this

00:33:16,720 --> 00:33:19,039
is basically the same stuff just from a

00:33:19,039 --> 00:33:21,120
programmer's perspective

00:33:21,120 --> 00:33:23,120
right so so again

00:33:23,120 --> 00:33:25,039
just repetition gonna repeat the same

00:33:25,039 --> 00:33:27,200
stuff uh

00:33:27,200 --> 00:33:29,039
same thing memory pool

00:33:29,039 --> 00:33:30,240
grab the transact uh grab the

00:33:30,240 --> 00:33:31,840
transactions to main pool fill up your

00:33:31,840 --> 00:33:34,000
block uh then you'll

00:33:34,000 --> 00:33:36,159
there we are this is the candidate block

00:33:36,159 --> 00:33:38,159
then you put your coinbase transaction

00:33:38,159 --> 00:33:40,320
at the top the first transaction in a

00:33:40,320 --> 00:33:41,840
block is always a coinbase transaction

00:33:41,840 --> 00:33:43,840
that a miner was put there

00:33:43,840 --> 00:33:45,120
um

00:33:45,120 --> 00:33:46,960
and so that allows you to claim the

00:33:46,960 --> 00:33:48,960
block reward which is currently 12.5

00:33:48,960 --> 00:33:50,159
bitcoins

00:33:50,159 --> 00:33:51,600
and the reason you would put the

00:33:51,600 --> 00:33:53,919
coinbase transaction um at the top of

00:33:53,919 --> 00:33:56,080
the block after selecting all these

00:33:56,080 --> 00:33:57,360
transactions

00:33:57,360 --> 00:33:58,960
is because each of these transactions

00:33:58,960 --> 00:34:00,720
will have a fee

00:34:00,720 --> 00:34:02,559
and uh

00:34:02,559 --> 00:34:04,799
through your coinbase transaction

00:34:04,799 --> 00:34:07,760
you can collect all of these fees

00:34:07,760 --> 00:34:10,079
um so instead of the coinbase

00:34:10,079 --> 00:34:12,560
transaction just receiving the 12.5

00:34:12,560 --> 00:34:14,239
block reward you'll be able to send

00:34:14,239 --> 00:34:17,040
yourself something like 13 or more maybe

00:34:17,040 --> 00:34:19,040
depending on how much the fees are worth

00:34:19,040 --> 00:34:20,239
uh depends how much you can send

00:34:20,239 --> 00:34:22,000
yourself in this coinbase transaction

00:34:22,000 --> 00:34:23,520
okay so the coinbase transaction

00:34:23,520 --> 00:34:25,280
includes the fees yes

00:34:25,280 --> 00:34:27,599
yes it's not only the the

00:34:27,599 --> 00:34:29,599
mining reward okay so basically you have

00:34:29,599 --> 00:34:31,520
the base level which is the block reward

00:34:31,520 --> 00:34:33,760
but then you can send yourself however

00:34:33,760 --> 00:34:35,359
much all these fees

00:34:35,359 --> 00:34:38,239
from each transaction

00:34:38,239 --> 00:34:40,560
so this means that miners will tend to

00:34:40,560 --> 00:34:41,760
pick uh

00:34:41,760 --> 00:34:42,800
uh

00:34:42,800 --> 00:34:47,040
transactions with a higher exactly yes

00:34:47,040 --> 00:34:48,639
uh so there we are we've got the

00:34:48,639 --> 00:34:50,800
transfer one more question on that uh

00:34:50,800 --> 00:34:53,040
yeah so i i remember seeing a graph

00:34:53,040 --> 00:34:54,879
where uh

00:34:54,879 --> 00:34:57,760
you know it showed me like uh

00:34:57,760 --> 00:34:59,839
on the left the fees and on the right

00:34:59,839 --> 00:35:02,079
like kind of how much time it will take

00:35:02,079 --> 00:35:05,760
to mine that block yeah so uh

00:35:05,760 --> 00:35:08,160
uh does this mean that

00:35:08,160 --> 00:35:09,119
you know

00:35:09,119 --> 00:35:12,000
if we put a very very low fee is it ever

00:35:12,000 --> 00:35:14,400
possible that our transaction will never

00:35:14,400 --> 00:35:16,880
get uh

00:35:16,880 --> 00:35:19,040
never be part of a block is that ever

00:35:19,040 --> 00:35:21,280
possible in your experience or what can

00:35:21,280 --> 00:35:23,359
happen is so say you make a transaction

00:35:23,359 --> 00:35:26,079
it'll go into the memory pool first um

00:35:26,079 --> 00:35:27,359
if there's a lot of transactions in the

00:35:27,359 --> 00:35:28,640
memory pool

00:35:28,640 --> 00:35:30,640
um then you basically basically your

00:35:30,640 --> 00:35:32,560
transaction is competing with all these

00:35:32,560 --> 00:35:35,200
other transactions for space in a block

00:35:35,200 --> 00:35:36,640
because a block

00:35:36,640 --> 00:35:38,720
it's the way a block is

00:35:38,720 --> 00:35:40,720
it used to be one megabytes worth of

00:35:40,720 --> 00:35:43,839
transactions um it's roughly about 1.7

00:35:43,839 --> 00:35:44,880
now

00:35:44,880 --> 00:35:46,640
it uses a different metric called weight

00:35:46,640 --> 00:35:48,320
but don't i'm not going to cover that

00:35:48,320 --> 00:35:50,160
just now but um

00:35:50,160 --> 00:35:51,760
what will happen is say you put such a

00:35:51,760 --> 00:35:53,040
low fee on there

00:35:53,040 --> 00:35:54,960
that um it doesn't make it into the

00:35:54,960 --> 00:35:56,560
blocks are still hanging around in the

00:35:56,560 --> 00:35:58,800
memory pool um

00:35:58,800 --> 00:36:00,640
if your transaction stays in the memory

00:36:00,640 --> 00:36:03,440
pool memory pool for longer than 72

00:36:03,440 --> 00:36:05,520
hours

00:36:05,520 --> 00:36:07,200
on average um

00:36:07,200 --> 00:36:08,160
your

00:36:08,160 --> 00:36:09,359
transaction will just get kicked out the

00:36:09,359 --> 00:36:10,640
memory pool

00:36:10,640 --> 00:36:11,440
so

00:36:11,440 --> 00:36:13,440
you if you put a very low transaction a

00:36:13,440 --> 00:36:15,440
fee on a transaction there's a chance

00:36:15,440 --> 00:36:18,000
that it will never make it um one into a

00:36:18,000 --> 00:36:20,640
into a candidate block or even it or

00:36:20,640 --> 00:36:22,320
onto the blockchain right

00:36:22,320 --> 00:36:24,320
so again in your experience what's like

00:36:24,320 --> 00:36:26,480
the like the bare minimum let's say if i

00:36:26,480 --> 00:36:28,320
want to send like five bucks to someone

00:36:28,320 --> 00:36:29,839
you know or buy a coffee like three

00:36:29,839 --> 00:36:30,720
bucks

00:36:30,720 --> 00:36:33,920
uh what's what's the minimum

00:36:33,920 --> 00:36:35,839
fee that i have to pay i mean

00:36:35,839 --> 00:36:40,560
um i think wallets generally um

00:36:40,560 --> 00:36:41,680
tend to

00:36:41,680 --> 00:36:42,960
um

00:36:42,960 --> 00:36:44,240
help you out with that but i don't think

00:36:44,240 --> 00:36:46,320
they created it but

00:36:46,320 --> 00:36:48,480
um

00:36:48,480 --> 00:36:49,839
one way

00:36:49,839 --> 00:36:52,079
what i would do is i would look at a cat

00:36:52,079 --> 00:36:54,960
this candidate block and

00:36:54,960 --> 00:36:56,960
transactions in general are ordered in a

00:36:56,960 --> 00:36:58,640
candidate block from highest to lowest

00:36:58,640 --> 00:37:01,359
fees not strictly but i would head

00:37:01,359 --> 00:37:02,560
towards the bottom of this candidate

00:37:02,560 --> 00:37:04,960
block and have a look at each of the fee

00:37:04,960 --> 00:37:07,040
the fees on them and

00:37:07,040 --> 00:37:08,560
um

00:37:08,560 --> 00:37:09,920
uh

00:37:09,920 --> 00:37:12,400
you can just basically add a fee that's

00:37:12,400 --> 00:37:15,119
greater than the lowest fees yeah

00:37:15,119 --> 00:37:16,960
exactly that's a

00:37:16,960 --> 00:37:18,880
rough i mean that's like the simplest

00:37:18,880 --> 00:37:22,000
way to do it in my opinion um

00:37:22,000 --> 00:37:23,040
so

00:37:23,040 --> 00:37:25,599
yeah yeah so again this is per byte i

00:37:25,599 --> 00:37:28,480
think when you hovered over uh yeah so

00:37:28,480 --> 00:37:32,400
fee per byte so this is uh

00:37:32,400 --> 00:37:34,320
so the average

00:37:34,320 --> 00:37:37,119
byte size of a transaction is that what

00:37:37,119 --> 00:37:39,200
this is yeah so

00:37:39,200 --> 00:37:40,000
um

00:37:40,000 --> 00:37:42,720
so this this is a transaction

00:37:42,720 --> 00:37:44,000
and um this

00:37:44,000 --> 00:37:47,359
yeah this takes up um space in a block

00:37:47,359 --> 00:37:50,560
so um then you set a fee on it but

00:37:50,560 --> 00:37:51,839
you're basically paying for each

00:37:51,839 --> 00:37:53,839
individual bytes so that the the bigger

00:37:53,839 --> 00:37:54,960
the um

00:37:54,960 --> 00:37:57,520
the transaction is in data wise uh the

00:37:57,520 --> 00:37:59,200
more of a higher fee you want to put on

00:37:59,200 --> 00:38:01,119
it to give you because

00:38:01,119 --> 00:38:02,880
a miner but they will

00:38:02,880 --> 00:38:05,839
select transactions um based on fee per

00:38:05,839 --> 00:38:07,520
byte so basically which transactions are

00:38:07,520 --> 00:38:09,440
giving them the most fee for the space

00:38:09,440 --> 00:38:10,720
they're going to take up in the

00:38:10,720 --> 00:38:12,480
candidate block

00:38:12,480 --> 00:38:13,599
okay

00:38:13,599 --> 00:38:15,119
um

00:38:15,119 --> 00:38:16,720
so again just going to went through

00:38:16,720 --> 00:38:17,920
mining again put your coinbase

00:38:17,920 --> 00:38:19,839
transaction at the top

00:38:19,839 --> 00:38:21,359
and then you can check the block header

00:38:21,359 --> 00:38:23,680
same again you have a version number

00:38:23,680 --> 00:38:24,560
um

00:38:24,560 --> 00:38:26,480
this was like this null block and the

00:38:26,480 --> 00:38:29,440
version of was one uh the way versions

00:38:29,440 --> 00:38:32,160
numbers has cha the way version numbers

00:38:32,160 --> 00:38:34,160
uh work now is different to how it used

00:38:34,160 --> 00:38:36,960
to be they can be used for um voting um

00:38:36,960 --> 00:38:38,079
i'm not going to cover that just now

00:38:38,079 --> 00:38:40,640
it's going to run through um

00:38:40,640 --> 00:38:42,400
simple block header then you have the

00:38:42,400 --> 00:38:44,160
previous block name again just refer to

00:38:44,160 --> 00:38:45,200
the block you're going to build on top

00:38:45,200 --> 00:38:47,119
of build on top of which is basically

00:38:47,119 --> 00:38:49,599
the tip of the blockchain

00:38:49,599 --> 00:38:51,599
uh then you have the merkle root

00:38:51,599 --> 00:38:54,079
so the way that works is um you have all

00:38:54,079 --> 00:38:55,920
the transactions uh

00:38:55,920 --> 00:38:57,119
in the block

00:38:57,119 --> 00:38:58,560
i'm just moving these to the side just

00:38:58,560 --> 00:39:00,480
for illustration purposes

00:39:00,480 --> 00:39:02,320
and what you do you just run through

00:39:02,320 --> 00:39:04,240
every single pair of transactions and

00:39:04,240 --> 00:39:05,839
you hash them together

00:39:05,839 --> 00:39:08,720
so remember the hash function and you

00:39:08,720 --> 00:39:10,560
basically line these up

00:39:10,560 --> 00:39:12,240
so one and two just line them up

00:39:12,240 --> 00:39:14,079
together and hash them together and

00:39:14,079 --> 00:39:15,760
they'll produce a

00:39:15,760 --> 00:39:17,920
digest or hash result

00:39:17,920 --> 00:39:19,359
and they do that for every single pair

00:39:19,359 --> 00:39:21,200
of transactions

00:39:21,200 --> 00:39:22,240
in the block

00:39:22,240 --> 00:39:24,960
um if you end up with a transaction on

00:39:24,960 --> 00:39:26,720
his own that doesn't have a pair all you

00:39:26,720 --> 00:39:29,440
do is you just hash it with itself

00:39:29,440 --> 00:39:31,680
and then that's the first round done you

00:39:31,680 --> 00:39:33,599
have these four hashes from all these

00:39:33,599 --> 00:39:34,800
pairs

00:39:34,800 --> 00:39:36,560
then you just run through again

00:39:36,560 --> 00:39:38,320
hash them all together hash each pair

00:39:38,320 --> 00:39:40,400
together and you keep going on and

00:39:40,400 --> 00:39:43,680
you'll end up with a single um

00:39:43,680 --> 00:39:44,880
hash result

00:39:44,880 --> 00:39:46,960
called the merkle root

00:39:46,960 --> 00:39:47,760
now

00:39:47,760 --> 00:39:49,839
the question is um

00:39:49,839 --> 00:39:51,119
why

00:39:51,119 --> 00:39:53,599
if you want to create a summary of all

00:39:53,599 --> 00:39:56,480
the transactions in the block you're

00:39:56,480 --> 00:39:57,839
hashing the transaction ids here

00:39:57,839 --> 00:40:00,160
together by the way but um

00:40:00,160 --> 00:40:01,359
if you want to create a summary or a

00:40:01,359 --> 00:40:02,720
fingerprint for all the transactions in

00:40:02,720 --> 00:40:04,560
the block why wouldn't you just hash

00:40:04,560 --> 00:40:06,320
them all together like this in a more

00:40:06,320 --> 00:40:07,760
simple way why would you do it in this

00:40:07,760 --> 00:40:09,280
more elaborate

00:40:09,280 --> 00:40:11,599
um tree structure

00:40:11,599 --> 00:40:13,520
and the reason for that is

00:40:13,520 --> 00:40:16,720
um say you you were given a merkle root

00:40:16,720 --> 00:40:17,839
um

00:40:17,839 --> 00:40:21,359
a merkel root and you want to check if

00:40:21,359 --> 00:40:23,599
this transaction id

00:40:23,599 --> 00:40:26,480
is present in this block

00:40:26,480 --> 00:40:29,359
um the only way you could check it

00:40:29,359 --> 00:40:30,800
would be to take

00:40:30,800 --> 00:40:32,400
all of the other

00:40:32,400 --> 00:40:34,160
transaction ids you need all the other

00:40:34,160 --> 00:40:36,079
ones including the one you want to check

00:40:36,079 --> 00:40:38,720
and then hash them together to get the

00:40:38,720 --> 00:40:40,400
miracle root

00:40:40,400 --> 00:40:41,680
um

00:40:41,680 --> 00:40:44,000
to get the to get the hash sorry

00:40:44,000 --> 00:40:44,800
um

00:40:44,800 --> 00:40:45,920
but

00:40:45,920 --> 00:40:47,760
with a miracle root um so you want to

00:40:47,760 --> 00:40:50,000
check the presence of this hash here all

00:40:50,000 --> 00:40:52,320
you actually need is you need this one

00:40:52,320 --> 00:40:54,000
to create this one

00:40:54,000 --> 00:40:55,760
and then if you've got that one and then

00:40:55,760 --> 00:40:57,599
all you need is that one

00:40:57,599 --> 00:40:59,280
and then you can create that one

00:40:59,280 --> 00:41:01,440
and then only then is this one up here

00:41:01,440 --> 00:41:03,920
and that will give you this miracle root

00:41:03,920 --> 00:41:06,480
so the other one needed was it one two

00:41:06,480 --> 00:41:10,240
three four five seven six um

00:41:10,240 --> 00:41:12,720
transaction ids but this one only needed

00:41:12,720 --> 00:41:13,920
uh three

00:41:13,920 --> 00:41:14,960
so obviously it doesn't look like a

00:41:14,960 --> 00:41:16,319
massive improvement but this is just a

00:41:16,319 --> 00:41:18,880
simple block that if this is a lot

00:41:18,880 --> 00:41:20,560
longer block with

00:41:20,560 --> 00:41:22,240
thousands of transactions

00:41:22,240 --> 00:41:23,520
then

00:41:23,520 --> 00:41:25,040
you're needing a lot less transaction

00:41:25,040 --> 00:41:26,480
ids to

00:41:26,480 --> 00:41:28,079
check the presence of a single

00:41:28,079 --> 00:41:30,079
transaction

00:41:30,079 --> 00:41:32,079
i've not done this myself but

00:41:32,079 --> 00:41:34,160
apparently this is useful and efficient

00:41:34,160 --> 00:41:35,599
to um

00:41:35,599 --> 00:41:37,280
do it this way so that's why we have

00:41:37,280 --> 00:41:38,640
this tree structure for hashing because

00:41:38,640 --> 00:41:41,520
it saves on checking for the presence of

00:41:41,520 --> 00:41:43,839
transactions in our block yeah just one

00:41:43,839 --> 00:41:46,400
question when you say that we we hash

00:41:46,400 --> 00:41:48,880
like two transactions you're saying that

00:41:48,880 --> 00:41:51,520
we just concatenate them and hash do a

00:41:51,520 --> 00:41:53,839
chat yeah 256. exactly you just

00:41:53,839 --> 00:41:57,760
concatenate the transaction ids

00:41:57,920 --> 00:41:59,440
which are basically the hashes of the

00:41:59,440 --> 00:42:01,040
time yeah so

00:42:01,040 --> 00:42:02,960
you basically hash transaction data to

00:42:02,960 --> 00:42:04,880
give you a transaction id and then you

00:42:04,880 --> 00:42:05,420
yeah yeah

00:42:05,420 --> 00:42:06,800
[Music]

00:42:06,800 --> 00:42:07,170
um

00:42:07,170 --> 00:42:08,319
[Music]

00:42:08,319 --> 00:42:10,319
so there we go um that's the merkel

00:42:10,319 --> 00:42:11,280
route

00:42:11,280 --> 00:42:13,760
uh time also in the block header

00:42:13,760 --> 00:42:15,359
you have something called but you just

00:42:15,359 --> 00:42:17,520
have the time which is a timestamp

00:42:17,520 --> 00:42:19,280
um like so

00:42:19,280 --> 00:42:21,839
but you don't the way the

00:42:21,839 --> 00:42:23,760
time is encoded in the block header is

00:42:23,760 --> 00:42:25,440
using unix time

00:42:25,440 --> 00:42:27,280
which is the number of seconds since the

00:42:27,280 --> 00:42:29,359
1st january 1970.

00:42:29,359 --> 00:42:30,880
so this

00:42:30,880 --> 00:42:34,480
blocks times timestamping so the human

00:42:34,480 --> 00:42:36,880
representation is 12 may 2011 but in

00:42:36,880 --> 00:42:38,960
unix time that would be this many

00:42:38,960 --> 00:42:41,040
seconds

00:42:41,040 --> 00:42:42,319
um

00:42:42,319 --> 00:42:43,599
a quick note

00:42:43,599 --> 00:42:45,680
on the time um these don't have to be

00:42:45,680 --> 00:42:46,720
accurate

00:42:46,720 --> 00:42:48,560
um they just have to be between a

00:42:48,560 --> 00:42:51,280
certain minimum and maximum value

00:42:51,280 --> 00:42:52,400
so um

00:42:52,400 --> 00:42:53,920
the minimum value

00:42:53,920 --> 00:42:55,520
you can set as the time for your block

00:42:55,520 --> 00:42:58,960
header is the median time of the last 11

00:42:58,960 --> 00:43:00,079
blocks

00:43:00,079 --> 00:43:03,359
or basically the the time set that's

00:43:03,359 --> 00:43:06,160
been the time of in the block header of

00:43:06,160 --> 00:43:08,800
the sixth block down

00:43:08,800 --> 00:43:10,800
so you can't have a time

00:43:10,800 --> 00:43:12,400
uh any lower than that

00:43:12,400 --> 00:43:14,000
that's the minimum bound

00:43:14,000 --> 00:43:15,599
and then the maximum

00:43:15,599 --> 00:43:17,839
um

00:43:17,839 --> 00:43:19,119
the maximum

00:43:19,119 --> 00:43:22,720
basically your node has its own time

00:43:22,720 --> 00:43:24,160
uh when you run it it just uses your

00:43:24,160 --> 00:43:26,000
computer's time and then when other

00:43:26,000 --> 00:43:28,000
nodes connect to you they will send you

00:43:28,000 --> 00:43:30,000
what their time is on their computer and

00:43:30,000 --> 00:43:31,760
so your node will keep track of the

00:43:31,760 --> 00:43:33,760
difference between

00:43:33,760 --> 00:43:35,119
all of the times of the nodes you're

00:43:35,119 --> 00:43:36,560
connected to

00:43:36,560 --> 00:43:38,560
and if you put them in order and you

00:43:38,560 --> 00:43:40,400
take the median time

00:43:40,400 --> 00:43:42,319
of all the nodes you're connected to

00:43:42,319 --> 00:43:44,319
um that's called the network average

00:43:44,319 --> 00:43:45,760
time

00:43:45,760 --> 00:43:47,280
so um

00:43:47,280 --> 00:43:50,079
the maximum value of this time is the

00:43:50,079 --> 00:43:53,680
network average time plus two hours

00:43:53,680 --> 00:43:55,520
so can you repeat this

00:43:55,520 --> 00:43:57,839
like quickly i mean i just got a little

00:43:57,839 --> 00:44:00,800
confused so why is this time used and uh

00:44:00,800 --> 00:44:02,480
is this the time to mine a block or

00:44:02,480 --> 00:44:04,480
something i mean uh no uh no this is

00:44:04,480 --> 00:44:07,280
this this time um i think this is i

00:44:07,280 --> 00:44:08,560
think this is quite a bit unnecessary

00:44:08,560 --> 00:44:11,200
necessary for me to explain um basically

00:44:11,200 --> 00:44:12,960
the time is just you just stick the

00:44:12,960 --> 00:44:14,960
current time of your computer um in the

00:44:14,960 --> 00:44:18,000
block header but it's but it's not um

00:44:18,000 --> 00:44:20,560
it doesn't have to be precise um

00:44:20,560 --> 00:44:23,200
it's not yeah so basically it just has

00:44:23,200 --> 00:44:25,760
to be between two certain values um as

00:44:25,760 --> 00:44:28,720
long as it's a greater than um the time

00:44:28,720 --> 00:44:29,599
of

00:44:29,599 --> 00:44:32,480
the sixth block down

00:44:32,480 --> 00:44:35,280
yeah or the meat of the median time of

00:44:35,280 --> 00:44:36,880
the last 11 blocks

00:44:36,880 --> 00:44:38,400
um it can't be any lower than that

00:44:38,400 --> 00:44:40,240
because if you were to put a time lower

00:44:40,240 --> 00:44:42,160
than that then it would get rejected by

00:44:42,160 --> 00:44:43,920
the nodes you send it to and also the

00:44:43,920 --> 00:44:45,760
maximum time is basically the current

00:44:45,760 --> 00:44:47,119
time

00:44:47,119 --> 00:44:49,280
plus two hours

00:44:49,280 --> 00:44:51,440
but it's we used

00:44:51,440 --> 00:44:53,920
um network average time is used which is

00:44:53,920 --> 00:44:56,000
just the average time

00:44:56,000 --> 00:44:57,359
of all the nodes that are connected to

00:44:57,359 --> 00:44:58,800
you

00:44:58,800 --> 00:44:59,680
um

00:44:59,680 --> 00:45:01,839
so don't worry about that um but it's

00:45:01,839 --> 00:45:03,599
basically all i'm saying is the time can

00:45:03,599 --> 00:45:04,640
be

00:45:04,640 --> 00:45:07,200
roughly an hour behind one or two hours

00:45:07,200 --> 00:45:08,079
ahead

00:45:08,079 --> 00:45:09,920
so it's not really if you see if a block

00:45:09,920 --> 00:45:12,079
comes comes through and it has a time

00:45:12,079 --> 00:45:13,359
like

00:45:13,359 --> 00:45:15,280
before or ahead of like a different

00:45:15,280 --> 00:45:16,240
block

00:45:16,240 --> 00:45:17,839
it doesn't really matter it has this

00:45:17,839 --> 00:45:20,240
sort of flexible sort of upper and lower

00:45:20,240 --> 00:45:22,240
boundary

00:45:22,240 --> 00:45:25,359
all right so that's the time um bits um

00:45:25,359 --> 00:45:27,440
bits remember the target

00:45:27,440 --> 00:45:29,599
bits is just a compact representation of

00:45:29,599 --> 00:45:30,800
the target

00:45:30,800 --> 00:45:33,359
so instead of putting the the current

00:45:33,359 --> 00:45:35,200
target um

00:45:35,200 --> 00:45:37,760
the entire target in the block header

00:45:37,760 --> 00:45:40,000
what you what you do

00:45:40,000 --> 00:45:42,880
is you just grab um the first three

00:45:42,880 --> 00:45:45,520
significant bytes or the first six you

00:45:45,520 --> 00:45:47,599
know significant characters after the

00:45:47,599 --> 00:45:49,680
leading zeros and then you put that

00:45:49,680 --> 00:45:50,560
there

00:45:50,560 --> 00:45:51,599
and then

00:45:51,599 --> 00:45:54,960
um you just grab the offset so how far

00:45:54,960 --> 00:45:55,760
these

00:45:55,760 --> 00:45:58,560
um three bytes are from the right

00:45:58,560 --> 00:46:00,880
uh and that is there are 26 bytes from

00:46:00,880 --> 00:46:02,240
the right here

00:46:02,240 --> 00:46:06,160
or in hexadecimal 26 is 1a

00:46:06,160 --> 00:46:08,640
so you just put that start there so bits

00:46:08,640 --> 00:46:10,800
is just this compact representation of

00:46:10,800 --> 00:46:13,280
the target

00:46:13,440 --> 00:46:15,040
um

00:46:15,040 --> 00:46:16,400
then that's it then then you just have

00:46:16,400 --> 00:46:18,800
the nonce and you can set that to zero

00:46:18,800 --> 00:46:22,400
and so this is all the basic data now um

00:46:22,400 --> 00:46:23,839
for the block header

00:46:23,839 --> 00:46:25,839
does that does it all these fields make

00:46:25,839 --> 00:46:28,720
sense each part okay good um so now

00:46:28,720 --> 00:46:30,160
we've got all the fields ready to be

00:46:30,160 --> 00:46:31,599
mined

00:46:31,599 --> 00:46:34,319
um we just have to get all the data into

00:46:34,319 --> 00:46:35,760
the correct format

00:46:35,760 --> 00:46:37,839
uh so this is just a bit of programming

00:46:37,839 --> 00:46:39,040
just to make sure everything's in the

00:46:39,040 --> 00:46:41,520
right order and format

00:46:41,520 --> 00:46:44,400
each field um should be in hexa put it

00:46:44,400 --> 00:46:46,640
all into hexadecimal

00:46:46,640 --> 00:46:47,680
so

00:46:47,680 --> 00:46:49,440
one is one in hexadecimal so this is

00:46:49,440 --> 00:46:51,040
going to change but you just go through

00:46:51,040 --> 00:46:52,560
every single field making sure that it's

00:46:52,560 --> 00:46:54,160
all hexadecimal so

00:46:54,160 --> 00:46:56,640
these two hexadecimal the time this is

00:46:56,640 --> 00:46:58,079
in decimal at the moment so we just

00:46:58,079 --> 00:47:00,079
convert that hex decimal and you do the

00:47:00,079 --> 00:47:02,800
same for every other field

00:47:02,800 --> 00:47:03,839
secondly

00:47:03,839 --> 00:47:05,359
each field

00:47:05,359 --> 00:47:07,040
must be a

00:47:07,040 --> 00:47:09,599
fixed number of bytes

00:47:09,599 --> 00:47:11,040
so there's only got one character in

00:47:11,040 --> 00:47:13,760
here but the version field is four bytes

00:47:13,760 --> 00:47:16,160
so if we convert that to four bytes it

00:47:16,160 --> 00:47:17,839
looks like this

00:47:17,839 --> 00:47:20,720
so one byte is two characters so zero

00:47:20,720 --> 00:47:23,119
zero that's one byte and there are four

00:47:23,119 --> 00:47:25,680
bytes in the version

00:47:25,680 --> 00:47:26,640
um

00:47:26,640 --> 00:47:27,680
then you just go through every single

00:47:27,680 --> 00:47:29,599
field giving it

00:47:29,599 --> 00:47:32,000
putting it into the correct um

00:47:32,000 --> 00:47:34,480
size so this is already 32 bytes that's

00:47:34,480 --> 00:47:36,319
already 32 bytes

00:47:36,319 --> 00:47:37,760
the time's gonna be four bytes it's

00:47:37,760 --> 00:47:40,400
already four bits same again four the

00:47:40,400 --> 00:47:42,640
nonce then that's four bytes as well

00:47:42,640 --> 00:47:45,119
so just for each field make sure that

00:47:45,119 --> 00:47:47,440
you've padded it out padded it out

00:47:47,440 --> 00:47:49,760
with the right number of bytes so this

00:47:49,760 --> 00:47:52,720
basically means that when a computer can

00:47:52,720 --> 00:47:54,079
read through each individual fields

00:47:54,079 --> 00:47:56,480
easily

00:47:56,960 --> 00:47:58,880
so that's all the

00:47:58,880 --> 00:48:00,640
data in the right

00:48:00,640 --> 00:48:03,359
format and the right field size

00:48:03,359 --> 00:48:05,280
lastly the only

00:48:05,280 --> 00:48:07,440
slightly frustrating thing with bitcoin

00:48:07,440 --> 00:48:10,160
is that when you send

00:48:10,160 --> 00:48:12,400
data to

00:48:12,400 --> 00:48:15,440
um the nodes um

00:48:15,440 --> 00:48:17,599
across the wire

00:48:17,599 --> 00:48:19,680
you have to send the data in reverse

00:48:19,680 --> 00:48:22,160
byte order which is called network byte

00:48:22,160 --> 00:48:23,200
order

00:48:23,200 --> 00:48:26,079
so um obviously we've got all this in

00:48:26,079 --> 00:48:29,200
human readable human human readable byte

00:48:29,200 --> 00:48:31,520
order but when you

00:48:31,520 --> 00:48:33,520
hash and work with bitcoin data it has

00:48:33,520 --> 00:48:35,680
to be in reverse byte order so you just

00:48:35,680 --> 00:48:37,200
go through every single field and put it

00:48:37,200 --> 00:48:39,440
into network byte order

00:48:39,440 --> 00:48:43,040
which is just reversing each byte

00:48:43,040 --> 00:48:45,599
so that's something that

00:48:45,599 --> 00:48:47,280
well they tripped me up when i first

00:48:47,280 --> 00:48:48,800
started mining i was like i was trying

00:48:48,800 --> 00:48:50,000
to hash these block headers and i was

00:48:50,000 --> 00:48:51,040
like why am i not getting the same

00:48:51,040 --> 00:48:52,800
results it's because

00:48:52,800 --> 00:48:54,559
you want to get everything in network

00:48:54,559 --> 00:48:56,240
byte order

00:48:56,240 --> 00:48:58,000
and just to show you i've made like a

00:48:58,000 --> 00:49:00,559
little quick um

00:49:00,559 --> 00:49:01,839
uh

00:49:01,839 --> 00:49:02,880
script

00:49:02,880 --> 00:49:06,480
so reverse bytes so if i put the

00:49:06,480 --> 00:49:08,160
a b c d e

00:49:08,160 --> 00:49:10,800
f one two three four

00:49:10,800 --> 00:49:13,200
let me see

00:49:13,839 --> 00:49:15,359
um the way that works is reverse byte

00:49:15,359 --> 00:49:17,520
order you just split it all into each

00:49:17,520 --> 00:49:19,839
individual byte so one byte is two

00:49:19,839 --> 00:49:23,200
characters and then you just um reverse

00:49:23,200 --> 00:49:24,720
the order of the bytes and that gives

00:49:24,720 --> 00:49:26,480
you that so that's how it works so

00:49:26,480 --> 00:49:28,480
you're not just reversing the string

00:49:28,480 --> 00:49:31,680
you are um reversing each byte

00:49:31,680 --> 00:49:34,800
so this might be a basic question but uh

00:49:34,800 --> 00:49:35,920
one

00:49:35,920 --> 00:49:38,720
so two characters is one byte yes yes

00:49:38,720 --> 00:49:40,400
yeah

00:49:40,400 --> 00:49:41,680
yep

00:49:41,680 --> 00:49:42,800
um

00:49:42,800 --> 00:49:45,200
that's just something i've learned

00:49:45,200 --> 00:49:47,359
uh

00:49:47,359 --> 00:49:51,520
i'm just looking at the c plus plus

00:49:51,520 --> 00:49:53,520
uh i've not done c plus plus in a long

00:49:53,520 --> 00:49:54,480
time

00:49:54,480 --> 00:49:59,520
so character type size is one byte um

00:50:01,599 --> 00:50:04,079
yeah no i i don't i don't know that much

00:50:04,079 --> 00:50:06,640
deep about computer science um but all i

00:50:06,640 --> 00:50:08,800
know is yeah

00:50:08,800 --> 00:50:10,880
i'm doing this more like a top down sort

00:50:10,880 --> 00:50:12,720
of level i i've just learned that um two

00:50:12,720 --> 00:50:15,359
characters translates as one byte so

00:50:15,359 --> 00:50:17,440
yeah

00:50:17,440 --> 00:50:19,599
um so there we are now we've got all the

00:50:19,599 --> 00:50:22,160
data finally in the right order um all

00:50:22,160 --> 00:50:23,839
you do then you just concatenate each

00:50:23,839 --> 00:50:26,559
individual field together like that so

00:50:26,559 --> 00:50:28,319
this is the block header

00:50:28,319 --> 00:50:30,559
now it's ready to put inside to put into

00:50:30,559 --> 00:50:32,240
the hash function

00:50:32,240 --> 00:50:35,440
um as i mentioned um sha-256 simple

00:50:35,440 --> 00:50:38,480
hashing algorithm 256

00:50:38,480 --> 00:50:39,520
is used

00:50:39,520 --> 00:50:41,839
um but in bitcoin everything gets hashed

00:50:41,839 --> 00:50:42,800
twice

00:50:42,800 --> 00:50:44,319
um

00:50:44,319 --> 00:50:46,400
it's just the way it was designed i

00:50:46,400 --> 00:50:48,240
don't think it provides any massive

00:50:48,240 --> 00:50:50,800
benefits it's just the way that

00:50:50,800 --> 00:50:52,640
bitcoin hashes things

00:50:52,640 --> 00:50:53,520
um

00:50:53,520 --> 00:50:55,760
so you just put this into hash function

00:50:55,760 --> 00:50:58,480
spits our result and then spits out then

00:50:58,480 --> 00:50:59,920
you hash the result to get you another

00:50:59,920 --> 00:51:01,359
result and that's the

00:51:01,359 --> 00:51:02,800
final hash

00:51:02,800 --> 00:51:05,520
um quick note um

00:51:05,520 --> 00:51:07,680
when when you hash things in bitcoin um

00:51:07,680 --> 00:51:10,000
this is in hexadecimal but you convert

00:51:10,000 --> 00:51:12,000
it into binary first so you put binary

00:51:12,000 --> 00:51:14,800
data into the hashing function

00:51:14,800 --> 00:51:15,920
and then

00:51:15,920 --> 00:51:17,520
that'll spit out a binding result then

00:51:17,520 --> 00:51:19,280
you put the binary result into the

00:51:19,280 --> 00:51:20,079
second

00:51:20,079 --> 00:51:21,440
hashing function

00:51:21,440 --> 00:51:24,880
that'll spit out a second binary digest

00:51:24,880 --> 00:51:27,839
and then when you convert that

00:51:27,839 --> 00:51:29,359
second digest

00:51:29,359 --> 00:51:31,200
back into hexadecimal

00:51:31,200 --> 00:51:33,040
that'll give you the

00:51:33,040 --> 00:51:35,119
um

00:51:35,119 --> 00:51:38,319
block hash but obviously this is in

00:51:38,319 --> 00:51:39,359
reverse

00:51:39,359 --> 00:51:41,680
uh network byte order again so if you

00:51:41,680 --> 00:51:42,880
reverse it

00:51:42,880 --> 00:51:45,760
then that's in the more human

00:51:45,760 --> 00:51:49,040
uh format so if you compare this

00:51:49,040 --> 00:51:50,559
to the target you want to make sure it's

00:51:50,559 --> 00:51:53,520
in you want to reverse it back into

00:51:53,520 --> 00:51:55,359
uh

00:51:55,359 --> 00:51:58,079
non-network byte order

00:51:58,079 --> 00:51:58,880
so

00:51:58,880 --> 00:52:01,359
so there we go um so this i've only

00:52:01,359 --> 00:52:03,119
covered these things because they just

00:52:03,119 --> 00:52:05,599
trip you up i mean get in the fields

00:52:05,599 --> 00:52:07,200
it's quite simple but then get anything

00:52:07,200 --> 00:52:08,960
into the right order then converting it

00:52:08,960 --> 00:52:11,040
to binary and then switching it back

00:52:11,040 --> 00:52:11,839
again

00:52:11,839 --> 00:52:14,240
um that's what'll trip you up if you're

00:52:14,240 --> 00:52:15,920
trying to minor block header or hash a

00:52:15,920 --> 00:52:18,240
block header for yourself

00:52:18,240 --> 00:52:20,640
all right so this was the block header

00:52:20,640 --> 00:52:23,760
on the left which already had the fields

00:52:23,760 --> 00:52:26,319
in reverse network order right

00:52:26,319 --> 00:52:28,240
uh yes yes

00:52:28,240 --> 00:52:30,400
okay then you

00:52:30,400 --> 00:52:31,359
uh

00:52:31,359 --> 00:52:34,319
do a double hash of that yeah and you

00:52:34,319 --> 00:52:36,720
convert it to hex and

00:52:36,720 --> 00:52:40,160
you converted that again in reverse

00:52:40,160 --> 00:52:43,599
i reversed it i reversed it back

00:52:44,000 --> 00:52:44,839
okay

00:52:44,839 --> 00:52:48,319
um yeah and this is how this is

00:52:48,319 --> 00:52:50,559
like if you mind the block this is the

00:52:50,559 --> 00:52:52,319
hash that you would send on to the

00:52:52,319 --> 00:52:54,880
network is that uh

00:52:54,880 --> 00:52:56,720
um let's say that you end up mining a

00:52:56,720 --> 00:52:58,880
block and let's say you get a nuance

00:52:58,880 --> 00:53:01,599
that is like below a target value yeah

00:53:01,599 --> 00:53:02,880
uh

00:53:02,880 --> 00:53:04,720
what do you do next yeah i mean okay i

00:53:04,720 --> 00:53:06,800
think i should cover that now i think um

00:53:06,800 --> 00:53:08,480
so okay um

00:53:08,480 --> 00:53:09,920
you don't actually send the block hash

00:53:09,920 --> 00:53:11,280
um you just send basically the block

00:53:11,280 --> 00:53:12,880
header and the transactions

00:53:12,880 --> 00:53:13,599
so

00:53:13,599 --> 00:53:15,440
okay but i'm just i don't think you have

00:53:15,440 --> 00:53:16,720
to if you're programming you wouldn't

00:53:16,720 --> 00:53:18,319
you might not have to reverse it this is

00:53:18,319 --> 00:53:19,599
just so i can

00:53:19,599 --> 00:53:23,040
display the results correctly uh in a

00:53:23,040 --> 00:53:24,720
sort of a human way

00:53:24,720 --> 00:53:27,359
so again so now like a minor you just

00:53:27,359 --> 00:53:29,520
change the nonce now i'm incrementing it

00:53:29,520 --> 00:53:30,240
from

00:53:30,240 --> 00:53:32,720
um zero one two three four five and so

00:53:32,720 --> 00:53:35,359
on so there you are obviously this is in

00:53:35,359 --> 00:53:36,880
network byte order

00:53:36,880 --> 00:53:40,319
and so on eventually you'll get a

00:53:40,319 --> 00:53:41,359
uh

00:53:41,359 --> 00:53:43,280
hash uh this below the target if you're

00:53:43,280 --> 00:53:44,160
lucky

00:53:44,160 --> 00:53:46,319
then that's mind so when you mind the

00:53:46,319 --> 00:53:47,839
actual block

00:53:47,839 --> 00:53:49,280
so this is done now so this is a

00:53:49,280 --> 00:53:51,280
successful block header

00:53:51,280 --> 00:53:52,000
so

00:53:52,000 --> 00:53:54,319
if you send this block header to anyone

00:53:54,319 --> 00:53:55,760
else they can hash it for themselves and

00:53:55,760 --> 00:53:57,200
they get the same result

00:53:57,200 --> 00:53:58,559
that's what i think that's what they

00:53:58,559 --> 00:54:00,400
call proof of work because you can just

00:54:00,400 --> 00:54:01,599
send this block header to anyone and

00:54:01,599 --> 00:54:03,440
they can prove for themselves that the

00:54:03,440 --> 00:54:05,359
hash is below the target so what you

00:54:05,359 --> 00:54:08,240
what you do then is you send this block

00:54:08,240 --> 00:54:10,480
uh to all the nodes you're connected to

00:54:10,480 --> 00:54:12,400
and what you're actually sending them is

00:54:12,400 --> 00:54:14,480
all of the transaction data concatenated

00:54:14,480 --> 00:54:16,480
together for each transaction

00:54:16,480 --> 00:54:17,440
um

00:54:17,440 --> 00:54:18,880
before that you put like a little

00:54:18,880 --> 00:54:20,559
transaction counter

00:54:20,559 --> 00:54:22,559
which is just a byte

00:54:22,559 --> 00:54:25,200
it's a it's a very very variable sized

00:54:25,200 --> 00:54:26,960
byte i haven't covered it but it's on

00:54:26,960 --> 00:54:28,720
the website um

00:54:28,720 --> 00:54:30,079
just tells you how many transactions are

00:54:30,079 --> 00:54:31,839
in the block and then before that you

00:54:31,839 --> 00:54:33,520
have the block header so this is what

00:54:33,520 --> 00:54:35,359
gets sent to

00:54:35,359 --> 00:54:37,599
um all the nodes so you don't have to

00:54:37,599 --> 00:54:38,480
send the

00:54:38,480 --> 00:54:39,839
block hash because they can calculate it

00:54:39,839 --> 00:54:42,400
for themselves

00:54:43,119 --> 00:54:44,800
so um

00:54:44,800 --> 00:54:47,599
that's how mining works um what i

00:54:47,599 --> 00:54:50,079
thought i would do now is um try and

00:54:50,079 --> 00:54:53,200
show you how you could uh

00:54:53,200 --> 00:54:56,800
mine a actual live block

00:54:56,800 --> 00:54:58,160
so yeah

00:54:58,160 --> 00:55:01,359
right so um if you run a bitcoin node

00:55:01,359 --> 00:55:05,040
um you have the um bitcoin cli um

00:55:05,040 --> 00:55:06,880
command which allows you to ask the

00:55:06,880 --> 00:55:08,640
bitcoin no questions and one of them you

00:55:08,640 --> 00:55:12,480
can ask them is to get block template

00:55:12,480 --> 00:55:14,559
so what that will do that will take your

00:55:14,559 --> 00:55:16,800
current memory pool and

00:55:16,800 --> 00:55:20,240
gather the highest value transactions

00:55:20,240 --> 00:55:21,839
that would fill up a

00:55:21,839 --> 00:55:22,720
block

00:55:22,720 --> 00:55:24,960
and

00:55:25,119 --> 00:55:27,680
give them to you so this is showing me

00:55:27,680 --> 00:55:29,119
all of the transactions that would make

00:55:29,119 --> 00:55:30,400
a

00:55:30,400 --> 00:55:32,319
candidate block

00:55:32,319 --> 00:55:37,520
so um let me just move this down sorry

00:55:38,000 --> 00:55:38,880
um

00:55:38,880 --> 00:55:40,720
so

00:55:40,720 --> 00:55:44,079
uh if we to if i just quickly examine um

00:55:44,079 --> 00:55:45,359
the information

00:55:45,359 --> 00:55:48,079
inside here if you if you um use bitcoin

00:55:48,079 --> 00:55:50,640
cli help get block template that will

00:55:50,640 --> 00:55:52,640
show you um all the fields that will

00:55:52,640 --> 00:55:55,119
give you all the fields they'll produce

00:55:55,119 --> 00:55:57,920
um but if i just quickly

00:55:57,920 --> 00:55:59,520
um

00:55:59,520 --> 00:56:02,319
what we want to see basically to minor

00:56:02,319 --> 00:56:04,319
block is to create a block header from

00:56:04,319 --> 00:56:06,240
all these transactions

00:56:06,240 --> 00:56:09,680
so bitcoin cli get block template

00:56:09,680 --> 00:56:11,520
and i'm going to use um

00:56:11,520 --> 00:56:14,319
grep just to search for the fields that

00:56:14,319 --> 00:56:15,680
we want

00:56:15,680 --> 00:56:19,200
i'm using rg which is a variant of grep

00:56:19,200 --> 00:56:21,760
and so we want to find we want to have a

00:56:21,760 --> 00:56:22,720
version

00:56:22,720 --> 00:56:24,160
number

00:56:24,160 --> 00:56:27,599
we want the previous block

00:56:27,920 --> 00:56:30,480
then we want the merkle root

00:56:30,480 --> 00:56:31,359
um

00:56:31,359 --> 00:56:32,559
then we want

00:56:32,559 --> 00:56:33,440
time

00:56:33,440 --> 00:56:34,799
then bits

00:56:34,799 --> 00:56:36,400
then there's a nonce but

00:56:36,400 --> 00:56:37,920
we're going to provide our own nuns so

00:56:37,920 --> 00:56:39,440
we don't need that

00:56:39,440 --> 00:56:41,359
so looking at the

00:56:41,359 --> 00:56:45,000
i spelt that wrong

00:56:45,200 --> 00:56:47,520
there we are so

00:56:47,520 --> 00:56:49,280
looking at the results of block get

00:56:49,280 --> 00:56:51,200
block template it's given us the version

00:56:51,200 --> 00:56:52,960
the previous block hash it's also giving

00:56:52,960 --> 00:56:56,160
us the time current time and bits

00:56:56,160 --> 00:56:58,480
so it's changing the current time

00:56:58,480 --> 00:57:00,000
so what it's not giving us is a miracle

00:57:00,000 --> 00:57:01,440
root

00:57:01,440 --> 00:57:02,880
um

00:57:02,880 --> 00:57:05,520
for some i don't know why it's not um

00:57:05,520 --> 00:57:07,440
but what you can do

00:57:07,440 --> 00:57:12,160
um what it is giving you is um

00:57:12,160 --> 00:57:13,520
this is just a

00:57:13,520 --> 00:57:15,440
json parser

00:57:15,440 --> 00:57:17,520
it has given you um

00:57:17,520 --> 00:57:19,440
a list of

00:57:19,440 --> 00:57:20,799
transactions

00:57:20,799 --> 00:57:22,400
and it has given you all the transaction

00:57:22,400 --> 00:57:25,040
ids so if we just go through each one

00:57:25,040 --> 00:57:27,040
and say give us

00:57:27,040 --> 00:57:29,599
the transaction ids

00:57:29,599 --> 00:57:33,920
now let's need to put that in quotes

00:57:36,240 --> 00:57:37,599
there we are so these are all the

00:57:37,599 --> 00:57:39,680
transaction ids

00:57:39,680 --> 00:57:41,760
in this candidate block

00:57:41,760 --> 00:57:43,200
so now we've got all those transaction

00:57:43,200 --> 00:57:44,400
ids we just need to create our own

00:57:44,400 --> 00:57:46,480
merkle route for them

00:57:46,480 --> 00:57:47,200
so

00:57:47,200 --> 00:57:49,839
um luckily i've written my own script

00:57:49,839 --> 00:57:51,760
and that will take in a list of

00:57:51,760 --> 00:57:53,599
transactions and create a miracle route

00:57:53,599 --> 00:57:55,359
from them

00:57:55,359 --> 00:57:56,960
um i've made this available on the

00:57:56,960 --> 00:57:58,960
website i'll show it in the moment

00:57:58,960 --> 00:58:00,720
so if i just do that

00:58:00,720 --> 00:58:02,880
then we have a miracle root

00:58:02,880 --> 00:58:05,839
so now um we've got all the data we need

00:58:05,839 --> 00:58:07,280
to mine a

00:58:07,280 --> 00:58:08,799
both or basically to construct a block

00:58:08,799 --> 00:58:10,640
header

00:58:10,640 --> 00:58:12,480
so if you just bare with me for five

00:58:12,480 --> 00:58:14,400
minutes i'm gonna go through each field

00:58:14,400 --> 00:58:16,079
and um

00:58:16,079 --> 00:58:18,720
yeah so first of all uh we need to get

00:58:18,720 --> 00:58:20,640
the version

00:58:20,640 --> 00:58:23,119
oh that's done wrong

00:58:23,119 --> 00:58:25,200
okay

00:58:25,200 --> 00:58:27,440
so there we are using get a get block

00:58:27,440 --> 00:58:29,119
template this is the current version uh

00:58:29,119 --> 00:58:32,079
like i said they've changed a bit so um

00:58:32,079 --> 00:58:33,040
this is

00:58:33,040 --> 00:58:34,640
they've been used to vote for voting so

00:58:34,640 --> 00:58:36,960
this is why it's a very high number but

00:58:36,960 --> 00:58:38,160
i'm not going to spend it now just take

00:58:38,160 --> 00:58:39,680
it as it is

00:58:39,680 --> 00:58:40,480
um

00:58:40,480 --> 00:58:41,920
so this is the version number but

00:58:41,920 --> 00:58:44,559
obviously it's in uh decimal so to

00:58:44,559 --> 00:58:46,240
convert that into

00:58:46,240 --> 00:58:49,440
hexadecimal first first so there we are

00:58:49,440 --> 00:58:50,400
and then

00:58:50,400 --> 00:58:52,480
now it's in hexadecimal this is already

00:58:52,480 --> 00:58:54,559
um four bytes

00:58:54,559 --> 00:58:57,119
so i just swap the byte order or swap

00:58:57,119 --> 00:58:59,920
the endianness because sometimes

00:58:59,920 --> 00:59:01,280
um

00:59:01,280 --> 00:59:03,119
the byte order is referred to referred

00:59:03,119 --> 00:59:05,359
to as endianness

00:59:05,359 --> 00:59:06,720
um

00:59:06,720 --> 00:59:09,359
so there we are so this is the

00:59:09,359 --> 00:59:10,160
uh

00:59:10,160 --> 00:59:12,480
version all set up and ready to go so

00:59:12,480 --> 00:59:13,599
i'll just

00:59:13,599 --> 00:59:15,119
trim the end off that

00:59:15,119 --> 00:59:16,640
because i'm going to concatenate it all

00:59:16,640 --> 00:59:20,160
together so if i save this as a

00:59:20,160 --> 00:59:22,640
variable

00:59:25,680 --> 00:59:26,880
there we have so just

00:59:26,880 --> 00:59:29,359
echo that out to check

00:59:29,359 --> 00:59:31,520
so that's the version done so next up

00:59:31,520 --> 00:59:33,839
after the version is the

00:59:33,839 --> 00:59:37,520
version previous block

00:59:37,599 --> 00:59:39,599
so previous block

00:59:39,599 --> 00:59:40,799
hash

00:59:40,799 --> 00:59:42,559
so this is the block hash for the

00:59:42,559 --> 00:59:44,559
previous block

00:59:44,559 --> 00:59:47,119
let me just trim off the

00:59:47,119 --> 00:59:49,520
uh quotes

00:59:49,520 --> 00:59:51,040
and then

00:59:51,040 --> 00:59:52,640
uh it's already in hex decimal it's

00:59:52,640 --> 00:59:55,440
already 32 bytes so what i need to do is

00:59:55,440 --> 00:59:57,680
sort the byte order or put it into

00:59:57,680 --> 00:59:59,040
little endian

00:59:59,040 --> 01:00:01,760
so there we are and then i can save this

01:00:01,760 --> 01:00:03,599
then

01:00:03,599 --> 01:00:07,200
as the previous block variable

01:00:11,119 --> 01:00:15,040
next up then is the miracle root

01:00:15,040 --> 01:00:16,000
uh

01:00:16,000 --> 01:00:18,400
obviously we don't get a miracle root

01:00:18,400 --> 01:00:21,359
um from the get block template um

01:00:21,359 --> 01:00:23,839
command but what does give us is the

01:00:23,839 --> 01:00:25,440
list of transactions

01:00:25,440 --> 01:00:28,559
and for each of those it will give us um

01:00:28,559 --> 01:00:30,480
a transaction id

01:00:30,480 --> 01:00:31,440
oops

01:00:31,440 --> 01:00:33,599
oh well i just lost that

01:00:33,599 --> 01:00:35,280
oh there it is

01:00:35,280 --> 01:00:37,440
so there we go

01:00:37,440 --> 01:00:41,760
and from these i can get the merkle root

01:00:41,760 --> 01:00:44,000
there we are and then it's already in

01:00:44,000 --> 01:00:46,079
hexadecimal it's already in

01:00:46,079 --> 01:00:48,079
32 bytes i just need to sort the byte

01:00:48,079 --> 01:00:49,599
order

01:00:49,599 --> 01:00:50,960
again

01:00:50,960 --> 01:00:52,960
uh there we are i'll save that as a

01:00:52,960 --> 01:00:54,240
variable

01:00:54,240 --> 01:00:56,799
i'm going to call

01:00:58,640 --> 01:01:00,559
nearly there i know it's a bit laborious

01:01:00,559 --> 01:01:03,680
but uh so that's yeah so version

01:01:03,680 --> 01:01:05,920
previous block miracle root uh then we

01:01:05,920 --> 01:01:07,040
have the time

01:01:07,040 --> 01:01:08,839
um for some reason

01:01:08,839 --> 01:01:10,480
um

01:01:10,480 --> 01:01:12,640
even though the get plot template

01:01:12,640 --> 01:01:14,000
doesn't give you the merkel route it

01:01:14,000 --> 01:01:15,119
does give you

01:01:15,119 --> 01:01:17,520
the current time on your computer

01:01:17,520 --> 01:01:19,280
um

01:01:19,280 --> 01:01:21,200
actually it gives you a

01:01:21,200 --> 01:01:24,880
valid time i'm not sure if this is um

01:01:24,880 --> 01:01:25,839
i don't know but this is definitely a

01:01:25,839 --> 01:01:27,760
valid time but what you could do if you

01:01:27,760 --> 01:01:29,440
want to use that if you want to use the

01:01:29,440 --> 01:01:30,480
get blocked

01:01:30,480 --> 01:01:32,079
template time you can use the date

01:01:32,079 --> 01:01:34,400
function from a programming language

01:01:34,400 --> 01:01:36,240
so if you just this gives you the number

01:01:36,240 --> 01:01:37,599
of seconds

01:01:37,599 --> 01:01:39,680
in unix times if i just use that

01:01:39,680 --> 01:01:42,799
um just need to get it into hexadecimal

01:01:42,799 --> 01:01:44,000
like so

01:01:44,000 --> 01:01:46,720
one two three four five six seven so 24

01:01:46,720 --> 01:01:47,920
bytes

01:01:47,920 --> 01:01:48,799
uh

01:01:48,799 --> 01:01:51,960
then we

01:01:52,079 --> 01:01:53,599
it to and

01:01:53,599 --> 01:01:56,319
uh reverse bite order

01:01:56,319 --> 01:01:58,160
there we are so there is that's the time

01:01:58,160 --> 01:01:59,040
ready

01:01:59,040 --> 01:02:00,799
enough

01:02:00,799 --> 01:02:02,240
and

01:02:02,240 --> 01:02:04,480
that's the time done

01:02:04,480 --> 01:02:07,440
lastly uh bits

01:02:07,440 --> 01:02:09,119
which is the compact version of the

01:02:09,119 --> 01:02:11,359
target

01:02:11,359 --> 01:02:14,079
there it is you just trim off the

01:02:14,079 --> 01:02:16,240
uh

01:02:16,960 --> 01:02:18,079
quotes

01:02:18,079 --> 01:02:21,839
and then put into reverse byte order

01:02:22,400 --> 01:02:24,720
and there it is so now we've got all the

01:02:24,720 --> 01:02:28,160
basic block header data

01:02:28,160 --> 01:02:29,200
uh

01:02:29,200 --> 01:02:31,599
ready

01:02:32,160 --> 01:02:36,160
in the right format so if i

01:02:36,160 --> 01:02:38,240
just construct the block header from

01:02:38,240 --> 01:02:39,839
each individ each of those individual

01:02:39,839 --> 01:02:40,960
fields

01:02:40,960 --> 01:02:43,359
that is the version

01:02:43,359 --> 01:02:46,799
the previous block

01:02:46,839 --> 01:02:50,400
the miracle root

01:02:50,400 --> 01:02:52,000
then

01:02:52,000 --> 01:02:53,119
time

01:02:53,119 --> 01:02:55,280
and then bits

01:02:55,280 --> 01:02:58,640
so check what that looks like

01:02:58,960 --> 01:03:00,640
there it is there's our block header and

01:03:00,640 --> 01:03:02,480
so all we have all we haven't put there

01:03:02,480 --> 01:03:04,160
now is the nonce

01:03:04,160 --> 01:03:05,040
so

01:03:05,040 --> 01:03:06,960
if we wanted to

01:03:06,960 --> 01:03:08,960
mine this we just need to create a loop

01:03:08,960 --> 01:03:10,079
that will

01:03:10,079 --> 01:03:12,400
keep hashing this

01:03:12,400 --> 01:03:13,280
uh

01:03:13,280 --> 01:03:15,520
block header and we'll adjust the nonce

01:03:15,520 --> 01:03:17,599
increment it with every attempt

01:03:17,599 --> 01:03:20,480
so the nonce um will look like we'll

01:03:20,480 --> 01:03:22,640
start off with zero

01:03:22,640 --> 01:03:24,000
um but obviously we need to get this in

01:03:24,000 --> 01:03:25,920
the right format um so we need to

01:03:25,920 --> 01:03:28,839
convert that to um

01:03:28,839 --> 01:03:30,960
uh extradition

01:03:30,960 --> 01:03:32,240
sorry thank you

01:03:32,240 --> 01:03:36,319
uh then at least so like so

01:03:37,119 --> 01:03:38,880
uh but obviously this needs to be um

01:03:38,880 --> 01:03:40,640
four bytes in length so i made a little

01:03:40,640 --> 01:03:42,000
function that will just make sure it's

01:03:42,000 --> 01:03:43,359
the right size

01:03:43,359 --> 01:03:45,280
and then convert the swap end in

01:03:45,280 --> 01:03:46,720
obviously it's not very interesting

01:03:46,720 --> 01:03:48,559
because i've used the number zero but if

01:03:48,559 --> 01:03:50,000
i wish to use like a much higher nonce

01:03:50,000 --> 01:03:50,960
value

01:03:50,960 --> 01:03:52,559
uh like that

01:03:52,559 --> 01:03:55,039
then like so it's prepared it for me

01:03:55,039 --> 01:03:56,319
so i'm not going to append this to it

01:03:56,319 --> 01:03:57,440
yet what i'm going to do i'm going to

01:03:57,440 --> 01:04:00,640
create a loop so while true

01:04:00,640 --> 01:04:02,000
do

01:04:02,000 --> 01:04:03,760
you want to

01:04:03,760 --> 01:04:05,440
oh wait there before that i want to set

01:04:05,440 --> 01:04:08,400
a variable to

01:04:08,400 --> 01:04:11,680
an increment incremented variable ready

01:04:11,680 --> 01:04:14,559
so while true

01:04:14,559 --> 01:04:15,599
uh

01:04:15,599 --> 01:04:16,960
do

01:04:16,960 --> 01:04:18,079
want to

01:04:18,079 --> 01:04:19,760
create the nonce

01:04:19,760 --> 01:04:21,839
which is going to be like i just showed

01:04:21,839 --> 01:04:23,280
you um

01:04:23,280 --> 01:04:25,039
echo

01:04:25,039 --> 01:04:26,400
i

01:04:26,400 --> 01:04:28,960
uh they want to get it in deck

01:04:28,960 --> 01:04:31,039
hex decimal

01:04:31,039 --> 01:04:34,559
four byte field size swap endian

01:04:34,559 --> 01:04:35,359
uh

01:04:35,359 --> 01:04:37,760
trim off the end

01:04:37,760 --> 01:04:39,440
uh so that's the non stun

01:04:39,440 --> 01:04:42,319
then our attempt at

01:04:42,319 --> 01:04:44,319
trying to mine the block will be just

01:04:44,319 --> 01:04:45,280
the

01:04:45,280 --> 01:04:48,000
uh block header we created

01:04:48,000 --> 01:04:51,039
plus the nonce at the end

01:04:51,039 --> 01:04:52,160
and then what we want to do is we want

01:04:52,160 --> 01:04:53,440
to hash that

01:04:53,440 --> 01:04:55,039
um all together so i've made a little

01:04:55,039 --> 01:04:57,760
function that will hash for me um

01:04:57,760 --> 01:05:00,319
called hash 256 because this

01:05:00,319 --> 01:05:02,480
is just the the double hash converts the

01:05:02,480 --> 01:05:04,480
binary then double hashes it i'm going

01:05:04,480 --> 01:05:08,960
to hash 256 um the attempt

01:05:08,960 --> 01:05:09,839
and

01:05:09,839 --> 01:05:12,400
every after every attempt we want to

01:05:12,400 --> 01:05:15,920
uh increment the nonce so let

01:05:15,920 --> 01:05:18,559
uh i must plus so just increment the

01:05:18,559 --> 01:05:20,559
notes from

01:05:20,559 --> 01:05:21,680
this

01:05:21,680 --> 01:05:23,760
number here actually

01:05:23,760 --> 01:05:25,599
uh and then done so hopefully this will

01:05:25,599 --> 01:05:27,920
work there we are so now

01:05:27,920 --> 01:05:30,240
this is hashing

01:05:30,240 --> 01:05:31,200
um

01:05:31,200 --> 01:05:33,839
very slowly uh a block header the

01:05:33,839 --> 01:05:36,000
current block header obviously it's very

01:05:36,000 --> 01:05:37,680
slow it took me a long time but this is

01:05:37,680 --> 01:05:40,559
actually mine trying to mine a block

01:05:40,559 --> 01:05:42,319
um

01:05:42,319 --> 01:05:44,000
so if that was

01:05:44,000 --> 01:05:44,960
lucky

01:05:44,960 --> 01:05:46,400
what you'd probably do you'd have some

01:05:46,400 --> 01:05:48,480
code in there that would stop

01:05:48,480 --> 01:05:51,119
um when you if yeah if it reaches the

01:05:51,119 --> 01:05:52,799
target target yeah and then what you do

01:05:52,799 --> 01:05:55,839
then there's a function and bitcoin cli

01:05:55,839 --> 01:05:59,280
called um submit block

01:05:59,520 --> 01:06:01,760
and you would just submit

01:06:01,760 --> 01:06:05,839
the header the transaction count

01:06:06,400 --> 01:06:08,960
and all the transaction data so if you

01:06:08,960 --> 01:06:10,799
constructed a successful block header

01:06:10,799 --> 01:06:12,000
you would send that to all the nodes

01:06:12,000 --> 01:06:13,760
you're connected to and you'd use that

01:06:13,760 --> 01:06:15,280
do that using the

01:06:15,280 --> 01:06:17,280
submit block um

01:06:17,280 --> 01:06:19,599
bitcoin cli command

01:06:19,599 --> 01:06:21,839
is there a way to uh get the target

01:06:21,839 --> 01:06:24,559
value from the bitcoin cli

01:06:24,559 --> 01:06:27,039
uh yeah so um i think it's included in

01:06:27,039 --> 01:06:31,680
um bitcoin cli get block template

01:06:31,680 --> 01:06:35,119
yeah so um i think it's it's

01:06:35,119 --> 01:06:36,480
extending the block

01:06:36,480 --> 01:06:37,520
yeah so there it is so this is the

01:06:37,520 --> 01:06:39,599
current target so you could grab that

01:06:39,599 --> 01:06:42,160
target and then stick that summer into

01:06:42,160 --> 01:06:44,079
yeah into the for loop

01:06:44,079 --> 01:06:46,480
yeah but obviously um

01:06:46,480 --> 01:06:48,400
that that hashing there was very very

01:06:48,400 --> 01:06:49,200
slow

01:06:49,200 --> 01:06:51,599
oh yeah yeah i i totally get it yeah you

01:06:51,599 --> 01:06:53,200
probably want to do that yeah

01:06:53,200 --> 01:06:55,039
in a single programming language this is

01:06:55,039 --> 01:06:57,280
just on bash just for quick sort of

01:06:57,280 --> 01:06:58,960
illustration purposes but that just goes

01:06:58,960 --> 01:07:01,520
to show like how basically how simple uh

01:07:01,520 --> 01:07:03,599
mining is really the hardest part is

01:07:03,599 --> 01:07:05,520
just getting the data in the right order

01:07:05,520 --> 01:07:07,440
um but after that it's just you just

01:07:07,440 --> 01:07:09,680
increment a nonsense hash it and

01:07:09,680 --> 01:07:11,119
hopefully you get a result a lucky

01:07:11,119 --> 01:07:14,119
result

01:07:14,319 --> 01:07:15,760
um

01:07:15,760 --> 01:07:18,480
i think yeah so that's everything i

01:07:18,480 --> 01:07:21,039
wanted to explain about how mining works

01:07:21,039 --> 01:07:22,480
um

01:07:22,480 --> 01:07:23,839
that's all the technical stuff but

01:07:23,839 --> 01:07:25,119
obviously is

01:07:25,119 --> 01:07:27,440
probably a lot simpler than it's made

01:07:27,440 --> 01:07:29,760
out to be

01:07:29,760 --> 01:07:30,559
um

01:07:30,559 --> 01:07:32,400
on the website i've made all this code

01:07:32,400 --> 01:07:35,119
available so each those little um hex

01:07:35,119 --> 01:07:36,640
decimal converters and decimal

01:07:36,640 --> 01:07:37,760
converters

01:07:37,760 --> 01:07:40,960
and the swap endianness they're all here

01:07:40,960 --> 01:07:42,559
there's a miracle root function on here

01:07:42,559 --> 01:07:44,240
written in php

01:07:44,240 --> 01:07:46,960
um it's not the prettiest um but it will

01:07:46,960 --> 01:07:48,160
take a

01:07:48,160 --> 01:07:49,200
list of

01:07:49,200 --> 01:07:50,880
transaction ids and create american

01:07:50,880 --> 01:07:52,400
route for you

01:07:52,400 --> 01:07:54,400
i might not want to use it in production

01:07:54,400 --> 01:07:55,599
you might want to use a different

01:07:55,599 --> 01:07:57,760
library i'm sure there's loads of

01:07:57,760 --> 01:07:59,039
bitcoin libraries out there with their

01:07:59,039 --> 01:08:01,520
own merkle root um functions for you to

01:08:01,520 --> 01:08:03,760
use

01:08:04,559 --> 01:08:05,760
um

01:08:05,760 --> 01:08:07,760
is there any questions about

01:08:07,760 --> 01:08:09,920
that sort of mining process no i mean

01:08:09,920 --> 01:08:11,520
this this was really awesome great

01:08:11,520 --> 01:08:13,200
thanks a lot

01:08:13,200 --> 01:08:15,359
uh

01:08:16,000 --> 01:08:18,479
just curious any any experience with

01:08:18,479 --> 01:08:21,198
those heavy duty miners

01:08:21,198 --> 01:08:23,198
no i've not actually mined myself

01:08:23,198 --> 01:08:25,359
because like we said like it's so

01:08:25,359 --> 01:08:27,120
inefficient to mine on your laptop if

01:08:27,120 --> 01:08:28,960
you wanted to mine now it's not a hobby

01:08:28,960 --> 01:08:30,399
thing you have to sort of

01:08:30,399 --> 01:08:33,120
you know buy a professional mining rig

01:08:33,120 --> 01:08:34,640
and run it like a proper business which

01:08:34,640 --> 01:08:37,040
is a shame because that takes mining out

01:08:37,040 --> 01:08:38,880
of the hands of the average person then

01:08:38,880 --> 01:08:40,560
so

01:08:40,560 --> 01:08:41,920
um

01:08:41,920 --> 01:08:43,359
yeah so i think if you want to get into

01:08:43,359 --> 01:08:44,880
mind you you would have to really commit

01:08:44,880 --> 01:08:46,319
to it

01:08:46,319 --> 01:08:48,238
it's not just right gone yeah right

01:08:48,238 --> 01:08:50,080
right even those guys would be doing

01:08:50,080 --> 01:08:51,759
like at a fundamental level they would

01:08:51,759 --> 01:08:53,759
be doing the same thing right just

01:08:53,759 --> 01:08:54,799
faster

01:08:54,799 --> 01:08:56,158
yes so they're just doing the exact same

01:08:56,158 --> 01:08:57,600
thing constructing block header and just

01:08:57,600 --> 01:08:58,960
hashing it as fast as you can like this

01:08:58,960 --> 01:09:00,560
whole construction of the block header

01:09:00,560 --> 01:09:02,880
is simple and takes a

01:09:02,880 --> 01:09:05,359
absolute fraction of a second to do and

01:09:05,359 --> 01:09:08,080
then the whole mining then the whole

01:09:08,080 --> 01:09:10,080
meat of mining is hashing as fast as

01:09:10,080 --> 01:09:12,400
possible

01:09:13,600 --> 01:09:14,000
um

01:09:14,000 --> 01:09:15,359
[Music]

01:09:15,359 --> 01:09:16,640
i think i've

01:09:16,640 --> 01:09:18,238
don't think i've missed anything i think

01:09:18,238 --> 01:09:19,839
i've covered everything i wanted to

01:09:19,839 --> 01:09:21,759
sorry i know that's a bit repetitive in

01:09:21,759 --> 01:09:24,960
parts uh no no no this was a great

01:09:24,960 --> 01:09:26,960
explanation again yeah thanks a lot for

01:09:26,960 --> 01:09:28,000
this yeah

01:09:28,000 --> 01:09:29,600
but i think if you're starting out with

01:09:29,600 --> 01:09:31,679
bitcoin um

01:09:31,679 --> 01:09:33,279
one of the best ways to learn i think is

01:09:33,279 --> 01:09:34,880
to try and

01:09:34,880 --> 01:09:36,479
mine your own block header i think it's

01:09:36,479 --> 01:09:38,158
quite simple to do and i think mining is

01:09:38,158 --> 01:09:40,000
one of the sort of first fundamental

01:09:40,000 --> 01:09:41,839
parts of how bitcoin works so if you can

01:09:41,839 --> 01:09:44,479
figure out how to mine a block header

01:09:44,479 --> 01:09:46,158
or hash a block header that's a great

01:09:46,158 --> 01:09:47,839
stepping stone i'll give you the tools

01:09:47,839 --> 01:09:50,158
then to figure out about the all the um

01:09:50,158 --> 01:09:52,960
hexadecimal and network byte order and

01:09:52,960 --> 01:09:54,960
how to hash and then you can take those

01:09:54,960 --> 01:09:56,560
tools then and use them in other parts

01:09:56,560 --> 01:09:58,000
of bitcoin like in you know with

01:09:58,000 --> 01:10:01,040
transactions and all that

01:10:01,040 --> 01:10:02,719
so this would be my first place to start

01:10:02,719 --> 01:10:04,960
if you were to try coding with

01:10:04,960 --> 01:10:06,000
bitcoin

01:10:06,000 --> 01:10:07,600
i mean you you're obviously probably not

01:10:07,600 --> 01:10:08,560
going to

01:10:08,560 --> 01:10:10,560
set up your minor but as a sort of

01:10:10,560 --> 01:10:11,679
learning experience this is a great

01:10:11,679 --> 01:10:14,320
place to start

01:10:15,280 --> 01:10:17,199
so yeah if you want to browse block

01:10:17,199 --> 01:10:18,880
headers just go into livia bitcoin this

01:10:18,880 --> 01:10:20,560
is the blockchain

01:10:20,560 --> 01:10:21,920
and you can browse to each individual

01:10:21,920 --> 01:10:23,600
block and see all the different block

01:10:23,600 --> 01:10:25,520
headers and test for yourself

01:10:25,520 --> 01:10:27,520
then you can get the same

01:10:27,520 --> 01:10:28,960
block cache results

01:10:28,960 --> 01:10:31,280
nice

01:10:31,280 --> 01:10:32,400
yep

01:10:32,400 --> 01:10:35,280
so uh thank you very much for that uh

01:10:35,280 --> 01:10:37,120
that was good to do

01:10:37,120 --> 01:10:38,320
thanks

01:10:38,320 --> 01:10:42,520
no worries so yeah