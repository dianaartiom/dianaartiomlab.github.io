---
layout: default
title: MIDPS
---
##Laboratory Work No.4
So far we've already got to the forth laboratory work. The task of the last laboratory work was to prototype program, using the MVC(Model-View-Controller) pattern. In order to do this I proceeded to the following steps:

###Step 1:
Go to Rails Girls Chisinau and meet there the most WONDERFUL mentors:
<div class="custom-image"><img src="https://scontent-frt3-1.xx.fbcdn.net/t31.0-8/12633660_1718734505025428_643532896065342991_o.jpg" /></div>

###Step 2:
Learn here great stuff, and don't stop to their guide only, check whether they lie or not using the official Rails Documentation.

###Step 3:
Wait for three months, and start emotionally preparing for the forth laboratory work at IDE course.

###Step 4:
Procrastinate and let the whole work for the last week before deadline.

###Step 5:
Star the actual work.

##Work process
In the following lines I will explain the whole work flow of how the app was done.
<br />
The first step was making a new rails app. It took time to choose a name for it, but it seemed like "Green-Rainbow" is the guy I need. In order to create a new app I used the command
```$
$ rails new green-rainbow
```
It generated a project which structure looks like this:
<div class="custom-image"><img src="https://66.media.tumblr.com/871cc3286010a5d98c3f1a29e3cfa7a3/tumblr_o7fev8fzc01udztn8o1_400.png" /></div>

The following step, according to the tasks, was to simply add three static pages.
<ul>To do that, I created :
	<li>a landing page</li>
	<li>a page displaying the posts</li>
	<li>a login/sign up page(generated with devise) </li>
</ul>

Screenshots of these pages can be found below.

<div class="custom-image"><img src="https://66.media.tumblr.com/5a7f9f574f132729d30a0c10f7439b19/tumblr_o7flmb3wRw1udztn8o1_1280.png" /></div>


Moreover, my site should keep all site data in a database. <br />
In order to do that I used sqlite3 as database for Active Record. The table for the posts looks like this:
<div class="custom-image"><img src="https://65.media.tumblr.com/48d0a83c0a17b60717315acc3fcf042b/tumblr_o7ffwzvnBj1udztn8o1_500.png" /></div>

I AJAX Requests when adding a new post and when deleting one. Ajax (Asynchronous JavaScript and XML) is used as a mechanism for sending and retrieving data asynchronously (in the background). While XML can certainly be used with ajax, it is not limited to this format. The JSON format, for example, is more commonly used today, especially in the Rails community. There are significant advantages in using Ajax, which include better user interactivity. Ajax allows content on a page to be updated without having to re-render the entire page, making it a “seamless” experience. Thus, when pressing "Add new post" or "Delete" button the browser is not reloaded, but the newly created object is rendered.

<div class="custom-image"><img src="https://67.media.tumblr.com/58a33b08d2bfce2dde59c9b8bac7add2/tumblr_o7flimUF9O1udztn8o1_1280.png" /></div>

<br />

You can visit my <a href="https://github.com/dianaartiom/green-rainbow">Github account</a> to see the code.
P.S. Ask me to show a demo!

###Conclusion:
Basically, most of the things while performing this laboratory work were known. The interesting was the part with Ajax. I did't know what this is and that was fine. I've got something to learn, that made the lab more enjoying. So far, the thing I liked the most is that by using Ajax you can update content on the page without rendering the entire page. I got stuck in the beginning, but after a couple of sites the things shaped themselves to be a bit more clear. I liked the way it worked in the case of creating a post, that's why I decided add this feature to the "Delete" button. It was fun and I really enjoyed the lab.

<br />

While making a general description of the course - It was, imho, the most amazing course up to this moment. I really enjoyed doing labs, even if there were white nights. The word "enjoying" describes perfect my state while writing code for these labs. Keep hacking on and motivating others!

##Laboratory Work No.3

The task for the third laboratory work was to create a pomodoro like app. In order to perform this laboratory work I had to deal with learnig the basic android concencepts, the life cycle of an application, ect. The hardest part was ingnoring all the facebook, twitter and telegram notifications. But in the end, I did it! Yey!
<br />
The first step in order to create a super fancy pomodoro app, was to learn, to get into what android is, and how to eat it. Here I met Advik Kabir:

<div class="custom-image"><img src="http://vomzi.com/wp-content/uploads/2016/03/indian-gif-852.gif" /></div>
No, not this, the other one:
<div class="custom-image"><img src="http://s2.djyimg.com/n3/eet-content/uploads/2014/02/Indian-head-shake.gif" /></div>

The next step was to choose a fancy bakground for my app.
<br />
  The background of my app, looks as serious as the name of my app: "SeriousPomodoro".
<br />


In my project I have 2 classes  - `MainWindow` and `WorkingPomodoro`. The first class is responsible for the main window screen and the second class is responsible for another Intent in which I actually created the progress bar and the timer.

<br/>

For getting to the intent of the second screen I made a function :

To get the id of each UI object I used:

```progressBar=(ProgressBar)findViewById(R.id.progressBar);
        relaxBar=(ProgressBar)findViewById(R.id.progressBar2);
        relaxBar.getProgressDrawable().setColorFilter(
                Color.RED, android.graphics.PorterDuff.Mode.SRC_IN);
        start_timer=(Button)findViewById(R.id.button);
        stop_timer=(Button)findViewById(R.id.button2);
        textView1 = (TextView) findViewById( R.id.textViewTimer );
        status = (TextView) findViewById(R.id.workingStatus);
```

```
public void onGetFocusedButtonClicked(View view) {
        Intent getWorkingPomodoroIntent = new Intent(this, WorkingPomodoro.class) ;
        final int result = 1;

        getWorkingPomodoroIntent.putExtra("callingActivity", "MainActivity");
        startActivityForResult(getWorkingPomodoroIntent, result);

    }
```

The funcion responsible for TextView setting time and progressBar setting proggress whith timer is the following:

```
@Override
			 public void onTick(long millisUntilFinished) {
					 status.setText("Focus time");
					 textView1.setText(new SimpleDateFormat("mm:ss").format(new Date( millisUntilFinished)));
					 int progress = (int) (millisUntilFinished/1000);
					 progressBar.setProgress(progressBar.getMax()-progress);
			 }
```

The full code can be found on Github (See the link below).

<div class="custom-image"><img src="https://66.media.tumblr.com/3d95b05a3bd554e5656a5c216b9fe4f4/tumblr_o72zz02b2i1rl36tko2_1280.jpg" /></div>

As you see, I downloaded 2 different fonts, in order to make the app look better, and to make every user feel excited about the app.

<br />

A new intend was created in the second activity, were the actual "focus mode" can be reached.
<div class="custom-image"><img src="https://66.media.tumblr.com/31d8cd9446e5d06315235dd15b44e8bf/tumblr_o72zz02b2i1rl36tko1_1280.jpg" /></div>

The source code of the laboratory work can be found <a href="https://github.com/dianaartiom/pomodoro">here</a>.


###Conclusion:
In this laboratory work we developed(or better saying - initialised) our mobile programming skills. It was a great amount of information, for some of us maybe even challenging, but it was worth it. The things I liked the most was the project architecture. You're splitting your UI with your bussines logic, without even thinking you are doing it, an that's kinda cool. Another thing I got in touch with was multithreading. The first iteration my code contained multiple threads, but I decided I have to improve my threading experience first, and then present a lab with it inside. But anyway, I spend some days on trying to understand what this is for, how to use it, and I'm ready to try implementing. I still feel motivated to do tasks and to proceed to the next point in my laboratory work journey. =)
<br />
P.S. Ask me for an demo. :)


##Laboratory Work No.2

In this laboratory work we had to create a travelling in time machine. To perform this laboratory work I used the following equipment:
<ul>
	<li><div class="custom-image"><img src="https://41.media.tumblr.com/6d829fd1563557a0370daee8590c5366/tumblr_o5amuvS6vG1udztn8o1_540.jpg" /></li>
	<li>A tanc
	<div class="custom-image"><img src="https://40.media.tumblr.com/20df6436da8d2c865d198bfdeb226fcb/tumblr_o5ammmdfy21udztn8o1_1280.jpg" /></div>
	</li>
	<li>and will fill it with the fuel from <a href="https://www.youtube.com/watch?v=3t0VMJdJna0&nohtml5=False">BEMOL</a><div class="custom-image"><img src="https://40.media.tumblr.com/27688078468a0e47037e46b1c5954d41/tumblr_o5amt2dq2M1udztn8o1_1280.jpg" /></div>
	</li>
</ul>

[![Everything Is AWESOME](https://40.media.tumblr.com/e5f02efc09647d9100c3584e9e454671/tumblr_o5azlt3opU1udztn8o1_540.png)](https://www.youtube.com/watch?v=3t0VMJdJna0&nohtml5=False "Everything Is AWESOME")

Actually,I'm kidding))
We had to make a calculator.
The source code of the laboratory work can be found <a href="https://github.com/dianaartiom/calculator-laboratory">here</a>.

####How does my project look like?
Basically, the UI looks something like this:
<div class="custom-image"><img src="https://41.media.tumblr.com/575207e0eef7058265c874c1cb011641/tumblr_o5anolsljV1udztn8o1_400.png" /></div>

######This week I made it for the first time. I wrote JAVA!

####Work process
#####Core <br />
A "special" thing I would like to tolk about is the way I parsed the input string. In order to parse it, i worked with regular expressions. Here is an example of code I used:

```
String signRegex = "(\\+|\\-|\\*|\\/|sqrt|\\^)";
String floatingPointNumber = "(([-|+])?[0-9]+\\.?[0-9]*)";
String pattern = floatingPointNumber + signRegex + floatingPointNumber;
```
I created a pattern and used Matcher.
```
Pattern r = Pattern.compile(pattern);
Matcher m = r.matcher(string)[]
```
I worked with groups. I can explain. :)

But most of all, I would like to talk about the project structure. <br />
I decided to separate the project in two parts. One of the parts consists from "Business Logic", which means the part which is related to the "smart" part of the program. The second part is UI. Here the visual part was implemented. Actually, that was done in the following way: I made an artefact(JAR) of the Logic part and icluded in the newly created project, where I implemented the UI. Moreover, same procedure was done for the lastly created project. Thus, I obtained a JAR file runnable on more platforms.<br />

#####This week I did for the first time! I wrote JAVA!

The project structure looks like this: the Core and the Interface. The core contains the calculator logic. The Interface contains the UI - graphical/visual part of the calculator, with which the user will interract.
######What about the work flow?
Actually, that was done in the following way: I made an artefact(JAR) of the Logic part and icluded in the newly created project, where I implemented the UI. Moreover, same procedure was done for the lastly created project. Thus, I obtained a JAR file runnable on more platforms.<br />
Don't forget to visit my github repository to see the code. ;)

####Conclusion:
This laboratory work was really-really interesting. What made it so interesting to me? Of course writing the report and dividing the project in two parts - the gui and the logic tiers. This is my first java trial. I've never tried java, not even to write an app or something like that. At some point, I realized I've done bidlocode. So I decided I'll rewrite it from scratch. It was painfully, but I did it. Of course in the end I still obtained bidlocode, but at least it's less now(lines of code ) :D. It's really nice that what we learn at the course helps us to perform the laboratory work. What's really funny now is that now same task seems a lot more easier than it seemt two weeks ago, and that is, probably, a result. So what's the difference btw now and two weeks ago? Lots of lines of bidlocode were written, some coffee in minus and... my pc probably hates me for so many

```java -jar Core.jar 2^3+((3-4)^2)
```
like-previous terminal commands, project creations and so on. Even stackoverflow must be surprised on frequency I visited their site with, considering the bunch of questions I had.
Now I feel really motivated and challenged to proceed to the next laboratory work, and to do my best. :)


##Laboratory Work No.1
In this laboratory work we had to deal with installing a normal operating system, Ubuntu (Server), in VirtualBox. Basically it was nothing difficult. I installed VirtualBox using

```$
sudo apt-get install virtual-box
```

The next thing I've done was downloading the Ubuntu Server image and installing it in VirtualBox. Having the IP address I connected my machine to the virtual one, by using SSH. The following image describes my actions:

####Basic Level
<ul>
  <li>Connect to a server using SSH</li>

<div class="custom-image"><img src="https://41.media.tumblr.com/899664a9733a7cee10d252a68e3f60df/tumblr_o33y88mR9p1uix9buo2_1280.png" /></div>
</ul>
<br \>
####The next following 5 tasks describe the same image(addet below the tasks)  .
<ul>
  <li>Run at least 2 sample programs from provided HelloWorldPrograms set</li>
  See the screen attached, to verify the status of this task.
  <div class="custom-image"><img src="https://41.media.tumblr.com/5518e5d800a977f566654b8de863c744/tumblr_o3bnydRG9U1udztn8o1_400.png" /></div>
  <li>Initialize and make commit using a VCS, configure it</li>
</ul>
To initialize a repository, I used the following commands:

```$
git init
```

initializes a new repository.

```$
echo "#midps" >> README.md
```
makes the README file.

```$
git commit -m "Initial commit"
```
performs the first commit.

```$
git remote add origin https://someorigin...
```  
####Normal Level
<ul>
  <li>Create two branches.</li>
</ul>
To create a new branch I used the command:

```$
git branch branch-name
```
<ul>
  <li>Commit two different branches.</li>
</ul>
To commit from a different branch, one should move on dat branch, using the following command:

```$
git checkout branch-name
```
<br />
After performing the modifications, I used : <br />

```$
git add
git commit -m "Some message"
```
####Advanced Level
<ul>
  <li>Set a branch to track a remote origin on which you are able to push (ex. Github, Bitbucket or custom server)</li>
  <div class="custom-image"><img src="https://40.media.tumblr.com/35bf62dfcd175242452344052c62591b/tumblr_o3arjnRIeV1udztn8o1_500.png" /></div>
</ul>

####The next following 4 tasks describe the same image(addet below the tasks), from Advanced.
<ul>
  <li>Set a branch to track a remote origin on which you are able to push.</li>
  Already done before, using the command <br />
</ul>

  ```$
  git remote add origin blah blah...
  ```
<ul>
  <li>Reset a branch to previous commit.</li>
</ul>
  To reset the branch to the previous commit I used the command: <br />

  ```$
  git reset --hard  3517831ce1
  ```
  The "number" after the --hard is the commit SHA-1 key.
<ul>
  <li>Merge two branches.</li>
</ul>
  To commit two branches I used

  ```$
  git merge branch-name-to-commit-with
  ```
  command.
<ul>
  <li>Conflict solving between 2 branches</li>
</ul>
   Opened the file, made some changes, saved it. Then used

   ```$
   git add
   git commit -m "...."
   ```
</ul>
<div class="custom-image"><img src="https://40.media.tumblr.com/9703a24e1d368e80b8e6c1906d4b3b04/tumblr_o3arof4qwk1udztn8o1_540.png" /></div>

####Conclusion
Althought at the beginnig it seemed to be a quite difficult task, because I've never done it before, in the end I felt pretty comfortable to install Ubuntu on a virtual machine, to explore the VirtualBox itself, and to connect through SSH. Moreover, it somehow made me understand how different processes, with different meaning can run on the same machine without interrupting each other, without even knowing about each other. <br \>
The second part of the laboratory work was to play with some VCS. It is a very powerful tool for developers and not only. Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. It is widely used. Developers may wish to compare today’s version of some software with yesterday’s version or last year’s version. Since version control systems keep track of every version of the software, this becomes a straightforward task. Knowing the what, who, and when of changes will help with comparing the performance of particular versions, working out when bugs were introduced (or fixed), and so on. Any problems that arose from a change can then be followed up by an examination of who made the change and the reasons they gave for making the change.<br \>
######I used git. Git - because I used it before. I thought I kinda look like this...
<div class="custom-image"><img src="http://s.quickmeme.com/img/e0/e0d4afacba74c1b28ae4caad6f98e9d2d1689fe8e43dc1ee680214c75eb24e17.jpg" /></div>
because I knew how to

```$
git pull
```

```$
git clone
```

```$
git add .
```

```$
git commit -m "Write somethig, otherwise you`ll enter VIM and you`ll never EXIT!!!!"
```

```$
git push
```

and that`s all.

But... Umm, I then discovered

```$
git cherry-pick
```

and

```$
git rebase
```

and even more,

```$
git hooks
```

#####and basically I got the point:
<div class="custom-image"><img src="https://40.media.tumblr.com/6f6502d41b0f9d7ad730d64a482db9ac/tumblr_o3at2qykMJ1udztn8o1_540.jpg" /></div>
<div class="custom-image"><img src="https://41.media.tumblr.com/53246bb32ba50abbd457243da1dbbf77/tumblr_o3at27M65m1udztn8o1_540.jpg" /></div>
Well, so I decided to learn what
```$
git cherry-pick
```
 does. It is a very powerful feature. It allows us to choose a specific commit, to treat it as a cherry and to pick it. =))<br />
So what have I done?<br />
I made a new branch using the command:

```$
git branch branch1
```

Switched to it. Made some commits and, on master, picked one of the commits I needed unsing the command:

```$
git cherry-pick ue89fa456
```
For a better understanding, see the screenshots attached.
<div class="custom-image"><img src="https://40.media.tumblr.com/11446e3ed86fe802714619cc692063b6/tumblr_o3bn84qCEX1udztn8o2_1280.png" /></div>
<div class="custom-image"><img src="https://40.media.tumblr.com/cf37f77445391ab7cac98cc5416e8c97/tumblr_o3bn84qCEX1udztn8o1_1280.png" /></div>

Screens and images on how I done git rebase will come soon. :)
