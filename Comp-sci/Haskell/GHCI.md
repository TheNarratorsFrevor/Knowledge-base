<h2>Ready, set, go!</h2>
<p>
<img src="http://s3.amazonaws.com/lyah/startingout.png" class="right" alt="egg" width="214" height="187">
Alright, let's get started! If you're the sort of horrible person who doesn't read introductions to things and you skipped it, you might want to read the last section in the introduction anyway because it explains what you need to follow this tutorial and how we're going to load functions. The first thing we're going to do is run ghc's interactive mode and call some function to get a very basic feel for haskell. Open your terminal and type in <span class="fixed">ghci</span>. You will be greeted with something like this.
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="type_constructors">GHCi</span><span>,&nbsp;version&nbsp;</span><span class="numbers">6.8</span><span>.</span><span class="numbers">2</span><span>:&nbsp;http://www.haskell.org/ghc/&nbsp;&nbsp;:?&nbsp;for&nbsp;help&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">Loading</span><span>&nbsp;package&nbsp;base&nbsp;...&nbsp;linking&nbsp;...&nbsp;done.&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="type_constructors">Prelude</span><span>&gt;&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">GHCi, version 6.8.2: http://www.haskell.org/ghc/  :? for help
Loading package base ... linking ... done.
Prelude&gt;</pre>
<p>
Congratulations, you're in GHCI! The prompt here is <span class="fixed">Prelude&gt;</span> but because it can get longer when you load stuff into the session, we're going to use <span class="fixed">ghci&gt;</span>. If you want to have the same prompt, just type in <span class="fixed">:set prompt "ghci&gt; "</span>. 
</p>
<p>
Here's some simple arithmetic.
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">2</span><span class="common_operators">&nbsp;+&nbsp;</span><span class="numbers">15</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">17</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">49</span><span class="common_operators">&nbsp;*&nbsp;</span><span class="numbers">100</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">4900</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">1892</span><span class="common_operators">&nbsp;-&nbsp;</span><span class="numbers">1472</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">420</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">5</span><span class="common_operators">&nbsp;/&nbsp;</span><span class="numbers">2</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">2.5</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">ghci&gt; 2 + 15
17
ghci&gt; 49 * 100
4900
ghci&gt; 1892 - 1472
420
ghci&gt; 5 / 2
2.5
ghci&gt;</pre>
<p>
This is pretty self-explanatory. We can also use several operators on one line and all the usual precedence rules are obeyed. We can use parentheses to make the precedence explicit or to change it.
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;(</span><span class="numbers">50</span><span class="common_operators">&nbsp;*&nbsp;</span><span class="numbers">100</span><span>)</span><span class="common_operators">&nbsp;-&nbsp;</span><span class="numbers">4999</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">1</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">50</span><span class="common_operators">&nbsp;*&nbsp;</span><span class="numbers">100</span><span class="common_operators">&nbsp;-&nbsp;</span><span class="numbers">4999</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">1</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">50</span><span class="common_operators">&nbsp;*&nbsp;</span><span>(</span><span class="numbers">100</span><span class="common_operators">&nbsp;-&nbsp;</span><span class="numbers">4999</span><span>)&nbsp;&nbsp;</span></span></li><li class=""><span>-<span class="numbers">244950</span><span>&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">ghci&gt; (50 * 100) - 4999
1
ghci&gt; 50 * 100 - 4999
1
ghci&gt; 50 * (100 - 4999)
-244950</pre>
<p>
Pretty cool, huh? Yeah, I know it's not but bear with me. A little pitfall to watch out for here is negating numbers. If we want to have a negative number, it's always best to surround it with parentheses. Doing <span class="fixed">5 * -3</span> will make GHCI yell at you but doing <span class="fixed">5 * (-3)</span> will work just fine.
</p>
<p>
Boolean algebra is also pretty straightforward. As you probably know, <span class="fixed">&amp;&amp;</span> means a boolean <i>and</i>, <span class="fixed">||</span> means a boolean <i>or</i>. <span class="fixed">not</span> negates a <span class="fixed">True</span> or a <span class="fixed">False</span>.
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="type_constructors">True</span><span>&nbsp;&amp;&amp;&nbsp;</span><span class="type_constructors">False</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">False</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="type_constructors">True</span><span>&nbsp;&amp;&amp;&nbsp;</span><span class="type_constructors">True</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">True</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="type_constructors">False</span><span>&nbsp;||&nbsp;</span><span class="type_constructors">True</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">True</span><span>&nbsp;&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;not&nbsp;</span><span class="type_constructors">False</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">True</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;not&nbsp;(</span><span class="type_constructors">True</span><span>&nbsp;&amp;&amp;&nbsp;</span><span class="type_constructors">True</span><span>)&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">False</span><span>&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">ghci&gt; True &amp;&amp; False
False
ghci&gt; True &amp;&amp; True
True
ghci&gt; False || True
True 
ghci&gt; not False
True
ghci&gt; not (True &amp;&amp; True)
False</pre>
<p>
Testing for equality is done like so.
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">5</span><span class="common_operators">&nbsp;==&nbsp;</span><span class="numbers">5</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">True</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">1</span><span class="common_operators">&nbsp;==&nbsp;</span><span class="numbers">0</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">False</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">5</span><span class="common_operators">&nbsp;/=&nbsp;</span><span class="numbers">5</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">False</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="numbers">5</span><span class="common_operators">&nbsp;/=&nbsp;</span><span class="numbers">4</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">True</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;</span><span class="string">"hello"</span><span class="common_operators">&nbsp;==&nbsp;</span><span class="string">"hello"</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">True</span><span>&nbsp;&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">ghci&gt; 5 == 5
True
ghci&gt; 1 == 0
False
ghci&gt; 5 /= 5
False
ghci&gt; 5 /= 4
True
ghci&gt; "hello" == "hello"
True </pre>
<p>
What about doing <span class="fixed">5 + "llama"</span> or <span class="fixed">5 == True</span>? Well, if we try the first snippet, we get a big scary error message!
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="type_constructors">No</span><span>&nbsp;</span><span class="keyword2">instance</span><span>&nbsp;for&nbsp;(</span><span class="type_constructors">Num</span><span>&nbsp;[</span><span class="type_constructors">Char</span><span>])&nbsp;&nbsp;</span></span></li><li class=""><span>arising&nbsp;from&nbsp;a&nbsp;use&nbsp;<span class="keyword">of</span><span>&nbsp;`+'&nbsp;at&nbsp;&lt;interactive&gt;:</span><span class="numbers">1</span><span>:</span><span class="numbers">0</span><span>-</span><span class="numbers">9</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="type_constructors">Possible</span><span>&nbsp;fix:&nbsp;add&nbsp;an&nbsp;</span><span class="keyword2">instance</span><span>&nbsp;declaration&nbsp;for&nbsp;(</span><span class="type_constructors">Num</span><span>&nbsp;[</span><span class="type_constructors">Char</span><span>])&nbsp;&nbsp;</span></span></li><li class=""><span><span class="type_constructors">In</span><span>&nbsp;the&nbsp;expression:&nbsp;</span><span class="numbers">5</span><span class="common_operators">&nbsp;+&nbsp;</span><span class="string">"llama"</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="type_constructors">In</span><span>&nbsp;the&nbsp;definition&nbsp;</span><span class="keyword">of</span><span>&nbsp;`it':&nbsp;it</span><span class="common_operators">&nbsp;=&nbsp;</span><span class="numbers">5</span><span class="common_operators">&nbsp;+&nbsp;</span><span class="string">"llama"</span><span>&nbsp;&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">No instance for (Num [Char])
arising from a use of `+' at &lt;interactive&gt;:1:0-9
Possible fix: add an instance declaration for (Num [Char])
In the expression: 5 + "llama"
In the definition of `it': it = 5 + "llama" </pre>
<p>
Yikes! What GHCI is telling us here is that <span class="fixed">"llama"</span> is not a number and so it doesn't know how to add it to 5. Even if it wasn't <span class="fixed">"llama"</span> but <span class="fixed">"four"</span> or <span class="fixed">"4"</span>, Haskell still wouldn't consider it to be a number. <span class="fixed">+</span> expects its left and right side to be numbers. If we tried to do <span class="fixed">True == 5</span>, GHCI would tell us that the types don't match. Whereas <span class="fixed">+</span> works only on things that are considered numbers, <span class="fixed">==</span> works on any two things that can be compared. But the catch is that they both have to be the same type of thing. You can't compare apples and oranges. We'll take a closer look at types a bit later. Note: you can do <span class="fixed">5 + 4.0</span> because <span class="fixed">5</span> is sneaky and can act like an integer or a floating-point number. <span class="fixed">4.0</span> can't act like an integer, so <span class="fixed">5</span> is the one that has to adapt.
</p>
<p>
You may not have known it but we've been using functions now all along. For instance, <span class="fixed">*</span> is a function that takes two numbers and multiplies them. As you've seen, we call it by sandwiching it between them. This is what we call an <i>infix</i> function. Most functions that aren't used with numbers are <i>prefix</i> functions. Let's take a look at them. 
</p>
<p>
<img src="http://s3.amazonaws.com/lyah/ringring.png" alt="phoen" class="right" width="160" height="161">
Functions are usually prefix so from now on we won't explicitly state that a function is of the prefix form, we'll just assume it. In most imperative languages functions are called by writing the function name and then writing its parameters in parentheses, usually separated by commas. In Haskell, functions are called by writing the function name, a space and then the parameters, separated by spaces. For a start, we'll try calling one of the most boring functions in Haskell.
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;succ&nbsp;</span><span class="numbers">8</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">9</span><span>&nbsp;&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">ghci&gt; succ 8
9 </pre>
<p>
The <span class="fixed">succ</span> function takes anything that has a defined successor and returns that successor. As you can see, we just separate the function name from the parameter with a space. Calling a function with several parameters is also simple. The functions <span class="fixed">min</span> and <span class="fixed">max</span> take two things that can be put in an order (like numbers!). <span class="fixed">min</span> returns the one that's lesser and <span class="fixed">max</span> returns the one that's greater. See for yourself:
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;min&nbsp;</span><span class="numbers">9</span><span>&nbsp;</span><span class="numbers">10</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">9</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;min&nbsp;</span><span class="numbers">3.4</span><span>&nbsp;</span><span class="numbers">3.2</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">3.2</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;max&nbsp;</span><span class="numbers">100</span><span>&nbsp;</span><span class="numbers">101</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">101</span><span>&nbsp;&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">ghci&gt; min 9 10
9
ghci&gt; min 3.4 3.2
3.2
ghci&gt; max 100 101
101 </pre>

<p>
Function application (calling a function by putting a space after it and then typing out the parameters) has the highest precedence of them all. What that means for us is that these two statements are equivalent.
</p>
<div class="dp-highlighter nogutter"><div class="bar"></div><ol class="dp-hs" start="1"><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;succ&nbsp;</span><span class="numbers">9</span><span class="common_operators">&nbsp;+&nbsp;</span><span>max&nbsp;</span><span class="numbers">5</span><span>&nbsp;</span><span class="numbers">4</span><span class="common_operators">&nbsp;+&nbsp;</span><span class="numbers">1</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">16</span><span>&nbsp;&nbsp;</span></span></li><li class="alt"><span><span class="ghci">ghci&gt;</span><span>&nbsp;(succ&nbsp;</span><span class="numbers">9</span><span>)</span><span class="common_operators">&nbsp;+&nbsp;</span><span>(max&nbsp;</span><span class="numbers">5</span><span>&nbsp;</span><span class="numbers">4</span><span>)</span><span class="common_operators">&nbsp;+&nbsp;</span><span class="numbers">1</span><span>&nbsp;&nbsp;</span></span></li><li class=""><span><span class="numbers">16</span><span>&nbsp;&nbsp;</span></span></li></ol></div><pre name="code" class="haskell: ghci" style="display: none;">ghci&gt; succ 9 + max 5 4 + 1
16
ghci&gt; (succ 9) + (max 5 4) + 1
16
</pre>
<p>
However, if we wanted to get the successor of the product of numbers 9 and 10, we couldn't write <span class="fixed">succ 9 * 10</span> because that would get the successor of 9, which would then be multiplied by 10. So 100. We'd have to write <span class="fixed">succ (9 * 10)</span> to get 91.
</p>
<p>If a function takes two parameters, we can also call it as an infix function by surrounding it with backticks. For instance, the <span class="fixed">div</span> function takes two integers and does integral division between them. Doing <span class="fixed">div 92 10</span> results in a 9. But when we call it like that, there may be some confusion as to which number is doing the division and which one is being divided. So we can call it as an infix function by doing <span class="fixed">92 `div` 10</span> and suddenly it's much clearer. </p>
<p>Lots of people who come from imperative languages tend to stick to the notion that parentheses should denote function application. For example, in C, you use parentheses to call functions like <span class="fixed">foo()</span>, <span class="fixed">bar(1)</span> or <span class="fixed">baz(3, "haha")</span>. Like we said, spaces are used for function application in Haskell. So those functions in Haskell would be <span class="fixed">foo</span>, <span class="fixed">bar 1</span> and <span class="fixed">baz 3 "haha"</span>. So if you see something like <span class="fixed">bar (bar 3)</span>, it doesn't mean that <span class="fixed">bar</span> is called with <span class="fixed">bar</span> and <span class="fixed">3</span> as parameters. It means that we first call the function <span class="fixed">bar</span> with <span class="fixed">3</span> as the parameter to get some number and then we call <span class="fixed">bar</span> again with that number. In C, that would be something like <span class="fixed">bar(bar(3))</span>.</p>