<body>

<hr>
<h1 data-number="50" id="limits"><span class="header-section-number">50</span> <code>&lt;limits.h&gt;</code>
Numeric Limits</h1>
<p>Important note: the “minimum magnitude” in the table below is the
minimum allowed by the spec. It’s very likely that the values on your
bad-ass system exceed those, below.</p>
<table>
<colgroup>
<col style="width: 13%">
<col style="width: 26%">
<col style="width: 60%">
</colgroup>
<thead>
<tr class="header">
<th>Macro</th>
<th>Minimum Magnitude</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>CHAR_BIT</code></td>
<td><code>8</code></td>
<td>Number of bits in a byte</td>
</tr>
<tr class="even">
<td><code>SCHAR_MIN</code></td>
<td><code>-127</code></td>
<td>Minimum value of a <code>signed char</code></td>
</tr>
<tr class="odd">
<td><code>SCHAR_MAX</code></td>
<td><code>127</code></td>
<td>Maximum value of a <code>signed char</code></td>
</tr>
<tr class="even">
<td><code>UCHAR_MAX</code></td>
<td><code>255</code></td>
<td>Maximum value of an <code>unsigned char</code><a href="footnotes.html#fn226" class="footnote-ref" id="fnref226" role="doc-noteref"><sup>226</sup></a></td>
</tr>
<tr class="odd">
<td><code>CHAR_MIN</code></td>
<td><code>0</code> or <code>SCHAR_MIN</code></td>
<td>More detail below</td>
</tr>
<tr class="even">
<td><code>CHAR_MAX</code></td>
<td><code>SCHAR_MAX</code> or <code>UCHAR_MAX</code></td>
<td>More detail below</td>
</tr>
<tr class="odd">
<td><code>MB_LEN_MAX</code></td>
<td><code>1</code></td>
<td>Maximum number of bytes in a multibyte character on any locale</td>
</tr>
<tr class="even">
<td><code>SHRT_MIN</code></td>
<td><code>-32767</code></td>
<td>Minimum value of a <code>short</code></td>
</tr>
<tr class="odd">
<td><code>SHRT_MAX</code></td>
<td><code>32767</code></td>
<td>Maximum value of a <code>short</code></td>
</tr>
<tr class="even">
<td><code>USHRT_MAX</code></td>
<td><code>65535</code></td>
<td>Maximum value of an <code>unsigned short</code></td>
</tr>
<tr class="odd">
<td><code>INT_MIN</code></td>
<td><code>-32767</code></td>
<td>Minimum vale of an <code>int</code></td>
</tr>
<tr class="even">
<td><code>INT_MAX</code></td>
<td><code>32767</code></td>
<td>Maximum value of an <code>int</code></td>
</tr>
<tr class="odd">
<td><code>UINT_MAX</code></td>
<td><code>65535</code></td>
<td>Maximum value of an <code>unsigned int</code></td>
</tr>
<tr class="even">
<td><code>LONG_MIN</code></td>
<td><code>-2147483647</code></td>
<td>Minimum value of a <code>long</code></td>
</tr>
<tr class="odd">
<td><code>LONG_MAX</code></td>
<td><code>2147483647</code></td>
<td>Maximum value of a <code>long</code></td>
</tr>
<tr class="even">
<td><code>ULONG_MAX</code></td>
<td><code>4294967295</code></td>
<td>Maximum value of an <code>unsigned long</code></td>
</tr>
<tr class="odd">
<td><code>LLONG_MIN</code></td>
<td><code>-9223372036854775807</code></td>
<td>Minimum value of a <code>long long</code></td>
</tr>
<tr class="even">
<td><code>LLONG_MAX</code></td>
<td><code>9223372036854775807</code></td>
<td>Maximum value of a <code>long long</code></td>
</tr>
<tr class="odd">
<td><code>ULLONG_MAX</code></td>
<td><code>18446744073709551615</code></td>
<td>Maximum value of an <code>unsigned long long</code></td>
</tr>
</tbody>
</table>
<h2 data-number="50.1" id="char_min-and-char_max"><span class="header-section-number">50.1</span> <code>CHAR_MIN</code> and
<code>CHAR_MAX</code></h2>
<p>When it comes to the <code>CHAR_MIN</code> and <code>CHAR_MAX</code>
macros, it all depends on if your <code>char</code> type is signed or
unsigned by default. Remember that C leaves that up to the
implementation? No? Well, it does.</p>
<p>So if it’s signed, the values of <code>CHAR_MIN</code> and
<code>CHAR_MAX</code> are the same as <code>SCHAR_MIN</code> and
<code>SCHAR_MAX</code>.</p>
<p>And if it’s unsigned, the values of <code>CHAR_MIN</code> and
<code>CHAR_MAX</code> are the same as <code>0</code> and
<code>UCHAR_MAX</code>.</p>
<p>Side benefit: you can tell at runtime if the system has signed or
unsigned chars by checking to see if <code>CHAR_MIN</code> is
<code>0</code>.</p>
<div class="sourceCode" id="cb958"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb958-1"><a href="limits.html#cb958-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb958-2"><a href="limits.html#cb958-2"></a><span class="pp">#include </span><span class="im">&lt;limits.h&gt;</span></span>
<span id="cb958-3"><a href="limits.html#cb958-3"></a></span>
<span id="cb958-4"><a href="limits.html#cb958-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb958-5"><a href="limits.html#cb958-5"></a><span class="op">{</span></span>
<span id="cb958-6"><a href="limits.html#cb958-6"></a>    printf<span class="op">(</span><span class="st">"chars are %ssigned</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> CHAR_MIN <span class="op">==</span> <span class="dv">0</span><span class="op">?</span> <span class="st">"un"</span><span class="op">:</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb958-7"><a href="limits.html#cb958-7"></a><span class="op">}</span></span></code></pre></div>
<p>On my system, <code>char</code>s are signed.</p>
<h2 data-number="50.2" id="choosing-the-correct-type"><span class="header-section-number">50.2</span> Choosing the Correct Type</h2>
<p>If you want to be super portable, choose a type you know will be at
least as big as you need by the table, above.</p>
<p>That said, a lot of code, for better or (likely) worse, assumes
<code>int</code>s are 32-bits, when in actuality it’s only guaranteed to
be 16.</p>
<p>If you need a guaranteed bit size, check out the
<code>int_leastN_t</code> types in <a href="#stdint"><code>&lt;stdint.h&gt;</code></a>.</p>
<h2 data-number="50.3" id="whither-twos-complement"><span class="header-section-number">50.3</span> Whither Two’s Complement?</h2>
<p>If you were looking closely and have <em>a priori</em> knowledge of
the matter, you might have thought I erred in the minimum values of the
macros, above.</p>
<p>“<code>short</code> goes from <code>32767</code> to
<code>-32767</code>? Shouldn’t it go to <code>-32768?</code>”</p>
<p>No, I have it right. The spec list the minimum magnitudes for those
macros, and some old-timey systems might have used a different encoding
for their signed values that could only go that far.</p>
<p>Virtually every modern system uses <a href="https://en.wikipedia.org/wiki/Two%27s_complement">Two’s
Complement</a><a href="footnotes.html#fn227" class="footnote-ref" id="fnref227" role="doc-noteref"><sup>227</sup></a> for signed numbers, and those
would go from <code>32767</code> to <code>-32768</code> for a
<code>short</code>. Your system probably does, too.</p>
<h2 data-number="50.4" id="demo-program"><span class="header-section-number">50.4</span> Demo Program</h2>
<p>Here’s a program to print out the values of the macros:</p>
<div class="sourceCode" id="cb959"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb959-1"><a href="limits.html#cb959-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb959-2"><a href="limits.html#cb959-2"></a><span class="pp">#include </span><span class="im">&lt;limits.h&gt;</span></span>
<span id="cb959-3"><a href="limits.html#cb959-3"></a></span>
<span id="cb959-4"><a href="limits.html#cb959-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb959-5"><a href="limits.html#cb959-5"></a><span class="op">{</span></span>
<span id="cb959-6"><a href="limits.html#cb959-6"></a>    printf<span class="op">(</span><span class="st">"CHAR_BIT = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> CHAR_BIT<span class="op">);</span></span>
<span id="cb959-7"><a href="limits.html#cb959-7"></a>    printf<span class="op">(</span><span class="st">"SCHAR_MIN = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> SCHAR_MIN<span class="op">);</span></span>
<span id="cb959-8"><a href="limits.html#cb959-8"></a>    printf<span class="op">(</span><span class="st">"SCHAR_MAX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> SCHAR_MAX<span class="op">);</span></span>
<span id="cb959-9"><a href="limits.html#cb959-9"></a>    printf<span class="op">(</span><span class="st">"UCHAR_MAX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> UCHAR_MAX<span class="op">);</span></span>
<span id="cb959-10"><a href="limits.html#cb959-10"></a>    printf<span class="op">(</span><span class="st">"CHAR_MIN = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> CHAR_MIN<span class="op">);</span></span>
<span id="cb959-11"><a href="limits.html#cb959-11"></a>    printf<span class="op">(</span><span class="st">"CHAR_MAX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> CHAR_MAX<span class="op">);</span></span>
<span id="cb959-12"><a href="limits.html#cb959-12"></a>    printf<span class="op">(</span><span class="st">"MB_LEN_MAX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> MB_LEN_MAX<span class="op">);</span></span>
<span id="cb959-13"><a href="limits.html#cb959-13"></a>    printf<span class="op">(</span><span class="st">"SHRT_MIN = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> SHRT_MIN<span class="op">);</span></span>
<span id="cb959-14"><a href="limits.html#cb959-14"></a>    printf<span class="op">(</span><span class="st">"SHRT_MAX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> SHRT_MAX<span class="op">);</span></span>
<span id="cb959-15"><a href="limits.html#cb959-15"></a>    printf<span class="op">(</span><span class="st">"USHRT_MAX = %u</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> USHRT_MAX<span class="op">);</span></span>
<span id="cb959-16"><a href="limits.html#cb959-16"></a>    printf<span class="op">(</span><span class="st">"INT_MIN = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> INT_MIN<span class="op">);</span></span>
<span id="cb959-17"><a href="limits.html#cb959-17"></a>    printf<span class="op">(</span><span class="st">"INT_MAX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> INT_MAX<span class="op">);</span></span>
<span id="cb959-18"><a href="limits.html#cb959-18"></a>    printf<span class="op">(</span><span class="st">"UINT_MAX = %u</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> UINT_MAX<span class="op">);</span></span>
<span id="cb959-19"><a href="limits.html#cb959-19"></a>    printf<span class="op">(</span><span class="st">"LONG_MIN = %ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LONG_MIN<span class="op">);</span></span>
<span id="cb959-20"><a href="limits.html#cb959-20"></a>    printf<span class="op">(</span><span class="st">"LONG_MAX = %ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LONG_MAX<span class="op">);</span></span>
<span id="cb959-21"><a href="limits.html#cb959-21"></a>    printf<span class="op">(</span><span class="st">"ULONG_MAX = %lu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ULONG_MAX<span class="op">);</span></span>
<span id="cb959-22"><a href="limits.html#cb959-22"></a>    printf<span class="op">(</span><span class="st">"LLONG_MIN = %lld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LLONG_MIN<span class="op">);</span></span>
<span id="cb959-23"><a href="limits.html#cb959-23"></a>    printf<span class="op">(</span><span class="st">"LLONG_MAX = %lld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LLONG_MAX<span class="op">);</span></span>
<span id="cb959-24"><a href="limits.html#cb959-24"></a>    printf<span class="op">(</span><span class="st">"ULLONG_MAX = %llu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ULLONG_MAX<span class="op">);</span></span>
<span id="cb959-25"><a href="limits.html#cb959-25"></a><span class="op">}</span></span></code></pre></div>
<p>On my 64-bit Intel system with clang, this outputs:</p>
<div class="sourceCode" id="cb960"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb960-1"><a href="limits.html#cb960-1" aria-hidden="true" tabindex="-1"></a>CHAR_BIT = 8</span>
<span id="cb960-2"><a href="limits.html#cb960-2" aria-hidden="true" tabindex="-1"></a>SCHAR_MIN = -128</span>
<span id="cb960-3"><a href="limits.html#cb960-3" aria-hidden="true" tabindex="-1"></a>SCHAR_MAX = 127</span>
<span id="cb960-4"><a href="limits.html#cb960-4" aria-hidden="true" tabindex="-1"></a>UCHAR_MAX = 255</span>
<span id="cb960-5"><a href="limits.html#cb960-5" aria-hidden="true" tabindex="-1"></a>CHAR_MIN = -128</span>
<span id="cb960-6"><a href="limits.html#cb960-6" aria-hidden="true" tabindex="-1"></a>CHAR_MAX = 127</span>
<span id="cb960-7"><a href="limits.html#cb960-7" aria-hidden="true" tabindex="-1"></a>MB_LEN_MAX = 6</span>
<span id="cb960-8"><a href="limits.html#cb960-8" aria-hidden="true" tabindex="-1"></a>SHRT_MIN = -32768</span>
<span id="cb960-9"><a href="limits.html#cb960-9" aria-hidden="true" tabindex="-1"></a>SHRT_MAX = 32767</span>
<span id="cb960-10"><a href="limits.html#cb960-10" aria-hidden="true" tabindex="-1"></a>USHRT_MAX = 65535</span>
<span id="cb960-11"><a href="limits.html#cb960-11" aria-hidden="true" tabindex="-1"></a>INT_MIN = -2147483648</span>
<span id="cb960-12"><a href="limits.html#cb960-12" aria-hidden="true" tabindex="-1"></a>INT_MAX = 2147483647</span>
<span id="cb960-13"><a href="limits.html#cb960-13" aria-hidden="true" tabindex="-1"></a>UINT_MAX = 4294967295</span>
<span id="cb960-14"><a href="limits.html#cb960-14" aria-hidden="true" tabindex="-1"></a>LONG_MIN = -9223372036854775808</span>
<span id="cb960-15"><a href="limits.html#cb960-15" aria-hidden="true" tabindex="-1"></a>LONG_MAX = 9223372036854775807</span>
<span id="cb960-16"><a href="limits.html#cb960-16" aria-hidden="true" tabindex="-1"></a>ULONG_MAX = 18446744073709551615</span>
<span id="cb960-17"><a href="limits.html#cb960-17" aria-hidden="true" tabindex="-1"></a>LLONG_MIN = -9223372036854775808</span>
<span id="cb960-18"><a href="limits.html#cb960-18" aria-hidden="true" tabindex="-1"></a>LLONG_MAX = 9223372036854775807</span>
<span id="cb960-19"><a href="limits.html#cb960-19" aria-hidden="true" tabindex="-1"></a>ULLONG_MAX = 18446744073709551615</span></code></pre></div>
<p>Looks like my system probably uses two’s-complement encoding for
signed numbers, my <code>char</code>s are signed, and my
<code>int</code>s are 32-bit.</p>


</body>