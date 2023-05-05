Download Link: https://assignmentchef.com/product/solved-ct5132-ct5148-lab-week-8
<br>






<strong>Finite State Machines</strong>

The Pacman ghost FSM was very simplified. It had no actions, just transitions from one state to another.

We’re now going to use an FSM to model the behaviour of a vending machine. The rules are:

<ol>

 <li>Each drink costs EUR3.</li>

 <li>The only coins allowed are EUR1 and EUR2.</li>

 <li>If the customer enters too much money, we just return it.</li>

 <li>If the customer enters the right amount, they can then select a drink, and we vend it.</li>

</ol>

How should we model this as an FSM? Let’s draw it on paper. Issues to think about:

<ul>

 <li>What are the states?</li>

 <li>What are the possible inputs?</li>

 <li>Are there actions?</li>

</ul>

Here is some code which implements a general FSM (also in Bb <sub>fsm.py</sub>):

<table width="632">

 <tbody>

  <tr>

   <td width="632"><strong>def </strong>fsm(SISAs, start_state, end_states, input_symbols): state <strong>= </strong>start_state<em># (current_state, input_symbol) -&gt; (next_state, action) </em><strong>for </strong>input_symbol <strong>in </strong>input_symbols:<strong>yield </strong>state <strong>if </strong>state <strong>in </strong>end_states:<strong>break</strong><strong>try</strong>:state, action <strong>= </strong>SISAs[state, input_symbol] <strong>if </strong>action <strong>is not </strong>None <strong>and </strong>callable(action):action() <strong>except </strong><em>KeyError</em>:<strong>pass </strong><em># stay in same state</em></td>

  </tr>

 </tbody>

</table>

Implement our vending machine FSM as a data structure <sub>SISAs</sub>, and confirm that it works by passing in various possible sequences of inputs. E.g. with input <sub>[1, 1, 1]</sub>, we should see that the FSM says <sub>vend </sub>drink at the end and comes back to state <sub>0</sub>.

<strong>What was the most important family in Renaissance Florence?</strong>

This is a short demo of <strong>betweenness centrality </strong>in <sub>networkx</sub>. Betweenness centrality is one way to measure how important each node in a graph is, due to being on the paths between other nodes. We don’t need to understand the maths, but let’s see how to use <sub>networkx </sub>for this.

Figure 1: This graph represents the <strong><sub>marriages </sub></strong>between important families in Renaissance Florence (Padgett, figure from Hanneman and Riddle):

Suppose we are given the data in this format (<sub>florentine_families.csv</sub>):

Acciaiuoli,Medici

Medici,Barbadori

Medici,Ridolfi

Medici,Tornabuoni

Medici,Albizzi

Medici,Salviati

Castellani,Peruzzi

Castellani,Strozzi

Castellani,Barbadori

Peruzzi,Strozzi

Peruzzi,Bischeri

Strozzi,Ridolfi

Strozzi,Bischeri

Ridolfi,Tornabuoni

Tornabuoni,Guadagni

Albizzi,Ginori

Albizzi,Guadagni

Salviati,Pazzi

Bischeri,Guadagni

Guadagni,Lamberteschi

<ol>

 <li>Import networkx.</li>

 <li>Create an empty graph. Should it be directed or undirected for this data?</li>

 <li>Add the edges.</li>

 <li>Look up how to calculate betweenness centrality in <sub>networkx</sub>, and call it.</li>

 <li>Which family seems the most important? Can you interpret this from the graph?</li>

 <li>Optional homework: there are other measures of centrality, e.g. <strong><sub>eigenvector centrality</sub></strong>, related to Google PageRank. Try them out. Do they all agree?</li>

 <li>Optional homework: use <sub>networkx </sub>to make an image of the graph.</li>

</ol>