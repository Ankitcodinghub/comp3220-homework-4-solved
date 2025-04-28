# comp3220-homework-4-solved
**TO GET THIS SOLUTION VISIT:** [COMP3220 Homework 4 Solved](https://www.ankitcodinghub.com/product/comp3220-homework-summary-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;118109&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;COMP3220 Homework 4 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
For this part of the Ruby Interpreter Collection of Assignments we will be modifying our existing Parser so that instead of printing parser output, it will build an AST (abstract syntax tree) that our interpreter can use to “run” programs written in the Tiny Language.

Details

I have given you all the files necessary to complete the assignment. You will need to modify Parser.rb so that it builds the AST while it is parsing a file.

I have included an AST.rb file that defines an AST node object that can be used to build this tree. It also has a method that can print the tree in list format (convenient since our interpreter will be written in a list-based language!).

You should NOT modify AST.rb unless you are attempting the extra credit (see Extra Credit section below).

I have done some of the work for you in Parser, so that you can use that as an example of how you should proceed. At the end of this document are screenshots showing what correct output should look like given some input files that I will also provide to you for debugging.

Note: We are building an AST and NOT a parse tree. What is the difference anyway!? The difference is that a Parse Tree

parse tree would look much like the examples we went through in class when we compared parse trees to derivations. They would INCLUDE every rule in our class as root nodes or sub nodes in the tree. However, an AST (Abstract Syntax Tree)

AST ONLY includes the actual lexemes that are needed to be interpreted. If you take a look at the compiler series article

here: https://ruslanspivak.com/lsbasi-part1/

, they illustrate that in one of the series articles. Here is the specific article

in the series that introduces AST’s: https://ruslanspivak.com/lsbasi-part7/

.

For our assignment, we will always start with a program node as the root of the whole tree. That is the only “not concrete” thing that should be part of our tree.

Extra Credit (25 pts) – must score 100 to qualify for any extra credit points. Otherwise, you only get 20 pts per test case passed.

Part 1 (5 pts)

Because of the way our grammar is defined (and because we want to produce a tree in list format) our tree WILL be nested correctly BUT our operands will be in reverse order. Since it is something that is consistent, it is an easy problem to handle in our interpreter (we already know it will behave this way, so just read in the operands in reverse order).

However, it is possible to produce the tree in list form with the operands in correct order. In order to do this, you will need to modify the AST.rb class. One way to do this is to:

1) add a method in AST.rb that allows you to swap the first child of a node

2) instead of calling addChild everywhere in Parser.rb, there are at least 2 instances where you will need to call your new custom function instead (maybe called addAsFirstChild).

Part 2 (20 pts)

This potential issue is a bit harder to fix (and describe) and requires that you (1) have a really good understanding of exactly how this AST tree works and (2) how our interpreter is going to process our tree (specifically that any math operator (except for equal) requires at least 2 operands). So, (- 3 4) is ok, but (- 4) is not. Scheme can actually handle this, but our interpreter won’t be able to. See examples below.

To get a really good understanding of how our AST tree is being built, I would recommend studying the toStringList() method in AST.rb to understand how its going through the tree in order to print things. You could then create a second toStringList() in AST.rb that is a modification of the first one. You could attempt to create this second one so that instead of printing the Token AND the Lexeme, it ONLY prints the lexeme. This will actually end up giving you something you can copy and paste into scheme to verify if it’s computing the answer correctly.

Example of the problem:

1 – 2 – 3 – 4 is -8.

You can type that into a calculator and get the correct result. However, you can’t type that into scheme (the way it is written) and get a correct result. Since scheme is a list-based language, it expects that the first item in the list be the operator.

If you don’t attempt the first part of the extra credit (5 pts), this is what your parser will produce. You can get this string exactly, by simply removing the Token names (or by writing a second toStringList() method that will print lexemes only). In this example, we are not reversing first operand (we can handle this in Interpreter). You can paste the partial tree below into scheme and it will produce a result, however, our interpreter will not be able to process it because there is an operator with just a single operand in this list; the inner ( – 4 ).

( – 2 ( – 3 ( – 4 ) ) 1 )  scheme will give you -6 as a result, which is still incorrect, even though it runs

If you do attempt the first part of the extra credit (5 pts), this is what your parser will produce. Note that we STILL have that inner list ( – 4 ) where the minus operator has only a single operand, the 4. Although you could type this expression into scheme and it would give you a correct result, our interpreter will still crash because of the the inner list ( – 4 ).

( – 1 2 ( – 3 ( – 4 ) ) )

Below is what you get 20 points for!

In addition to swapping the first child of some nodes (part 1) you will also occasionally need to “reverse” an entire subtree. You can think about this as if you were “flipping” a sub-tree over, where the bottom (the leaf/leaves) become the new root and the top (the root) becomes the new leaf/leaves. Doing this would produce a tree that scheme could use to correctly calculate a result AND our interpreter will ALSO be able to use the tree to produce the correct output.

Continuing the example above, this method would produce the following list that would be correct for our interpreter. ( – ( – ( – 1 2 ) 3 ) 4 )  I’ll go over this in class

Screenshots No extra credit input1.tiny (20 pts)

input2.tiny (20 pts)

input3.tiny (20 pts)

input4.tiny (this one has syntax errors) (20 pts)

input5.tiny (this one has syntax errors) (20 pts)

Extra credit (5 pts only) – MUST score 100 to get the +5 points, otherwise you simply get 20 pts for each test passed. input1.tiny (20 pts)

input2.tiny (20 pts)

input3.tiny (20 pts)

input4.tiny (this one has syntax errors) (20 pts)

input5.tiny (this one has syntax errors) (20 pts)

Extra credit (20 pts) – MUST score 100 AND get 5 pts extra credit to qualify for these points. MUST pass BOTH test cases below to earn the additional 20 points. input6.tiny

input7.tiny
