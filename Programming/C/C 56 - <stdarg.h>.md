<body>

<hr>
<h1 data-number="56" id="stdarg"><span class="header-section-number">56</span> <code>&lt;stdarg.h&gt;</code>
Variable Arguments</h1>
<table>
<colgroup>
<col style="width: 26%">
<col style="width: 73%">
</colgroup>
<thead>
<tr class="header">
<th>Macro</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="stdarg.html#man-va_arg"><code>va_arg()</code></a></td>
<td>Get the next variable argument</td>
</tr>
<tr class="even">
<td><a href="stdarg.html#man-va_copy"><code>va_copy()</code></a></td>
<td>Copy a <code>va_list</code> and the work done so far</td>
</tr>
<tr class="odd">
<td><a href="stdarg.html#man-va_end"><code>va_end()</code></a></td>
<td>Signify we’re done processing variable arguments</td>
</tr>
<tr class="even">
<td><a href="stdarg.html#man-va_start"><code>va_start()</code></a></td>
<td>Initialize a <code>va_list</code> to start variable argument
processing</td>
</tr>
</tbody>
</table>
<p>This header file is what allows you to write functions that take a
variable number of arguments.</p>
<p>In addition to the macros, you get a new type that helps C keep track
of where it is in the variable-number-of-arguments-processing:
<code>va_list</code>. This type is opaque, and you’ll be passing it
around to the various macros to help get at the arguments.</p>
<p>Note that every variadic function requires at least one non-variable
parameter. You need this to kick off processing with
<code>va_start()</code>.</p>
<hr>
<h2 data-number="56.1" id="man-va_arg"><span class="header-section-number">56.1</span> <code>va_arg()</code></h2>
<p>Get the next variable argument</p>
<h3 class="unnumbered unlisted" id="synopsis-118">Synopsis</h3>
<div class="sourceCode" id="cb1150"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1150-1"><a href="stdarg.html#cb1150-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1150-2"><a href="stdarg.html#cb1150-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1150-3"><a href="stdarg.html#cb1150-3" aria-hidden="true" tabindex="-1"></a>type va_arg<span class="op">(</span><span class="dt">va_list</span> ap<span class="op">,</span> type<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-118">Description</h3>
<p>If you have a variable argument list you’ve initialized with
<code>va_start()</code>, pass it to this one along with the type of
argument you’re trying to get, e.g.</p>
<div class="sourceCode" id="cb1151"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1151-1"><a href="stdarg.html#cb1151-1" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span>   x <span class="op">=</span> va_arg<span class="op">(</span>args<span class="op">,</span> <span class="dt">int</span><span class="op">);</span></span>
<span id="cb1151-2"><a href="stdarg.html#cb1151-2" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> y <span class="op">=</span> va_arg<span class="op">(</span>args<span class="op">,</span> <span class="dt">float</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-116">Return Value</h3>
<p>Evaluates to the value and type of the next variable argument.</p>
<h3 class="unnumbered unlisted" id="example-118">Example</h3>
<p>Here’s a demo that adds together an arbitrary number of integers. The
first argument is the number of integers to add together. We’ll make use
of that to figure out how many times we have to call
<code>va_arg()</code>.</p>
<div class="sourceCode" id="cb1152"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1152-1"><a href="stdarg.html#cb1152-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1152-2"><a href="stdarg.html#cb1152-2"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1152-3"><a href="stdarg.html#cb1152-3"></a></span>
<span id="cb1152-4"><a href="stdarg.html#cb1152-4"></a><span class="dt">int</span> add<span class="op">(</span><span class="dt">int</span> count<span class="op">,</span> <span class="op">...)</span></span>
<span id="cb1152-5"><a href="stdarg.html#cb1152-5"></a><span class="op">{</span></span>
<span id="cb1152-6"><a href="stdarg.html#cb1152-6"></a>    <span class="dt">int</span> total <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1152-7"><a href="stdarg.html#cb1152-7"></a>    <span class="dt">va_list</span> va<span class="op">;</span></span>
<span id="cb1152-8"><a href="stdarg.html#cb1152-8"></a></span>
<span id="cb1152-9"><a href="stdarg.html#cb1152-9"></a>    va_start<span class="op">(</span>va<span class="op">,</span> count<span class="op">);</span>   <span class="co">// Start with arguments after "count"</span></span>
<span id="cb1152-10"><a href="stdarg.html#cb1152-10"></a></span>
<span id="cb1152-11"><a href="stdarg.html#cb1152-11"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> count<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1152-12"><a href="stdarg.html#cb1152-12"></a>        <span class="dt">int</span> n <span class="op">=</span> va_arg<span class="op">(</span>va<span class="op">,</span> <span class="dt">int</span><span class="op">);</span>   <span class="co">// Get the next int</span></span>
<span id="cb1152-13"><a href="stdarg.html#cb1152-13"></a></span>
<span id="cb1152-14"><a href="stdarg.html#cb1152-14"></a>        total <span class="op">+=</span> n<span class="op">;</span></span>
<span id="cb1152-15"><a href="stdarg.html#cb1152-15"></a>    <span class="op">}</span></span>
<span id="cb1152-16"><a href="stdarg.html#cb1152-16"></a></span>
<span id="cb1152-17"><a href="stdarg.html#cb1152-17"></a>    va_end<span class="op">(</span>va<span class="op">);</span>  <span class="co">// All done</span></span>
<span id="cb1152-18"><a href="stdarg.html#cb1152-18"></a></span>
<span id="cb1152-19"><a href="stdarg.html#cb1152-19"></a>    <span class="cf">return</span> total<span class="op">;</span></span>
<span id="cb1152-20"><a href="stdarg.html#cb1152-20"></a><span class="op">}</span></span>
<span id="cb1152-21"><a href="stdarg.html#cb1152-21"></a></span>
<span id="cb1152-22"><a href="stdarg.html#cb1152-22"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1152-23"><a href="stdarg.html#cb1152-23"></a><span class="op">{</span></span>
<span id="cb1152-24"><a href="stdarg.html#cb1152-24"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> add<span class="op">(</span><span class="dv">4</span><span class="op">,</span> <span class="dv">6</span><span class="op">,</span> <span class="dv">2</span><span class="op">,</span> <span class="op">-</span><span class="dv">4</span><span class="op">,</span> <span class="dv">17</span><span class="op">));</span>  <span class="co">// 6 + 2 - 4 + 17 = 21</span></span>
<span id="cb1152-25"><a href="stdarg.html#cb1152-25"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> add<span class="op">(</span><span class="dv">2</span><span class="op">,</span> <span class="dv">22</span><span class="op">,</span> <span class="dv">44</span><span class="op">));</span>        <span class="co">// 22 + 44 = 66</span></span>
<span id="cb1152-26"><a href="stdarg.html#cb1152-26"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-111">See Also</h3>
<p><a href="stdarg.html#man-va_start"><code>va_start()</code></a>, <a href="#man-va_end"><code>va_end()</code></a></p>
<hr>
<h2 data-number="56.2" id="man-va_copy"><span class="header-section-number">56.2</span> <code>va_copy()</code></h2>
<p>Copy a <code>va_list</code> and the work done so far</p>
<h3 class="unnumbered unlisted" id="synopsis-119">Synopsis</h3>
<div class="sourceCode" id="cb1153"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1153-1"><a href="stdarg.html#cb1153-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1153-2"><a href="stdarg.html#cb1153-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1153-3"><a href="stdarg.html#cb1153-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> va_copy<span class="op">(</span><span class="dt">va_list</span> dest<span class="op">,</span> <span class="dt">va_list</span> src<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-119">Description</h3>
<p>The main intended use of this is to save your state partway through
processing variable arguments so you can scan ahead and then rewind back
to the save point.</p>
<p>You pass in a <code>src</code> <code>va_list</code> and it copies it
to <code>dest</code>.</p>
<p>If you’ve already called this once for a particular
<code>dest</code>, you can’t call it (or <code>va_start()</code>) again
with the same <code>dest</code> unless you call <code>va_end()</code> on
that <code>dest</code> first.</p>
<div class="sourceCode" id="cb1154"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1154-1"><a href="stdarg.html#cb1154-1" aria-hidden="true" tabindex="-1"></a>va_copy<span class="op">(</span>dest<span class="op">,</span> src<span class="op">);</span></span>
<span id="cb1154-2"><a href="stdarg.html#cb1154-2" aria-hidden="true" tabindex="-1"></a>va_copy<span class="op">(</span>dest<span class="op">,</span> src2<span class="op">);</span>  <span class="co">// BAD!</span></span>
<span id="cb1154-3"><a href="stdarg.html#cb1154-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1154-4"><a href="stdarg.html#cb1154-4" aria-hidden="true" tabindex="-1"></a>va_copy<span class="op">(</span>dest<span class="op">,</span> src<span class="op">);</span></span>
<span id="cb1154-5"><a href="stdarg.html#cb1154-5" aria-hidden="true" tabindex="-1"></a>va_start<span class="op">(</span>dest<span class="op">,</span> var<span class="op">);</span>  <span class="co">// BAD!</span></span>
<span id="cb1154-6"><a href="stdarg.html#cb1154-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1154-7"><a href="stdarg.html#cb1154-7" aria-hidden="true" tabindex="-1"></a>va_copy<span class="op">(</span>dest<span class="op">,</span> src<span class="op">);</span></span>
<span id="cb1154-8"><a href="stdarg.html#cb1154-8" aria-hidden="true" tabindex="-1"></a>va_end<span class="op">(</span>dest<span class="op">);</span></span>
<span id="cb1154-9"><a href="stdarg.html#cb1154-9" aria-hidden="true" tabindex="-1"></a>va_copy<span class="op">(</span>dest<span class="op">,</span> src2<span class="op">);</span>  <span class="co">// OK!</span></span>
<span id="cb1154-10"><a href="stdarg.html#cb1154-10" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1154-11"><a href="stdarg.html#cb1154-11" aria-hidden="true" tabindex="-1"></a>va_copy<span class="op">(</span>dest<span class="op">,</span> src<span class="op">);</span></span>
<span id="cb1154-12"><a href="stdarg.html#cb1154-12" aria-hidden="true" tabindex="-1"></a>va_end<span class="op">(</span>dest<span class="op">);</span></span>
<span id="cb1154-13"><a href="stdarg.html#cb1154-13" aria-hidden="true" tabindex="-1"></a>va_start<span class="op">(</span>dest<span class="op">,</span> var<span class="op">);</span>  <span class="co">// OK!</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-117">Return Value</h3>
<p>Returns nothing.</p>
<h3 class="unnumbered unlisted" id="example-119">Example</h3>
<p>Here’s an example where we’re adding together all the variable
arguments, but then we want to go back and add on all the numbers past
the first two, for example if the arguments are:</p>
<div class="sourceCode" id="cb1155"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1155-1"><a href="stdarg.html#cb1155-1" aria-hidden="true" tabindex="-1"></a>10 20 30 40</span></code></pre></div>
<p>First we add them all for <code>100</code>, and then we add on
everything from the third number on, so add on <code>30+40</code> for a
total of <code>170</code>.</p>
<p>We’ll do this by saving our place in the variable argument processing
with <code>va_copy</code> and then using that later to reprocess the
trailing arguments.</p>
<p>(And yes, I know there’s a mathematical way to do this without all
the rewinding, but I’m having an heck of a time coming up with a good
example!)</p>
<div class="sourceCode" id="cb1156"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1156-1"><a href="stdarg.html#cb1156-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1156-2"><a href="stdarg.html#cb1156-2"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1156-3"><a href="stdarg.html#cb1156-3"></a></span>
<span id="cb1156-4"><a href="stdarg.html#cb1156-4"></a><span class="co">// Add all the numbers together, but then add on all the numbers</span></span>
<span id="cb1156-5"><a href="stdarg.html#cb1156-5"></a><span class="co">// past the second one again.</span></span>
<span id="cb1156-6"><a href="stdarg.html#cb1156-6"></a><span class="dt">int</span> contrived_adder<span class="op">(</span><span class="dt">int</span> count<span class="op">,</span> <span class="op">...)</span></span>
<span id="cb1156-7"><a href="stdarg.html#cb1156-7"></a><span class="op">{</span></span>
<span id="cb1156-8"><a href="stdarg.html#cb1156-8"></a>    <span class="cf">if</span> <span class="op">(</span>count <span class="op">&lt;</span> <span class="dv">3</span><span class="op">)</span> <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span> <span class="co">// OK, I'm being lazy. You got me.</span></span>
<span id="cb1156-9"><a href="stdarg.html#cb1156-9"></a></span>
<span id="cb1156-10"><a href="stdarg.html#cb1156-10"></a>    <span class="dt">int</span> total <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1156-11"><a href="stdarg.html#cb1156-11"></a></span>
<span id="cb1156-12"><a href="stdarg.html#cb1156-12"></a>    <span class="dt">va_list</span> args<span class="op">,</span> mid_args<span class="op">;</span></span>
<span id="cb1156-13"><a href="stdarg.html#cb1156-13"></a></span>
<span id="cb1156-14"><a href="stdarg.html#cb1156-14"></a>    va_start<span class="op">(</span>args<span class="op">,</span> count<span class="op">);</span></span>
<span id="cb1156-15"><a href="stdarg.html#cb1156-15"></a></span>
<span id="cb1156-16"><a href="stdarg.html#cb1156-16"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> count<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1156-17"><a href="stdarg.html#cb1156-17"></a></span>
<span id="cb1156-18"><a href="stdarg.html#cb1156-18"></a>        <span class="co">// If we're at the second number, save our place in</span></span>
<span id="cb1156-19"><a href="stdarg.html#cb1156-19"></a>        <span class="co">// mid_args:</span></span>
<span id="cb1156-20"><a href="stdarg.html#cb1156-20"></a></span>
<span id="cb1156-21"><a href="stdarg.html#cb1156-21"></a>        <span class="cf">if</span> <span class="op">(</span>i <span class="op">==</span> <span class="dv">2</span><span class="op">)</span></span>
<span id="cb1156-22"><a href="stdarg.html#cb1156-22"></a>            va_copy<span class="op">(</span>mid_args<span class="op">,</span> args<span class="op">);</span></span>
<span id="cb1156-23"><a href="stdarg.html#cb1156-23"></a></span>
<span id="cb1156-24"><a href="stdarg.html#cb1156-24"></a>        total <span class="op">+=</span> va_arg<span class="op">(</span>args<span class="op">,</span> <span class="dt">int</span><span class="op">);</span></span>
<span id="cb1156-25"><a href="stdarg.html#cb1156-25"></a>    <span class="op">}</span></span>
<span id="cb1156-26"><a href="stdarg.html#cb1156-26"></a></span>
<span id="cb1156-27"><a href="stdarg.html#cb1156-27"></a>    va_end<span class="op">(</span>args<span class="op">);</span> <span class="co">// Done with this</span></span>
<span id="cb1156-28"><a href="stdarg.html#cb1156-28"></a></span>
<span id="cb1156-29"><a href="stdarg.html#cb1156-29"></a>    <span class="co">// But now let's start with mid_args and add all those on:</span></span>
<span id="cb1156-30"><a href="stdarg.html#cb1156-30"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> count <span class="op">-</span> <span class="dv">2</span><span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1156-31"><a href="stdarg.html#cb1156-31"></a>        total <span class="op">+=</span> va_arg<span class="op">(</span>mid_args<span class="op">,</span> <span class="dt">int</span><span class="op">);</span></span>
<span id="cb1156-32"><a href="stdarg.html#cb1156-32"></a></span>
<span id="cb1156-33"><a href="stdarg.html#cb1156-33"></a>    va_end<span class="op">(</span>mid_args<span class="op">);</span> <span class="co">// Done with this, too</span></span>
<span id="cb1156-34"><a href="stdarg.html#cb1156-34"></a></span>
<span id="cb1156-35"><a href="stdarg.html#cb1156-35"></a>    <span class="cf">return</span> total<span class="op">;</span></span>
<span id="cb1156-36"><a href="stdarg.html#cb1156-36"></a><span class="op">}</span></span>
<span id="cb1156-37"><a href="stdarg.html#cb1156-37"></a></span>
<span id="cb1156-38"><a href="stdarg.html#cb1156-38"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1156-39"><a href="stdarg.html#cb1156-39"></a><span class="op">{</span></span>
<span id="cb1156-40"><a href="stdarg.html#cb1156-40"></a>    <span class="co">// 10+20+30 + 30 == 90</span></span>
<span id="cb1156-41"><a href="stdarg.html#cb1156-41"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> contrived_adder<span class="op">(</span><span class="dv">3</span><span class="op">,</span> <span class="dv">10</span><span class="op">,</span> <span class="dv">20</span><span class="op">,</span> <span class="dv">30</span><span class="op">));</span></span>
<span id="cb1156-42"><a href="stdarg.html#cb1156-42"></a></span>
<span id="cb1156-43"><a href="stdarg.html#cb1156-43"></a>    <span class="co">// 10+20+30+40+50 + 30+40+50 == 270</span></span>
<span id="cb1156-44"><a href="stdarg.html#cb1156-44"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> contrived_adder<span class="op">(</span><span class="dv">5</span><span class="op">,</span> <span class="dv">10</span><span class="op">,</span> <span class="dv">20</span><span class="op">,</span> <span class="dv">30</span><span class="op">,</span> <span class="dv">40</span><span class="op">,</span> <span class="dv">50</span><span class="op">));</span></span>
<span id="cb1156-45"><a href="stdarg.html#cb1156-45"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-112">See Also</h3>
<p><a href="stdarg.html#man-va_start"><code>va_start()</code></a>, <a href="#man-va_arg"><code>va_arg()</code></a>, <a href="#man-va_end"><code>va_end()</code></a></p>
<hr>
<h2 data-number="56.3" id="man-va_end"><span class="header-section-number">56.3</span> <code>va_end()</code></h2>
<p>Signify we’re done processing variable arguments</p>
<h3 class="unnumbered unlisted" id="synopsis-120">Synopsis</h3>
<div class="sourceCode" id="cb1157"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1157-1"><a href="stdarg.html#cb1157-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1157-2"><a href="stdarg.html#cb1157-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1157-3"><a href="stdarg.html#cb1157-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> va_end<span class="op">(</span><span class="dt">va_list</span> ap<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-120">Description</h3>
<p>After you’ve <code>va_start()</code>ed or <code>va_copy</code>’d a
new <code>va_list</code>, you <strong>must</strong> call
<code>va_end()</code> with it before it goes out of scope.</p>
<p>You also have to do this if you’re going to call
<code>va_start()</code> or <code>va_copy()</code> <em>again</em> on a
variable you’ve already done that to.</p>
<p>Them’s the rules if you want to avoid undefined behavior.</p>
<p>But just think of it as cleanup. You called <code>va_start()</code>,
so you’ll call <code>va_end()</code> when you’re done.</p>
<h3 class="unnumbered unlisted" id="return-value-118">Return Value</h3>
<p>Returns nothing.</p>
<h3 class="unnumbered unlisted" id="example-120">Example</h3>
<p>Here’s a demo that adds together an arbitrary number of integers. The
first argument is the number of integers to add together. We’ll make use
of that to figure out how many times we have to call
<code>va_arg()</code>.</p>
<div class="sourceCode" id="cb1158"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1158-1"><a href="stdarg.html#cb1158-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1158-2"><a href="stdarg.html#cb1158-2"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1158-3"><a href="stdarg.html#cb1158-3"></a></span>
<span id="cb1158-4"><a href="stdarg.html#cb1158-4"></a><span class="dt">int</span> add<span class="op">(</span><span class="dt">int</span> count<span class="op">,</span> <span class="op">...)</span></span>
<span id="cb1158-5"><a href="stdarg.html#cb1158-5"></a><span class="op">{</span></span>
<span id="cb1158-6"><a href="stdarg.html#cb1158-6"></a>    <span class="dt">int</span> total <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1158-7"><a href="stdarg.html#cb1158-7"></a>    <span class="dt">va_list</span> va<span class="op">;</span></span>
<span id="cb1158-8"><a href="stdarg.html#cb1158-8"></a></span>
<span id="cb1158-9"><a href="stdarg.html#cb1158-9"></a>    va_start<span class="op">(</span>va<span class="op">,</span> count<span class="op">);</span>   <span class="co">// Start with arguments after "count"</span></span>
<span id="cb1158-10"><a href="stdarg.html#cb1158-10"></a></span>
<span id="cb1158-11"><a href="stdarg.html#cb1158-11"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> count<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1158-12"><a href="stdarg.html#cb1158-12"></a>        <span class="dt">int</span> n <span class="op">=</span> va_arg<span class="op">(</span>va<span class="op">,</span> <span class="dt">int</span><span class="op">);</span>   <span class="co">// Get the next int</span></span>
<span id="cb1158-13"><a href="stdarg.html#cb1158-13"></a></span>
<span id="cb1158-14"><a href="stdarg.html#cb1158-14"></a>        total <span class="op">+=</span> n<span class="op">;</span></span>
<span id="cb1158-15"><a href="stdarg.html#cb1158-15"></a>    <span class="op">}</span></span>
<span id="cb1158-16"><a href="stdarg.html#cb1158-16"></a></span>
<span id="cb1158-17"><a href="stdarg.html#cb1158-17"></a>    va_end<span class="op">(</span>va<span class="op">);</span>  <span class="co">// All done</span></span>
<span id="cb1158-18"><a href="stdarg.html#cb1158-18"></a></span>
<span id="cb1158-19"><a href="stdarg.html#cb1158-19"></a>    <span class="cf">return</span> total<span class="op">;</span></span>
<span id="cb1158-20"><a href="stdarg.html#cb1158-20"></a><span class="op">}</span></span>
<span id="cb1158-21"><a href="stdarg.html#cb1158-21"></a></span>
<span id="cb1158-22"><a href="stdarg.html#cb1158-22"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1158-23"><a href="stdarg.html#cb1158-23"></a><span class="op">{</span></span>
<span id="cb1158-24"><a href="stdarg.html#cb1158-24"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> add<span class="op">(</span><span class="dv">4</span><span class="op">,</span> <span class="dv">6</span><span class="op">,</span> <span class="dv">2</span><span class="op">,</span> <span class="op">-</span><span class="dv">4</span><span class="op">,</span> <span class="dv">17</span><span class="op">));</span>  <span class="co">// 6 + 2 - 4 + 17 = 21</span></span>
<span id="cb1158-25"><a href="stdarg.html#cb1158-25"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> add<span class="op">(</span><span class="dv">2</span><span class="op">,</span> <span class="dv">22</span><span class="op">,</span> <span class="dv">44</span><span class="op">));</span>        <span class="co">// 22 + 44 = 66</span></span>
<span id="cb1158-26"><a href="stdarg.html#cb1158-26"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-113">See Also</h3>
<p><a href="stdarg.html#man-va_start"><code>va_start()</code></a>, <a href="#man-va_copy"><code>va_copy()</code></a></p>
<hr>
<h2 data-number="56.4" id="man-va_start"><span class="header-section-number">56.4</span> <code>va_start()</code></h2>
<p>Initialize a <code>va_list</code> to start variable argument
processing</p>
<h3 class="unnumbered unlisted" id="synopsis-121">Synopsis</h3>
<div class="sourceCode" id="cb1159"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1159-1"><a href="stdarg.html#cb1159-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1159-2"><a href="stdarg.html#cb1159-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1159-3"><a href="stdarg.html#cb1159-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> va_start<span class="op">(</span><span class="dt">va_list</span> ap<span class="op">,</span> parmN<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-121">Description</h3>
<p>You’ve declared a variable of type <code>va_list</code> to keep track
of the variable argument processing… now how to initialize it so you can
start calling <code>va_arg()</code> to get those arguments?</p>
<p><code>va_start()</code> to the rescue!</p>
<p>What you do is pass in your <code>va_list</code>, here shown as
parameter <code>ap</code>. Just pass the list, not a pointer to it.</p>
<p>Then for the second argument to <code>va_start()</code>, you give the
name of the parameter that you want to start processing arguments
<em>after</em>. This must be the parameter right before the
<code>...</code> in the argument list.</p>
<p>If you’ve already called <code>va_start()</code> on a particular
<code>va_list</code> and you want to call <code>va_start()</code> on it
again, you <strong>must</strong> call <code>va_end()</code> first!</p>
<h3 class="unnumbered unlisted" id="return-value-119">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-121">Example</h3>
<p>Here’s a demo that adds together an arbitrary number of integers. The
first argument is the number of integers to add together. We’ll make use
of that to figure out how many times we have to call
<code>va_arg()</code>.</p>
<div class="sourceCode" id="cb1160"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1160-1"><a href="stdarg.html#cb1160-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1160-2"><a href="stdarg.html#cb1160-2"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1160-3"><a href="stdarg.html#cb1160-3"></a></span>
<span id="cb1160-4"><a href="stdarg.html#cb1160-4"></a><span class="dt">int</span> add<span class="op">(</span><span class="dt">int</span> count<span class="op">,</span> <span class="op">...)</span></span>
<span id="cb1160-5"><a href="stdarg.html#cb1160-5"></a><span class="op">{</span></span>
<span id="cb1160-6"><a href="stdarg.html#cb1160-6"></a>    <span class="dt">int</span> total <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1160-7"><a href="stdarg.html#cb1160-7"></a>    <span class="dt">va_list</span> va<span class="op">;</span></span>
<span id="cb1160-8"><a href="stdarg.html#cb1160-8"></a></span>
<span id="cb1160-9"><a href="stdarg.html#cb1160-9"></a>    va_start<span class="op">(</span>va<span class="op">,</span> count<span class="op">);</span>   <span class="co">// Start with arguments after "count"</span></span>
<span id="cb1160-10"><a href="stdarg.html#cb1160-10"></a></span>
<span id="cb1160-11"><a href="stdarg.html#cb1160-11"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> count<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1160-12"><a href="stdarg.html#cb1160-12"></a>        <span class="dt">int</span> n <span class="op">=</span> va_arg<span class="op">(</span>va<span class="op">,</span> <span class="dt">int</span><span class="op">);</span>   <span class="co">// Get the next int</span></span>
<span id="cb1160-13"><a href="stdarg.html#cb1160-13"></a></span>
<span id="cb1160-14"><a href="stdarg.html#cb1160-14"></a>        total <span class="op">+=</span> n<span class="op">;</span></span>
<span id="cb1160-15"><a href="stdarg.html#cb1160-15"></a>    <span class="op">}</span></span>
<span id="cb1160-16"><a href="stdarg.html#cb1160-16"></a></span>
<span id="cb1160-17"><a href="stdarg.html#cb1160-17"></a>    va_end<span class="op">(</span>va<span class="op">);</span>  <span class="co">// All done</span></span>
<span id="cb1160-18"><a href="stdarg.html#cb1160-18"></a></span>
<span id="cb1160-19"><a href="stdarg.html#cb1160-19"></a>    <span class="cf">return</span> total<span class="op">;</span></span>
<span id="cb1160-20"><a href="stdarg.html#cb1160-20"></a><span class="op">}</span></span>
<span id="cb1160-21"><a href="stdarg.html#cb1160-21"></a></span>
<span id="cb1160-22"><a href="stdarg.html#cb1160-22"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1160-23"><a href="stdarg.html#cb1160-23"></a><span class="op">{</span></span>
<span id="cb1160-24"><a href="stdarg.html#cb1160-24"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> add<span class="op">(</span><span class="dv">4</span><span class="op">,</span> <span class="dv">6</span><span class="op">,</span> <span class="dv">2</span><span class="op">,</span> <span class="op">-</span><span class="dv">4</span><span class="op">,</span> <span class="dv">17</span><span class="op">));</span>  <span class="co">// 6 + 2 - 4 + 17 = 21</span></span>
<span id="cb1160-25"><a href="stdarg.html#cb1160-25"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> add<span class="op">(</span><span class="dv">2</span><span class="op">,</span> <span class="dv">22</span><span class="op">,</span> <span class="dv">44</span><span class="op">));</span>        <span class="co">// 22 + 44 = 66</span></span>
<span id="cb1160-26"><a href="stdarg.html#cb1160-26"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-114">See Also</h3>
<p><a href="stdarg.html#man-va_arg"><code>va_arg()</code></a>, <a href="#man-va_end"><code>va_end()</code></a></p>


</body>