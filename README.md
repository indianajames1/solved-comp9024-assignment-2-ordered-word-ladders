Download Link: https://assignmentchef.com/product/solved-comp9024-assignment-2-ordered-word-ladders
<br>
<strong>Assignment 2: Ordered Word Ladders</strong>

An <em>ordered word ladder</em> (‘owl’) is an alphabetically-ordered sequence of words where each word in the sequence differs from its predecessor by one action:

<ol>

 <li>changing one letter, e.g. <em>barn</em>→<em>born</em></li>

 <li>adding or removing one letter, e.g. <em>band</em>→<em>brand</em> and <em>bran</em>→<em>ran</em></li>

</ol>

The following are examples of word ladders of different length: <em>ban</em>→<em>bar</em>→<em>boar</em>→<em>boat</em>→<em>goat</em>, length 5

<em>an</em>→<em>can</em>→<em>cane</em>→<em>dane</em>→<em>date</em>→<em>mate</em>→<em>mite</em>→<em>site</em>→<em>size</em>, length 9

<h1>Phase 1</h1>

At the heart of the assignment is a function that compares 2 arbitrary null-terminated strings and returns <em>true</em> if the strings satisfy one of the 2 conditions above, and <em>false</em> otherwise. This function has signature:

<table width="605">

 <tbody>

  <tr>

   <td width="605">切换⾏号显⽰</td>

  </tr>

  <tr>

   <td width="605">   1 bool differByOne(char *, char *)</td>

  </tr>

 </tbody>

</table>

Write such a function and of course test it.

<h1>Phase 2</h1>

Generate a graph that represents all the words in the input that <em>differ by one</em>. Each word is represented by a vertex in the graph, and vertices are adjacent if the corresponding words <em>differ by one</em>. For example, if a dictionary consists of the 7 words an ban bean ben hen mean men then the graph that represents all <em>ordered word ladders</em> would be drawn as:

0

|

1

/   

2 — 3

|    /            5—6—4

where the vertices 0..6 represent the 7 words in the given order. There are lots of ordered word ladders in this graph: for example, 0→1→2→5 representing <em>an</em>→<em>ban</em>→<em>bean</em>→<em>mean</em>. Any path between any two vertices in the graph is an <em>owl</em>, but notice that, although the edges are undirected, you can select vertices only in ascending order (the ladders must be in dictionary order).

In this phase of the assignment you are asked to create a graph for a dictionary, and simply print the graph.

<strong> Input</strong> The words in the dictionary should be read from <em>stdin</em>. There will be <em>whitespace </em>between the words (i.e. spaces, tabs, newlines). You may assume that the words are in lower-case letters (so there are no capital letters, punctuation, hyphens …) You may assume also the words are sorted in dictionary order. For example, an input file could consist of:

an ban bean ben hen mean men

You should use the <em>Graph ADT</em> from lectures to build your graph (I will be using the <em>Adjacency Matrix</em> version), and you are welcome to use any part of the <em>readGraph.c </em>program from lectures as well. You do not have to check the input for correctness (that is not what this assignment is about), so your program does not be have to handle ‘bad’ input (except for handling <em>whitespace</em>).

<strong> Output</strong> Print the dictionary and the resulting graph (using <em>showGraph()</em> from the ADT). For the example above, the output of your program should look like:

Dictionary

0: an

1: ban

2: bean

3: ben

4: hen

5: mean

6: men

Ordered Word Ladder Graph

V=7, E=9

&lt;0 1&gt;

&lt;1 0&gt; &lt;1 2&gt; &lt;1 3&gt;

&lt;2 1&gt; &lt;2 3&gt; &lt;2 5&gt;

&lt;3 1&gt; &lt;3 2&gt; &lt;3 4&gt; &lt;3 6&gt;

&lt;4 3&gt; &lt;4 6&gt;

&lt;5 2&gt; &lt;5 6&gt;

&lt;6 3&gt; &lt;6 4&gt; &lt;6 5&gt;

You may also assume in the assignment that the length of dictionary words is less than or equal to 20, and that there will not be more than 1000 nodes in the graph.

<h1>Phase 3</h1>

In this phase you need to find the length of the longest <em>owl</em> in the graph, which corresponds to finding the maximal path in the graph.

You should first concentrate on dictionaries that have a single longest path, as in the dictionary above, which has one ladder of length 6, namely 0→1→2→3→4→6, and no other paths are longer. When you have determined the longest <em>owl</em>, print its length and the corresponding path as follows:

Maximum ladder length: 6

Maximal ladders:

1: an -&gt; ban -&gt; bean -&gt; ben -&gt; hen -&gt; men

This output appears directly after the output above of course. Note that in general the maximal path may start at any vertex in the graph.

Now address the problem of finding all the paths that have the longest length. All these paths should be output.

For example, the input file an at in it on generates the following output:

Dictionary

0: an

1: at

2: in

3: it

4: on

Ordered Word Ladder Graph

V=5, E=6

&lt;0 1&gt; &lt;0 2&gt; &lt;0 4&gt;

&lt;1 0&gt; &lt;1 3&gt;

&lt;2 0&gt; &lt;2 3&gt; &lt;2 4&gt;

&lt;3 1&gt; &lt;3 2&gt;

&lt;4 0&gt; &lt;4 2&gt;

Longest ladder length: 3

Longest ladders:

1: an -&gt; at -&gt; it

2: an -&gt; in -&gt; it

3: an -&gt; in -&gt; on

You see there are 3 <em>owls</em> here that have maximal length.

To test your program, you should create your own small dictionaries. If you want to see more of my examples see the links below.

<ol>

 <li><a href="https://wiki.cse.unsw.edu.au/cs9024cgi/19T2/Assignment2Ex1">‘case’ example, 4 longest ladders</a></li>

 <li><a href="https://wiki.cse.unsw.edu.au/cs9024cgi/19T2/Assignment2Ex2">‘bear’ example, 1 longest ladder</a></li>

 <li><a href="https://wiki.cse.unsw.edu.au/cs9024cgi/19T2/Assignment2Ex3">‘aaaa’ example, 24 longest ladders</a></li>

</ol>

Assignment2