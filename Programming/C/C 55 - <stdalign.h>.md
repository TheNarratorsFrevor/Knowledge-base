<body>

<hr>
<h1 data-number="55" id="stdalign"><span class="header-section-number">55</span> <code>&lt;stdalign.h&gt;</code>
Macros for Alignment</h1>
<p>If you’re coding up something low-level like a memory allocator that
interfaces with your OS, you might need this header file. But most C
devs go their careers without using it.</p>
<p><a href="https://en.wikipedia.org/wiki/Data_structure_alignment"><em>Alignment</em></a><a href="#fn244" class="footnote-ref" id="fnref244" role="doc-noteref"><sup>244</sup></a> is all about multiples of
addresses on which objects can be stored. Can you store this at any
address? Or must it be a starting address that’s divisible by 2? Or 8?
Or 16?</p>
<table>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="stdalign.html#man-alignas"><code>alignas()</code></a></td>
<td>Specify alignment, expands to <code>_Alignas</code></td>
</tr>
<tr class="even">
<td><a href="stdalign.html#man-alignof"><code>alignof()</code></a></td>
<td>Get alignment, expands to <code>_Alignof</code></td>
</tr>
</tbody>
</table>
<p>These two additional macros are defined to be <code>1</code>:</p>
<div class="sourceCode" id="cb1138"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1138-1"><a href="stdalign.html#cb1138-1" aria-hidden="true" tabindex="-1"></a>__alignas_is_defined</span>
<span id="cb1138-2"><a href="stdalign.html#cb1138-2" aria-hidden="true" tabindex="-1"></a>__alignof_is_defined</span></code></pre></div>
<p>Quick note: alignments greater than that of <code>max_align_t</code>
are known as <em>overalignments</em> and are implementation-defined.</p>
<h2 data-number="55.1" id="man-alignas"><span class="header-section-number">55.1</span> <code>alignas()</code>
<code>_Alignas()</code></h2>
<p>Force a variable to have a certain alignment</p>
<h3 class="unnumbered unlisted" id="synopsis-116">Synopsis</h3>
<div class="sourceCode" id="cb1139"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1139-1"><a href="stdalign.html#cb1139-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdalign.h&gt;</span></span>
<span id="cb1139-2"><a href="stdalign.html#cb1139-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1139-3"><a href="stdalign.html#cb1139-3" aria-hidden="true" tabindex="-1"></a>alignas<span class="op">(</span>type<span class="op">-</span>name<span class="op">)</span></span>
<span id="cb1139-4"><a href="stdalign.html#cb1139-4" aria-hidden="true" tabindex="-1"></a>alignas<span class="op">(</span>constant<span class="op">-</span>expression<span class="op">)</span></span></code></pre></div>
<div class="sourceCode" id="cb1140"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1140-1"><a href="stdalign.html#cb1140-1" aria-hidden="true" tabindex="-1"></a><span class="kw">_Alignas</span><span class="op">(</span>type<span class="op">-</span>name<span class="op">)</span></span>
<span id="cb1140-2"><a href="stdalign.html#cb1140-2" aria-hidden="true" tabindex="-1"></a><span class="kw">_Alignas</span><span class="op">(</span>constant<span class="op">-</span>expression<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-116">Description</h3>
<p>Use this <em>alignment specifier</em> to force the alignment of
particular variables. For instance, we can declare <code>c</code> to be
<code>char</code>, but aligned as if it were an <code>int</code>:</p>
<div class="sourceCode" id="cb1141"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1141-1"><a href="stdalign.html#cb1141-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> alignas<span class="op">(</span><span class="dt">int</span><span class="op">)</span> c<span class="op">;</span></span></code></pre></div>
<p>You can put a constant integer expression in there, as well. The
compiler will probably impose limits on what these values can be. Small
powers of 2 (1, 2, 4, 8, and 16) are generally safe bets.</p>
<div class="sourceCode" id="cb1142"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1142-1"><a href="stdalign.html#cb1142-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> alignas<span class="op">(</span><span class="dv">8</span><span class="op">)</span> c<span class="op">;</span>   <span class="co">// align on 8-byte boundaries</span></span></code></pre></div>
<p>For convenience, you can also specify <code>0</code> if you want the
default alignment (as if you hadn’t said <code>alignas()</code> at
all):</p>
<div class="sourceCode" id="cb1143"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1143-1"><a href="stdalign.html#cb1143-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> alignas<span class="op">(</span><span class="dv">0</span><span class="op">)</span> c<span class="op">;</span>   <span class="co">// use default alignment for this type</span></span></code></pre></div>
<!--
### Return Value {.unnumbered .unlisted}
-->
<h3 class="unnumbered unlisted" id="example-116">Example</h3>
<div class="sourceCode" id="cb1144"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1144-1"><a href="stdalign.html#cb1144-1"></a><span class="pp">#include </span><span class="im">&lt;stdalign.h&gt;</span></span>
<span id="cb1144-2"><a href="stdalign.html#cb1144-2"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">     </span><span class="co">// for printf()</span></span>
<span id="cb1144-3"><a href="stdalign.html#cb1144-3"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span><span class="pp">    </span><span class="co">// for max_align_t</span></span>
<span id="cb1144-4"><a href="stdalign.html#cb1144-4"></a></span>
<span id="cb1144-5"><a href="stdalign.html#cb1144-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1144-6"><a href="stdalign.html#cb1144-6"></a><span class="op">{</span></span>
<span id="cb1144-7"><a href="stdalign.html#cb1144-7"></a>    <span class="dt">int</span> i<span class="op">,</span> j<span class="op">;</span></span>
<span id="cb1144-8"><a href="stdalign.html#cb1144-8"></a>    <span class="dt">char</span> alignas<span class="op">(</span><span class="dt">max_align_t</span><span class="op">)</span> a<span class="op">,</span> b<span class="op">;</span></span>
<span id="cb1144-9"><a href="stdalign.html#cb1144-9"></a>    <span class="dt">char</span> alignas<span class="op">(</span><span class="dt">int</span><span class="op">)</span> c<span class="op">,</span> d<span class="op">;</span></span>
<span id="cb1144-10"><a href="stdalign.html#cb1144-10"></a>    <span class="dt">char</span> e<span class="op">,</span> f<span class="op">;</span></span>
<span id="cb1144-11"><a href="stdalign.html#cb1144-11"></a></span>
<span id="cb1144-12"><a href="stdalign.html#cb1144-12"></a>    printf<span class="op">(</span><span class="st">"i: %p</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>i<span class="op">);</span></span>
<span id="cb1144-13"><a href="stdalign.html#cb1144-13"></a>    printf<span class="op">(</span><span class="st">"j: %p</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>j<span class="op">);</span></span>
<span id="cb1144-14"><a href="stdalign.html#cb1144-14"></a>    printf<span class="op">(</span><span class="st">"a: %p</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>a<span class="op">);</span></span>
<span id="cb1144-15"><a href="stdalign.html#cb1144-15"></a>    printf<span class="op">(</span><span class="st">"b: %p</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>b<span class="op">);</span></span>
<span id="cb1144-16"><a href="stdalign.html#cb1144-16"></a>    printf<span class="op">(</span><span class="st">"c: %p</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>c<span class="op">);</span></span>
<span id="cb1144-17"><a href="stdalign.html#cb1144-17"></a>    printf<span class="op">(</span><span class="st">"d: %p</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>d<span class="op">);</span></span>
<span id="cb1144-18"><a href="stdalign.html#cb1144-18"></a>    printf<span class="op">(</span><span class="st">"e: %p</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>e<span class="op">);</span></span>
<span id="cb1144-19"><a href="stdalign.html#cb1144-19"></a>    printf<span class="op">(</span><span class="st">"f: %p</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">(</span><span class="dt">void</span> <span class="op">*)&amp;</span>f<span class="op">);</span></span>
<span id="cb1144-20"><a href="stdalign.html#cb1144-20"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system follows. Notice the difference between the pairs
of values.</p>
<ul>
<li><code>i</code> and <code>j</code>, both <code>int</code>s, are
aligned on 4-byte boundaries.</li>
<li><code>a</code> and <code>b</code> have been forced to the boundary
of the type <code>max_align_t</code>, which is every 16 bytes on my
system.</li>
<li><code>c</code> and <code>d</code> have been forced to the same
alignment as <code>int</code>, which is 4 bytes, just like with
<code>i</code> and <code>j</code>.</li>
<li><code>e</code> and <code>f</code> do not have an alignment
specified, so they were stored with their default alignment of 1
byte.</li>
</ul>
<div class="sourceCode" id="cb1145"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1145-1"><a href="stdalign.html#cb1145-1" aria-hidden="true" tabindex="-1"></a>i: 0x7ffee7dfb4cc    &lt;-- difference of 4 bytes</span>
<span id="cb1145-2"><a href="stdalign.html#cb1145-2" aria-hidden="true" tabindex="-1"></a>j: 0x7ffee7dfb4c8</span>
<span id="cb1145-3"><a href="stdalign.html#cb1145-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1145-4"><a href="stdalign.html#cb1145-4" aria-hidden="true" tabindex="-1"></a>a: 0x7ffee7dfb4c0    &lt;-- difference of 16 bytes</span>
<span id="cb1145-5"><a href="stdalign.html#cb1145-5" aria-hidden="true" tabindex="-1"></a>b: 0x7ffee7dfb4b0</span>
<span id="cb1145-6"><a href="stdalign.html#cb1145-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1145-7"><a href="stdalign.html#cb1145-7" aria-hidden="true" tabindex="-1"></a>c: 0x7ffee7dfb4ac    &lt;-- difference of 4 bytes</span>
<span id="cb1145-8"><a href="stdalign.html#cb1145-8" aria-hidden="true" tabindex="-1"></a>d: 0x7ffee7dfb4a8</span>
<span id="cb1145-9"><a href="stdalign.html#cb1145-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1145-10"><a href="stdalign.html#cb1145-10" aria-hidden="true" tabindex="-1"></a>e: 0x7ffee7dfb4a7    &lt;-- difference of 1 byte</span>
<span id="cb1145-11"><a href="stdalign.html#cb1145-11" aria-hidden="true" tabindex="-1"></a>f: 0x7ffee7dfb4a6</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-109">See Also</h3>
<p><a href="stdalign.html#man-alignof"><code>alignof</code></a>, <a href="#man-max_align_t"><code>max_align_t</code></a></p>
<hr>
<h2 data-number="55.2" id="man-alignof"><span class="header-section-number">55.2</span> <code>alignof()</code>
<code>_Alignof()</code></h2>
<p>Get the alignment of a type</p>
<h3 class="unnumbered unlisted" id="synopsis-117">Synopsis</h3>
<div class="sourceCode" id="cb1146"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1146-1"><a href="stdalign.html#cb1146-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdalign.h&gt;</span></span>
<span id="cb1146-2"><a href="stdalign.html#cb1146-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1146-3"><a href="stdalign.html#cb1146-3" aria-hidden="true" tabindex="-1"></a>alignof<span class="op">(</span>type<span class="op">-</span>name<span class="op">)</span></span></code></pre></div>
<div class="sourceCode" id="cb1147"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1147-1"><a href="stdalign.html#cb1147-1" aria-hidden="true" tabindex="-1"></a><span class="kw">_Alignof</span><span class="op">(</span>type<span class="op">-</span>name<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-117">Description</h3>
<p>This evaluates to a value of type <code>size_t</code> that gives the
alignment of a particular type on your system.</p>
<h3 class="unnumbered unlisted" id="return-value-115">Return Value</h3>
<p>Returns the alignment value, i.e.&nbsp;the address of the beginning of the
given type of object must begin on an address boundary divisible by this
number.</p>
<h3 class="unnumbered unlisted" id="example-117">Example</h3>
<p>Print out the alignments of a variety of different types.</p>
<div class="sourceCode" id="cb1148"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1148-1"><a href="stdalign.html#cb1148-1"></a><span class="pp">#include </span><span class="im">&lt;stdalign.h&gt;</span></span>
<span id="cb1148-2"><a href="stdalign.html#cb1148-2"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">     </span><span class="co">// for printf()</span></span>
<span id="cb1148-3"><a href="stdalign.html#cb1148-3"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span><span class="pp">    </span><span class="co">// for max_align_t</span></span>
<span id="cb1148-4"><a href="stdalign.html#cb1148-4"></a></span>
<span id="cb1148-5"><a href="stdalign.html#cb1148-5"></a><span class="kw">struct</span> t <span class="op">{</span></span>
<span id="cb1148-6"><a href="stdalign.html#cb1148-6"></a>    <span class="dt">int</span> a<span class="op">;</span></span>
<span id="cb1148-7"><a href="stdalign.html#cb1148-7"></a>    <span class="dt">char</span> b<span class="op">;</span></span>
<span id="cb1148-8"><a href="stdalign.html#cb1148-8"></a>    <span class="dt">float</span> c<span class="op">;</span></span>
<span id="cb1148-9"><a href="stdalign.html#cb1148-9"></a><span class="op">};</span></span>
<span id="cb1148-10"><a href="stdalign.html#cb1148-10"></a></span>
<span id="cb1148-11"><a href="stdalign.html#cb1148-11"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1148-12"><a href="stdalign.html#cb1148-12"></a><span class="op">{</span></span>
<span id="cb1148-13"><a href="stdalign.html#cb1148-13"></a>    printf<span class="op">(</span><span class="st">"char       : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">char</span><span class="op">));</span></span>
<span id="cb1148-14"><a href="stdalign.html#cb1148-14"></a>    printf<span class="op">(</span><span class="st">"short      : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">short</span><span class="op">));</span></span>
<span id="cb1148-15"><a href="stdalign.html#cb1148-15"></a>    printf<span class="op">(</span><span class="st">"int        : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">int</span><span class="op">));</span></span>
<span id="cb1148-16"><a href="stdalign.html#cb1148-16"></a>    printf<span class="op">(</span><span class="st">"long       : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">long</span><span class="op">));</span></span>
<span id="cb1148-17"><a href="stdalign.html#cb1148-17"></a>    printf<span class="op">(</span><span class="st">"long long  : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">long</span> <span class="dt">long</span><span class="op">));</span></span>
<span id="cb1148-18"><a href="stdalign.html#cb1148-18"></a>    printf<span class="op">(</span><span class="st">"double     : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">double</span><span class="op">));</span></span>
<span id="cb1148-19"><a href="stdalign.html#cb1148-19"></a>    printf<span class="op">(</span><span class="st">"long double: %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span><span class="op">));</span></span>
<span id="cb1148-20"><a href="stdalign.html#cb1148-20"></a>    printf<span class="op">(</span><span class="st">"struct t   : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="kw">struct</span> t<span class="op">));</span></span>
<span id="cb1148-21"><a href="stdalign.html#cb1148-21"></a>    printf<span class="op">(</span><span class="st">"max_align_t: %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> alignof<span class="op">(</span><span class="dt">max_align_t</span><span class="op">));</span></span>
<span id="cb1148-22"><a href="stdalign.html#cb1148-22"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1149"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1149-1"><a href="stdalign.html#cb1149-1" aria-hidden="true" tabindex="-1"></a>char       : 1</span>
<span id="cb1149-2"><a href="stdalign.html#cb1149-2" aria-hidden="true" tabindex="-1"></a>short      : 2</span>
<span id="cb1149-3"><a href="stdalign.html#cb1149-3" aria-hidden="true" tabindex="-1"></a>int        : 4</span>
<span id="cb1149-4"><a href="stdalign.html#cb1149-4" aria-hidden="true" tabindex="-1"></a>long       : 8</span>
<span id="cb1149-5"><a href="stdalign.html#cb1149-5" aria-hidden="true" tabindex="-1"></a>long long  : 8</span>
<span id="cb1149-6"><a href="stdalign.html#cb1149-6" aria-hidden="true" tabindex="-1"></a>double     : 8</span>
<span id="cb1149-7"><a href="stdalign.html#cb1149-7" aria-hidden="true" tabindex="-1"></a>long double: 16</span>
<span id="cb1149-8"><a href="stdalign.html#cb1149-8" aria-hidden="true" tabindex="-1"></a>struct t   : 16</span>
<span id="cb1149-9"><a href="stdalign.html#cb1149-9" aria-hidden="true" tabindex="-1"></a>max_align_t: 16</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-110">See Also</h3>
<p><a href="stdalign.html#man-alignas"><code>alignas</code></a>, <a href="#man-max_align_t"><code>max_align_t</code></a></p>

</body>