<body>

<hr>
<h1 data-number="63" id="stdnoreturn"><span class="header-section-number">63</span>
<code>&lt;stdnoreturn.h&gt;</code> Macros for Non-Returning
Functions</h1>
<p>This header provides a macro <code>noreturn</code> that is a handy
alias for <a href="function-specifiers-alignment-specifiersoperators.html#noreturn"><code>_Noreturn</code></a>.</p>
<p>Use this macro to indicate to the compiler that a function will never
return to the caller. It’s undefined behavior if the so-marked function
does return.</p>
<p>Here’s a usage example:</p>
<div class="sourceCode" id="cb1374"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1374-1"><a href="stdnoreturn.html#cb1374-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1374-2"><a href="stdnoreturn.html#cb1374-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1374-3"><a href="stdnoreturn.html#cb1374-3"></a><span class="pp">#include </span><span class="im">&lt;stdnoreturn.h&gt;</span></span>
<span id="cb1374-4"><a href="stdnoreturn.html#cb1374-4"></a></span>
<span id="cb1374-5"><a href="stdnoreturn.html#cb1374-5"></a>noreturn <span class="dt">void</span> foo<span class="op">(</span><span class="dt">void</span><span class="op">)</span> <span class="co">// This function should never return!</span></span>
<span id="cb1374-6"><a href="stdnoreturn.html#cb1374-6"></a><span class="op">{</span></span>
<span id="cb1374-7"><a href="stdnoreturn.html#cb1374-7"></a>    printf<span class="op">(</span><span class="st">"Happy days</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1374-8"><a href="stdnoreturn.html#cb1374-8"></a></span>
<span id="cb1374-9"><a href="stdnoreturn.html#cb1374-9"></a>    exit<span class="op">(</span><span class="dv">1</span><span class="op">);</span>            <span class="co">// And it doesn't return--it exits here!</span></span>
<span id="cb1374-10"><a href="stdnoreturn.html#cb1374-10"></a><span class="op">}</span></span>
<span id="cb1374-11"><a href="stdnoreturn.html#cb1374-11"></a></span>
<span id="cb1374-12"><a href="stdnoreturn.html#cb1374-12"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1374-13"><a href="stdnoreturn.html#cb1374-13"></a><span class="op">{</span></span>
<span id="cb1374-14"><a href="stdnoreturn.html#cb1374-14"></a>    foo<span class="op">();</span></span>
<span id="cb1374-15"><a href="stdnoreturn.html#cb1374-15"></a><span class="op">}</span></span></code></pre></div>
<p>That’s all there is to it.</p>


</body>