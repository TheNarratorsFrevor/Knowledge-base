<body>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="complex.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="errno.html">Next»</a></div>
<hr>
<h1 data-number="44" id="ctype"><span class="header-section-number">44</span> <code>&lt;ctype.h&gt;</code>
Character Classification and Conversion</h1>
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
<td><a href="ctype.html#man-isalnum"><code>isalnum()</code></a></td>
<td>Tests if a character is alphabetic or is a digit</td>
</tr>
<tr class="even">
<td><a href="ctype.html#man-isalpha"><code>isalpha()</code></a></td>
<td>Returns true if a character is alphabetic</td>
</tr>
<tr class="odd">
<td><a href="ctype.html#man-isblank"><code>isblank()</code></a></td>
<td>Tests if a character is word-separating whitespace</td>
</tr>
<tr class="even">
<td><a href="ctype.html#man-iscntrl"><code>iscntrl()</code></a></td>
<td>Test if a character is a control character</td>
</tr>
<tr class="odd">
<td><a href="ctype.html#man-isdigit"><code>isdigit()</code></a></td>
<td>Tests if a character is a digit</td>
</tr>
<tr class="even">
<td><a href="ctype.html#man-isgraph"><code>isgraph()</code></a></td>
<td>Tests if the character is printable and not a space</td>
</tr>
<tr class="odd">
<td><a href="ctype.html#man-islower"><code>islower()</code></a></td>
<td>Tests if a character is lowercase</td>
</tr>
<tr class="even">
<td><a href="ctype.html#man-isprint"><code>isprint()</code></a></td>
<td>Tests if a character is printable</td>
</tr>
<tr class="odd">
<td><a href="ctype.html#man-ispunct"><code>ispunct()</code></a></td>
<td>Test if a character is punctuation</td>
</tr>
<tr class="even">
<td><a href="ctype.html#man-isspace"><code>isspace()</code></a></td>
<td>Test if a character is whitespace</td>
</tr>
<tr class="odd">
<td><a href="ctype.html#man-isupper"><code>isupper()</code></a></td>
<td>Tests if a character is uppercase</td>
</tr>
<tr class="even">
<td><a href="ctype.html#man-isxdigit"><code>isxdigit()</code></a></td>
<td>Tests if a character is a hexadecimal digit</td>
</tr>
<tr class="odd">
<td><a href="ctype.html#man-tolower"><code>tolower()</code></a></td>
<td>Convert a letter to lowercase</td>
</tr>
<tr class="even">
<td><a href="ctype.html#man-toupper"><code>toupper()</code></a></td>
<td>Convert a letter to uppercase</td>
</tr>
</tbody>
</table>
<p>This collection of macros is good for testing characters to see if
they’re of a certain class, such as alphabetic, numeric, control
characters, etc.</p>
<p>Surprisingly, they take <code>int</code> arguments instead of some
kind of <code>char</code>. This is so you can feed <code>EOF</code> in
for convenience if you have an integer representation of that. If not
<code>EOF</code>, the value passed in has to be representable in an
<code>unsigned char</code>. Otherwise it’s (dun dun DUUNNNN) undefined
behavior. So you can forget about passing in your UTF-8 multibyte
characters.</p>
<p>You can portably avoid this undefined behavior by casting the
arguments to these functions to <code>(unsigned char)</code>. This is
irksome and ugly, admittedly. The values in the <span id="src-exec-charset">basic character set</span> are all safe to use
since they’re positive values that fit into an
<code>unsigned char</code>.</p>
<p>Also, the behavior of these functions varies based on locale.</p>
<p>In many of the pages in this section, I give some examples. These are
from the “C” locale, and might vary if you’ve set a different
locale.</p>
<p>Note that wide characters have their own set of classification
functions, so don’t try to use these on <code>wchar_t</code>s. Or
<em>else</em>!</p>
<hr>
<h2 data-number="44.1" id="man-isalnum"><span class="header-section-number">44.1</span> <code>isalnum()</code></h2>
<p>Tests if a character is alphabetic or is a digit</p>
<h3 class="unnumbered unlisted" id="synopsis-25">Synopsis</h3>
<div class="sourceCode" id="cb874"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb874-1"><a href="ctype.html#cb874-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb874-2"><a href="ctype.html#cb874-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb874-3"><a href="ctype.html#cb874-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isalnum<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-25">Description</h3>
<p>Tests if a character is alphabetic (<code>A</code>-<code>Z</code> or
<code>a</code>-<code>z</code>) or a digit
(<code>0</code>-<code>9</code>).</p>
<p>Is equivalent to:</p>
<div class="sourceCode" id="cb875"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb875-1"><a href="ctype.html#cb875-1" aria-hidden="true" tabindex="-1"></a>isalpha<span class="op">(</span>c<span class="op">)</span> <span class="op">||</span> isdigit<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-25">Return Value</h3>
<p>Returns true if a character is alphabetic
(<code>A</code>-<code>Z</code> or <code>a</code>-<code>z</code>) or a
digit (<code>0</code>-<code>9</code>).</p>
<h3 class="unnumbered unlisted" id="example-25">Example</h3>
<div class="sourceCode" id="cb876"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb876-1"><a href="ctype.html#cb876-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb876-2"><a href="ctype.html#cb876-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb876-3"><a href="ctype.html#cb876-3"></a></span>
<span id="cb876-4"><a href="ctype.html#cb876-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb876-5"><a href="ctype.html#cb876-5"></a><span class="op">{</span></span>
<span id="cb876-6"><a href="ctype.html#cb876-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb876-7"><a href="ctype.html#cb876-7"></a>    <span class="co">//                      v</span></span>
<span id="cb876-8"><a href="ctype.html#cb876-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalnum<span class="op">(</span><span class="ch">'a'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb876-9"><a href="ctype.html#cb876-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalnum<span class="op">(</span><span class="ch">'B'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb876-10"><a href="ctype.html#cb876-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalnum<span class="op">(</span><span class="ch">'5'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb876-11"><a href="ctype.html#cb876-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalnum<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb876-12"><a href="ctype.html#cb876-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-22">See Also</h3>
<p><a href="ctype.html#man-isalpha"><code>isalpha()</code></a>, <a href="#man-isdigit"><code>isdigit()</code></a></p>
<hr>
<h2 data-number="44.2" id="man-isalpha"><span class="header-section-number">44.2</span> <code>isalpha()</code></h2>
<p>Returns true if a character is alphabetic</p>
<h3 class="unnumbered unlisted" id="synopsis-26">Synopsis</h3>
<div class="sourceCode" id="cb877"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb877-1"><a href="ctype.html#cb877-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb877-2"><a href="ctype.html#cb877-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb877-3"><a href="ctype.html#cb877-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isalpha<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-26">Description</h3>
<p>Returns true for alphabetic characters (<code>A</code>-<code>Z</code>
or <code>a</code>-<code>z</code>).</p>
<p>Technically (and in the “C” locale) equivalent to:</p>
<div class="sourceCode" id="cb878"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb878-1"><a href="ctype.html#cb878-1" aria-hidden="true" tabindex="-1"></a>isupper<span class="op">(</span>c<span class="op">)</span> <span class="op">||</span> islower<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<p>Extra super technically, because I know you’re dying for this to be
extra unnecessarily complex, it can also include some locale-specific
characters for which this is true:</p>
<div class="sourceCode" id="cb879"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb879-1"><a href="ctype.html#cb879-1" aria-hidden="true" tabindex="-1"></a><span class="op">!</span>iscntrl<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isdigit<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>ispunct<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isspace<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<p>and this is true:</p>
<div class="sourceCode" id="cb880"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb880-1"><a href="ctype.html#cb880-1" aria-hidden="true" tabindex="-1"></a>isupper<span class="op">(</span>c<span class="op">)</span> <span class="op">||</span> islower<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-26">Return Value</h3>
<p>Returns true for alphabetic characters (<code>A</code>-<code>Z</code>
or <code>a</code>-<code>z</code>).</p>
<p>Or for any of the other crazy stuff in the description, above.</p>
<h3 class="unnumbered unlisted" id="example-26">Example</h3>
<div class="sourceCode" id="cb881"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb881-1"><a href="ctype.html#cb881-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb881-2"><a href="ctype.html#cb881-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb881-3"><a href="ctype.html#cb881-3"></a></span>
<span id="cb881-4"><a href="ctype.html#cb881-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb881-5"><a href="ctype.html#cb881-5"></a><span class="op">{</span></span>
<span id="cb881-6"><a href="ctype.html#cb881-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb881-7"><a href="ctype.html#cb881-7"></a>    <span class="co">//                      v</span></span>
<span id="cb881-8"><a href="ctype.html#cb881-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalpha<span class="op">(</span><span class="ch">'a'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb881-9"><a href="ctype.html#cb881-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalpha<span class="op">(</span><span class="ch">'B'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb881-10"><a href="ctype.html#cb881-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalpha<span class="op">(</span><span class="ch">'5'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb881-11"><a href="ctype.html#cb881-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isalpha<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb881-12"><a href="ctype.html#cb881-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-23">See Also</h3>
<p><a href="ctype.html#man-isalnum"><code>isalnum()</code></a></p>
<hr>
<h2 data-number="44.3" id="man-isblank"><span class="header-section-number">44.3</span> <code>isblank()</code></h2>
<p>Tests if a character is word-separating whitespace</p>
<h3 class="unnumbered unlisted" id="synopsis-27">Synopsis</h3>
<div class="sourceCode" id="cb882"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb882-1"><a href="ctype.html#cb882-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb882-2"><a href="ctype.html#cb882-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb882-3"><a href="ctype.html#cb882-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isblank<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-27">Description</h3>
<p>True if the character is a whitespace character used to separate
words in a single line.</p>
<p>For example, space (<code>' '</code>) or horizontal tab
(<code>'\t'</code>). Other locales might define other blank
characters.</p>
<h3 class="unnumbered unlisted" id="return-value-27">Return Value</h3>
<p>Returns true if the character is a whitespace character used to
separate words in a single line.</p>
<h3 class="unnumbered unlisted" id="example-27">Example</h3>
<div class="sourceCode" id="cb883"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb883-1"><a href="ctype.html#cb883-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb883-2"><a href="ctype.html#cb883-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb883-3"><a href="ctype.html#cb883-3"></a></span>
<span id="cb883-4"><a href="ctype.html#cb883-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb883-5"><a href="ctype.html#cb883-5"></a><span class="op">{</span></span>
<span id="cb883-6"><a href="ctype.html#cb883-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb883-7"><a href="ctype.html#cb883-7"></a>    <span class="co">//                      v</span></span>
<span id="cb883-8"><a href="ctype.html#cb883-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isblank<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb883-9"><a href="ctype.html#cb883-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isblank<span class="op">(</span><span class="ch">'\t'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb883-10"><a href="ctype.html#cb883-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isblank<span class="op">(</span><span class="ch">'\n'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb883-11"><a href="ctype.html#cb883-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isblank<span class="op">(</span><span class="ch">'a'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb883-12"><a href="ctype.html#cb883-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isblank<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb883-13"><a href="ctype.html#cb883-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-24">See Also</h3>
<p><a href="ctype.html#man-isspace"><code>isspace()</code></a></p>
<hr>
<h2 data-number="44.4" id="man-iscntrl"><span class="header-section-number">44.4</span> <code>iscntrl()</code></h2>
<p>Test if a character is a control character</p>
<h3 class="unnumbered unlisted" id="synopsis-28">Synopsis</h3>
<div class="sourceCode" id="cb884"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb884-1"><a href="ctype.html#cb884-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb884-2"><a href="ctype.html#cb884-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb884-3"><a href="ctype.html#cb884-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iscntrl<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-28">Description</h3>
<p>A <em>control character</em> is a locale-specific non-printing
character.</p>
<p>For the “C” locale, this means control characters are in the range
0x00 to 0x1F (the character right before SPACE) and 0x7F (the DEL
character).</p>
<p>Basically if it’s not an ASCII (or Unicode less than 128) printable
character, it’s a control character in the “C” locale.</p>
<h3 class="unnumbered unlisted" id="return-value-28">Return Value</h3>
<p>Returns true if <code>c</code> is a control character.</p>
<h3 class="unnumbered unlisted" id="example-28">Example</h3>
<div class="sourceCode" id="cb885"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb885-1"><a href="ctype.html#cb885-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb885-2"><a href="ctype.html#cb885-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb885-3"><a href="ctype.html#cb885-3"></a></span>
<span id="cb885-4"><a href="ctype.html#cb885-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb885-5"><a href="ctype.html#cb885-5"></a><span class="op">{</span></span>
<span id="cb885-6"><a href="ctype.html#cb885-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb885-7"><a href="ctype.html#cb885-7"></a>    <span class="co">//                      v</span></span>
<span id="cb885-8"><a href="ctype.html#cb885-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iscntrl<span class="op">(</span><span class="ch">'\t'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (tab)</span></span>
<span id="cb885-9"><a href="ctype.html#cb885-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iscntrl<span class="op">(</span><span class="ch">'\n'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (newline)</span></span>
<span id="cb885-10"><a href="ctype.html#cb885-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iscntrl<span class="op">(</span><span class="ch">'\r'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (return)</span></span>
<span id="cb885-11"><a href="ctype.html#cb885-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iscntrl<span class="op">(</span><span class="ch">'\a'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (bell)</span></span>
<span id="cb885-12"><a href="ctype.html#cb885-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iscntrl<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb885-13"><a href="ctype.html#cb885-13"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iscntrl<span class="op">(</span><span class="ch">'a'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb885-14"><a href="ctype.html#cb885-14"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iscntrl<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb885-15"><a href="ctype.html#cb885-15"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-25">See Also</h3>
<p><a href="ctype.html#man-isgraph"><code>isgraph()</code></a>, <a href="#man-isprint"><code>isprint()</code></a></p>
<hr>
<h2 data-number="44.5" id="man-isdigit"><span class="header-section-number">44.5</span> <code>isdigit()</code></h2>
<p>Tests if a character is a digit</p>
<h3 class="unnumbered unlisted" id="synopsis-29">Synopsis</h3>
<div class="sourceCode" id="cb886"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb886-1"><a href="ctype.html#cb886-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb886-2"><a href="ctype.html#cb886-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb886-3"><a href="ctype.html#cb886-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isdigit<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-29">Description</h3>
<p>Tests if <code>c</code> is a digit in the range
<code>0</code>-<code>9</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-29">Return Value</h3>
<p>Returns true if the character is a digit, unsurprisingly.</p>
<h3 class="unnumbered unlisted" id="example-29">Example</h3>
<div class="sourceCode" id="cb887"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb887-1"><a href="ctype.html#cb887-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb887-2"><a href="ctype.html#cb887-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb887-3"><a href="ctype.html#cb887-3"></a></span>
<span id="cb887-4"><a href="ctype.html#cb887-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb887-5"><a href="ctype.html#cb887-5"></a><span class="op">{</span></span>
<span id="cb887-6"><a href="ctype.html#cb887-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb887-7"><a href="ctype.html#cb887-7"></a>    <span class="co">//                      v</span></span>
<span id="cb887-8"><a href="ctype.html#cb887-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isdigit<span class="op">(</span><span class="ch">'0'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb887-9"><a href="ctype.html#cb887-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isdigit<span class="op">(</span><span class="ch">'5'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb887-10"><a href="ctype.html#cb887-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isdigit<span class="op">(</span><span class="ch">'a'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb887-11"><a href="ctype.html#cb887-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isdigit<span class="op">(</span><span class="ch">'B'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb887-12"><a href="ctype.html#cb887-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isdigit<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb887-13"><a href="ctype.html#cb887-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-26">See Also</h3>
<p><a href="ctype.html#man-isalnum"><code>isalnum()</code></a>, <a href="#man-isxdigit"><code>isxdigit()</code></a></p>
<hr>
<h2 data-number="44.6" id="man-isgraph"><span class="header-section-number">44.6</span> <code>isgraph()</code></h2>
<p>Tests if the character is printable and not a space</p>
<h3 class="unnumbered unlisted" id="synopsis-30">Synopsis</h3>
<div class="sourceCode" id="cb888"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb888-1"><a href="ctype.html#cb888-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb888-2"><a href="ctype.html#cb888-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb888-3"><a href="ctype.html#cb888-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isgraph<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-30">Description</h3>
<p>Tests if <code>c</code> is any printable character that isn’t a space
(<code>' '</code>).</p>
<h3 class="unnumbered unlisted" id="return-value-30">Return Value</h3>
<p>Returns true if <code>c</code> is any printable character that isn’t
a space (<code>' '</code>).</p>
<h3 class="unnumbered unlisted" id="example-30">Example</h3>
<div class="sourceCode" id="cb889"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb889-1"><a href="ctype.html#cb889-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb889-2"><a href="ctype.html#cb889-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb889-3"><a href="ctype.html#cb889-3"></a></span>
<span id="cb889-4"><a href="ctype.html#cb889-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb889-5"><a href="ctype.html#cb889-5"></a><span class="op">{</span></span>
<span id="cb889-6"><a href="ctype.html#cb889-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb889-7"><a href="ctype.html#cb889-7"></a>    <span class="co">//                      v</span></span>
<span id="cb889-8"><a href="ctype.html#cb889-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgraph<span class="op">(</span><span class="ch">'0'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb889-9"><a href="ctype.html#cb889-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgraph<span class="op">(</span><span class="ch">'a'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb889-10"><a href="ctype.html#cb889-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgraph<span class="op">(</span><span class="ch">'B'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb889-11"><a href="ctype.html#cb889-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgraph<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb889-12"><a href="ctype.html#cb889-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgraph<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb889-13"><a href="ctype.html#cb889-13"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgraph<span class="op">(</span><span class="ch">'\n'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb889-14"><a href="ctype.html#cb889-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-27">See Also</h3>
<p><a href="ctype.html#man-iscntrl"><code>iscntrl()</code></a>, <a href="#man-isprint"><code>isprint()</code></a></p>
<hr>
<h2 data-number="44.7" id="man-islower"><span class="header-section-number">44.7</span> <code>islower()</code></h2>
<p>Tests if a character is lowercase</p>
<h3 class="unnumbered unlisted" id="synopsis-31">Synopsis</h3>
<div class="sourceCode" id="cb890"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb890-1"><a href="ctype.html#cb890-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb890-2"><a href="ctype.html#cb890-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb890-3"><a href="ctype.html#cb890-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> islower<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-31">Description</h3>
<p>Tests if a character is lowercase, in the range
<code>a</code>-<code>z</code>.</p>
<p>In other locales, there could be other lowercase characters. In all
cases, to be lowercase, the following must be true:</p>
<div class="sourceCode" id="cb891"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb891-1"><a href="ctype.html#cb891-1" aria-hidden="true" tabindex="-1"></a><span class="op">!</span>iscntrl<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isdigit<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>ispunct<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isspace<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-31">Return Value</h3>
<p>Returns true if the character is lowercase.</p>
<h3 class="unnumbered unlisted" id="example-31">Example</h3>
<div class="sourceCode" id="cb892"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb892-1"><a href="ctype.html#cb892-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb892-2"><a href="ctype.html#cb892-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb892-3"><a href="ctype.html#cb892-3"></a></span>
<span id="cb892-4"><a href="ctype.html#cb892-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb892-5"><a href="ctype.html#cb892-5"></a><span class="op">{</span></span>
<span id="cb892-6"><a href="ctype.html#cb892-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb892-7"><a href="ctype.html#cb892-7"></a>    <span class="co">//                      v</span></span>
<span id="cb892-8"><a href="ctype.html#cb892-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islower<span class="op">(</span><span class="ch">'c'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb892-9"><a href="ctype.html#cb892-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islower<span class="op">(</span><span class="ch">'0'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb892-10"><a href="ctype.html#cb892-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islower<span class="op">(</span><span class="ch">'B'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb892-11"><a href="ctype.html#cb892-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islower<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb892-12"><a href="ctype.html#cb892-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islower<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb892-13"><a href="ctype.html#cb892-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-28">See Also</h3>
<p><a href="ctype.html#man-isupper"><code>isupper()</code></a>, <a href="#man-isalpha"><code>isalpha()</code></a>, <a href="#man-toupper"><code>toupper()</code></a>, <a href="#man-tolower"><code>tolower()</code></a></p>
<hr>
<h2 data-number="44.8" id="man-isprint"><span class="header-section-number">44.8</span> <code>isprint()</code></h2>
<p>Tests if a character is printable</p>
<h3 class="unnumbered unlisted" id="synopsis-32">Synopsis</h3>
<div class="sourceCode" id="cb893"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb893-1"><a href="ctype.html#cb893-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb893-2"><a href="ctype.html#cb893-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb893-3"><a href="ctype.html#cb893-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isprint<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-32">Description</h3>
<p>Tests if a character is printable, including space
(<code>' '</code>). So like <code>isgraph()</code>, except space isn’t
left out in the cold.</p>
<h3 class="unnumbered unlisted" id="return-value-32">Return Value</h3>
<p>Returns true if the character is printable, including space
(<code>' '</code>).</p>
<h3 class="unnumbered unlisted" id="example-32">Example</h3>
<div class="sourceCode" id="cb894"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb894-1"><a href="ctype.html#cb894-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb894-2"><a href="ctype.html#cb894-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb894-3"><a href="ctype.html#cb894-3"></a></span>
<span id="cb894-4"><a href="ctype.html#cb894-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb894-5"><a href="ctype.html#cb894-5"></a><span class="op">{</span></span>
<span id="cb894-6"><a href="ctype.html#cb894-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb894-7"><a href="ctype.html#cb894-7"></a>    <span class="co">//                      v</span></span>
<span id="cb894-8"><a href="ctype.html#cb894-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isprint<span class="op">(</span><span class="ch">'c'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb894-9"><a href="ctype.html#cb894-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isprint<span class="op">(</span><span class="ch">'0'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb894-10"><a href="ctype.html#cb894-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isprint<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb894-11"><a href="ctype.html#cb894-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isprint<span class="op">(</span><span class="ch">'\r'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb894-12"><a href="ctype.html#cb894-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-29">See Also</h3>
<p><a href="ctype.html#man-isgraph"><code>isgraph()</code></a>, <a href="#man-iscntrl"><code>iscntrl()</code></a></p>
<hr>
<h2 data-number="44.9" id="man-ispunct"><span class="header-section-number">44.9</span> <code>ispunct()</code></h2>
<p>Test if a character is punctuation</p>
<h3 class="unnumbered unlisted" id="synopsis-33">Synopsis</h3>
<div class="sourceCode" id="cb895"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb895-1"><a href="ctype.html#cb895-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb895-2"><a href="ctype.html#cb895-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb895-3"><a href="ctype.html#cb895-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> ispunct<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-33">Description</h3>
<p>Tests if a character is punctuation.</p>
<p>In the “C” locale, this means:</p>
<div class="sourceCode" id="cb896"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb896-1"><a href="ctype.html#cb896-1" aria-hidden="true" tabindex="-1"></a><span class="op">!</span>isspace<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isalnum<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<p>In other locales, there could be other punctuation characters (but
they also can’t be space or alphanumeric).</p>
<h3 class="unnumbered unlisted" id="return-value-33">Return Value</h3>
<p>True if the character is punctuation.</p>
<h3 class="unnumbered unlisted" id="example-33">Example</h3>
<div class="sourceCode" id="cb897"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb897-1"><a href="ctype.html#cb897-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb897-2"><a href="ctype.html#cb897-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb897-3"><a href="ctype.html#cb897-3"></a></span>
<span id="cb897-4"><a href="ctype.html#cb897-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb897-5"><a href="ctype.html#cb897-5"></a><span class="op">{</span></span>
<span id="cb897-6"><a href="ctype.html#cb897-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb897-7"><a href="ctype.html#cb897-7"></a>    <span class="co">//                      v</span></span>
<span id="cb897-8"><a href="ctype.html#cb897-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ispunct<span class="op">(</span><span class="ch">','</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb897-9"><a href="ctype.html#cb897-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ispunct<span class="op">(</span><span class="ch">'!'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb897-10"><a href="ctype.html#cb897-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ispunct<span class="op">(</span><span class="ch">'c'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb897-11"><a href="ctype.html#cb897-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ispunct<span class="op">(</span><span class="ch">'0'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb897-12"><a href="ctype.html#cb897-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ispunct<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb897-13"><a href="ctype.html#cb897-13"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ispunct<span class="op">(</span><span class="ch">'\n'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb897-14"><a href="ctype.html#cb897-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-30">See Also</h3>
<p><a href="ctype.html#man-isspace"><code>isspace()</code></a>, <a href="#man-isalnum"><code>isalnum()</code></a></p>
<hr>
<h2 data-number="44.10" id="man-isspace"><span class="header-section-number">44.10</span> <code>isspace()</code></h2>
<p>Test if a character is whitespace</p>
<h3 class="unnumbered unlisted" id="synopsis-34">Synopsis</h3>
<div class="sourceCode" id="cb898"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb898-1"><a href="ctype.html#cb898-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb898-2"><a href="ctype.html#cb898-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb898-3"><a href="ctype.html#cb898-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isspace<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-34">Description</h3>
<p>Tests if <code>c</code> is a whitespace character. These are:</p>
<ul>
<li>Space (<code>' '</code>)</li>
<li>Formfeed (<code>'\f'</code>)</li>
<li>Newline (<code>'\n'</code>)</li>
<li>Carriage Return (<code>'\r'</code>)</li>
<li>Horizontal Tab (<code>'\t'</code>)</li>
<li>Vertical Tab (<code>'\v'</code>)</li>
</ul>
<p>Other locales might specify other whitespace characters.
<code>isalnum()</code> is false for all whitespace characters.</p>
<h3 class="unnumbered unlisted" id="return-value-34">Return Value</h3>
<p>True if the character is whitespace.</p>
<h3 class="unnumbered unlisted" id="example-34">Example</h3>
<div class="sourceCode" id="cb899"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb899-1"><a href="ctype.html#cb899-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb899-2"><a href="ctype.html#cb899-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb899-3"><a href="ctype.html#cb899-3"></a></span>
<span id="cb899-4"><a href="ctype.html#cb899-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb899-5"><a href="ctype.html#cb899-5"></a><span class="op">{</span></span>
<span id="cb899-6"><a href="ctype.html#cb899-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb899-7"><a href="ctype.html#cb899-7"></a>    <span class="co">//                      v</span></span>
<span id="cb899-8"><a href="ctype.html#cb899-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isspace<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb899-9"><a href="ctype.html#cb899-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isspace<span class="op">(</span><span class="ch">'\n'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb899-10"><a href="ctype.html#cb899-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isspace<span class="op">(</span><span class="ch">'\t'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb899-11"><a href="ctype.html#cb899-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isspace<span class="op">(</span><span class="ch">','</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb899-12"><a href="ctype.html#cb899-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isspace<span class="op">(</span><span class="ch">'!'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb899-13"><a href="ctype.html#cb899-13"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isspace<span class="op">(</span><span class="ch">'c'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb899-14"><a href="ctype.html#cb899-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-31">See Also</h3>
<p><a href="ctype.html#man-isblank"><code>isblank()</code></a></p>
<hr>
<h2 data-number="44.11" id="man-isupper"><span class="header-section-number">44.11</span> <code>isupper()</code></h2>
<p>Tests if a character is uppercase</p>
<h3 class="unnumbered unlisted" id="synopsis-35">Synopsis</h3>
<div class="sourceCode" id="cb900"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb900-1"><a href="ctype.html#cb900-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb900-2"><a href="ctype.html#cb900-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb900-3"><a href="ctype.html#cb900-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isupper<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-35">Description</h3>
<p>Tests if a character is uppercase, in the range
<code>A</code>-<code>Z</code>.</p>
<p>In other locales, there could be other uppercase characters. In all
cases, to be uppercase, the following must be true:</p>
<div class="sourceCode" id="cb901"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb901-1"><a href="ctype.html#cb901-1" aria-hidden="true" tabindex="-1"></a><span class="op">!</span>iscntrl<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isdigit<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>ispunct<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isspace<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-35">Return Value</h3>
<p>Returns true if the character is uppercase.</p>
<h3 class="unnumbered unlisted" id="example-35">Example</h3>
<div class="sourceCode" id="cb902"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb902-1"><a href="ctype.html#cb902-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb902-2"><a href="ctype.html#cb902-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb902-3"><a href="ctype.html#cb902-3"></a></span>
<span id="cb902-4"><a href="ctype.html#cb902-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb902-5"><a href="ctype.html#cb902-5"></a><span class="op">{</span></span>
<span id="cb902-6"><a href="ctype.html#cb902-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb902-7"><a href="ctype.html#cb902-7"></a>    <span class="co">//                      v</span></span>
<span id="cb902-8"><a href="ctype.html#cb902-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isupper<span class="op">(</span><span class="ch">'B'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb902-9"><a href="ctype.html#cb902-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isupper<span class="op">(</span><span class="ch">'c'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb902-10"><a href="ctype.html#cb902-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isupper<span class="op">(</span><span class="ch">'0'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb902-11"><a href="ctype.html#cb902-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isupper<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb902-12"><a href="ctype.html#cb902-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isupper<span class="op">(</span><span class="ch">' '</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb902-13"><a href="ctype.html#cb902-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-32">See Also</h3>
<p><a href="ctype.html#man-islower"><code>islower()</code></a>, <a href="#man-isalpha"><code>isalpha()</code></a>, <a href="#man-toupper"><code>toupper()</code></a>, <a href="#man-tolower"><code>tolower()</code></a></p>
<hr>
<h2 data-number="44.12" id="man-isxdigit"><span class="header-section-number">44.12</span> <code>isxdigit()</code></h2>
<p>Tests if a character is a hexadecimal digit</p>
<h3 class="unnumbered unlisted" id="synopsis-36">Synopsis</h3>
<div class="sourceCode" id="cb903"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb903-1"><a href="ctype.html#cb903-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb903-2"><a href="ctype.html#cb903-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb903-3"><a href="ctype.html#cb903-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isxdigit<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-36">Description</h3>
<p>Returns true if the character is a hexadecimal digit. Namely if it’s
<code>0</code>-<code>9</code>, <code>a</code>-<code>f</code>, or
<code>A</code>-<code>F</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-36">Return Value</h3>
<p>True if the character is a hexadecimal digit.</p>
<h3 class="unnumbered unlisted" id="example-36">Example</h3>
<div class="sourceCode" id="cb904"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb904-1"><a href="ctype.html#cb904-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb904-2"><a href="ctype.html#cb904-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb904-3"><a href="ctype.html#cb904-3"></a></span>
<span id="cb904-4"><a href="ctype.html#cb904-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb904-5"><a href="ctype.html#cb904-5"></a><span class="op">{</span></span>
<span id="cb904-6"><a href="ctype.html#cb904-6"></a>    <span class="co">//             testing this char</span></span>
<span id="cb904-7"><a href="ctype.html#cb904-7"></a>    <span class="co">//                      v</span></span>
<span id="cb904-8"><a href="ctype.html#cb904-8"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isxdigit<span class="op">(</span><span class="ch">'B'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb904-9"><a href="ctype.html#cb904-9"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isxdigit<span class="op">(</span><span class="ch">'c'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb904-10"><a href="ctype.html#cb904-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isxdigit<span class="op">(</span><span class="ch">'2'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb904-11"><a href="ctype.html#cb904-11"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isxdigit<span class="op">(</span><span class="ch">'G'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb904-12"><a href="ctype.html#cb904-12"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isxdigit<span class="op">(</span><span class="ch">'?'</span><span class="op">)?</span> <span class="st">"yes"</span><span class="op">:</span> <span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb904-13"><a href="ctype.html#cb904-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-33">See Also</h3>
<p><a href="ctype.html#man-isdigit"><code>isdigit()</code></a></p>
<hr>
<h2 data-number="44.13" id="man-tolower"><span class="header-section-number">44.13</span> <code>tolower()</code></h2>
<p>Convert a letter to lowercase</p>
<h3 class="unnumbered unlisted" id="synopsis-37">Synopsis</h3>
<div class="sourceCode" id="cb905"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb905-1"><a href="ctype.html#cb905-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb905-2"><a href="ctype.html#cb905-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb905-3"><a href="ctype.html#cb905-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> tolower<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-37">Description</h3>
<p>If the character is uppercase (i.e.&nbsp;<code>isupper(c)</code> is true),
this function returns the corresponding lowercase letter.</p>
<p>Different locales might have different upper- and lowercase
letters.</p>
<h3 class="unnumbered unlisted" id="return-value-37">Return Value</h3>
<p>Returns the lowercase value for an uppercase letter. If the letter
isn’t uppercase, returns it unchanged.</p>
<h3 class="unnumbered unlisted" id="example-37">Example</h3>
<div class="sourceCode" id="cb906"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb906-1"><a href="ctype.html#cb906-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb906-2"><a href="ctype.html#cb906-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb906-3"><a href="ctype.html#cb906-3"></a></span>
<span id="cb906-4"><a href="ctype.html#cb906-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb906-5"><a href="ctype.html#cb906-5"></a><span class="op">{</span></span>
<span id="cb906-6"><a href="ctype.html#cb906-6"></a>    <span class="co">//             changing this char</span></span>
<span id="cb906-7"><a href="ctype.html#cb906-7"></a>    <span class="co">//                      v</span></span>
<span id="cb906-8"><a href="ctype.html#cb906-8"></a>    printf<span class="op">(</span><span class="st">"%c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tolower<span class="op">(</span><span class="ch">'B'</span><span class="op">));</span>  <span class="co">// b (made lowercase!)</span></span>
<span id="cb906-9"><a href="ctype.html#cb906-9"></a>    printf<span class="op">(</span><span class="st">"%c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tolower<span class="op">(</span><span class="ch">'e'</span><span class="op">));</span>  <span class="co">// e (unchanged)</span></span>
<span id="cb906-10"><a href="ctype.html#cb906-10"></a>    printf<span class="op">(</span><span class="st">"%c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tolower<span class="op">(</span><span class="ch">'!'</span><span class="op">));</span>  <span class="co">// ! (unchanged)</span></span>
<span id="cb906-11"><a href="ctype.html#cb906-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-34">See Also</h3>
<p><a href="ctype.html#man-toupper"><code>toupper()</code></a>, <a href="#man-islower"><code>islower()</code></a>, <a href="#man-isupper"><code>isupper()</code></a></p>
<hr>
<h2 data-number="44.14" id="man-toupper"><span class="header-section-number">44.14</span> <code>toupper()</code></h2>
<p>Convert a letter to uppercase</p>
<h3 class="unnumbered unlisted" id="synopsis-38">Synopsis</h3>
<div class="sourceCode" id="cb907"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb907-1"><a href="ctype.html#cb907-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb907-2"><a href="ctype.html#cb907-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb907-3"><a href="ctype.html#cb907-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> toupper<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-38">Description</h3>
<p>If the character is lower (i.e.&nbsp;<code>islower(c)</code> is true),
this function returns the corresponding uppercase letter.</p>
<p>Different locales might have different upper- and lowercase
letters.</p>
<h3 class="unnumbered unlisted" id="return-value-38">Return Value</h3>
<p>Returns the uppercase value for a lowercase letter. If the letter
isn’t lowercase, returns it unchanged.</p>
<h3 class="unnumbered unlisted" id="example-38">Example</h3>
<div class="sourceCode" id="cb908"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb908-1"><a href="ctype.html#cb908-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb908-2"><a href="ctype.html#cb908-2"></a><span class="pp">#include </span><span class="im">&lt;ctype.h&gt;</span></span>
<span id="cb908-3"><a href="ctype.html#cb908-3"></a></span>
<span id="cb908-4"><a href="ctype.html#cb908-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb908-5"><a href="ctype.html#cb908-5"></a><span class="op">{</span></span>
<span id="cb908-6"><a href="ctype.html#cb908-6"></a>    <span class="co">//             changing this char</span></span>
<span id="cb908-7"><a href="ctype.html#cb908-7"></a>    <span class="co">//                      v</span></span>
<span id="cb908-8"><a href="ctype.html#cb908-8"></a>    printf<span class="op">(</span><span class="st">"%c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> toupper<span class="op">(</span><span class="ch">'B'</span><span class="op">));</span>  <span class="co">// B (unchanged)</span></span>
<span id="cb908-9"><a href="ctype.html#cb908-9"></a>    printf<span class="op">(</span><span class="st">"%c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> toupper<span class="op">(</span><span class="ch">'e'</span><span class="op">));</span>  <span class="co">// E (made uppercase!)</span></span>
<span id="cb908-10"><a href="ctype.html#cb908-10"></a>    printf<span class="op">(</span><span class="st">"%c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> toupper<span class="op">(</span><span class="ch">'!'</span><span class="op">));</span>  <span class="co">// ! (unchanged)</span></span>
<span id="cb908-11"><a href="ctype.html#cb908-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-35">See Also</h3>
<p><a href="ctype.html#man-tolower"><code>tolower()</code></a>, <a href="#man-islower"><code>islower()</code></a>, <a href="#man-isupper"><code>isupper()</code></a></p>

</body>