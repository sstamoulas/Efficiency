# Efficiency
<p>In this assignment, you are asked to improve the execution time of a Java program that attempts to detect plagiarism in a corpus of documents.</p>

<p>In completing this assignment, you will:</p>

<ul>
   <li>Apply the techniques discussed in the lessons to improve the efficiency of code</li>
   <li>Get more experience understanding and modifying existing code</li>
   <li>Enhance your understanding of the behavior and efficiency of various data structures</li>
</ul>

<p><b>Background</b></p>

<p>Plagiarism detection is a very difficult problem to solve, but a simple approach is to just look for common words and phrases between documents. If two (or more) documents contain many of the same phrases, then there is a good possibility that one author copied from the other.</p>

<p>The program you will improve detects common phrases of size windowSize in a corpus of documents, and then report pairs of documents for which the number of common phrases is greater than some threshold, sorted by the number of common phrases.</p>

<p><b>Getting Started</b></p>

<p>Download the <a href="//prod-edxapp.edx-cdn.org/assets/courseware/v1/ccc00ac39a42a47c6b62c66331d12139/asset-v1:PennX+SD2x+2T2017+type@asset+block/PlagiarismDetector.java" target="[object Object]">PlagiarismDetector.java</a> source code.</p>

<p>The detectPlagiarism method takes the name of the directory containing the corpus of documents, as well as the windowSize and threshold parameters, and returns a Map that lists the pairs of documents, with the Map keys sorted by the number of matches. If two or more pairs have the same number of matches, the order in which they are stored is not specified.</p>

<p>Aside from the detectPlagiarism method, the PlagiarismDetector also has helper methods to:</p>

<ul>
  <li>Read a file and store its contents in a List of Strings</li>
  <li>Create the distinct phrases, each of which is of size windowSize</li>
  <li>Find the common phrases between two documents</li>
  <li>Sort the results</li>
</ul>

<p>There is also a main method that you can use to run the detectPlagiarism method (be sure to specify the directory containing the corpus), which then reports the execution time in seconds. Note that this measures the “wall clock” or actual elapsed time, and not the time that the program is actually running on the CPU, but assuming you are the only person using the computer, and there are not too many other processes running in the background, it should give you a good idea of the execution time of the code.</p>

<p>You can, of course, create your own corpus as you modify this program, but we will evaluate the performance of your program using the corpus we provided in <a href="//prod-edxapp.edx-cdn.org/assets/courseware/v1/d25bdf1bf147f97722800ae3e617913e/asset-v1:PennX+SD2x+2T2017+type@asset+block/corpus.zip" target="[object Object]">corpus.zip</a> with windowSize of 4 and threshold of 5.</p>

<p>A modified version of this problem (and the corpus of documents) was originally used at the University of Chicago and presented as a Nifty Assignment at SIGCSE 2008 (<a href="http://nifty.stanford.edu/2008/franke-catch-plagiarists/" target="[object Object]">http://nifty.stanford.edu/2008/franke-catch-plagiarists/</a>), and the implementation was modified by the PennX instruction staff. We will assume that this implementation is correct for our purposes.</p>

<p><b>Activity</b></p>

<p>Your goal in this assignment is to improve the execution time of the detectPlagiarism method and the methods it uses, using the various techniques seen in the lessons.</p>

<p>In particular, you should consider:</p>

<ul>
  <li>Does the code use the correct data structures? If it’s using a List, maybe it should use a Set, or the other way around</li>
  <li>Does the code use efficient algorithms? Perhaps there are quicker ways to accomplish the same things</li>
  <li>Does the code do unnecessary work? Perhaps some code can be rewritten or even removed if it is doing work that’s already been done</li>
</ul>

<p>Keep in mind that you are asked to focus only on improving the execution time of the code. It is okay if your changes have a negative effect on things like memory usage or other aspects of quality, except for correctness, of course: your changes must not change the output of the code!</p>

<p>Please do not change the signature of the detectPlagiarism method. You may, however, modify or even remove any of the other methods as you see fit, as long as the code still works correctly. Likewise, you may add new methods or classes, though if you add new classes, please add them to PlagiarismDetector.java and do not create new .java files. Please be sure that your PlagiarismDetector class is in the default package (i.e., that there is no "package" declaration at the top), and -- perhaps this goes without saying -- please implement all code in Java. :-)</p>

<p>In making changes to the code, you may not assume that:</p>

<ul>
  <li>The program will always use the same set of documents that was provided to you, so you cannot pre-compute results</li>
  <li>The number and size of documents in the corpus will always be the same as the one that was provided to you, so you cannot hardcode values</li>
  <li>The windowSize and threshold will always have the values specified above</li>
  <li>The code is always executed on a multi-core/multi-processor machine, so you can’t know for certain that using threads will help</li>
</ul>

<p>In some cases, you may need to make a decision that is somewhat dictated by the input, e.g. it may be better to use one data structure for small window sizes and a different one for large ones. In such cases, choose the one that works best for the input values specified above since that is what we will use to measure the execution time of your code.</p>

<p><b>Helpful Hints</b></p>

<p>We do not recommend that you try to make a lot of changes to the code and then hope that (a) it’s faster and (b) it still works.</p>

<p>Remember one of the rules of thumb: “measure, don’t guess.” In addition to testing the overall execution time using the main method we provided, write some additional code that measures the execution time (e.g., for individual methods or parts of the code) and then check that each change you make is making the code faster.</p>

<p>But also make sure that the output is still the same! Check the contents of the Map and be sure that you haven’t accidentally introduced any bugs.</p>

<p>You might want to consider making backup copies of the code as you modify it, in case you accidentally break it and/or make it slower. Better yet, use a version control system such as Git/GitHub so you can go back to previous versions of your code if necessary.</p>

<p><b>Before You Submit</b></p>

<p>Please be sure that:</p>

<ul>
  <li>your PlagiarismDetector class is in the default package, i.e. there is no “package” declaration at the top of the source code</li>
  <li>your PlagiarismDetector class compiles and you have not changed the signature of the detectPlagiarism method</li>
  <li>you have not created any additional .java files</li>
</ul>

<p>Assessment</p>

<p>Part of the challenge of this assignment is knowing when you can stop improving the code. Your new implementation will be considered “correct” when the new execution time is less than or equal to 40% of the original execution time.</p>

<p>Execution time depends greatly on the CPU, operating system, other processes, etc. so you may notice fluctuation in the execution times as you are evaluating your code. For this assignment, we will assess your submission based on the improvement measured on the Codio grading platform that we have used for other assignments. You can access it by clicking the "Begin Submission" button below. You may notice that the improvement on Codio is different than it is on your computer, but we will standardize on that platform for grading this assignment.</p>

<p>Of course, your code must still produce the same output as the original code, regardless of the values of the arguments to the detectPlagiarism method. You will be given a score of 0 on this assignment if the output is incorrect with respect to the original implementation, no matter how fast the code runs.</p>

<p>If the execution time of your code on the Codio platform is less than 40% of the original execution time, you will receive a score of 100 for this assignment. If your execution time is greater than 40%, you will lose two points for every 1% over 40%. For instance, you will receive 98 if your execution time is 41% of the original, 96 if it is 42%, 90 if it is 45%, and so on.</p>

<p>On Codio, the original code should take around 95 seconds to complete, so your code should take a little under 40 seconds on Codio in order to earn a score of 100 on this assignment. We strongly recommend that you perform the "Run Autograder" step on Codio to measure the execution time and correctness of your code before submitting it. See the "Submitting this assignment" instructions on the Codio platform after you click the "Begin Submission" button below.</p>

<p>Please note that your code must finish running in under 60 seconds on the Codio platform in order to receive a grade. If it takes more than 60 seconds to complete, the Codio autograder will time out and you will not receive a score for this assignment. So be sure to check the execution time on Codio before completing your submission.</p>

<p>Unlike other assignments, you may not get your score right away for this assignment. Please be patient as it may take 2-3 minutes for your score to appear in Codio and edX.</p>
