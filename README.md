Download Link: https://assignmentchef.com/product/solved-cs61a-homework-3-recursion-tree-recursion
<br>
<h2>Instructions</h2>

Download <a href="https://cs61a.org/hw/hw03/hw03.zip">hw03.zip</a> <a href="https://cs61a.org/hw/hw03/hw03.zip">(hw03.zip)</a><a href="https://cs61a.org/hw/hw03/hw03.zip">.</a> Inside the archive, you will nd a le called <a href="https://cs61a.org/hw/hw03/hw03.py">hw03.py</a> <a href="https://cs61a.org/hw/hw03/hw03.py">(hw03.py)</a><a href="https://cs61a.org/hw/hw03/hw03.py">,</a> along with a copy of the ok autograder.

Submission: When you are done, submit with python3 ok –submit . You may submit more than once before the deadline; only the nal submission will be scored. Check that you have successfully submitted your code on <a href="https://okpy.org/">okpy.org</a> <a href="https://okpy.org/">(https://okpy.org/)</a>. See <a href="https://cs61a.org/lab/lab00#submitting-the-assignment">Lab</a> <a href="https://cs61a.org/lab/lab00#submitting-the-assignment">0</a> <a href="https://cs61a.org/lab/lab00#submitting-the-assignment">(/lab/lab00#submitting-the-assignment)</a> for more instructions on submitting assignments.

Using Ok: If you have any questions about using Ok, please refer to <a href="https://cs61a.org/articles/using-ok">this</a> <a href="https://cs61a.org/articles/using-ok">guide.</a> <a href="https://cs61a.org/articles/using-ok">(/articles/using-ok)</a>

Readings: You might nd the following references useful:

<a href="http://composingprograms.com/pages/17-recursive-functions.html">Section</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html">1.7</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html">(http://composingprograms.com/pages/17-recursive-functions.html)</a>

Grading: Homework is graded based on correctness. Each incorrect problem will decrease the total score by one point. There is a homework recovery policy as stated in the syllabus. This homework is out of 2 points.

<h1>Required Questions</h1>

<h2>Q1: Num eights</h2>

Write a recursive function num_eights that takes a positive integer pos and returns the number of times the digit 8 appears in pos .

Important: Use recursion; the tests will fail if you use any assignment statements. (You can however use function de nitions if you so wish.)

def num_e<span style="text-decoration: line-through;">i</span>ghts(pos):

“””Returns the number of times 8 appears as a digit of pos.

&gt;&gt;&gt; num_eights(3)

0

&gt;&gt;&gt; num_eights(8)

1

&gt;&gt;&gt; num_eights(88888888)

8

&gt;&gt;&gt; num_eights(2638)

1

&gt;&gt;&gt; num_eights(86380)

2

&gt;&gt;&gt; num_eights(12345)

0

&gt;&gt;&gt; from construct_check import check

&gt;&gt;&gt; # ban all assignment statements

&gt;&gt;&gt; check(HW_SOURCE_FILE, ‘num_eights’,

…       [‘Assign’, ‘AnnAssign’, ‘AugAssign’, ‘NamedExpr’])

True

“””

“*** YOUR CODE HERE ***”

Use Ok to test your code:

python3 ok -q num_eights                                                                                                                                                                                                       &#x2702;

<h2>Q2: Ping-pong</h2>

The ping-pong sequence counts up starting from 1 and is always either counting up or counting down. At element k , the direction switches if k is a multiple of 8 or contains the digit 8. The rst 30 elements of the ping-pong sequence are listed below, with direction swaps marked using brackets at the 8th, 16th, 18th, 24th, and 28th elements:

<table width="717">

 <tbody>

  <tr>

   <td width="72">Index</td>

   <td width="21">1</td>

   <td width="23">2</td>

   <td width="23">3</td>

   <td width="24">4</td>

   <td width="23">5</td>

   <td width="24">6</td>

   <td colspan="2" width="24">7</td>

   <td width="33">[8]</td>

   <td width="24">9</td>

   <td colspan="2" width="30">10</td>

   <td width="26">11</td>

   <td colspan="2" width="29">12</td>

   <td width="29">13</td>

   <td colspan="2" width="30">14</td>

   <td width="29">15</td>

   <td colspan="2" width="39">[16]</td>

   <td width="29">17</td>

   <td width="39">[18]</td>

   <td colspan="2" width="29">19</td>

   <td width="31">20</td>

   <td colspan="2" width="29">21</td>

   <td width="31">22</td>

   <td colspan="2" width="31">23</td>

  </tr>

  <tr>

   <td width="72">PingPongValue</td>

   <td width="21">1</td>

   <td width="23">2</td>

   <td width="23">3</td>

   <td width="24">4</td>

   <td width="23">5</td>

   <td width="24">6</td>

   <td colspan="2" width="24">7</td>

   <td width="33">[8]</td>

   <td width="24">7</td>

   <td colspan="2" width="30">6</td>

   <td width="26">5</td>

   <td colspan="2" width="29">4</td>

   <td width="29">3</td>

   <td colspan="2" width="30">2</td>

   <td width="29">1</td>

   <td colspan="2" width="39">[0]</td>

   <td width="29">1</td>

   <td width="39">[2]</td>

   <td colspan="2" width="29">1</td>

   <td width="31">0</td>

   <td colspan="2" width="29">-1</td>

   <td width="31">-2</td>

   <td colspan="2" width="31">-3</td>

  </tr>

  <tr>

   <td colspan="8" width="222">Index (cont.)</td>

   <td colspan="4" width="81">[24]</td>

   <td colspan="3" width="61">25</td>

   <td colspan="3" width="63">26</td>

   <td colspan="3" width="61">27</td>

   <td colspan="4" width="82">[28]</td>

   <td colspan="3" width="63">29</td>

   <td colspan="3" width="63">30</td>

   <td width="22"> </td>

  </tr>

  <tr>

   <td colspan="8" width="222">PingPong Value</td>

   <td colspan="4" width="81">[-4]</td>

   <td colspan="3" width="61">-3</td>

   <td colspan="3" width="63">-2</td>

   <td colspan="3" width="61">-1</td>

   <td colspan="4" width="82">[0]</td>

   <td colspan="3" width="63">-1</td>

   <td colspan="3" width="63">-2</td>

   <td width="22"> </td>

  </tr>

  <tr>

   <td width="72"></td>

   <td width="22"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="14"></td>

   <td width="9"></td>

   <td width="33"></td>

   <td width="23"></td>

   <td width="15"></td>

   <td width="15"></td>

   <td width="28"></td>

   <td width="20"></td>

   <td width="9"></td>

   <td width="29"></td>

   <td width="25"></td>

   <td width="4"></td>

   <td width="29"></td>

   <td width="28"></td>

   <td width="11"></td>

   <td width="29"></td>

   <td width="39"></td>

   <td width="3"></td>

   <td width="26"></td>

   <td width="31"></td>

   <td width="5"></td>

   <td width="23"></td>

   <td width="30"></td>

   <td width="9"></td>

   <td width="22"></td>

  </tr>

 </tbody>

</table>

Implement a function pingpong that returns the nth element of the ping-pong sequence without using any assignment statements. (You are allowed to use function de nitions.)

You may use the function num_eights , which you de ned in the previous question.

Important: Use recursion; the tests will fail if you use any assignment statements. (You can however use function de nitions if you so wish.)

“””Return the nth element of the ping-pong sequence.

&gt;&gt;&gt; pingpong(8)

8

&gt;&gt;&gt; pingpong(10)

6

&gt;&gt;&gt; pingpong(15)

1    &gt;&gt;&gt; pingpong(21)

-1

&gt;&gt;&gt; pingpong(22)

-2

&gt;&gt;&gt; pingpong(30)

-2

&gt;&gt;&gt; pingpong(68)

0    &gt;&gt;&gt; pingpong(69)

-1

&gt;&gt;&gt; pingpong(80)

<ul>

 <li>&gt;&gt;&gt; pingpong(81)</li>

 <li>&gt;&gt;&gt; pingpong(82)</li>

</ul>

0

&gt;&gt;&gt; pingpong(100)

-6

&gt;&gt;&gt; from construct_check import check

&gt;&gt;&gt; # ban assignment statements

&gt;&gt;&gt; check(HW_SOURCE_FILE, ‘pingpong’,

…       [‘Assign’, ‘AnnAssign’, ‘AugAssign’, ‘NamedExpr’])

True

“””

“*** YOUR CODE HERE ***”

Use Ok to test your code:

python3 ok -q pingpong                                                                                                                                                                                                            &#x2702;

<h2>Q3: Missing Digits</h2>

Write the recursive function missing_digits that takes a number n that is sorted in non-decreasing order (for example, 12289 is valid but 15362 and 98764 are not). It returns the number of missing digits in n . A missing digit is a number between the rst and last digit of n of a that is not in n .

Important: Use recursion; the tests will fail if you use any loops.

def m<span style="text-decoration: line-through;">i</span>ss<span style="text-decoration: line-through;">i</span>ng_d<span style="text-decoration: line-through;">i</span>g<span style="text-decoration: line-through;">i</span>ts(n):

“””Given a number a that is in sorted, non-decreasing order,    return the number of missing digits in n. A missing digit is    a number between the first and last digit of a that is not in n.    &gt;&gt;&gt; missing_digits(1248) # 3, 5, 6, 7

4    &gt;&gt;&gt; missing_digits(19) # 2, 3, 4, 5, 6, 7, 8

7    &gt;&gt;&gt; missing_digits(1122) # No missing numbers

0    &gt;&gt;&gt; missing_digits(123456) # No missing numbers

0    &gt;&gt;&gt; missing_digits(3558) # 4, 6, 7

3    &gt;&gt;&gt; missing_digits(35578) # 4, 6

2    &gt;&gt;&gt; missing_digits(12456) # 3

1    &gt;&gt;&gt; missing_digits(16789) # 2, 3, 4, 5

4

&gt;&gt;&gt; missing_digits(4) # No missing numbers between 4 and 4

0

&gt;&gt;&gt; from construct_check import check

&gt;&gt;&gt; # ban while or for loops    &gt;&gt;&gt; check(HW_SOURCE_FILE, ‘missing_digits’, [‘While’, ‘For’])

True

“””

“*** YOUR CODE HERE ***”

Use Ok to test your code:

python3 ok -q missing_digits                                                                                                                                                                                                  &#x2702;

<h2>Q4: Count coins</h2>

Given a positive integer change , a set of coins makes change for change if the sum of the values of the coins is change . Here we will use standard US Coin values: 1, 5, 10, 25. For example, the following sets make change for 15 :

15 1-cent coins

10 1-cent, 1 5-cent coins

5 1-cent, 2 5-cent coins

5 1-cent, 1 10-cent coins

3 5-cent coins

1 5-cent, 1 10-cent coin

Thus, there are 6 ways to make change for 15 . Write a recursive function count_coins that takes a positive integer change and returns the number of ways to make change for change using coins.

You can use either of the functions given to you:

ascending_coin will return the next larger coin denomination from the input, i.e. ascending_coin(5) is 10 . descending_coin will return the next smaller coin denomination from the input, i.e. descending_coin(5) is 1 .

There are two main ways in which you can approach this problem. One way uses ascending_coin , and another uses descending_coin .

Important: Use recursion; the tests will fail if you use loops.

<a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">Hint:</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">Refer</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">the</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">implementation</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">(http://composingprograms.com/pages/17-recursive-</a>

<a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">functions.html#example-partitions)</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">of</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">count_partitions</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">for</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">an</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">example</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">of</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">how</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">to</a> <a href="http://composingprograms.com/pages/17-recursive-functions.html#example-partitions">c</a>ount the ways to sum up to a nal value with smaller parts. If you need to keep track of more than one value across recursive calls, consider writing a helper function.

def ascending<u>_</u>coin(coin):

“””Returns the next ascending coin in order.    &gt;&gt;&gt; ascending_coin(1)

5    &gt;&gt;&gt; ascending_coin(5)

10    &gt;&gt;&gt; ascending_coin(10)

25    &gt;&gt;&gt; ascending_coin(2) # Other values return None

“””    if coin == 1:        return 5    elif coin == 5:        return 10    elif coin == 10:        return 25

def descending<u>_</u>coin(coin):

“””Returns the next descending coin in order.

&gt;&gt;&gt; descending_coin(25)

10

&gt;&gt;&gt; descending_coin(10)

5    &gt;&gt;&gt; descending_coin(5)

1    &gt;&gt;&gt; descending_coin(2) # Other values return None

“””    if coin == 25:        return 10    elif coin == 10:        return 5    elif coin == 5:        return 1

def count<u>_</u>coins(change):

“””Return the number of ways to make change using coins of value of 1, 5, 10, 25.

&gt;&gt;&gt; count_coins(15)

6

&gt;&gt;&gt; count_coins(10)

4

&gt;&gt;&gt; count_coins(20)

9    &gt;&gt;&gt; count_coins(100) # How many ways to make change for a dollar?

242    &gt;&gt;&gt; count_coins(200)

1463    &gt;&gt;&gt; from construct_check import check

&gt;&gt;&gt; # ban iteration    &gt;&gt;&gt; check(HW_SOURCE_FILE, ‘count_coins’, [‘While’, ‘For’])

True

“””

“*** YOUR CODE HERE ***”

Use Ok to test your code:

python3 ok -q count_coins                                                                                                                                                                                                       &#x2702;

<h1>Just for fun Questions</h1>

<h2>Q5: Towers of Hanoi</h2>

A classic puzzle called the Towers of Hanoi is a game that consists of three rods, and a number of disks of di erent sizes which can slide onto any rod. The puzzle starts with n disks in a neat stack in ascending order of size on a start rod, the smallest at the top, forming a conical shape.

Complete the de nition of move_stack , which prints out the steps required to move n disks from the start rod to the end rod without violating the rules. The provided print_move function will print out the

step to move a single disk from the given origin to the given destination .

Hint: Draw out a few games with various n on a piece of paper and try to nd a pattern of disk movements that applies to any n . In your solution, take the recursive leap of faith whenever you need to move any amount of disks less than n from one rod to another. If you need more help, see the following hints.

def print<u>_</u>move(origin, destination):

“””Print instructions to move a disk.”””

print(“Move the top disk from rod”, origin, “to rod”, destination)

def move<u>_</u>stack(n, start, end):

“””Print the moves required to move n disks on the start pole to the end    pole without violating the rules of Towers of Hanoi.

n — number of disks    start — a pole position, either 1, 2, or 3    end — a pole position, either 1, 2, or 3

There are exactly three poles, and start and end must be different. Assume    that the start pole has at least n disks of increasing size, and the end    pole is either empty or has a top disk larger than the top n start disks.

&gt;&gt;&gt; move_stack(1, 1, 3)

Move the top disk from rod 1 to rod 3

&gt;&gt;&gt; move_stack(2, 1, 3)

Move the top disk from rod 1 to rod 2

Move the top disk from rod 1 to rod 3

Move the top disk from rod 2 to rod 3

&gt;&gt;&gt; move_stack(3, 1, 3)

Move the top disk from rod 1 to rod 3

Move the top disk from rod 1 to rod 2

Move the top disk from rod 3 to rod 2

Move the top disk from rod 1 to rod 3

Move the top disk from rod 2 to rod 1

Move the top disk from rod 2 to rod 3    Move the top disk from rod 1 to rod 3

“””    assert 1 &lt;= start &lt;= 3 and 1 &lt;= end &lt;= 3 and start != end, “Bad start/end”    “*** YOUR CODE HERE ***”

Use Ok to test your code:

python3 ok -q move_stack                                                                                                                                                                                                       &#x2702;

<h2>Q6: Anonymous factorial</h2>

<a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">The</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">recursive</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">factorial</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">function</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">can</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">be</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">written</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">as</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">a</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">single</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">expression</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">by</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">using</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">a</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">conditional</a> <a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">expression (http://docs.python.org/py3k/reference/expressions.html#conditional-expressions)</a><a href="https://docs.python.org/py3k/reference/expressions.html#conditional-expressions">.</a>

&gt;&gt;&gt; fact = lambda n: 1 <span style="text-decoration: line-through;">i</span>f n == 1 else mul(n, fact(sub(n, 1)))

&gt;&gt;&gt; fact(5)

120

However, this implementation relies on the fact (no pun intended) that fact has a name, to which we refer in the body of fact . To write a recursive function, we have always given it a name using a def or assignment statement so that we can refer to the function within its own body. In this question, your job is to de ne fact recursively without giving it a name!

Write an expression that computes n factorial using only call expressions, conditional expressions, and

lambda expressions (no assignment or def statements).

The sub and mul functions from the operator module are the only built-in functions required to solve this problem.

from operator <span style="text-decoration: line-through;">i</span>mport sub, mul

def make<u>_</u>anonymous<u>_</u>factor<span style="text-decoration: line-through;">i</span>al():

“””Return the value of an expression that computes factorial.

&gt;&gt;&gt; make_anonymous_factorial()(5)

120

&gt;&gt;&gt; from construct_check import check

&gt;&gt;&gt; # ban any assignments or recursion

&gt;&gt;&gt; check(HW_SOURCE_FILE, ‘make_anonymous_factorial’,

…     [‘Assign’, ‘AnnAssign’, ‘AugAssign’, ‘NamedExpr’, ‘FunctionDef’, ‘Recursion’])

True

“””    return ‘YOUR_EXPRESSION_HERE’

Use Ok to test your code:

python3 ok -q make_anonymous_factorial                                                                                                                                                                      &#x2702;


