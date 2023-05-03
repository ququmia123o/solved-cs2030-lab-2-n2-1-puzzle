Download Link: https://assignmentchef.com/product/solved-cs2030-lab-2-n2-1-puzzle
<br>



<h1>Task Content</h1>

<table width="680">

 <tbody>

  <tr>

   <td width="680"><strong>The </strong><strong>(n</strong><strong><sup>2</sup></strong><strong> − 1)</strong><strong> Puzzle</strong><strong>Topic Coverage</strong>Abstraction and EncapsulationImmutable List<a href="https://www.comp.nus.edu.sg/~cs2030/style/">CS2030 Java St</a><a href="https://www.comp.nus.edu.sg/~cs2030/style/">y</a><a href="https://www.comp.nus.edu.sg/~cs2030/style/">le Guide</a><strong>Problem Description</strong>The 15-Puzzle is a classic sliding puzzle game consisting of a 4-by-4 grid of 15 numbered tiles all jumbled up. The following is an example.

    <table width="607">

     <tbody>

      <tr>

       <td width="607">   7  15  12   411   9   8   2.   1  10   313   5   6  14</td>

      </tr>

     </tbody>

    </table>The objective of the game is to un-jumble the puzzle by repeatedly sliding the tiles to the empty space (denoted by .) to attain the solution below.

    <table width="607">

     <tbody>

      <tr>

       <td width="607">   1   2   3   45   6   7   89  10  11  12   13  14  15   .</td>

      </tr>

     </tbody>

    </table>We shall generalize the 15-Puzzle game to a (n<sup>2</sup> − 1) puzzle.<strong>The Task</strong>The task is to let our user play the game (rather than solve the game which is a non-trivial task). You will first write a Grid2D class to represent a two-dimensional grid. Next, write the Puzzle class that makes use of Grid2D to move the tiles and determine if the puzzle is solved.This task is divided into several levels. You may submit as soon as you complete one level. There is no restriction on the number of attempts.You will need to complete ALL levels to get full credit for this lab.<strong>Level 1</strong></td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">$ javac your_java_files$ jshell your_java_files_in_bottom-up_dependency_order jshell&gt; new Grid2D(List.of(1, 2, 3), 1)$.. ==&gt; {1;2;3} jshell&gt; new Grid2D(List.of(1, 2, 3), 2)$.. ==&gt; {1,2;3} jshell&gt; new Grid2D(List.of(1, 2, 3), 3)$.. ==&gt; {1,2,3} jshell&gt; new Grid2D(List.of(1, 2, 3), 4) $.. ==&gt; {1,2,3}</td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">$ javac your_java_files$ jshell your_java_files_in_bottom-up_dependency_orderjshell&gt; Grid2D emptyGrid = new Grid2D(2)emptyGrid ==&gt; {} jshell&gt; emptyGrid.add(1)$.. ==&gt; {1} jshell&gt; emptyGrid.add(1).add(2)$.. ==&gt; {1,2} jshell&gt; emptyGrid.add(1).add(2).add(3)$.. ==&gt; {1,2;3} jshell&gt; emptyGrid emptyGrid ==&gt; {} jshell&gt; new Grid2D(List.of(1,2,3), 2)$.. ==&gt; {1,2;3} jshell&gt; new Grid2D(List.of(1,2,3), 2).add(4)$.. ==&gt; {1,2;3,4} jshell&gt; new Grid2D(List.of(1,2,3), 2).add(4).add(5) $.. ==&gt; {1,2;3,4;5}</td>

  </tr>

 </tbody>

</table>

By making use of the ImList class provided, create a Grid2D class to represent a variable-sized two-dimensional grid containing integer values with the following specifications:

a constructor Grid2D(List&lt;Integer&gt; list, int numOfCols) that takes in a List of values and the number of columns numOfCols. You may assume that numOfCols &gt; 0.

a toString() method that outputs the values stored in the grid such that values within each row are separated by commas, with each row separated by semi-colons.

<h1>Level 2</h1>

Define an overloaded constructor Grid2D(int numOfCols) that takes in the number of columns numOfCols and creates an empty two-dimensional grid.

Include the add(int elem) method that adds to the current two-dimensional grid.

<h1>Level 3</h1>

Include the get and set methods in Grid2D to get an element, and set the element of the two-dimensional grid respectively.

the method get(int r, int c) returns the element from row r and column c.

the method set(int r, int c, int elem) sets the element at row r and column c, and returns the new Grid2D object.

You may assume that row r and column c are valid positions on the two-dimensional grid with some element value.

$ javac your_java_files

$ jshell your_java_files_in_bottom-up_dependency_order jshell&gt; new Grid2D(List.of(1,2,3,4,5), 2).get(0,0)

$.. ==&gt; 1




jshell&gt; new Grid2D(List.of(1,2,3,4,5), 2).get(1,1)

<table width="606">

 <tbody>

  <tr>

   <td width="606">$ javac your_java_files$ jshell your_java_files_in_bottom-up_dependency_orderjshell&gt; new Puzzle(4)$.. ==&gt;1   2   3   45   6   7   89  10  11  12   13  14  15   . jshell&gt; new Puzzle(5)$.. ==&gt;1   2   3   4   56   7   8   9  1011  12  13  14  1516  17  18  19  20   21  22  23  24   .</td>

  </tr>

 </tbody>

</table>

<table width="606">

 <tbody>

  <tr>

   <td width="606">$ javac your_java_files$ jshell your_java_files_in_bottom-up_dependency_orderjshell&gt; Puzzle puzzle = new Puzzle(4) puzzle ==&gt;    1   2   3   45   6   7   89  10  11  12   13  14  15   . jshell&gt; puzzle.move(10)$.. ==&gt;1   2   3   45   6   7   89  10  11  12   13  14  15   . jshell&gt; puzzle.move(12)</td>

  </tr>

 </tbody>

</table>

$.. ==&gt; 4

jshell&gt; new Grid2D(List.of(1,2,3,4,5), 3).get(1,1)

$.. ==&gt; 5

jshell&gt; new Grid2D(List.of(1,2,3,4,5), 2).set(1,1,9)

$.. ==&gt; {1,2;3,9;5}




jshell&gt; new Grid2D(List.of(1,2,3,4,5), 3).set(1,1,9)

$.. ==&gt; {1,2,3;4,9}

<h1>Level 4</h1>

We are now ready to define the Puzzle class with the following specifications:

define a constructor Puzzle(int n) that takes in a integer value n and creates a (n<sup>2</sup> − 1) puzzle in a solution configuration. define a toString() method that outputs the puzzle.

Each tile should be output with leading spaces using the format String.format(“%4d”, …). In addition, output a dot . to represent the empty tile.

You may assume that the puzzle will be at least of dimensions 2-by-2.

<h1>Level 5</h1>

Sliding the tiles of the puzzle is implemented by specifying which tile is to be moved. Define a method Puzzle move(int num) that takes as argument the number of the tile to be moved.

A tile with number num can be moved if there is an empty space above/below it, or to the left/right of it. If a move is possible, make the move and return the resulting Puzzle object. Otherwise, the existing puzzle is returned.

In addition, include the isSolved() method that returns true if the puzzle is solved, or false otherwise.

You may assume that num is always in the range of 1 to (n<sup>2</sup> − 1) inclusive.

Note that the following sample run shows the puzzles moves for a 4-by-4 puzzle only.




<table width="680">

 <tbody>

  <tr>

   <td rowspan="2" width="37"> </td>

   <td width="607">$.. ==&gt;1   2   3   45   6   7   8    9  10  11   .13  14  15  12 jshell&gt; puzzle.move(12).move(11).move(15).move(12)$.. ==&gt;1   2   3   45   6   7   89  10  15  11   13  14  12   . jshell&gt; puzzle.move(12).move(11).move(15).move(12).isSolved()$.. ==&gt; false jshell&gt; puzzle.isSolved()$.. ==&gt; true</td>

   <td rowspan="2" width="37"> </td>

  </tr>

  <tr>

   <td width="607"> </td>

  </tr>

 </tbody>

</table>


