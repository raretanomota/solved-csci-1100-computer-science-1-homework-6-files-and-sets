Download Link: https://assignmentchef.com/product/solved-csci-1100-computer-science-1-homework-6-files-and-sets
<br>
<h1>Problem: Six Degrees of Villainy</h1>

You are given a file called DrWhoVillains.tsv. It is a TAB separated file containing villains in a science fiction show called Dr. Who. The show is known for its extremely low budget and silly creature effects. Although the modern version is slicky produced and has a higher budget, it still pays homage to the original look and feel of the old villains. Look at the picture of a Dalek (one of the main villains) above to see this for yourself. Each line of DrWhoVillains.tsv contains information on a single villain. No villain is repeated on more than one line. Each line contains the following information (separated by TABs):

<ol>

 <li>Villain: name of the villain (e.g. Dalek)</li>

 <li>Year first: the first year this villain was introduced</li>

 <li>Year last: the last year this villain was shown</li>

 <li>no.: the list of doctor ids with this villain, separated by commas</li>

 <li>Doctor actor: the list of actors for each doctor above</li>

 <li>Episodes: number of episodes featuring this villain</li>

 <li>Motivation (invasion earth, kill humans, etc): the description of the mainmotivation of this villain</li>

 <li>Story titles: the titles of the stories that the villain was involved with,a list of strings separated by commas.</li>

</ol>

Note that some of the names of the villains are very long!

Your program must do the following:

<ol>

 <li>Read through the file to find the villain names and the (set of) stories for each villain. <strong>Be careful: </strong>the file is manually created and may have repeated story titles, incorrect case, extra spaces before and after names, etc. We will guarantee that each villain only appears on one line and that there are no misspellings, but you must use consistent capitalization and sets to find unique stories.</li>

 <li>Ask the user for the name of a “target villain” to try to reach: we are going to see how manysteps it will take us to find this villain in a chain from one of the top ten most popular villains.</li>

 <li>Find the top 10 most popular villains: those with the top 10 highest number of stories listedin the file and display them to the user, numbered 1 to 10, in decreasing order of popularity. When there is a tie, break it in reverse alphabetic order (starting at Z and going to A). These top ten villains become our initial candidates.</li>

 <li>In a loop, do the following:

  <ul>

   <li>Display the candidate villains.</li>

   <li>Ask the user for a villain number from the candidates list.</li>

   <li>If the user enters something other than a number from 1 up to and including the numberof candidates, the program displays the current list again and asks for another input.</li>

   <li>If the user enters a valid option then check if the villain at the index (actually one lessthan the index) in the candidates list is the target villain. If so, report that the target villain has been found and exit. This output should include the number of steps to get to this villain. Incorrect input does not count as a step. If the villain is found right away it is 1 step.</li>

   <li>Otherwise, print out how many stories this selected candidate villain was in and thengenerate new candidate villains by finding out all of those villains who appeared in a story with the currently selected candidate villain. Order the new candidate villains in the same way as the original villains.</li>

  </ul></li>

</ol>

<h1>Some Hints</h1>

We are not going to tell you exactly how to structure your code, but we are going to give you a few hints.

<ol>

 <li>Parsing the villain file is an important of this HW. We suggest you create a function thattakes a single string parameter corresponding to a single line of the input file, parses that line, and then returns a list containing:</li>

</ol>

[number of shows, villain name, set of show titles]

Think about this a little. It is not overly hard if you realize that we only need information from 2 of the 8 fields contained in the file. The remaining 6 fields – Year first, Year last, Doc. no., Doc. Actor, Episodes, and Motivation – are not used in this assignment. Take the line, split it at the TABS. Item[0] is the villain name and item[7] is a comma separated string that you can split and turn into a set of story titles.

Test your parsing very thoroughly before proceeding. If you come to use for help after you believe you have parsing working, you must be prepared to demonstrate to us that it is correct!

<ol start="2">

 <li>If you maintain a list of lists, for example if you make a list of lists returned by the parsingfunction just described, it is simple to sort this list. As mentioned at the start of this assignment, check out py for code that will help you with this. If you understand example_list_of_lists.py you will see how to easily do the sorting required by this project as well. We suggest you experiment by modifing that program to put all of the states at the same rank, and look at the sorted list before you try the sorting in your program.</li>

 <li>Start small and build up. Make sure you can parse the lines correctly into a list first and testit. Then build up the list of lists. Then sort it. Then figure out how to generate the list of villains, etc. Once your program is working correctly, get the formatting right.</li>

 <li>Lab 8 touches on some of the same topics and requires many of the same skills required here.</li>

</ol>

If you are having problems, work through the material in Lab 8. It will help.




<h1>Expected Output</h1>

Below you can see the expected functioning of this program with the file we gave you (note: we might change the file in the homework submission server):

Who are you trying to reach? Neo-Nazis, WindSOR Neo-Nazis, WindSOR

<ol>

 <li>Daleks</li>

 <li>Cybermen</li>

 <li>Master (the)</li>

 <li>Dalek Supreme (Supreme Dalek), inc Progenitor</li>

 <li>Sontarans</li>

 <li>Ice Warriors (inc benevolent appearences)</li>

 <li>Davros</li>

 <li>Silurians (exc Sea Devils)</li>

 <li>Kovarian, Madame</li>

 <li>Cyber-leader</li>

</ol>

Enter a selection =&gt; 2 2

Cybermen appeared in 24 stories and overlapped with:

<ol>

 <li>Daleks</li>

 <li>Master (the)</li>

 <li>Dalek Supreme (Supreme Dalek), inc Progenitor</li>

 <li>Sontarans</li>

 <li>Ice Warriors (inc benevolent appearences)</li>

 <li>Silurians (exc Sea Devils)</li>

 <li>Kovarian, Madame</li>

 <li>Cyber-leader</li>

 <li>Black Guardian (the)</li>

 <li>Ood, the (Oodkind), inc benevolent appearances</li>

 <li>Cybermat</li>

 <li>Borusa</li>

 <li>Yeti</li>

 <li>Terrible Zodin</li>

 <li>Rassilon</li>

 <li>Lytton, Commander Gustav</li>

 <li>Cyber-controller</li>

 <li>Cult of Skaro (inc Dalek Sec and three others)</li>

 <li>Atraxi</li>

 <li>van Statten, Henry</li>

 <li>War Lord</li>

 <li>War Chief</li>

 <li>Vaughn, Tobias</li>

 <li>Raston Warrior Robot</li>

 <li>Peinforte, Lady</li>

 <li>Neo-Nazis, Windsor</li>

 <li>Mawdryn</li>

 <li>Manton, Colonel</li>

 <li>Mailer, Harry</li>

 <li>Lumic, John</li>

 <li>Kellman</li>

 <li>Keller Machine</li>

 <li>Kalik</li>

 <li>Headless Monks</li>

 <li>Hartman, Yvonne</li>

 <li>Hartigan, Mercy</li>

 <li>Drashigs</li>

 <li>De Flores</li>

 <li>Cybershades</li>

 <li>Cyberman Android</li>

 <li>Alliance – onscreen – Daleks, Cybermen, Sontarans &amp; Autons, (cameos Silurians, Sycorax,</li>

</ol>

Enter a selection =&gt; 38 38

De Flores appeared in 1 story and overlapped with:

<ol>

 <li>Cybermen</li>

 <li>Cyber-leader</li>

 <li>Peinforte, Lady</li>

 <li>Neo-Nazis, Windsor</li>

</ol>

Enter a selection =&gt; 4 4

You reached the villain Neo-Nazis, Windsor in 3 steps.

Have a nice day.

A second example:

Who are you trying to reach? Daleks

Daleks

<ol>

 <li>Daleks</li>

 <li>Cybermen</li>

 <li>Master (the)</li>

 <li>Dalek Supreme (Supreme Dalek), inc Progenitor</li>

 <li>Sontarans</li>

 <li>Ice Warriors (inc benevolent appearences)</li>

 <li>Davros</li>

 <li>Silurians (exc Sea Devils)</li>

 <li>Kovarian, Madame</li>

 <li>Cyber-leader</li>

</ol>

Enter a selection =&gt; stop stop

<ol>

 <li>Daleks</li>

 <li>Cybermen</li>

 <li>Master (the)</li>

 <li>Dalek Supreme (Supreme Dalek), inc Progenitor</li>

 <li>Sontarans</li>

 <li>Ice Warriors (inc benevolent appearences)</li>

 <li>Davros</li>

 <li>Silurians (exc Sea Devils)</li>

 <li>Kovarian, Madame</li>

 <li>Cyber-leader</li>

</ol>

Enter a selection =&gt; -1 -1

<ol>

 <li>Daleks</li>

 <li>Cybermen</li>

 <li>Master (the)</li>

 <li>Dalek Supreme (Supreme Dalek), inc Progenitor</li>

 <li>Sontarans</li>

 <li>Ice Warriors (inc benevolent appearences)</li>

 <li>Davros</li>

 <li>Silurians (exc Sea Devils)</li>

 <li>Kovarian, Madame</li>

 <li>Cyber-leader</li>

</ol>

Enter a selection =&gt; 1 1

You reached the villain Daleks in 1 steps.

Have a nice day.