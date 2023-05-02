Download Link: https://assignmentchef.com/product/solved-comp249-object-oriented-programming-ii-assignment-4
<br>
<strong>Purpose:</strong>  The purpose of this assignment is to allow you practice ArrayList, Interfaces, Generics and Linked Lists.

<h1>Part 1: Interfaces, Generics &amp; ArrayList</h1>

<em> </em>

In 1935, the American linguist George Zipf noticed something very peculiar with the books he was reading… whenever he would count the words in his books, he noticed that most of the words appeared only once and a small number of words appeared very frequently.  In addition, this phenomenon seemed to hold true for any text and in any language.  Zipf analysed this a little further, and noticed that if you sort the words by frequency and plot the frequency of words versus their rank in the sorted list, you will always get a graph similar to the one below, where a few words have a high frequency (the peak on the left), and most words appear only once (the long tail on the right).







In technical terms:

<ul>

 <li>Words that appear frequently (the peak on the left) and that happen to be short are called <em>stop-words</em>.</li>

 <li>Words that only appear once (the tail on the right) are called <em>happax legomena</em>.</li>

</ul>
















Today, this behaviour of language is known as Zipf’s law and is used tremendously in the Search Engine industry.  In fact, it turns out that Zipf’s law is also applicable to many other domains and applications such as monitoring traffic (on the Internet or on the highway), predicting financial activities, and even analysing animal behaviour…




Write a program to verify Zipf’s law with your favourite text.  Specifically, your program must ask the user for an input text file (please handle potential I/O errors properly), and count how many words the file contains and display the following statistics:




<ul>

 <li>Display each word in the text along with its rank and frequency.</li>

</ul>

You can assume that a word is defined as anything that the method <sub>Scanner.next()</sub> returns and only contains letters.  For example “U2”, “data-base” and “hi!” should not be counted as words.

Your program does not have to be case-sensitive.  For example, the words “hi” and “Hi” can be considered as same words.

The list of rank/word/frequency must be displayed in descending order of frequency, and all words with the same frequency must be displayed in alphabetical order (uppercases before lowercases).




<ul>

 <li>Display the total number of word tokens and word types.</li>

</ul>

The number of word tokens refers to the total number of words in the text (the number of times the method Scanner.next() returned a <sub>String</sub>); whereas the number of word types refers to the number of different words in the text.  For example, if the word “the” appears 30 times, it will count as 30 word tokens, but only 1 word type.




<ul>

 <li>Display statistics on the <em>happax legomena</em>:</li>

 <li>the number of happax,</li>

 <li>the percentage of happax (nb happax ÷ nb of word types), and</li>

 <li>how many of the tokens in the text they account for (nb happax ÷ nb of word tokens).</li>

</ul>




– Display statistics on the stops words:

<ul>

 <li>the number of stop words,</li>

 <li>the percentage of stop words (nb stop words ÷ nb of word types), and</li>

 <li>how many of the tokens in the text they account for (total frequency of stop stops ÷ nb of word tokens). For this assignment, you can assume that a stop word is a word that has a length of 4 characters or less and that appears at least 10 times in the text.</li>

</ul>

Here is an example of how your program should behave (the file <sub>jokes.txt</sub> is available with this assignment):




<table width="586">

 <tbody>

  <tr>

   <td rowspan="2" width="147"><strong>Enter input file:  </strong><strong> </strong><strong>————————————</strong><strong>RANK           FREQ </strong><strong>————————————</strong><strong>1                  </strong><strong>17 </strong><strong>2                  </strong><strong>10 </strong><strong>3                  </strong><strong>7 </strong><strong>4                  </strong><strong>7 </strong><strong>5                  </strong><strong>5 </strong><strong>6                  </strong><strong>5 </strong><strong>7                  </strong><strong>4 </strong><strong>8                  </strong><strong>4 </strong><strong>9                  </strong><strong>4 </strong><strong>10                 </strong><strong>4 </strong><strong>11                 </strong><strong>4 </strong><strong>12                 </strong><strong>4 </strong><strong>13                 </strong><strong>4 </strong><strong>14                 </strong><strong>3 </strong><strong>… </strong><strong>34                 </strong><strong>1 </strong><strong>35                 </strong><strong>1 </strong><strong>36                 </strong><strong>1 </strong><strong>… </strong><strong>51                 </strong><strong>1 </strong><strong>52                 </strong><strong>1 </strong><strong>53                 </strong><strong>1 </strong><strong>54                 </strong><strong>1 </strong><strong>55                 </strong><strong>1 </strong><strong>… </strong><strong>174               </strong><strong>1 </strong><strong>175               </strong><strong>1 </strong><strong>176               </strong><strong>1 </strong><strong>177               </strong><strong>1 </strong><strong>178               </strong><strong>1 </strong><strong> </strong><strong>———————————</strong><strong> </strong><strong>Nb of word tokens: 268</strong><strong>Nb of word types: 178</strong><strong> </strong><strong>Nb of Happax: 145 </strong><strong>% of Happax: 81% </strong><strong>Happax account for: 54% of the text  </strong><strong>Nb of stop words: 6</strong><strong>% of stop words: 3%</strong></td>

   <td width="66"><strong>jokes.txt</strong></td>

   <td rowspan="2" width="373"><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong>Bakers </strong><strong>Count  </strong><strong>about </strong><strong> backward baseball batteries </strong><strong> </strong><strong> wondered write writes </strong><strong>— </strong><strong> </strong><strong> </strong></td>

  </tr>

  <tr>

   <td width="66"><strong>       WORD</strong><strong>       a         A         in         was         the         you         The         When</strong><strong>       are         is         of         who         your         and</strong><strong> </strong><strong> </strong><strong>      Did</strong><strong> </strong><strong>      all</strong><strong> </strong><strong> </strong><strong> </strong><strong>      why</strong><strong>       will</strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong> </strong><strong>Stop words account for: 19% of the text</strong></td>

  </tr>

 </tbody>

</table>







<h1>Part 2: Linked Lists</h1>

<strong> </strong>

Write a program to manipulate Cellular Phones using linked lists.




<ol>

 <li>The <strong><sub>CellPhone</sub></strong> class has the following attributes: a <sub>serialNum</sub> (long type), a <sub>brand</sub> (String type), a <sub>year</sub> (int type, which indicates manufacturing year) and a <sub>price</sub> (double type). It is assumed that brand name is always recorded as a single word (i.e. Motorola, SonyEricsson, Panasonic, etc.). It is also assumed that all cellular phones follow one system of assigning serial numbers, regardless of their different brands, so no two cell phones may have the same serial number.</li>

</ol>

You are required to write the implementation of the <sub>CellPhone</sub> class. Beside the usual mutator and accessor methods (i.e. <sub>getPrice(),</sub> <sub>setYear())</sub> the class must have the following:

<ul>

 <li>Parameterized constructor that accepts four values and initializes <em>serialNum</em>, <em>brand</em>, <em>year</em> and <em>price</em> to these passed values;</li>

 <li>Copy constructor, which takes two parameters, a <sub>CellPhone</sub> object and a long value. The newly created object will be assigned all the attributes of the passed object, with the exception of the serial number. <em>serialNum </em>is assigned the value passed as the second parameter to the constructor. It is always assumed that this value will correspond to the unique serial number rule;</li>

 <li><sub>clone()</sub> This method will prompt the user to enter a new serial number, then creates and returns a clone of the calling object with the exception of the serial number, which is assigned the value entered by the user;</li>

 <li>Additionally, the class should have a <sub>toString()</sub> and an <sub>equals()</sub> Two cell phones are equal if they have the same attributes, with the exception of the serial number, which could be different.</li>

</ul>

<ol>

 <li>The file <strong><sub>txt</sub></strong>, which one of its versions is provided with this assignment, has the information of various cell phone objects. The file may have zero or more records. The information stored in this file is always assumed to be correct and following the unique serial number rule. A snapshot of the contents of the <sub>Cell_info.txt</sub> file is shown in Figure 1 below.</li>

</ol>

<em>Figure 1: Cell_info.txt </em>




<ul>

 <li>The <strong>Cell</strong><strong><sub>List</sub></strong> class has the following:</li>

 <li>An inner class called <sub>CellNode</sub>. This class has the following:

  <ol>

   <li>Two private attributes: an object of <sub>CellPhone</sub> and a pointer to a <sub>CellNode</sub> object;</li>

   <li>A default constructor, which assigns both attributes to <sub>null</sub>;</li>

  </ol></li>

</ul>

<ul>

 <li>A parameterized constructor that accepts two parameters, a <sub>CellPhone</sub> object and a <sub>CellNode</sub> object, then initializes the attributes accordingly;</li>

</ul>

<ol>

 <li>A copy constructor;</li>

 <li>A <sub>clone()</sub> method;</li>

 <li>Other mutator and accessor methods.</li>

</ol>

<ul>

 <li>A private attribute called <sub>head</sub>, which should point to the first node in this list object;</li>

 <li>A private attribute called <sub>size</sub>, which always indicates the current size of the list (how many nodes are in the list); (d) A default constructor, which creates an empty list;</li>

 <li>A copy constructor, which accepts a <sub>CellList</sub> object and creates a copy of it;</li>

 <li>A method called <sub>addToStart()</sub>, which accepts one parameter, an object from <sub>CellPhone</sub> The method then creates a node with that passed object and inserts this node at the head of the list;</li>

 <li>A method called <sub>insertAtIndex()</sub>, which accepts two parameters, an object from <sub>CellPhone</sub> class, and an integer representing an index. If the index is not valid (a valid index must have a value between <sub>0</sub> and <sub>size-1</sub>), the method must throw a <sub>NoSuchElementException</sub> and terminate the program. If the index is valid, then the method creates a node with the passed <sub>CellPhone</sub> object and inserts this node at the given index. The method must properly handle all special cases;</li>

 <li>A method called <sub>deleteFromIndex()</sub>, which accepts one integer parameter representing an index. Again, if the index is not valid, the method must throw a <sub>NoSuchElementException</sub> and terminate the program. Otherwise; the node pointed by that index is deleted from the list. The method must properly handle all special cases;</li>

 <li>A method called <sub>deleteFromStart()</sub>, which deletes the first node in the list (the one pointed by <sub>head</sub>). All special cases must be properly handled.</li>

 <li>A method called <sub>replaceAtIndex()</sub>, which accepts two parameters, an object from <sub>CellPhone</sub> class, and an integer representing an index. If the index is not valid, the method simply returns; otherwise the object in the node at the passed index is to be replaced by the passed object;</li>

 <li>A method called <sub>find()</sub>, which accepts one parameter of type long representing a serial number. The method then searches the list for a node with a cell phone with that serial number. If such an object is found, then the method returns a pointer to that node where the object is found; otherwise, the method returns <sub>null</sub>. The method must keep track of how many iterations were made before the search finally finds the phone or concludes that it is not in the list;</li>

 <li>A method called <sub>contains()</sub>, which accepts one parameter of type long representing a serial number. The method returns <sub>true</sub> if the an object with that serial number is in the list; otherwise, the method returns <sub>false</sub>;</li>

 <li>A method called <sub>showContents()</sub>, which displays the contents of the list, in a similar fashion to what is shown in Figure 2 below.</li>

 <li>A method called <sub>equals()</sub>, which accepts one parameter of type <sub>CellList</sub>. The method returns <sub>true</sub> if the two lists contain similar objects; otherwise the method returns <sub>false</sub>. Recall that two <sub>CellPhone</sub> objects are equal if they have the same values with the exception of the serial number, which can, and actually is expected to be, different.</li>

</ul>




<em>Figure 2: Sample of Displaying the Contents of a CellList </em>




è Finally, here are some general rules that you must consider when implementing the above methods:

<ul>

 <li>Whenever a node is added or deleted, the list size must be adjusted accordingly;</li>

 <li>All special cases must be handled, whether or not the method description explicitly states that;</li>

 <li>All <sub>clone()</sub> and copy constructors must perform a deep copy; no shallow copies are allowed;</li>

 <li><u>If any of your methods allows a privacy leak, you must clearly place a comment at the beginning of the method 1)</u> <u>indicating that this method may result in a privacy leak 2) explaning the reason behind the privacy leak. Please</u> <u>keep in mind that you are not required to implement these proposals;</u></li>

</ul>




<ol>

 <li><strong>IV)</strong> Now, you are required to write a public class called <strong><sub>CellListUtilization</sub></strong>. In the <sub>main() </sub>method, you must do the following:</li>

</ol>

<ul>

 <li>Create at least two empty lists from the <sub>CellList</sub> class;</li>

 <li>Open the <sub>txt</sub> file, and read its contents line by line. Use these records to initialize one of the</li>

</ul>

CellList objects you created above. You can simply use the <sub>addToStart()</sub> method to insert the read objects into the list. However, the list should not have any duplicate records, so if the input file has duplicate entries, which is the case in the file provided with the assignment for instance, your code must handle this case so thast each record is inserted in the list only once;

<ul>

 <li>Show the contents of the list you just initialized;</li>

 <li>Prompt the user to enter a few serial numbers and search the list that you created from the input file for these values. Make sure to display the number of iterations performed;</li>

 <li>Following that, you must create enough objects to test each of the constructors/methods of your classes. The details of this part are left as open to you. You can do whatever you wish as long as your methods are being tested including some of the special cases.</li>

</ul>

<strong>Evaluation Criteria (10pts): </strong>




<table width="392">

 <tbody>

  <tr>

   <td width="321">Part 1 (5 points)</td>

   <td width="70"> </td>

  </tr>

  <tr>

   <td width="321">Proper Use of ArrayList</td>

   <td width="70">1.5 pts</td>

  </tr>

  <tr>

   <td width="321">Proper Use of the Comparable Interface</td>

   <td width="70">1.5 pts</td>

  </tr>

  <tr>

   <td width="321">Simplicity of the Algorithm</td>

   <td width="70">1.5 pts</td>

  </tr>

  <tr>

   <td width="321">Programming Style</td>

   <td width="70">0.5 pts</td>

  </tr>

  <tr>

   <td width="321">Part 2 (5 points)</td>

   <td width="70"> </td>

  </tr>

  <tr>

   <td width="321">Design and Corretness of Classes</td>

   <td width="70">2.5 pts</td>

  </tr>

  <tr>

   <td width="321">Proper and Sufficient Testing of Your Methods</td>

   <td width="70">2 pts</td>

  </tr>

  <tr>

   <td width="321">Privay Leak Comments and Proposals to Avoid Them</td>

   <td width="70">0.5 pts</td>

  </tr>

 </tbody>

</table>




In addition, please note that part of the submission will involve a short 10 minute demonstration to the marker.  No extra preparation is necessary – you only need to explain your code to the marker and answer his/her questions.  All members of the group must attend the demo and must be able to explain their program to the marker. Different marks may be assigned to teammates based on this demo. The schedule of the demos will be determined and announced by the markers, and students must contact the marker to reserve their time slot.  Demos are mandatory.  Failure to do your demo will entail a mark of zero for the assignment.  There will be no substitution for a missed demo.

<strong> </strong>