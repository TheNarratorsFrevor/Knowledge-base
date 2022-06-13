<body>

<hr>
<h1 data-number="58" id="stdbool"><span class="header-section-number">58</span> <code>&lt;stdbool.h&gt;</code>
Boolean Types</h1>
<p>This is a small header file that defines a number of convenient
Boolean macros. If you really need that kind of thing.</p>
<table>
<thead>
<tr class="header">
<th>Macro</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>bool</code></td>
<td>Type for Boolean, expands to <code>_Bool</code></td>
</tr>
<tr class="even">
<td><code>true</code></td>
<td>True value, expands to <code>1</code></td>
</tr>
<tr class="odd">
<td><code>false</code></td>
<td>False value, expands to <code>0</code></td>
</tr>
</tbody>
</table>
<p>There’s on more macro that I’m not putting in the table because it’s
such a long name it’ll blow up the table alignment:</p>
<div class="sourceCode" id="cb1199"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1199-1"><a href="stdbool.html#cb1199-1" aria-hidden="true" tabindex="-1"></a>__bool_true_false_are_defined</span></code></pre></div>
<p>which expands to <code>1</code>.</p>
<h2 data-number="58.1" id="example-135"><span class="header-section-number">58.1</span> Example</h2>
<p>Here’s a lame example that shows off these macros.</p>
<div class="sourceCode" id="cb1200"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1200-1"><a href="stdbool.html#cb1200-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1200-2"><a href="stdbool.html#cb1200-2"></a><span class="pp">#include </span><span class="im">&lt;stdbool.h&gt;</span></span>
<span id="cb1200-3"><a href="stdbool.html#cb1200-3"></a></span>
<span id="cb1200-4"><a href="stdbool.html#cb1200-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1200-5"><a href="stdbool.html#cb1200-5"></a><span class="op">{</span></span>
<span id="cb1200-6"><a href="stdbool.html#cb1200-6"></a>    <span class="dt">bool</span> x<span class="op">;</span></span>
<span id="cb1200-7"><a href="stdbool.html#cb1200-7"></a></span>
<span id="cb1200-8"><a href="stdbool.html#cb1200-8"></a>    x <span class="op">=</span> <span class="op">(</span><span class="dv">3</span> <span class="op">&gt;</span> <span class="dv">2</span><span class="op">);</span></span>
<span id="cb1200-9"><a href="stdbool.html#cb1200-9"></a></span>
<span id="cb1200-10"><a href="stdbool.html#cb1200-10"></a>    <span class="cf">if</span> <span class="op">(</span>x <span class="op">==</span> true<span class="op">)</span></span>
<span id="cb1200-11"><a href="stdbool.html#cb1200-11"></a>        printf<span class="op">(</span><span class="st">"The universe still makes sense.</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1200-12"><a href="stdbool.html#cb1200-12"></a></span>
<span id="cb1200-13"><a href="stdbool.html#cb1200-13"></a>    x <span class="op">=</span> false<span class="op">;</span></span>
<span id="cb1200-14"><a href="stdbool.html#cb1200-14"></a></span>
<span id="cb1200-15"><a href="stdbool.html#cb1200-15"></a>    printf<span class="op">(</span><span class="st">"x is now %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span>  <span class="co">// 0</span></span>
<span id="cb1200-16"><a href="stdbool.html#cb1200-16"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1201"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1201-1"><a href="stdbool.html#cb1201-1" aria-hidden="true" tabindex="-1"></a>The universe still makes sense.</span>
<span id="cb1201-2"><a href="stdbool.html#cb1201-2" aria-hidden="true" tabindex="-1"></a>x is now 0</span></code></pre></div>
<h2 data-number="58.2" id="bool"><span class="header-section-number">58.2</span> <code>_Bool</code>?</h2>
<p>What’s the deal with <code>_Bool</code>? Why didn’t they just make it
<code>bool</code>?</p>
<p>Well, there was a lot of C code out there where people had defined
their own <code>bool</code> type and adding an official
<code>bool</code> would have broken those <code>typedef</code>s.</p>
<p>But C has already reserved all identifiers that start with an
underscore followed by a capital letter, so it was clear to make up a
new <code>_Bool</code> type and go with that.</p>
<p>And, if you know your code can handle it, you can include this header
to get all this juicy syntax.</p>
<p>One more note on conversions: unlike converting to <code>int</code>,
the <em>only</em> thing that converts to <code>false</code> in a
<code>_Bool</code> is a scalar zero value. Anything at all that’s not
zero, like <code>-3490</code>, <code>0.12</code>, or <code>NaN</code>,
converts to <code>true</code>.</p>


</body>