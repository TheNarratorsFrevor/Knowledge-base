<body>

<hr>
<h1 data-number="68" id="uchar"><span class="header-section-number">68</span> <code>&lt;uchar.h&gt;</code>
Unicode utility functions</h1>
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
<td><a href="uchar.html#man-c16rtomb"><code>c16rtomb()</code></a></td>
<td>Convert a <code>char16_t</code> to a multibyte character</td>
</tr>
<tr class="even">
<td><a href="uchar.html#man-c16rtomb"><code>c32rtomb()</code></a></td>
<td>Convert a <code>char32_t</code> to a multibyte character</td>
</tr>
<tr class="odd">
<td><a href="uchar.html#man-mbrtoc16"><code>mbrtoc16()</code></a></td>
<td>Convert a multibyte character to a <code>char16_t</code></td>
</tr>
<tr class="even">
<td><a href="uchar.html#man-mbrtoc16"><code>mbrtoc32()</code></a></td>
<td>Convert a multibyte character to a <code>char32_t</code></td>
</tr>
</tbody>
</table>
<p>These functions are <em>restartable</em>, meaning multiple threads
can safely call them at once. They handle this by having their own
conversion state variable (of type <code>mbstate_t</code>) per call.</p>
<h2 data-number="68.1" id="types"><span class="header-section-number">68.1</span> Types</h2>
<p>This header file defines four types.</p>
<table>
<colgroup>
<col style="width: 21%">
<col style="width: 78%">
</colgroup>
<thead>
<tr class="header">
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>char16_t</code></td>
<td>Type to hold 16-bit characters</td>
</tr>
<tr class="even">
<td><code>char32_t</code></td>
<td>Type to hold 32-bit characters</td>
</tr>
<tr class="odd">
<td><code>mbstate_t</code></td>
<td>Holds the conversion state for restartable funcitons (also defined
in <a href="wchar.html"><code>&lt;wchar.h&gt;</code></a>)</td>
</tr>
<tr class="even">
<td><code>size_t</code></td>
<td>To hold various counts (also defined in <a href="#stddef"><code>&lt;stddef.h&gt;</code></a>)</td>
</tr>
</tbody>
</table>
<p>String literals for the character types are <code>u</code> for
<code>char16_t</code> and <code>U</code> for <code>char32_t</code>.</p>
<div class="sourceCode" id="cb1527"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1527-1"><a href="uchar.html#cb1527-1" aria-hidden="true" tabindex="-1"></a>char16_t <span class="op">*</span>str1 <span class="op">=</span> u<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb1527-2"><a href="uchar.html#cb1527-2" aria-hidden="true" tabindex="-1"></a>char32_t <span class="op">*</span>str2 <span class="op">=</span> U<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb1527-3"><a href="uchar.html#cb1527-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1527-4"><a href="uchar.html#cb1527-4" aria-hidden="true" tabindex="-1"></a>char16_t <span class="op">*</span>chr1 <span class="op">=</span> u<span class="ch">'A'</span><span class="op">;</span></span>
<span id="cb1527-5"><a href="uchar.html#cb1527-5" aria-hidden="true" tabindex="-1"></a>char32_t <span class="op">*</span>chr2 <span class="op">=</span> U<span class="ch">'B'</span><span class="op">;</span></span></code></pre></div>
<p>Note that <code>char16_t</code> and <code>char32_t</code>
<em>might</em> contain Unicode. Or not. If <code>__STDC_UTF_16__</code>
or <code>__STDC_UTF_32__</code> is defined as <code>1</code>, then
<code>char16_t</code> and <code>char32_t</code> use Unicode,
respectively. Otherwise they don’t and the actual value stored depend on
the locale. And if you’re not using Unicode, you have my
commiserations.</p>
<h2 data-number="68.2" id="os-x-issue"><span class="header-section-number">68.2</span> OS X issue</h2>
<p>This header file doesn’t exist on OS X—bummer. If you just want the
types, you can:</p>
<div class="sourceCode" id="cb1528"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1528-1"><a href="uchar.html#cb1528-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdint.h&gt;</span></span>
<span id="cb1528-2"><a href="uchar.html#cb1528-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1528-3"><a href="uchar.html#cb1528-3" aria-hidden="true" tabindex="-1"></a><span class="kw">typedef</span> <span class="dt">int_least16_t</span> char16_t<span class="op">;</span></span>
<span id="cb1528-4"><a href="uchar.html#cb1528-4" aria-hidden="true" tabindex="-1"></a><span class="kw">typedef</span> <span class="dt">int_least32_t</span> char32_t<span class="op">;</span></span></code></pre></div>
<p>But if you also want the functions, that’s all on you.</p>
<hr>
<h2 data-number="68.3" id="man-mbrtoc16"><span class="header-section-number">68.3</span> <code>mbrtoc16()</code>
<code>mbrtoc32()</code></h2>
<p>Convert a multibyte character to a <code>char16_t</code> or
<code>char32_t</code> restartably</p>
<h3 class="unnumbered unlisted" id="synopsis-233">Synopsis</h3>
<div class="sourceCode" id="cb1529"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1529-1"><a href="uchar.html#cb1529-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;uchar.h&gt;</span></span>
<span id="cb1529-2"><a href="uchar.html#cb1529-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1529-3"><a href="uchar.html#cb1529-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> mbrtoc16<span class="op">(</span>char16_t <span class="op">*</span> <span class="dt">restrict</span> pc16<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">,</span></span>
<span id="cb1529-4"><a href="uchar.html#cb1529-4" aria-hidden="true" tabindex="-1"></a>                mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span>
<span id="cb1529-5"><a href="uchar.html#cb1529-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1529-6"><a href="uchar.html#cb1529-6" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> mbrtoc32<span class="op">(</span>char32_t <span class="op">*</span> <span class="dt">restrict</span> pc32<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">,</span></span>
<span id="cb1529-7"><a href="uchar.html#cb1529-7" aria-hidden="true" tabindex="-1"></a>                mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-233">Description</h3>
<p>Given a source string <code>s</code> and a destination buffer
<code>pc16</code> (or <code>pc32</code> for <code>mbrtoc32()</code>),
convert the first character of the source to <code>char16_t</code>s (or
<code>char32_t</code>s for <code>mbrtoc32()</code>).</p>
<p>Basically you have a regular character and you want it as
<code>char16_t</code> or <code>char32_t</code>. Use these functions to
do it. Note that only one character is converted no matter how many
characters in <code>s</code>.</p>
<p>As the functions scan <code>s</code>, you don’t want them to overrun
the end. So you pass in <code>n</code> as the maximum number of bytes to
inspect. The functions will quit after that many bytes or when they have
a complete multibyte character, whichever comes first.</p>
<p>Since they’re restartable, pass in a conversion state variable for
the functions to do their work.</p>
<p>And the result will be placed in <code>pc16</code> (or
<code>pc32</code> for <code>mbrtoc32()</code>).</p>
<h3 class="unnumbered unlisted" id="return-value-231">Return Value</h3>
<p>When successful this function returns a number between <code>1</code>
and <code>n</code> inclusive representing the number of bytes that made
up the multibyte character.</p>
<p>Or, also in the success category, they can return <code>0</code> if
the source character is the NUL character (value <code>0</code>).</p>
<p>When not entirely successful, they can return a variety of codes.
These are all of type <code>size_t</code>, but negative values cast to
that type.</p>
<table>
<colgroup>
<col style="width: 21%">
<col style="width: 78%">
</colgroup>
<thead>
<tr class="header">
<th>Return Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>(size_t)(-1)</code></td>
<td>Encoding error—this isn’t a valid sequence of bytes.
<code>errno</code> is set to <code>EILSEQ</code>.</td>
</tr>
<tr class="even">
<td><code>(size_t)(-2)</code></td>
<td><code>n</code> bytes were examined and were a <em>partial</em> valid
character, but not a complete one.</td>
</tr>
<tr class="odd">
<td><code>(size_t)(-3)</code></td>
<td>A subsequent value of a character that can’t be represented as a
single value. See below.</td>
</tr>
</tbody>
</table>
<p>Case <code>(size_t)(-3)</code> is an odd one. Basically there are
some characters that can’t be represented with 16 bits and so can’t be
stored in a <code>char16_t</code>. These characters are store in
something called (in the Unicode world) <em>surrogate pairs</em>. That
is, there are <em>two</em> 16-bit values back to back that represent a
larger Unicode value.</p>
<p>For example, if you want to read the Unicode character
<code>\U0001fbc5</code> (which is a <a href="https://en.wikipedia.org/wiki/Symbols_for_Legacy_Computing">stick
figure</a><a href="footnotes.html#fn283" class="footnote-ref" id="fnref283" role="doc-noteref"><sup>283</sup></a>—I’m just not putting it in the
text because my font doesn’t render it) that’s more than 16 bits. But
each call to <code>mbrtoc16()</code> only returns a single
<code>char16_t</code>!</p>
<p>So subsequent calls to <code>mbrtoc16()</code> resolves the
<em>next</em> value in the surrogate pair and returns
<code>(size_t)(-3)</code> to let you know this has happened.</p>
<p>You can also pass <code>NULL</code> for <code>pc16</code> or
<code>pc32</code>. This will cause no result to be stored, but you can
use it if you’re only interested in the return value from the
functions.</p>
<p>Finally, if you pass <code>NULL</code> for <code>s</code>, the call
is equivalent to:</p>
<div class="sourceCode" id="cb1530"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1530-1"><a href="uchar.html#cb1530-1" aria-hidden="true" tabindex="-1"></a>mbrtoc16<span class="op">(</span>NULL<span class="op">,</span> <span class="st">""</span><span class="op">,</span> <span class="dv">1</span><span class="op">,</span> ps<span class="op">)</span></span></code></pre></div>
<p>Since the character is a NUL in that case, this has the effect of
setting the state in <code>ps</code> to the initial conversion
state.</p>
<h3 class="unnumbered unlisted" id="example-235">Example</h3>
<p>Normal use case example where we get the first two character values
from the multibyte string <code>"€Zillion"</code>:</p>
<div class="sourceCode" id="cb1531"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1531-1"><a href="uchar.html#cb1531-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;uchar.h&gt;</span></span>
<span id="cb1531-2"><a href="uchar.html#cb1531-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// for printf()</span></span>
<span id="cb1531-3"><a href="uchar.html#cb1531-3" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// for setlocale()</span></span>
<span id="cb1531-4"><a href="uchar.html#cb1531-4" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// for memset()</span></span>
<span id="cb1531-5"><a href="uchar.html#cb1531-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1531-6"><a href="uchar.html#cb1531-6" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1531-7"><a href="uchar.html#cb1531-7" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1531-8"><a href="uchar.html#cb1531-8" aria-hidden="true" tabindex="-1"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"\u20acZillion"</span><span class="op">;</span>  <span class="co">// 20ac is "€"</span></span>
<span id="cb1531-9"><a href="uchar.html#cb1531-9" aria-hidden="true" tabindex="-1"></a>    char16_t pc16<span class="op">;</span></span>
<span id="cb1531-10"><a href="uchar.html#cb1531-10" aria-hidden="true" tabindex="-1"></a>    <span class="dt">size_t</span> r<span class="op">;</span></span>
<span id="cb1531-11"><a href="uchar.html#cb1531-11" aria-hidden="true" tabindex="-1"></a>    mbstate_t mbs<span class="op">;</span></span>
<span id="cb1531-12"><a href="uchar.html#cb1531-12" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1531-13"><a href="uchar.html#cb1531-13" aria-hidden="true" tabindex="-1"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1531-14"><a href="uchar.html#cb1531-14" aria-hidden="true" tabindex="-1"></a>    memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span></span>
<span id="cb1531-15"><a href="uchar.html#cb1531-15" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1531-16"><a href="uchar.html#cb1531-16" aria-hidden="true" tabindex="-1"></a>    <span class="co">// Examine the next 8 bytes to see if there's a character in there</span></span>
<span id="cb1531-17"><a href="uchar.html#cb1531-17" aria-hidden="true" tabindex="-1"></a>    r <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>pc16<span class="op">,</span> s<span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1531-18"><a href="uchar.html#cb1531-18" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1531-19"><a href="uchar.html#cb1531-19" aria-hidden="true" tabindex="-1"></a>    printf<span class="op">(</span><span class="st">"%zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>     <span class="co">// Prints a value &gt;= 1 (3 in UTF-8 locale)</span></span>
<span id="cb1531-20"><a href="uchar.html#cb1531-20" aria-hidden="true" tabindex="-1"></a>    printf<span class="op">(</span><span class="st">"%#x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pc16<span class="op">);</span>  <span class="co">// Prints 0x20ac for "€"</span></span>
<span id="cb1531-21"><a href="uchar.html#cb1531-21" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1531-22"><a href="uchar.html#cb1531-22" aria-hidden="true" tabindex="-1"></a>    s <span class="op">+=</span> r<span class="op">;</span>  <span class="co">// Move to next character</span></span>
<span id="cb1531-23"><a href="uchar.html#cb1531-23" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1531-24"><a href="uchar.html#cb1531-24" aria-hidden="true" tabindex="-1"></a>    <span class="co">// Examine the next 8 bytes to see if there's a character in there</span></span>
<span id="cb1531-25"><a href="uchar.html#cb1531-25" aria-hidden="true" tabindex="-1"></a>    r <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>pc16<span class="op">,</span> s<span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1531-26"><a href="uchar.html#cb1531-26" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1531-27"><a href="uchar.html#cb1531-27" aria-hidden="true" tabindex="-1"></a>    printf<span class="op">(</span><span class="st">"%zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>     <span class="co">// Prints 1</span></span>
<span id="cb1531-28"><a href="uchar.html#cb1531-28" aria-hidden="true" tabindex="-1"></a>    printf<span class="op">(</span><span class="st">"%#x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pc16<span class="op">);</span>  <span class="co">// Prints 0x5a for "Z"</span></span>
<span id="cb1531-29"><a href="uchar.html#cb1531-29" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span></code></pre></div>
<p>Example with a surrogate pair. In this case we read plenty to get the
entire character, but the result must be stored in two
<code>char16_t</code>s, requiring two calls to get them both.</p>
<div class="sourceCode" id="cb1532"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1532-1"><a href="uchar.html#cb1532-1"></a><span class="pp">#include </span><span class="im">&lt;uchar.h&gt;</span></span>
<span id="cb1532-2"><a href="uchar.html#cb1532-2"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// for printf()</span></span>
<span id="cb1532-3"><a href="uchar.html#cb1532-3"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// for memset()</span></span>
<span id="cb1532-4"><a href="uchar.html#cb1532-4"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// for setlocale()</span></span>
<span id="cb1532-5"><a href="uchar.html#cb1532-5"></a></span>
<span id="cb1532-6"><a href="uchar.html#cb1532-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1532-7"><a href="uchar.html#cb1532-7"></a><span class="op">{</span></span>
<span id="cb1532-8"><a href="uchar.html#cb1532-8"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"\U0001fbc5*"</span><span class="op">;</span>   <span class="co">// Stick figure glyph, more than 16 bits</span></span>
<span id="cb1532-9"><a href="uchar.html#cb1532-9"></a>    char16_t pc16<span class="op">;</span></span>
<span id="cb1532-10"><a href="uchar.html#cb1532-10"></a>    mbstate_t mbs<span class="op">;</span></span>
<span id="cb1532-11"><a href="uchar.html#cb1532-11"></a>    <span class="dt">size_t</span> r<span class="op">;</span></span>
<span id="cb1532-12"><a href="uchar.html#cb1532-12"></a></span>
<span id="cb1532-13"><a href="uchar.html#cb1532-13"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1532-14"><a href="uchar.html#cb1532-14"></a>    memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span></span>
<span id="cb1532-15"><a href="uchar.html#cb1532-15"></a></span>
<span id="cb1532-16"><a href="uchar.html#cb1532-16"></a>    r <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>pc16<span class="op">,</span> s<span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1532-17"><a href="uchar.html#cb1532-17"></a></span>
<span id="cb1532-18"><a href="uchar.html#cb1532-18"></a>    printf<span class="op">(</span><span class="st">"%zd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>     <span class="co">// r is 4 bytes in UTF-8 locale</span></span>
<span id="cb1532-19"><a href="uchar.html#cb1532-19"></a>    printf<span class="op">(</span><span class="st">"%#x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pc16<span class="op">);</span>  <span class="co">// First value of surrogate pair</span></span>
<span id="cb1532-20"><a href="uchar.html#cb1532-20"></a></span>
<span id="cb1532-21"><a href="uchar.html#cb1532-21"></a>    s <span class="op">+=</span> r<span class="op">;</span>  <span class="co">// Move to next character</span></span>
<span id="cb1532-22"><a href="uchar.html#cb1532-22"></a></span>
<span id="cb1532-23"><a href="uchar.html#cb1532-23"></a>    r <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>pc16<span class="op">,</span> s<span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1532-24"><a href="uchar.html#cb1532-24"></a></span>
<span id="cb1532-25"><a href="uchar.html#cb1532-25"></a>    printf<span class="op">(</span><span class="st">"%zd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>     <span class="co">// r is (size_t)(-3) here to indicate...</span></span>
<span id="cb1532-26"><a href="uchar.html#cb1532-26"></a>    printf<span class="op">(</span><span class="st">"%#x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pc16<span class="op">);</span>  <span class="co">// ...Second value of surrogate pair</span></span>
<span id="cb1532-27"><a href="uchar.html#cb1532-27"></a></span>
<span id="cb1532-28"><a href="uchar.html#cb1532-28"></a>    <span class="co">// Since r is -3, it means we're still processing the same</span></span>
<span id="cb1532-29"><a href="uchar.html#cb1532-29"></a>    <span class="co">// character, so DON'T move to the next character this time</span></span>
<span id="cb1532-30"><a href="uchar.html#cb1532-30"></a>    <span class="co">//s += r;  // Commented out</span></span>
<span id="cb1532-31"><a href="uchar.html#cb1532-31"></a></span>
<span id="cb1532-32"><a href="uchar.html#cb1532-32"></a>    r <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>pc16<span class="op">,</span> s<span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1532-33"><a href="uchar.html#cb1532-33"></a></span>
<span id="cb1532-34"><a href="uchar.html#cb1532-34"></a>    printf<span class="op">(</span><span class="st">"%zd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>     <span class="co">// 1 byte for "*"</span></span>
<span id="cb1532-35"><a href="uchar.html#cb1532-35"></a>    printf<span class="op">(</span><span class="st">"%#x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pc16<span class="op">);</span>  <span class="co">// 0x2a for "*"</span></span>
<span id="cb1532-36"><a href="uchar.html#cb1532-36"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system, indicating the first character is represented by
the pair <code>(0xd83e, 0xdfc5)</code> and the second character is
represented by <code>0x2a</code>:</p>
<div class="sourceCode" id="cb1533"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1533-1"><a href="uchar.html#cb1533-1" aria-hidden="true" tabindex="-1"></a>4</span>
<span id="cb1533-2"><a href="uchar.html#cb1533-2" aria-hidden="true" tabindex="-1"></a>0xd83e</span>
<span id="cb1533-3"><a href="uchar.html#cb1533-3" aria-hidden="true" tabindex="-1"></a>-3</span>
<span id="cb1533-4"><a href="uchar.html#cb1533-4" aria-hidden="true" tabindex="-1"></a>0xdfc5</span>
<span id="cb1533-5"><a href="uchar.html#cb1533-5" aria-hidden="true" tabindex="-1"></a>1</span>
<span id="cb1533-6"><a href="uchar.html#cb1533-6" aria-hidden="true" tabindex="-1"></a>0x2a</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-221">See Also</h3>
<p><a href="uchar.html#man-c16rtomb"><code>c16rtomb()</code></a>, <a href="#man-c16rtomb"><code>c32rtomb()</code></a></p>
<hr>
<h2 data-number="68.4" id="man-c16rtomb"><span class="header-section-number">68.4</span> <code>c16rtomb()</code>
<code>c32rtomb()</code></h2>
<p>Convert a <code>char16_t</code> or <code>char32_t</code> to a
multibyte character restartably</p>
<h3 class="unnumbered unlisted" id="synopsis-234">Synopsis</h3>
<div class="sourceCode" id="cb1534"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1534-1"><a href="uchar.html#cb1534-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;uchar.h&gt;</span></span>
<span id="cb1534-2"><a href="uchar.html#cb1534-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1534-3"><a href="uchar.html#cb1534-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> c16rtomb<span class="op">(</span><span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> char16_t c16<span class="op">,</span> mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span>
<span id="cb1534-4"><a href="uchar.html#cb1534-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1534-5"><a href="uchar.html#cb1534-5" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> c32rtomb<span class="op">(</span><span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> char32_t c32<span class="op">,</span> mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-234">Description</h3>
<p>If you have a character in a <code>char16_t</code> or
<code>char32_t</code>, use these functions to convert them into a
multibyte character.</p>
<p>These functions figure out how many bytes are needed for the
multibyte character in the current locale and stores them in the buffer
pointed to by <code>s</code>.</p>
<p>But how big to make that buffer? Luckily there is a macro to help: it
needs be no larger than <code>MB_CUR_MAX</code>.</p>
<p>As a special case, if <code>s</code> is <code>NULL</code>, it’s the
same as calling</p>
<div class="sourceCode" id="cb1535"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1535-1"><a href="uchar.html#cb1535-1" aria-hidden="true" tabindex="-1"></a>c16rtomb<span class="op">(</span>buf<span class="op">,</span> L<span class="ch">'\0'</span><span class="op">,</span> ps<span class="op">);</span>  <span class="co">// or...</span></span>
<span id="cb1535-2"><a href="uchar.html#cb1535-2" aria-hidden="true" tabindex="-1"></a>c32rtomb<span class="op">(</span>buf<span class="op">,</span> L<span class="ch">'\0'</span><span class="op">,</span> ps<span class="op">);</span></span></code></pre></div>
<p>where <code>buf</code> is a buffer maintained by the system that you
don’t have access to.</p>
<p>This has the effect of setting the <code>ps</code> state to the
initial state.</p>
<p>Finally for surrogate pairs (where the character has been split into
two <code>char16_t</code>s), you call this once with the first of the
pair—at this point, the function will return <code>0</code>. Then you
call it again with the second of the pair, and the function will return
the number of bytes and store the result in the array
<code>s</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-232">Return Value</h3>
<p>Returns the number of bytes stored in the array pointed to by
<code>s</code>.</p>
<p>Returns 0 if processing is not yet complete for the current
character, as in the case of surrogate pairs.</p>
<p>If there is an encoding error, the functions return
<code>(size_t)(-1)</code> and <code>errno</code> is set to
<code>EILSEQ</code>.</p>
<h3 class="unnumbered unlisted" id="example-236">Example</h3>
<div class="sourceCode" id="cb1536"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1536-1"><a href="uchar.html#cb1536-1"></a><span class="pp">#include </span><span class="im">&lt;uchar.h&gt;</span></span>
<span id="cb1536-2"><a href="uchar.html#cb1536-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span><span class="pp">  </span><span class="co">// for MB_CUR_MAX</span></span>
<span id="cb1536-3"><a href="uchar.html#cb1536-3"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// for printf()</span></span>
<span id="cb1536-4"><a href="uchar.html#cb1536-4"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// for memset()</span></span>
<span id="cb1536-5"><a href="uchar.html#cb1536-5"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// for setlocale()</span></span>
<span id="cb1536-6"><a href="uchar.html#cb1536-6"></a></span>
<span id="cb1536-7"><a href="uchar.html#cb1536-7"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1536-8"><a href="uchar.html#cb1536-8"></a><span class="op">{</span></span>
<span id="cb1536-9"><a href="uchar.html#cb1536-9"></a>    char16_t c16 <span class="op">=</span> <span class="bn">0x20ac</span><span class="op">;</span>  <span class="co">// Unicode for Euro symbol</span></span>
<span id="cb1536-10"><a href="uchar.html#cb1536-10"></a>    <span class="dt">char</span> dest<span class="op">[</span>MB_CUR_MAX<span class="op">];</span></span>
<span id="cb1536-11"><a href="uchar.html#cb1536-11"></a>    <span class="dt">size_t</span> r<span class="op">;</span></span>
<span id="cb1536-12"><a href="uchar.html#cb1536-12"></a>    mbstate_t mbs<span class="op">;</span></span>
<span id="cb1536-13"><a href="uchar.html#cb1536-13"></a></span>
<span id="cb1536-14"><a href="uchar.html#cb1536-14"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1536-15"><a href="uchar.html#cb1536-15"></a>    memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span>  <span class="co">// Reset conversion state</span></span>
<span id="cb1536-16"><a href="uchar.html#cb1536-16"></a></span>
<span id="cb1536-17"><a href="uchar.html#cb1536-17"></a>    <span class="co">// Convert</span></span>
<span id="cb1536-18"><a href="uchar.html#cb1536-18"></a>    r <span class="op">=</span> c16rtomb<span class="op">(</span>dest<span class="op">,</span> c16<span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1536-19"><a href="uchar.html#cb1536-19"></a></span>
<span id="cb1536-20"><a href="uchar.html#cb1536-20"></a>    printf<span class="op">(</span><span class="st">"r == %zd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>  <span class="co">// r == 3 on my system</span></span>
<span id="cb1536-21"><a href="uchar.html#cb1536-21"></a></span>
<span id="cb1536-22"><a href="uchar.html#cb1536-22"></a>    <span class="co">// And this should print a Euro symbol</span></span>
<span id="cb1536-23"><a href="uchar.html#cb1536-23"></a>    printf<span class="op">(</span><span class="st">"dest == </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span></span>
<span id="cb1536-24"><a href="uchar.html#cb1536-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1537"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1537-1"><a href="uchar.html#cb1537-1" aria-hidden="true" tabindex="-1"></a>r == 3</span>
<span id="cb1537-2"><a href="uchar.html#cb1537-2" aria-hidden="true" tabindex="-1"></a>dest == "€"</span></code></pre></div>
<p>This is a more complex example that converts a large-valued character
in a multibyte string into a surrogate pair (as in the
<code>mbrtoc16()</code> example, above) and then converts it back again
into a multibyte string to print.</p>
<div class="sourceCode" id="cb1538"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1538-1"><a href="uchar.html#cb1538-1"></a><span class="pp">#include </span><span class="im">&lt;uchar.h&gt;</span></span>
<span id="cb1538-2"><a href="uchar.html#cb1538-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span><span class="pp">  </span><span class="co">// for MB_CUR_MAX</span></span>
<span id="cb1538-3"><a href="uchar.html#cb1538-3"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// for printf()</span></span>
<span id="cb1538-4"><a href="uchar.html#cb1538-4"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// for memset()</span></span>
<span id="cb1538-5"><a href="uchar.html#cb1538-5"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// for setlocale()</span></span>
<span id="cb1538-6"><a href="uchar.html#cb1538-6"></a></span>
<span id="cb1538-7"><a href="uchar.html#cb1538-7"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1538-8"><a href="uchar.html#cb1538-8"></a><span class="op">{</span></span>
<span id="cb1538-9"><a href="uchar.html#cb1538-9"></a>    <span class="dt">char</span> <span class="op">*</span>src <span class="op">=</span> <span class="st">"\U0001fbc5*"</span><span class="op">;</span>   <span class="co">// Stick figure glyph, more than 16 bits</span></span>
<span id="cb1538-10"><a href="uchar.html#cb1538-10"></a>    <span class="dt">char</span> dest<span class="op">[</span>MB_CUR_MAX<span class="op">];</span></span>
<span id="cb1538-11"><a href="uchar.html#cb1538-11"></a>    char16_t surrogate0<span class="op">,</span> surrogate1<span class="op">;</span></span>
<span id="cb1538-12"><a href="uchar.html#cb1538-12"></a>    mbstate_t mbs<span class="op">;</span></span>
<span id="cb1538-13"><a href="uchar.html#cb1538-13"></a>    <span class="dt">size_t</span> r<span class="op">;</span></span>
<span id="cb1538-14"><a href="uchar.html#cb1538-14"></a></span>
<span id="cb1538-15"><a href="uchar.html#cb1538-15"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1538-16"><a href="uchar.html#cb1538-16"></a>    memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span>  <span class="co">// Reset conversion state</span></span>
<span id="cb1538-17"><a href="uchar.html#cb1538-17"></a></span>
<span id="cb1538-18"><a href="uchar.html#cb1538-18"></a>    <span class="co">// Get first surrogate character</span></span>
<span id="cb1538-19"><a href="uchar.html#cb1538-19"></a>    r <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>surrogate0<span class="op">,</span> src<span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1538-20"><a href="uchar.html#cb1538-20"></a></span>
<span id="cb1538-21"><a href="uchar.html#cb1538-21"></a>    <span class="co">// Get next surrogate character</span></span>
<span id="cb1538-22"><a href="uchar.html#cb1538-22"></a>    src <span class="op">+=</span> r<span class="op">;</span>  <span class="co">// Move to next character</span></span>
<span id="cb1538-23"><a href="uchar.html#cb1538-23"></a>    r <span class="op">=</span> mbrtoc16<span class="op">(&amp;</span>surrogate1<span class="op">,</span> src<span class="op">,</span> <span class="dv">8</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1538-24"><a href="uchar.html#cb1538-24"></a></span>
<span id="cb1538-25"><a href="uchar.html#cb1538-25"></a>    printf<span class="op">(</span><span class="st">"Surrogate pair: %#x, %#x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> surrogate0<span class="op">,</span> surrogate1<span class="op">);</span></span>
<span id="cb1538-26"><a href="uchar.html#cb1538-26"></a></span>
<span id="cb1538-27"><a href="uchar.html#cb1538-27"></a>    <span class="co">// Now reverse it</span></span>
<span id="cb1538-28"><a href="uchar.html#cb1538-28"></a>    memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span>  <span class="co">// Reset conversion state</span></span>
<span id="cb1538-29"><a href="uchar.html#cb1538-29"></a></span>
<span id="cb1538-30"><a href="uchar.html#cb1538-30"></a>    <span class="co">// Process first surrogate character</span></span>
<span id="cb1538-31"><a href="uchar.html#cb1538-31"></a>    r <span class="op">=</span> c16rtomb<span class="op">(</span>dest<span class="op">,</span> surrogate0<span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1538-32"><a href="uchar.html#cb1538-32"></a></span>
<span id="cb1538-33"><a href="uchar.html#cb1538-33"></a>    <span class="co">// r should be 0 at this point, because the character hasn't been</span></span>
<span id="cb1538-34"><a href="uchar.html#cb1538-34"></a>    <span class="co">// processed yet. And dest won't have anything useful... yet!</span></span>
<span id="cb1538-35"><a href="uchar.html#cb1538-35"></a>    printf<span class="op">(</span><span class="st">"r == %zd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>   <span class="co">// r == 0</span></span>
<span id="cb1538-36"><a href="uchar.html#cb1538-36"></a></span>
<span id="cb1538-37"><a href="uchar.html#cb1538-37"></a>    <span class="co">// Process second surrogate character</span></span>
<span id="cb1538-38"><a href="uchar.html#cb1538-38"></a>    r <span class="op">=</span> c16rtomb<span class="op">(</span>dest<span class="op">,</span> surrogate1<span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb1538-39"><a href="uchar.html#cb1538-39"></a></span>
<span id="cb1538-40"><a href="uchar.html#cb1538-40"></a>    <span class="co">// Now we should be in business. r should have the number of</span></span>
<span id="cb1538-41"><a href="uchar.html#cb1538-41"></a>    <span class="co">// bytes, and dest should hold the character.</span></span>
<span id="cb1538-42"><a href="uchar.html#cb1538-42"></a>    printf<span class="op">(</span><span class="st">"r == %zd</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r<span class="op">);</span>  <span class="co">// r == 4 on my system</span></span>
<span id="cb1538-43"><a href="uchar.html#cb1538-43"></a></span>
<span id="cb1538-44"><a href="uchar.html#cb1538-44"></a>    <span class="co">// And this should print a stick figure, if your font supports it</span></span>
<span id="cb1538-45"><a href="uchar.html#cb1538-45"></a>    printf<span class="op">(</span><span class="st">"dest == </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span></span>
<span id="cb1538-46"><a href="uchar.html#cb1538-46"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-222">See Also</h3>
<p><a href="uchar.html#man-mbrtoc16"><code>mbrtoc16()</code></a>, <a href="#man-mbrtoc16"><code>mbrtoc32()</code></a></p>


</body>