**CS-255** Computer Graphics I Assignment<br/>
Date set : 5/2/2018;<br/>
Deadline : Friday 2nd March 2018 at 11:00<br/>
<br/>
Guidance: **A lot of guidance for this assignment will be given in the lectures**. Email J.O.Whittle@swansea.ac.uk with any questions. Unfair Practice: Do not copy code from colleagues, internet or other sources. You may discuss approaches together, but all coding must be your own. Presenting work other than your own at a viva is plagiarism and a recipe for disaster.<br/>
<br/>
Aims<br/>
Understand how an image is stored internally, and how to manipulate the image<br/>
Translate useful graphics algorithms into working code<br/>
Improve your programming skills<br/>
Understand that graphics can be useful to users (in this case within the medical context)<br/>
Work with a three-dimensional data set<br/>
Combine interaction with visual feedback<br/>
Practice presenting your work in a viva situation<br/>
<br/>
Files:<br/>
The supporting framework is written in Java. You may build on this framework. If you wish to carry out the coursework in a different language you may do so, but there will be no provided framework. The assignment is to be demonstrated in the departmental PC Lab (you may use your own laptop). You will be required to demonstrate your working program to me from the deadline onwards at times to be arranged. You will require several things to start the exercise:
1. A copy of the Java template – downloadable from blackboard. This demonstrates how to display and manipulate images, and also functions and procedures which will help you with the exercise.
2. A data set to operate on – CThead.

[Note: You should not redistribute this data set anywhere – you will not have permission to do that]<br/>
<br/>
Exercise:
1. Implement the following:
   - Display a slider to allow the user to move through slices arbitrarily (currently slice 76 is hardcoded)
   - Display front and side views in addition to the top view (with independent sliders for each view)
   - Perform maximum intensity projection [note the sliders will not affect this image (see guidance lectures if this does not make sense)]. Make sure your ray goes all the way to the back of the data set. (i.e. do not clip at 113 when it could go to 255).
2. Choose to implement 2 from the following list
   - Display thumbnail images for all slices of the data set (use your own resize function, do not use example internet code that writes to a file then reads it back in again – this will be plagiarism, and is an awful way to do it anyway). Some solutions include having an array of images (image pointers) or creating a very large array and filling it with the thumbnails.
   - Allow the image to be resized (you could fix the containing image to 512x512, and allow the user to resize the medical image to any size) – nearest neighbour sampling, bilinear sampling (write your own code – don’t use the java library/function to do the resize).
   - Perform histogram equalization on the data set (not on the images) when scaling from the signed short int range to the unsigned byte range. Do not use the image histogram equalisation function (from java library, or from my notes on image histogram equalisation). Do use the correct histogram equalisation that operates on the full source 3D data set as indicated and discussed in the lectures. Generally, students that do not attend (or understand) the lectures copy the simple image histogram equalisation and get zero here.
   - Render from a different view apart from the ones above (i.e. a view from 45o, which will require sub-voxel sampling, either nearest neighbour or trilinear sampling) (hard). This requires some (straightforward trigonometry, doing it in 3D using 4x4 matrices gives the best implementation, and is easier to program/understand if you are comfortable with 4x4 matrices.) See chapter “Three-dimensional Geometric and Modeling Transformations” in Hearn and Baker text book (ch. 11 in second edition, ch.9 in 4th edition). If you really want to impress – implement arcball rotation with mouse interaction. To be clear – rendering from a different view will achieve full marks. The additional suggestions of 4x4 matrices, and arcball are challenges with no attached marks.

Requirements:<br/>
Also see later. You will demonstrate your program working to me or a post-graduate at times to be arranged in the week of the deadline. You therefore need to have a comment with your name and student number at the top of your java files along with the declaration that it is your own work (if you have several files, place them in a ZIP – **do not include the data set**). The coursework is worth 30% of this module. There is only 1 coursework.<br/>
<br/>
Mark distribution:<br/>
See over for a breakdown. 50% will be awarded for the user interface and, 20% for the first question and 30% for the second question. If you don’t do the viva you will receive zero. The maximum marks you can receive for the viva and UI is the sum of the other parts.<br/>
<br/>
Plagiarism:<br/>
It’s so important, I’m going to say it again. Each year a student will try to present code they don’t understand – don’t be that student. A simple question like “Why did you do that” or “What does that do” should not stump you.<br/>
<br/>
<br/>
Computer Graphics Assignment<br/>
Marking scheme<br/>
Note, for Q4 of the first part and Q5 of the second part, you can only score a maximum of the total you have obtained in the previous parts. e.g. if you do Q1 and Q2 of the first part (24 marks), the maximum for Q4 is 24 marks. Also, if you cannot answer any questions about your code (or have limited understanding of it), the marks for those previous questions will be reduced (sometimes down to zero).<br/>
<br/>
First part [80 marks]
1. Has a slider been implemented correctly? [12 marks]
2. Can all three views be seen with independent sliders? [12 marks]
3. Has the maximum intensity projection been implemented correctly? [16 marks]
4. If the student has done at least 1 thing from above, does the student answer a suitable set of questions about their implementation and MIP? – e.g. What is the purpose of MIP, what is the algorithm for MIP, how is this implemented, how are the other parts implemented? [40 marks]. Deduct appropriate marks from 1-3 above if the student cannot describe their own code.

Second part [120 marks] (only your best 2 count)<br/>
1. Thumbnails: working visually [15 marks], additional functionality (e.g. click on a thumbnail to see it in the large window, or a good approach to coding (being able to deal with arbitrary numbers of slices) [15 marks]
2. Image resize: working visually [15 marks], additional functionality (e.g. bilinear interpolation to get a smoother image rather than nearest neighbour lookup) [15 marks]
3. Histogram equalization: Calculating the histogram correctly [15 marks], applying histogram equalization correctly [15 marks]
4. Different view: Work out and implement the equation to loop through the data set at an angle [25 marks]. Include tri-linear interpolation [5 marks]
5. If the student has done at least 1 from 1-4 above, does the student answer a suitable set of questions about their choice? [60 marks]. Deduct appropriate marks from 1-4 above if the student cannot describe their own code. If the student has done the hardest 1 and can describe their difficulties, award bonus marks.

Submission Procedure:<br/>
Submit the assignment through blackboard before the deadline. Demonstrate/viva your assignment after the deadline at times to be notified.<br/>
<br/>
The college policy for late submission will be used. The timestamp from Blackboard will be used. I will email students at their University account, so you must read this frequently during the term. You might not be able to demonstrate/viva if you submit late.<br/>
<br/>
If you have extenuating circumstances (documentation must be provided), we will not have a problem with making alternative arrangements.<br/>
<br/>
Java and Bytes<br/>
Java does not support the unsigned types (e.g. unsigned byte). Images store the red, green and blue values as unsigned bytes (0 to 255), therefore some problems can arise - e.g. a value of 255 can be interpreted as -1. In order to work around this problem, one needs to carry out a logical AND with a bit mask of 255 and correctly typecast the result to int. e.g. int red = image_byte[index]&255; The MIP function contains such an example.<br/>
<br/>
<br/>
FAQ<br/>
How do I submit through blackboard?<br/>
On blackboard, use the following menus (this might be out of date?):<br/>
Assignments->View/Complete Assignment: Graphics ->Attach local file ->Submit<br/>
<br/>
I see the error: “Please enter a valid file”<br/>
Perhaps you have a space in the name. Please move your file to a top level directory (e.g. c:\) and try submitting. If you still get problems, please ask at the library helpdesk.<br/>
<br/>
Why won’t you accept an emailed file?<br/>
I will delete emailed submissions. I have many students enrolled on this course. Blackboard provides a simple to use interface for accessing files – in a few clicks I can have a directory with sub-directories of student numbers, with your submission file in each directory. We also have to store assignments for 2 years after you leave so having them all in Blackboard allows me to do this in a simple way. It also timestamps assignment submissions (and you should receive a receipt).<br/>
<br/>
I’m not registered on blackboard for your course.<br/>
Send me your student number for me to add you.<br/>
<br/>
I’ve submitted the wrong version.<br/>
You can submit multiple times – I will mark the last version.<br/>
<br/>
I cannot be available at the University on the days set aside for the viva.<br/>
Of course, we are fully sympathetic for extenuating circumstances (documentation must be provided). If you are absent for a trivial reason (e.g. holiday), firstly, you are expected to attend fulltime at University, so this is not a good excuse, and secondly it demonstrates a lack of commitment to the course. Even in those circumstances, we will do the right thing, and allow you to demonstrate before you leave (but not after you get back as this is unfair on all the diligent students).<br/>
<br/>
Feedback?<br/>
Feedback is provided at the demonstration/viva, or very shortly **after all vivas are complete** in an email to your University number mail account.<br/>
<br/>
I haven’t done any of the code, but I’ve read all the notes, book chapter, etc., so I am an expert in the various algorithms. Can I do the viva?<br/>
No. At some point in the near future you will probably want to work for a computing company and will need to program. This assignment is all part of the programming experience you will get at University to put you in a position where you can do that work. You don’t usually get handed a good salary for no work in the real world.
