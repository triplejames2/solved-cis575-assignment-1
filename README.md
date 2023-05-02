Download Link: https://assignmentchef.com/product/solved-cis575-assignment-1
<br>
We want to write an algorithm that expects an array <em>A</em>[1<em>..n</em>] and a number <em>x</em>, and returns a number <em>q</em>, and that implements the specification <strong>precondition </strong>the array <em>A</em>[1<em>..n</em>] is non-decreasing, and we know that <em>x </em>occurs in <em>A</em>[1<em>..n</em>] <strong>postcondition </strong><em>q </em>∈ 1<em>..n </em>and <em>A</em>[<em>q</em>] = <em>x</em>.

1          2          3          4          5          6

<table width="183">

 <tbody>

  <tr>

   <td width="30">12</td>

   <td width="30">15</td>

   <td width="30">17</td>

   <td width="30">17</td>

   <td width="30">26</td>

   <td width="30">30</td>

  </tr>

 </tbody>

</table>

For example, if <em>A</em>[1<em>..</em>6] is given bythen

<ul>

 <li>if <em>x </em>= 26 then <em>q </em>= 5 must be returned</li>

 <li>if <em>x </em>= 17 then either <em>q </em>= 3 or <em>q </em>= 4 must be returned (the specification is non-deterministic)</li>

 <li>if <em>x </em>= 10 then (as the precondition is not fulfilled) the algorithm could behave in any way; it may return 1, never terminate, or crash…</li>

</ul>

To implement this specification we shall use the binary search principle, and develop an iterative algorithm of the form

Find(<em>x,A,n</em>) <em>P q </em>← (<em>lo </em>+ <em>hi</em>) div 2 <strong>while </strong><em>A</em>[<em>q</em>] 6= <em>x</em>

<strong>if </strong><em>A</em>[<em>q</em>] <em>&lt; x</em>

<em>T</em>

<strong>else</strong>

<em>E q </em>← (<em>lo </em>+ <em>hi</em>) div 2

<strong>return </strong><em>q</em>

which uses variables <em>lo</em>, <em>hi</em>, and <em>q</em>, and where the loop invariant Φ has various parts:

<ul>

 <li><em>A </em>is non-decreasing</li>

 <li>1 ≤ <em>lo </em>≤ <em>hi </em>≤ <em>n</em></li>

 <li><em>lo </em>≤ <em>q </em>≤ <em>hi</em></li>

 <li><em>x </em>occurs in <em>A</em>[<em>.hi</em>]</li>

</ul>

In this exercise, we shall develop <em>P </em>so as to complete the preamble, and develop <em>T </em>and <em>E </em>so as to complete the loop body.

<ol>

 <li><strong>Specification </strong>Translate the precondition into a formula in predicate logic (which must contain quantifiers, universal ∀ and/or existential ∃).</li>

 <li><strong>Preamble </strong>We shall find a suitable <em>P</em>.

  <ol>

   <li>Give an example that shows that letting <em>P </em>be <em>lo </em>← 1; <em>hi </em>← <em>n </em>− 1 may <em>not </em>establish Φ.</li>

   <li>Now define <em>P </em>(as a sequence of assignments) so that Φ will <em>always </em>be established (you don’t need to argue for that).</li>

  </ol></li>

 <li><strong>Loop body </strong>We shall find suitable <em>T </em>and <em>E</em>.

  <ol>

   <li>First consider the case where <em>T </em>is given by <em>hi </em>← <em>q </em>and <em>E </em>is given by <em>lo </em>← <em>q</em>.</li>

  </ol></li>

</ol>

It is quite obvious that this choice will maintain parts (0)–(2) of Φ. But give an example that shows that this may <em>not </em>maintain part (3) of Φ.

<ol start="2">

 <li>Next consider the case where <em>T </em>is given by <em>lo </em>← <em>q </em>and <em>E </em>is given by <em>hi </em>← <em>q</em>.

  <ul>

   <li>Argue that this choice will maintain part (3) of Φ.</li>

   <li>Give an example that shows that with this choice, the loop may <em>not </em></li>

  </ul></li>

 <li>Write <em>T </em>and <em>E </em>such that Φ is maintained <em>and </em>termination is ensured (you do not need to argue for these properties).</li>

</ol>

<ol start="4">

 <li><strong>Recursion (</strong>Translate your completed iterative algorithm into a recursive algorithm that is equivalent, in that it always examines the <em>same </em>array elements.</li>

</ol>

Specifically, you must write a function Find that calls itself (but contains no <strong>while </strong>loop) and which as argument takes at least <em>lo </em>and <em>hi</em>, and <em>perhaps </em>also <em>q</em>, but you <em>may </em>omit the “global” <em>A </em>and <em>x</em>.

Remember also to state how to call Find at “top-level” so as to implement the specification.