0:02
Welcome to Practical Deep Learning for coders,  lesson one. This is version five of this course,  
0:11
and it's the first new one we've done  in two years. So, we've got a lot of   cool things to cover! It's amazing how much has  changed. Here is an xkcd from the end of 2015.  
What has changed since 2015
0:28
Who here has seen xkcd comics before?  …Pretty much everybody. Not surprising.  
0:35
So the basic joke here is… I'll let you  read it, and then I'll come back to it.
0:51
So, it can be hard to tell what's easy and what's  nearly impossible, and in 2015 or at the end of  
0:57
2015 the idea of checking whether something  is a photo of a bird was considered nearly   impossible. So impossible, it was the basic  idea of a joke. Because everybody knows that  
1:06
that's nearly impossible. We're now going to build  exactly that system for free in about two minutes!
1:15
So, let's build an “is it a bird” system. So, we're going to use python, and I'm  going to run through this really quickly.  
Is it a bird
1:23
You're not expected to run through it with me  because we're going to come back to it. But  
1:29
let's go ahead and run that cell. Okay, so what we're doing is we're  searching DuckDuckgo for images of  
1:38
bird photos and we're just going to grab one and so here is the url of  the bird that we grabbed.
1:49
Okay, we'll download it. Okay, so there it is. So we've grabbed a bird  and so okay we've now got something that can  
1:57
download pictures of birds. Now we're  going to need to build a system that can  
2:04
recognize things that are birds versus  things that aren't birds, from photos.   Now of course computers need numbers to work  with, but luckily images are made of numbers.
Images are made of numbers
2:17
I actually found this really  nice website called pixby  
2:25
where I can grab a bird, and if I wiggle over it  (let's pick its beak) you'll see here that that  
2:34
part of the beak was 251 brightness of red, 48  of green, and 21 of blue. So that's RGB. And so  
2:45
you can see as I wave around, those colors are  changing (those numbers). And so this picture,  
2:55
the thing that we recognize as a picture, is  actually 256 x 171 x 3 numbers, between 0 and 255,  
3:06
representing the amount of red, green and blue  on each pixel. So that's going to be an input  
3:12
to our program, that's going to try and figure  out whether this is a picture of a bird or not.
3:23
Okay, so let's go ahead and run this cell, which  is going to go through… (and I needed bird and  
Downloading images
3:31
non-bird but you can't really search Google  images or DuckDuckGo images for not a bird,  
3:37
it just doesn't work that way. So I just decided  to use forest - I thought okay pictures of forest   versus pictures of birds sounds like a good  starting point.) So I go through each of:  
3:46
forest, and bird. And I search for forest  photo and bird photo, download images,  
3:55
and then resize them to be no bigger than 400  pixels on a side - just because we don't need  
4:01
particularly big ones and it takes a surprisingly  large amount of time just for a computer to open   an image. Okay, so we've now got 200 of each.  I find when I download images I often get a few  
4:13
broken ones and if you try and train a model  with broken images it will not work. So here's  
4:18
something which just verifies each image and  unlinks - so deletes the ones that don't work
Creating a DataBlock and Learner
4:25
Okay, so now we can create what's called  a data block. So after I run this cell  
4:37
you'll see that I've basically… I'll go through  the details of this later, but… a data block  
4:44
gives fast.ai (the library) all the information  it needs to create a computer vision model. And  
4:49
so in this case we're basically telling it… get  all the image files that we just downloaded.   And then we say show me a few  up to six, and let's see… yeah,  
4:57
so we've got some birds, forest, bird,  bird, forest. Okay, so one of the nice   things about doing computer vision models is  it's really easy to check your data because  
5:04
you can just look at it - which is not  the case for a lot of kinds of models.
5:10
Okay, so we've now downloaded 200 pictures  of birds, 200 pictures of forests,  
5:17
so we'll now press run. And this model  is actually running on my laptop,  
Training the model and making a prediction
5:24
so this is not using a vast data center.  It's running on my presentation laptop. And  
5:29
it's doing it at the same time as my laptop is  streaming video, which is possibly a bad idea.
5:37
And so what it's going to do is it's going  to run through every photo out of those 400,  
5:44
and for the ones that are forest it's going  to learn a bit more about what forest looks   like and for the ones that are bird it'll  learn a bit more about what bird looks like.  
5:53
So overall it took under 30 seconds,  and believe it or not, that's enough to  
6:02
finish doing the thing which was  in that xkcd comic. Let's check  
6:08
by passing in that bird that we downloaded at the  start. This is a bird. Probability it's a bird:  
6:16
1.0000 (rounded to the nearest four decimal  places). So something pretty extraordinary  
6:23
has happened since late 2015, which is literally  something that has gone from so impossible it's  
6:30
a joke to so easy that I can run it on my laptop  computer in (I don't know how long it was) about  
6:39
two minutes. And so hopefully that gives you  a sense that creating really interesting,  
6:50
you know real working programs with deep learning  is something that… doesn't take a lot of code,  
6:55
didn't take any math, didn't take more than my  laptop computer. It's pretty accessible in fact.  
7:03
So that's really what we're going to be  learning about over the next seven weeks.
7:09
So where have we got to now  with deep learning? Well   it moves so fast, but even in the last few weeks  we've taken it up another notch as a community.  
What can deep learning do now
7:22
You might have seen that something called DALLꞏEꞏ2  has been released which uses deep learning to  
7:27
generate new pictures. And I thought this was an  amazing thing that this guy nick did where he took  
7:34
his friends twitter bios and typed them into the  DALLꞏEꞏ2 input and it generated these pictures. So  
7:42
this guy's… he typed in commitment, sympathetic,  psychedelic, philosophical, and it generated  
7:47
these pictures. So I'll just show you  a few of these. I'll let you read them…
7:54
I love that.
8:04
That one's pretty amazing I reckon! actually.
8:15
I love this. Happy Sisyphus has actually  got a happy rock to move around.
8:22
So this is like, um, yeah, I don't know. When  I look at these I still get pretty blown away  
8:28
that this is a computer algorithm using nothing  but this text input to generate these arbitrary  
8:36
pictures. In this case of fairly, you know,  complex and creative things. So the guy who  
8:42
made those points out, this is like… he spends  about two minutes or so, you know, creating  
8:48
each of these. Like he tries a few different  prompts and he tries a few different pictures,   you know, and so he's given an example here of…  like when he types something into the system…  
8:55
like, here's an example of like 10 different  things he gets back when he puts in “expressive  
9:01
painting of a man shining rays of justice and  transparency, on a blue bird twitter logo.”
9:09
So it's not just, you know, DALLꞏEꞏ2, to be  clear. There's, you know, a lot of different   systems doing something like this now. There's  something called MidJourney, which this twitter  
9:18
account posted: a “female scientist with a  laptop writing code, in a symbolic, meaningful,   and vibrant style.” This one here is “an HD  photo of a rare psychedelic pink elephant.”  
9:31
And this one I think is the second one here  (I never know how to actually pronounce this.)  
9:38
This one's pretty cool “a blind bat with big  sunglasses holding a walking stick in his hand.”
9:45
And so when actual artists, you know, this for  example, this guy said he knows nothing about art,  
9:53
you know he's got no artistic talent, it's just  something you know, he threw together. This guy is   an artist who actually writes his own software  based on deep learning and spends, you know,  
10:03
months on building stuff, and as you can see,  you can really take it to the next level.  
10:08
It's been really great actually to see how  a lot of fast.ai alumni with backgrounds as  
10:15
artists have gone on to bring deep learning and  art together, and it's a very exciting direction.  
10:21
And it's not just images to be clear, you know one  of another interesting thing that's popped up in   the last couple of weeks is google's pathways  language model which can take any arbitrary  
10:32
english as text, a question, and can create  an answer which not only answers the question  
Pathways Language Model (PaLM)
10:39
but also explains its thinking (whatever it  means for a language model to be thinking.)  
10:47
One of the ones I found pretty amazing was that  it can explain a joke. I'll let you read this…
11:07
So, this is actually a joke that probably needs  explanations for anybody who's not familiar with  
11:13
TPUs. So it, this model, just took the text  as input and created this text as output.  
11:21
And so you can see, you know, again, deep learning  models are doing things which I think very few,  
11:28
if any of us, would have believed would be maybe  possible to do by computers even in our lifetime
11:37
This means that there is a lot of  practical and ethical considerations.  
11:44
We will touch on them during this course  but can't possibly hope to do them justice.  
11:50
So I would certainly encourage you to check  out ethics.fast.ai to see our whole data ethics  
11:56
course, taught by my co-founder Dr Rachel Thomas,  which goes into these issues in a lot more detail.
12:08
All right, so as well as being an AI researcher  at the University of Queensland and fast.ai,  
12:15
I am also a homeschooling primary school teacher  and for that reason I study education a lot.  
12:24
One of the people who I love in education is a  guy named Dylan Williams and he has this great  
12:29
approach in his classrooms of figuring  out how his students are getting along,   which is to put a coloured cup on their desk  - green to mean that they're doing fine,  
12:40
yellow cup to mean I'm not quite sure, and a red  cup to mean I have no idea what's going on. Now  
12:47
since most of you are watching this remotely  I can't look at your cups and I don't think   anybody bought coloured cups with them today,  so instead we have an online version of this.  
12:59
So what I want you to do is go to  cups.fast.ai/fast - that's cups.fast.ai/fast -  
13:12
and don't do this if you're, like, a fast.ai  expert who's done the course five times - because  
13:18
if you're following along that doesn't really mean  much obviously. This is really for people who are,  
13:23
you know, not already fast.ai experts.  And so click one of these colored buttons.
13:30
And what I will do, is I will go to the teacher  version and see what buttons you're pressing.  
13:38
All right! So, so far people are feeling we're  not going too fast on the whole. We've got one,   nope not one, brief red. Okay! So, hey Nick,  this url, the same thing with teacher on the end,  
13:52
if you can you keep that open as well and let  me know if it suddenly gets covered in red.  
13:59
If you are somebody who's red, I'm not going  to come to you now because there's not enough  
14:07
of you to stop the class. So it's up to you to  ask on the forum or on the youtube live chat,  
14:14
and there's a lot of folks luckily  who will be able to help you, I hope. All right! I wanted to do a big shout out  to Radek. Radeck created cups.fast.ai for  
14:29
me. I said to him last week I need a way  of seeing coloured cups on the internet   and he wrote it in one evening. And  I also wanted to shout out that Radek  
14:41
just announced today that he got a job at  Nvidia AI and I wanted to say, you know,   that fast.ai alumni around the world very  very frequently, like every day or two,  
14:52
email me to say that they've got their dream job.  Yeah… If you're looking for inspiration on how to  
15:01
get into the field I couldn't recommend nothing…  nothing would be better than checking out Radek's  
15:07
work. And he's actually written a book about his  journey. It's got a lot of tips in particular   about how to take advantage of fast.ai -  make the most of these lessons. And so I  
15:16
would certainly… so check that out as well. And  if you're here live he's one of our TAs as well   so you can say hello to him afterwards.  He looks exactly like this picture here.
15:28
So I mentioned I spent a lot of time studying  education both for my home schooling duties  
15:34
and also for my courses, and you'll see  that there's something a bit different,  
15:39
very different, about this course… which is that  we started by training a model. We didn't start  
How the course will be taught. Top down learning
15:45
by doing an in-depth review of linear algebra  and calculus. That's because two of my favorite  
15:53
writers and researchers on education Paul Lockhart  and David Perkins, and many others talk about how  
15:59
much better people learn when they learn with  a context in place. So the way we learn math  
16:06
at school where we do counting and then adding  and then fractions and then decimals and then  
16:12
blah blah blah and you know, 15 years later  we start doing the really interesting stuff  
16:18
at grad school. That is not the way most people  learn effectively. The way most people learn  
16:24
effectively is from the way we teach sports, for  example, where we show you a whole game of sports.  
16:32
We show you how much fun it is. You go and  start playing sports, simple versions of them,   you're not very good right and then you  gradually put more and more pieces together.  
16:41
So that's how we do deep learning. You will go  into as much depth as the most sophisticated,  
16:52
technically detailed classes you'll find - later,  right! But first you'll learn to be very very good  
17:01
at actually building and deploying models. And you  will learn why and how things work as you need, to  
17:10
get to the next level. For those of you that have  spent a lot of time in technical education (like   if you've done a phd or something) will find this  deeply uncomfortable because you'll be wanting to  
17:20
understand why everything works from the start.  Just do your best to go along with it. Those of  
17:25
you who haven't will find this very natural.  Oh! And this is Dylan Wiliam, who I mentioned   before - the guy who came up with the really cool  cups things. There'll be a lot of tricks that have  
17:38
come out of the educational research literature  scattered through this course. On the whole I   won't call them out, they'll just be there, but  maybe from time to time we'll talk about them.
17:47
All right! So before we start talking about how  we actually built that model and how it works,   I guess I should convince you that I'm worth  listening to. I'll try to do that reasonably  
17:57
quickly, because I don't like tooting my own  horn, but I know it's important. So the first  
18:03
thing I mentioned about me, is that me and my  friend Silvain wrote this extremely popular book  
18:08
“Deep Learning for Coders” and that book is what  this course is quite heavily based on. We're not  
18:14
going to be using any material from the book  directly, and you might be surprised by that,   but the reason actually is that the educational  research literature shows that people learn things  
18:24
best when they hear the same thing in multiple  different ways. So I want you to read the book  
18:30
and you'll also see the same information presented  in a different way, in these videos. So on,e of  
18:37
the bits of homework after each lesson will  be to read a chapter of the book. A lot of  
18:43
people like the book. Peter Norvig, Director of  Research, loves the book. In fact his ones here  
18:49
“one of the best sources for a programmer to  become proficient in deep learning.” Eric Topple  
18:55
loves the book. Hal Varian Emeritus Professor at  Berkeley, Chief Economist, Google, likes the book.  
19:01
Jerome Pecente who is the head of AI at Facebook  likes the book. A lot of people like the book, so  
19:08
hopefully you'll find that you like this material  as well. I've spent about 30 years of my life  
19:15
working in and around machine learning including  building a number of companies that relied on it.  
19:22
And became the highest ranked competitor in the  world on Kaggle in machine learning competitions.
Jeremy Howard’s qualifications
19:29
My company Enlitic, which I founded, was the  first company to specialize in deep learning for   medicine, and MIT voted it one of the 50 smartest  companies in 2016, just above Facebook and Spacex.  
19:44
I started fast.ai with Rachel Thomas and that  was quite a few years ago now, but it's had  
19:51
a big impact on the world already, including work  we've done with our students, has been globally  
20:00
recognized, such as our win in the DAWNBench  competition which showed how we could train big  
20:07
neural networks faster than anybody in the  world, and cheaper than anybody in the world.  
20:13
And so that was a really big step in 2018,  which actually made a big difference. Google  
20:21
started using our special approaches in  their models. Nvidia started optimizing  
20:28
their stuff using our approaches. So  it made quite a big difference there.  
20:34
I'm the inventor of the ULMFiT algorithm  which according to the Transformers book   was one of the two key foundations behind  the modern NLP revolution. This is the  
20:49
paper here. And actually, you know, interesting  point about that, it was actually invented for  
20:56
a fast.ai course. So the first time  it appeared was not actually in  
21:03
the journal. It was actually in lesson four   of the course, I think, the 2016  course, if I remember correctly.
21:15
And, you know, most importantly of course, I've  been teaching this course since Version One. And  
21:22
this is actually, I think, this is the very  first version of it (which even back then   was getting hbr's attention) a lot of people have  been watching the course, and it's been, you know,  
21:33
really widely used. Youtube doesn't show likes  anymore, so I have to show you our likes for you.  
21:41
You know it's been amazing to see how many  alumni have gone from this to, you know,  
21:52
to really doing amazing things, you know.  And so for example Andrej Karpathy told me  
21:59
that at Tesla, I think he said, pretty  much everybody who joins Tesla in AI   is meant to do this course. I  believe at OpenAI, they told me that  
22:07
all the residents joining there first do  this course. So this, you know this course,   is really widely used in industry and research  for people, and they have a lot of success.  
22:18
Okay, so there's a bit of brief information about  why you should hopefully keep going with this.
22:26
All right so let's get back to what's  happened here. Why are we able to create   a bird recognizer in a minute or two?  And why couldn't we do it before?  
Comparison between modern deep learning and 2012 machine learning practices
22:38
So I'm going to go back to 2012 and in 2012  this was how image recognition was done.  
22:46
This is the computational pathologist - it was  a project done at Stanford. A very successful,  
22:54
very famous project that was looking at the  five-year survival of breast cancer patients  
23:00
by looking at their histopathology image slides.  Now, so this is, like, what I would call a classic  
23:07
machine learning approach. And I spoke to  the senior author of this, Daphne Koller,  
23:12
and I asked her why they didn't use deep  learning and she said “well it just,   you know, it wasn't really on the radar at that  point.” So this is like a pre-deep-learning  
23:21
approach. And so the way they did this was they  got a big team of mathematicians and computer  
23:27
scientists and pathologists and so forth to get  together and build these ideas for features,   like relationships between epithelial nuclear  neighbors. Thousands and thousands actually they  
23:37
created of features, and each one required a lot  of expertise from a cross-disciplinary group of  
23:42
experts at Stanford. So this project took years,  and a lot of people, and a lot of code, and a lot  
23:48
of math. And then once they had all these features  they then fed them into a machine learning  
23:53
model - in this case, logistic regression, to  predict survival. As I say it's very successful,  
23:59
right, but it's not something that I could create  for you in a minute at the start of a course.  
24:06
The difference with neural networks is neural  networks don't require us to build these features.   They build them for us! And so what actually  happened was, in I think it was 2015,  
24:19
Matt Zeiler and Rob Fergus took a trained  neural network and they looked inside it  
24:26
to see what it had learned. So we don't give  it features, we ask it to learn features.  
Visualizing layers of a trained neural network
24:33
So when Zeiler and Zeiler looked inside a  neural network, they looked at the actual  
24:40
weights in the model and they drew a picture of  them. And this was nine of the sets of weights   they found. And this set of weights, for example,  finds diagonal edges. This set of weights finds  
24:52
yellow to blue gradients. And this set of weights  finds red to green gradients, and so forth, right.  
24:58
And then down here are examples of some bits of  photos which closely matched, for example, this  
25:06
feature detector. And deep learning, I  mean, is deep because we can then take  
25:13
these features and combine them  to create more advanced features.  
25:18
So these are some layer two features. So there's  a feature, for example, that finds corners.  
25:23
And a feature that finds curves.  And a feature that finds circles.   And here are some examples of bits of pictures  that the circle finder found. And so remember  
25:34
with a neural net which is the basic function used  in deep learning, we don't have to hand code any  
25:40
of these or come up with any of these ideas. You  just start with actually a random neural network  
25:47
and your feed it examples and you have it  learn to recognize things, and it turns out  
25:54
that these are the things that it creates for  itself. So you can then combine these features.
26:03
And when you combine these features it creates a  feature detector, for example, that finds kind of  
26:08
repeating geometric shapes. And it creates a  feature detector, for example, that finds kind of  
26:15
frilly little things, which it looks like is  finding the edges of flowers. And this feature  
26:21
detector here seems to be finding words. And so  the deeper you get the more sophisticated the  
26:29
features it can find are. And so you can imagine  that trying to code these things by hand would be,  
26:34
you know, insanely difficult, and you  wouldn't know even what to encode by hand,  
26:39
right! So what we're going to learn is how neural  networks do this automatically, right, but this  
26:45
is the key difference of why we can now do things  that previously we just didn't even conceive of as  
26:51
possible, because now we don't have to hand code  the features we look for. They can all be learned.
27:04
it's important to recognize we're going to  be spending some time learning about building   image based algorithms and image-based algorithms  are not just for images and in fact this is going  
27:16
to be a general theme. We're going to show you  some foundational techniques but with creativity  
27:22
these foundational techniques can be used very  widely. So for example, an image recognizer  
27:29
can also be used to classify sounds. So  this was an example from one of our students  
27:39
who posted on the forum and said for their  project they would try classifying sounds  
Image classification applied to audio
27:44
and so they basically took sounds and  created pictures from their waveforms  
27:50
and then they used an image recognizer on that  and they got a state-of-the-art result by the way.
27:55
Another of our students on the forum  said that they did something very similar   to take time series and turn them into  pictures and then use image classifiers.  
28:06
Another of our students created pictures  from mouse movements from... from users of  
Image classification applied to time series and fraud
28:13
a computer system. So the clicks became  dots and the movements became lines and   the speed of the movement became colors and  then used that to create an image classifier.
28:23
So you can see with... with some creativity  there's a lot of things you can do with images.
28:33
There's something else I wanted to point out which  is that as you saw when we trained a real working  
28:42
bird recognizer image model we didn't need lots  of math; there wasn't any. We didn't need lots of  
28:48
data. We had 200 pictures. We didn't need lots of  expensive computers; we just used my laptop. This  
28:55
is generally the case for the vast majority of  deep learning that you'll need in... in real life.
29:05
There will be some math that pops up during this  course but we will teach it to you as needed or  
29:11
we'll refer you to external resources as...  as needed but it'll just be the little bits   that you actually need. You know the myth that  deep learning needs lots of data, I think, is  
29:22
mainly passed along by big companies that want to  sell you computers to store lots of data and to  
29:29
process it. We find that most real world projects  don't need extraordinary amounts of data at all  
29:38
and as you'll see there's  actually a lot of fantastic   places you can do state-of-the-art work for  free nowadays which is... which is great news.
29:50
One of the key reasons for this is because  of something called transfer learning   which we'll be learning about a lot during  this course and it's something which  
29:59
very few people are aware of the pay-off. In this course we'll be using Pytorch. For  those of you who are not particularly close  
30:11
to the deep learning world, you might have  heard of Tensorflow and not of Pytorch.  
Pytorch vs Tensorflow
30:17
You might be surprised to hear that Tensorflow  has been dying in popularity in recent years  
30:26
and Pytorch is actually growing rapidly and in…  in research repositories amongst the top papers,  
30:40
Tensorflow is a tiny minority now  compared to Pytorch. This is also   great research that's come out from Ryan  O'Connor. He also discovered that...
30:52
the majority of people that were doing Tensorflow  in 2018 researchers, the majority have now shifted  
30:59
to Pytorch and I mention this because what people  use in research is a very strong leading indicator  
31:06
of what's going to happen in industry because  this is where you know all the new algorithms   are going to come out. this is where all  the papers are going to be written about.  
31:14
it's going to be increasingly difficult to use  Tensorflow. We've been using Pytorch since before  
31:20
it came out, before the initial release because  we knew just from technical fundamentals, it was  
31:25
far better. So this course has  been using Pytorch for a long time.   I will say however that Pytorch requires a lot of  hairy code for relatively simple things. This is  
31:37
the code required to implement a particular  optimizer called AdamW in plain Pytorch.  
Example of how Fastai builds off Pytorch (AdamW optimizer)
31:43
I actually copied this code from the Pytorch  repository so as you can see there's a lot of it.
31:51
This gray bit here is the code required to do the  same thing with fast.ai. fast.ai is a library we  
31:59
built on top of Pytorch. This huge difference  is not because Pytorch is bad. It's because  
32:06
Pytorch is designed to be a strong foundation  to build things on top of, like fast.ai. So...
32:15
When you use fast.ai - the library, you get  access to all the power of Pytorch as well but  
32:23
you shouldn't be writing all this code if you only  need to write this much code, right? The problem  
32:28
of writing lots of code is that that's lots of  things to make mistakes with, lots of things to,   you know, not have best practices in, lots of  things to maintain. In general we've found,  
32:39
particularly with deep learning: less  code is better. Particularly with fastai,  
32:46
the code you don't write is code that we've  basically found kind of best practices   for you. So when you use the code that we've  provided for you, you know you'll generally  
32:56
find you get better results. So... so fast.ai has  been a really popular library and it's very widely  
33:05
used in industry, in academia, and in teaching  and as we go through this course we'll be seeing  
33:14
more and more pure Pytorch as we get deeper and  deeper underneath to see exactly how things work.
33:22
The fast.ai library just won the 2020  best paper award for the paper about it   in Information so again you can see it's  a very well regarded library. Okay so…
33:37
Okay we're still green, that's good.   So you may have noticed something interesting,  which is that I'm actually running code  
33:48
in these slides. That's because these slides  are not in PowerPoint. These slides are in a  
33:57
Jupyter notebook. Jupyter notebook is the  environment in which you will be doing  
34:04
most of your computing.  It's a web-based application  
34:12
which is extremely popular and widely used  in industry and in academia and in teaching  
34:20
and it is a very very very powerful way  to to experiment and explore and to build.
34:30
Nowadays I would say most people at least  most students run jupyter notebooks not on  
34:38
their own computers particularly for  data science but on a cloud server  
34:43
of which there's quite a few and as I  mentioned earlier if you go to course.fast.ai  
34:51
you can see how to use various  different cloud servers.
34:59
One I'm going to show an example of is Kaggle.  So Kaggle doesn't just have competitions but it  
35:07
also has a cloud notebook server and  I've got quite a few examples there.
Using cloud servers to run your notebooks (Kaggle)
35:18
So let me give you a quick example of  how we use Jupyter notebooks. To... to...  
35:25
to build stuff, to... to experiment, to explore.  So on kaggle, if you start with somebody else's  
35:30
notebook... so why don't you start with this one  Jupyter notebook 101. If it's your own notebook  
35:36
you'll see a button called edit. If it's somebody  else's, that button will say copy and edit.  
35:42
If you use somebody's notebook that  you like, make sure you click the   upvote button to encourage them  and to help other people find it  
35:49
before you go ahead and copy and edit. And  once we're in edit mode we can now use this  
35:57
notebook and to use it we can type in any  arbitrary expression in python and click run  
36:05
and the very first time we do that it says  session is starting it's basically launching   a virtual computer for us to  run our code. This is all free.
36:15
In a sense, it's like the world's most powerful  calculator. It's a calculator where you have  
36:22
all of the capabilities of the world's I think  most popular programming language – certainly it  
36:28
and javascript would be the top two – directly  at your disposal. So, python does know how to  
36:34
do one plus one, and so you can see here it spits  out the answer. I hate clicking I always use  
36:39
keyboard shortcuts so instead of clicking this  little arrow, you just press shift enter to do   the same thing but as you can see there's  not just calculations here, there's also  
36:51
prose, and so jupyter notebooks are great  for explaining to you the version of yourself  
36:57
in six months time, what on earth you were  doing, or to your co-workers, or the people   in the open source community, or the people  you're blogging for etc, and so you just type  
37:06
prose, and as you can see when we create a new  cell, you can create a code cell which is a cell  
37:13
that lets you type calculations, or a markdown  cell which is a cell that lets you create prose.
37:24
And the prose uses formatting in a little mini  language called “markdown”. There's so many   tutorials around I won't explain it to you but  it lets you do things like links and so forth.
37:40
So I'll let you follow through the tutorial in  your own time because it really explains to you  
37:46
what to do. One thing to point out is that  sometimes you'll see me use cells with an   exclamation mark at the start. That's  not Python, that's a bash shell command,  
37:57
okay? so that's what the exclamation mark means.
38:02
As you can see you can put images into notebooks,  and so the image I popped in here was the one   showing that Jupyter won the 2017 software  system award which is pretty much the biggest  
38:12
award there is for this kind of software. Okay,  so that's the basic idea of how we use notebooks.
38:25
So let's have a look at how we  do our bird or not bird model.
38:36
One thing I always like to do when I'm  using something like colab or kaggle cloud,   cloud platforms that I'm not controlling is, make  sure that I'm using the most recent version of any  
Bird or not bird? & explaining some Kaggle features
38:45
software. So my first cell here is exclamation  mark pip install minus u , (that means upgrade)  
38:52
q (for quiet) fast.ai. So that makes sure  that we have the latest version of fast.ai,  
38:57
and if you always have that at the start of  your notebooks you're never going to have those   awkward forum threads where you say  “why isn't this working?” and somebody  
39:04
says to you “oh you're using an  old version of some software!”
39:09
So, you'll see here this notebook   is the exact thing that I was showing  you at the start of this lesson,
39:21
So, if you haven't done much python, you might  be surprised about how little code there is here,  
39:34
and so python is a concise but not too  concise language. You'll see that there's less  
39:42
boilerplate than some other languages you might  be familiar with, and I'm also taking advantage  
39:47
of a lot of libraries so fast.ai provides a lot of  convenient things for you. Oh I forgot to import…
40:00
So, to use a external library we use  import to “import a symbol from a library”.  
40:11
fast.ai has a lot of libraries we  provide. They generally start with   “fast something” so for example to make it  easy to download a url, “fastdownload” has  
How to import libraries like Fastai in Python
40:19
download_url(). To make it easy to create a  thumbnail, we have Image.to_thumb() and so forth.
40:30
So, I always like to view – as I'm building a  model – my data at every step. So that's why  
40:38
I first of all grab one bird, and then I  grab one forest photo, and I look at them  
Best practice - viewing your data between steps
40:45
to make sure they look reasonable. And once I think, “okay they look  okay”, then I go ahead and download.
40:58
And, so, you can see fast.ai has  a download_images() where you just   provide a list of urls so that's how easy it is,  and it does that in parallel. So it does that,  
41:09
you know, surprisingly quickly. One other fast.ai  thing I'm using here is resize_images(). You  
41:17
generally… you'll find that for computer vision  algorithms you don't need particularly big images,  
41:23
so I'm resizing these to a maximum size length  of 400 because it just… it's actually much faster  
41:30
because gpus are so quick for big images, most  of the time can be taken up just opening it.  
41:37
The neural net itself often takes less time. So  that's another good reason to make them smaller.
41:45
Okay, so the main thing I wanted to tell you about  was this data block command. So the data block  
41:52
is the key thing that you're going to want to get  familiar with as deep learning practitioners at   the start of your journey because the main thing  you're going to be trying to figure out is how do  
Datablocks API overarching explanation
42:04
I get this data into my model? Now that might  surprise you. You might be thinking we should  
42:10
be spending all of our time talking about neural  network architectures, and matrix multiplication  
42:16
and gradients and stuff like that, the truth is  very little of that comes up in practice, and the  
42:24
reason is, that at this point the deep learning  community has found a reasonably small number of  
42:32
types of model that work for nearly  all the main applications you'll need;  
42:40
and fast.ai will create the right type of  model for you the vast majority of the time.  
42:46
So all of that stuff about tweaking neural  network architectures and stuff… I mean  
42:53
we'll get to it eventually in this course  but you might be surprised to discover that  
42:58
it almost never comes up. Kind of like if you ever  did like a computer science course or something  
43:03
and they spent all this time on the details of  compilers and operating systems, and then you  
43:09
get to the real world and you never use it again.  So this course is called practical deep learning,  
43:14
and so we're going to focus on the  stuff that is practically important.   Okay, so our images have finished downloading, and  two of them were broken so we just deleted them.
43:29
Another thing you'll note by the way if you're   a keen software engineer is, I tend  to use a lot of functional style in my  
43:38
programs I find for kind of the kind of work I do  that a functional style works very well if you're,  
43:46
you know a lot of people in python are less  familiar with, that it's more, maybe comes,   more from other things. So yeah that's why you'll  see me using stuff like map and stuff quite a lot.
43:56
Alright so a data block is the  key thing you need to know about   if you're going to know how to  use different kinds of data sets,  
44:04
and so these are all of the things,  basically, that you'll be providing.   And so what we did when we designed the data  block was we actually looked and said “okay over  
44:15
hundreds of projects what are all the things that  change from project to project to get the data  
44:22
into the right shape”?, and we realized we could  basically split it down into these five things.  
44:28
So the first thing that we tell fast.ai is “what  kind of input do we have”?, and so then, so there  
44:34
are lots of blocks in fast.ai for different kinds  of inputs so we said “ah, the input is an image!;  
Datablocks API parameters explanation
44:40
“what kind of output is there?”, “what  kind of label?.” The output's a category,   so that means it's one of  a number of possibilities.  
44:49
So that's enough for fast.ai to know  what kind of model to build for you.
44:55
So what are the items in this model? what  am I actually going to be looking at to look   to train from? this is a function! In fact  you might have noticed if you were looking  
45:04
carefully that we use this function here.   It's a function which returns a list of all of  the image files in a path based on extension,  
45:16
so every time it's going to try and find out  what things to train from, it's going to use   that function. In this case we'll get a list of  image files. Something we'll talk about shortly is  
45:26
that it's critical that you put aside some data  for testing the accuracy of your model that's  
45:32
called a “validation set.” It's so critical that  fast.ai won't let you train a model without one,  
45:40
so you actually have to tell it  how to create a validation set,   how to set aside some data, and in this case  we say “randomly, set aside 20% of the data.”  
45:53
Okay, next question, then you have to tell  fast.ai is “how do we know the correct label  
46:00
of a photo”, how do we know if it's a bird photo  or a forest photo? and this is another function,  
46:08
and this function simply returns the parent  folder of of a path and so in this case we  
46:17
saved our images into either forest or bird. So  that's where the labels are going to come from
46:26
And then finally,   most computer vision architectures need all of  your inputs as you train to be the same size,  
46:37
so “item transforms” are all of the bits  of code that are gonna run on every item,  
46:44
on every image in this case, and we're saying  okay we want you to resize each of them to being  
46:51
192 by 192 pixels. There's two ways  you can resize: you can either crop out  
46:57
a piece in the middle, or you can squish  it, and so we're saying “squish it”.
47:05
So that's the data block that's all that you  need, and from there we create an important  
47:11
class called data loaders. Data loaders are  the things that, actually, pytorch iterates  
47:17
through to grab a bunch of your data at a time.  The way it can do it so fast is by using a GPU  
47:24
which is something that can do thousands of things  at the same time and that means it needs thousands   of things to do at the same time so a data loader  will feed the training algorithm with a “bunch”  
47:36
of your images at once; in fact we don't call it  a bunch we call it a “batch” or a “mini batch”.
47:46
And so, when we say show “batch” that's actually  a very specific word in deep learning. It's  
47:54
saying show me an example of a batch of data  that you would be passing into the model,  
48:00
and so you can see showbatch gives you – tells  you – two things: the input which is the picture,  
48:06
and the label, and remember! the label  came by calling that function. So,  
48:15
when you come to building your own models  you'll be wanting to know what kind of splitters  
48:21
are there? what kinds of labeling functions  are there? and so forth what's wrong button  
48:27
you'll be wanting to know what kind of labeling  functions are there and what kind of splitters   are there and so forth and so docs.fast.ai is  where you go to get that information. Often the  
48:37
best place to go is to choose the tutorials. So  for example here's a whole data block tutorial,  
Where to find fastai documentation
48:46
and there's lots and lots of examples, so  hopefully you can start out by finding something   that's similar to what you want to do and see  how we did it, but then of course there's also  
48:59
the underlying api information  so here's data blocks!
49:06
Okay. How are we doing? Still doing good! Alright.
49:17
So at the end of all this we've got an object  called “dls” that stand for “data loaders”   and that contains iterators that pytorch can  run through to grab batches of randomly split  
49:31
out training images to train the model with,  and validation images to test the model with.
49:39
So now we need a model. The critical concept here in fastai is called  a “learner”. A “learner” is something which  
49:48
combines a model, which is, that is, the actual  neural network function we’ll be training,  
49:53
and the data we use to train it with; and  that's why you have to pass in two things:  
Fastai’s learner (combines model & data)
49:58
the data which is the data loaders  object, and a model. And so the model  
50:07
is going to be the actual neural network function  that you want to pass in, and as I said there's  
50:13
a relatively small number that basically  work for the vast majority of things you do.
50:21
If you pass in just a bare symbol  like this it's going to be one of   fast.ai's built-in models but  what's particularly interesting  
50:29
is that we integrate a wonderful library by Ross  Wightman called “timm” (the pytorch image models)  
50:36
which is the largest collection of computer vision  models in the world, and at this point fast.ai is  
Fastai’s available pretrained models
50:41
the first and only framework to integrate this.  So you can use any one of the pytorch image models  
50:49
and one of our students Amanamoro was kind  enough to create this fantastic documentation  
50:56
where you can find out all  about the different models.
51:02
And if we click on here, you can get lots and lots  of information about all the different models that  
51:10
Ross has provided. Having said that,  the model family called “resnet”  
51:19
are probably going to be fine for nearly all  the things you want to do, but it is fun to   try different models out so you can type in any  string here to use any one of those other models
51:35
Okay so if we run that, let's see what happens  okay? So this is interesting… So when I ran this…  
51:42
so, remember on kaggle it's creating a new   virtual computer for us, so it doesn't  really have anything ready to go,  
51:49
so when I ran this the first thing it did  was it said “downloading resnet18.pth”
51:56
What's that? well, the reason we can do this so  fast is, because somebody else has already trained  
What’s a pretrained model?
52:04
this model to recognize over 1 million  images of over 1 000 different types;  
52:11
something called the “ImageNet” dataset, and  they then made those weights available – those  
52:18
parameters– available on the internet for anybody  to download. By default on fast.ai when you  
52:26
ask for a model, we will download those weights  for you, so that you don't start with a random  
52:32
network that can't do anything. You actually  start with a network that can do an awful lot,  
52:38
and so, then something that fast.ai has,  that's unique, is this fine_tune method,  
52:43
which, what it does is: it takes those pre-trained  weights we downloaded for you, and it adjusts  
52:49
them in a really carefully controlled way  to just teach the model the differences  
52:56
between your data set, and what it was originally  trained for. That's called “fine tuning”;  
53:03
hence the name. So that's why you'll see this  downloading happen first, and so as you can  
53:10
see at the end of it, this is the error right  here after a few seconds it's a 100% accurate
53:21
So we now have a learner, and this learner  has been, has started with, a pre-trained  
53:27
model that's been fine-tuned for the purpose of  recognizing bird pictures from forest pictures.  
53:35
So you can now call dot predict on it, and dot  predict you pass in an image, and so this is  
53:45
how you would then deploy your model. So in  the code you have whatever it needs to do.  
Testing your model with predict method
53:53
So in this particular case this  person had some reason that he needs  
54:00
the app to check whether they're in the national  park, and whether it's a photo of a bird,   so at the vet where they need to know if  it's a photo of a bird it would just call  
54:08
this one line of code learn.predict();  and so that's going to return  
54:14
whether it's a bird or not as a string,  whether it's a bird or not as an integer, and   the probability that it's a non-bird or a bird;  and so that's why we can print these things out.
54:27
Okay so that's how we can  create a computer vision model.
54:37
What about other kinds of models? right? There's  a lot more in the world than just computer vision.  
54:43
A lot more than just image recognition.  Well even within computer vision,   there's a lot more than just  image recognition. For example,  
54:55
for example, there's segmentation!
55:03
So segmentation, maybe the best way to explain  segmentation is to show you the result of this   model. Segmentation is where we take photos –  in this case of road scenes – and we color in  
Other applications of computer vision. Segmentation
55:17
every pixel according to what it's a, what is  it. So in this case we've got brown as cars,  
55:24
blue is fences I guess?  red is buildings? or brown?
55:30
And so on the left here some photos that  some somebody has already gone through,  
55:36
and classified every pixel of, every one of these  images according to what that pixel is a pixel of,  
55:42
and then on the right is what our  model is guessing, and as you can see  
55:51
it's getting a lot of the pixels correct  and some of them it’s getting wrong.
55:57
It's actually amazing how many is getting  correct because this particular model  
56:07
I trained in about 20 seconds using a tiny, tiny,  tiny, amount of data. So you know, again, like,  
56:17
you would think this would be a particularly  challenging problem to solve, but it took about  
56:25
20 seconds of training to solve it, not amazingly  well, but pretty well. If I trained it for another  
56:31
two minutes it'd probably be close to perfect. So  this is called “segmentation”. Now you'll see that  
56:39
there's very, very, little data required, and …  sorry, very little CODE required, and the steps  
56:47
are actually going to look quite familiar. In fact  in this case we're using an even simpler approach.  
Segmentation code explanation
56:52
Earlier on, we used “data blocks”. Data blocks  are a kind of intermediate level very … flexible  
57:02
approach that you can take to handling almost any  kind of data, but for the kinds of data that occur  
57:08
a lot, you can use these special data loaders  classes which kind of lets you use even less code.
57:15
So, in this case, to create  data loaders for segmentation,   you can just say: “okay I'm going to pass you  in a function for labeling”; and you can see  
57:24
here it's got pretty similar things that we pass  in, to what we passed in for data blocks before.
57:31
So our file names is get_image_files()  again, and then our label function  
57:37
is something that grabs this path, and the codes.  So the labels for further segmentation, sorry,  
57:47
the codes. So, like, “what does each code  mean?” is going to be this text file, but  
57:52
you can see the basic information we're providing  is very very similar regardless of whether we're  
57:58
doing segmentation or object recognition; and  then the next steps are pretty much the same.
58:03
We create a learner for segmentation. We create,   so, we've got a UNet learner which we'll learn  about later, and then again, we call fine_tune()  
58:12
so that is it! and that's how  we create a segmentation model!
58:19
What about stepping away from computer vision?  So perhaps the most widely used kind of  
58:25
model used in industry is tabular analysis. So,   taking things like spreadsheets and database  tables, and trying to predict columns of those.
Tabular analysis with fastai
58:37
So, in tabular analysis, it really looks  very similar to what we've seen already,  
58:44
We grabbed some data and you'll see when I call  this untar_data(), this is the thing in fast.ai  
58:50
that downloads some data and decompresses it for  you and there's a whole lot of urls provided by   fast.ai for all the, kind of common data sets that  you might want to use; you know all the ones that  
59:00
are in the book? or lots of data sets that are  kind of widely used in learning and research?  
59:06
So, it makes life nice and easy for you. So  again, we're going to create data loaders,   but this time it's tabular data loaders, but we  provide pretty similar kind of information to what  
59:15
we have before. Couple of new things we have to  tell it. “Which of the columns are categorical?”  
59:20
so they can only take one of a few  values, and “which ones are continuous”   so they can take, basically, any real number,  and then again, we can use the exact same  
59:32
show_batch() that we've seen before, to  see the data, and so, fast.ai uses a lot of  
59:40
something called “type dispatch” which is a  system that's particularly popular in in a  
show_batch method explanation
59:45
language called Julia, to basically,  automatically, do the right thing   for your data, regardless of what kind of data it  is. So, if you call show_batch() on something you  
59:55
should go get back something “useful” regardless  of what kind of information you provided.   So for a table it shows you on the information in  that table. This particular data set is a data set  
1:00:08
of whether people have less than fifty thousand  dollars or more than fifty thousand dollars in  
1:00:14
salary for different districts based on  demographic information in each district.
1:00:23
So, to build a model for that  data loader, we do as always  
1:00:30
“something” underscore “learner”.  In this case it's a tabular learner.   Now this time we don't say: “fine_tune()”;  we say “fit”. Specifically, fit_one_cycle().  
1:00:40
That's because for tabular models, there's  not generally going to be a pre-trained model   that already does something like what you want,  because every table of data is very different,  
1:00:50
whereas pictures often have a similar theme,  you know? They're all pictures. They all have   the same kind of “general idea” of what  pictures are. So that's why it generally  
1:00:59
doesn't make too much sense to fine-tune  a tabular model. So instead, you just fit.  
1:01:06
So there's one difference there.  I'll show another example.
1:01:12
Okay, so, collaborative filtering.
1:01:20
“Collaborative filtering” is the basis  of most recommendation systems today.   It's a system where we basically take data set  that says: which users liked which products,  
Collaborative filtering (recommendation system) example
1:01:32
or which users used which products, and then we  use that to guess what other products those users  
1:01:39
might like based on finding similar users, and  what those similar users like. The interesting  
1:01:45
thing about collaborative filtering is that when  we say “similar users,” we're not referring to   similar demographically, but similar in the  sense of people who liked the same kinds of  
1:01:58
products. So, for example, if you use any of  the music systems like Spotify, or Apple music,  
1:02:05
or whatever, it'll ask you first, like, “what's  a few pieces of music you like,” and you tell it,  
1:02:13
and then it says “okay well maybe let's start  playing this music for you,” and that's how  
1:02:18
it works. It uses collaborative filtering. So  we can create a collaborative filtering data  
1:02:26
loaders in exactly the same way that we're used  to, by downloading and decompressing some data,  
1:02:33
create our collab data loaders. In  this case we can just save from csv,   and pass in a csv, and this is what collaborative  filtering data looks like. It's going to have,  
1:02:42
generally speaking, a user id, some kind of  product id; in this case, a movie, and a rating.
1:02:51
So, in this case this user gave  this movie a rating of 3.5 out of 5,  
1:02:58
and so, again, you can see show_batch,  right? So use show batch. You should get back   some useful visualization of your data  regardless of what kind of data it is,  
1:03:10
and so again, we create a “learner.”   This time the “collaborative filtering”  learner, and you pass in your data.
1:03:20
In this case we give it one extra piece  of information, which is – because this   is not predicting a category, but it's  predicting a real number – we tell it:  
1:03:29
“what's the possible range.”  The actual range is one to five,  
1:03:34
but for reasons you'll learn about later, it's  a good idea to actually go from a little bit   lower than the possible minimum, to a little  bit higher. That's why I say 0.5 to 5.5,  
1:03:44
and then fine-tune. Now, again, you know we don't  really need to fine-tune here because there's not   really such a thing as a pre-trained collaborative  filtering model. We could just say “fit”  
1:03:52
or “fit_one_cycle”, but actually fine_tune() works  fine as well. So, after we train it for a while,  
1:04:00
this here is the “mean squared error”, so it's  basically, that: “on average how far off are we  
1:04:08
for the validation set”.  And you can see as we train,   and it's literally so fast (it's  less than a second each epoch)  
1:04:15
that error goes down and down, and for any kind of  fast.ai model you can always call show_results() ,  
1:04:29
and get something sensible. So in this case it's  going to show a few examples of users and movies.   Here's the actual rating that user gave that movie  and here's the rating that the model predicted.  
1:04:42
Okay, so, apparently a lot of people  on the forum are asking how I'm   turning this notebook into a presentation?
1:04:50
So, I'll be delighted to show you, because I'm  very pleased that these people made this thing   for free for us to use. It's called “Rise”,  and all I do is, it's a notebook extension,  
1:05:04
and in your notebook it gives you an extra little  thing on the side where you say which things are  
How to turn your notebooks into a presentation tool (RISE)
1:05:10
slides, or which things are fragments, and a  fragment just being… so, this is a slide, that's   a fragment. So if I do that you'll see it starts  with a slide and then the fragment gets added in.
1:05:24
Yeah, that's about all there is to it!  Actually it's pretty great, and it's very   well documented. You know I'll just mention,  like what do I make with Jupyter notebooks:  
1:05:39
this entire book was written  entirely in Jupyter notebooks.
What else can you make with notebooks?
1:05:47
Here are the notebooks. So if you go to the  fastai fastbook repo… if you go to the fastai   fastbook repo, you can read the whole book, and  because it's all in notebooks, every time we say:  
1:06:00
“here's how you create this plot,” or “here's  how you train this model,” you can actually   create the plot, or you can actually train  the model, because it's all notebooks.
1:06:14
The entire fast.ai library is  actually written in notebooks.   So you might be surprised to discover  that if you go to fast.ai fast.ai  
1:06:26
that the source code for the  entire library is notebooks,  
1:06:38
and so the nice thing about this  is that, you know, the source code   for the fast.ai library has actual pictures of  the actual things that we're building for example.
1:06:51
What else have we done with notebooks? oh! blogging!
1:06:58
I love blogging with notebooks, because  when I want to explain something  
1:07:03
I just write the code, and you can just  see the outputs, and it all just works.  
1:07:12
Another thing you might be surprised by, is  all of our tests and continuous integration   are also all in notebooks. So every  time we change one of our notebooks…  
1:07:27
every time we change one of our notebooks,  hundreds of tests get run automatically,  
1:07:35
in parallel, and if there's any issues  we will find out about it. So, yeah,  
1:07:41
notebooks are great! and rise is… is a  really nice way to do slides in notebooks.
1:07:51
Alright. So, what can deep learning do at present?  
1:08:00
We're still scratching this the tip of the iceberg  even though it's a pretty well hyped you know  
1:08:05
heavily marketed technology this pro… you  know when we started in 2014 or so, you know,  
What can deep learning do presently?
1:08:14
not many people were talking about deep learning,  and really there was no accessible way to get  
1:08:20
started with it. There were no pre-trained  models you could download, you know. There  
1:08:26
was just starting to appear some of the first  open source software that would run on gpus,  
1:08:33
but yeah, I mean, but despite the fact that  today there's a lot of people talking about deep   learning, we're just scratching the surface.  Every time pretty much somebody says to me  
1:08:41
I work in domain x, and I thought I might  try deep learning out to see if it can help,  
1:08:47
and I see them a few months later,  and I say “how did it go?” they   nearly always say: “well we just broke the  state-of-the-art results in our field.”  
1:08:54
So, you know, when I say these are things that  it's currently state of the art for – these are   kind of the ones that people have tried so far  – but still, most things haven't been tried.
1:09:02
So, in NLP, deep learning is the state of the art   method in all these kinds of things and a  lot more; computer vision, medicine, biology  
1:09:21
recommendation systems, playing games, robotics…  I mean it's just… I've tried… I've tried elsewhere  
1:09:28
to make bigger lists, and I just end up with  pages and pages and pages! so yeah it's… it's  
1:09:36
generally speaking you know, if it's something  that a human can do reasonably quickly,  
1:09:44
like look at a go board and  decide if it looks like a good   go board or not, even if it needs to be an  ex even… if it needs to be an expert human,  
1:09:53
then that's probably something that  deep learning will be pretty good at.   If it's something that takes a lot of logical  thought processes over an extended period of time,  
1:10:04
you know, particularly if it's not based  on much data, maybe not. You know, like,  
1:10:11
“who's going to win the next election”, or  something like that. That'd be kind of broadly   how I try to decide: is your thing useful for  deep… you know, good for deep learning or not.  
1:10:21
You know it's been a long  time to get to this point. Yes, deep learning is incredibly powerful now,  but it's taken decades of work. This was the first  
1:10:32
neural network. Remember, neural networks are the  basis of deep learning. So this was back in 1957.  
The first neural network - Mark I Perceptron (1957)
1:10:41
The basic ideas have not changed much at all,  but you know we do have things like gpus now,  
1:10:51
and solid-state drives, and stuff like that,  and of course much more data, just is available,  
1:10:57
now, but this has been decades of really hard  work by a lot of people to get to this point.
1:11:11
So let's kind of take a step back, and  talk about, like, what's what's going on  
1:11:18
in these models, and I'm going to describe  the basic idea of machine learning  
1:11:26
largely as it was described by Arthur  Samuel in the late 50s when it was invented,  
1:11:33
and I'm going to kind of do it with  these graphs; oh which, by the way,  
1:11:40
you might find fun… these graphs are themselves…  
1:11:52
created with Jupyter notebooks. So these are  graphviz descriptions that are going to get   turned into these, so there's a little  sneak peek behind the scenes for you?
1:12:03
So, let's start with kind of a graph of, like,  well, what does a normal program look like? right?   so, in the pre deep learning, and machine learning  days, well, you know, you'd have… you still have  
1:12:12
inputs, and you still have results. Right? and  then you code a program in the middle, which is,   you know, a bunch of conditionals, and loops,  and setting variables, and blah blah blah. Okay.  
1:12:24
A “machine learning model”  doesn't look that different…
1:12:30
but… The program has been replaced with something  called “a model,” and we don't just have inputs  
Machine learning models at a high level
1:12:38
now, we now also have weights, which are also  called “parameters,” and the key thing is this:  
1:12:44
the model is not any more a bunch of  conditionals, and loops, and things.
1:12:50
It's a mathematical function. In the case of a neural network, it's a  mathematical function that takes the inputs,  
1:12:58
multiplies them together by the weights –  by one set of weights – and adds them up;   and then it does that again for a  second set of weights and adds them up,  
1:13:05
does it again for a third set of  weights, and adds them up and so forth. It then takes all the negative  numbers, and replaces them with zeros,  
1:13:14
and then it takes those as inputs to  the next layer. It does the same thing;   multiplies them a bunch of times, and adds  them up, and it does that a few times,  
1:13:23
and that's called “a neural  network.” Now, the model  
1:13:30
therefore, is not going to do anything useful,  unless these weights are very carefully chosen.
1:13:36
And, so the way it works is, that we actually  start out with these weights as being   random. So initially, this thing  doesn't do anything useful at all!
1:13:52
So, what we do –- the way arthur samuel  described it back in the late 50s   (the inventor of machine learning) – is,  he said: “okay, let's take the inputs,  
1:14:01
and the weights, put them through our  model.” He wasn't talking particularly   about neural networks. He's just  like… whatever model you like…
1:14:09
get the results, and then let's decide how  “good” they are, right? So, if for example,  
1:14:16
we're trying to decide: “is this a picture of  a bird?” and the model said – which initially  
1:14:22
is random – says “this isn't a bird,” and actually  it IS a bird, we would say: “oh you're wrong!” So  
1:14:27
we then calculate “the loss.” So, the loss is  a number that says how good were the results.
1:14:35
So that's all pretty straightforward, you  know. We could, for example, say oh what's   the accuracy? We could look at 100 photos and  say which percentage of them did it get right.  
1:14:43
No worries. Now the critical step is this  arrow. We need a way of updating the weights  
1:14:52
that is coming up with a new set of weights  that are a bit better than the previous set.  
1:14:57
Okay. And by a bit better we  mean it should make the loss  
1:15:03
get a little bit better. So we've got this  number that says how good is our model and  
1:15:09
initially it's terrible, right? It's random. We  need some mechanism of making a little bit better.
1:15:15
If we can just do that one thing   then we just need to iterate this a few times.  Because each time we put in some more inputs  
1:15:24
and... and put in our weights and get our loss  and use it to make it a little bit better,  
1:15:29
then if we make it a little bit better enough  times, eventually it's going to get good.  
1:15:34
Assuming that our model is flexible enough to  represent the thing we want to do. Now remember  
1:15:41
what I told you earlier about what a neural  network is: which is basically multiplying things   together and adding them up and replacing the  negatives with zeros and you do that a few times,  
1:15:51
that is provably an infinitely flexible function. So it actually turns out that that incredibly  simple sequence of steps, if you repeat it a  
1:16:02
few times, you do enough of them, can solve any  computable function. And something like generate  
1:16:13
an artwork based off somebody's twitter bio  is an example of a computable function, right?  
1:16:21
Or translate English to Chinese is an example  of a computable function. So they're not the  
1:16:28
kinds of normal functions you do in year eight  math right but they are computable functions.  
1:16:35
and so therefore if we can just create this step  then and use the neural network as our model  
1:16:45
then we're good to go. In theory we can solve  anything given enough time and enough data  
1:16:53
and so that's exactly what we do. And so once we've finished that training procedure  
1:17:04
we don't need the loss anymore and even the  weights themselves, we can integrate them,  
1:17:09
kind of into the model, right? We finish  changing them so we can just say that's now fixed   and so once we've done that we now  have something which takes inputs,  
1:17:18
puts them through a model and gives us results. It  looks exactly like our original idea of a program  
1:17:26
and that's why we can do what I described earlier,  that is once we've got that learn.predict for our  
1:17:33
bird recognizer we can insert it into any piece  of computer code, right? Once we've got a trained  
1:17:38
model it's just another piece of code we can  call with some inputs and get some outputs.
1:17:47
Deploying machine learning models in practice  can come with a lot of, you know, little tricky  
1:17:56
details but the basic idea in your code is that  you're just going to have a line of code that says  
1:18:01
learn.predict and then you just fit it in with  all the rest of your code in the usual way.   And this is why: because a trained model is  just another thing that maps inputs to results.
1:18:15
Okay. All right. so as we come to  wrap up this first lesson,  
1:18:25
for those of you that are already familiar with  notebooks and Python, there's... you know... this  
Homework
1:18:31
has got to be pretty easy for you. You're just  going to be using some stuff that you're already  
1:18:37
familiar with and some slightly new libraries.  For those of you who are not familiar with Python,  
1:18:42
you know, you... you're biting into a big thing  here. There's obviously a lot you're going to  
1:18:47
have to learn and to be clear I'm... I'm not  going to be teaching Python in this course  
1:18:54
but we do have links to great python resources in  the forum. So check out... check out that thread.  
1:19:03
Regardless of where you're at, the most important  thing is to experiment and so experimenting  
1:19:12
could be as simple as just running those Kaggle  notebooks that I've shown you just to see them  
1:19:19
run. You could try changing things a little bit.  I'd really love you to try doing the... the bird  
1:19:26
or forest exercise but come up with something  else. Maybe try to use three or four categories  
1:19:31
rather than two, you know. Have a think about  something that you think would be fun to try.
1:19:38
Depending on where you're at, you know, push  yourself a little bit but not too much. So make  
1:19:43
sure you get something finished before the next  lesson. Most importantly, read chapter one of the  
1:19:50
book. It's got much the same stuff that we've seen  today but presented in a slightly different way.  
1:19:57
And then come back to the forums and present  what you've done in the share your work here  
1:20:03
thread. After the first time we  did this in year one of the course  
1:20:10
we got over a thousand replies and of  those replies it's amazing how many  
1:20:15
of them have ended up turning into new  startups, scientific papers, job offers.
1:20:23
It's been really cool to watch people's journeys  and some of them are just plain fun, you know. So   this person classified different types of  Trinidad and Tobago people. So you know,  
1:20:32
people do stuff based on where they  live and what their interests are.   I don't know if this person is particularly  interested in zucchini and cucumber but they  
1:20:39
made a zucchini and cucumber classifier. I  thought this was a really interesting one:   classifying satellite imagery into what city  it's probably a picture of. Amazingly accurate  
1:20:49
actually. 85 percent with 110 classes. Panama  city bus classifier. Batik cloth classifier.  
1:20:58
This one, you know, very practically important,  you know, recognizing the state of buildings.  
1:21:04
We've had quite a few students actually move into  disaster resilience based on satellite imagery   using exactly this kind of work. We've already  actually seen this example. Ethan Sutin the... the  
1:21:15
sound classifier and I mentioned it was  state of the art. He actually checked up the  
1:21:20
dataset's website and found that he beat the state  of the art for that. Alena Harley did tumor-normal  
1:21:27
sequencing. So she was at Human Longevity  International. So she actually did three   different really interesting pieces of cancer work  during that first course if I remember correctly.  
1:21:38
And I showed you this picture before. What I  didn't mention is actually this... this student   Gleb was a software developer at Splunk, a big  NASDAQ listed company. And this student project  
1:21:51
he did turned into a new patented product at  Splunk and a big blog post and the whole thing  
1:21:56
turned out to be really cool. Basically something  to identify fraudsters using image recognition  
1:22:03
with these pictures we discussed. One of our  students built this startup called Envision.
1:22:11
Anyway there's been lots and lots of examples. So  all of this is to say, you know, have... have a go  
1:22:17
at you know, starting something. Create something  you think would be fun or or interesting and share  
1:22:24
it in the forum. If you're a total beginner  with Python, you know, then start... start  
1:22:30
with something simple. But I think you'll find  people very encouraging and if you've done this   a few times before then try to push yourself  a little bit further. And don't forget to look  
1:22:38
at the quiz questions at the end of the book  and see if you can answer them all correctly.
1:22:47
All right, thanks everybody, so much for coming.  Okay. Thanks so much for coming everybody. Bye.