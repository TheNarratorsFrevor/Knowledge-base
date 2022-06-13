<body>

<hr>
<h1 data-number="62" id="stdlib"><span class="header-section-number">62</span> <code>&lt;stdlib.h&gt;</code>
Standard Library Functions</h1>
<p>Some of the following functions have variants that handle different
types: <code>atoi()</code>, <code>strtod()</code>,
<code>strtol()</code>, <code>abs()</code>, and <code>div()</code>. Only
a single one is listed here for brevity.</p>
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
<td><a href="stdlib.html#man-exit"><code>_Exit()</code></a></td>
<td>Exit the currently-running program and don’t look back</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-abort"><code>abort()</code></a></td>
<td>Abruptly end program execution</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-abs"><code>abs()</code></a></td>
<td>Compute the absolute value of an integer</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-aligned_alloc"><code>aligned_alloc()</code></a></td>
<td>Allocate specifically-aligned memory</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-atexit"><code>at_quick_exit()</code></a></td>
<td>Set up handlers to run when the program quickly exits</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-atexit"><code>atexit()</code></a></td>
<td>Set up handlers to run when the program exits</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-atof"><code>atof()</code></a></td>
<td>Convert a string to a floating point value</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-atoi"><code>atoi()</code></a></td>
<td>Convert an integer in a string into a integer type</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-bsearch"><code>bsearch()</code></a></td>
<td>Binary Search (maybe) an array of objects</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-malloc"><code>calloc()</code></a></td>
<td>Allocate and clear memory for arbitrary use</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-div"><code>div()</code></a></td>
<td>Compute the quotient and remainder of two numbers</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-exit"><code>exit()</code></a></td>
<td>Exit the currently-running program</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-free"><code>free()</code></a></td>
<td>Free a memory region</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-getenv"><code>getenv()</code></a></td>
<td>Get the value of an environment variable</td>
</tr>
<tr class="odd">
<td><a href="man-malloc"><code>malloc()</code></a></td>
<td>Allocate memory for arbitrary use</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-mblen"><code>mblen()</code></a></td>
<td>Return the number of bytes in a multibyte character</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-mbstowcs"><code>mbstowcs()</code></a></td>
<td>Convert a multibyte string to a wide character string</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-mbtowc"><code>mbtowc()</code></a></td>
<td>Convert a multibyte character to a wide character</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-qsort"><code>qsort()</code></a></td>
<td>Quicksort (maybe) some data</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-exit"><code>quick_exit()</code></a></td>
<td>Exit the currently-running program quickly</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-rand"><code>rand()</code></a></td>
<td>Return a pseudorandom number</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-realloc"><code>realloc()</code></a></td>
<td>Resize a previously allocated stretch of memory</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-srand"><code>srand()</code></a></td>
<td>Seed the built-in pseudorandom number generator</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-strtod"><code>strtod()</code></a></td>
<td>Convert a string to a floating point number</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-strtol"><code>strtol()</code></a></td>
<td>Convert a string to an integer</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-system"><code>system()</code></a></td>
<td>Run an external program</td>
</tr>
<tr class="odd">
<td><a href="stdlib.html#man-wcstombs"><code>wcstombs()</code></a></td>
<td>Convert a wide character string to a multibyte string</td>
</tr>
<tr class="even">
<td><a href="stdlib.html#man-wctomb"><code>wctomb()</code></a></td>
<td>Convert a wide character to a multibyte character</td>
</tr>
</tbody>
</table>
<p>The <code>&lt;stdlib.h&gt;</code> header has all kinds of—dare I
say—miscellaneous functions bundled into it. This functionality
includes:</p>
<ul>
<li>Conversions from numbers to strings</li>
<li>Conversions from strings to numbers</li>
<li>Pseudorandom number generation</li>
<li>Dynamic memory allocation</li>
<li>Various ways to exit the program</li>
<li>Ability to run external programs</li>
<li>Binary search (or some fast search)</li>
<li>Quicksort (or some fast sort)</li>
<li>Integer arithmetic functions</li>
<li>Multibyte and wide character and string conversions</li>
</ul>
<p>So, you know… a little of everything.</p>
<h2 data-number="62.1" id="stdlib.h-types-and-macros"><span class="header-section-number">62.1</span> <code>&lt;stdlib.h&gt;</code>
Types and Macros</h2>
<p>A couple new types and macros are introduced, though some of these
might also be defined elsewhere:</p>
<table>
<thead>
<tr class="header">
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>size_t</code></td>
<td>Returned from <code>sizeof</code> and used elsewhere</td>
</tr>
<tr class="even">
<td><code>wchar_t</code></td>
<td>For wide character operations</td>
</tr>
<tr class="odd">
<td><code>div_t</code></td>
<td>For the <code>div()</code> function</td>
</tr>
<tr class="even">
<td><code>ldiv_t</code></td>
<td>For the <code>ldiv()</code> function</td>
</tr>
<tr class="odd">
<td><code>lldiv_t</code></td>
<td>for the <code>lldiv()</code> function</td>
</tr>
</tbody>
</table>
<p>And some macros:</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>NULL</code></td>
<td>Our good pointer friend</td>
</tr>
<tr class="even">
<td><code>EXIT_SUCCESS</code></td>
<td>Good exit status when things go well</td>
</tr>
<tr class="odd">
<td><code>EXIT_FAILURE</code></td>
<td>Good exit status when things go poorly</td>
</tr>
<tr class="even">
<td><code>RAND_MAX</code></td>
<td>The maximum value that can be returned by the <code>rand()</code>
function</td>
</tr>
<tr class="odd">
<td><code>MB_CUR_MAX</code></td>
<td>Maximum number of bytes in a multibyte character in the current
locale</td>
</tr>
</tbody>
</table>
<p>And there you have it. Just a lot of fun, useful functions in here.
Let’s check ’em out!</p>
<hr>
<h2 data-number="62.2" id="man-atof"><span class="header-section-number">62.2</span> <code>atof()</code></h2>
<p>Convert a string to a floating point value</p>
<h3 class="unnumbered unlisted" id="synopsis-160">Synopsis</h3>
<div class="sourceCode" id="cb1300"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1300-1"><a href="stdlib.html#cb1300-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1300-2"><a href="stdlib.html#cb1300-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1300-3"><a href="stdlib.html#cb1300-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> atof<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>nptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-160">Description</h3>
<p>This stood for <a href="http://man.cat-v.org/unix-1st/3/atof">“ASCII-To-Floating” back in
the day</a><a href="footnotes.html#fn257" class="footnote-ref" id="fnref257" role="doc-noteref"><sup>257</sup></a>, but no one would dare to use such
coarse language now.</p>
<p>But the gist is the same: we’re going to convert a string with
numbers and (optionally) a decimal point into a floating point value.
Leading whitespace is ignored, and translation stops at the first
invalid character.</p>
<p>If the result doesn’t fit in a <code>double</code>, behavior is
undefined.</p>
<p>It generally works as if you’d called <a href="#man-strtod"><code>strtod()</code></a>:</p>
<div class="sourceCode" id="cb1301"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1301-1"><a href="stdlib.html#cb1301-1" aria-hidden="true" tabindex="-1"></a>strtod<span class="op">(</span>nptr<span class="op">,</span> NULL<span class="op">)</span></span></code></pre></div>
<p>So check out <a href="stdlib.html#man-strtod">that reference page</a> for more
info.</p>
<p>In fact, <code>strtod()</code> is just better and you should probably
use that.</p>
<h3 class="unnumbered unlisted" id="return-value-158">Return Value</h3>
<p>Returns the string converted to a <code>double</code>.</p>
<h3 class="unnumbered unlisted" id="example-161">Example</h3>
<div class="sourceCode" id="cb1302"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1302-1"><a href="stdlib.html#cb1302-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1302-2"><a href="stdlib.html#cb1302-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1302-3"><a href="stdlib.html#cb1302-3"></a></span>
<span id="cb1302-4"><a href="stdlib.html#cb1302-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1302-5"><a href="stdlib.html#cb1302-5"></a><span class="op">{</span></span>
<span id="cb1302-6"><a href="stdlib.html#cb1302-6"></a>    <span class="dt">double</span> x <span class="op">=</span> atof<span class="op">(</span><span class="st">"3.141593"</span><span class="op">);</span></span>
<span id="cb1302-7"><a href="stdlib.html#cb1302-7"></a></span>
<span id="cb1302-8"><a href="stdlib.html#cb1302-8"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span>  <span class="co">// 3.141593</span></span>
<span id="cb1302-9"><a href="stdlib.html#cb1302-9"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-152">See Also</h3>
<p><a href="stdlib.html#man-atoi"><code>atoi()</code></a>, <a href="#man-strtod"><code>strtod()</code></a></p>
<hr>
<h2 data-number="62.3" id="man-atoi"><span class="header-section-number">62.3</span> <code>atoi()</code>,
<code>atol()</code>, <code>atoll()</code></h2>
<p>Convert an integer in a string into a integer type</p>
<h3 class="unnumbered unlisted" id="synopsis-161">Synopsis</h3>
<div class="sourceCode" id="cb1303"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1303-1"><a href="stdlib.html#cb1303-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1303-2"><a href="stdlib.html#cb1303-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1303-3"><a href="stdlib.html#cb1303-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> atoi<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>nptr<span class="op">);</span></span>
<span id="cb1303-4"><a href="stdlib.html#cb1303-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1303-5"><a href="stdlib.html#cb1303-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> atol<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>nptr<span class="op">);</span></span>
<span id="cb1303-6"><a href="stdlib.html#cb1303-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1303-7"><a href="stdlib.html#cb1303-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> atoll<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>nptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-161">Description</h3>
<p>Back in the day, <code>atoi()</code> stood for <a href="http://man.cat-v.org/unix-1st/3/atoi">“ASCII-To_Integer”</a><a href="#fn258" class="footnote-ref" id="fnref258" role="doc-noteref"><sup>258</sup></a> but now the spec makes no mention
of that.</p>
<p>These functions take a string with a number in them and convert it to
an integer of the specified return type. Leading whitespace is ignored.
Translation stops at the first invalid character.</p>
<p>If the result doesn’t fit in the return type, behavior is
undefined.</p>
<p>It generally works as if you’d called <a href="#man-strtol"><code>strtol()</code></a> family of functions:</p>
<div class="sourceCode" id="cb1304"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1304-1"><a href="stdlib.html#cb1304-1" aria-hidden="true" tabindex="-1"></a>atoi<span class="op">(</span>nptr<span class="op">)</span>                 <span class="co">// is basically the same as...</span></span>
<span id="cb1304-2"><a href="stdlib.html#cb1304-2" aria-hidden="true" tabindex="-1"></a><span class="op">(</span><span class="dt">int</span><span class="op">)</span>strtol<span class="op">(</span>nptr<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">10</span><span class="op">)</span></span>
<span id="cb1304-3"><a href="stdlib.html#cb1304-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1304-4"><a href="stdlib.html#cb1304-4" aria-hidden="true" tabindex="-1"></a>atol<span class="op">(</span>nptr<span class="op">)</span>                 <span class="co">// is basically the same as...</span></span>
<span id="cb1304-5"><a href="stdlib.html#cb1304-5" aria-hidden="true" tabindex="-1"></a>strtol<span class="op">(</span>nptr<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">10</span><span class="op">)</span></span>
<span id="cb1304-6"><a href="stdlib.html#cb1304-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1304-7"><a href="stdlib.html#cb1304-7" aria-hidden="true" tabindex="-1"></a>atoll<span class="op">(</span>nptr<span class="op">)</span>                <span class="co">// is basically the same as...</span></span>
<span id="cb1304-8"><a href="stdlib.html#cb1304-8" aria-hidden="true" tabindex="-1"></a>strtoll<span class="op">(</span>nptr<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">10</span><span class="op">)</span></span></code></pre></div>
<p>Again, the <a href="stdlib.html#man-strtol"><code>strtol()</code></a> functions
are generally better, so I recommend them instead of these.</p>
<h3 class="unnumbered unlisted" id="return-value-159">Return Value</h3>
<p>Returns an integer result corresponding to the return type.</p>
<h3 class="unnumbered unlisted" id="example-162">Example</h3>
<div class="sourceCode" id="cb1305"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1305-1"><a href="stdlib.html#cb1305-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1305-2"><a href="stdlib.html#cb1305-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1305-3"><a href="stdlib.html#cb1305-3"></a></span>
<span id="cb1305-4"><a href="stdlib.html#cb1305-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1305-5"><a href="stdlib.html#cb1305-5"></a><span class="op">{</span></span>
<span id="cb1305-6"><a href="stdlib.html#cb1305-6"></a>    <span class="dt">int</span> x <span class="op">=</span> atoi<span class="op">(</span><span class="st">"3490"</span><span class="op">);</span></span>
<span id="cb1305-7"><a href="stdlib.html#cb1305-7"></a></span>
<span id="cb1305-8"><a href="stdlib.html#cb1305-8"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span>  <span class="co">// 3490</span></span>
<span id="cb1305-9"><a href="stdlib.html#cb1305-9"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-153">See Also</h3>
<p><a href="stdlib.html#man-atof"><code>atof()</code></a>, <a href="#man-strtol"><code>strtol()</code></a></p>
<hr>
<h2 data-number="62.4" id="man-strtod"><span class="header-section-number">62.4</span> <code>strtod()</code>,
<code>strtof()</code>, <code>strtold()</code></h2>
<p>Convert a string to a floating point number</p>
<h3 class="unnumbered unlisted" id="synopsis-162">Synopsis</h3>
<div class="sourceCode" id="cb1306"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1306-1"><a href="stdlib.html#cb1306-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1306-2"><a href="stdlib.html#cb1306-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1306-3"><a href="stdlib.html#cb1306-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> strtod<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">);</span></span>
<span id="cb1306-4"><a href="stdlib.html#cb1306-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1306-5"><a href="stdlib.html#cb1306-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> strtof<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">);</span></span>
<span id="cb1306-6"><a href="stdlib.html#cb1306-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1306-7"><a href="stdlib.html#cb1306-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> strtold<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-162">Description</h3>
<p>These are some neat functions that convert strings to floating point
numbers (or even NaN or Infinity) and provide some error checking,
besides.</p>
<p>Firstly, leading whitespace is skipped.</p>
<p>Then the functions attempt to convert characters into the floating
point result. Finally, when an invalid character (or NUL character) is
reached, they set <code>endptr</code> to point to the invalid
character.</p>
<p>Set <code>endptr</code> to <code>NULL</code> if you don’t care about
where the first invalid character is.</p>
<p>If you didn’t set <code>endptr</code> to <code>NULL</code>, it will
point to a NUL character if the translation didn’t find any bad
characters. That is:</p>
<div class="sourceCode" id="cb1307"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1307-1"><a href="stdlib.html#cb1307-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(*</span>endptr <span class="op">==</span> <span class="ch">'\0'</span><span class="op">)</span> <span class="op">{</span></span>
<span id="cb1307-2"><a href="stdlib.html#cb1307-2" aria-hidden="true" tabindex="-1"></a>    printf<span class="op">(</span><span class="st">"What a perfectly-formed number!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1307-3"><a href="stdlib.html#cb1307-3" aria-hidden="true" tabindex="-1"></a><span class="op">}</span> <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1307-4"><a href="stdlib.html#cb1307-4" aria-hidden="true" tabindex="-1"></a>    printf<span class="op">(</span><span class="st">"I found badness in your number: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> endptr<span class="op">);</span></span>
<span id="cb1307-5"><a href="stdlib.html#cb1307-5" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span></code></pre></div>
<p>But guess what! You can also translate strings into special values,
like NaN and Infinity!</p>
<p>If <code>nptr</code> points to a string containing <code>INF</code>
or <code>INFINITY</code> (upper or lowercase), the value for Infinity
will be returned.</p>
<p>If <code>nptr</code> points to a string containing <code>NAN</code>,
then (a quiet, non-signalling) NaN will be returned. You can tag the
<code>NAN</code> with a sequence of characters from the set
<code>0</code>-<code>9</code>, <code>a</code>-<code>z</code>,
<code>A</code>-<code>Z</code>, and <code>_</code> by enclosing them in
parens:</p>
<div class="sourceCode" id="cb1308"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1308-1"><a href="stdlib.html#cb1308-1" aria-hidden="true" tabindex="-1"></a>NAN<span class="op">(</span>foobar_3490<span class="op">)</span></span></code></pre></div>
<p>What your compiler does with this is implementation-defined, but it
can be used to specify different kinds of NaN.</p>
<p>You can also specify a number in hexadecimal with a power-of-two
exponent (<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mi>x</mi></msup></math></mjx-assistive-mml></mjx-container></span>) if you lead with
<code>0x</code> (or <code>0X</code>). For the exponent, use a
<code>p</code> followed by a base 10 exponent. (You can’t use
<code>e</code> because that’s a valid hex digit!)</p>
<p>Example:</p>
<div class="sourceCode" id="cb1309"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1309-1"><a href="stdlib.html#cb1309-1" aria-hidden="true" tabindex="-1"></a><span class="fl">0xabc.123p15</span></span></code></pre></div>
<p>Which computes to <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D450 TEX-I"></mjx-c></mjx-mi><mjx-mn class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn><mi>x</mi><mi>a</mi><mi>b</mi><mi>c</mi><mn>.123</mn><mo>×</mo><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>15</mn></mrow></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>You can put in <code>FLT_DECIMAL_DIG</code>,
<code>DBL_DECIMAL_DIG</code>, or <code>LDBL_DECIMAL_DIG</code> digits
and get a correctly-rounded result for the type.</p>
<h3 class="unnumbered unlisted" id="return-value-160">Return Value</h3>
<p>Returns the converted number. If there was no number, returns
<code>0</code>. <code>endptr</code> is set to point to the first invalid
character, or the NUL terminator if all characters were consumed.</p>
<p>If there’s an overflow, <code>HUGE_VAL</code>,
<code>HUGE_VALF</code>, or <code>HUGE_VALL</code> is returned, signed
like the input, and <code>errno</code> is set to
<code>ERANGE</code>.</p>
<p>If there’s an underflow, it returns the smallest number closest to
zero with the input sign. <code>errno</code> may be set to
<code>ERANGE</code>.</p>
<h3 class="unnumbered unlisted" id="example-163">Example</h3>
<div class="sourceCode" id="cb1310"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1310-1"><a href="stdlib.html#cb1310-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1310-2"><a href="stdlib.html#cb1310-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1310-3"><a href="stdlib.html#cb1310-3"></a></span>
<span id="cb1310-4"><a href="stdlib.html#cb1310-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1310-5"><a href="stdlib.html#cb1310-5"></a><span class="op">{</span></span>
<span id="cb1310-6"><a href="stdlib.html#cb1310-6"></a>    <span class="dt">char</span> <span class="op">*</span>inp <span class="op">=</span> <span class="st">"   123.4567beej"</span><span class="op">;</span></span>
<span id="cb1310-7"><a href="stdlib.html#cb1310-7"></a>    <span class="dt">char</span> <span class="op">*</span>badchar<span class="op">;</span></span>
<span id="cb1310-8"><a href="stdlib.html#cb1310-8"></a></span>
<span id="cb1310-9"><a href="stdlib.html#cb1310-9"></a>    <span class="dt">double</span> val <span class="op">=</span> strtod<span class="op">(</span>inp<span class="op">,</span> <span class="op">&amp;</span>badchar<span class="op">);</span></span>
<span id="cb1310-10"><a href="stdlib.html#cb1310-10"></a></span>
<span id="cb1310-11"><a href="stdlib.html#cb1310-11"></a>    printf<span class="op">(</span><span class="st">"Converted string to %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">);</span></span>
<span id="cb1310-12"><a href="stdlib.html#cb1310-12"></a>    printf<span class="op">(</span><span class="st">"Encountered bad characters: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> badchar<span class="op">);</span></span>
<span id="cb1310-13"><a href="stdlib.html#cb1310-13"></a></span>
<span id="cb1310-14"><a href="stdlib.html#cb1310-14"></a>    val <span class="op">=</span> strtod<span class="op">(</span><span class="st">"987.654321beej"</span><span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1310-15"><a href="stdlib.html#cb1310-15"></a>    printf<span class="op">(</span><span class="st">"Ignoring bad chars for result: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">);</span></span>
<span id="cb1310-16"><a href="stdlib.html#cb1310-16"></a></span>
<span id="cb1310-17"><a href="stdlib.html#cb1310-17"></a>    val <span class="op">=</span> strtod<span class="op">(</span><span class="st">"11.2233"</span><span class="op">,</span> <span class="op">&amp;</span>badchar<span class="op">);</span></span>
<span id="cb1310-18"><a href="stdlib.html#cb1310-18"></a></span>
<span id="cb1310-19"><a href="stdlib.html#cb1310-19"></a>    <span class="cf">if</span> <span class="op">(*</span>badchar <span class="op">==</span> <span class="ch">'\0'</span><span class="op">)</span></span>
<span id="cb1310-20"><a href="stdlib.html#cb1310-20"></a>        printf<span class="op">(</span><span class="st">"No bad chars: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">);</span></span>
<span id="cb1310-21"><a href="stdlib.html#cb1310-21"></a>    <span class="cf">else</span></span>
<span id="cb1310-22"><a href="stdlib.html#cb1310-22"></a>        printf<span class="op">(</span><span class="st">"Found bad chars: %f, %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">,</span> badchar<span class="op">);</span></span>
<span id="cb1310-23"><a href="stdlib.html#cb1310-23"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1311"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1311-1"><a href="stdlib.html#cb1311-1" aria-hidden="true" tabindex="-1"></a>Converted string to 123.456700</span>
<span id="cb1311-2"><a href="stdlib.html#cb1311-2" aria-hidden="true" tabindex="-1"></a>Encountered bad characters: beej</span>
<span id="cb1311-3"><a href="stdlib.html#cb1311-3" aria-hidden="true" tabindex="-1"></a>Ignoring bad chars: 987.654321</span>
<span id="cb1311-4"><a href="stdlib.html#cb1311-4" aria-hidden="true" tabindex="-1"></a>No bad chars: 11.223300</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-154">See Also</h3>
<p><a href="stdlib.html#man-atof"><code>atof()</code></a>, <a href="#man-strtol"><code>strtol()</code></a></p>
<hr>
<h2 data-number="62.5" id="man-strtol"><span class="header-section-number">62.5</span> <code>strtol()</code>,
<code>strtoll()</code>, <code>strtoul()</code>,
<code>strtoull()</code></h2>
<p>Convert a string to an integer</p>
<h3 class="unnumbered unlisted" id="synopsis-163">Synopsis</h3>
<div class="sourceCode" id="cb1312"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1312-1"><a href="stdlib.html#cb1312-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1312-2"><a href="stdlib.html#cb1312-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1312-3"><a href="stdlib.html#cb1312-3" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> strtol<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1312-4"><a href="stdlib.html#cb1312-4" aria-hidden="true" tabindex="-1"></a>                <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb1312-5"><a href="stdlib.html#cb1312-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1312-6"><a href="stdlib.html#cb1312-6" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> strtoll<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1312-7"><a href="stdlib.html#cb1312-7" aria-hidden="true" tabindex="-1"></a>                      <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb1312-8"><a href="stdlib.html#cb1312-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1312-9"><a href="stdlib.html#cb1312-9" aria-hidden="true" tabindex="-1"></a><span class="dt">unsigned</span> <span class="dt">long</span> <span class="dt">int</span> strtoul<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1312-10"><a href="stdlib.html#cb1312-10" aria-hidden="true" tabindex="-1"></a>                          <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb1312-11"><a href="stdlib.html#cb1312-11" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1312-12"><a href="stdlib.html#cb1312-12" aria-hidden="true" tabindex="-1"></a><span class="dt">unsigned</span> <span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> strtoull<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1312-13"><a href="stdlib.html#cb1312-13" aria-hidden="true" tabindex="-1"></a>                                <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-163">Description</h3>
<p>These convert a string to an integer like <code>atoi()</code>, but
they have a few more bells and whistles.</p>
<p>Most notable, they can tell you where conversion started going wrong,
i.e.&nbsp;where invalid characters, if any, appear. Leading spaces are
ignored. A <code>+</code> or <code>-</code> sign may precede the
number.</p>
<p>The basic idea is that if things go well, these functions will return
the integer values contained in the strings. And if you pass in the
<code>char**</code> typed <code>endptr</code>, it’ll set it to point at
the NUL at the end of the string.</p>
<p>If things don’t go well, they’ll set <code>endptr</code> to point at
the first character where things have gone awry. That is, if you’re
converting a value <code>103z2!</code> in base 10, they’ll send
<code>endptr</code> to point at the <code>z</code> because that’s the
first non-numeric character.</p>
<p>You can pass in <code>NULL</code> for <code>endptr</code> if you
don’t care to do any of that kind of error checking.</p>
<p>Wait—did I just say we could set the number base for the conversion?
Yes! Yes, I did. Now <a href="https://en.wikipedia.org/wiki/Radix">number bases</a><a href="#fn259" class="footnote-ref" id="fnref259" role="doc-noteref"><sup>259</sup></a> are out of scope for this
document, but certainly some of the more well-known are binary (base 2),
octal (base 8), decimal (base 10), and hexadecimal (base 16).</p>
<p>You can specify the number base for the conversion as the third
parameter. Bases from 2 to 36 are supported, with case-insensitive
digits running from <code>0</code> to <code>Z</code>.</p>
<p>If you specify a base of <code>0</code>, the function will make an
effort to determine it. It’ll default to base 10 except for a couple
cases:</p>
<ul>
<li>If the number has a leading <code>0</code>, it will be octal (base
8)</li>
<li>If the number has a leading <code>0x</code> or <code>0X</code>, it
will be hex (base 16)</li>
</ul>
<p>The locale might affect the behavior of these functions.</p>
<h3 class="unnumbered unlisted" id="return-value-161">Return Value</h3>
<p>Returns the converted value.</p>
<p><code>endptr</code>, if not <code>NULL</code> is set to the first
invalid character, or to the beginning of the string if no conversion
was performed, or to the string terminal NUL if all characters were
valid.</p>
<p>If there’s overflow, one of these values will be returned:
<code>LONG_MIN</code>, <code>LONG_MAX</code>, <code>LLONG_MIN</code>,
<code>LLONG_MAX</code>, <code>ULONG_MAX</code>, <code>ULLONG_MAX</code>.
And <code>errno</code> is set to <code>ERANGE</code>.</p>
<h3 class="unnumbered unlisted" id="example-164">Example</h3>
<div class="sourceCode" id="cb1313"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1313-1"><a href="stdlib.html#cb1313-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1313-2"><a href="stdlib.html#cb1313-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1313-3"><a href="stdlib.html#cb1313-3"></a></span>
<span id="cb1313-4"><a href="stdlib.html#cb1313-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1313-5"><a href="stdlib.html#cb1313-5"></a><span class="op">{</span></span>
<span id="cb1313-6"><a href="stdlib.html#cb1313-6"></a>    <span class="co">// All output in decimal (base 10)</span></span>
<span id="cb1313-7"><a href="stdlib.html#cb1313-7"></a></span>
<span id="cb1313-8"><a href="stdlib.html#cb1313-8"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strtol<span class="op">(</span><span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span>      <span class="co">// 123</span></span>
<span id="cb1313-9"><a href="stdlib.html#cb1313-9"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strtol<span class="op">(</span><span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">10</span><span class="op">));</span>     <span class="co">// 123</span></span>
<span id="cb1313-10"><a href="stdlib.html#cb1313-10"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strtol<span class="op">(</span><span class="st">"101010"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">2</span><span class="op">));</span>   <span class="co">// binary, 42</span></span>
<span id="cb1313-11"><a href="stdlib.html#cb1313-11"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strtol<span class="op">(</span><span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">8</span><span class="op">));</span>      <span class="co">// octal, 83</span></span>
<span id="cb1313-12"><a href="stdlib.html#cb1313-12"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strtol<span class="op">(</span><span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">16</span><span class="op">));</span>     <span class="co">// hex, 291</span></span>
<span id="cb1313-13"><a href="stdlib.html#cb1313-13"></a></span>
<span id="cb1313-14"><a href="stdlib.html#cb1313-14"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strtol<span class="op">(</span><span class="st">"0123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span>     <span class="co">// octal, 83</span></span>
<span id="cb1313-15"><a href="stdlib.html#cb1313-15"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strtol<span class="op">(</span><span class="st">"0x123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span>    <span class="co">// hex, 291</span></span>
<span id="cb1313-16"><a href="stdlib.html#cb1313-16"></a></span>
<span id="cb1313-17"><a href="stdlib.html#cb1313-17"></a>    <span class="dt">char</span> <span class="op">*</span>badchar<span class="op">;</span></span>
<span id="cb1313-18"><a href="stdlib.html#cb1313-18"></a>    <span class="dt">long</span> <span class="dt">int</span> x <span class="op">=</span> strtol<span class="op">(</span><span class="st">"   1234beej"</span><span class="op">,</span> <span class="op">&amp;</span>badchar<span class="op">,</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb1313-19"><a href="stdlib.html#cb1313-19"></a></span>
<span id="cb1313-20"><a href="stdlib.html#cb1313-20"></a>    printf<span class="op">(</span><span class="st">"Value is %ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span>               <span class="co">// Value is 1234</span></span>
<span id="cb1313-21"><a href="stdlib.html#cb1313-21"></a>    printf<span class="op">(</span><span class="st">"Bad chars at </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> badchar<span class="op">);</span>  <span class="co">// Bad chars at "beej"</span></span>
<span id="cb1313-22"><a href="stdlib.html#cb1313-22"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1314"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1314-1"><a href="stdlib.html#cb1314-1" aria-hidden="true" tabindex="-1"></a>123</span>
<span id="cb1314-2"><a href="stdlib.html#cb1314-2" aria-hidden="true" tabindex="-1"></a>123</span>
<span id="cb1314-3"><a href="stdlib.html#cb1314-3" aria-hidden="true" tabindex="-1"></a>42</span>
<span id="cb1314-4"><a href="stdlib.html#cb1314-4" aria-hidden="true" tabindex="-1"></a>83</span>
<span id="cb1314-5"><a href="stdlib.html#cb1314-5" aria-hidden="true" tabindex="-1"></a>291</span>
<span id="cb1314-6"><a href="stdlib.html#cb1314-6" aria-hidden="true" tabindex="-1"></a>83</span>
<span id="cb1314-7"><a href="stdlib.html#cb1314-7" aria-hidden="true" tabindex="-1"></a>291</span>
<span id="cb1314-8"><a href="stdlib.html#cb1314-8" aria-hidden="true" tabindex="-1"></a>Value is 1234</span>
<span id="cb1314-9"><a href="stdlib.html#cb1314-9" aria-hidden="true" tabindex="-1"></a>Bad chars at "beej"</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-155">See Also</h3>
<p><a href="stdlib.html#man-atoi"><code>atoi()</code></a>, <a href="#man-strtod"><code>strtod()</code></a>, <a href="#man-setlocale"><code>setlocale()</code></a>, <a href="#man-strtoimax"><code>strtoimax()</code></a>, <a href="#man-strtoimax"><code>strtoumax()</code></a></p>
<hr>
<h2 data-number="62.6" id="man-rand"><span class="header-section-number">62.6</span> <code>rand()</code></h2>
<p>Return a pseudorandom number</p>
<h3 class="unnumbered unlisted" id="synopsis-164">Synopsis</h3>
<div class="sourceCode" id="cb1315"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1315-1"><a href="stdlib.html#cb1315-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1315-2"><a href="stdlib.html#cb1315-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1315-3"><a href="stdlib.html#cb1315-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> rand<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-164">Description</h3>
<p>This gives us back a pseudorandom number in the range <code>0</code>
to <code>RAND_MAX</code>, inclusive. (<code>RAND_MAX</code> will be at
least <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c37"></mjx-c><mjx-c class="mjx-c36"></mjx-c><mjx-c class="mjx-c37"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>32767</mn></math></mjx-assistive-mml></mjx-container></span>.)</p>
<p>If you want to force this to a certain range, the classic way to do
this is to force it with the modulo operator <code>%</code>, although <a href="https://stackoverflow.com/questions/10984974/why-do-people-say-there-is-modulo-bias-when-using-a-random-number-generator">this
introduces biases</a><a href="footnotes.html#fn260" class="footnote-ref" id="fnref260" role="doc-noteref"><sup>260</sup></a> if <code>RAND_MAX+1</code> is not
a multiple of the number you’re modding by. Dealing with this is out of
scope for this guide.</p>
<p>If you want to to make a floating point number between <code>0</code>
and <code>1</code> inclusive, you can divide the result by
<code>RAND_MAX</code>. Or <code>RAND_MAX+1</code> if you don’t want to
include <code>1</code>. But of course, there are out-of-scope <a href="https://mumble.net/~campbell/2014/04/28/uniform-random-float">problems
with this, as well</a><a href="footnotes.html#fn261" class="footnote-ref" id="fnref261" role="doc-noteref"><sup>261</sup></a>.</p>
<p>In short, <code>rand()</code> is a great way to get potentially poor
random numbers with ease. Probably good enough for the game you’re
writing.</p>
<p>The spec elaborates:</p>
<blockquote>
<p>There are no guarantees as to the quality of the random sequence
produced and some implementations are known to produce sequences with
distressingly non-random low-order bits. Applications with particular
requirements should use a generator that is known to be sufficient for
their needs.</p>
</blockquote>
<p>Your system probably has a good random number generator on it if you
need a stronger source. Linux users have <code>getrandom()</code>, for
example, and Windows has <code>CryptGenRandom()</code>.</p>
<p>For other more demanding random number work, you might find a library
like the <a href="https://www.gnu.org/software/gsl/doc/html/rng.html">GNU Scientific
Library</a><a href="footnotes.html#fn262" class="footnote-ref" id="fnref262" role="doc-noteref"><sup>262</sup></a> of use.</p>
<p>With most implementations, the numbers produced by
<code>rand()</code> will be the same from run to run. To get around
this, you need to start it off in a different place by passing a
<em>seed</em> into the random number generator. You can do this with <a href="#man-srand"><code>srand()</code></a>.</p>
<h3 class="unnumbered unlisted" id="return-value-162">Return Value</h3>
<p>Returns a random number in the range <code>0</code> to
<code>RAND_MAX</code>, inclusive.</p>
<h3 class="unnumbered unlisted" id="example-165">Example</h3>
<p>Note that all of these examples don’t produce perfectly uniform
distributions. But good enough for the untrained eye, and really common
in general use when mediocre random number quality is acceptable.</p>
<div class="sourceCode" id="cb1316"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1316-1"><a href="stdlib.html#cb1316-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1316-2"><a href="stdlib.html#cb1316-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1316-3"><a href="stdlib.html#cb1316-3"></a></span>
<span id="cb1316-4"><a href="stdlib.html#cb1316-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1316-5"><a href="stdlib.html#cb1316-5"></a><span class="op">{</span></span>
<span id="cb1316-6"><a href="stdlib.html#cb1316-6"></a>    printf<span class="op">(</span><span class="st">"RAND_MAX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> RAND_MAX<span class="op">);</span></span>
<span id="cb1316-7"><a href="stdlib.html#cb1316-7"></a></span>
<span id="cb1316-8"><a href="stdlib.html#cb1316-8"></a>    printf<span class="op">(</span><span class="st">"0 to 9: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rand<span class="op">()</span> <span class="op">%</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb1316-9"><a href="stdlib.html#cb1316-9"></a></span>
<span id="cb1316-10"><a href="stdlib.html#cb1316-10"></a>    printf<span class="op">(</span><span class="st">"10 to 44: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rand<span class="op">()</span> <span class="op">%</span> <span class="dv">35</span> <span class="op">+</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb1316-11"><a href="stdlib.html#cb1316-11"></a>    printf<span class="op">(</span><span class="st">"0 to 0.99999: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rand<span class="op">()</span> <span class="op">/</span> <span class="op">((</span><span class="dt">float</span><span class="op">)</span>RAND_MAX <span class="op">+</span> <span class="dv">1</span><span class="op">));</span></span>
<span id="cb1316-12"><a href="stdlib.html#cb1316-12"></a>    printf<span class="op">(</span><span class="st">"10.5 to 15.7: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="fl">10.5</span> <span class="op">+</span> <span class="fl">5.2</span> <span class="op">*</span> rand<span class="op">()</span> <span class="op">/</span> <span class="op">(</span><span class="dt">float</span><span class="op">)</span>RAND_MAX<span class="op">);</span></span>
<span id="cb1316-13"><a href="stdlib.html#cb1316-13"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1317"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1317-1"><a href="stdlib.html#cb1317-1" aria-hidden="true" tabindex="-1"></a>RAND_MAX = 2147483647</span>
<span id="cb1317-2"><a href="stdlib.html#cb1317-2" aria-hidden="true" tabindex="-1"></a>0 to 9: 3</span>
<span id="cb1317-3"><a href="stdlib.html#cb1317-3" aria-hidden="true" tabindex="-1"></a>10 to 44: 21</span>
<span id="cb1317-4"><a href="stdlib.html#cb1317-4" aria-hidden="true" tabindex="-1"></a>0 to 0.99999: 0.783099</span>
<span id="cb1317-5"><a href="stdlib.html#cb1317-5" aria-hidden="true" tabindex="-1"></a>10.5 to 15.7: 14.651888</span></code></pre></div>
<p>Example of seeding the RNG with the time:</p>
<div class="sourceCode" id="cb1318"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1318-1"><a href="stdlib.html#cb1318-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1318-2"><a href="stdlib.html#cb1318-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1318-3"><a href="stdlib.html#cb1318-3"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1318-4"><a href="stdlib.html#cb1318-4"></a></span>
<span id="cb1318-5"><a href="stdlib.html#cb1318-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1318-6"><a href="stdlib.html#cb1318-6"></a><span class="op">{</span></span>
<span id="cb1318-7"><a href="stdlib.html#cb1318-7"></a>    <span class="co">// time(NULL) very likely returns the number of seconds since</span></span>
<span id="cb1318-8"><a href="stdlib.html#cb1318-8"></a>    <span class="co">// January 1, 1970:</span></span>
<span id="cb1318-9"><a href="stdlib.html#cb1318-9"></a></span>
<span id="cb1318-10"><a href="stdlib.html#cb1318-10"></a>    srand<span class="op">(</span>time<span class="op">(</span>NULL<span class="op">));</span></span>
<span id="cb1318-11"><a href="stdlib.html#cb1318-11"></a></span>
<span id="cb1318-12"><a href="stdlib.html#cb1318-12"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> <span class="dv">5</span><span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1318-13"><a href="stdlib.html#cb1318-13"></a>        printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rand<span class="op">());</span></span>
<span id="cb1318-14"><a href="stdlib.html#cb1318-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-156">See Also</h3>
<p><a href="stdlib.html#man-srand"><code>srand()</code></a></p>
<hr>
<h2 data-number="62.7" id="man-srand"><span class="header-section-number">62.7</span> <code>srand()</code></h2>
<p>Seed the built-in pseudorandom number generator</p>
<h3 class="unnumbered unlisted" id="synopsis-165">Synopsis</h3>
<div class="sourceCode" id="cb1319"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1319-1"><a href="stdlib.html#cb1319-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1319-2"><a href="stdlib.html#cb1319-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1319-3"><a href="stdlib.html#cb1319-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> srand<span class="op">(</span><span class="dt">unsigned</span> <span class="dt">int</span> seed<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-165">Description</h3>
<p>The dirty little secret of pseudorandom number generation is that
they’re completely deterministic. There’s nothing random about them.
They just look random.</p>
<p>If you use <code>rand()</code> and run your program several times,
you might notice something <em>fishy</em>: they produce the same random
numbers over and over again.</p>
<p>To mix it up, we need to give the pseudorandom number generator a new
“starting point”, if you will. We call that the <em>seed</em>. It’s just
a number, but it is used as the basic for subsequent number generation.
Give a different seed, and you’ll get a different sequence of random
numbers. Give the same seed, and you’ll get the same sequence of random
numbers corresponding to it<a href="footnotes.html#fn263" class="footnote-ref" id="fnref263" role="doc-noteref"><sup>263</sup></a>.</p>
<p>So if you call <code>srand(3490)</code> before you start generating
numbers with <code>rand()</code>, you’ll get the same sequence every
time. <code>srand(37)</code> would also give you the same sequence every
time, but it would be a different sequence than the one you got with
<code>srand(3490)</code>.</p>
<p>But if you can’t hardcode the seed (because that would give you the
same sequence every time), how are you supposed to do this?</p>
<p>It’s really common to use the number of seconds since January 1, 1970
(this date is known as the <a href="https://en.wikipedia.org/wiki/Unix_time"><em>Unix epoch</em></a><a href="#fn264" class="footnote-ref" id="fnref264" role="doc-noteref"><sup>264</sup></a>) to seed the generator. This
sounds pretty arbitrary except for the fact that it’s exactly the value
most implementations return from the library call
<code>time(NULL)</code><a href="footnotes.html#fn265" class="footnote-ref" id="fnref265" role="doc-noteref"><sup>265</sup></a>.</p>
<p>We’ll do that in the example.</p>
<p>If you don’t call <code>srand()</code>, it’s as if you called
<code>srand(1)</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-163">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-166">Example</h3>
<div class="sourceCode" id="cb1320"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1320-1"><a href="stdlib.html#cb1320-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1320-2"><a href="stdlib.html#cb1320-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1320-3"><a href="stdlib.html#cb1320-3"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span><span class="pp">    </span><span class="co">// for the time() call</span></span>
<span id="cb1320-4"><a href="stdlib.html#cb1320-4"></a></span>
<span id="cb1320-5"><a href="stdlib.html#cb1320-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1320-6"><a href="stdlib.html#cb1320-6"></a><span class="op">{</span></span>
<span id="cb1320-7"><a href="stdlib.html#cb1320-7"></a>    srand<span class="op">(</span>time<span class="op">(</span>NULL<span class="op">));</span></span>
<span id="cb1320-8"><a href="stdlib.html#cb1320-8"></a></span>
<span id="cb1320-9"><a href="stdlib.html#cb1320-9"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> <span class="dv">5</span><span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1320-10"><a href="stdlib.html#cb1320-10"></a>        printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rand<span class="op">()</span> <span class="op">%</span> <span class="dv">32</span><span class="op">);</span></span>
<span id="cb1320-11"><a href="stdlib.html#cb1320-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1321"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1321-1"><a href="stdlib.html#cb1321-1" aria-hidden="true" tabindex="-1"></a>4</span>
<span id="cb1321-2"><a href="stdlib.html#cb1321-2" aria-hidden="true" tabindex="-1"></a>20</span>
<span id="cb1321-3"><a href="stdlib.html#cb1321-3" aria-hidden="true" tabindex="-1"></a>22</span>
<span id="cb1321-4"><a href="stdlib.html#cb1321-4" aria-hidden="true" tabindex="-1"></a>14</span>
<span id="cb1321-5"><a href="stdlib.html#cb1321-5" aria-hidden="true" tabindex="-1"></a>9</span></code></pre></div>
<p>Output from a subsequent run:</p>
<div class="sourceCode" id="cb1322"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1322-1"><a href="stdlib.html#cb1322-1" aria-hidden="true" tabindex="-1"></a>19</span>
<span id="cb1322-2"><a href="stdlib.html#cb1322-2" aria-hidden="true" tabindex="-1"></a>0</span>
<span id="cb1322-3"><a href="stdlib.html#cb1322-3" aria-hidden="true" tabindex="-1"></a>31</span>
<span id="cb1322-4"><a href="stdlib.html#cb1322-4" aria-hidden="true" tabindex="-1"></a>31</span>
<span id="cb1322-5"><a href="stdlib.html#cb1322-5" aria-hidden="true" tabindex="-1"></a>24</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-157">See Also</h3>
<p><a href="stdlib.html#man-rand"><code>rand()</code></a>, <a href="#man-time"><code>time()</code></a></p>
<hr>
<h2 data-number="62.8" id="man-aligned_alloc"><span class="header-section-number">62.8</span>
<code>aligned_alloc()</code></h2>
<p>Allocate specifically-aligned memory</p>
<h3 class="unnumbered unlisted" id="synopsis-166">Synopsis</h3>
<div class="sourceCode" id="cb1323"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1323-1"><a href="stdlib.html#cb1323-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1323-2"><a href="stdlib.html#cb1323-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1323-3"><a href="stdlib.html#cb1323-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>aligned_alloc<span class="op">(</span><span class="dt">size_t</span> alignment<span class="op">,</span> <span class="dt">size_t</span> size<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-166">Description</h3>
<p>Maybe you wanted <a href="stdlib.html#man-malloc"><code>malloc()</code></a> or
<a href="stdlib.html#man-malloc"><code>calloc()</code></a> instead of this. But if
you’re sure you don’t, read on!</p>
<p>Normally you don’t have to think about this, since
<code>malloc()</code> and <code>realloc()</code> both provide memory
regions that are suitably <a href="https://en.wikipedia.org/wiki/Data_structure_alignment">aligned</a><a href="#fn266" class="footnote-ref" id="fnref266" role="doc-noteref"><sup>266</sup></a> for use with any data type.</p>
<p>But if you need a more specific alignment, you can specify it with
this function.</p>
<p>When you’re done using the memory region, be sure to free it with a
call to <a href="stdlib.html#man-free"><code>free()</code></a>.</p>
<p>Don’t pass in <code>0</code> for the size. It probably won’t do
anything you want.</p>
<p>In case you’re wondering, all dynamically-allocated memory is
automatically freed by the system when the program ends. That said, it’s
considered to be <em>Good Form</em> to explicitly <code>free()</code>
everything you allocate. This way other programmers don’t think you were
being sloppy.</p>
<h3 class="unnumbered unlisted" id="return-value-164">Return Value</h3>
<p>Returns a pointer to the newly-allocated memory, aligned as
specified. Returns <code>NULL</code> if something goes wrong.</p>
<h3 class="unnumbered unlisted" id="example-167">Example</h3>
<div class="sourceCode" id="cb1324"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1324-1"><a href="stdlib.html#cb1324-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1324-2"><a href="stdlib.html#cb1324-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1324-3"><a href="stdlib.html#cb1324-3"></a><span class="pp">#include </span><span class="im">&lt;stdint.h&gt;</span></span>
<span id="cb1324-4"><a href="stdlib.html#cb1324-4"></a></span>
<span id="cb1324-5"><a href="stdlib.html#cb1324-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1324-6"><a href="stdlib.html#cb1324-6"></a><span class="op">{</span></span>
<span id="cb1324-7"><a href="stdlib.html#cb1324-7"></a>    <span class="dt">int</span> <span class="op">*</span>p <span class="op">=</span> aligned_alloc<span class="op">(</span><span class="dv">256</span><span class="op">,</span> <span class="dv">10</span> <span class="op">*</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">));</span></span>
<span id="cb1324-8"><a href="stdlib.html#cb1324-8"></a></span>
<span id="cb1324-9"><a href="stdlib.html#cb1324-9"></a>    <span class="co">// Just for fun, let's convert to intptr_t and mod with 256</span></span>
<span id="cb1324-10"><a href="stdlib.html#cb1324-10"></a>    <span class="co">// to make sure we're actually aligned on a 256-byte boundary.</span></span>
<span id="cb1324-11"><a href="stdlib.html#cb1324-11"></a>    <span class="co">//</span></span>
<span id="cb1324-12"><a href="stdlib.html#cb1324-12"></a>    <span class="co">// This is probably some kind of implementation-defined</span></span>
<span id="cb1324-13"><a href="stdlib.html#cb1324-13"></a>    <span class="co">// behavior, but I'll bet it works.</span></span>
<span id="cb1324-14"><a href="stdlib.html#cb1324-14"></a></span>
<span id="cb1324-15"><a href="stdlib.html#cb1324-15"></a>    <span class="dt">intptr_t</span> ip <span class="op">=</span> <span class="op">(</span><span class="dt">intptr_t</span><span class="op">)</span>p<span class="op">;</span></span>
<span id="cb1324-16"><a href="stdlib.html#cb1324-16"></a></span>
<span id="cb1324-17"><a href="stdlib.html#cb1324-17"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ip <span class="op">%</span> <span class="dv">256</span><span class="op">);</span>   <span class="co">// 0!</span></span>
<span id="cb1324-18"><a href="stdlib.html#cb1324-18"></a></span>
<span id="cb1324-19"><a href="stdlib.html#cb1324-19"></a>    <span class="co">// Free it up</span></span>
<span id="cb1324-20"><a href="stdlib.html#cb1324-20"></a>    free<span class="op">(</span>p<span class="op">);</span></span>
<span id="cb1324-21"><a href="stdlib.html#cb1324-21"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-158">See Also</h3>
<p><a href="stdlib.html#man-malloc"><code>malloc()</code></a>, <a href="#man-malloc"><code>calloc()</code></a>, <a href="#man-free"><code>free()</code></a></p>
<hr>
<h2 data-number="62.9" id="man-malloc"><span class="header-section-number">62.9</span> <code>calloc()</code>,
<code>malloc()</code></h2>
<p>Allocate memory for arbitrary use</p>
<h3 class="unnumbered unlisted" id="synopsis-167">Synopsis</h3>
<div class="sourceCode" id="cb1325"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1325-1"><a href="stdlib.html#cb1325-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1325-2"><a href="stdlib.html#cb1325-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1325-3"><a href="stdlib.html#cb1325-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>calloc<span class="op">(</span><span class="dt">size_t</span> nmemb<span class="op">,</span> <span class="dt">size_t</span> size<span class="op">);</span></span>
<span id="cb1325-4"><a href="stdlib.html#cb1325-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1325-5"><a href="stdlib.html#cb1325-5" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>malloc<span class="op">(</span><span class="dt">size_t</span> size<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-167">Description</h3>
<p>Both of these functions allocate memory for general-purpose use. It
will be aligned such that it’s useable for storing any data type.</p>
<p><code>malloc()</code> allocates exactly the specified number of bytes
of memory in a contiguous block. The memory might be full of garbage
data. (You can clear it with <a href="#man-memset"><code>memset()</code></a>, if you wish.)</p>
<p><code>calloc()</code> is different in that it allocates space for
<code>nmemb</code> objects of <code>size</code> bytes each. (You can do
the same with <code>malloc()</code>, but you have to do the
multiplication yourself.)</p>
<p><code>calloc()</code> has an additional feature: it clears all the
memory to <code>0</code>.</p>
<p>So if you’re planning to zero the memory anyway,
<code>calloc()</code> is probably the way to go. If you’re not, you can
avoid that overhead by calling <code>malloc()</code>.</p>
<p>When you’re done using the memory region, free it with a call to
<code>free()</code>.</p>
<p>Don’t pass in <code>0</code> for the size. It probably won’t do
anything you want.</p>
<p>In case you’re wondering, all dynamically-allocated memory is
automatically freed by the system when the program ends. That said, it’s
considered to be <em>Good Form</em> to explicitly <code>free()</code>
everything you allocate. This way other programmers don’t think you were
being sloppy.</p>
<h3 class="unnumbered unlisted" id="return-value-165">Return Value</h3>
<p>Both functions return a pointer to the shiny, newly-allocated memory.
Or <code>NULL</code> if something’s gone awry.</p>
<h3 class="unnumbered unlisted" id="example-168">Example</h3>
<p>Comparison of <code>malloc()</code> and <code>calloc()</code> for
allocating 5 <code>int</code>s:</p>
<div class="sourceCode" id="cb1326"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1326-1"><a href="stdlib.html#cb1326-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1326-2"><a href="stdlib.html#cb1326-2"></a></span>
<span id="cb1326-3"><a href="stdlib.html#cb1326-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1326-4"><a href="stdlib.html#cb1326-4"></a><span class="op">{</span></span>
<span id="cb1326-5"><a href="stdlib.html#cb1326-5"></a>    <span class="co">// Allocate space for 5 ints</span></span>
<span id="cb1326-6"><a href="stdlib.html#cb1326-6"></a>    <span class="dt">int</span> <span class="op">*</span>p <span class="op">=</span> malloc<span class="op">(</span><span class="dv">5</span> <span class="op">*</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">));</span></span>
<span id="cb1326-7"><a href="stdlib.html#cb1326-7"></a></span>
<span id="cb1326-8"><a href="stdlib.html#cb1326-8"></a>    p<span class="op">[</span><span class="dv">0</span><span class="op">]</span> <span class="op">=</span> <span class="dv">12</span><span class="op">;</span></span>
<span id="cb1326-9"><a href="stdlib.html#cb1326-9"></a>    p<span class="op">[</span><span class="dv">1</span><span class="op">]</span> <span class="op">=</span> <span class="dv">30</span><span class="op">;</span></span>
<span id="cb1326-10"><a href="stdlib.html#cb1326-10"></a></span>
<span id="cb1326-11"><a href="stdlib.html#cb1326-11"></a>    <span class="co">// Allocate space for 5 ints</span></span>
<span id="cb1326-12"><a href="stdlib.html#cb1326-12"></a>    <span class="co">// (Also clear that memory to 0)</span></span>
<span id="cb1326-13"><a href="stdlib.html#cb1326-13"></a>    <span class="dt">int</span> <span class="op">*</span>q <span class="op">=</span> calloc<span class="op">(</span><span class="dv">5</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">));</span></span>
<span id="cb1326-14"><a href="stdlib.html#cb1326-14"></a></span>
<span id="cb1326-15"><a href="stdlib.html#cb1326-15"></a>    q<span class="op">[</span><span class="dv">0</span><span class="op">]</span> <span class="op">=</span> <span class="dv">12</span><span class="op">;</span></span>
<span id="cb1326-16"><a href="stdlib.html#cb1326-16"></a>    q<span class="op">[</span><span class="dv">1</span><span class="op">]</span> <span class="op">=</span> <span class="dv">30</span><span class="op">;</span></span>
<span id="cb1326-17"><a href="stdlib.html#cb1326-17"></a></span>
<span id="cb1326-18"><a href="stdlib.html#cb1326-18"></a>    <span class="co">// All done</span></span>
<span id="cb1326-19"><a href="stdlib.html#cb1326-19"></a>    free<span class="op">(</span>p<span class="op">);</span></span>
<span id="cb1326-20"><a href="stdlib.html#cb1326-20"></a>    free<span class="op">(</span>q<span class="op">);</span></span>
<span id="cb1326-21"><a href="stdlib.html#cb1326-21"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-159">See Also</h3>
<p><a href="stdlib.html#man-aligned_alloc"><code>aligned_alloc()</code></a>, <a href="#man-free"><code>free()</code></a></p>
<hr>
<h2 data-number="62.10" id="man-free"><span class="header-section-number">62.10</span> <code>free()</code></h2>
<p>Free a memory region</p>
<h3 class="unnumbered unlisted" id="synopsis-168">Synopsis</h3>
<div class="sourceCode" id="cb1327"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1327-1"><a href="stdlib.html#cb1327-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1327-2"><a href="stdlib.html#cb1327-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1327-3"><a href="stdlib.html#cb1327-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> free<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>ptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-168">Description</h3>
<p>You know that pointer you got back from <code>malloc()</code>,
<code>calloc()</code>, or <code>aligned_alloc()</code>? You pass that
pointer to <code>free()</code> to free the memory associated with
it.</p>
<p>If you don’t do this, the memory will stay allocated FOREVER AND
EVER! (Well, until your program exits, anyway.)</p>
<p>Fun fact: <code>free(NULL)</code> does nothing. You can safely call
that. Sometimes it’s convenient.</p>
<p>Don’t <code>free()</code> a pointer that’s already been
<code>free()</code>d.&nbsp;Don’t <code>free()</code> a pointer that you
didn’t get back from one of the allocation functions. It would be
<em>Bad</em><a href="footnotes.html#fn267" class="footnote-ref" id="fnref267" role="doc-noteref"><sup>267</sup></a>.</p>
<h3 class="unnumbered unlisted" id="return-value-166">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-169">Example</h3>
<div class="sourceCode" id="cb1328"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1328-1"><a href="stdlib.html#cb1328-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1328-2"><a href="stdlib.html#cb1328-2"></a></span>
<span id="cb1328-3"><a href="stdlib.html#cb1328-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1328-4"><a href="stdlib.html#cb1328-4"></a><span class="op">{</span></span>
<span id="cb1328-5"><a href="stdlib.html#cb1328-5"></a>    <span class="co">// Allocate space for 5 ints</span></span>
<span id="cb1328-6"><a href="stdlib.html#cb1328-6"></a>    <span class="dt">int</span> <span class="op">*</span>p <span class="op">=</span> malloc<span class="op">(</span><span class="dv">5</span> <span class="op">*</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">));</span></span>
<span id="cb1328-7"><a href="stdlib.html#cb1328-7"></a></span>
<span id="cb1328-8"><a href="stdlib.html#cb1328-8"></a>    p<span class="op">[</span><span class="dv">0</span><span class="op">]</span> <span class="op">=</span> <span class="dv">12</span><span class="op">;</span></span>
<span id="cb1328-9"><a href="stdlib.html#cb1328-9"></a>    p<span class="op">[</span><span class="dv">1</span><span class="op">]</span> <span class="op">=</span> <span class="dv">30</span><span class="op">;</span></span>
<span id="cb1328-10"><a href="stdlib.html#cb1328-10"></a></span>
<span id="cb1328-11"><a href="stdlib.html#cb1328-11"></a>    <span class="co">// Free that space</span></span>
<span id="cb1328-12"><a href="stdlib.html#cb1328-12"></a>    free<span class="op">(</span>p<span class="op">);</span></span>
<span id="cb1328-13"><a href="stdlib.html#cb1328-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-160">See Also</h3>
<p><a href="stdlib.html#man-malloc"><code>malloc()</code></a>, <a href="#man-malloc"><code>calloc()</code></a>, <a href="#man-aligned_alloc"><code>aligned_alloc()</code></a></p>
<hr>
<h2 data-number="62.11" id="man-realloc"><span class="header-section-number">62.11</span> <code>realloc()</code></h2>
<p>Resize a previously allocated stretch of memory</p>
<h3 class="unnumbered unlisted" id="synopsis-169">Synopsis</h3>
<div class="sourceCode" id="cb1329"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1329-1"><a href="stdlib.html#cb1329-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1329-2"><a href="stdlib.html#cb1329-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1329-3"><a href="stdlib.html#cb1329-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>realloc<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>ptr<span class="op">,</span> <span class="dt">size_t</span> size<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-169">Description</h3>
<p>This takes a pointer to some memory previously allocated with
<code>malloc()</code> or <code>calloc()</code> and resizes it to the new
size.</p>
<p>If the new size is smaller than the old size, any data larger than
the new size is discarded.</p>
<p>If the new size is larger than the old size, the new larger part is
uninitialized. (You can clear it with <a href="#man-memset"><code>memset()</code></a>.)</p>
<p>Important note: the memory might move! If you resize, the system
might need to relocate the memory to a larger continguous chunk. If this
happens, <code>realloc()</code> will copy the old data to the new
location for you.</p>
<p>Because of this, it’s important to save the returned value to your
pointer to update it to the new location if things move. (Also, be sure
to error-check so that you don’t overwrite your old pointer with
<code>NULL</code>, leaking the memory.)</p>
<p>You can also <code>relloc()</code> memory allocated with
<code>aligned_alloc()</code>, but it will potentially lose its alignment
if the block is moved.</p>
<h3 class="unnumbered unlisted" id="return-value-167">Return Value</h3>
<p>Returns a pointer to the resized memory region. This might be
equivalent to the <code>ptr</code> passed in, or it might be some other
location.</p>
<h3 class="unnumbered unlisted" id="example-170">Example</h3>
<div class="sourceCode" id="cb1330"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1330-1"><a href="stdlib.html#cb1330-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1330-2"><a href="stdlib.html#cb1330-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1330-3"><a href="stdlib.html#cb1330-3"></a></span>
<span id="cb1330-4"><a href="stdlib.html#cb1330-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1330-5"><a href="stdlib.html#cb1330-5"></a><span class="op">{</span></span>
<span id="cb1330-6"><a href="stdlib.html#cb1330-6"></a>    <span class="co">// Allocate space for 5 ints</span></span>
<span id="cb1330-7"><a href="stdlib.html#cb1330-7"></a>    <span class="dt">int</span> <span class="op">*</span>p <span class="op">=</span> malloc<span class="op">(</span><span class="dv">5</span> <span class="op">*</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">));</span></span>
<span id="cb1330-8"><a href="stdlib.html#cb1330-8"></a></span>
<span id="cb1330-9"><a href="stdlib.html#cb1330-9"></a>    p<span class="op">[</span><span class="dv">0</span><span class="op">]</span> <span class="op">=</span> <span class="dv">12</span><span class="op">;</span></span>
<span id="cb1330-10"><a href="stdlib.html#cb1330-10"></a>    p<span class="op">[</span><span class="dv">1</span><span class="op">]</span> <span class="op">=</span> <span class="dv">30</span><span class="op">;</span></span>
<span id="cb1330-11"><a href="stdlib.html#cb1330-11"></a></span>
<span id="cb1330-12"><a href="stdlib.html#cb1330-12"></a>    <span class="co">// Reallocate for 10 bytes</span></span>
<span id="cb1330-13"><a href="stdlib.html#cb1330-13"></a>    <span class="dt">int</span> <span class="op">*</span>new_p <span class="op">=</span> realloc<span class="op">(</span>p<span class="op">,</span> <span class="dv">10</span> <span class="op">*</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">));</span></span>
<span id="cb1330-14"><a href="stdlib.html#cb1330-14"></a></span>
<span id="cb1330-15"><a href="stdlib.html#cb1330-15"></a>    <span class="cf">if</span> <span class="op">(</span>new_p <span class="op">==</span> NULL<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1330-16"><a href="stdlib.html#cb1330-16"></a>        printf<span class="op">(</span><span class="st">"Error reallocing</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1330-17"><a href="stdlib.html#cb1330-17"></a>    <span class="op">}</span> <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1330-18"><a href="stdlib.html#cb1330-18"></a>        p <span class="op">=</span> new_p<span class="op">;</span>  <span class="co">// It's good; let's keep it</span></span>
<span id="cb1330-19"><a href="stdlib.html#cb1330-19"></a>        p<span class="op">[</span><span class="dv">7</span><span class="op">]</span> <span class="op">=</span> <span class="dv">99</span><span class="op">;</span></span>
<span id="cb1330-20"><a href="stdlib.html#cb1330-20"></a>    <span class="op">}</span></span>
<span id="cb1330-21"><a href="stdlib.html#cb1330-21"></a></span>
<span id="cb1330-22"><a href="stdlib.html#cb1330-22"></a>    <span class="co">// All done</span></span>
<span id="cb1330-23"><a href="stdlib.html#cb1330-23"></a>    free<span class="op">(</span>p<span class="op">);</span></span>
<span id="cb1330-24"><a href="stdlib.html#cb1330-24"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-161">See Also</h3>
<p><a href="stdlib.html#man-malloc"><code>malloc()</code></a>, <a href="#man-malloc"><code>calloc()</code></a></p>
<hr>
<h2 data-number="62.12" id="man-abort"><span class="header-section-number">62.12</span> <code>abort()</code></h2>
<p>Abruptly end program execution</p>
<h3 class="unnumbered unlisted" id="synopsis-170">Synopsis</h3>
<div class="sourceCode" id="cb1331"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1331-1"><a href="stdlib.html#cb1331-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1331-2"><a href="stdlib.html#cb1331-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1331-3"><a href="stdlib.html#cb1331-3" aria-hidden="true" tabindex="-1"></a><span class="kw">_Noreturn</span> <span class="dt">void</span> abort<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-170">Description</h3>
<p>This ends program execution <em>abnormally</em> and immediately. Use
this in rare, unexpected circumstances.</p>
<p>Open streams might not be flushed. Temporary files created might not
be removed. Exit handlers are not called.</p>
<p>A non-zero exit status is returned to the environment.</p>
<p>On some systems, <code>abort()</code> might <a href="https://en.wikipedia.org/wiki/Core_dump">dump core</a><a href="#fn268" class="footnote-ref" id="fnref268" role="doc-noteref"><sup>268</sup></a>, but this is outside the scope of
the spec.</p>
<p>You can cause the equivalent of an <code>abort()</code> by calling
<code>raise(SIGABRT)</code>, but I don’t know why you’d do that.</p>
<p>The only portable way to stop an <code>abort()</code> call midway is
to use <code>signal()</code> to catch <code>SIGABRT</code> and then
<code>exit()</code> in the signal handler.</p>
<h3 class="unnumbered unlisted" id="return-value-168">Return Value</h3>
<p>This function never returns.</p>
<h3 class="unnumbered unlisted" id="example-171">Example</h3>
<div class="sourceCode" id="cb1332"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1332-1"><a href="stdlib.html#cb1332-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1332-2"><a href="stdlib.html#cb1332-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1332-3"><a href="stdlib.html#cb1332-3"></a></span>
<span id="cb1332-4"><a href="stdlib.html#cb1332-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1332-5"><a href="stdlib.html#cb1332-5"></a><span class="op">{</span></span>
<span id="cb1332-6"><a href="stdlib.html#cb1332-6"></a>    <span class="dt">int</span> bad_thing <span class="op">=</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1332-7"><a href="stdlib.html#cb1332-7"></a></span>
<span id="cb1332-8"><a href="stdlib.html#cb1332-8"></a>    <span class="cf">if</span> <span class="op">(</span>bad_thing<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1332-9"><a href="stdlib.html#cb1332-9"></a>        printf<span class="op">(</span><span class="st">"This should never have happened!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1332-10"><a href="stdlib.html#cb1332-10"></a>        fflush<span class="op">(</span>stdout<span class="op">);</span>  <span class="co">// Make sure the message goes out</span></span>
<span id="cb1332-11"><a href="stdlib.html#cb1332-11"></a>        abort<span class="op">();</span></span>
<span id="cb1332-12"><a href="stdlib.html#cb1332-12"></a>    <span class="op">}</span></span>
<span id="cb1332-13"><a href="stdlib.html#cb1332-13"></a><span class="op">}</span></span></code></pre></div>
<p>On my system, this outputs:</p>
<div class="sourceCode" id="cb1333"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1333-1"><a href="stdlib.html#cb1333-1" aria-hidden="true" tabindex="-1"></a>This should never have happened!</span>
<span id="cb1333-2"><a href="stdlib.html#cb1333-2" aria-hidden="true" tabindex="-1"></a>zsh: abort (core dumped)  ./foo</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-162">See Also</h3>
<p><a href="signal.html#man-signal"><code>signal()</code></a></p>
<hr>
<h2 data-number="62.13" id="man-atexit"><span class="header-section-number">62.13</span> <code>atexit()</code>,
<code>at_quick_exit()</code></h2>
<p>Set up handlers to run when the program exits</p>
<h3 class="unnumbered unlisted" id="synopsis-171">Synopsis</h3>
<div class="sourceCode" id="cb1334"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1334-1"><a href="stdlib.html#cb1334-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1334-2"><a href="stdlib.html#cb1334-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1334-3"><a href="stdlib.html#cb1334-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> atexit<span class="op">(</span><span class="dt">void</span> <span class="op">(*</span>func<span class="op">)(</span><span class="dt">void</span><span class="op">));</span></span>
<span id="cb1334-4"><a href="stdlib.html#cb1334-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1334-5"><a href="stdlib.html#cb1334-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> at_quick_exit<span class="op">(</span><span class="dt">void</span> <span class="op">(*</span>func<span class="op">)(</span><span class="dt">void</span><span class="op">));</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-171">Description</h3>
<p>When the program does a normal exit with <code>exit()</code> or
returns from <code>main()</code>, it looks for previously-registered
handlers to call on the way out. These handlers are registered with the
<code>atexit()</code> call.</p>
<p>Think of it like, “Hey, when you’re about to exit, do these extra
things.”</p>
<p>For the <code>quick_exit()</code> call, you can use the
<code>at_quick_exit()</code> function to register handlers for that<a href="#fn269" class="footnote-ref" id="fnref269" role="doc-noteref"><sup>269</sup></a>. There’s no crossover in handlers
from <code>exit()</code> to <code>quick_exit()</code>, i.e.&nbsp;for a call
to one, none of the other’s handlers will fire.</p>
<p>You can register multiple handlers to fire—at least 32 handlers are
supported by both <code>exit()</code> and <code>quick_exit()</code>.</p>
<p>The argument <code>func</code> to the functions looks a little
weird—it’s a pointer to a function to call. Basically just put the
function name to call in there (without parentheses after). See the
example, below.</p>
<p>If you call <code>atexit()</code> from inside your
<code>atexit()</code> handler (or equivalent in your
<code>at_quick_exit()</code> handler), it’s unspecified if it will get
called. So get them all registered before you exit.</p>
<p>When exiting, the functions will be called in the reverse order they
were registered.</p>
<h3 class="unnumbered unlisted" id="return-value-169">Return Value</h3>
<p>These functions return <code>0</code> on success, or nonzero on
failure.</p>
<h3 class="unnumbered unlisted" id="example-172">Example</h3>
<p><code>atexit()</code>:</p>
<div class="sourceCode" id="cb1335"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1335-1"><a href="stdlib.html#cb1335-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1335-2"><a href="stdlib.html#cb1335-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1335-3"><a href="stdlib.html#cb1335-3"></a></span>
<span id="cb1335-4"><a href="stdlib.html#cb1335-4"></a><span class="dt">void</span> exit_handler_1<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1335-5"><a href="stdlib.html#cb1335-5"></a><span class="op">{</span></span>
<span id="cb1335-6"><a href="stdlib.html#cb1335-6"></a>    printf<span class="op">(</span><span class="st">"Exit handler 1 called!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1335-7"><a href="stdlib.html#cb1335-7"></a><span class="op">}</span></span>
<span id="cb1335-8"><a href="stdlib.html#cb1335-8"></a></span>
<span id="cb1335-9"><a href="stdlib.html#cb1335-9"></a><span class="dt">void</span> exit_handler_2<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1335-10"><a href="stdlib.html#cb1335-10"></a><span class="op">{</span></span>
<span id="cb1335-11"><a href="stdlib.html#cb1335-11"></a>    printf<span class="op">(</span><span class="st">"Exit handler 2 called!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1335-12"><a href="stdlib.html#cb1335-12"></a><span class="op">}</span></span>
<span id="cb1335-13"><a href="stdlib.html#cb1335-13"></a></span>
<span id="cb1335-14"><a href="stdlib.html#cb1335-14"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1335-15"><a href="stdlib.html#cb1335-15"></a><span class="op">{</span></span>
<span id="cb1335-16"><a href="stdlib.html#cb1335-16"></a>    atexit<span class="op">(</span>exit_handler_1<span class="op">);</span></span>
<span id="cb1335-17"><a href="stdlib.html#cb1335-17"></a>    atexit<span class="op">(</span>exit_handler_2<span class="op">);</span></span>
<span id="cb1335-18"><a href="stdlib.html#cb1335-18"></a></span>
<span id="cb1335-19"><a href="stdlib.html#cb1335-19"></a>    exit<span class="op">(</span><span class="dv">0</span><span class="op">);</span></span>
<span id="cb1335-20"><a href="stdlib.html#cb1335-20"></a><span class="op">}</span></span></code></pre></div>
<p>For the output:</p>
<div class="sourceCode" id="cb1336"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1336-1"><a href="stdlib.html#cb1336-1" aria-hidden="true" tabindex="-1"></a>Exit handler 2 called!</span>
<span id="cb1336-2"><a href="stdlib.html#cb1336-2" aria-hidden="true" tabindex="-1"></a>Exit handler 1 called!</span></code></pre></div>
<p>And a similar example with <code>quick_exit()</code>:</p>
<div class="sourceCode" id="cb1337"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1337-1"><a href="stdlib.html#cb1337-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1337-2"><a href="stdlib.html#cb1337-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1337-3"><a href="stdlib.html#cb1337-3"></a></span>
<span id="cb1337-4"><a href="stdlib.html#cb1337-4"></a><span class="dt">void</span> exit_handler_1<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1337-5"><a href="stdlib.html#cb1337-5"></a><span class="op">{</span></span>
<span id="cb1337-6"><a href="stdlib.html#cb1337-6"></a>    printf<span class="op">(</span><span class="st">"Exit handler 1 called!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1337-7"><a href="stdlib.html#cb1337-7"></a><span class="op">}</span></span>
<span id="cb1337-8"><a href="stdlib.html#cb1337-8"></a></span>
<span id="cb1337-9"><a href="stdlib.html#cb1337-9"></a><span class="dt">void</span> exit_handler_2<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1337-10"><a href="stdlib.html#cb1337-10"></a><span class="op">{</span></span>
<span id="cb1337-11"><a href="stdlib.html#cb1337-11"></a>    printf<span class="op">(</span><span class="st">"Exit handler 2 called!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1337-12"><a href="stdlib.html#cb1337-12"></a><span class="op">}</span></span>
<span id="cb1337-13"><a href="stdlib.html#cb1337-13"></a></span>
<span id="cb1337-14"><a href="stdlib.html#cb1337-14"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1337-15"><a href="stdlib.html#cb1337-15"></a><span class="op">{</span></span>
<span id="cb1337-16"><a href="stdlib.html#cb1337-16"></a>    at_quick_exit<span class="op">(</span>exit_handler_1<span class="op">);</span></span>
<span id="cb1337-17"><a href="stdlib.html#cb1337-17"></a>    at_quick_exit<span class="op">(</span>exit_handler_2<span class="op">);</span></span>
<span id="cb1337-18"><a href="stdlib.html#cb1337-18"></a></span>
<span id="cb1337-19"><a href="stdlib.html#cb1337-19"></a>    quick_exit<span class="op">(</span><span class="dv">0</span><span class="op">);</span></span>
<span id="cb1337-20"><a href="stdlib.html#cb1337-20"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-163">See Also</h3>
<p><a href="stdlib.html#man-exit"><code>exit()</code></a>, <a href="#man-exit"><code>quick_exit()</code></a></p>
<hr>
<h2 data-number="62.14" id="man-exit"><span class="header-section-number">62.14</span> <code>exit()</code>,
<code>quick_exit()</code>, <code>_Exit()</code></h2>
<p>Exit the currently-running program</p>
<h3 class="unnumbered unlisted" id="synopsis-172">Synopsis</h3>
<div class="sourceCode" id="cb1338"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1338-1"><a href="stdlib.html#cb1338-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1338-2"><a href="stdlib.html#cb1338-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1338-3"><a href="stdlib.html#cb1338-3" aria-hidden="true" tabindex="-1"></a><span class="kw">_Noreturn</span> <span class="dt">void</span> exit<span class="op">(</span><span class="dt">int</span> status<span class="op">);</span></span>
<span id="cb1338-4"><a href="stdlib.html#cb1338-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1338-5"><a href="stdlib.html#cb1338-5" aria-hidden="true" tabindex="-1"></a><span class="kw">_Noreturn</span> <span class="dt">void</span> quick_exit<span class="op">(</span><span class="dt">int</span> status<span class="op">);</span></span>
<span id="cb1338-6"><a href="stdlib.html#cb1338-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1338-7"><a href="stdlib.html#cb1338-7" aria-hidden="true" tabindex="-1"></a><span class="kw">_Noreturn</span> <span class="dt">void</span> _Exit<span class="op">(</span><span class="dt">int</span> status<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-172">Description</h3>
<p>All these functions cause the program to exit, with various levels of
cleanup performed.</p>
<p><code>exit()</code> does the most cleanup and is the most normal
exit.</p>
<p><code>quick_exit()</code> is the second most.</p>
<p><code>_Exit()</code> unceremoniously drops everything and ragequits
on the spot.</p>
<p>Calling either of <code>exit()</code> or <code>quick_exit()</code>
causes their respective <code>atexit()</code> or
<code>at_quick_exit()</code> handlers to be called in the reverse order
in which they were registered.</p>
<p><code>exit()</code> will flush all streams and delete all temporary
files.</p>
<p><code>quick_exit()</code> or <code>_Exit()</code> might not perform
that nicety.</p>
<p><code>_Exit()</code> doesn’t call any of the at-exit handlers,
either.</p>
<p>For all functions, the exit <code>status</code> is returned to the
environment.</p>
<p>Defined exit statuses are:</p>
<table>
<thead>
<tr class="header">
<th>Status</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>EXIT_SUCCESS</code></td>
<td>Typically returned when good things happen</td>
</tr>
<tr class="even">
<td><code>0</code></td>
<td>Same as <code>EXIT_SUCCESS</code></td>
</tr>
<tr class="odd">
<td><code>EXIT_FAILURE</code></td>
<td>Oh noes! Definitely failure!</td>
</tr>
<tr class="even">
<td>Any positive value</td>
<td>Generally indicates another failure of some kind</td>
</tr>
</tbody>
</table>
<p>OS X note: <code>quick_exit()</code> is not supported.</p>
<h3 class="unnumbered unlisted" id="return-value-170">Return Value</h3>
<p>None of these functions ever return.</p>
<h3 class="unnumbered unlisted" id="example-173">Example</h3>
<div class="sourceCode" id="cb1339"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1339-1"><a href="stdlib.html#cb1339-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1339-2"><a href="stdlib.html#cb1339-2"></a></span>
<span id="cb1339-3"><a href="stdlib.html#cb1339-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1339-4"><a href="stdlib.html#cb1339-4"></a><span class="op">{</span></span>
<span id="cb1339-5"><a href="stdlib.html#cb1339-5"></a>    <span class="dt">int</span> contrived_exit_type <span class="op">=</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1339-6"><a href="stdlib.html#cb1339-6"></a></span>
<span id="cb1339-7"><a href="stdlib.html#cb1339-7"></a>    <span class="cf">switch</span><span class="op">(</span>contrived_exit_type<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1339-8"><a href="stdlib.html#cb1339-8"></a>        <span class="cf">case</span> <span class="dv">1</span><span class="op">:</span></span>
<span id="cb1339-9"><a href="stdlib.html#cb1339-9"></a>            exit<span class="op">(</span>EXIT_SUCCESS<span class="op">);</span></span>
<span id="cb1339-10"><a href="stdlib.html#cb1339-10"></a></span>
<span id="cb1339-11"><a href="stdlib.html#cb1339-11"></a>        <span class="cf">case</span> <span class="dv">2</span><span class="op">:</span></span>
<span id="cb1339-12"><a href="stdlib.html#cb1339-12"></a>            <span class="co">// Not supported in OS X</span></span>
<span id="cb1339-13"><a href="stdlib.html#cb1339-13"></a>            quick_exit<span class="op">(</span>EXIT_SUCCESS<span class="op">);</span></span>
<span id="cb1339-14"><a href="stdlib.html#cb1339-14"></a></span>
<span id="cb1339-15"><a href="stdlib.html#cb1339-15"></a>        <span class="cf">case</span> <span class="dv">3</span><span class="op">:</span></span>
<span id="cb1339-16"><a href="stdlib.html#cb1339-16"></a>            _Exit<span class="op">(</span><span class="dv">2</span><span class="op">);</span></span>
<span id="cb1339-17"><a href="stdlib.html#cb1339-17"></a>    <span class="op">}</span></span>
<span id="cb1339-18"><a href="stdlib.html#cb1339-18"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-164">See Also</h3>
<p><a href="stdlib.html#man-atexit"><code>atexit()</code></a>, <a href="#man-atexit"><code>at_quick_exit()</code></a></p>
<hr>
<h2 data-number="62.15" id="man-getenv"><span class="header-section-number">62.15</span> <code>getenv()</code></h2>
<p>Get the value of an environment variable</p>
<h3 class="unnumbered unlisted" id="synopsis-173">Synopsis</h3>
<div class="sourceCode" id="cb1340"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1340-1"><a href="stdlib.html#cb1340-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1340-2"><a href="stdlib.html#cb1340-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1340-3"><a href="stdlib.html#cb1340-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>getenv<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>name<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-173">Description</h3>
<p>The environment often provides variables that are set before the
program run that you can access at runtime.</p>
<p>Of course the exact details are system dependent, but these variables
are key/value pairs, and you can get the value by passing the key to
<code>getenv()</code> as the <code>name</code> parameter.</p>
<p>You’re not allowed to overwrite the string that’s returned.</p>
<p>This is pretty limited in the standard, but your OS often provides
better functionality. See the <a href="the-outside-environment.html#env-var">Environment
Variables</a> section for more details.</p>
<h3 class="unnumbered unlisted" id="return-value-171">Return Value</h3>
<p>Returns a pointer to the environment variable value, or
<code>NULL</code> if the variable doesn’t exist.</p>
<h3 class="unnumbered unlisted" id="example-174">Example</h3>
<div class="sourceCode" id="cb1341"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1341-1"><a href="stdlib.html#cb1341-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1341-2"><a href="stdlib.html#cb1341-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1341-3"><a href="stdlib.html#cb1341-3"></a></span>
<span id="cb1341-4"><a href="stdlib.html#cb1341-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1341-5"><a href="stdlib.html#cb1341-5"></a><span class="op">{</span></span>
<span id="cb1341-6"><a href="stdlib.html#cb1341-6"></a>    printf<span class="op">(</span><span class="st">"PATH is %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> getenv<span class="op">(</span><span class="st">"PATH"</span><span class="op">));</span></span>
<span id="cb1341-7"><a href="stdlib.html#cb1341-7"></a><span class="op">}</span></span></code></pre></div>
<p>Output (truncated in my case):</p>
<div class="sourceCode" id="cb1342"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1342-1"><a href="stdlib.html#cb1342-1" aria-hidden="true" tabindex="-1"></a>PATH is /usr/bin:/usr/local/bin:/usr/sbin:/home/beej/.cargo/bin [...]</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="62.16" id="man-system"><span class="header-section-number">62.16</span> <code>system()</code></h2>
<p>Run an external program</p>
<h3 class="unnumbered unlisted" id="synopsis-174">Synopsis</h3>
<div class="sourceCode" id="cb1343"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1343-1"><a href="stdlib.html#cb1343-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1343-2"><a href="stdlib.html#cb1343-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1343-3"><a href="stdlib.html#cb1343-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> system<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>string<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-174">Description</h3>
<p>This will run an external program and then return to the caller.</p>
<p>The manner in which it runs the program is system-defined, but
typically you can pass something to it just like you’d run on the
command line, searching the <code>PATH</code>, etc.</p>
<p>Not all systems have this capability, but you can test for it by
passing <code>NULL</code> to <code>system()</code> and seeing if it
returns 0 (no command processor is available) or non-zero (a command
processor is available! Yay!)</p>
<p>If you’re getting user input and passing it to the
<code>system()</code> call, be extremely careful to escape all special
shell characters (everything that’s not alphanumeric) with a backslash
to keep a villain from running something you don’t want them to.</p>
<h3 class="unnumbered unlisted" id="return-value-172">Return Value</h3>
<p>If <code>NULL</code> is passed, returns nonzero if a command
processor is available (i.e.&nbsp;<code>system()</code> will work at
all).</p>
<p>Otherwise returns an implementation-defined value.</p>
<h3 class="unnumbered unlisted" id="example-175">Example</h3>
<div class="sourceCode" id="cb1344"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1344-1"><a href="stdlib.html#cb1344-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1344-2"><a href="stdlib.html#cb1344-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1344-3"><a href="stdlib.html#cb1344-3"></a></span>
<span id="cb1344-4"><a href="stdlib.html#cb1344-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1344-5"><a href="stdlib.html#cb1344-5"></a><span class="op">{</span></span>
<span id="cb1344-6"><a href="stdlib.html#cb1344-6"></a>    printf<span class="op">(</span><span class="st">"Here's a directory listing:</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1344-7"><a href="stdlib.html#cb1344-7"></a></span>
<span id="cb1344-8"><a href="stdlib.html#cb1344-8"></a>    system<span class="op">(</span><span class="st">"ls -l"</span><span class="op">);</span>   <span class="co">// Run this command and return</span></span>
<span id="cb1344-9"><a href="stdlib.html#cb1344-9"></a></span>
<span id="cb1344-10"><a href="stdlib.html#cb1344-10"></a>    printf<span class="op">(</span><span class="st">"</span><span class="sc">\n</span><span class="st">All done!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1344-11"><a href="stdlib.html#cb1344-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1345"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1345-1"><a href="stdlib.html#cb1345-1" aria-hidden="true" tabindex="-1"></a>Here's a directory listing:</span>
<span id="cb1345-2"><a href="stdlib.html#cb1345-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1345-3"><a href="stdlib.html#cb1345-3" aria-hidden="true" tabindex="-1"></a>total 92</span>
<span id="cb1345-4"><a href="stdlib.html#cb1345-4" aria-hidden="true" tabindex="-1"></a>drwxr-xr-x 3 beej beej  4096 Oct 14 21:38 bin</span>
<span id="cb1345-5"><a href="stdlib.html#cb1345-5" aria-hidden="true" tabindex="-1"></a>drwxr-xr-x 2 beej beej  4096 Dec 20 20:07 examples</span>
<span id="cb1345-6"><a href="stdlib.html#cb1345-6" aria-hidden="true" tabindex="-1"></a>-rwxr-xr-x 1 beej beej 16656 Feb 23 21:49 foo</span>
<span id="cb1345-7"><a href="stdlib.html#cb1345-7" aria-hidden="true" tabindex="-1"></a>-rw-rw-rw- 1 beej beej   155 Feb 23 21:49 foo.c</span>
<span id="cb1345-8"><a href="stdlib.html#cb1345-8" aria-hidden="true" tabindex="-1"></a>-rw-r--r-- 1 beej beej  1350 Jan 27 22:11 Makefile</span>
<span id="cb1345-9"><a href="stdlib.html#cb1345-9" aria-hidden="true" tabindex="-1"></a>-rw-r--r-- 1 beej beej  4644 Jan 18 09:12 README.md</span>
<span id="cb1345-10"><a href="stdlib.html#cb1345-10" aria-hidden="true" tabindex="-1"></a>drwxr-xr-x 3 beej beej  4096 Feb 23 20:21 src</span>
<span id="cb1345-11"><a href="stdlib.html#cb1345-11" aria-hidden="true" tabindex="-1"></a>drwxr-xr-x 6 beej beej  4096 Feb 21 20:24 stage</span>
<span id="cb1345-12"><a href="stdlib.html#cb1345-12" aria-hidden="true" tabindex="-1"></a>drwxr-xr-x 2 beej beej  4096 Sep 27 20:54 translations</span>
<span id="cb1345-13"><a href="stdlib.html#cb1345-13" aria-hidden="true" tabindex="-1"></a>drwxr-xr-x 2 beej beej  4096 Sep 27 20:54 website</span>
<span id="cb1345-14"><a href="stdlib.html#cb1345-14" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1345-15"><a href="stdlib.html#cb1345-15" aria-hidden="true" tabindex="-1"></a>All done!</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="62.17" id="man-bsearch"><span class="header-section-number">62.17</span> <code>bsearch()</code></h2>
<p>Binary Search (maybe) an array of objects</p>
<h3 class="unnumbered unlisted" id="synopsis-175">Synopsis</h3>
<div class="sourceCode" id="cb1346"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1346-1"><a href="stdlib.html#cb1346-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1346-2"><a href="stdlib.html#cb1346-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1346-3"><a href="stdlib.html#cb1346-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>bsearch<span class="op">(</span><span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>key<span class="op">,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>base<span class="op">,</span></span>
<span id="cb1346-4"><a href="stdlib.html#cb1346-4" aria-hidden="true" tabindex="-1"></a>              <span class="dt">size_t</span> nmemb<span class="op">,</span> <span class="dt">size_t</span> size<span class="op">,</span></span>
<span id="cb1346-5"><a href="stdlib.html#cb1346-5" aria-hidden="true" tabindex="-1"></a>              <span class="dt">int</span> <span class="op">(*</span>compar<span class="op">)(</span><span class="dt">const</span> <span class="dt">void</span> <span class="op">*,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*));</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-175">Description</h3>
<p>This crazy-looking function searches an array for a value.</p>
<p>It probably is a binary search or some fast, efficient search. But
the spec doesn’t really say.</p>
<p>However, the array must be sorted! So binary search seems likely.</p>
<ul>
<li><code>key</code> is a pointer to the value to find.</li>
<li><code>base</code> is a pointer to the start of the array—the array
must be sorted!</li>
<li><code>nmemb</code> is the number of elements in the array.</li>
<li><code>size</code> is the <code>sizeof</code> each element in the
array.</li>
<li><code>compar</code> is a pointer to a function that will compare the
key against other values.</li>
</ul>
<p>The comparison function takes the key as the first argument and the
value to compare against as the second. It should return a negative
number if the key is less than the value, <code>0</code> if the key
equals the value, and a positive number if the key is greater than the
value.</p>
<p>This is commonly computed by taking the difference between the key
and the value to be compared. If subtraction is supported.</p>
<p>The return value from the <a href="#man-strcmp"><code>strcmp()</code></a> function can be used for
comparing strings.</p>
<p>Again, the array must be sorted according to the order of the
comparison function before running <code>bsearch()</code>. Luckily for
you, you can just call <a href="stdlib.html#man-qsort"><code>qsort()</code></a>
with the same comparison function to get this done.</p>
<p>It’s a general-purpose function—it’ll search any type of array for
anything. The catch is you have to write the comparison function.</p>
<p>And that’s not as scary as it looks. Jump down to the example</p>
<h3 class="unnumbered unlisted" id="return-value-173">Return Value</h3>
<p>The function returns a pointer to the found value, or
<code>NULL</code> if it can’t be found.</p>
<h3 class="unnumbered unlisted" id="example-176">Example</h3>
<div class="sourceCode" id="cb1347"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1347-1"><a href="stdlib.html#cb1347-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1347-2"><a href="stdlib.html#cb1347-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1347-3"><a href="stdlib.html#cb1347-3"></a></span>
<span id="cb1347-4"><a href="stdlib.html#cb1347-4"></a><span class="dt">int</span> compar<span class="op">(</span><span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>key<span class="op">,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>value<span class="op">)</span></span>
<span id="cb1347-5"><a href="stdlib.html#cb1347-5"></a><span class="op">{</span></span>
<span id="cb1347-6"><a href="stdlib.html#cb1347-6"></a>    <span class="dt">const</span> <span class="dt">int</span> <span class="op">*</span>k <span class="op">=</span> key<span class="op">,</span> <span class="op">*</span>v <span class="op">=</span> value<span class="op">;</span>  <span class="co">// Need ints, not voids</span></span>
<span id="cb1347-7"><a href="stdlib.html#cb1347-7"></a></span>
<span id="cb1347-8"><a href="stdlib.html#cb1347-8"></a>    <span class="cf">return</span> <span class="op">*</span>k <span class="op">-</span> <span class="op">*</span>v<span class="op">;</span></span>
<span id="cb1347-9"><a href="stdlib.html#cb1347-9"></a><span class="op">}</span></span>
<span id="cb1347-10"><a href="stdlib.html#cb1347-10"></a></span>
<span id="cb1347-11"><a href="stdlib.html#cb1347-11"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1347-12"><a href="stdlib.html#cb1347-12"></a><span class="op">{</span></span>
<span id="cb1347-13"><a href="stdlib.html#cb1347-13"></a>    <span class="dt">int</span> a<span class="op">[</span><span class="dv">9</span><span class="op">]</span> <span class="op">=</span> <span class="op">{</span><span class="dv">2</span><span class="op">,</span> <span class="dv">6</span><span class="op">,</span> <span class="dv">9</span><span class="op">,</span> <span class="dv">12</span><span class="op">,</span> <span class="dv">13</span><span class="op">,</span> <span class="dv">18</span><span class="op">,</span> <span class="dv">20</span><span class="op">,</span> <span class="dv">32</span><span class="op">,</span> <span class="dv">47</span><span class="op">};</span></span>
<span id="cb1347-14"><a href="stdlib.html#cb1347-14"></a></span>
<span id="cb1347-15"><a href="stdlib.html#cb1347-15"></a>    <span class="dt">int</span> <span class="op">*</span>r<span class="op">,</span> key<span class="op">;</span></span>
<span id="cb1347-16"><a href="stdlib.html#cb1347-16"></a></span>
<span id="cb1347-17"><a href="stdlib.html#cb1347-17"></a>    key <span class="op">=</span> <span class="dv">12</span><span class="op">;</span>  <span class="co">// 12 is in there</span></span>
<span id="cb1347-18"><a href="stdlib.html#cb1347-18"></a>    r <span class="op">=</span> bsearch<span class="op">(&amp;</span>key<span class="op">,</span> a<span class="op">,</span> <span class="dv">9</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">),</span> compar<span class="op">);</span></span>
<span id="cb1347-19"><a href="stdlib.html#cb1347-19"></a>    printf<span class="op">(</span><span class="st">"Found %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">*</span>r<span class="op">);</span></span>
<span id="cb1347-20"><a href="stdlib.html#cb1347-20"></a></span>
<span id="cb1347-21"><a href="stdlib.html#cb1347-21"></a>    key <span class="op">=</span> <span class="dv">30</span><span class="op">;</span>  <span class="co">// Won't find a 30</span></span>
<span id="cb1347-22"><a href="stdlib.html#cb1347-22"></a>    r <span class="op">=</span> bsearch<span class="op">(&amp;</span>key<span class="op">,</span> a<span class="op">,</span> <span class="dv">9</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">),</span> compar<span class="op">);</span></span>
<span id="cb1347-23"><a href="stdlib.html#cb1347-23"></a>    <span class="cf">if</span> <span class="op">(</span>r <span class="op">==</span> NULL<span class="op">)</span></span>
<span id="cb1347-24"><a href="stdlib.html#cb1347-24"></a>        printf<span class="op">(</span><span class="st">"Didn't find 30</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1347-25"><a href="stdlib.html#cb1347-25"></a></span>
<span id="cb1347-26"><a href="stdlib.html#cb1347-26"></a>    <span class="co">// Searching with an unnamed key, pointer to 32</span></span>
<span id="cb1347-27"><a href="stdlib.html#cb1347-27"></a>    r <span class="op">=</span> bsearch<span class="op">(&amp;(</span><span class="dt">int</span><span class="op">){</span><span class="dv">32</span><span class="op">},</span> a<span class="op">,</span> <span class="dv">9</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">),</span> compar<span class="op">);</span></span>
<span id="cb1347-28"><a href="stdlib.html#cb1347-28"></a>    printf<span class="op">(</span><span class="st">"Found %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">*</span>r<span class="op">);</span>  <span class="co">// Found it</span></span>
<span id="cb1347-29"><a href="stdlib.html#cb1347-29"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1348"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1348-1"><a href="stdlib.html#cb1348-1" aria-hidden="true" tabindex="-1"></a>Found 12</span>
<span id="cb1348-2"><a href="stdlib.html#cb1348-2" aria-hidden="true" tabindex="-1"></a>Didn't find 30</span>
<span id="cb1348-3"><a href="stdlib.html#cb1348-3" aria-hidden="true" tabindex="-1"></a>Found 32</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-165">See Also</h3>
<p><a href="stringref.html#man-strcmp"><code>strcmp()</code></a>, <a href="#man-qsort"><code>qsort()</code></a></p>
<hr>
<h2 data-number="62.18" id="man-qsort"><span class="header-section-number">62.18</span> <code>qsort()</code></h2>
<p>Quicksort (maybe) some data</p>
<h3 class="unnumbered unlisted" id="synopsis-176">Synopsis</h3>
<div class="sourceCode" id="cb1349"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1349-1"><a href="stdlib.html#cb1349-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1349-2"><a href="stdlib.html#cb1349-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1349-3"><a href="stdlib.html#cb1349-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> qsort<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>base<span class="op">,</span> <span class="dt">size_t</span> nmemb<span class="op">,</span> <span class="dt">size_t</span> size<span class="op">,</span></span>
<span id="cb1349-4"><a href="stdlib.html#cb1349-4" aria-hidden="true" tabindex="-1"></a>           <span class="dt">int</span> <span class="op">(*</span>compar<span class="op">)(</span><span class="dt">const</span> <span class="dt">void</span> <span class="op">*,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*));</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-176">Description</h3>
<p>This function will quicksort (or some other sort, probably speedy) an
array of data in-place<a href="footnotes.html#fn270" class="footnote-ref" id="fnref270" role="doc-noteref"><sup>270</sup></a>.</p>
<p>Like <code>bsearch()</code>, it’s data-agnostic. Any data for which
you can define a relative ordering can be sorted, whether
<code>int</code>s, <code>struct</code>s, or anything else.</p>
<p>Also like <code>bsearch()</code>, you have to give a comparison
function to do the actual compare.</p>
<ul>
<li><code>base</code> is a pointer to the start of the array to be
sorted.</li>
<li><code>nmemb</code> is the number of elements in the array.</li>
<li><code>size</code> is the <code>sizeof</code> each element.</li>
<li><code>compar</code> is a pointer to the comparison function.</li>
</ul>
<p>The comparison function takes pointers to two elements of the array
as arguments and compares them. It should return a negative number if
the first argument is less than the second, <code>0</code> if they are
equal, and a positive number if the first argument is greater than the
second.</p>
<p>This is commonly computed by taking the difference between the first
argument and the second. If subtraction is supported.</p>
<p>The return value from the <a href="#man-strcmp"><code>strcmp()</code></a> function can provide sort
order for strings.</p>
<p>If you have to sort a <code>struct</code>, just subtract the specific
field you want to sort by.</p>
<p>This comparison function can be used by <a href="#man-bsearch"><code>bsearch()</code></a> to do searches after the
list is sorted.</p>
<p>To reverse the sort, subtract the second argument from the first,
i.e. negate the return value from <code>compar()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-174">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-177">Example</h3>
<div class="sourceCode" id="cb1350"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1350-1"><a href="stdlib.html#cb1350-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1350-2"><a href="stdlib.html#cb1350-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1350-3"><a href="stdlib.html#cb1350-3"></a></span>
<span id="cb1350-4"><a href="stdlib.html#cb1350-4"></a><span class="dt">int</span> compar<span class="op">(</span><span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>elem0<span class="op">,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>elem1<span class="op">)</span></span>
<span id="cb1350-5"><a href="stdlib.html#cb1350-5"></a><span class="op">{</span></span>
<span id="cb1350-6"><a href="stdlib.html#cb1350-6"></a>    <span class="dt">const</span> <span class="dt">int</span> <span class="op">*</span>x <span class="op">=</span> elem0<span class="op">,</span> <span class="op">*</span>y <span class="op">=</span> elem1<span class="op">;</span>  <span class="co">// Need ints, not voids</span></span>
<span id="cb1350-7"><a href="stdlib.html#cb1350-7"></a></span>
<span id="cb1350-8"><a href="stdlib.html#cb1350-8"></a>    <span class="cf">if</span> <span class="op">(*</span>x <span class="op">&gt;</span> <span class="op">*</span>y<span class="op">)</span> <span class="cf">return</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1350-9"><a href="stdlib.html#cb1350-9"></a>    <span class="cf">if</span> <span class="op">(*</span>x <span class="op">&lt;</span> <span class="op">*</span>y<span class="op">)</span> <span class="cf">return</span> <span class="op">-</span><span class="dv">1</span><span class="op">;</span></span>
<span id="cb1350-10"><a href="stdlib.html#cb1350-10"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1350-11"><a href="stdlib.html#cb1350-11"></a><span class="op">}</span></span>
<span id="cb1350-12"><a href="stdlib.html#cb1350-12"></a></span>
<span id="cb1350-13"><a href="stdlib.html#cb1350-13"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1350-14"><a href="stdlib.html#cb1350-14"></a><span class="op">{</span></span>
<span id="cb1350-15"><a href="stdlib.html#cb1350-15"></a>    <span class="dt">int</span> a<span class="op">[</span><span class="dv">9</span><span class="op">]</span> <span class="op">=</span> <span class="op">{</span><span class="dv">14</span><span class="op">,</span> <span class="dv">2</span><span class="op">,</span> <span class="dv">3</span><span class="op">,</span> <span class="dv">17</span><span class="op">,</span> <span class="dv">10</span><span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="dv">6</span><span class="op">,</span> <span class="dv">1</span><span class="op">,</span> <span class="dv">13</span><span class="op">};</span></span>
<span id="cb1350-16"><a href="stdlib.html#cb1350-16"></a></span>
<span id="cb1350-17"><a href="stdlib.html#cb1350-17"></a>    <span class="co">// Sort the list</span></span>
<span id="cb1350-18"><a href="stdlib.html#cb1350-18"></a></span>
<span id="cb1350-19"><a href="stdlib.html#cb1350-19"></a>    qsort<span class="op">(</span>a<span class="op">,</span> <span class="dv">9</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">),</span> compar<span class="op">);</span></span>
<span id="cb1350-20"><a href="stdlib.html#cb1350-20"></a></span>
<span id="cb1350-21"><a href="stdlib.html#cb1350-21"></a>    <span class="co">// Print sorted list</span></span>
<span id="cb1350-22"><a href="stdlib.html#cb1350-22"></a></span>
<span id="cb1350-23"><a href="stdlib.html#cb1350-23"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> <span class="dv">9</span><span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1350-24"><a href="stdlib.html#cb1350-24"></a>        printf<span class="op">(</span><span class="st">"%d "</span><span class="op">,</span> a<span class="op">[</span>i<span class="op">]);</span></span>
<span id="cb1350-25"><a href="stdlib.html#cb1350-25"></a></span>
<span id="cb1350-26"><a href="stdlib.html#cb1350-26"></a>    putchar<span class="op">(</span><span class="ch">'\n'</span><span class="op">);</span></span>
<span id="cb1350-27"><a href="stdlib.html#cb1350-27"></a></span>
<span id="cb1350-28"><a href="stdlib.html#cb1350-28"></a>    <span class="co">// Use the same compar() function to binary search</span></span>
<span id="cb1350-29"><a href="stdlib.html#cb1350-29"></a>    <span class="co">// for 17 (passed in as an unnamed object)</span></span>
<span id="cb1350-30"><a href="stdlib.html#cb1350-30"></a></span>
<span id="cb1350-31"><a href="stdlib.html#cb1350-31"></a>    <span class="dt">int</span> <span class="op">*</span>r <span class="op">=</span> bsearch<span class="op">(&amp;(</span><span class="dt">int</span><span class="op">){</span><span class="dv">17</span><span class="op">},</span> a<span class="op">,</span> <span class="dv">9</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">int</span><span class="op">),</span> compar<span class="op">);</span></span>
<span id="cb1350-32"><a href="stdlib.html#cb1350-32"></a>    printf<span class="op">(</span><span class="st">"Found %d!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="op">*</span>r<span class="op">);</span></span>
<span id="cb1350-33"><a href="stdlib.html#cb1350-33"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1351"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1351-1"><a href="stdlib.html#cb1351-1" aria-hidden="true" tabindex="-1"></a>1 2 3 6 8 10 13 14 17</span>
<span id="cb1351-2"><a href="stdlib.html#cb1351-2" aria-hidden="true" tabindex="-1"></a>Found 17!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-166">See Also</h3>
<p><a href="stringref.html#man-strcmp"><code>strcmp()</code></a>, <a href="#man-bsearch"><code>bsearch()</code></a></p>
<hr>
<h2 data-number="62.19" id="man-abs"><span class="header-section-number">62.19</span> <code>abs()</code>,
<code>labs()</code>, <code>llabs()</code></h2>
<p>Compute the absolute value of an integer</p>
<h3 class="unnumbered unlisted" id="synopsis-177">Synopsis</h3>
<div class="sourceCode" id="cb1352"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1352-1"><a href="stdlib.html#cb1352-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1352-2"><a href="stdlib.html#cb1352-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1352-3"><a href="stdlib.html#cb1352-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> abs<span class="op">(</span><span class="dt">int</span> j<span class="op">);</span></span>
<span id="cb1352-4"><a href="stdlib.html#cb1352-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1352-5"><a href="stdlib.html#cb1352-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> labs<span class="op">(</span><span class="dt">long</span> <span class="dt">int</span> j<span class="op">);</span></span>
<span id="cb1352-6"><a href="stdlib.html#cb1352-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1352-7"><a href="stdlib.html#cb1352-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> llabs<span class="op">(</span><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> j<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-177">Description</h3>
<p>Compute the absolute value of <code>j</code>. If you don’t remember,
that’s how far from zero <code>j</code> is.</p>
<p>In other words, if <code>j</code> is negative, return it as a
positive. If it’s positive, return it as a positive. Always be positive.
Enjoy life.</p>
<p>If the result cannot be represented, the behavior is undefined. Be
especially aware of the upper half of unsigned numbers.</p>
<h3 class="unnumbered unlisted" id="return-value-175">Return Value</h3>
<p>Returns the absolute value of <code>j</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>j</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-178">Example</h3>
<div class="sourceCode" id="cb1353"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1353-1"><a href="stdlib.html#cb1353-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1353-2"><a href="stdlib.html#cb1353-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1353-3"><a href="stdlib.html#cb1353-3"></a></span>
<span id="cb1353-4"><a href="stdlib.html#cb1353-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1353-5"><a href="stdlib.html#cb1353-5"></a><span class="op">{</span></span>
<span id="cb1353-6"><a href="stdlib.html#cb1353-6"></a>    printf<span class="op">(</span><span class="st">"|-2| = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> abs<span class="op">(-</span><span class="dv">2</span><span class="op">));</span></span>
<span id="cb1353-7"><a href="stdlib.html#cb1353-7"></a>    printf<span class="op">(</span><span class="st">"|4|  = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> abs<span class="op">(</span><span class="dv">4</span><span class="op">));</span></span>
<span id="cb1353-8"><a href="stdlib.html#cb1353-8"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1354"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1354-1"><a href="stdlib.html#cb1354-1" aria-hidden="true" tabindex="-1"></a>|-2| = 2</span>
<span id="cb1354-2"><a href="stdlib.html#cb1354-2" aria-hidden="true" tabindex="-1"></a>|4|  = 4</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-167">See Also</h3>
<p><a href="math.html#man-fabs"><code>fabs()</code></a></p>
<hr>
<h2 data-number="62.20" id="man-div"><span class="header-section-number">62.20</span> <code>div()</code>,
<code>ldiv()</code>, <code>lldiv()</code></h2>
<p>Compute the quotient and remainder of two numbers</p>
<h3 class="unnumbered unlisted" id="synopsis-178">Synopsis</h3>
<div class="sourceCode" id="cb1355"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1355-1"><a href="stdlib.html#cb1355-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1355-2"><a href="stdlib.html#cb1355-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1355-3"><a href="stdlib.html#cb1355-3" aria-hidden="true" tabindex="-1"></a>div_t div<span class="op">(</span><span class="dt">int</span> numer<span class="op">,</span> <span class="dt">int</span> denom<span class="op">);</span></span>
<span id="cb1355-4"><a href="stdlib.html#cb1355-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1355-5"><a href="stdlib.html#cb1355-5" aria-hidden="true" tabindex="-1"></a>ldiv_t ldiv<span class="op">(</span><span class="dt">long</span> <span class="dt">int</span> numer<span class="op">,</span> <span class="dt">long</span> <span class="dt">int</span> denom<span class="op">);</span></span>
<span id="cb1355-6"><a href="stdlib.html#cb1355-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1355-7"><a href="stdlib.html#cb1355-7" aria-hidden="true" tabindex="-1"></a>lldiv_t lldiv<span class="op">(</span><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> numer<span class="op">,</span> <span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> denom<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-178">Description</h3>
<p>These functions get you the quotient and remainder of a pair of
numbers in one go.</p>
<p>They return a structure that has two fields, <code>quot</code>, and
<code>rem</code>, the types of which match types of <code>numer</code>
and <code>denom</code>. Note how each function returns a different
variant of <code>div_t</code>.</p>
<p>These <code>div_t</code> variants are equivalent to the
following:</p>
<div class="sourceCode" id="cb1356"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1356-1"><a href="stdlib.html#cb1356-1" aria-hidden="true" tabindex="-1"></a><span class="kw">typedef</span> <span class="kw">struct</span> <span class="op">{</span></span>
<span id="cb1356-2"><a href="stdlib.html#cb1356-2" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> quot<span class="op">,</span> rem<span class="op">;</span></span>
<span id="cb1356-3"><a href="stdlib.html#cb1356-3" aria-hidden="true" tabindex="-1"></a><span class="op">}</span> div_t<span class="op">;</span></span>
<span id="cb1356-4"><a href="stdlib.html#cb1356-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1356-5"><a href="stdlib.html#cb1356-5" aria-hidden="true" tabindex="-1"></a><span class="kw">typedef</span> <span class="kw">struct</span> <span class="op">{</span></span>
<span id="cb1356-6"><a href="stdlib.html#cb1356-6" aria-hidden="true" tabindex="-1"></a>    <span class="dt">long</span> <span class="dt">int</span> quot<span class="op">,</span> rem<span class="op">;</span></span>
<span id="cb1356-7"><a href="stdlib.html#cb1356-7" aria-hidden="true" tabindex="-1"></a><span class="op">}</span> ldiv_t<span class="op">;</span></span>
<span id="cb1356-8"><a href="stdlib.html#cb1356-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1356-9"><a href="stdlib.html#cb1356-9" aria-hidden="true" tabindex="-1"></a><span class="kw">typedef</span> <span class="kw">struct</span> <span class="op">{</span></span>
<span id="cb1356-10"><a href="stdlib.html#cb1356-10" aria-hidden="true" tabindex="-1"></a>    <span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> quot<span class="op">,</span> rem<span class="op">;</span></span>
<span id="cb1356-11"><a href="stdlib.html#cb1356-11" aria-hidden="true" tabindex="-1"></a><span class="op">}</span> lldiv_t<span class="op">;</span></span></code></pre></div>
<p>Why use these instead of the division operator?</p>
<p>The C99 Rationale says:</p>
<blockquote>
<p>Because C89 had implementation-defined semantics for division of
signed integers when negative operands were involved, <code>div</code>
and <code>ldiv</code>, and <code>lldiv</code> in C99, were invented to
provide well-specified semantics for signed integer division and
remainder operations. The semantics were adopted to be the same as in
Fortran. Since these functions return both the quotient and the
remainder, they also serve as a convenient way of efficiently modeling
underlying hardware that computes both results as part of the same
operation. Table 7.2 summarizes the semantics of these functions.</p>
</blockquote>
<p>Indeed, K&amp;R2 (C89) says:</p>
<blockquote>
<p>The direction of truncation for <code>/</code> and the sign of the
result for <code>%</code> are machine-dependent for negative operands
[…]</p>
</blockquote>
<p>The Rationale then goes on to spell out what the signs of the
quotient and remainder will be given the signs of a numerator and
denominator when using the <code>div()</code> functions:</p>
<table>
<thead>
<tr class="header">
<th style="text-align: center;"><code>numer</code></th>
<th style="text-align: center;"><code>denom</code></th>
<th style="text-align: center;"><code>quot</code></th>
<th style="text-align: center;"><code>rem</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
</tr>
<tr class="even">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
</tr>
<tr class="odd">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="12" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="13" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="14" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="15" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
</tr>
<tr class="even">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="16" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="17" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="18" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo></math></mjx-assistive-mml></mjx-container></span></td>
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="19" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo></math></mjx-assistive-mml></mjx-container></span></td>
</tr>
</tbody>
</table>
<h3 class="unnumbered unlisted" id="return-value-176">Return Value</h3>
<p>A <code>div_t</code>, <code>ldiv_t</code>, or <code>lldiv_t</code>
structure with the <code>quot</code> and <code>rem</code> fields loaded
with the quotient and remainder of the operation of
<code>numer/denom</code>.</p>
<h3 class="unnumbered unlisted" id="example-179">Example</h3>
<div class="sourceCode" id="cb1357"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1357-1"><a href="stdlib.html#cb1357-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1357-2"><a href="stdlib.html#cb1357-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1357-3"><a href="stdlib.html#cb1357-3"></a></span>
<span id="cb1357-4"><a href="stdlib.html#cb1357-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1357-5"><a href="stdlib.html#cb1357-5"></a><span class="op">{</span></span>
<span id="cb1357-6"><a href="stdlib.html#cb1357-6"></a>    div_t d <span class="op">=</span> div<span class="op">(</span><span class="dv">64</span><span class="op">,</span> <span class="op">-</span><span class="dv">7</span><span class="op">);</span></span>
<span id="cb1357-7"><a href="stdlib.html#cb1357-7"></a></span>
<span id="cb1357-8"><a href="stdlib.html#cb1357-8"></a>    printf<span class="op">(</span><span class="st">"64 / -7 = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> d<span class="op">.</span>quot<span class="op">);</span></span>
<span id="cb1357-9"><a href="stdlib.html#cb1357-9"></a>    printf<span class="op">(</span><span class="st">"64 %% -7 = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> d<span class="op">.</span>rem<span class="op">);</span></span>
<span id="cb1357-10"><a href="stdlib.html#cb1357-10"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1358"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1358-1"><a href="stdlib.html#cb1358-1" aria-hidden="true" tabindex="-1"></a>64 / -7 = -9</span>
<span id="cb1358-2"><a href="stdlib.html#cb1358-2" aria-hidden="true" tabindex="-1"></a>64 % -7 = 1</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-168">See Also</h3>
<p><a href="math.html#man-fmod"><code>fmod()</code></a>, <a href="#man-remainder"><code>remainder()</code></a></p>
<hr>
<h2 data-number="62.21" id="man-mblen"><span class="header-section-number">62.21</span> <code>mblen()</code></h2>
<p>Return the number of bytes in a multibyte character</p>
<h3 class="unnumbered unlisted" id="synopsis-179">Synopsis</h3>
<div class="sourceCode" id="cb1359"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1359-1"><a href="stdlib.html#cb1359-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1359-2"><a href="stdlib.html#cb1359-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1359-3"><a href="stdlib.html#cb1359-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mblen<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-179">Description</h3>
<p>If you have a multibyte character in a string, this will tell you how
many bytes long it is.</p>
<p><code>n</code> is the maximum number of bytes <code>mblen()</code>
will scan before giving up.</p>
<p>If <code>s</code> is a <code>NULL</code> pointer, tests if this
encoding has state dependency, as noted in the return value, below. It
also resets the state, if there is one.</p>
<p>The behavior of this function is influenced by the locale.</p>
<h3 class="unnumbered unlisted" id="return-value-177">Return Value</h3>
<p>Returns the number of bytes used to encode this character, or
<code>-1</code> if there is no valid multibyte character in the next
<code>n</code> bytes.</p>
<p>Or, if <code>s</code> is NULL, returns true if this encoding has
state dependency.</p>
<h3 class="unnumbered unlisted" id="example-180">Example</h3>
<p>For the example, I used my extended character set to put Unicode
characters in the source. If this doesn’t work for you, use the
<code>\uXXXX</code> escape.</p>
<div class="sourceCode" id="cb1360"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1360-1"><a href="stdlib.html#cb1360-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1360-2"><a href="stdlib.html#cb1360-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1360-3"><a href="stdlib.html#cb1360-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1360-4"><a href="stdlib.html#cb1360-4"></a></span>
<span id="cb1360-5"><a href="stdlib.html#cb1360-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1360-6"><a href="stdlib.html#cb1360-6"></a><span class="op">{</span></span>
<span id="cb1360-7"><a href="stdlib.html#cb1360-7"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1360-8"><a href="stdlib.html#cb1360-8"></a></span>
<span id="cb1360-9"><a href="stdlib.html#cb1360-9"></a>    printf<span class="op">(</span><span class="st">"State dependency: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mblen<span class="op">(</span>NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span></span>
<span id="cb1360-10"><a href="stdlib.html#cb1360-10"></a>    printf<span class="op">(</span><span class="st">"Bytes for €: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mblen<span class="op">(</span><span class="st">"€"</span><span class="op">,</span> <span class="dv">5</span><span class="op">));</span></span>
<span id="cb1360-11"><a href="stdlib.html#cb1360-11"></a>    printf<span class="op">(</span><span class="st">"Bytes for \u00e9: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mblen<span class="op">(</span><span class="st">"\u00e9"</span><span class="op">,</span> <span class="dv">5</span><span class="op">));</span>  <span class="co">// \u00e9 == é</span></span>
<span id="cb1360-12"><a href="stdlib.html#cb1360-12"></a>    printf<span class="op">(</span><span class="st">"Bytes for &amp;: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mblen<span class="op">(</span><span class="st">"&amp;"</span><span class="op">,</span> <span class="dv">5</span><span class="op">));</span></span>
<span id="cb1360-13"><a href="stdlib.html#cb1360-13"></a><span class="op">}</span></span></code></pre></div>
<p>Output (in my case, the encoding is UTF-8, but your mileage may
vary):</p>
<div class="sourceCode" id="cb1361"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1361-1"><a href="stdlib.html#cb1361-1" aria-hidden="true" tabindex="-1"></a>State dependency: 0</span>
<span id="cb1361-2"><a href="stdlib.html#cb1361-2" aria-hidden="true" tabindex="-1"></a>Bytes for €: 3</span>
<span id="cb1361-3"><a href="stdlib.html#cb1361-3" aria-hidden="true" tabindex="-1"></a>Bytes for é: 2</span>
<span id="cb1361-4"><a href="stdlib.html#cb1361-4" aria-hidden="true" tabindex="-1"></a>Bytes for &amp;: 1</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-169">See Also</h3>
<p><a href="stdlib.html#man-mbtowc"><code>mbtowc()</code></a>, <a href="#man-mbstowcs"><code>mbstowcs())</code></a>, <a href="#man-setlocale"><code>setlocale()</code></a></p>
<hr>
<h2 data-number="62.22" id="man-mbtowc"><span class="header-section-number">62.22</span> <code>mbtowc()</code></h2>
<p>Convert a multibyte character to a wide character</p>
<h3 class="unnumbered unlisted" id="synopsis-180">Synopsis</h3>
<div class="sourceCode" id="cb1362"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1362-1"><a href="stdlib.html#cb1362-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1362-2"><a href="stdlib.html#cb1362-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1362-3"><a href="stdlib.html#cb1362-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mbtowc<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> pwc<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-180">Description</h3>
<p>If you have a multibyte character, this function will convert it to a
wide character and stored at the address pointed to by <code>pwc</code>.
Up to <code>n</code> bytes of the multibyte character will be
analyzed.</p>
<p>If <code>pwc</code> is <code>NULL</code>, the resulting character
will not be stored. (Useful for just getting the return value.)</p>
<p>If <code>s</code> is a <code>NULL</code> pointer, tests if this
encoding has state dependency, as noted in the return value, below. It
also resets the state, if there is one.</p>
<p>The behavior of this function is influenced by the locale.</p>
<h3 class="unnumbered unlisted" id="return-value-178">Return Value</h3>
<p>Returns the number of bytes used in the encoded wide character, or
<code>-1</code> if there is no valid multibyte character in the next
<code>n</code> bytes.</p>
<p>Returns <code>0</code> if <code>s</code> points to the NUL
character.</p>
<p>Or, if <code>s</code> is NULL, returns true if this encoding has
state dependency.</p>
<h3 class="unnumbered unlisted" id="example-181">Example</h3>
<div class="sourceCode" id="cb1363"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1363-1"><a href="stdlib.html#cb1363-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1363-2"><a href="stdlib.html#cb1363-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1363-3"><a href="stdlib.html#cb1363-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1363-4"><a href="stdlib.html#cb1363-4"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1363-5"><a href="stdlib.html#cb1363-5"></a></span>
<span id="cb1363-6"><a href="stdlib.html#cb1363-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1363-7"><a href="stdlib.html#cb1363-7"></a><span class="op">{</span></span>
<span id="cb1363-8"><a href="stdlib.html#cb1363-8"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1363-9"><a href="stdlib.html#cb1363-9"></a></span>
<span id="cb1363-10"><a href="stdlib.html#cb1363-10"></a>    printf<span class="op">(</span><span class="st">"State dependency: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbtowc<span class="op">(</span>NULL<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span></span>
<span id="cb1363-11"><a href="stdlib.html#cb1363-11"></a></span>
<span id="cb1363-12"><a href="stdlib.html#cb1363-12"></a>    <span class="dt">wchar_t</span> wc<span class="op">;</span></span>
<span id="cb1363-13"><a href="stdlib.html#cb1363-13"></a>    <span class="dt">int</span> bytes<span class="op">;</span></span>
<span id="cb1363-14"><a href="stdlib.html#cb1363-14"></a></span>
<span id="cb1363-15"><a href="stdlib.html#cb1363-15"></a>    bytes <span class="op">=</span> mbtowc<span class="op">(&amp;</span>wc<span class="op">,</span> <span class="st">"€"</span><span class="op">,</span> <span class="dv">5</span><span class="op">);</span></span>
<span id="cb1363-16"><a href="stdlib.html#cb1363-16"></a></span>
<span id="cb1363-17"><a href="stdlib.html#cb1363-17"></a>    printf<span class="op">(</span><span class="st">"L'%lc' takes %d bytes as multibyte char '€'</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wc<span class="op">,</span> bytes<span class="op">);</span></span>
<span id="cb1363-18"><a href="stdlib.html#cb1363-18"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1364"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1364-1"><a href="stdlib.html#cb1364-1" aria-hidden="true" tabindex="-1"></a>State dependency: 0</span>
<span id="cb1364-2"><a href="stdlib.html#cb1364-2" aria-hidden="true" tabindex="-1"></a>L'€' takes 3 bytes as multibyte char '€'</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-170">See Also</h3>
<p><a href="stdlib.html#man-mblen"><code>mblen()</code></a>, <a href="#man-mbstowcs"><code>mbstowcs()</code></a>, <a href="#man-wcstombs"><code>wcstombs()</code></a>, <a href="#man-setlocale"><code>setlocale()</code></a></p>
<hr>
<h2 data-number="62.23" id="man-wctomb"><span class="header-section-number">62.23</span> <code>wctomb()</code></h2>
<p>Convert a wide character to a multibyte character</p>
<h3 class="unnumbered unlisted" id="synopsis-181">Synopsis</h3>
<div class="sourceCode" id="cb1365"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1365-1"><a href="stdlib.html#cb1365-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1365-2"><a href="stdlib.html#cb1365-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1365-3"><a href="stdlib.html#cb1365-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wctomb<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>s<span class="op">,</span> <span class="dt">wchar_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-181">Description</h3>
<p>If you have your hands on a wide character, you can use this to make
it multibyte.</p>
<p>The wide character <code>wc</code> is stored as a multibyte character
in the string pointed to by <code>s</code>. The buffer <code>s</code>
points to should be at least <code>MB_CUR_MAX</code> characters long.
Note that <code>MB_CUR_MAX</code> changes with locale.</p>
<p>If <code>wc</code> is a NUL wide character, a NUL is stored in
<code>s</code> after the bytes needed to reset the shift state (if
any).</p>
<p>If <code>s</code> is a <code>NULL</code> pointer, tests if this
encoding has state dependency, as noted in the return value, below. It
also resets the state, if there is one.</p>
<p>The behavior of this function is influenced by the locale.</p>
<h3 class="unnumbered unlisted" id="return-value-179">Return Value</h3>
<p>Returns the number of bytes used in the encoded multibyte character,
or <code>-1</code> if <code>wc</code> does not correspond to any valid
multibyte character.</p>
<p>Or, if <code>s</code> is NULL, returns true if this encoding has
state dependency.</p>
<h3 class="unnumbered unlisted" id="example-182">Example</h3>
<div class="sourceCode" id="cb1366"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1366-1"><a href="stdlib.html#cb1366-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1366-2"><a href="stdlib.html#cb1366-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1366-3"><a href="stdlib.html#cb1366-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1366-4"><a href="stdlib.html#cb1366-4"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1366-5"><a href="stdlib.html#cb1366-5"></a></span>
<span id="cb1366-6"><a href="stdlib.html#cb1366-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1366-7"><a href="stdlib.html#cb1366-7"></a><span class="op">{</span></span>
<span id="cb1366-8"><a href="stdlib.html#cb1366-8"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1366-9"><a href="stdlib.html#cb1366-9"></a></span>
<span id="cb1366-10"><a href="stdlib.html#cb1366-10"></a>    printf<span class="op">(</span><span class="st">"State dependency: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbtowc<span class="op">(</span>NULL<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span></span>
<span id="cb1366-11"><a href="stdlib.html#cb1366-11"></a></span>
<span id="cb1366-12"><a href="stdlib.html#cb1366-12"></a>    <span class="dt">int</span> bytes<span class="op">;</span></span>
<span id="cb1366-13"><a href="stdlib.html#cb1366-13"></a>    <span class="dt">char</span> mb<span class="op">[</span>MB_CUR_MAX <span class="op">+</span> <span class="dv">1</span><span class="op">];</span></span>
<span id="cb1366-14"><a href="stdlib.html#cb1366-14"></a></span>
<span id="cb1366-15"><a href="stdlib.html#cb1366-15"></a>    bytes <span class="op">=</span> wctomb<span class="op">(</span>mb<span class="op">,</span> L'€'<span class="op">);</span></span>
<span id="cb1366-16"><a href="stdlib.html#cb1366-16"></a>    mb<span class="op">[</span>bytes<span class="op">]</span> <span class="op">=</span> <span class="ch">'\0'</span><span class="op">;</span></span>
<span id="cb1366-17"><a href="stdlib.html#cb1366-17"></a></span>
<span id="cb1366-18"><a href="stdlib.html#cb1366-18"></a>    printf<span class="op">(</span><span class="st">"L'€' takes %d bytes as multibyte char '%s'</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> bytes<span class="op">,</span> mb<span class="op">);</span></span>
<span id="cb1366-19"><a href="stdlib.html#cb1366-19"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1367"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1367-1"><a href="stdlib.html#cb1367-1" aria-hidden="true" tabindex="-1"></a>State dependency: 0</span>
<span id="cb1367-2"><a href="stdlib.html#cb1367-2" aria-hidden="true" tabindex="-1"></a>L'€' takes 3 bytes as multibyte char '€'</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-171">See Also</h3>
<p><a href="stdlib.html#man-mbtowc"><code>mbtowc()</code></a>, <a href="#man-mbstowcs"><code>mbstowcs()</code></a>, <a href="#man-wcstombs"><code>wcstombs()</code></a>, <a href="#man-setlocale"><code>setlocale()</code></a></p>
<hr>
<h2 data-number="62.24" id="man-mbstowcs"><span class="header-section-number">62.24</span> <code>mbstowcs()</code></h2>
<p>Convert a multibyte string to a wide character string</p>
<h3 class="unnumbered unlisted" id="synopsis-182">Synopsis</h3>
<div class="sourceCode" id="cb1368"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1368-1"><a href="stdlib.html#cb1368-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1368-2"><a href="stdlib.html#cb1368-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1368-3"><a href="stdlib.html#cb1368-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> mbstowcs<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> pwcs<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-182">Description</h3>
<p>If you have a multibyte string (AKA a regular string), you can
convert it wto a wide character string with this function.</p>
<p>At most <code>n</code> wide characters are written to the destination
<code>pwcs</code> from the source <code>s</code>.</p>
<p>A NUL character is stored as a wide NUL character.</p>
<p>Non-portable POSIX extension: if you’re using a POSIX-complaint
library, this function allows <code>pwcs</code> to be <code>NULL</code>
if you’re only interested in the return value. Most notably, this will
give you the number of characters in a multibyte string (as opposed to
<a href="stringref.html#man-strlen"><code>strlen()</code></a> which counts the
bytes.)</p>
<h3 class="unnumbered unlisted" id="return-value-180">Return Value</h3>
<p>Returns the number of wide characters written to the destination
<code>pwcs</code>.</p>
<p>If an invalid multibyte character was found, returns
<code>(size_t)(-1)</code>.</p>
<p>If the return value is <code>n</code>, it means the result was
<em>not</em> NUL-terminated.</p>
<h3 class="unnumbered unlisted" id="example-183">Example</h3>
<p>This source uses an extended character set. If your compiler doesn’t
support it, you’ll have to replace them with <code>\u</code>
escapes.</p>
<div class="sourceCode" id="cb1369"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1369-1"><a href="stdlib.html#cb1369-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1369-2"><a href="stdlib.html#cb1369-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1369-3"><a href="stdlib.html#cb1369-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1369-4"><a href="stdlib.html#cb1369-4"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1369-5"><a href="stdlib.html#cb1369-5"></a></span>
<span id="cb1369-6"><a href="stdlib.html#cb1369-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1369-7"><a href="stdlib.html#cb1369-7"></a><span class="op">{</span></span>
<span id="cb1369-8"><a href="stdlib.html#cb1369-8"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1369-9"><a href="stdlib.html#cb1369-9"></a></span>
<span id="cb1369-10"><a href="stdlib.html#cb1369-10"></a>    <span class="dt">wchar_t</span> wcs<span class="op">[</span><span class="dv">128</span><span class="op">];</span></span>
<span id="cb1369-11"><a href="stdlib.html#cb1369-11"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"€200 for this spoon?"</span><span class="op">;</span>  <span class="co">// 20 characters</span></span>
<span id="cb1369-12"><a href="stdlib.html#cb1369-12"></a></span>
<span id="cb1369-13"><a href="stdlib.html#cb1369-13"></a>    <span class="dt">size_t</span> char_count<span class="op">,</span> byte_count<span class="op">;</span></span>
<span id="cb1369-14"><a href="stdlib.html#cb1369-14"></a></span>
<span id="cb1369-15"><a href="stdlib.html#cb1369-15"></a>    char_count <span class="op">=</span> mbstowcs<span class="op">(</span>wcs<span class="op">,</span> s<span class="op">,</span> <span class="dv">128</span><span class="op">);</span></span>
<span id="cb1369-16"><a href="stdlib.html#cb1369-16"></a>    byte_count <span class="op">=</span> strlen<span class="op">(</span>s<span class="op">);</span></span>
<span id="cb1369-17"><a href="stdlib.html#cb1369-17"></a></span>
<span id="cb1369-18"><a href="stdlib.html#cb1369-18"></a>    printf<span class="op">(</span><span class="st">"Wide string: L</span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> wcs<span class="op">);</span></span>
<span id="cb1369-19"><a href="stdlib.html#cb1369-19"></a>    printf<span class="op">(</span><span class="st">"Char count : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> char_count<span class="op">);</span>    <span class="co">// 20</span></span>
<span id="cb1369-20"><a href="stdlib.html#cb1369-20"></a>    printf<span class="op">(</span><span class="st">"Byte count : %zu</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> byte_count<span class="op">);</span>  <span class="co">// 22 on my system</span></span>
<span id="cb1369-21"><a href="stdlib.html#cb1369-21"></a></span>
<span id="cb1369-22"><a href="stdlib.html#cb1369-22"></a>    <span class="co">// POSIX Extension that allows you to pass NULL for</span></span>
<span id="cb1369-23"><a href="stdlib.html#cb1369-23"></a>    <span class="co">// the destination so you can just use the return</span></span>
<span id="cb1369-24"><a href="stdlib.html#cb1369-24"></a>    <span class="co">// value (which is the character count of the string, </span></span>
<span id="cb1369-25"><a href="stdlib.html#cb1369-25"></a>    <span class="co">// if no errors have occurred)</span></span>
<span id="cb1369-26"><a href="stdlib.html#cb1369-26"></a></span>
<span id="cb1369-27"><a href="stdlib.html#cb1369-27"></a>    s <span class="op">=</span> <span class="st">"§¶°±π€•"</span><span class="op">;</span>  <span class="co">// 7 characters</span></span>
<span id="cb1369-28"><a href="stdlib.html#cb1369-28"></a></span>
<span id="cb1369-29"><a href="stdlib.html#cb1369-29"></a>    char_count <span class="op">=</span> mbstowcs<span class="op">(</span>NULL<span class="op">,</span> s<span class="op">,</span> <span class="dv">0</span><span class="op">);</span>  <span class="co">// POSIX-only, nonportable</span></span>
<span id="cb1369-30"><a href="stdlib.html#cb1369-30"></a>    byte_count <span class="op">=</span> strlen<span class="op">(</span>s<span class="op">);</span></span>
<span id="cb1369-31"><a href="stdlib.html#cb1369-31"></a></span>
<span id="cb1369-32"><a href="stdlib.html#cb1369-32"></a>    printf<span class="op">(</span><span class="st">"Multibyte str: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span></span>
<span id="cb1369-33"><a href="stdlib.html#cb1369-33"></a>    printf<span class="op">(</span><span class="st">"Char count   : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> char_count<span class="op">);</span>  <span class="co">// 7</span></span>
<span id="cb1369-34"><a href="stdlib.html#cb1369-34"></a>    printf<span class="op">(</span><span class="st">"Byte count   : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> byte_count<span class="op">);</span>  <span class="co">// 16 on my system</span></span>
<span id="cb1369-35"><a href="stdlib.html#cb1369-35"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system (byte count will depend on your encoding):</p>
<div class="sourceCode" id="cb1370"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1370-1"><a href="stdlib.html#cb1370-1" aria-hidden="true" tabindex="-1"></a>Wide string: L"€200 for this spoon?"</span>
<span id="cb1370-2"><a href="stdlib.html#cb1370-2" aria-hidden="true" tabindex="-1"></a>Char count : 20</span>
<span id="cb1370-3"><a href="stdlib.html#cb1370-3" aria-hidden="true" tabindex="-1"></a>Byte count : 22</span>
<span id="cb1370-4"><a href="stdlib.html#cb1370-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1370-5"><a href="stdlib.html#cb1370-5" aria-hidden="true" tabindex="-1"></a>Multibyte str: "§¶°±π€•"</span>
<span id="cb1370-6"><a href="stdlib.html#cb1370-6" aria-hidden="true" tabindex="-1"></a>Char count   : 7</span>
<span id="cb1370-7"><a href="stdlib.html#cb1370-7" aria-hidden="true" tabindex="-1"></a>Byte count   : 16</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-172">See Also</h3>
<p><a href="stdlib.html#man-mblen"><code>mblen()</code></a>, <a href="#man-mbtowc"><code>mbtowc()</code></a>, <a href="#man-wcstombs"><code>wcstombs()</code></a>, <a href="#man-setlocale"><code>setlocale()</code></a></p>
<hr>
<h2 data-number="62.25" id="man-wcstombs"><span class="header-section-number">62.25</span> <code>wcstombs()</code></h2>
<p>Convert a wide character string to a multibyte string</p>
<h3 class="unnumbered unlisted" id="synopsis-183">Synopsis</h3>
<div class="sourceCode" id="cb1371"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1371-1"><a href="stdlib.html#cb1371-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1371-2"><a href="stdlib.html#cb1371-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1371-3"><a href="stdlib.html#cb1371-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcstombs<span class="op">(</span><span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> pwcs<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-183">Description</h3>
<p>If you have a wide character string and you want it as multibyte
string, this is the function for you!</p>
<p>It’ll take the wide characters pointed to by <code>pwcs</code> and
convert them to multibyte characters stored in <code>s</code>. No more
than <code>n</code> bytes will be written to <code>s</code>.</p>
<p>Non-portable POSIX extension: if you’re using a POSIX-complaint
library, this function allows <code>s</code> to be <code>NULL</code> if
you’re only interested in the return value. Most notably, this will give
you the number of bytes needed to encode the wide characters in a
multibyte string.</p>
<h3 class="unnumbered unlisted" id="return-value-181">Return Value</h3>
<p>Returns the number of bytes written to <code>s</code>, or
<code>(size_t)(-1)</code> if one of the characters can’t be encoded into
a multibyte string.</p>
<p>If the return value is <code>n</code>, it means the result was
<em>not</em> NUL-terminated.</p>
<h3 class="unnumbered unlisted" id="example-184">Example</h3>
<p>This source uses an extended character set. If your compiler doesn’t
support it, you’ll have to replace them with <code>\u</code>
escapes.</p>
<div class="sourceCode" id="cb1372"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1372-1"><a href="stdlib.html#cb1372-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1372-2"><a href="stdlib.html#cb1372-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1372-3"><a href="stdlib.html#cb1372-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1372-4"><a href="stdlib.html#cb1372-4"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1372-5"><a href="stdlib.html#cb1372-5"></a></span>
<span id="cb1372-6"><a href="stdlib.html#cb1372-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1372-7"><a href="stdlib.html#cb1372-7"></a><span class="op">{</span></span>
<span id="cb1372-8"><a href="stdlib.html#cb1372-8"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1372-9"><a href="stdlib.html#cb1372-9"></a></span>
<span id="cb1372-10"><a href="stdlib.html#cb1372-10"></a>    <span class="dt">char</span> mbs<span class="op">[</span><span class="dv">128</span><span class="op">];</span></span>
<span id="cb1372-11"><a href="stdlib.html#cb1372-11"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>wcs <span class="op">=</span> L<span class="st">"€200 for this spoon?"</span><span class="op">;</span>  <span class="co">// 20 characters</span></span>
<span id="cb1372-12"><a href="stdlib.html#cb1372-12"></a></span>
<span id="cb1372-13"><a href="stdlib.html#cb1372-13"></a>    <span class="dt">size_t</span> byte_count<span class="op">;</span></span>
<span id="cb1372-14"><a href="stdlib.html#cb1372-14"></a></span>
<span id="cb1372-15"><a href="stdlib.html#cb1372-15"></a>    byte_count <span class="op">=</span> wcstombs<span class="op">(</span>mbs<span class="op">,</span> wcs<span class="op">,</span> <span class="dv">128</span><span class="op">);</span></span>
<span id="cb1372-16"><a href="stdlib.html#cb1372-16"></a></span>
<span id="cb1372-17"><a href="stdlib.html#cb1372-17"></a>    printf<span class="op">(</span><span class="st">"Wide string: L</span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> wcs<span class="op">);</span></span>
<span id="cb1372-18"><a href="stdlib.html#cb1372-18"></a>    printf<span class="op">(</span><span class="st">"Multibyte  : </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> mbs<span class="op">);</span></span>
<span id="cb1372-19"><a href="stdlib.html#cb1372-19"></a>    printf<span class="op">(</span><span class="st">"Byte count : %zu</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> byte_count<span class="op">);</span>  <span class="co">// 22 on my system</span></span>
<span id="cb1372-20"><a href="stdlib.html#cb1372-20"></a></span>
<span id="cb1372-21"><a href="stdlib.html#cb1372-21"></a>    <span class="co">// POSIX Extension that allows you to pass NULL for</span></span>
<span id="cb1372-22"><a href="stdlib.html#cb1372-22"></a>    <span class="co">// the destination so you can just use the return</span></span>
<span id="cb1372-23"><a href="stdlib.html#cb1372-23"></a>    <span class="co">// value (which is the character count of the string, </span></span>
<span id="cb1372-24"><a href="stdlib.html#cb1372-24"></a>    <span class="co">// if no errors have occurred)</span></span>
<span id="cb1372-25"><a href="stdlib.html#cb1372-25"></a></span>
<span id="cb1372-26"><a href="stdlib.html#cb1372-26"></a>    wcs <span class="op">=</span> L<span class="st">"§¶°±π€•"</span><span class="op">;</span>  <span class="co">// 7 characters</span></span>
<span id="cb1372-27"><a href="stdlib.html#cb1372-27"></a></span>
<span id="cb1372-28"><a href="stdlib.html#cb1372-28"></a>    byte_count <span class="op">=</span> wcstombs<span class="op">(</span>NULL<span class="op">,</span> wcs<span class="op">,</span> <span class="dv">0</span><span class="op">);</span>  <span class="co">// POSIX-only, nonportable</span></span>
<span id="cb1372-29"><a href="stdlib.html#cb1372-29"></a></span>
<span id="cb1372-30"><a href="stdlib.html#cb1372-30"></a>    printf<span class="op">(</span><span class="st">"Wide string: L</span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> wcs<span class="op">);</span></span>
<span id="cb1372-31"><a href="stdlib.html#cb1372-31"></a>    printf<span class="op">(</span><span class="st">"Byte count : %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> byte_count<span class="op">);</span>  <span class="co">// 16 on my system</span></span>
<span id="cb1372-32"><a href="stdlib.html#cb1372-32"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system (byte count will depend on your encoding):</p>
<div class="sourceCode" id="cb1373"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1373-1"><a href="stdlib.html#cb1373-1" aria-hidden="true" tabindex="-1"></a>Wide string: L"€200 for this spoon?"</span>
<span id="cb1373-2"><a href="stdlib.html#cb1373-2" aria-hidden="true" tabindex="-1"></a>Multibyte  : "€200 for this spoon?"</span>
<span id="cb1373-3"><a href="stdlib.html#cb1373-3" aria-hidden="true" tabindex="-1"></a>Byte count : 22</span>
<span id="cb1373-4"><a href="stdlib.html#cb1373-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1373-5"><a href="stdlib.html#cb1373-5" aria-hidden="true" tabindex="-1"></a>Wide string: L"§¶°±π€•"</span>
<span id="cb1373-6"><a href="stdlib.html#cb1373-6" aria-hidden="true" tabindex="-1"></a>Byte count : 16</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-173">See Also</h3>
<p><a href="stdlib.html#man-mblen"><code>mblen()</code></a>, <a href="#man-wctomb"><code>wctomb()</code></a>, <a href="#man-mbstowcs"><code>mbstowcs()</code></a>, <a href="#man-setlocale"><code>setlocale()</code></a></p>


</body>