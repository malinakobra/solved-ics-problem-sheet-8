Download Link: https://assignmentchef.com/product/solved-ics-problem-sheet-8
<br>
<table width="572">

 <tbody>

  <tr>

   <td width="463"><strong>Problem 8.1: </strong><em>digital circuit analysis</em></td>

   <td width="108"> </td>

  </tr>

 </tbody>

</table>

You are given the following digital circuit. The circuit may as well be found online at <a href="http://simulator.io/board/pu8qlKwg1J/3">http:// </a><a href="http://simulator.io/board/pu8qlKwg1J/3">simulator.io/board/pu8qlKwg1J/3</a> (but there is no guarantee that it persists).

<ol>

 <li>Write down the truth table defining the outputs <em>y</em><sub>0</sub>, <em>y</em><sub>1</sub>, and <em>y</em>.</li>

 <li>Write down the boolean expressions defining <em>y</em><sub>0</sub>, <em>y</em><sub>1</sub>, and <em>y</em>.</li>

 <li>Describe in your own words what the circuit is doing and how it might be used.</li>

</ol>

<strong>Problem 8.2: </strong><em>fold function duality theorems                                                                              </em>

The fold functions compute a value over a list (or some other type that is foldable) by applying an operator to the list elements and a neutral element. The foldl function assumes that the operator is left associative, the foldr function assumes that the operatore is right associative. For example, the function application

1                               foldl (+) 0 [3,5,2,1]

results in the computation of ((((0+3)+5)+2)+1) and the function application

1                               foldr (+) 0 [3,5,2,1]

results in the computation of (3+(5+(2+(1+0)))). The value computed by the fold functions may be more complex than a simple scalar. It is very well possible to construct a new list as part of the fold. For example:

<ul>

 <li>map’ :: (a -&gt; b) -&gt; [a] -&gt; [b]</li>

 <li>map’ f xs = foldr ((:) . f) [] xs</li>

</ul>

The evaluation of map’ succ [1,2,3] results in the list [2,3,4]. There are several duality theorems that can be stated for fold functions. Prove the following three duality theorems:

<ol>

 <li>Let op be an associative operation with e as the neutral element:</li>

</ol>

op is associative: (x op y) op z = x op (y op z) e is neutral element: e op x = x and x op e = x

Then the following holds for finite lists xs:

foldr op e xs = foldl op e xs

<ol>

 <li>Let op1 and op2 be two operations for which

  <ul>

   <li>`op1` (y `op2` z) = (x `op1` y) `op2` zx `op1` e = e `op2` x</li>

  </ul></li>

</ol>

holds. Then the following holds for finite lists xs:

foldr op1 e xs = foldl op2 e xs

<ol>

 <li>Let op be an associative operation and xs a finite list. Then</li>

</ol>

foldr op a xs = foldl op’ a (reverse xs)

holds with

<ul>

 <li>op’ y = y op x</li>

</ul>