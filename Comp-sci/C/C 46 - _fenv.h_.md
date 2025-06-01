<body>
<hr>
<h1 data-number="46" id="fenv"><span class="header-section-number">46</span> <code>&lt;fenv.h&gt;</code>
Floating Point Exceptions and Environment</h1>
<table>
<colgroup>
<col style="width: 26%">
<col style="width: 73%">
</colgroup>
<thead>
<tr class="header">
<th>Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="fenv.html#man-feclearexcept"><code>feclearexcept()</code></a></td>
<td>Clear floating point exceptions</td>
</tr>
<tr class="even">
<td><a href="#man-fegetexceptflag"><code>fegetexceptflag()</code></a></td>
<td>Save the floating point exception flags</td>
</tr>
<tr class="odd">
<td><a href="#man-fegetexceptflag"><code>fesetexceptflag()</code></a></td>
<td>Restore the floating point exception flags</td>
</tr>
<tr class="even">
<td><a href="fenv.html#man-feraiseexcept"><code>feraiseexcept()</code></a></td>
<td>Raise a floating point exception through software</td>
</tr>
<tr class="odd">
<td><a href="fenv.html#man-fetestexcept"><code>fetestexcept()</code></a></td>
<td>Test to see if an exception has occurred</td>
</tr>
<tr class="even">
<td><a href="fenv.html#man-fegetround"><code>fegetround()</code></a></td>
<td>Get the rounding direction</td>
</tr>
<tr class="odd">
<td><a href="fenv.html#man-fegetround"><code>fesetround()</code></a></td>
<td>Set the rounding direction</td>
</tr>
<tr class="even">
<td><a href="fenv.html#man-fegetenv"><code>fegetenv()</code></a></td>
<td>Save the entire floating point environment</td>
</tr>
<tr class="odd">
<td><a href="fenv.html#man-fegetenv"><code>fesetenv()</code></a></td>
<td>Restore the entire floating point environment</td>
</tr>
<tr class="even">
<td><a href="fenv.html#man-feholdexcept"><code>feholdexcept()</code></a></td>
<td>Save floating point state and install non-stop mode</td>
</tr>
<tr class="odd">
<td><a href="fenv.html#man-feupdateenv"><code>feupdateenv()</code></a></td>
<td>Restore floating point environment and apply recent exceptions</td>
</tr>
</tbody>
</table>
<h2 data-number="46.1" id="types-and-macros"><span class="header-section-number">46.1</span> Types and Macros</h2>
<p>There are two types defined in this header:</p>
<table>
<thead>
<tr class="header">
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>fenv_t</code></td>
<td>The entire floating point environment</td>
</tr>
<tr class="even">
<td><code>fexcept_t</code></td>
<td>A set of floating point exceptions</td>
</tr>
</tbody>
</table>
<p>The “environment” can be thought of as the status at this moment of
the floating point processing system: this includes the exceptions,
rounding, etc. It’s an opaque type, so you won’t be able to access it
directly, and it must be done through the proper functions.</p>
<p>If the functions in question exist on your system (they might not
be!), then you’ll also have these macros defined to represent different
exceptions:</p>
<table>
<thead>
<tr class="header">
<th>Macro</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>FE_DIVBYZERO</code></td>
<td>Division by zero</td>
</tr>
<tr class="even">
<td><code>FE_INEXACT</code></td>
<td>Result was not exact, was rounded</td>
</tr>
<tr class="odd">
<td><code>FE_INVALID</code></td>
<td>Domain error</td>
</tr>
<tr class="even">
<td><code>FE_OVERFLOW</code></td>
<td>Numeric overflow</td>
</tr>
<tr class="odd">
<td><code>FE_UNDERFLOW</code></td>
<td>Numeric underflow</td>
</tr>
<tr class="even">
<td><code>FE_ALL_EXCEPT</code></td>
<td>All of the above combined</td>
</tr>
</tbody>
</table>
<p>The idea is that you can bitwise-OR these together to represent
multiple exceptions, e.g.&nbsp;<code>FE_INVALID|FE_OVERFLOW</code>.</p>
<p>The functions, below, that have an <code>excepts</code> parameter
will take these values.</p>
<p>See <a href="math.html"><code>&lt;math.h&gt;</code></a> for which
functions raise which exceptions and when.</p>
<h2 data-number="46.2" id="pragmas"><span class="header-section-number">46.2</span> Pragmas</h2>
<p>Normally C is free to optimize all kinds of stuff that might cause
the flags to not look like you might expect. So if you’re going to use
this stuff, be sure to set this pragma:</p>
<div class="sourceCode" id="cb916"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb916-1"><a href="fenv.html#cb916-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#pragma STDC FENV_ACCESS ON</span></span></code></pre></div>
<p>If you do this at global scope, it remains in effect until you turn
it off:</p>
<div class="sourceCode" id="cb917"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb917-1"><a href="fenv.html#cb917-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#pragma STDC FENV_ACCESS OFF</span></span></code></pre></div>
<p>If you do it in block scope, it has to come before any statements or
declarations. In this case, it has effect until the block ends (or until
it is explicitly turned off.)</p>
<p><strong>A caveat</strong>: this program isn’t supported on either of
the compilers I have (gcc and clang) as of this writing, so though I
have built the code, below, it’s not particularly well-tested.</p>
<hr>
<h2 data-number="46.3" id="man-feclearexcept"><span class="header-section-number">46.3</span>
<code>feclearexcept()</code></h2>
<p>Clear floating point exceptions</p>
<h3 class="unnumbered unlisted" id="synopsis-40">Synopsis</h3>
<div class="sourceCode" id="cb918"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb918-1"><a href="fenv.html#cb918-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb918-2"><a href="fenv.html#cb918-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb918-3"><a href="fenv.html#cb918-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> feclearexcept<span class="op">(</span><span class="dt">int</span> excepts<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-40">Description</h3>
<p>If a floating point exception has occurred, this function can clear
it.</p>
<p>Set <code>excepts</code> to a bitwise-OR list of exceptions to
clear.</p>
<p>Passing <code>0</code> has no effect.</p>
<h3 class="unnumbered unlisted" id="return-value-39">Return Value</h3>
<p>Returns <code>0</code> on success and non-zero on failure.</p>
<h3 class="unnumbered unlisted" id="example-40">Example</h3>
<div class="sourceCode" id="cb919"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb919-1"><a href="fenv.html#cb919-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb919-2"><a href="fenv.html#cb919-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb919-3"><a href="fenv.html#cb919-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb919-4"><a href="fenv.html#cb919-4"></a></span>
<span id="cb919-5"><a href="fenv.html#cb919-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb919-6"><a href="fenv.html#cb919-6"></a><span class="op">{</span></span>
<span id="cb919-7"><a href="fenv.html#cb919-7"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb919-8"><a href="fenv.html#cb919-8"></a></span>
<span id="cb919-9"><a href="fenv.html#cb919-9"></a>    <span class="dt">double</span> f <span class="op">=</span> sqrt<span class="op">(-</span><span class="dv">1</span><span class="op">);</span></span>
<span id="cb919-10"><a href="fenv.html#cb919-10"></a></span>
<span id="cb919-11"><a href="fenv.html#cb919-11"></a>    <span class="dt">int</span> r <span class="op">=</span> feclearexcept<span class="op">(</span>FE_INVALID<span class="op">);</span></span>
<span id="cb919-12"><a href="fenv.html#cb919-12"></a></span>
<span id="cb919-13"><a href="fenv.html#cb919-13"></a>    printf<span class="op">(</span><span class="st">"%d %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">,</span> f<span class="op">);</span></span>
<span id="cb919-14"><a href="fenv.html#cb919-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-37">See Also</h3>
<p><a href="fenv.html#man-feraiseexcept"><code>feraiseexcept()</code></a>, <a href="#man-fetestexcept"><code>fetestexcept()</code></a></p>
<hr>
<h2 data-number="46.4" id="man-fegetexceptflag"><span class="header-section-number">46.4</span> <code>fegetexceptflag()</code>
<code>fesetexceptflag()</code></h2>
<p>Save or restore the floating point exception flags</p>
<h3 class="unnumbered unlisted" id="synopsis-41">Synopsis</h3>
<div class="sourceCode" id="cb920"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb920-1"><a href="fenv.html#cb920-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb920-2"><a href="fenv.html#cb920-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb920-3"><a href="fenv.html#cb920-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fegetexceptflag<span class="op">(</span>fexcept_t <span class="op">*</span>flagp<span class="op">,</span> <span class="dt">int</span> excepts<span class="op">);</span></span>
<span id="cb920-4"><a href="fenv.html#cb920-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb920-5"><a href="fenv.html#cb920-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fesetexceptflag<span class="op">(</span>fexcept_t <span class="op">*</span>flagp<span class="op">,</span> <span class="dt">int</span> excepts<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-41">Description</h3>
<p>Use these functions to save or restore the current floating point
environment in a variable.</p>
<p>Set <code>excepts</code> to the set of exceptions you want to save or
restore the state of. Setting it to <code>FE_ALL_EXCEPT</code> will save
or restore the entire state.</p>
<p>Note that <code>fexcept_t</code> is an opaque type—you don’t know
what’s in it.</p>
<p><code>excepts</code> can be set to zero for no effect.</p>
<h3 class="unnumbered unlisted" id="return-value-40">Return Value</h3>
<p>Returns <code>0</code> on success or if <code>excepts</code> is
zero.</p>
<p>Returns non-zero on failure.</p>
<h3 class="unnumbered unlisted" id="example-41">Example</h3>
<p>This program saves the state (before any error has happened), then
deliberately causes a domain error by trying to take <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msqrt><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.134em;"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-box></mjx-sqrt></mjx-msqrt></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msqrt><mo>−</mo><mn>1</mn></msqrt></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>After that, it restores the floating point state to before the error
had occurred, thereby clearing it.</p>
<div class="sourceCode" id="cb921"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb921-1"><a href="fenv.html#cb921-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb921-2"><a href="fenv.html#cb921-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb921-3"><a href="fenv.html#cb921-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb921-4"><a href="fenv.html#cb921-4"></a></span>
<span id="cb921-5"><a href="fenv.html#cb921-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb921-6"><a href="fenv.html#cb921-6"></a><span class="op">{</span></span>
<span id="cb921-7"><a href="fenv.html#cb921-7"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb921-8"><a href="fenv.html#cb921-8"></a></span>
<span id="cb921-9"><a href="fenv.html#cb921-9"></a>    fexcept_t flag<span class="op">;</span></span>
<span id="cb921-10"><a href="fenv.html#cb921-10"></a></span>
<span id="cb921-11"><a href="fenv.html#cb921-11"></a>    fegetexceptflag<span class="op">(&amp;</span>flag<span class="op">,</span> FE_ALL_EXCEPT<span class="op">);</span>  <span class="co">// Save state</span></span>
<span id="cb921-12"><a href="fenv.html#cb921-12"></a></span>
<span id="cb921-13"><a href="fenv.html#cb921-13"></a>    <span class="dt">double</span> f <span class="op">=</span> sqrt<span class="op">(-</span><span class="dv">1</span><span class="op">);</span>                    <span class="co">// I imagine this won't work</span></span>
<span id="cb921-14"><a href="fenv.html#cb921-14"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> f<span class="op">);</span>                      <span class="co">// "nan"</span></span>
<span id="cb921-15"><a href="fenv.html#cb921-15"></a></span>
<span id="cb921-16"><a href="fenv.html#cb921-16"></a>    <span class="cf">if</span> <span class="op">(</span>fetestexcept<span class="op">(</span>FE_INVALID<span class="op">))</span></span>
<span id="cb921-17"><a href="fenv.html#cb921-17"></a>        printf<span class="op">(</span><span class="st">"1: Domain error</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>        <span class="co">// This prints!</span></span>
<span id="cb921-18"><a href="fenv.html#cb921-18"></a>    <span class="cf">else</span></span>
<span id="cb921-19"><a href="fenv.html#cb921-19"></a>        printf<span class="op">(</span><span class="st">"1: No domain error</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb921-20"><a href="fenv.html#cb921-20"></a></span>
<span id="cb921-21"><a href="fenv.html#cb921-21"></a>    fesetexceptflag<span class="op">(&amp;</span>flag<span class="op">,</span> FE_ALL_EXCEPT<span class="op">);</span>  <span class="co">// Restore to before error</span></span>
<span id="cb921-22"><a href="fenv.html#cb921-22"></a></span>
<span id="cb921-23"><a href="fenv.html#cb921-23"></a>    <span class="cf">if</span> <span class="op">(</span>fetestexcept<span class="op">(</span>FE_INVALID<span class="op">))</span></span>
<span id="cb921-24"><a href="fenv.html#cb921-24"></a>        printf<span class="op">(</span><span class="st">"2: Domain error</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb921-25"><a href="fenv.html#cb921-25"></a>    <span class="cf">else</span></span>
<span id="cb921-26"><a href="fenv.html#cb921-26"></a>        printf<span class="op">(</span><span class="st">"2: No domain error</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>     <span class="co">// This prints!</span></span>
<span id="cb921-27"><a href="fenv.html#cb921-27"></a><span class="op">}</span></span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="46.5" id="man-feraiseexcept"><span class="header-section-number">46.5</span>
<code>feraiseexcept()</code></h2>
<p>Raise a floating point exception through software</p>
<h3 class="unnumbered unlisted" id="synopsis-42">Synopsis</h3>
<div class="sourceCode" id="cb922"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb922-1"><a href="fenv.html#cb922-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb922-2"><a href="fenv.html#cb922-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb922-3"><a href="fenv.html#cb922-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> feraiseexcept<span class="op">(</span><span class="dt">int</span> excepts<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-42">Description</h3>
<p>This attempts to raise a floating point exception as if it had
happened.</p>
<p>You can specify multiple exceptions to raise.</p>
<p>If either <code>FE_UNDERFLOW</code> or <code>FE_OVERFLOW</code> is
raised, C <em>might</em> also raise <code>FE_INEXACT</code>.</p>
<p>If either <code>FE_UNDERFLOW</code> or <code>FE_OVERFLOW</code> is
raised at the same time as <code>FE_INEXACT</code>, then
<code>FE_UNDERFLOW</code> or <code>FE_OVERFLOW</code> will be raised
<em>before</em> <code>FE_INEXACT</code> behind the scenes.</p>
<p>The order the other exceptions are raised is undefined.</p>
<h3 class="unnumbered unlisted" id="return-value-41">Return Value</h3>
<p>Returns <code>0</code> if all the exceptions were raised or if
<code>excepts</code> is <code>0</code>.</p>
<p>Returns non-zero otherwise.</p>
<h3 class="unnumbered unlisted" id="example-42">Example</h3>
<p>This code deliberately raises a division-by-zero exception and then
detects it.</p>
<div class="sourceCode" id="cb923"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb923-1"><a href="fenv.html#cb923-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb923-2"><a href="fenv.html#cb923-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb923-3"><a href="fenv.html#cb923-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb923-4"><a href="fenv.html#cb923-4"></a></span>
<span id="cb923-5"><a href="fenv.html#cb923-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb923-6"><a href="fenv.html#cb923-6"></a><span class="op">{</span></span>
<span id="cb923-7"><a href="fenv.html#cb923-7"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb923-8"><a href="fenv.html#cb923-8"></a></span>
<span id="cb923-9"><a href="fenv.html#cb923-9"></a>    feraiseexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">);</span></span>
<span id="cb923-10"><a href="fenv.html#cb923-10"></a></span>
<span id="cb923-11"><a href="fenv.html#cb923-11"></a>    <span class="cf">if</span> <span class="op">(</span>fetestexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">)</span> <span class="op">==</span> FE_DIVBYZERO<span class="op">)</span></span>
<span id="cb923-12"><a href="fenv.html#cb923-12"></a>        printf<span class="op">(</span><span class="st">"Detected division by zero</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This prints!!</span></span>
<span id="cb923-13"><a href="fenv.html#cb923-13"></a>    <span class="cf">else</span></span>
<span id="cb923-14"><a href="fenv.html#cb923-14"></a>        printf<span class="op">(</span><span class="st">"This is fine.</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb923-15"><a href="fenv.html#cb923-15"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-38">See Also</h3>
<p><a href="fenv.html#man-feclearexcept"><code>feclearexcept()</code></a>, <a href="#man-fetestexcept"><code>fetestexcept()</code></a></p>
<hr>
<h2 data-number="46.6" id="man-fetestexcept"><span class="header-section-number">46.6</span>
<code>fetestexcept()</code></h2>
<p>Test to see if an exception has occurred</p>
<h3 class="unnumbered unlisted" id="synopsis-43">Synopsis</h3>
<div class="sourceCode" id="cb924"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb924-1"><a href="fenv.html#cb924-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb924-2"><a href="fenv.html#cb924-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb924-3"><a href="fenv.html#cb924-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fetestexcept<span class="op">(</span><span class="dt">int</span> excepts<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-43">Description</h3>
<p>Put the exceptions you want to test in <code>excepts</code>,
bitwise-ORing them together.</p>
<h3 class="unnumbered unlisted" id="return-value-42">Return Value</h3>
<p>Returns the bitwise-OR of the exceptions that have been raised.</p>
<h3 class="unnumbered unlisted" id="example-43">Example</h3>
<p>This code deliberately raises a division-by-zero exception and then
detects it.</p>
<div class="sourceCode" id="cb925"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb925-1"><a href="fenv.html#cb925-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb925-2"><a href="fenv.html#cb925-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb925-3"><a href="fenv.html#cb925-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb925-4"><a href="fenv.html#cb925-4"></a></span>
<span id="cb925-5"><a href="fenv.html#cb925-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb925-6"><a href="fenv.html#cb925-6"></a><span class="op">{</span></span>
<span id="cb925-7"><a href="fenv.html#cb925-7"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb925-8"><a href="fenv.html#cb925-8"></a></span>
<span id="cb925-9"><a href="fenv.html#cb925-9"></a>    feraiseexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">);</span></span>
<span id="cb925-10"><a href="fenv.html#cb925-10"></a></span>
<span id="cb925-11"><a href="fenv.html#cb925-11"></a>    <span class="cf">if</span> <span class="op">(</span>fetestexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">)</span> <span class="op">==</span> FE_DIVBYZERO<span class="op">)</span></span>
<span id="cb925-12"><a href="fenv.html#cb925-12"></a>        printf<span class="op">(</span><span class="st">"Detected division by zero</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This prints!!</span></span>
<span id="cb925-13"><a href="fenv.html#cb925-13"></a>    <span class="cf">else</span></span>
<span id="cb925-14"><a href="fenv.html#cb925-14"></a>        printf<span class="op">(</span><span class="st">"This is fine.</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb925-15"><a href="fenv.html#cb925-15"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-39">See Also</h3>
<p><a href="fenv.html#man-feclearexcept"><code>feclearexcept()</code></a>, <a href="#man-feraiseexcept"><code>feraiseexcept()</code></a></p>
<hr>
<h2 data-number="46.7" id="man-fegetround"><span class="header-section-number">46.7</span> <code>fegetround()</code>
<code>fesetround()</code></h2>
<p>Get or set the rounding direction</p>
<h3 class="unnumbered unlisted" id="synopsis-44">Synopsis</h3>
<div class="sourceCode" id="cb926"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb926-1"><a href="fenv.html#cb926-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb926-2"><a href="fenv.html#cb926-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb926-3"><a href="fenv.html#cb926-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fegetround<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span>
<span id="cb926-4"><a href="fenv.html#cb926-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb926-5"><a href="fenv.html#cb926-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fesetround<span class="op">(</span><span class="dt">int</span> round<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-44">Description</h3>
<p>Use these to get or set the rounding direction used by a variety of
math functions.</p>
<p>Basically when a function “rounds” a number, it wants to know how to
do it. By default, it does it how we tend to expect: if the fractional
part is less than 0.5, it rounds down closer to zero, otherwise up
farther from zero.</p>
<table>
<thead>
<tr class="header">
<th>Macro</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>FE_TONEAREST</code></td>
<td>Round to the nearest whole number, the default</td>
</tr>
<tr class="even">
<td><code>FE_TOWARDZERO</code></td>
<td>Round toward zero always</td>
</tr>
<tr class="odd">
<td><code>FE_DOWNWARD</code></td>
<td>Round toward the next lesser whole number</td>
</tr>
<tr class="even">
<td><code>FE_UPWARD</code></td>
<td>Round toward the next greater whole number</td>
</tr>
</tbody>
</table>
<p>Some implementations don’t support rounding. If it does, the above
macros will be defined.</p>
<p>Note that the <code>round()</code> function is always “to-nearest”
and doesn’t pay attention to the rounding mode.</p>
<h3 class="unnumbered unlisted" id="return-value-43">Return Value</h3>
<p><code>fegetround()</code> returns the current rounding direction, or
a negative value on error.</p>
<p><code>fesetround()</code> returns zero on success, or non-zero on
failure.</p>
<h3 class="unnumbered unlisted" id="example-44">Example</h3>
<p>This rounds some numbers</p>
<div class="sourceCode" id="cb927"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb927-1"><a href="fenv.html#cb927-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb927-2"><a href="fenv.html#cb927-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb927-3"><a href="fenv.html#cb927-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb927-4"><a href="fenv.html#cb927-4"></a></span>
<span id="cb927-5"><a href="fenv.html#cb927-5"></a><span class="co">// Helper function to print the rounding mode</span></span>
<span id="cb927-6"><a href="fenv.html#cb927-6"></a><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>rounding_mode_str<span class="op">(</span><span class="dt">int</span> mode<span class="op">)</span></span>
<span id="cb927-7"><a href="fenv.html#cb927-7"></a><span class="op">{</span></span>
<span id="cb927-8"><a href="fenv.html#cb927-8"></a>    <span class="cf">switch</span> <span class="op">(</span>mode<span class="op">)</span> <span class="op">{</span></span>
<span id="cb927-9"><a href="fenv.html#cb927-9"></a>        <span class="cf">case</span> FE_TONEAREST<span class="op">:</span>  <span class="cf">return</span> <span class="st">"FE_TONEAREST"</span><span class="op">;</span></span>
<span id="cb927-10"><a href="fenv.html#cb927-10"></a>        <span class="cf">case</span> FE_TOWARDZERO<span class="op">:</span> <span class="cf">return</span> <span class="st">"FE_TOWARDZERO"</span><span class="op">;</span></span>
<span id="cb927-11"><a href="fenv.html#cb927-11"></a>        <span class="cf">case</span> FE_DOWNWARD<span class="op">:</span>   <span class="cf">return</span> <span class="st">"FE_DOWNWARD"</span><span class="op">;</span></span>
<span id="cb927-12"><a href="fenv.html#cb927-12"></a>        <span class="cf">case</span> FE_UPWARD<span class="op">:</span>     <span class="cf">return</span> <span class="st">"FE_UPWARD"</span><span class="op">;</span></span>
<span id="cb927-13"><a href="fenv.html#cb927-13"></a>    <span class="op">}</span></span>
<span id="cb927-14"><a href="fenv.html#cb927-14"></a></span>
<span id="cb927-15"><a href="fenv.html#cb927-15"></a>    <span class="cf">return</span> <span class="st">"Unknown"</span><span class="op">;</span></span>
<span id="cb927-16"><a href="fenv.html#cb927-16"></a><span class="op">}</span></span>
<span id="cb927-17"><a href="fenv.html#cb927-17"></a></span>
<span id="cb927-18"><a href="fenv.html#cb927-18"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb927-19"><a href="fenv.html#cb927-19"></a><span class="op">{</span></span>
<span id="cb927-20"><a href="fenv.html#cb927-20"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb927-21"><a href="fenv.html#cb927-21"></a></span>
<span id="cb927-22"><a href="fenv.html#cb927-22"></a>    <span class="dt">int</span> rm<span class="op">;</span></span>
<span id="cb927-23"><a href="fenv.html#cb927-23"></a></span>
<span id="cb927-24"><a href="fenv.html#cb927-24"></a>    rm <span class="op">=</span> fegetround<span class="op">();</span></span>
<span id="cb927-25"><a href="fenv.html#cb927-25"></a></span>
<span id="cb927-26"><a href="fenv.html#cb927-26"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rounding_mode_str<span class="op">(</span>rm<span class="op">));</span>    <span class="co">// Print current mode</span></span>
<span id="cb927-27"><a href="fenv.html#cb927-27"></a>    printf<span class="op">(</span><span class="st">"%f %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rint<span class="op">(</span><span class="fl">2.1</span><span class="op">),</span> rint<span class="op">(</span><span class="fl">2.7</span><span class="op">));</span>  <span class="co">// Try rounding</span></span>
<span id="cb927-28"><a href="fenv.html#cb927-28"></a></span>
<span id="cb927-29"><a href="fenv.html#cb927-29"></a>    fesetround<span class="op">(</span>FE_TOWARDZERO<span class="op">);</span>                <span class="co">// Set the mode</span></span>
<span id="cb927-30"><a href="fenv.html#cb927-30"></a></span>
<span id="cb927-31"><a href="fenv.html#cb927-31"></a>    rm <span class="op">=</span> fegetround<span class="op">();</span></span>
<span id="cb927-32"><a href="fenv.html#cb927-32"></a></span>
<span id="cb927-33"><a href="fenv.html#cb927-33"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rounding_mode_str<span class="op">(</span>rm<span class="op">));</span>    <span class="co">// Print it</span></span>
<span id="cb927-34"><a href="fenv.html#cb927-34"></a>    printf<span class="op">(</span><span class="st">"%f %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rint<span class="op">(</span><span class="fl">2.1</span><span class="op">),</span> rint<span class="op">(</span><span class="fl">2.7</span><span class="op">));</span>  <span class="co">// Try it now!</span></span>
<span id="cb927-35"><a href="fenv.html#cb927-35"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb928"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb928-1"><a href="fenv.html#cb928-1" aria-hidden="true" tabindex="-1"></a>FE_TONEAREST</span>
<span id="cb928-2"><a href="fenv.html#cb928-2" aria-hidden="true" tabindex="-1"></a>2.000000 3.000000</span>
<span id="cb928-3"><a href="fenv.html#cb928-3" aria-hidden="true" tabindex="-1"></a>FE_TOWARDZERO</span>
<span id="cb928-4"><a href="fenv.html#cb928-4" aria-hidden="true" tabindex="-1"></a>2.000000 2.000000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-40">See Also</h3>
<p><a href="math.html#man-nearbyint"><code>nearbyint()</code></a>, <a href="#man-nearbyint"><code>nearbyintf()</code></a>, <a href="#man-nearbyint"><code>nearbyintl()</code></a>, <a href="#man-rint"><code>rint()</code></a>, <a href="#man-rint"><code>rintf()</code></a>, <a href="#man-rint"><code>rintl()</code></a>, <a href="#man-lrint"><code>lrint()</code></a>, <a href="#man-lrint"><code>lrintf()</code></a>, <a href="#man-lrint"><code>lrintl()</code></a>, <a href="#man-lrint"><code>llrint()</code></a>, <a href="#man-lrint"><code>llrintf()</code></a>, <a href="#man-lrint"><code>llrintl()</code></a></p>
<hr>
<h2 data-number="46.8" id="man-fegetenv"><span class="header-section-number">46.8</span> <code>fegetenv()</code>
<code>fesetenv()</code></h2>
<p>Save or restore the entire floating point environment</p>
<h3 class="unnumbered unlisted" id="synopsis-45">Synopsis</h3>
<div class="sourceCode" id="cb929"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb929-1"><a href="fenv.html#cb929-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb929-2"><a href="fenv.html#cb929-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb929-3"><a href="fenv.html#cb929-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fegetenv<span class="op">(</span>fenv_t <span class="op">*</span>envp<span class="op">);</span></span>
<span id="cb929-4"><a href="fenv.html#cb929-4" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fesetenv<span class="op">(</span><span class="dt">const</span> fenv_t <span class="op">*</span>envp<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-45">Description</h3>
<p>You can save the environment (exceptions, rounding direction, etc.)
by calling <code>fegetenv()</code> and restore it with
<code>fesetenv()</code>.</p>
<p>Use this if you want to restore the state after a function call, i.e.
hide from the caller that some floating point exceptions or changes
occurred.</p>
<h3 class="unnumbered unlisted" id="return-value-44">Return Value</h3>
<p><code>fegetenv()</code> and <code>fesetenv()</code> return
<code>0</code> on success, and non-zero otherwise.</p>
<h3 class="unnumbered unlisted" id="example-45">Example</h3>
<p>This example saves the environment, messes with the rounding and
exceptions, then restores it. After the environment is restored, we see
that the rounding is back to default and the exception is cleared.</p>
<div class="sourceCode" id="cb930"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb930-1"><a href="fenv.html#cb930-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb930-2"><a href="fenv.html#cb930-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb930-3"><a href="fenv.html#cb930-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb930-4"><a href="fenv.html#cb930-4"></a></span>
<span id="cb930-5"><a href="fenv.html#cb930-5"></a><span class="dt">void</span> show_status<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb930-6"><a href="fenv.html#cb930-6"></a><span class="op">{</span></span>
<span id="cb930-7"><a href="fenv.html#cb930-7"></a>    printf<span class="op">(</span><span class="st">"Rounding is FE_TOWARDZERO: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span></span>
<span id="cb930-8"><a href="fenv.html#cb930-8"></a>           fegetround<span class="op">()</span> <span class="op">==</span> FE_TOWARDZERO<span class="op">);</span></span>
<span id="cb930-9"><a href="fenv.html#cb930-9"></a></span>
<span id="cb930-10"><a href="fenv.html#cb930-10"></a>    printf<span class="op">(</span><span class="st">"FE_DIVBYZERO is set: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span></span>
<span id="cb930-11"><a href="fenv.html#cb930-11"></a>           fetestexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">)</span> <span class="op">!=</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb930-12"><a href="fenv.html#cb930-12"></a><span class="op">}</span></span>
<span id="cb930-13"><a href="fenv.html#cb930-13"></a></span>
<span id="cb930-14"><a href="fenv.html#cb930-14"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb930-15"><a href="fenv.html#cb930-15"></a><span class="op">{</span></span>
<span id="cb930-16"><a href="fenv.html#cb930-16"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb930-17"><a href="fenv.html#cb930-17"></a></span>
<span id="cb930-18"><a href="fenv.html#cb930-18"></a>    fenv_t env<span class="op">;</span></span>
<span id="cb930-19"><a href="fenv.html#cb930-19"></a></span>
<span id="cb930-20"><a href="fenv.html#cb930-20"></a>    fegetenv<span class="op">(&amp;</span>env<span class="op">);</span>  <span class="co">// Save the environment</span></span>
<span id="cb930-21"><a href="fenv.html#cb930-21"></a></span>
<span id="cb930-22"><a href="fenv.html#cb930-22"></a>    fesetround<span class="op">(</span>FE_TOWARDZERO<span class="op">);</span>    <span class="co">// Change rounding</span></span>
<span id="cb930-23"><a href="fenv.html#cb930-23"></a>    feraiseexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">);</span>  <span class="co">// Raise an exception</span></span>
<span id="cb930-24"><a href="fenv.html#cb930-24"></a></span>
<span id="cb930-25"><a href="fenv.html#cb930-25"></a>    show_status<span class="op">();</span></span>
<span id="cb930-26"><a href="fenv.html#cb930-26"></a></span>
<span id="cb930-27"><a href="fenv.html#cb930-27"></a>    fesetenv<span class="op">(&amp;</span>env<span class="op">);</span>  <span class="co">// Restore the environment</span></span>
<span id="cb930-28"><a href="fenv.html#cb930-28"></a></span>
<span id="cb930-29"><a href="fenv.html#cb930-29"></a>    show_status<span class="op">();</span></span>
<span id="cb930-30"><a href="fenv.html#cb930-30"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb931"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb931-1"><a href="fenv.html#cb931-1" aria-hidden="true" tabindex="-1"></a>Rounding is FE_TOWARDZERO: 1</span>
<span id="cb931-2"><a href="fenv.html#cb931-2" aria-hidden="true" tabindex="-1"></a>FE_DIVBYZERO is set: 1</span>
<span id="cb931-3"><a href="fenv.html#cb931-3" aria-hidden="true" tabindex="-1"></a>Rounding is FE_TOWARDZERO: 0</span>
<span id="cb931-4"><a href="fenv.html#cb931-4" aria-hidden="true" tabindex="-1"></a>FE_DIVBYZERO is set: 0</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-41">See Also</h3>
<p><a href="fenv.html#man-feholdexcept"><code>feholdexcept()</code></a>, <a href="#man-feupdateenv"><code>feupdateenv()</code></a></p>
<hr>
<h2 data-number="46.9" id="man-feholdexcept"><span class="header-section-number">46.9</span>
<code>feholdexcept()</code></h2>
<p>Save floating point state and install non-stop mode</p>
<h3 class="unnumbered unlisted" id="synopsis-46">Synopsis</h3>
<div class="sourceCode" id="cb932"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb932-1"><a href="fenv.html#cb932-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb932-2"><a href="fenv.html#cb932-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb932-3"><a href="fenv.html#cb932-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> feholdexcept<span class="op">(</span>fenv_t <span class="op">*</span>envp<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-46">Description</h3>
<p>This is just like <code>fegetenv()</code> except that it updates the
current environment to be in <em>non-stop</em> mode, namely it won’t
halt on any exceptions.</p>
<p>It remains in this state until you restore the state with
<code>fesetenv()</code> or <code>feupdateenv()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-45">Return Value</h3>
<h3 class="unnumbered unlisted" id="example-46">Example</h3>
<p>This example saves the environment and goes into non-stop mode,
messes with the rounding and exceptions, then restores it. After the
environment is restored, we see that the rounding is back to default and
the exception is cleared. We’ll also be out of non-stop mode.</p>
<div class="sourceCode" id="cb933"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb933-1"><a href="fenv.html#cb933-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb933-2"><a href="fenv.html#cb933-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb933-3"><a href="fenv.html#cb933-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb933-4"><a href="fenv.html#cb933-4"></a></span>
<span id="cb933-5"><a href="fenv.html#cb933-5"></a><span class="dt">void</span> show_status<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb933-6"><a href="fenv.html#cb933-6"></a><span class="op">{</span></span>
<span id="cb933-7"><a href="fenv.html#cb933-7"></a>    printf<span class="op">(</span><span class="st">"Rounding is FE_TOWARDZERO: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span></span>
<span id="cb933-8"><a href="fenv.html#cb933-8"></a>           fegetround<span class="op">()</span> <span class="op">==</span> FE_TOWARDZERO<span class="op">);</span></span>
<span id="cb933-9"><a href="fenv.html#cb933-9"></a></span>
<span id="cb933-10"><a href="fenv.html#cb933-10"></a>    printf<span class="op">(</span><span class="st">"FE_DIVBYZERO is set: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span></span>
<span id="cb933-11"><a href="fenv.html#cb933-11"></a>           fetestexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">)</span> <span class="op">!=</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb933-12"><a href="fenv.html#cb933-12"></a><span class="op">}</span></span>
<span id="cb933-13"><a href="fenv.html#cb933-13"></a></span>
<span id="cb933-14"><a href="fenv.html#cb933-14"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb933-15"><a href="fenv.html#cb933-15"></a><span class="op">{</span></span>
<span id="cb933-16"><a href="fenv.html#cb933-16"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb933-17"><a href="fenv.html#cb933-17"></a></span>
<span id="cb933-18"><a href="fenv.html#cb933-18"></a>    fenv_t env<span class="op">;</span></span>
<span id="cb933-19"><a href="fenv.html#cb933-19"></a></span>
<span id="cb933-20"><a href="fenv.html#cb933-20"></a>    <span class="co">// Save the environment and don't stop on exceptions</span></span>
<span id="cb933-21"><a href="fenv.html#cb933-21"></a>    feholdexcept<span class="op">(&amp;</span>env<span class="op">);</span></span>
<span id="cb933-22"><a href="fenv.html#cb933-22"></a></span>
<span id="cb933-23"><a href="fenv.html#cb933-23"></a>    fesetround<span class="op">(</span>FE_TOWARDZERO<span class="op">);</span>    <span class="co">// Change rounding</span></span>
<span id="cb933-24"><a href="fenv.html#cb933-24"></a>    feraiseexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">);</span>  <span class="co">// Raise an exception</span></span>
<span id="cb933-25"><a href="fenv.html#cb933-25"></a></span>
<span id="cb933-26"><a href="fenv.html#cb933-26"></a>    show_status<span class="op">();</span></span>
<span id="cb933-27"><a href="fenv.html#cb933-27"></a></span>
<span id="cb933-28"><a href="fenv.html#cb933-28"></a>    fesetenv<span class="op">(&amp;</span>env<span class="op">);</span>  <span class="co">// Restore the environment</span></span>
<span id="cb933-29"><a href="fenv.html#cb933-29"></a></span>
<span id="cb933-30"><a href="fenv.html#cb933-30"></a>    show_status<span class="op">();</span></span>
<span id="cb933-31"><a href="fenv.html#cb933-31"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-42">See Also</h3>
<p><a href="fenv.html#man-fegetenv"><code>fegetenv()</code></a>, <a href="#man-fegetenv"><code>fesetenv()</code></a>, <a href="#man-feupdateenv"><code>feupdateenv()</code></a></p>
<hr>
<h2 data-number="46.10" id="man-feupdateenv"><span class="header-section-number">46.10</span>
<code>feupdateenv()</code></h2>
<p>Restore floating point environment and apply recent exceptions</p>
<h3 class="unnumbered unlisted" id="synopsis-47">Synopsis</h3>
<div class="sourceCode" id="cb934"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb934-1"><a href="fenv.html#cb934-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb934-2"><a href="fenv.html#cb934-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb934-3"><a href="fenv.html#cb934-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> feupdateenv<span class="op">(</span><span class="dt">const</span> fenv_t <span class="op">*</span>envp<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-47">Description</h3>
<p>This is like <code>fesetenv()</code> except that it modifies the
passed-in environment so that it is updated with exceptions that have
happened in the meantime.</p>
<p>So let’s say you had a function that might raise exceptions, but you
wanted to hide those in the caller. One option might be to:</p>
<ol type="1">
<li>Save the environment with <code>fegetenv()</code> or
<code>feholdexcept()</code>.</li>
<li>Do whatever you do that might raise exceptions.</li>
<li>Restore the environment with <code>fesetenv()</code>, thereby hiding
the exceptions that happened in step 2.</li>
</ol>
<p>But that hides <em>all</em> exceptions. What if you just wanted to
hide some of them? You could use <code>feupdateenv()</code> like
this:</p>
<ol type="1">
<li>Save the environment with <code>fegetenv()</code> or
<code>feholdexcept()</code>.</li>
<li>Do whatever you do that might raise exceptions.</li>
<li>Call <code>feclearexcept()</code> to clear the exceptions you want
to hide from the caller.</li>
<li>Call <code>feupdateenv()</code> to restore the previous environment
and update it with the other exceptions that have occurred.</li>
</ol>
<p>So it’s like a more capable way of restoring the environment than
simply <code>fegetenv()</code>/<code>fesetenv()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-46">Return Value</h3>
<p>Returns <code>0</code> on success, non-zero otherwise.</p>
<h3 class="unnumbered unlisted" id="example-47">Example</h3>
<p>This program saves state, raises some exceptions, then clears one of
the exceptions, then restores and updates the state.</p>
<div class="sourceCode" id="cb935"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb935-1"><a href="fenv.html#cb935-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb935-2"><a href="fenv.html#cb935-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb935-3"><a href="fenv.html#cb935-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb935-4"><a href="fenv.html#cb935-4"></a></span>
<span id="cb935-5"><a href="fenv.html#cb935-5"></a><span class="dt">void</span> show_status<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb935-6"><a href="fenv.html#cb935-6"></a><span class="op">{</span></span>
<span id="cb935-7"><a href="fenv.html#cb935-7"></a>    printf<span class="op">(</span><span class="st">"FE_DIVBYZERO: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fetestexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">)</span> <span class="op">!=</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb935-8"><a href="fenv.html#cb935-8"></a>    printf<span class="op">(</span><span class="st">"FE_INVALID  : %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fetestexcept<span class="op">(</span>FE_INVALID<span class="op">)</span> <span class="op">!=</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb935-9"><a href="fenv.html#cb935-9"></a>    printf<span class="op">(</span><span class="st">"FE_OVERFLOW : %d</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> fetestexcept<span class="op">(</span>FE_OVERFLOW<span class="op">)</span> <span class="op">!=</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb935-10"><a href="fenv.html#cb935-10"></a><span class="op">}</span></span>
<span id="cb935-11"><a href="fenv.html#cb935-11"></a></span>
<span id="cb935-12"><a href="fenv.html#cb935-12"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb935-13"><a href="fenv.html#cb935-13"></a><span class="op">{</span></span>
<span id="cb935-14"><a href="fenv.html#cb935-14"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON </span></span>
<span id="cb935-15"><a href="fenv.html#cb935-15"></a></span>
<span id="cb935-16"><a href="fenv.html#cb935-16"></a>    fenv_t env<span class="op">;</span></span>
<span id="cb935-17"><a href="fenv.html#cb935-17"></a></span>
<span id="cb935-18"><a href="fenv.html#cb935-18"></a>    feholdexcept<span class="op">(&amp;</span>env<span class="op">);</span>  <span class="co">// Save the environment</span></span>
<span id="cb935-19"><a href="fenv.html#cb935-19"></a></span>
<span id="cb935-20"><a href="fenv.html#cb935-20"></a>    <span class="co">// Pretend some bad math happened here:</span></span>
<span id="cb935-21"><a href="fenv.html#cb935-21"></a>    feraiseexcept<span class="op">(</span>FE_DIVBYZERO<span class="op">);</span>  <span class="co">// Raise an exception</span></span>
<span id="cb935-22"><a href="fenv.html#cb935-22"></a>    feraiseexcept<span class="op">(</span>FE_INVALID<span class="op">);</span>    <span class="co">// Raise an exception</span></span>
<span id="cb935-23"><a href="fenv.html#cb935-23"></a>    feraiseexcept<span class="op">(</span>FE_OVERFLOW<span class="op">);</span>   <span class="co">// Raise an exception</span></span>
<span id="cb935-24"><a href="fenv.html#cb935-24"></a></span>
<span id="cb935-25"><a href="fenv.html#cb935-25"></a>    show_status<span class="op">();</span></span>
<span id="cb935-26"><a href="fenv.html#cb935-26"></a></span>
<span id="cb935-27"><a href="fenv.html#cb935-27"></a>    feclearexcept<span class="op">(</span>FE_INVALID<span class="op">);</span></span>
<span id="cb935-28"><a href="fenv.html#cb935-28"></a></span>
<span id="cb935-29"><a href="fenv.html#cb935-29"></a>    feupdateenv<span class="op">(&amp;</span>env<span class="op">);</span>  <span class="co">// Restore the environment</span></span>
<span id="cb935-30"><a href="fenv.html#cb935-30"></a></span>
<span id="cb935-31"><a href="fenv.html#cb935-31"></a>    show_status<span class="op">();</span></span>
<span id="cb935-32"><a href="fenv.html#cb935-32"></a><span class="op">}</span></span></code></pre></div>
<p>In the output, at first we have no exceptions. Then we have the three
we raised. Then after we restore/update the environment, we see the one
we cleared (<code>FE_INVALID</code>) hasn’t been applied:</p>
<div class="sourceCode" id="cb936"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb936-1"><a href="fenv.html#cb936-1" aria-hidden="true" tabindex="-1"></a>FE_DIVBYZERO: 0</span>
<span id="cb936-2"><a href="fenv.html#cb936-2" aria-hidden="true" tabindex="-1"></a>FE_INVALID  : 0</span>
<span id="cb936-3"><a href="fenv.html#cb936-3" aria-hidden="true" tabindex="-1"></a>FE_OVERFLOW : 0</span>
<span id="cb936-4"><a href="fenv.html#cb936-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb936-5"><a href="fenv.html#cb936-5" aria-hidden="true" tabindex="-1"></a>FE_DIVBYZERO: 1</span>
<span id="cb936-6"><a href="fenv.html#cb936-6" aria-hidden="true" tabindex="-1"></a>FE_INVALID  : 1</span>
<span id="cb936-7"><a href="fenv.html#cb936-7" aria-hidden="true" tabindex="-1"></a>FE_OVERFLOW : 1</span>
<span id="cb936-8"><a href="fenv.html#cb936-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb936-9"><a href="fenv.html#cb936-9" aria-hidden="true" tabindex="-1"></a>FE_DIVBYZERO: 1</span>
<span id="cb936-10"><a href="fenv.html#cb936-10" aria-hidden="true" tabindex="-1"></a>FE_INVALID  : 0</span>
<span id="cb936-11"><a href="fenv.html#cb936-11" aria-hidden="true" tabindex="-1"></a>FE_OVERFLOW : 1</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-43">See Also</h3>
<p><a href="fenv.html#man-fegetenv"><code>fegetenv()</code></a>, <a href="#man-fegetenv"><code>fesetenv()</code></a>, <a href="#man-feholdexcept"><code>feholdexcept()</code></a>, <a href="#man-feclearexcept"><code>feclearexcept()</code></a></p>

</body>