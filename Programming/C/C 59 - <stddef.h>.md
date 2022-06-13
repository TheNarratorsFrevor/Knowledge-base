<body>

<hr>
<h1 data-number="59" id="stddef"><span class="header-section-number">59</span> <code>&lt;stddef.h&gt;</code> A
Few Standard Definitions</h1>
<p>Despite its name, I’ve haven’t seen this frequently included.</p>
<p>It includes several types and macros.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="stddef.html#man-ptrdiff_t"><code>ptrdiff_t</code></a></td>
<td>Signed integer difference between two pointers</td>
</tr>
<tr class="even">
<td><a href="stddef.html#man-size_t"><code>size_t</code></a></td>
<td>Unsigned integer type returned by <code>sizeof</code></td>
</tr>
<tr class="odd">
<td><a href="stddef.html#man-max_align_t"><code>max_align_t</code></a></td>
<td>Declare a type with the biggest possible alignment</td>
</tr>
<tr class="even">
<td><a href="stddef.html#man-wchar_t"><code>wchar_t</code></a></td>
<td>Wide character type</td>
</tr>
<tr class="odd">
<td><code>NULL</code></td>
<td><code>NULL</code> pointer, as defined a number of places</td>
</tr>
<tr class="even">
<td><a href="stddef.html#man-offsetof"><code>offsetof</code></a></td>
<td>Get the byte offsets of <code>struct</code> or <code>union</code>
fields</td>
</tr>
</tbody>
</table>
<h2 data-number="59.1" id="man-ptrdiff_t"><span class="header-section-number">59.1</span> <code>ptrdiff_t</code></h2>
<p>This holds the different between two pointers. You could store this
in another type, but the result of a pointer subtraction is an
implementation-defined type; you can be maximally portable by using
<code>ptrdiff_t</code>.</p>
<div class="sourceCode" id="cb1202"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1202-1"><a href="stddef.html#cb1202-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1202-2"><a href="stddef.html#cb1202-2"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span></span>
<span id="cb1202-3"><a href="stddef.html#cb1202-3"></a></span>
<span id="cb1202-4"><a href="stddef.html#cb1202-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1202-5"><a href="stddef.html#cb1202-5"></a><span class="op">{</span></span>
<span id="cb1202-6"><a href="stddef.html#cb1202-6"></a>    <span class="dt">int</span> cats<span class="op">[</span><span class="dv">100</span><span class="op">];</span></span>
<span id="cb1202-7"><a href="stddef.html#cb1202-7"></a></span>
<span id="cb1202-8"><a href="stddef.html#cb1202-8"></a>    <span class="dt">int</span> <span class="op">*</span>f <span class="op">=</span> cats <span class="op">+</span> <span class="dv">20</span><span class="op">;</span></span>
<span id="cb1202-9"><a href="stddef.html#cb1202-9"></a>    <span class="dt">int</span> <span class="op">*</span>g <span class="op">=</span> cats <span class="op">+</span> <span class="dv">60</span><span class="op">;</span></span>
<span id="cb1202-10"><a href="stddef.html#cb1202-10"></a></span>
<span id="cb1202-11"><a href="stddef.html#cb1202-11"></a>    <span class="dt">ptrdiff_t</span> d <span class="op">=</span> g <span class="op">-</span> f<span class="op">;</span>  <span class="co">// difference is 40</span></span></code></pre></div>
<p>And you can print it by prefixing the integer format specifier with
<code>t</code>:</p>
<div class="sourceCode" id="cb1203" data-startfrom="13"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c" style="counter-reset: source-line 12;"><span id="cb1203-13"><a href="stddef.html#cb1203-13"></a>    printf<span class="op">(</span><span class="st">"%td</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> d<span class="op">);</span>  <span class="co">// Print decimal: 40</span></span>
<span id="cb1203-14"><a href="stddef.html#cb1203-14"></a>    printf<span class="op">(</span><span class="st">"%tX</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> d<span class="op">);</span>  <span class="co">// Print hex:     28</span></span>
<span id="cb1203-15"><a href="stddef.html#cb1203-15"></a><span class="op">}</span></span></code></pre></div>
<h2 data-number="59.2" id="man-size_t"><span class="header-section-number">59.2</span> <code>size_t</code></h2>
<p>This is the type returned by <code>sizeof</code> and used in a few
other places. It’s an unsigned integer.</p>
<p>You can print it using the <code>z</code> prefix in
<code>printf()</code>:</p>
<div class="sourceCode" id="cb1204"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1204-1"><a href="stddef.html#cb1204-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1204-2"><a href="stddef.html#cb1204-2"></a><span class="pp">#include </span><span class="im">&lt;uchar.h&gt;</span></span>
<span id="cb1204-3"><a href="stddef.html#cb1204-3"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1204-4"><a href="stddef.html#cb1204-4"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span></span>
<span id="cb1204-5"><a href="stddef.html#cb1204-5"></a></span>
<span id="cb1204-6"><a href="stddef.html#cb1204-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1204-7"><a href="stddef.html#cb1204-7"></a><span class="op">{</span></span>
<span id="cb1204-8"><a href="stddef.html#cb1204-8"></a>    <span class="dt">size_t</span> x<span class="op">;</span></span>
<span id="cb1204-9"><a href="stddef.html#cb1204-9"></a></span>
<span id="cb1204-10"><a href="stddef.html#cb1204-10"></a>    x <span class="op">=</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">);</span></span>
<span id="cb1204-11"><a href="stddef.html#cb1204-11"></a></span>
<span id="cb1204-12"><a href="stddef.html#cb1204-12"></a>    printf<span class="op">(</span><span class="st">"%zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span></code></pre></div>
<p>Some functions return negative numbers cast to <code>size_t</code> as
error values (such as <a href="#man-mbrtoc16"><code>mbrtoc16()</code></a>). If you want to print
these as negative values, you can do it with <code>%zd</code>:</p>
<div class="sourceCode" id="cb1205" data-startfrom="14"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c" style="counter-reset: source-line 13;"><span id="cb1205-14"><a href="stddef.html#cb1205-14"></a>    char16_t a<span class="op">;</span></span>
<span id="cb1205-15"><a href="stddef.html#cb1205-15"></a>    mbstate_t mbs<span class="op">;</span></span>
<span id="cb1205-16"><a href="stddef.html#cb1205-16"></a>    memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span></span>
<span id="cb1205-17"><a href="stddef.html#cb1205-17"></a></span>
<span id="cb1205-18"><a href="stddef.html#cb1205-18"></a>    x <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>a<span class="op">,</span> <span class="st">"b"</span><span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1205-19"><a href="stddef.html#cb1205-19"></a></span>
<span id="cb1205-20"><a href="stddef.html#cb1205-20"></a>    printf<span class="op">(</span><span class="st">"%zd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb1205-21"><a href="stddef.html#cb1205-21"></a><span class="op">}</span></span></code></pre></div>
<h2 data-number="59.3" id="man-max_align_t"><span class="header-section-number">59.3</span> <code>max_align_t</code></h2>
<p>As far as I can tell, this exists to allow the runtime computation of
the maximum fundamental <a href="https://en.wikipedia.org/wiki/Data_structure_alignment">alignment</a><a href="#fn252" class="footnote-ref" id="fnref252" role="doc-noteref"><sup>252</sup></a> on the current platform. Someone
please mail me if there’s another use.</p>
<p>Maybe you need this if you’re writing your own memory allocator or
somesuch.</p>
<div class="sourceCode" id="cb1206"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1206-1"><a href="stddef.html#cb1206-1"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span></span>
<span id="cb1206-2"><a href="stddef.html#cb1206-2"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">      </span><span class="co">// For printf()</span></span>
<span id="cb1206-3"><a href="stddef.html#cb1206-3"></a><span class="pp">#include </span><span class="im">&lt;stdalign.h&gt;</span><span class="pp">   </span><span class="co">// For alignof</span></span>
<span id="cb1206-4"><a href="stddef.html#cb1206-4"></a></span>
<span id="cb1206-5"><a href="stddef.html#cb1206-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1206-6"><a href="stddef.html#cb1206-6"></a><span class="op">{</span></span>
<span id="cb1206-7"><a href="stddef.html#cb1206-7"></a>    <span class="dt">int</span> max <span class="op">=</span> alignof<span class="op">(</span><span class="dt">max_align_t</span><span class="op">);</span></span>
<span id="cb1206-8"><a href="stddef.html#cb1206-8"></a></span>
<span id="cb1206-9"><a href="stddef.html#cb1206-9"></a>    printf<span class="op">(</span><span class="st">"Maximum fundamental alignment: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> max<span class="op">);</span></span>
<span id="cb1206-10"><a href="stddef.html#cb1206-10"></a><span class="op">}</span></span></code></pre></div>
<p>On my system, this prints:</p>
<div class="sourceCode" id="cb1207"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1207-1"><a href="stddef.html#cb1207-1" aria-hidden="true" tabindex="-1"></a>Maximum fundamental alignment: 16</span></code></pre></div>
<p>See also <a href="stdalign.html#man-alignas"><code>alignas</code></a>, <a href="#man-alignof"><code>alignof</code></a>.</p>
<h2 data-number="59.4" id="man-wchar_t"><span class="header-section-number">59.4</span> <code>wchar_t</code></h2>
<p>This is analogous to <code>char</code>, except it’s for <a href="#wide-characters">wide characters</a>.</p>
<p>It’s an integer type that has enough range to hold unique values for
all characters in all supported locales.</p>
<p>The value <code>0</code> is the wide <code>NUL</code> character.</p>
<p>Finally, the values of character constants from the <a href="#src-exec-charset">basic character set</a> will be the same as
their corresponding <code>wchar_t</code> values… unless
<code>__STDC_MB_MIGHT_NEQ_WC__</code> is defined.</p>
<h2 data-number="59.5" id="man-offsetof"><span class="header-section-number">59.5</span> <code>offsetof</code></h2>
<p>If you have a <code>struct</code> or <code>union</code>, you can use
this to get the byte offset of fields within that type.</p>
<p>Usage is:</p>
<div class="sourceCode" id="cb1208"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1208-1"><a href="stddef.html#cb1208-1" aria-hidden="true" tabindex="-1"></a>offsetof<span class="op">(</span>type<span class="op">,</span> fieldname<span class="op">);</span></span></code></pre></div>
<p>The resulting value has type <code>size_t</code>.</p>
<p>Here’s an example that prints the field offsets of a
<code>struct</code>:</p>
<div class="sourceCode" id="cb1209"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1209-1"><a href="stddef.html#cb1209-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1209-2"><a href="stddef.html#cb1209-2"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span></span>
<span id="cb1209-3"><a href="stddef.html#cb1209-3"></a></span>
<span id="cb1209-4"><a href="stddef.html#cb1209-4"></a><span class="kw">struct</span> foo <span class="op">{</span></span>
<span id="cb1209-5"><a href="stddef.html#cb1209-5"></a>    <span class="dt">int</span> a<span class="op">;</span></span>
<span id="cb1209-6"><a href="stddef.html#cb1209-6"></a>    <span class="dt">char</span> b<span class="op">;</span></span>
<span id="cb1209-7"><a href="stddef.html#cb1209-7"></a>    <span class="dt">char</span> c<span class="op">;</span></span>
<span id="cb1209-8"><a href="stddef.html#cb1209-8"></a>    <span class="dt">float</span> d<span class="op">;</span></span>
<span id="cb1209-9"><a href="stddef.html#cb1209-9"></a><span class="op">};</span></span>
<span id="cb1209-10"><a href="stddef.html#cb1209-10"></a></span>
<span id="cb1209-11"><a href="stddef.html#cb1209-11"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1209-12"><a href="stddef.html#cb1209-12"></a><span class="op">{</span></span>
<span id="cb1209-13"><a href="stddef.html#cb1209-13"></a>    printf<span class="op">(</span><span class="st">"a: %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> offsetof<span class="op">(</span><span class="kw">struct</span> foo<span class="op">,</span> a<span class="op">));</span></span>
<span id="cb1209-14"><a href="stddef.html#cb1209-14"></a>    printf<span class="op">(</span><span class="st">"b: %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> offsetof<span class="op">(</span><span class="kw">struct</span> foo<span class="op">,</span> b<span class="op">));</span></span>
<span id="cb1209-15"><a href="stddef.html#cb1209-15"></a>    printf<span class="op">(</span><span class="st">"c: %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> offsetof<span class="op">(</span><span class="kw">struct</span> foo<span class="op">,</span> c<span class="op">));</span></span>
<span id="cb1209-16"><a href="stddef.html#cb1209-16"></a>    printf<span class="op">(</span><span class="st">"d: %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> offsetof<span class="op">(</span><span class="kw">struct</span> foo<span class="op">,</span> d<span class="op">));</span></span>
<span id="cb1209-17"><a href="stddef.html#cb1209-17"></a><span class="op">}</span></span></code></pre></div>
<p>On my system, this outputs:</p>
<div class="sourceCode" id="cb1210"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1210-1"><a href="stddef.html#cb1210-1" aria-hidden="true" tabindex="-1"></a>a: 0</span>
<span id="cb1210-2"><a href="stddef.html#cb1210-2" aria-hidden="true" tabindex="-1"></a>b: 4</span>
<span id="cb1210-3"><a href="stddef.html#cb1210-3" aria-hidden="true" tabindex="-1"></a>c: 5</span>
<span id="cb1210-4"><a href="stddef.html#cb1210-4" aria-hidden="true" tabindex="-1"></a>d: 8</span></code></pre></div>
<p>And you can’t use <code>offsetof</code> on a bitfield, so don’t get
your hopes up.</p>

</body>