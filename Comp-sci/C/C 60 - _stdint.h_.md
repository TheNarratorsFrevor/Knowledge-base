<body>

<hr>
<h1 data-number="60" id="stdint"><span class="header-section-number">60</span> <code>&lt;stdint.h&gt;</code>
More Integer Types</h1>
<p>This header gives us access to (potentially) types of a fixed number
of bits, or, at the very least, types that are at least that many
bits.</p>
<p>It also gives us handy macros to use.</p>
<h2 data-number="60.1" id="specific-width-integers"><span class="header-section-number">60.1</span> Specific-Width Integers</h2>
<p>There are three main classes of types defined here, signed and
unsigned:</p>
<ul>
<li>Integers of exactly a certain size
(<code>int</code><em>N</em><code>_t</code>,
<code>uint</code><em>N</em><code>_t</code>)</li>
<li>Integers that are at least a certain size
(<code>int_least</code><em>N</em><code>_t</code>,
<code>uint_least</code><em>N</em><code>_t</code>)</li>
<li>Integers that are at least a certain size and are as fast as
possible (<code>int_fast</code><em>N</em><code>_t</code>,
<code>uint_fast</code><em>N</em><code>_t</code>)</li>
</ul>
<p>Where the <em>N</em> occurs, you substitute the number of bits,
commonly multiples of 8, e.g.&nbsp;<code>uint16_t</code>.</p>
<p>The following types are guaranteed to be defined:</p>
<div class="sourceCode" id="cb1211"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1211-1"><a href="stdint.html#cb1211-1" aria-hidden="true" tabindex="-1"></a><span class="dt">int_least8_t</span>      <span class="dt">uint_least8_t</span></span>
<span id="cb1211-2"><a href="stdint.html#cb1211-2" aria-hidden="true" tabindex="-1"></a><span class="dt">int_least16_t</span>     <span class="dt">uint_least16_t</span></span>
<span id="cb1211-3"><a href="stdint.html#cb1211-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int_least32_t</span>     <span class="dt">uint_least32_t</span></span>
<span id="cb1211-4"><a href="stdint.html#cb1211-4" aria-hidden="true" tabindex="-1"></a><span class="dt">int_least64_t</span>     <span class="dt">uint_least64_t</span></span>
<span id="cb1211-5"><a href="stdint.html#cb1211-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1211-6"><a href="stdint.html#cb1211-6" aria-hidden="true" tabindex="-1"></a><span class="dt">int_fast8_t</span>       <span class="dt">uint_fast8_t</span></span>
<span id="cb1211-7"><a href="stdint.html#cb1211-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int_fast16_t</span>      <span class="dt">uint_fast16_t</span></span>
<span id="cb1211-8"><a href="stdint.html#cb1211-8" aria-hidden="true" tabindex="-1"></a><span class="dt">int_fast32_t</span>      <span class="dt">uint_fast32_t</span></span>
<span id="cb1211-9"><a href="stdint.html#cb1211-9" aria-hidden="true" tabindex="-1"></a><span class="dt">int_fast64_t</span>      <span class="dt">uint_fast64_t</span></span></code></pre></div>
<p>Everything else is optional, but you’ll probably also have the
following, which are required when a system has integers of these sizes
with no padding and two’s-complement representation… which is the case
for Macs and PCs and a lot of other systems. In short, you very likely
have these:</p>
<div class="sourceCode" id="cb1212"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1212-1"><a href="stdint.html#cb1212-1" aria-hidden="true" tabindex="-1"></a><span class="dt">int8_t</span>      <span class="dt">uint8_t</span></span>
<span id="cb1212-2"><a href="stdint.html#cb1212-2" aria-hidden="true" tabindex="-1"></a><span class="dt">int16_t</span>     <span class="dt">uint16_t</span></span>
<span id="cb1212-3"><a href="stdint.html#cb1212-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int32_t</span>     <span class="dt">uint32_t</span></span>
<span id="cb1212-4"><a href="stdint.html#cb1212-4" aria-hidden="true" tabindex="-1"></a><span class="dt">int64_t</span>     <span class="dt">uint64_t</span></span></code></pre></div>
<p>Other numbers of bits can also be supported by an implementation if
it wants to go all crazy with it.</p>
<p>Examples:</p>
<div class="sourceCode" id="cb1213"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1213-1"><a href="stdint.html#cb1213-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdint.h&gt;</span></span>
<span id="cb1213-2"><a href="stdint.html#cb1213-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1213-3"><a href="stdint.html#cb1213-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1213-4"><a href="stdint.html#cb1213-4" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1213-5"><a href="stdint.html#cb1213-5" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int16_t</span> x <span class="op">=</span> <span class="dv">32</span><span class="op">;</span></span>
<span id="cb1213-6"><a href="stdint.html#cb1213-6" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int_fast32_t</span> y <span class="op">=</span> <span class="dv">3490</span><span class="op">;</span></span>
<span id="cb1213-7"><a href="stdint.html#cb1213-7" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1213-8"><a href="stdint.html#cb1213-8" aria-hidden="true" tabindex="-1"></a>    <span class="co">// ...</span></span></code></pre></div>
<h2 data-number="60.2" id="other-integer-types"><span class="header-section-number">60.2</span> Other Integer Types</h2>
<p>There are a couple optional types that are integers capable of
holding pointer types.</p>
<div class="sourceCode" id="cb1214"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1214-1"><a href="stdint.html#cb1214-1" aria-hidden="true" tabindex="-1"></a><span class="dt">intptr_t</span></span>
<span id="cb1214-2"><a href="stdint.html#cb1214-2" aria-hidden="true" tabindex="-1"></a><span class="dt">uintptr_t</span></span></code></pre></div>
<p>You can convert a <code>void*</code> to one of these types, and back
again. And the <code>void*</code>s will compare equal.</p>
<p>The use case is any place you need an integer that represents a
pointer for some reason.</p>
<p>Also, there are a couple types that are just there to be the biggest
possible integers your system supports:</p>
<div class="sourceCode" id="cb1215"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1215-1"><a href="stdint.html#cb1215-1" aria-hidden="true" tabindex="-1"></a><span class="dt">intmax_t</span></span>
<span id="cb1215-2"><a href="stdint.html#cb1215-2" aria-hidden="true" tabindex="-1"></a><span class="dt">uintmax_t</span></span></code></pre></div>
<p>Fun fact: you can print these types with the <code>"%jd"</code> and
<code>"%ju"</code> <a href="stdio.html#man-printf"><code>printf()</code></a>
format specifiers.</p>
<p>There are also a bunch of macros in
<code>&lt;inttypes.h&gt;</code>(#inttypes) that you can use to print any
of the types mentioned, above.</p>
<h2 data-number="60.3" id="macros-2"><span class="header-section-number">60.3</span> Macros</h2>
<p>The following macros define the minimum and maximum values for these
types:</p>
<div class="sourceCode" id="cb1216"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1216-1"><a href="stdint.html#cb1216-1" aria-hidden="true" tabindex="-1"></a>INT8_MAX           INT8_MIN           UINT8_MAX</span>
<span id="cb1216-2"><a href="stdint.html#cb1216-2" aria-hidden="true" tabindex="-1"></a>INT16_MAX          INT16_MIN          UINT16_MAX</span>
<span id="cb1216-3"><a href="stdint.html#cb1216-3" aria-hidden="true" tabindex="-1"></a>INT32_MAX          INT32_MIN          UINT32_MAX</span>
<span id="cb1216-4"><a href="stdint.html#cb1216-4" aria-hidden="true" tabindex="-1"></a>INT64_MAX          INT64_MIN          UINT64_MAX</span>
<span id="cb1216-5"><a href="stdint.html#cb1216-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1216-6"><a href="stdint.html#cb1216-6" aria-hidden="true" tabindex="-1"></a>INT_LEAST8_MAX     INT_LEAST8_MIN     UINT_LEAST8_MAX</span>
<span id="cb1216-7"><a href="stdint.html#cb1216-7" aria-hidden="true" tabindex="-1"></a>INT_LEAST16_MAX    INT_LEAST16_MIN    UINT_LEAST16_MAX</span>
<span id="cb1216-8"><a href="stdint.html#cb1216-8" aria-hidden="true" tabindex="-1"></a>INT_LEAST32_MAX    INT_LEAST32_MIN    UINT_LEAST32_MAX</span>
<span id="cb1216-9"><a href="stdint.html#cb1216-9" aria-hidden="true" tabindex="-1"></a>INT_LEAST64_MAX    INT_LEAST64_MIN    UINT_LEAST64_MAX</span>
<span id="cb1216-10"><a href="stdint.html#cb1216-10" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1216-11"><a href="stdint.html#cb1216-11" aria-hidden="true" tabindex="-1"></a>INT_FAST8_MAX      INT_FAST8_MIN      UINT_FAST8_MAX</span>
<span id="cb1216-12"><a href="stdint.html#cb1216-12" aria-hidden="true" tabindex="-1"></a>INT_FAST16_MAX     INT_FAST16_MIN     UINT_FAST16_MAX</span>
<span id="cb1216-13"><a href="stdint.html#cb1216-13" aria-hidden="true" tabindex="-1"></a>INT_FAST32_MAX     INT_FAST32_MIN     UINT_FAST32_MAX</span>
<span id="cb1216-14"><a href="stdint.html#cb1216-14" aria-hidden="true" tabindex="-1"></a>INT_FAST64_MAX     INT_FAST64_MIN     UINT_FAST64_MAX</span>
<span id="cb1216-15"><a href="stdint.html#cb1216-15" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1216-16"><a href="stdint.html#cb1216-16" aria-hidden="true" tabindex="-1"></a>INTMAX_MAX         INTMAX_MIN         UINTMAX_MAX</span>
<span id="cb1216-17"><a href="stdint.html#cb1216-17" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1216-18"><a href="stdint.html#cb1216-18" aria-hidden="true" tabindex="-1"></a>INTPTR_MAX         INTPTR_MIN         UINTPTR_MAX</span></code></pre></div>
<p>For the exact-bit-size signed types, the minimum is exactly <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D441 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mo stretchy="false">(</mo><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mi>N</mi><mo>−</mo><mn>1</mn></mrow></msup><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> and the maximum is exactly
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D441 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mi>N</mi><mo>−</mo><mn>1</mn></mrow></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>. And for the
exact-bit-size unsigned types, the max is exactly <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D441 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mi>N</mi></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>For the signed “least” and “fast” variants, the magnitude and sign of
the minimum is at least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D441 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mo stretchy="false">(</mo><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mi>N</mi><mo>−</mo><mn>1</mn></mrow></msup><mo>−</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> and the maximum is at least
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D441 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mi>N</mi><mo>−</mo><mn>1</mn></mrow></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>. And for unsigned it’s at
least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D441 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mi>N</mi></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>.</p>
<p><code>INTMAX_MAX</code> is at least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c36"></mjx-c><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>63</mn></mrow></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>, <code>INTMAX_MIN</code> is at
least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c36"></mjx-c><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mo stretchy="false">(</mo><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>63</mn></mrow></msup><mo>−</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> in sign and
magnitude. And <code>UINTMAX_MAX</code> is at least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c36"></mjx-c><mjx-c class="mjx-c34"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>64</mn></mrow></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>Finally, <code>INTPTR_MAX</code> is at least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>15</mn></mrow></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>, <code>INTPTR_MIN</code> is at
least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mo stretchy="false">(</mo><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>15</mn></mrow></msup><mo>−</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> in sign and
magnitude. And <code>UINTPTR_MAX</code> is at least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c36"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>16</mn></mrow></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>.</p>
<h2 data-number="60.4" id="other-limits"><span class="header-section-number">60.4</span> Other Limits</h2>
<p>There are a bunch of types in
<code>&lt;inttypes.h&gt;</code>(#inttypes) that have their limits
defined here. (<code>&lt;inttypes.h&gt;</code> includes
<code>&lt;stdint.h&gt;</code>.)</p>
<table>
<thead>
<tr class="header">
<th>Macro</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>PTRDIFF_MIN</code></td>
<td>Minimum <code>ptrdiff_t</code> value</td>
</tr>
<tr class="even">
<td><code>PTRDIFF_MAX</code></td>
<td>Maximum <code>ptrdiff_t</code> value</td>
</tr>
<tr class="odd">
<td><code>SIG_ATOMIC_MIN</code></td>
<td>Minimum <code>sig_atomic_t</code> value</td>
</tr>
<tr class="even">
<td><code>SIG_ATOMIC_MAX</code></td>
<td>Maximum <code>sig_atomic_t</code> value</td>
</tr>
<tr class="odd">
<td><code>SIZE_MAX</code></td>
<td>Maximum <code>size_t</code> value</td>
</tr>
<tr class="even">
<td><code>WCHAR_MIN</code></td>
<td>Minimum <code>wchar_t</code> value</td>
</tr>
<tr class="odd">
<td><code>WCHAR_MAX</code></td>
<td>Maximum <code>wchar_t</code> value</td>
</tr>
<tr class="even">
<td><code>WINT_MIN</code></td>
<td>Minimum <code>wint_t</code> value</td>
</tr>
<tr class="odd">
<td><code>WINT_MAX</code></td>
<td>Maximum <code>wint_t</code> value</td>
</tr>
</tbody>
</table>
<p>The spec says that <code>PTRDIFF_MIN</code> will be at least -65535
in magnitude. And <code>PTRDIFF_MAX</code> and <code>SIZE_MAX</code>
will be at least 65535.</p>
<p><code>SIG_ATOMIC_MIN</code> and <code>MAX</code> will be either -127
and 127 (if it’s signed) or 0 and 255 (if it’s unsigned).</p>
<p>Same for <code>WCHAR_MIN</code> and <code>MAX</code>.</p>
<p><code>WINT_MIN</code> and <code>MAX</code> will be either -32767 and
32767 (if it’s signed) or 0 and 65535 (if it’s unsigned).</p>
<h2 data-number="60.5" id="macros-for-declaring-constants"><span class="header-section-number">60.5</span> Macros for Declaring
Constants</h2>
<p>If you recall, you can specify a type for integer constants:</p>
<div class="sourceCode" id="cb1217"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1217-1"><a href="stdint.html#cb1217-1" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> x <span class="op">=</span> <span class="dv">12</span><span class="op">;</span></span>
<span id="cb1217-2"><a href="stdint.html#cb1217-2" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> y <span class="op">=</span> <span class="dv">12</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1217-3"><a href="stdint.html#cb1217-3" aria-hidden="true" tabindex="-1"></a><span class="dt">unsigned</span> <span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> z <span class="op">=</span> <span class="dv">12</span><span class="bu">ULL</span><span class="op">;</span></span></code></pre></div>
<p>You can use the macros <code>INT</code><em>N</em><code>_C()</code>
and <code>UINT</code><em>N</em><code>()</code> where <em>N</em> is
<code>8</code>, <code>16</code>, <code>32</code> or <code>64</code>.</p>
<div class="sourceCode" id="cb1218"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1218-1"><a href="stdint.html#cb1218-1" aria-hidden="true" tabindex="-1"></a><span class="dt">uint_least16_t</span> x <span class="op">=</span> INT16_C<span class="op">(</span><span class="dv">3490</span><span class="op">);</span></span>
<span id="cb1218-2"><a href="stdint.html#cb1218-2" aria-hidden="true" tabindex="-1"></a><span class="dt">uint_least64_t</span> y <span class="op">=</span> INT64_C<span class="op">(</span><span class="dv">1122334455</span><span class="op">);</span></span></code></pre></div>
<p>A variant on these is <code>INTMAX_C()</code> and
<code>UINTMAX_C()</code>. They will make a constant suitable for storing
in an <code>intmax_t</code> or <code>uintmax_t</code>.</p>
<div class="sourceCode" id="cb1219"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1219-1"><a href="stdint.html#cb1219-1" aria-hidden="true" tabindex="-1"></a><span class="dt">intmax_t</span> x <span class="op">=</span> INTMAX_C<span class="op">(</span><span class="dv">3490</span><span class="op">);</span></span>
<span id="cb1219-2"><a href="stdint.html#cb1219-2" aria-hidden="true" tabindex="-1"></a><span class="dt">uintmax_t</span> x <span class="op">=</span> UINTMAX_C<span class="op">(</span><span class="dv">1122334455</span><span class="op">);</span></span></code></pre></div>


</body>