Download Link: https://assignmentchef.com/product/solved-cis4930-project-1-boggle
<br>
<h1>1           Boggle</h1>

Peggy Hill needs your help in preparing for the big Boggle tournament coming up! Your task is to create a Boggle simulator. If you don’t know the rules to Boggle, start by reading up on them here: <a href="https://en.wikipedia.org/wiki/Boggle">https://en.wikipedia.org/wiki/Boggle</a><a href="https://en.wikipedia.org/wiki/Boggle">.</a>




The Boggle simulator will serve as a tool to help players practice their Boggle skills – that is, it is intended to be used by a single player. The game has the following phases:

<ol>

 <li>The 16 dice (described on the next page) are “rolled” and randomly positioned on a 4×4 grid.</li>

</ol>




<ol start="2">

 <li>The player begins to type the words that appear in the grid. The player must search for words that can be constructed from the letters of sequentially adjacent cubes, where “adjacent” cubes are those horizontally, vertically, and diagonally neighboring. For a word to be scored, it must meet the following requirements:

  <ul>

   <li>The word must not have already been scored.</li>

   <li>It must be at least three letters long.</li>

   <li>It must be a word in the English language.</li>

   <li>It must be present in the 4×4 grid of dice.</li>

   <li>It may not use the same letter cube more than once per word.</li>

  </ul></li>

</ol>

These conditions should be checked in this order. For example, the word “OG” should be rejected for being too short, not for being absent from the dictionary. The user entries should not be case-sensitive. The player must be prompted to end this phase by entering the letter ‘X’.




<ol start="3">

 <li>When the player elects to quit, the player will be presented with their final score. The player may only receive the points for the word if it meets the qualifications above. The program should print out how many points the player received for each word and if the word was not included, the program must print the reason. Finally, the program should print the total score. Note that we do not enforce a timer as is done in traditional Boggle.</li>

</ol>

Words are awarded points according to the table below (as long as they meet the conditions listed above):

<table width="188">

 <tbody>

  <tr>

   <td width="106">Word Length</td>

   <td width="83">Points</td>

  </tr>

  <tr>

   <td width="106">3, 4</td>

   <td width="83">1</td>

  </tr>

  <tr>

   <td width="106">5</td>

   <td width="83">2</td>

  </tr>

  <tr>

   <td width="106">6</td>

   <td width="83">3</td>

  </tr>

  <tr>

   <td width="106">7</td>

   <td width="83">5</td>

  </tr>

  <tr>

   <td width="106">8+</td>

   <td width="83">11</td>

  </tr>

 </tbody>

</table>







The 16 dice have the following letters on each of their six sides:




<table width="248">

 <tbody>

  <tr>

   <td width="144">1. A E A N E G</td>

   <td width="104">9. W N G E E H</td>

  </tr>

  <tr>

   <td width="144">2. A H S P C O</td>

   <td width="104">10. L N H N R Z</td>

  </tr>

  <tr>

   <td width="144">3. A S P F F K</td>

   <td width="104">11. T S T I Y D</td>

  </tr>

  <tr>

   <td width="144">4. O B J O A B</td>

   <td width="104">12. O W T O A T</td>

  </tr>

  <tr>

   <td width="144">5. I O T M U C</td>

   <td width="104">13. E R T T Y L</td>

  </tr>

  <tr>

   <td width="144">6. R Y V D E L</td>

   <td width="104">14. T O E S S I</td>

  </tr>

  <tr>

   <td width="144">7. L R E I X D</td>

   <td width="104">15. T E R W H V</td>

  </tr>

  <tr>

   <td width="144">8. E I U N E S</td>

   <td width="104">16. N U I H M Qu</td>

  </tr>

 </tbody>

</table>

Note that Qu is the only two-letter sequence that appears on a single face of a die.




To verify that a word is actually present in the English language, you are encouraged to use the PyEnchant module. The PyEnchant module may be installed on Ubuntu 14.04 with the following command:




$ sudo apt-get install python-enchant




and an example usage of the dictionary lookup functionality is shown below:

&gt;&gt;&gt; import enchant

&gt;&gt;&gt; d = enchant.Dict(“en_US”)

&gt;&gt;&gt; d.check(“Hello”)

True

&gt;&gt;&gt; d.check(“sdjh”)

False




<strong>A few more suggestions:</strong>




<ul>

 <li>Consider a recursive approach to verifying that the word can be found within the dice grid. Start with finding all of the possible positions where the word may start, then recursively check each valid position for the next letter, backtracking when you determine that the word cannot be found from that point.</li>

 <li>The majority of your implementation will likely rely on lists and strings. Make use of list comprehensions for brevity and use built-in string methods to make it easier on yourself.</li>

 <li>Come see me if you are struggling!</li>

</ul>




<strong>Some sample runs follow:</strong>




$ python boggle.py

[O] [I] [S] [E]

[L] [R] [O] [N]




[T] [K] [N] [I]

[Y] [N] [J] [I]




Start typing your words! (press enter after each word and enter

‘X’ when done):

&gt; NORSE

&gt; RISE

&gt; SON

&gt; IN

&gt; SORT

&gt; NINE

&gt; KIN

&gt; NOR

&gt; EONS

&gt; KON

&gt; X

The word NORSE is worth 2 points.

The word RISE is worth 1 point.

The word SON is worth 1 point.

The word IN is too short.

The word SORT is worth 1 point.

The word NINE is worth 1 point.

The word KIN is not present.

The word NOR is worth 1 point.

The word EONS is worth 1 point.

The word KON is … not a word.

Your total score is 8 points!







$ python boggle.py

[S] [E] [T] [T]




[O] [A] [N] [T]

[M] [O] [V] [E]

[T] [H] [E] [E]




Start typing your words! (press enter after each word and enter

‘X’ when done):

&gt; TEN

&gt; OVEN

&gt; MOVE

&gt; MOVED

&gt; TEAM

&gt; TEA

&gt; AT

&gt; MATE

&gt; NAOS

&gt; TEA

&gt; X

The word TEN is worth 1 point.

The word OVEN is worth 1 point.

The word MOVE is worth 1 point. The word MOVED is not present.

The word TEAM is worth 1 point.

The word TEA is worth 1 point.

The word AT is too short.

The word MATE is worth 1 point.

The word NAOS is … not a word.

The word TEA has already been used.

Your total score is 6 points!




$ python boggle.py

[I] [N] [D] [E]




[E] [C] [A] [E]

[I] [S] [O] [T]

[D] [T] [M] [A]




Start typing your words! (press enter after each word and enter

‘X’ when done):

&gt; NICEST

&gt; ATOM

&gt; TOAST

&gt; X

The word NICEST is worth 3 points.

The word ATOM is worth 1 point.

The word TOAST is worth 2 points.

Your total score is 6 points!





