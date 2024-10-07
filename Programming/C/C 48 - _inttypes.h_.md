<body>

<hr>
<h1 data-number="48" id="inttypes"><span class="header-section-number">48</span> <code>&lt;inttypes.h&gt;</code>
More Integer Conversions</h1>
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
<td><a href="inttypes.html#man-imaxabs"><code>imaxabs()</code></a></td>
<td>Compute the absolute value of an <code>intmax_t</code></td>
</tr>
<tr class="even">
<td><a href="inttypes.html#man-imaxdiv"><code>imaxdiv()</code></a></td>
<td>Compute the quotient and remainder of <code>intmax_t</code>s</td>
</tr>
<tr class="odd">
<td><a href="inttypes.html#man-strtoimax"><code>strtoimax()</code></a></td>
<td>Convert strings to type <code>intmax_t</code></td>
</tr>
<tr class="even">
<td><a href="inttypes.html#man-strtoimax"><code>strtoumax()</code></a></td>
<td>Convert strings to type <code>uintmax_t</code></td>
</tr>
<tr class="odd">
<td><a href="inttypes.html#man-wcstoimax"><code>wcstoimax()</code></a></td>
<td>Convert wide strings to type <code>intmax_t</code></td>
</tr>
<tr class="even">
<td><a href="inttypes.html#man-wcstoimax"><code>wcstoumax()</code></a></td>
<td>Convert wide strings to type <code>uintmax_t</code></td>
</tr>
</tbody>
</table>
<p>This header does conversions to maximum sized integers, division with
maximum sized integers, and also provides format specifiers for <a href="#man-printf"><code>printf()</code></a> and <a href="#man-scanf"><code>scanf()</code></a> for a variety of types
defined in <a href="stdint.html"><code>&lt;stdint.h&gt;</code></a>.</p>
<p>The header <a href="stdint.html"><code>&lt;stdint.h&gt;</code></a> is
included by this one.</p>
<h2 data-number="48.1" id="macros-1"><span class="header-section-number">48.1</span> Macros</h2>
<p>These are to help with <a href="#man-printf"><code>printf()</code></a> and <a href="#man-scanf"><code>scanf()</code></a> when you use a type such as
<code>int_least16_t</code>… what format specifiers do you use?</p>
<p>Let’s start with <code>printf()</code>—all these macros start with
<code>PRI</code> and then are followed by the format specifier you’d
typically use for that type. Lastly, the number of bits is added on.</p>
<p>For example, the format specifier for a 64-bit integer is
<code>PRId64</code>—the <code>d</code> is because you usually print
integers with <code>"%d"</code>.</p>
<p>An unsigned 16-bit integer could be printed with
<code>PRIu16</code>.</p>
<p>These macros expand to string literals. We can take advantage of the
fact that C automatically concatenates neighboring string literals and
use these specifiers like this:</p>
<div class="sourceCode" id="cb942"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb942-1"><a href="inttypes.html#cb942-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">     </span><span class="co">// for printf()</span></span>
<span id="cb942-2"><a href="inttypes.html#cb942-2"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb942-3"><a href="inttypes.html#cb942-3"></a></span>
<span id="cb942-4"><a href="inttypes.html#cb942-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb942-5"><a href="inttypes.html#cb942-5"></a><span class="op">{</span></span>
<span id="cb942-6"><a href="inttypes.html#cb942-6"></a>    <span class="dt">int16_t</span> x <span class="op">=</span> <span class="dv">32</span><span class="op">;</span></span>
<span id="cb942-7"><a href="inttypes.html#cb942-7"></a></span>
<span id="cb942-8"><a href="inttypes.html#cb942-8"></a>    printf<span class="op">(</span><span class="st">"The value is %"</span> PRId16 <span class="st">"!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb942-9"><a href="inttypes.html#cb942-9"></a><span class="op">}</span></span></code></pre></div>
<p>There’s nothing magical happening on line 8, above. Indeed, if I
print out the value of the macro:</p>
<div class="sourceCode" id="cb943"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb943-1"><a href="inttypes.html#cb943-1" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> PRId16<span class="op">);</span></span></code></pre></div>
<p>we get this on my system:</p>
<div class="sourceCode" id="cb944"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb944-1"><a href="inttypes.html#cb944-1" aria-hidden="true" tabindex="-1"></a>hd</span></code></pre></div>
<p>which is a <code>printf()</code> format specifier meaning “short
signed integer” .</p>
<p>So back to line 8, after string literal concatenation, it’s just as
if I’d typed:</p>
<div class="sourceCode" id="cb945" data-startfrom="8"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c" style="counter-reset: source-line 7;"><span id="cb945-8"><a href="inttypes.html#cb945-8"></a>    printf<span class="op">(</span><span class="st">"The value is %hd!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span></code></pre></div>
<p>Here’s a table of all the macros you can use for
<code>printf()</code> format specifiers… substitute the number of bits
for <em>N</em>, usually 8, 16, 32, or 64.</p>
<table>
<tbody>
<tr class="odd">
<td><code>PRId</code><em>N</em></td>
<td><code>PRIdLEAST</code><em>N</em></td>
<td><code>PRIdFAST</code><em>N</em></td>
<td><code>PRIdMAX</code></td>
<td><code>PRIdPTR</code></td>
</tr>
<tr class="even">
<td><code>PRIi</code><em>N</em></td>
<td><code>PRIiLEAST</code><em>N</em></td>
<td><code>PRIiFAST</code><em>N</em></td>
<td><code>PRIiMAX</code></td>
<td><code>PRIiPTR</code></td>
</tr>
<tr class="odd">
<td><code>PRIo</code><em>N</em></td>
<td><code>PRIoLEAST</code><em>N</em></td>
<td><code>PRIoFAST</code><em>N</em></td>
<td><code>PRIoMAX</code></td>
<td><code>PRIoPTR</code></td>
</tr>
<tr class="even">
<td><code>PRIu</code><em>N</em></td>
<td><code>PRIuLEAST</code><em>N</em></td>
<td><code>PRIuFAST</code><em>N</em></td>
<td><code>PRIuMAX</code></td>
<td><code>PRIuPTR</code></td>
</tr>
<tr class="odd">
<td><code>PRIx</code><em>N</em></td>
<td><code>PRIxLEAST</code><em>N</em></td>
<td><code>PRIxFAST</code><em>N</em></td>
<td><code>PRIxMAX</code></td>
<td><code>PRIxPTR</code></td>
</tr>
<tr class="even">
<td><code>PRIX</code><em>N</em></td>
<td><code>PRIXLEAST</code><em>N</em></td>
<td><code>PRIXFAST</code><em>N</em></td>
<td><code>PRIXMAX</code></td>
<td><code>PRIXPTR</code></td>
</tr>
</tbody>
</table>
<p>Note again how the lowercase center letter represents the usual
format specifiers you’d pass to <code>printf()</code>: <code>d</code>,
<code>i</code>, <code>o</code>, <code>u</code>, <code>x</code>, and
<code>X</code>.</p>
<p>And we have a similar set of macros for <code>scanf()</code> for
reading in these various types:</p>
<table>
<tbody>
<tr class="odd">
<td><code>SCNd</code><em>N</em></td>
<td><code>SCNdLEAST</code><em>N</em></td>
<td><code>SCNdFAST</code><em>N</em></td>
<td><code>SCNdMAX</code></td>
<td><code>SCNdPTR</code></td>
</tr>
<tr class="even">
<td><code>SCNi</code><em>N</em></td>
<td><code>SCNiLEAST</code><em>N</em></td>
<td><code>SCNiFAST</code><em>N</em></td>
<td><code>SCNiMAX</code></td>
<td><code>SCNiPTR</code></td>
</tr>
<tr class="odd">
<td><code>SCNo</code><em>N</em></td>
<td><code>SCNoLEAST</code><em>N</em></td>
<td><code>SCNoFAST</code><em>N</em></td>
<td><code>SCNoMAX</code></td>
<td><code>SCNoPTR</code></td>
</tr>
<tr class="even">
<td><code>SCNu</code><em>N</em></td>
<td><code>SCNuLEAST</code><em>N</em></td>
<td><code>SCNuFAST</code><em>N</em></td>
<td><code>SCNuMAX</code></td>
<td><code>SCNuPTR</code></td>
</tr>
<tr class="odd">
<td><code>SCNx</code><em>N</em></td>
<td><code>SCNxLEAST</code><em>N</em></td>
<td><code>SCNxFAST</code><em>N</em></td>
<td><code>SCNxMAX</code></td>
<td><code>SCNxPTR</code></td>
</tr>
</tbody>
</table>
<p>The rule is that for each type defined in
<code>&lt;stdint.h&gt;</code> there will be corresponding
<code>printf()</code> and <code>scanf()</code> macros defined here.</p>
<hr>
<h2 data-number="48.2" id="man-imaxabs"><span class="header-section-number">48.2</span> <code>imaxabs()</code></h2>
<p>Compute the absolute value of an <code>intmax_t</code></p>
<h3 class="unnumbered unlisted" id="synopsis-48">Synopsis</h3>
<div class="sourceCode" id="cb946"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb946-1"><a href="inttypes.html#cb946-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb946-2"><a href="inttypes.html#cb946-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb946-3"><a href="inttypes.html#cb946-3" aria-hidden="true" tabindex="-1"></a><span class="dt">intmax_t</span> imaxabs<span class="op">(</span><span class="dt">intmax_t</span> j<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-48">Description</h3>
<p>When you need the absolute value of the biggest integer type on the
system, this is the function for you.</p>
<p>The spec notes that if the absolute value of the number cannot be
represented, the behavior is undefined. This would happen if you tried
to take the absolute value of the smallest possible negative number in a
two’s-complement system.</p>
<h3 class="unnumbered unlisted" id="return-value-47">Return Value</h3>
<p>Returns the absolute value of the input, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>j</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-48">Example</h3>
<div class="sourceCode" id="cb947"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb947-1"><a href="inttypes.html#cb947-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb947-2"><a href="inttypes.html#cb947-2"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb947-3"><a href="inttypes.html#cb947-3"></a></span>
<span id="cb947-4"><a href="inttypes.html#cb947-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb947-5"><a href="inttypes.html#cb947-5"></a><span class="op">{</span></span>
<span id="cb947-6"><a href="inttypes.html#cb947-6"></a>    <span class="dt">intmax_t</span> j <span class="op">=</span> <span class="op">-</span><span class="dv">3490</span><span class="op">;</span></span>
<span id="cb947-7"><a href="inttypes.html#cb947-7"></a></span>
<span id="cb947-8"><a href="inttypes.html#cb947-8"></a>    printf<span class="op">(</span><span class="st">"%jd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> imaxabs<span class="op">(</span>j<span class="op">));</span>    <span class="co">// 3490</span></span>
<span id="cb947-9"><a href="inttypes.html#cb947-9"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-44">See Also</h3>
<p><a href="math.html#man-fabs"><code>fabs()</code></a></p>
<hr>
<h2 data-number="48.3" id="man-imaxdiv"><span class="header-section-number">48.3</span> <code>imaxdiv()</code></h2>
<p>Compute the quotient and remainder of <code>intmax_t</code>s</p>
<h3 class="unnumbered unlisted" id="synopsis-49">Synopsis</h3>
<div class="sourceCode" id="cb948"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb948-1"><a href="inttypes.html#cb948-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb948-2"><a href="inttypes.html#cb948-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb948-3"><a href="inttypes.html#cb948-3" aria-hidden="true" tabindex="-1"></a>imaxdiv_t imaxdiv<span class="op">(</span><span class="dt">intmax_t</span> numer<span class="op">,</span> <span class="dt">intmax_t</span> denom<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-49">Description</h3>
<p>When you want to do integer division and remainder in a single
operation, this function will do it for you.</p>
<p>It computes <code>numer/denom</code> and <code>numer%denom</code> and
returns the result in a structure of type <code>imaxdiv_t</code>.</p>
<p>This structure has two <code>imaxdiv_t</code> fields,
<code>quot</code> and <code>rem</code>, that you use to retrieve the
sought-after values.</p>
<h3 class="unnumbered unlisted" id="return-value-48">Return Value</h3>
<p>Returns an <code>imaxdiv_t</code> containing the quotient and
remainder of the operation.</p>
<h3 class="unnumbered unlisted" id="example-49">Example</h3>
<div class="sourceCode" id="cb949"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb949-1"><a href="inttypes.html#cb949-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb949-2"><a href="inttypes.html#cb949-2"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb949-3"><a href="inttypes.html#cb949-3"></a></span>
<span id="cb949-4"><a href="inttypes.html#cb949-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb949-5"><a href="inttypes.html#cb949-5"></a><span class="op">{</span></span>
<span id="cb949-6"><a href="inttypes.html#cb949-6"></a>    <span class="dt">intmax_t</span> numer <span class="op">=</span> INTMAX_C<span class="op">(</span><span class="dv">3490</span><span class="op">);</span></span>
<span id="cb949-7"><a href="inttypes.html#cb949-7"></a>    <span class="dt">intmax_t</span> denom <span class="op">=</span> INTMAX_C<span class="op">(</span><span class="dv">17</span><span class="op">);</span></span>
<span id="cb949-8"><a href="inttypes.html#cb949-8"></a></span>
<span id="cb949-9"><a href="inttypes.html#cb949-9"></a>    imaxdiv_t r <span class="op">=</span> imaxdiv<span class="op">(</span>numer<span class="op">,</span> denom<span class="op">);</span></span>
<span id="cb949-10"><a href="inttypes.html#cb949-10"></a></span>
<span id="cb949-11"><a href="inttypes.html#cb949-11"></a>    printf<span class="op">(</span><span class="st">"Quotient: %jd, remainder: %jd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">.</span>quot<span class="op">,</span> r<span class="op">.</span>rem<span class="op">);</span></span>
<span id="cb949-12"><a href="inttypes.html#cb949-12"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb950"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb950-1"><a href="inttypes.html#cb950-1" aria-hidden="true" tabindex="-1"></a>Quotient: 205, remainder: 5</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-45">See Also</h3>
<p><a href="math.html#man-remquo"><code>remquo()</code></a></p>
<hr>
<h2 data-number="48.4" id="man-strtoimax"><span class="header-section-number">48.4</span> <code>strtoimax()</code>
<code>strtoumax()</code></h2>
<p>Convert strings to types <code>intmax_t</code> and
<code>uintmax_t</code></p>
<h3 class="unnumbered unlisted" id="synopsis-50">Synopsis</h3>
<div class="sourceCode" id="cb951"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb951-1"><a href="inttypes.html#cb951-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb951-2"><a href="inttypes.html#cb951-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb951-3"><a href="inttypes.html#cb951-3" aria-hidden="true" tabindex="-1"></a><span class="dt">intmax_t</span> strtoimax<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span></span>
<span id="cb951-4"><a href="inttypes.html#cb951-4" aria-hidden="true" tabindex="-1"></a>                   <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb951-5"><a href="inttypes.html#cb951-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb951-6"><a href="inttypes.html#cb951-6" aria-hidden="true" tabindex="-1"></a><span class="dt">uintmax_t</span> strtoumax<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span></span>
<span id="cb951-7"><a href="inttypes.html#cb951-7" aria-hidden="true" tabindex="-1"></a>                   <span class="dt">int</span> base<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-50">Description</h3>
<p>These work just like the <a href="#man-strtol"><code>strtol()</code></a> family of functions, except
they return an <code>intmax_t</code> or <code>uintmax_t</code>.</p>
<p>See the <a href="stdlib.html#man-strtol"><code>strtol()</code></a> reference
page for details.</p>
<h3 class="unnumbered unlisted" id="return-value-49">Return Value</h3>
<p>Returns the converted string as an <code>intmax_t</code> or
<code>uintmax_t</code>.</p>
<p>If the result is out of range, the returned value will be
<code>INTMAX_MAX</code>, <code>INTMAX_MIN</code>, or
<code>UINTMAX_MAX</code>, as appropriate. And the <code>errno</code>
variable will be set to <code>ERANGE</code>.</p>
<h3 class="unnumbered unlisted" id="example-50">Example</h3>
<p>The following example converts a base-10 number to an
<code>intmax_t</code>. Then it attempts to convert an invalid base-2
number, catching the error.</p>
<div class="sourceCode" id="cb952"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb952-1"><a href="inttypes.html#cb952-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb952-2"><a href="inttypes.html#cb952-2"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb952-3"><a href="inttypes.html#cb952-3"></a></span>
<span id="cb952-4"><a href="inttypes.html#cb952-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb952-5"><a href="inttypes.html#cb952-5"></a><span class="op">{</span></span>
<span id="cb952-6"><a href="inttypes.html#cb952-6"></a>    <span class="dt">intmax_t</span> r<span class="op">;</span></span>
<span id="cb952-7"><a href="inttypes.html#cb952-7"></a>    <span class="dt">char</span> <span class="op">*</span>endptr<span class="op">;</span></span>
<span id="cb952-8"><a href="inttypes.html#cb952-8"></a></span>
<span id="cb952-9"><a href="inttypes.html#cb952-9"></a>    <span class="co">// Valid base-10 number</span></span>
<span id="cb952-10"><a href="inttypes.html#cb952-10"></a>    r <span class="op">=</span> strtoimax<span class="op">(</span><span class="st">"123456789012345"</span><span class="op">,</span> <span class="op">&amp;</span>endptr<span class="op">,</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb952-11"><a href="inttypes.html#cb952-11"></a></span>
<span id="cb952-12"><a href="inttypes.html#cb952-12"></a>    <span class="cf">if</span> <span class="op">(*</span>endptr <span class="op">!=</span> <span class="ch">'\0'</span><span class="op">)</span></span>
<span id="cb952-13"><a href="inttypes.html#cb952-13"></a>        printf<span class="op">(</span><span class="st">"Invalid digit: %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">*</span>endptr<span class="op">);</span></span>
<span id="cb952-14"><a href="inttypes.html#cb952-14"></a>    <span class="cf">else</span></span>
<span id="cb952-15"><a href="inttypes.html#cb952-15"></a>        printf<span class="op">(</span><span class="st">"Value is %jd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span></span>
<span id="cb952-16"><a href="inttypes.html#cb952-16"></a>    </span>
<span id="cb952-17"><a href="inttypes.html#cb952-17"></a>    <span class="co">// The following binary number contains an invalid digit</span></span>
<span id="cb952-18"><a href="inttypes.html#cb952-18"></a>    r <span class="op">=</span> strtoimax<span class="op">(</span><span class="st">"0100102010101101"</span><span class="op">,</span> <span class="op">&amp;</span>endptr<span class="op">,</span> <span class="dv">2</span><span class="op">);</span></span>
<span id="cb952-19"><a href="inttypes.html#cb952-19"></a></span>
<span id="cb952-20"><a href="inttypes.html#cb952-20"></a>    <span class="cf">if</span> <span class="op">(*</span>endptr <span class="op">!=</span> <span class="ch">'\0'</span><span class="op">)</span></span>
<span id="cb952-21"><a href="inttypes.html#cb952-21"></a>        printf<span class="op">(</span><span class="st">"Invalid digit: %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">*</span>endptr<span class="op">);</span></span>
<span id="cb952-22"><a href="inttypes.html#cb952-22"></a>    <span class="cf">else</span></span>
<span id="cb952-23"><a href="inttypes.html#cb952-23"></a>        printf<span class="op">(</span><span class="st">"Value is %jd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span></span>
<span id="cb952-24"><a href="inttypes.html#cb952-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb953"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb953-1"><a href="inttypes.html#cb953-1" aria-hidden="true" tabindex="-1"></a>Value is 123456789012345</span>
<span id="cb953-2"><a href="inttypes.html#cb953-2" aria-hidden="true" tabindex="-1"></a>Invalid digit: 2</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-46">See Also</h3>
<p><a href="stdlib.html#man-strtol"><code>strtol()</code></a>, <a href="#errno"><code>errno</code></a></p>
<hr>
<h2 data-number="48.5" id="man-wcstoimax"><span class="header-section-number">48.5</span> <code>wcstoimax()</code>
<code>wcstoumax()</code></h2>
<p>Convert wide strings to types <code>intmax_t</code> and
<code>uintmax_t</code></p>
<h3 class="unnumbered unlisted" id="synopsis-51">Synopsis</h3>
<div class="sourceCode" id="cb954"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb954-1"><a href="inttypes.html#cb954-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span><span class="pp"> </span><span class="co">// for wchar_t</span></span>
<span id="cb954-2"><a href="inttypes.html#cb954-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb954-3"><a href="inttypes.html#cb954-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb954-4"><a href="inttypes.html#cb954-4" aria-hidden="true" tabindex="-1"></a><span class="dt">intmax_t</span> wcstoimax<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb954-5"><a href="inttypes.html#cb954-5" aria-hidden="true" tabindex="-1"></a>                   <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb954-6"><a href="inttypes.html#cb954-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb954-7"><a href="inttypes.html#cb954-7" aria-hidden="true" tabindex="-1"></a><span class="dt">uintmax_t</span> wcstoumax<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb954-8"><a href="inttypes.html#cb954-8" aria-hidden="true" tabindex="-1"></a>                    <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-51">Description</h3>
<p>These work just like the <a href="#man-wcstol"><code>wcstol()</code></a> family of functions, except
they return an <code>intmax_t</code> or <code>uintmax_t</code>.</p>
<p>See the <a href="wchar.html#man-wcstol"><code>wcstol()</code></a> reference
page for details.</p>
<h3 class="unnumbered unlisted" id="return-value-50">Return Value</h3>
<p>Returns the converted wide string as an <code>intmax_t</code> or
<code>uintmax_t</code>.</p>
<p>If the result is out of range, the returned value will be
<code>INTMAX_MAX</code>, <code>INTMAX_MIN</code>, or
<code>UINTMAX_MAX</code>, as appropriate. And the <code>errno</code>
variable will be set to <code>ERANGE</code>.</p>
<h3 class="unnumbered unlisted" id="example-51">Example</h3>
<p>The following example converts a base-10 number to an
<code>intmax_t</code>. Then it attempts to convert an invalid base-2
number, catching the error.</p>
<div class="sourceCode" id="cb955"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb955-1"><a href="inttypes.html#cb955-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb955-2"><a href="inttypes.html#cb955-2"></a><span class="pp">#include </span><span class="im">&lt;inttypes.h&gt;</span></span>
<span id="cb955-3"><a href="inttypes.html#cb955-3"></a></span>
<span id="cb955-4"><a href="inttypes.html#cb955-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb955-5"><a href="inttypes.html#cb955-5"></a><span class="op">{</span></span>
<span id="cb955-6"><a href="inttypes.html#cb955-6"></a>    <span class="dt">intmax_t</span> r<span class="op">;</span></span>
<span id="cb955-7"><a href="inttypes.html#cb955-7"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>endptr<span class="op">;</span></span>
<span id="cb955-8"><a href="inttypes.html#cb955-8"></a></span>
<span id="cb955-9"><a href="inttypes.html#cb955-9"></a>    <span class="co">// Valid base-10 number</span></span>
<span id="cb955-10"><a href="inttypes.html#cb955-10"></a>    r <span class="op">=</span> wcstoimax<span class="op">(</span>L<span class="st">"123456789012345"</span><span class="op">,</span> <span class="op">&amp;</span>endptr<span class="op">,</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb955-11"><a href="inttypes.html#cb955-11"></a></span>
<span id="cb955-12"><a href="inttypes.html#cb955-12"></a>    <span class="cf">if</span> <span class="op">(*</span>endptr <span class="op">!=</span> <span class="ch">'\0'</span><span class="op">)</span></span>
<span id="cb955-13"><a href="inttypes.html#cb955-13"></a>        wprintf<span class="op">(</span>L<span class="st">"Invalid digit: %lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">*</span>endptr<span class="op">);</span></span>
<span id="cb955-14"><a href="inttypes.html#cb955-14"></a>    <span class="cf">else</span></span>
<span id="cb955-15"><a href="inttypes.html#cb955-15"></a>        wprintf<span class="op">(</span>L<span class="st">"Value is %jd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span></span>
<span id="cb955-16"><a href="inttypes.html#cb955-16"></a>    </span>
<span id="cb955-17"><a href="inttypes.html#cb955-17"></a>    <span class="co">// The following binary number contains an invalid digit</span></span>
<span id="cb955-18"><a href="inttypes.html#cb955-18"></a>    r <span class="op">=</span> wcstoimax<span class="op">(</span>L<span class="st">"0100102010101101"</span><span class="op">,</span> <span class="op">&amp;</span>endptr<span class="op">,</span> <span class="dv">2</span><span class="op">);</span></span>
<span id="cb955-19"><a href="inttypes.html#cb955-19"></a></span>
<span id="cb955-20"><a href="inttypes.html#cb955-20"></a>    <span class="cf">if</span> <span class="op">(*</span>endptr <span class="op">!=</span> <span class="ch">'\0'</span><span class="op">)</span></span>
<span id="cb955-21"><a href="inttypes.html#cb955-21"></a>        wprintf<span class="op">(</span>L<span class="st">"Invalid digit: %lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">*</span>endptr<span class="op">);</span></span>
<span id="cb955-22"><a href="inttypes.html#cb955-22"></a>    <span class="cf">else</span></span>
<span id="cb955-23"><a href="inttypes.html#cb955-23"></a>        wprintf<span class="op">(</span>L<span class="st">"Value is %jd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span></span>
<span id="cb955-24"><a href="inttypes.html#cb955-24"></a><span class="op">}</span></span></code></pre></div>
<div class="sourceCode" id="cb956"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb956-1"><a href="inttypes.html#cb956-1" aria-hidden="true" tabindex="-1"></a>Value is 123456789012345</span>
<span id="cb956-2"><a href="inttypes.html#cb956-2" aria-hidden="true" tabindex="-1"></a>Invalid digit: 2</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-47">See Also</h3>
<p><a href="wchar.html#man-wcstol"><code>wcstol()</code></a>, <a href="#errno"><code>errno</code></a></p>

</body>