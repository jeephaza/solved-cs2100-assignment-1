Download Link: https://assignmentchef.com/product/solved-cs2100-assignment-1
<br>
<h1>QUESTION 0.</h1>

<ol>

 <li>Ensure that you name your file &lt;AxxxxxxxY&gt;.pdf, where AxxxxxxxY is your matric number.</li>

 <li>Ensure that you submit your assignment as a single PDF file.</li>

 <li>Ensure that your assignment submission has your tutorial group number, student ID and name</li>

</ol>










<h1>QUESTION 1. COMPLEMENT NUMBER SYSTEMS</h1>

In the lectures we saw the 2’s complement and 1’s complement number system which are based on the binary (base 2) system. Here we will explore other complement number systems under other bases.

<ol>

 <li>Given a base <em>B</em> (≥ 2), derive a formula to calculate <em>X’</em>, the <em>n</em>-digit <em>B</em>’s complement of a number <em>X</em>.</li>

 <li>An additive inverse of a number <em>a</em> is a number <em>b</em> such that <em>a </em>+ <em>b </em>= 0. Prove that the <em>B</em>’s complement, <em>n’, </em>of a number <em>n</em>, is the additive inverse of <em>n</em>.</li>

 <li>Find the four digit 10’s complement representation of the decimal numbers 123 and -456. I.e. you should find the representation of the two numbers in 10’s complement and not their negation.</li>

</ol>




<ol>

 <li>Following the procedure for subtraction of two 2’s complement numbers in base 2 (by converting it into an addition operation like what you did in tutorial 1), compute the following subtraction in 4-digit 10’s complement. Show your working and give your final answer in 10’s complement.</li>

</ol>

123 – 456







<h1>QUESTION 2. FLOATING POINT NUMBERS</h1>




<ol>

 <li>When representing <em>n-bit </em>signed numbers in excess notation, briefly explain, using a 3bit signed number system as example, why the excess chosen is usually <em>2<sup>n-1</sup></em>.</li>

</ol>

<strong> </strong>

In the following parts we will use an 8-bit floating point representation with this format:




<table width="553">

 <tbody>

  <tr>

   <td width="46">Sign</td>

   <td width="104">Exponent</td>

   <td width="403">Mantissa</td>

  </tr>

  <tr>

   <td width="46">1-bit</td>

   <td width="104">3-bit excess-4</td>

   <td width="403">5 bits normalized with 1 hidden bit (i.e. only 4 bits of the mantissa are stored)</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<ol>

 <li>What are the smallest and largest positive decimal numbers that can be represented? We assume that the entire range of exponent values can be used, i.e. there are no exponent values with special meanings. Write your answers in decimal.</li>

</ol>




<ol>

 <li>Find the normalized representation for these two numbers in the 8-bit floating point representation above. You should calculate the mantissa to one bit more than you require and round up the result if necessary. Write your answer in hexadecimal.</li>

</ol>




<ul>

 <li>= 4.4</li>

 <li>= –0.7</li>

</ul>

<strong> </strong>

<ol>

 <li>Are the two numbers represented perfectly in this floating-point representation? If no, what is the error in the representation for each number (i.e. the difference between the actual value and the floating point representation)?</li>

</ol>




<ol start="3">

 <li>Is the accuracy of one of the two numbers better than the other? Explain. <strong>QUESTION 3. STRUCTURES IN C </strong></li>

</ol>

In this question we will examine how C stores structures in memory.

<ol start="3">

 <li>Compile and run the enclosed q3.c program using gcc on PC, MacOS or Sunfire. The code included is at the end of this file for your reference. Complete the following tables:</li>

</ol>




Table 1: Component Sizes

<table width="320">

 <tbody>

  <tr>

   <td width="103">Variable</td>

   <td width="217">Size in bytes</td>

  </tr>

  <tr>

   <td width="103">t1.num1</td>

   <td width="217"><strong> </strong></td>

  </tr>

  <tr>

   <td width="103">t1.ch</td>

   <td width="217"><strong> </strong></td>

  </tr>

  <tr>

   <td width="103">t1.num2</td>

   <td width="217"><strong> </strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

Table 2: Component Addresses

<table width="320">

 <tbody>

  <tr>

   <td width="103">Variable</td>

   <td width="217">Address</td>

  </tr>

  <tr>

   <td width="103">&amp;t1.num1</td>

   <td width="217"><strong> </strong></td>

  </tr>

  <tr>

   <td width="103">&amp;t1.ch</td>

   <td width="217"><strong> </strong></td>

  </tr>

  <tr>

   <td width="103">&amp;t1.num2</td>

   <td width="217"><strong> </strong></td>

  </tr>

 </tbody>

</table>




Table 3: Array Element Addresses

<table width="320">

 <tbody>

  <tr>

   <td width="103">Variable</td>

   <td width="217">Address</td>

  </tr>

  <tr>

   <td width="103">&amp;t2[0]</td>

   <td width="217"><strong> </strong></td>

  </tr>

  <tr>

   <td width="103">&amp;t2[1]</td>

   <td width="217"><strong> </strong></td>

  </tr>

  <tr>

   <td width="103">&amp;t2[2]</td>

   <td width="217"><strong> </strong></td>

  </tr>

 </tbody>

</table>




<ol>

 <li>Look at the addresses of t1.ch and t1.num2 in Table 2. Do they differ by 1 byte or 4 bytes? Explain why, with reference to the size of t1.ch.</li>

</ol>




<ol start="3">

 <li>The code fragment from q3.c sums the num2 component of the array t2 and stores the total in result.num2.</li>

</ol>

<table width="598">

 <tbody>

  <tr>

   <td width="598">… &lt;other code here&gt; … mystruct_t result = {0.0, ‘ ‘, 0}; int i; … &lt;other code here&gt; … for (i=0; i&lt;6; i++) {result.num2 = result.num2 + t2[i].num2; }</td>

  </tr>

 </tbody>

</table>




Assuming that $s0 contains the base address of t2, $s1 contains the address of result and $t0 is mapped to the variable i, rewrite the for-loop part of the code in MIPS assembly. Ensure that your code is properly commented or marks will be deducted. Note also that pseudoinstructions other than those required for any unaligned loads and stores are not allowed. (Hint: Look at Table 3 to see how far apart each element of t2 is in memory).  (<strong>QUESTION 4. ANALYSIS OF MIPS ASSEMBLY PROGRAM  </strong>




<table width="351">

 <tbody>

  <tr>

   <td width="47"><strong>Line </strong></td>

   <td width="85"><strong>Labels </strong></td>

   <td width="219"><strong>Instructions </strong></td>

  </tr>

  <tr>

   <td width="47">1</td>

   <td width="85"> </td>

   <td width="219">addi $1, $0, 0</td>

  </tr>

  <tr>

   <td width="47">2</td>

   <td width="85"> </td>

   <td width="219">add  $3, $20, $1</td>

  </tr>

  <tr>

   <td width="47">3</td>

   <td width="85">loop:</td>

   <td width="219">lw   $4, 0($3)</td>

  </tr>

  <tr>

   <td width="47">4</td>

   <td width="85"> </td>

   <td width="219">srl  $5, $4, 16</td>

  </tr>

  <tr>

   <td width="47">5</td>

   <td width="85"> </td>

   <td width="219">sll  $6, $4, 16</td>

  </tr>

  <tr>

   <td width="47">6</td>

   <td width="85"> </td>

   <td width="219">or   $4, $5, $6</td>

  </tr>

  <tr>

   <td width="47">7</td>

   <td width="85"> </td>

   <td width="219">sw   $4, 0($3)</td>

  </tr>

  <tr>

   <td width="47">8</td>

   <td width="85"> </td>

   <td width="219">addi $1, $1, 1</td>

  </tr>

  <tr>

   <td width="47">9</td>

   <td width="85"> </td>

   <td width="219">slt  $5, $1, $21</td>

  </tr>

  <tr>

   <td width="47">10</td>

   <td width="85"> </td>

   <td width="219">beq  $5, $zero, loop</td>

  </tr>

 </tbody>

</table>




The program above goes through the elements of an integer array whose base address is in register $20, and the number of elements is in register $21. It does something with the data in the array and writes it back.

<ol>

 <li>Unfortunately, this program does not work as intended. Rewrite the program so that it works properly, changing only what is necessary. You may also add instructions but these should be kept to the absolute minimum. You may assume that there are no errors in lines 4 to 6 inclusive and you are NOT allowed to change these lines.</li>

</ol>







<ol>

 <li>How many instructions are executed in the CORRECTED program if $21 = 5?</li>

</ol>




Describe in one sentence what the CORRECTED program does.