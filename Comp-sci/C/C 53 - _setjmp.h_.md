<body>
<hr>
<h1 data-number="53" id="setjmp"><span class="header-section-number">53</span> <code>&lt;setjmp.h&gt;</code>
Non-local Goto</h1>
<p>These functions enable you to rewind the call stack to an earlier
point, with a bunch of gotchas. See the <a href="#setjmp-longjmp">chapter on
<code>setjmp()</code>/<code>longjmp()</code></a> for more info.</p>
<table>
<thead>
<tr class="header">
<th>Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>longjmp()</code></td>
<td>Return to the previously-placed bookmark</td>
</tr>
<tr class="even">
<td><code>setjmp()</code></td>
<td>Bookmark this place to return to later</td>
</tr>
</tbody>
</table>
<p>There’s also a new opaque type, <code>jmp_buf</code>, that holds all
the information needed to pull off this magic trick.</p>
<p>If you want your automatic local variables to be correct after a call
to <code>longjmp()</code>. declare them as <code>volatile</code> where
you called <code>setjmp()</code>.</p>
<hr>
<h2 data-number="53.1" id="man-setjmp"><span class="header-section-number">53.1</span> <code>setjmp()</code></h2>
<p>Save this location as one to return to later</p>
<h3 class="unnumbered unlisted" id="synopsis-112">Synopsis</h3>
<div class="sourceCode" id="cb1115"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1115-1"><a href="setjmp.html#cb1115-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;setjmp.h&gt;</span></span>
<span id="cb1115-2"><a href="setjmp.html#cb1115-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1115-3"><a href="setjmp.html#cb1115-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> setjmp<span class="op">(</span>jmp_buf env<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-112">Description</h3>
<p>This is how you save your position so you can <code>longjmp()</code>
back it, later. Think of it as setting up a warp destination for later
use.</p>
<p>Basically, you call this, giving it an <code>env</code> it can fill
in with all the information it needs to come back here later. This
<code>env</code> is one you’ll pass to <code>longjmp()</code> later when
you want to teleport back here.</p>
<p>And the really funky part is this can return two different ways:</p>
<ol type="1">
<li><p>It can return <code>0</code> from the call where you set up the
jump destination.</p></li>
<li><p>If can return non-zero when you actually warp back here as the
result of a call to <code>longjmp()</code>.</p></li>
</ol>
<p>What you can do is check the return value to see which case has
occurred.</p>
<p>You’re only allowed to call <code>setjmp()</code> in a limited number
of circumstances.</p>
<ol type="1">
<li><p>As a standalone expression:</p>
<div class="sourceCode" id="cb1116"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1116-1"><a href="setjmp.html#cb1116-1" aria-hidden="true" tabindex="-1"></a>setjmp<span class="op">(</span>env<span class="op">);</span></span></code></pre></div>
<p>You can also cast it to <code>(void)</code> if you really wanted to
do such a thing.</p></li>
<li><p>As the complete controlling expression in an <code>if</code> or
<code>switch</code>.</p>
<div class="sourceCode" id="cb1117"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1117-1"><a href="setjmp.html#cb1117-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(</span>setjmp<span class="op">(</span>env<span class="op">))</span> <span class="op">{</span> <span class="op">...</span> <span class="op">}</span></span>
<span id="cb1117-2"><a href="setjmp.html#cb1117-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1117-3"><a href="setjmp.html#cb1117-3" aria-hidden="true" tabindex="-1"></a><span class="cf">switch</span> <span class="op">(</span>setjmp<span class="op">(</span>env<span class="op">))</span> <span class="op">{</span> <span class="op">...</span> <span class="op">}</span></span></code></pre></div>
<p>But not this as it’s not the complete controlling expression in this
case:</p>
<div class="sourceCode" id="cb1118"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1118-1"><a href="setjmp.html#cb1118-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(</span>x <span class="op">==</span> <span class="dv">2</span> <span class="op">&amp;&amp;</span> setjmp<span class="op">())</span> <span class="op">{</span> <span class="op">...</span> <span class="op">}</span>   <span class="co">// Undefined behavior</span></span></code></pre></div></li>
<li><p>The same as (2), above, except with a comparison to an integer
constant:</p>
<div class="sourceCode" id="cb1119"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1119-1"><a href="setjmp.html#cb1119-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(</span>setjmp<span class="op">(</span>env<span class="op">)</span> <span class="op">==</span> <span class="dv">0</span><span class="op">)</span> <span class="op">{</span> <span class="op">...</span> <span class="op">}</span></span>
<span id="cb1119-2"><a href="setjmp.html#cb1119-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1119-3"><a href="setjmp.html#cb1119-3" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(</span>setjmp<span class="op">(</span>env<span class="op">)</span> <span class="op">&gt;</span> <span class="dv">2</span><span class="op">)</span> <span class="op">{</span> <span class="op">...</span> <span class="op">}</span></span></code></pre></div></li>
<li><p>As the operand to the not (<code>!</code>) operator:</p>
<div class="sourceCode" id="cb1120"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1120-1"><a href="setjmp.html#cb1120-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(!</span>setjmp<span class="op">(</span>env<span class="op">))</span> <span class="op">{</span> <span class="op">...</span> <span class="op">}</span></span></code></pre></div></li>
</ol>
<p>Anything else is (you guessed it) undefined behavior!</p>
<p>This can be a macro or a function, but you’ll treat it the same way
in any case.</p>
<h3 class="unnumbered unlisted" id="return-value-111">Return Value</h3>
<p>This one is funky. It returns one of two things:</p>
<p>Returns <code>0</code> if this was the call to <code>setjmp()</code>
to set it up.</p>
<p>Returns non-zero if being here was the result of a call to
<code>longjmp()</code>. (Namely, it returns the value passed into the
<code>longjmp()</code> function.)</p>
<h3 class="unnumbered unlisted" id="example-112">Example</h3>
<p>Here’s a function that calls <code>setjmp()</code> to set things up
(where it returns <code>0</code>), then calls a couple levels deep into
functions, and finally short-circuits the return path by
<code>longjmp()</code>ing back to the place where <code>setjmp()</code>
was called, earlier. This time, it passes <code>3490</code> as a value,
which <code>setjmp()</code> returns.</p>
<div class="sourceCode" id="cb1121"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1121-1"><a href="setjmp.html#cb1121-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1121-2"><a href="setjmp.html#cb1121-2"></a><span class="pp">#include </span><span class="im">&lt;setjmp.h&gt;</span></span>
<span id="cb1121-3"><a href="setjmp.html#cb1121-3"></a></span>
<span id="cb1121-4"><a href="setjmp.html#cb1121-4"></a>jmp_buf env<span class="op">;</span></span>
<span id="cb1121-5"><a href="setjmp.html#cb1121-5"></a></span>
<span id="cb1121-6"><a href="setjmp.html#cb1121-6"></a><span class="dt">void</span> depth2<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1121-7"><a href="setjmp.html#cb1121-7"></a><span class="op">{</span></span>
<span id="cb1121-8"><a href="setjmp.html#cb1121-8"></a>    printf<span class="op">(</span><span class="st">"Entering depth 2</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1121-9"><a href="setjmp.html#cb1121-9"></a>    longjmp<span class="op">(</span>env<span class="op">,</span> <span class="dv">3490</span><span class="op">);</span>           <span class="co">// Jump back to setjmp()!!</span></span>
<span id="cb1121-10"><a href="setjmp.html#cb1121-10"></a>    printf<span class="op">(</span><span class="st">"Leaving depth 2</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This won't happen</span></span>
<span id="cb1121-11"><a href="setjmp.html#cb1121-11"></a><span class="op">}</span></span>
<span id="cb1121-12"><a href="setjmp.html#cb1121-12"></a></span>
<span id="cb1121-13"><a href="setjmp.html#cb1121-13"></a><span class="dt">void</span> depth1<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1121-14"><a href="setjmp.html#cb1121-14"></a><span class="op">{</span></span>
<span id="cb1121-15"><a href="setjmp.html#cb1121-15"></a>    printf<span class="op">(</span><span class="st">"Entering depth 1</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1121-16"><a href="setjmp.html#cb1121-16"></a>    depth2<span class="op">();</span></span>
<span id="cb1121-17"><a href="setjmp.html#cb1121-17"></a>    printf<span class="op">(</span><span class="st">"Leaving depth 1</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This won't happen</span></span>
<span id="cb1121-18"><a href="setjmp.html#cb1121-18"></a><span class="op">}</span></span>
<span id="cb1121-19"><a href="setjmp.html#cb1121-19"></a></span>
<span id="cb1121-20"><a href="setjmp.html#cb1121-20"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1121-21"><a href="setjmp.html#cb1121-21"></a><span class="op">{</span></span>
<span id="cb1121-22"><a href="setjmp.html#cb1121-22"></a>    <span class="cf">switch</span> <span class="op">(</span>setjmp<span class="op">(</span>env<span class="op">))</span> <span class="op">{</span></span>
<span id="cb1121-23"><a href="setjmp.html#cb1121-23"></a>        <span class="cf">case</span> <span class="dv">0</span><span class="op">:</span></span>
<span id="cb1121-24"><a href="setjmp.html#cb1121-24"></a>            printf<span class="op">(</span><span class="st">"Calling into functions, setjmp() returned 0</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1121-25"><a href="setjmp.html#cb1121-25"></a>            depth1<span class="op">();</span></span>
<span id="cb1121-26"><a href="setjmp.html#cb1121-26"></a>            printf<span class="op">(</span><span class="st">"Returned from functions</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This won't happen</span></span>
<span id="cb1121-27"><a href="setjmp.html#cb1121-27"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1121-28"><a href="setjmp.html#cb1121-28"></a></span>
<span id="cb1121-29"><a href="setjmp.html#cb1121-29"></a>        <span class="cf">case</span> <span class="dv">3490</span><span class="op">:</span></span>
<span id="cb1121-30"><a href="setjmp.html#cb1121-30"></a>            printf<span class="op">(</span><span class="st">"Bailed back to main, setjmp() returned 3490</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1121-31"><a href="setjmp.html#cb1121-31"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1121-32"><a href="setjmp.html#cb1121-32"></a>    <span class="op">}</span></span>
<span id="cb1121-33"><a href="setjmp.html#cb1121-33"></a><span class="op">}</span></span></code></pre></div>
<p>When run, this outputs:</p>
<div class="sourceCode" id="cb1122"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1122-1"><a href="setjmp.html#cb1122-1" aria-hidden="true" tabindex="-1"></a>Calling into functions, setjmp() returned 0</span>
<span id="cb1122-2"><a href="setjmp.html#cb1122-2" aria-hidden="true" tabindex="-1"></a>Entering depth 1</span>
<span id="cb1122-3"><a href="setjmp.html#cb1122-3" aria-hidden="true" tabindex="-1"></a>Entering depth 2</span>
<span id="cb1122-4"><a href="setjmp.html#cb1122-4" aria-hidden="true" tabindex="-1"></a>Bailed back to main, setjmp() returned 3490</span></code></pre></div>
<p>Notice that the second <code>printf()</code> in <code>case 0</code>
didn’t run; it got jumped over by <code>longjmp()</code>!</p>
<h3 class="unnumbered unlisted" id="see-also-105">See Also</h3>
<p><a href="setjmp.html#man-longjmp"><code>longjmp()</code></a></p>
<hr>
<h2 data-number="53.2" id="man-longjmp"><span class="header-section-number">53.2</span> <code>longjmp()</code></h2>
<p>Return to the previous <code>setjmp()</code> location</p>
<h3 class="unnumbered unlisted" id="synopsis-113">Synopsis</h3>
<div class="sourceCode" id="cb1123"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1123-1"><a href="setjmp.html#cb1123-1" aria-hidden="true" tabindex="-1"></a> <span class="pp">#include </span><span class="im">&lt;setjmp.h&gt;</span></span>
<span id="cb1123-2"><a href="setjmp.html#cb1123-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1123-3"><a href="setjmp.html#cb1123-3" aria-hidden="true" tabindex="-1"></a><span class="kw">_Noreturn</span> <span class="dt">void</span> longjmp<span class="op">(</span>jmp_buf env<span class="op">,</span> <span class="dt">int</span> val<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-113">Description</h3>
<p>This returns to a previous call to <code>setjmp()</code> back in the
call history. <code>setjmp()</code> will return the <code>val</code>
passed into <code>longjmp()</code>.</p>
<p>The <code>env</code> passed to <code>setjmp()</code> should be the
same one you pass into <code>longjmp()</code>.</p>
<p>There are a bunch of potential issues with doing this, so you’ll want
to be careful that you avoid undefined behavior by not doing the
following:</p>
<ol type="1">
<li><p>Don’t call <code>longjmp()</code> if the corresponding
<code>setjmp()</code> was in a different thread.</p></li>
<li><p>Don’t call <code>longjmp()</code> if you didn’t call
<code>setjmp()</code> first.</p></li>
<li><p>Don’t call <code>longjmp()</code> if the function that called
<code>setjmp()</code> has completed.</p></li>
<li><p>Don’t call <code>longjmp()</code> if the call to
<code>setjmp()</code> had a variable length array (VLA) in scope and the
scope has ended.</p></li>
<li><p>Don’t call <code>longjmp()</code> if there are any VLAs in any
active scopes between the <code>setjmp()</code> and the
<code>longjmp()</code>. A good rule of thumb here is to not mix VLAs and
<code>longjmp()</code>.</p></li>
</ol>
<p>Though <code>longjmp()</code> attempts to restore the machine to the
state at the <code>setjmp()</code>, including local variables, there are
some things that aren’t brought back to life:</p>
<ul>
<li>Non-volatile local variables that might have changed</li>
<li>Floating point status flags</li>
<li>Open files</li>
<li>Any other component of the abstract machine</li>
</ul>
<h3 class="unnumbered unlisted" id="return-value-112">Return Value</h3>
<p>This one is also funky in that it is one of the few functions in C
that never returns!</p>
<h3 class="unnumbered unlisted" id="example-113">Example</h3>
<p>Here’s a function that calls <code>setjmp()</code> to set things up
(where it returns <code>0</code>), then calls a couple levels deep into
functions, and finally short-circuits the return path by
<code>longjmp()</code>ing back to the place where <code>setjmp()</code>
was called, earlier. This time, it passes <code>3490</code> as a value,
which <code>setjmp()</code> returns.</p>
<div class="sourceCode" id="cb1124"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1124-1"><a href="setjmp.html#cb1124-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1124-2"><a href="setjmp.html#cb1124-2"></a><span class="pp">#include </span><span class="im">&lt;setjmp.h&gt;</span></span>
<span id="cb1124-3"><a href="setjmp.html#cb1124-3"></a></span>
<span id="cb1124-4"><a href="setjmp.html#cb1124-4"></a>jmp_buf env<span class="op">;</span></span>
<span id="cb1124-5"><a href="setjmp.html#cb1124-5"></a></span>
<span id="cb1124-6"><a href="setjmp.html#cb1124-6"></a><span class="dt">void</span> depth2<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1124-7"><a href="setjmp.html#cb1124-7"></a><span class="op">{</span></span>
<span id="cb1124-8"><a href="setjmp.html#cb1124-8"></a>    printf<span class="op">(</span><span class="st">"Entering depth 2</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1124-9"><a href="setjmp.html#cb1124-9"></a>    longjmp<span class="op">(</span>env<span class="op">,</span> <span class="dv">3490</span><span class="op">);</span>           <span class="co">// Jump back to setjmp()!!</span></span>
<span id="cb1124-10"><a href="setjmp.html#cb1124-10"></a>    printf<span class="op">(</span><span class="st">"Leaving depth 2</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This won't happen</span></span>
<span id="cb1124-11"><a href="setjmp.html#cb1124-11"></a><span class="op">}</span></span>
<span id="cb1124-12"><a href="setjmp.html#cb1124-12"></a></span>
<span id="cb1124-13"><a href="setjmp.html#cb1124-13"></a><span class="dt">void</span> depth1<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1124-14"><a href="setjmp.html#cb1124-14"></a><span class="op">{</span></span>
<span id="cb1124-15"><a href="setjmp.html#cb1124-15"></a>    printf<span class="op">(</span><span class="st">"Entering depth 1</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1124-16"><a href="setjmp.html#cb1124-16"></a>    depth2<span class="op">();</span></span>
<span id="cb1124-17"><a href="setjmp.html#cb1124-17"></a>    printf<span class="op">(</span><span class="st">"Leaving depth 1</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This won't happen</span></span>
<span id="cb1124-18"><a href="setjmp.html#cb1124-18"></a><span class="op">}</span></span>
<span id="cb1124-19"><a href="setjmp.html#cb1124-19"></a></span>
<span id="cb1124-20"><a href="setjmp.html#cb1124-20"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1124-21"><a href="setjmp.html#cb1124-21"></a><span class="op">{</span></span>
<span id="cb1124-22"><a href="setjmp.html#cb1124-22"></a>    <span class="cf">switch</span> <span class="op">(</span>setjmp<span class="op">(</span>env<span class="op">))</span> <span class="op">{</span></span>
<span id="cb1124-23"><a href="setjmp.html#cb1124-23"></a>        <span class="cf">case</span> <span class="dv">0</span><span class="op">:</span></span>
<span id="cb1124-24"><a href="setjmp.html#cb1124-24"></a>            printf<span class="op">(</span><span class="st">"Calling into functions, setjmp() returned 0</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1124-25"><a href="setjmp.html#cb1124-25"></a>            depth1<span class="op">();</span></span>
<span id="cb1124-26"><a href="setjmp.html#cb1124-26"></a>            printf<span class="op">(</span><span class="st">"Returned from functions</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// This won't happen</span></span>
<span id="cb1124-27"><a href="setjmp.html#cb1124-27"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1124-28"><a href="setjmp.html#cb1124-28"></a></span>
<span id="cb1124-29"><a href="setjmp.html#cb1124-29"></a>        <span class="cf">case</span> <span class="dv">3490</span><span class="op">:</span></span>
<span id="cb1124-30"><a href="setjmp.html#cb1124-30"></a>            printf<span class="op">(</span><span class="st">"Bailed back to main, setjmp() returned 3490</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1124-31"><a href="setjmp.html#cb1124-31"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1124-32"><a href="setjmp.html#cb1124-32"></a>    <span class="op">}</span></span>
<span id="cb1124-33"><a href="setjmp.html#cb1124-33"></a><span class="op">}</span></span></code></pre></div>
<p>When run, this outputs:</p>
<div class="sourceCode" id="cb1125"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1125-1"><a href="setjmp.html#cb1125-1" aria-hidden="true" tabindex="-1"></a>Calling into functions, setjmp() returned 0</span>
<span id="cb1125-2"><a href="setjmp.html#cb1125-2" aria-hidden="true" tabindex="-1"></a>Entering depth 1</span>
<span id="cb1125-3"><a href="setjmp.html#cb1125-3" aria-hidden="true" tabindex="-1"></a>Entering depth 2</span>
<span id="cb1125-4"><a href="setjmp.html#cb1125-4" aria-hidden="true" tabindex="-1"></a>Bailed back to main, setjmp() returned 3490</span></code></pre></div>
<p>Notice that the second <code>printf()</code> in <code>case 0</code>
didn’t run; it got jumped over by <code>longjmp()</code>!</p>
<h3 class="unnumbered unlisted" id="see-also-106">See Also</h3>
<p><a href="setjmp.html#man-setjmp"><code>setjmp()</code></a></p>


</body>