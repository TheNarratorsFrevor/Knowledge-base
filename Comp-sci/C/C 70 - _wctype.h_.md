2<body>

<hr>
<h1 data-number="70" id="wctype"><span class="header-section-number">70</span> <code>&lt;wctype.h&gt;</code>
Wide Character Classification and Transformation</h1>
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
<td><a href="wctype.html#man-iswalnum"><code>iswalnum()</code></a></td>
<td>Test if a wide character is alphanumeric.</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-iswalpha"><code>iswalpha()</code></a></td>
<td>Tests if a wide character is alphabetic</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-iswblank"><code>iswblank()</code></a></td>
<td>Tests if this is a wide blank character</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-iswcntrl"><code>iswcntrl()</code></a></td>
<td>Tests if this is a wide control character.</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-iswctype"><code>iswctype()</code></a></td>
<td>Determine wide character classification</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-iswdigit"><code>iswdigit()</code></a></td>
<td>Test if this wide character is a digit</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-iswgraph"><code>iswgraph()</code></a></td>
<td>Test to see if a wide character is a printable non-space</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-iswlower"><code>iswlower()</code></a></td>
<td>Tests if a wide character is lowercase</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-iswprint"><code>iswprint()</code></a></td>
<td>Tests if a wide character is printable</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-iswpunct"><code>iswpunct()</code></a></td>
<td>Test if a wide character is punctuation</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-iswspace"><code>iswspace()</code></a></td>
<td>Test if a wide character is whitespace</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-iswupper"><code>iswupper()</code></a></td>
<td>Tests if a wide character is uppercase</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-iswxdigit"><code>iswxdigit()</code></a></td>
<td>Tests if a wide character is a hexadecimal digit</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-towctrans"><code>towctrans()</code></a></td>
<td>Convert wide characters to upper or lowercase</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-towlower"><code>towlower()</code></a></td>
<td>Convert an uppercase wide character to lowercase</td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-towupper"><code>towupper()</code></a></td>
<td>Convert a lowercase wide character to uppercase</td>
</tr>
<tr class="odd">
<td><a href="wctype.html#man-wctrans"><code>wctrans()</code></a></td>
<td>Helper function for <code>towctrans()</code></td>
</tr>
<tr class="even">
<td><a href="wctype.html#man-wctype"><code>wctype()</code></a></td>
<td>Helper function for <code>iswctype()</code></td>
</tr>
</tbody>
</table>
<p>This is like <a href="ctype.html"><code>&lt;ctype.h&gt;</code></a> except
for wide characters.</p>
<p>With it you can test for character classifications (like “is this
character whitespace?”) or do basic character conversions (like “force
this character to lowercase”).</p>
<hr>
<h2 data-number="70.1" id="man-iswalnum"><span class="header-section-number">70.1</span> <code>iswalnum()</code></h2>
<p>Test if a wide character is alphanumeric.</p>
<h3 class="unnumbered unlisted" id="synopsis-267">Synopsis</h3>
<div class="sourceCode" id="cb1631"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1631-1"><a href="wctype.html#cb1631-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1631-2"><a href="wctype.html#cb1631-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1631-3"><a href="wctype.html#cb1631-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswalnum<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-267">Description</h3>
<p>Basically tests if a character is alphabetic
(<code>A</code>-<code>Z</code> or <code>a</code>-<code>z</code>) or a
digit (<code>0</code>-<code>9</code>). But some other characters might
also qualify based on the locale.</p>
<p>This is equivalent to testing if <code>iswalpha()</code> or
<code>iswdigit()</code> is true.</p>
<h3 class="unnumbered unlisted" id="return-value-265">Return Value</h3>
<p>Returns true if the character is alphanumeric.</p>
<h3 class="unnumbered unlisted" id="example-269">Example</h3>
<div class="sourceCode" id="cb1632"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1632-1"><a href="wctype.html#cb1632-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1632-2"><a href="wctype.html#cb1632-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1632-3"><a href="wctype.html#cb1632-3"></a></span>
<span id="cb1632-4"><a href="wctype.html#cb1632-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1632-5"><a href="wctype.html#cb1632-5"></a><span class="op">{</span></span>
<span id="cb1632-6"><a href="wctype.html#cb1632-6"></a>    <span class="co">//                  testing this char</span></span>
<span id="cb1632-7"><a href="wctype.html#cb1632-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1632-8"><a href="wctype.html#cb1632-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalnum<span class="op">(</span>L<span class="ch">'a'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1632-9"><a href="wctype.html#cb1632-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalnum<span class="op">(</span>L<span class="ch">'B'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1632-10"><a href="wctype.html#cb1632-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalnum<span class="op">(</span>L<span class="ch">'5'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1632-11"><a href="wctype.html#cb1632-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalnum<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb1632-12"><a href="wctype.html#cb1632-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-254">See Also</h3>
<p><a href="wctype.html#man-iswalpha"><code>iswalpha()</code></a>, <a href="#man-iswdigit"><code>iswdigit()</code></a>, <a href="#man-isalnum"><code>isalnum()</code></a></p>
<hr>
<h2 data-number="70.2" id="man-iswalpha"><span class="header-section-number">70.2</span> <code>iswalpha()</code></h2>
<p>Tests if a wide character is alphabetic</p>
<h3 class="unnumbered unlisted" id="synopsis-268">Synopsis</h3>
<div class="sourceCode" id="cb1633"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1633-1"><a href="wctype.html#cb1633-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1633-2"><a href="wctype.html#cb1633-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1633-3"><a href="wctype.html#cb1633-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswalpha<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-268">Description</h3>
<p>Basically tests if a character is alphabetic
(<code>A</code>-<code>Z</code> or <code>a</code>-<code>z</code>). But
some other characters might also qualify based on the locale. (If other
characters qualify, they won’t be control characters, digits,
punctuation, or spaces.)</p>
<p>This is the same as testing for <code>iswupper()</code> or
<code>iswlower()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-266">Return Value</h3>
<p>Returns true if the character is alphabetic.</p>
<h3 class="unnumbered unlisted" id="example-270">Example</h3>
<div class="sourceCode" id="cb1634"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1634-1"><a href="wctype.html#cb1634-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1634-2"><a href="wctype.html#cb1634-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1634-3"><a href="wctype.html#cb1634-3"></a></span>
<span id="cb1634-4"><a href="wctype.html#cb1634-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1634-5"><a href="wctype.html#cb1634-5"></a><span class="op">{</span></span>
<span id="cb1634-6"><a href="wctype.html#cb1634-6"></a>    <span class="co">//                  testing this char</span></span>
<span id="cb1634-7"><a href="wctype.html#cb1634-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1634-8"><a href="wctype.html#cb1634-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalpha<span class="op">(</span>L<span class="ch">'a'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1634-9"><a href="wctype.html#cb1634-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalpha<span class="op">(</span>L<span class="ch">'B'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1634-10"><a href="wctype.html#cb1634-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalpha<span class="op">(</span>L<span class="ch">'5'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb1634-11"><a href="wctype.html#cb1634-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswalpha<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb1634-12"><a href="wctype.html#cb1634-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-255">See Also</h3>
<p><a href="wctype.html#man-iswalnum"><code>iswalnum()</code></a>, <a href="#man-isalpha"><code>isalpha()</code></a></p>
<hr>
<h2 data-number="70.3" id="man-iswblank"><span class="header-section-number">70.3</span> <code>iswblank()</code></h2>
<p>Tests if this is a wide blank character</p>
<h3 class="unnumbered unlisted" id="synopsis-269">Synopsis</h3>
<div class="sourceCode" id="cb1635"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1635-1"><a href="wctype.html#cb1635-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1635-2"><a href="wctype.html#cb1635-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1635-3"><a href="wctype.html#cb1635-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswblank<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-269">Description</h3>
<p>Blank characters are whitespace that are also used as word separators
on the same line. In the “C” locale, the only blank characters are space
and tab.</p>
<p>Other locales might define other blank characters.</p>
<h3 class="unnumbered unlisted" id="return-value-267">Return Value</h3>
<p>Returns true if this is a blank character.</p>
<h3 class="unnumbered unlisted" id="example-271">Example</h3>
<div class="sourceCode" id="cb1636"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1636-1"><a href="wctype.html#cb1636-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1636-2"><a href="wctype.html#cb1636-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1636-3"><a href="wctype.html#cb1636-3"></a></span>
<span id="cb1636-4"><a href="wctype.html#cb1636-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1636-5"><a href="wctype.html#cb1636-5"></a><span class="op">{</span></span>
<span id="cb1636-6"><a href="wctype.html#cb1636-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1636-7"><a href="wctype.html#cb1636-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1636-8"><a href="wctype.html#cb1636-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswblank<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1636-9"><a href="wctype.html#cb1636-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswblank<span class="op">(</span>L<span class="ch">'\t'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1636-10"><a href="wctype.html#cb1636-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswblank<span class="op">(</span>L<span class="ch">'\n'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb1636-11"><a href="wctype.html#cb1636-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswblank<span class="op">(</span>L<span class="ch">'a'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1636-12"><a href="wctype.html#cb1636-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswblank<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1636-13"><a href="wctype.html#cb1636-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-256">See Also</h3>
<p><a href="wctype.html#man-iswspace"><code>iswspace()</code></a>, <a href="#man-isblank"><code>isblank()</code></a></p>
<hr>
<h2 data-number="70.4" id="man-iswcntrl"><span class="header-section-number">70.4</span> <code>iswcntrl()</code></h2>
<p>Tests if this is a wide control character.</p>
<h3 class="unnumbered unlisted" id="synopsis-270">Synopsis</h3>
<div class="sourceCode" id="cb1637"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1637-1"><a href="wctype.html#cb1637-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1637-2"><a href="wctype.html#cb1637-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1637-3"><a href="wctype.html#cb1637-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswcntrl<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-270">Description</h3>
<p>The spec is pretty barren, here. But I’m just going to assume that it
works like the non-wide version. So let’s look at that.</p>
<p>A <em>control character</em> is a locale-specific non-printing
character.</p>
<p>For the “C” locale, this means control characters are in the range
0x00 to 0x1F (the character right before SPACE) and 0x7F (the DEL
character).</p>
<p>Basically if it’s not an ASCII (or Unicode less than 128) printable
character, it’s a control character in the “C” locale.</p>
<p>Probably.</p>
<h3 class="unnumbered unlisted" id="return-value-268">Return Value</h3>
<p>Returns true if this is a control character.</p>
<h3 class="unnumbered unlisted" id="example-272">Example</h3>
<div class="sourceCode" id="cb1638"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1638-1"><a href="wctype.html#cb1638-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1638-2"><a href="wctype.html#cb1638-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1638-3"><a href="wctype.html#cb1638-3"></a></span>
<span id="cb1638-4"><a href="wctype.html#cb1638-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1638-5"><a href="wctype.html#cb1638-5"></a><span class="op">{</span></span>
<span id="cb1638-6"><a href="wctype.html#cb1638-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1638-7"><a href="wctype.html#cb1638-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1638-8"><a href="wctype.html#cb1638-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswcntrl<span class="op">(</span>L<span class="ch">'\t'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (tab)</span></span>
<span id="cb1638-9"><a href="wctype.html#cb1638-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswcntrl<span class="op">(</span>L<span class="ch">'\n'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (newline)</span></span>
<span id="cb1638-10"><a href="wctype.html#cb1638-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswcntrl<span class="op">(</span>L<span class="ch">'\r'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (return)</span></span>
<span id="cb1638-11"><a href="wctype.html#cb1638-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswcntrl<span class="op">(</span>L<span class="ch">'\a'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes (bell)</span></span>
<span id="cb1638-12"><a href="wctype.html#cb1638-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswcntrl<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1638-13"><a href="wctype.html#cb1638-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswcntrl<span class="op">(</span>L<span class="ch">'a'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1638-14"><a href="wctype.html#cb1638-14"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswcntrl<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1638-15"><a href="wctype.html#cb1638-15"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-257">See Also</h3>
<p><a href="ctype.html#man-iscntrl"><code>iscntrl()</code></a></p>
<hr>
<h2 data-number="70.5" id="man-iswdigit"><span class="header-section-number">70.5</span> <code>iswdigit()</code></h2>
<p>Test if this wide character is a digit</p>
<h3 class="unnumbered unlisted" id="synopsis-271">Synopsis</h3>
<div class="sourceCode" id="cb1639"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1639-1"><a href="wctype.html#cb1639-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1639-2"><a href="wctype.html#cb1639-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1639-3"><a href="wctype.html#cb1639-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswdigit<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-271">Description</h3>
<p>Tests if the wide character is a digit
(<code>0</code>-<code>9</code>).</p>
<h3 class="unnumbered unlisted" id="return-value-269">Return Value</h3>
<p>Returns true if the character is a digit.</p>
<h3 class="unnumbered unlisted" id="example-273">Example</h3>
<div class="sourceCode" id="cb1640"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1640-1"><a href="wctype.html#cb1640-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1640-2"><a href="wctype.html#cb1640-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1640-3"><a href="wctype.html#cb1640-3"></a></span>
<span id="cb1640-4"><a href="wctype.html#cb1640-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1640-5"><a href="wctype.html#cb1640-5"></a><span class="op">{</span></span>
<span id="cb1640-6"><a href="wctype.html#cb1640-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1640-7"><a href="wctype.html#cb1640-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1640-8"><a href="wctype.html#cb1640-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswdigit<span class="op">(</span>L<span class="ch">'0'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1640-9"><a href="wctype.html#cb1640-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswdigit<span class="op">(</span>L<span class="ch">'5'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1640-10"><a href="wctype.html#cb1640-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswdigit<span class="op">(</span>L<span class="ch">'a'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1640-11"><a href="wctype.html#cb1640-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswdigit<span class="op">(</span>L<span class="ch">'B'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1640-12"><a href="wctype.html#cb1640-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswdigit<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1640-13"><a href="wctype.html#cb1640-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-258">See Also</h3>
<p><a href="wctype.html#man-iswalnum"><code>iswalnum()</code></a>, <a href="#man-isdigit"><code>isdigit()</code></a></p>
<hr>
<h2 data-number="70.6" id="man-iswgraph"><span class="header-section-number">70.6</span> <code>iswgraph()</code></h2>
<p>Test to see if a wide character is a printable non-space</p>
<h3 class="unnumbered unlisted" id="synopsis-272">Synopsis</h3>
<div class="sourceCode" id="cb1641"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1641-1"><a href="wctype.html#cb1641-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1641-2"><a href="wctype.html#cb1641-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1641-3"><a href="wctype.html#cb1641-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswgraph<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-272">Description</h3>
<p>Returns true if this is a printable (non-control) character and also
not a whitespace character.</p>
<p>Basically if <code>iswprint()</code> is true and
<code>iswspace()</code> is false.</p>
<h3 class="unnumbered unlisted" id="return-value-270">Return Value</h3>
<p>Returns true if this is a printable non-space character.</p>
<h3 class="unnumbered unlisted" id="example-274">Example</h3>
<div class="sourceCode" id="cb1642"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1642-1"><a href="wctype.html#cb1642-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1642-2"><a href="wctype.html#cb1642-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1642-3"><a href="wctype.html#cb1642-3"></a></span>
<span id="cb1642-4"><a href="wctype.html#cb1642-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1642-5"><a href="wctype.html#cb1642-5"></a><span class="op">{</span></span>
<span id="cb1642-6"><a href="wctype.html#cb1642-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1642-7"><a href="wctype.html#cb1642-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1642-8"><a href="wctype.html#cb1642-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswgraph<span class="op">(</span>L<span class="ch">'0'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1642-9"><a href="wctype.html#cb1642-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswgraph<span class="op">(</span>L<span class="ch">'a'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1642-10"><a href="wctype.html#cb1642-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswgraph<span class="op">(</span>L<span class="ch">'B'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1642-11"><a href="wctype.html#cb1642-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswgraph<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1642-12"><a href="wctype.html#cb1642-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswgraph<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1642-13"><a href="wctype.html#cb1642-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswgraph<span class="op">(</span>L<span class="ch">'\n'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb1642-14"><a href="wctype.html#cb1642-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-259">See Also</h3>
<p><a href="wctype.html#man-iswprint"><code>iswprint()</code></a>, <a href="#man-iswspace"><code>iswspace()</code></a>, <a href="#man-isgraph"><code>isgraph()</code></a></p>
<hr>
<h2 data-number="70.7" id="man-iswlower"><span class="header-section-number">70.7</span> <code>iswlower()</code></h2>
<p>Tests if a wide character is lowercase</p>
<h3 class="unnumbered unlisted" id="synopsis-273">Synopsis</h3>
<div class="sourceCode" id="cb1643"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1643-1"><a href="wctype.html#cb1643-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1643-2"><a href="wctype.html#cb1643-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1643-3"><a href="wctype.html#cb1643-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswlower<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-273">Description</h3>
<p>Tests if a character is lowercase, in the range
<code>a</code>-<code>z</code>.</p>
<p>In other locales, there could be other lowercase characters. In all
cases, to be lowercase, the following must be true:</p>
<div class="sourceCode" id="cb1644"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1644-1"><a href="wctype.html#cb1644-1" aria-hidden="true" tabindex="-1"></a><span class="op">!</span>iswcntrl<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>iswdigit<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>iswpunct<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>iswspace<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-271">Return Value</h3>
<p>Returns true if the wide character is lowercase.</p>
<h3 class="unnumbered unlisted" id="example-275">Example</h3>
<div class="sourceCode" id="cb1645"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1645-1"><a href="wctype.html#cb1645-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1645-2"><a href="wctype.html#cb1645-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1645-3"><a href="wctype.html#cb1645-3"></a></span>
<span id="cb1645-4"><a href="wctype.html#cb1645-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1645-5"><a href="wctype.html#cb1645-5"></a><span class="op">{</span></span>
<span id="cb1645-6"><a href="wctype.html#cb1645-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1645-7"><a href="wctype.html#cb1645-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1645-8"><a href="wctype.html#cb1645-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswlower<span class="op">(</span>L<span class="ch">'c'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1645-9"><a href="wctype.html#cb1645-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswlower<span class="op">(</span>L<span class="ch">'0'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1645-10"><a href="wctype.html#cb1645-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswlower<span class="op">(</span>L<span class="ch">'B'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1645-11"><a href="wctype.html#cb1645-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswlower<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1645-12"><a href="wctype.html#cb1645-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswlower<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1645-13"><a href="wctype.html#cb1645-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-260">See Also</h3>
<p><a href="ctype.html#man-islower"><code>islower()</code></a>, <a href="#man-isupper"><code>iswupper()</code></a>, <a href="#man-isalpha"><code>iswalpha()</code></a>, <a href="#man-toupper"><code>towupper()</code></a>, <a href="#man-tolower"><code>towlower()</code></a></p>
<hr>
<h2 data-number="70.8" id="man-iswprint"><span class="header-section-number">70.8</span> <code>iswprint()</code></h2>
<p>Tests if a wide character is printable</p>
<h3 class="unnumbered unlisted" id="synopsis-274">Synopsis</h3>
<div class="sourceCode" id="cb1646"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1646-1"><a href="wctype.html#cb1646-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1646-2"><a href="wctype.html#cb1646-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1646-3"><a href="wctype.html#cb1646-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswprint<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-274">Description</h3>
<p>Tests if a wide character is printable, including space
(<code>' '</code>). So like <code>isgraph()</code>, except space isn’t
left out in the cold.</p>
<h3 class="unnumbered unlisted" id="return-value-272">Return Value</h3>
<p>Returns true if the wide character is printable, including space
(<code>' '</code>).</p>
<h3 class="unnumbered unlisted" id="example-276">Example</h3>
<div class="sourceCode" id="cb1647"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1647-1"><a href="wctype.html#cb1647-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1647-2"><a href="wctype.html#cb1647-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1647-3"><a href="wctype.html#cb1647-3"></a></span>
<span id="cb1647-4"><a href="wctype.html#cb1647-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1647-5"><a href="wctype.html#cb1647-5"></a><span class="op">{</span></span>
<span id="cb1647-6"><a href="wctype.html#cb1647-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1647-7"><a href="wctype.html#cb1647-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1647-8"><a href="wctype.html#cb1647-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswprint<span class="op">(</span>L<span class="ch">'c'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1647-9"><a href="wctype.html#cb1647-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswprint<span class="op">(</span>L<span class="ch">'0'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1647-10"><a href="wctype.html#cb1647-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswprint<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1647-11"><a href="wctype.html#cb1647-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswprint<span class="op">(</span>L<span class="ch">'\r'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb1647-12"><a href="wctype.html#cb1647-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-261">See Also</h3>
<p><a href="ctype.html#man-isprint"><code>isprint()</code></a>, <a href="#man-iswgraph"><code>iswgraph()</code></a>, <a href="#man-iswcntrl"><code>iswcntrl()</code></a></p>
<hr>
<h2 data-number="70.9" id="man-iswpunct"><span class="header-section-number">70.9</span> <code>iswpunct()</code></h2>
<p>Test if a wide character is punctuation</p>
<h3 class="unnumbered unlisted" id="synopsis-275">Synopsis</h3>
<div class="sourceCode" id="cb1648"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1648-1"><a href="wctype.html#cb1648-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1648-2"><a href="wctype.html#cb1648-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1648-3"><a href="wctype.html#cb1648-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswpunct<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-275">Description</h3>
<p>Tests if a wide character is punctuation.</p>
<p>This means for any given locale:</p>
<div class="sourceCode" id="cb1649"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1649-1"><a href="wctype.html#cb1649-1" aria-hidden="true" tabindex="-1"></a><span class="op">!</span>isspace<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isalnum<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-273">Return Value</h3>
<p>True if the wide character is punctuation.</p>
<h3 class="unnumbered unlisted" id="example-277">Example</h3>
<p>Results may vary based on locale.</p>
<div class="sourceCode" id="cb1650"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1650-1"><a href="wctype.html#cb1650-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1650-2"><a href="wctype.html#cb1650-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1650-3"><a href="wctype.html#cb1650-3"></a></span>
<span id="cb1650-4"><a href="wctype.html#cb1650-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1650-5"><a href="wctype.html#cb1650-5"></a><span class="op">{</span></span>
<span id="cb1650-6"><a href="wctype.html#cb1650-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1650-7"><a href="wctype.html#cb1650-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1650-8"><a href="wctype.html#cb1650-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswpunct<span class="op">(</span>L<span class="ch">','</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1650-9"><a href="wctype.html#cb1650-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswpunct<span class="op">(</span>L<span class="ch">'!'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1650-10"><a href="wctype.html#cb1650-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswpunct<span class="op">(</span>L<span class="ch">'c'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1650-11"><a href="wctype.html#cb1650-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswpunct<span class="op">(</span>L<span class="ch">'0'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1650-12"><a href="wctype.html#cb1650-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswpunct<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1650-13"><a href="wctype.html#cb1650-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswpunct<span class="op">(</span>L<span class="ch">'\n'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// no</span></span>
<span id="cb1650-14"><a href="wctype.html#cb1650-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-262">See Also</h3>
<p><a href="ctype.html#man-ispunct"><code>ispunct()</code></a>, <a href="#man-iswspace"><code>iswspace()</code></a>, <a href="#man-iswalnum"><code>iswalnum()</code></a></p>
<hr>
<h2 data-number="70.10" id="man-iswspace"><span class="header-section-number">70.10</span> <code>iswspace()</code></h2>
<p>Test if a wide character is whitespace</p>
<h3 class="unnumbered unlisted" id="synopsis-276">Synopsis</h3>
<div class="sourceCode" id="cb1651"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1651-1"><a href="wctype.html#cb1651-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1651-2"><a href="wctype.html#cb1651-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1651-3"><a href="wctype.html#cb1651-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswspace<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-276">Description</h3>
<p>Tests if <code>c</code> is a whitespace character. These are
probably:</p>
<ul>
<li>Space (<code>' '</code>)</li>
<li>Formfeed (<code>'\f'</code>)</li>
<li>Newline (<code>'\n'</code>)</li>
<li>Carriage Return (<code>'\r'</code>)</li>
<li>Horizontal Tab (<code>'\t'</code>)</li>
<li>Vertical Tab (<code>'\v'</code>)</li>
</ul>
<p>Other locales might specify other whitespace characters.
<code>iswalnum()</code>, <code>iswgraph()</code>, and
<code>iswpunct()</code> are all false for all whitespace characters.</p>
<h3 class="unnumbered unlisted" id="return-value-274">Return Value</h3>
<p>True if the character is whitespace.</p>
<h3 class="unnumbered unlisted" id="example-278">Example</h3>
<p>Results may vary based on locale.</p>
<div class="sourceCode" id="cb1652"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1652-1"><a href="wctype.html#cb1652-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1652-2"><a href="wctype.html#cb1652-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1652-3"><a href="wctype.html#cb1652-3"></a></span>
<span id="cb1652-4"><a href="wctype.html#cb1652-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1652-5"><a href="wctype.html#cb1652-5"></a><span class="op">{</span></span>
<span id="cb1652-6"><a href="wctype.html#cb1652-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1652-7"><a href="wctype.html#cb1652-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1652-8"><a href="wctype.html#cb1652-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswspace<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1652-9"><a href="wctype.html#cb1652-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswspace<span class="op">(</span>L<span class="ch">'\n'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1652-10"><a href="wctype.html#cb1652-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswspace<span class="op">(</span>L<span class="ch">'\t'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>  <span class="co">// yes</span></span>
<span id="cb1652-11"><a href="wctype.html#cb1652-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswspace<span class="op">(</span>L<span class="ch">','</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1652-12"><a href="wctype.html#cb1652-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswspace<span class="op">(</span>L<span class="ch">'!'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1652-13"><a href="wctype.html#cb1652-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswspace<span class="op">(</span>L<span class="ch">'c'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1652-14"><a href="wctype.html#cb1652-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-263">See Also</h3>
<p><a href="ctype.html#man-isspace"><code>isspace()</code></a>, <a href="#man-iswblank"><code>iswblank()</code></a></p>
<hr>
<h2 data-number="70.11" id="man-iswupper"><span class="header-section-number">70.11</span> <code>iswupper()</code></h2>
<p>Tests if a wide character is uppercase</p>
<h3 class="unnumbered unlisted" id="synopsis-277">Synopsis</h3>
<div class="sourceCode" id="cb1653"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1653-1"><a href="wctype.html#cb1653-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1653-2"><a href="wctype.html#cb1653-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1653-3"><a href="wctype.html#cb1653-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswupper<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-277">Description</h3>
<p>Tests if a character is uppercase in the current locale.</p>
<p>To be uppercase, the following must be true:</p>
<div class="sourceCode" id="cb1654"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1654-1"><a href="wctype.html#cb1654-1" aria-hidden="true" tabindex="-1"></a><span class="op">!</span>iscntrl<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isdigit<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>ispunct<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> <span class="op">!</span>isspace<span class="op">(</span>c<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-275">Return Value</h3>
<p>Returns true if the wide character is uppercase.</p>
<h3 class="unnumbered unlisted" id="example-279">Example</h3>
<div class="sourceCode" id="cb1655"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1655-1"><a href="wctype.html#cb1655-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1655-2"><a href="wctype.html#cb1655-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1655-3"><a href="wctype.html#cb1655-3"></a></span>
<span id="cb1655-4"><a href="wctype.html#cb1655-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1655-5"><a href="wctype.html#cb1655-5"></a><span class="op">{</span></span>
<span id="cb1655-6"><a href="wctype.html#cb1655-6"></a>    <span class="co">//                   testing this char</span></span>
<span id="cb1655-7"><a href="wctype.html#cb1655-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1655-8"><a href="wctype.html#cb1655-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswupper<span class="op">(</span>L<span class="ch">'B'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1655-9"><a href="wctype.html#cb1655-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswupper<span class="op">(</span>L<span class="ch">'c'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1655-10"><a href="wctype.html#cb1655-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswupper<span class="op">(</span>L<span class="ch">'0'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1655-11"><a href="wctype.html#cb1655-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswupper<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1655-12"><a href="wctype.html#cb1655-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswupper<span class="op">(</span>L<span class="ch">' '</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1655-13"><a href="wctype.html#cb1655-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-264">See Also</h3>
<p><a href="ctype.html#man-isupper"><code>isupper()</code></a>, <a href="#man-iswlower"><code>iswlower()</code></a>, <a href="#man-iswalpha"><code>iswalpha()</code></a>, <a href="#man-towupper"><code>towupper()</code></a>, <a href="#man-towlower"><code>towlower()</code></a></p>
<hr>
<h2 data-number="70.12" id="man-iswxdigit"><span class="header-section-number">70.12</span> <code>iswxdigit()</code></h2>
<p>Tests if a wide character is a hexadecimal digit</p>
<h3 class="unnumbered unlisted" id="synopsis-278">Synopsis</h3>
<div class="sourceCode" id="cb1656"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1656-1"><a href="wctype.html#cb1656-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1656-2"><a href="wctype.html#cb1656-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1656-3"><a href="wctype.html#cb1656-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswxdigit<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-278">Description</h3>
<p>Returns true if the wide character is a hexadecimal digit. Namely if
it’s <code>0</code>-<code>9</code>, <code>a</code>-<code>f</code>, or
<code>A</code>-<code>F</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-276">Return Value</h3>
<p>True if the character is a hexadecimal digit.</p>
<h3 class="unnumbered unlisted" id="example-280">Example</h3>
<div class="sourceCode" id="cb1657"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1657-1"><a href="wctype.html#cb1657-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1657-2"><a href="wctype.html#cb1657-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1657-3"><a href="wctype.html#cb1657-3"></a></span>
<span id="cb1657-4"><a href="wctype.html#cb1657-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1657-5"><a href="wctype.html#cb1657-5"></a><span class="op">{</span></span>
<span id="cb1657-6"><a href="wctype.html#cb1657-6"></a>    <span class="co">//                    testing this char</span></span>
<span id="cb1657-7"><a href="wctype.html#cb1657-7"></a>    <span class="co">//                            v</span></span>
<span id="cb1657-8"><a href="wctype.html#cb1657-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswxdigit<span class="op">(</span>L<span class="ch">'B'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1657-9"><a href="wctype.html#cb1657-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswxdigit<span class="op">(</span>L<span class="ch">'c'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1657-10"><a href="wctype.html#cb1657-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswxdigit<span class="op">(</span>L<span class="ch">'2'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// yes</span></span>
<span id="cb1657-11"><a href="wctype.html#cb1657-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswxdigit<span class="op">(</span>L<span class="ch">'G'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1657-12"><a href="wctype.html#cb1657-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> iswxdigit<span class="op">(</span>L<span class="ch">'?'</span><span class="op">)?</span> L<span class="st">"yes"</span><span class="op">:</span> L<span class="st">"no"</span><span class="op">);</span>   <span class="co">// no</span></span>
<span id="cb1657-13"><a href="wctype.html#cb1657-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-265">See Also</h3>
<p><a href="ctype.html#man-isxdigit"><code>isxdigit()</code></a>, <a href="#man-iswdigit"><code>iswdigit()</code></a></p>
<hr>
<h2 data-number="70.13" id="man-iswctype"><span class="header-section-number">70.13</span> <code>iswctype()</code></h2>
<p>Determine wide character classification</p>
<h3 class="unnumbered unlisted" id="synopsis-279">Synopsis</h3>
<div class="sourceCode" id="cb1658"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1658-1"><a href="wctype.html#cb1658-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1658-2"><a href="wctype.html#cb1658-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1658-3"><a href="wctype.html#cb1658-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> iswctype<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">,</span> wctype_t desc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-279">Description</h3>
<p>This is the Swiss Army knife of classification functions; it’s all
the other ones rolled into one.</p>
<p>You call it with something like this:</p>
<div class="sourceCode" id="cb1659"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1659-1"><a href="wctype.html#cb1659-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(</span>iswctype<span class="op">(</span>c<span class="op">,</span> wctype<span class="op">(</span><span class="st">"digit"</span><span class="op">)))</span>  <span class="co">// or "alpha" or "space" or...</span></span></code></pre></div>
<p>and it behaves just like you’d called:</p>
<div class="sourceCode" id="cb1660"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1660-1"><a href="wctype.html#cb1660-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(</span>iswdigit<span class="op">(</span>c<span class="op">))</span></span></code></pre></div>
<p>The difference is that you can specify the type of matching you want
to do as a string at runtime, which might be convenient.</p>
<p><code>iswctype()</code> relies on the return value from the <a href="#man-wctype"><code>wctype()</code></a> call to get its work
done.</p>
<p>Stolen from the spec, here are the <code>iswctype()</code> calls and
their equivalents:</p>
<table>
<thead>
<tr class="header">
<th><code>iswctype()</code> call</th>
<th>Hard-coded equivalent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>iswctype(c, wctype("alnum"))</code></td>
<td><code>iswalnum(c)</code></td>
</tr>
<tr class="even">
<td><code>iswctype(c, wctype("alpha"))</code></td>
<td><code>iswalpha(c)</code></td>
</tr>
<tr class="odd">
<td><code>iswctype(c, wctype("blank"))</code></td>
<td><code>iswblank(c)</code></td>
</tr>
<tr class="even">
<td><code>iswctype(c, wctype("cntrl"))</code></td>
<td><code>iswcntrl(c)</code></td>
</tr>
<tr class="odd">
<td><code>iswctype(c, wctype("digit"))</code></td>
<td><code>iswdigit(c)</code></td>
</tr>
<tr class="even">
<td><code>iswctype(c, wctype("graph"))</code></td>
<td><code>iswgraph(c)</code></td>
</tr>
<tr class="odd">
<td><code>iswctype(c, wctype("lower"))</code></td>
<td><code>iswlower(c)</code></td>
</tr>
<tr class="even">
<td><code>iswctype(c, wctype("print"))</code></td>
<td><code>iswprint(c)</code></td>
</tr>
<tr class="odd">
<td><code>iswctype(c, wctype("punct"))</code></td>
<td><code>iswpunct(c)</code></td>
</tr>
<tr class="even">
<td><code>iswctype(c, wctype("space"))</code></td>
<td><code>iswspace(c)</code></td>
</tr>
<tr class="odd">
<td><code>iswctype(c, wctype("upper"))</code></td>
<td><code>iswupper(c)</code></td>
</tr>
<tr class="even">
<td><code>iswctype(c, wctype("xdigit"))</code></td>
<td><code>iswxdigit(c)</code></td>
</tr>
</tbody>
</table>
<p>See the <a href="wctype.html#man-wctype"><code>wctype()</code> documentation</a>
for how that helper function works.</p>
<h3 class="unnumbered unlisted" id="return-value-277">Return Value</h3>
<p>Returns true if the wide character <code>wc</code> matches the
character class in <code>desc</code>.</p>
<h3 class="unnumbered unlisted" id="example-281">Example</h3>
<p>Test for a given character classification at when the classification
isn’t known at compile time:</p>
<div class="sourceCode" id="cb1661"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1661-1"><a href="wctype.html#cb1661-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">  </span><span class="co">// for fflush(stdout)</span></span>
<span id="cb1661-2"><a href="wctype.html#cb1661-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1661-3"><a href="wctype.html#cb1661-3"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1661-4"><a href="wctype.html#cb1661-4"></a></span>
<span id="cb1661-5"><a href="wctype.html#cb1661-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1661-6"><a href="wctype.html#cb1661-6"></a><span class="op">{</span></span>
<span id="cb1661-7"><a href="wctype.html#cb1661-7"></a>    <span class="dt">wchar_t</span> c<span class="op">;</span>        <span class="co">// Holds a single wide character (to test)</span></span>
<span id="cb1661-8"><a href="wctype.html#cb1661-8"></a>    <span class="dt">char</span> desc<span class="op">[</span><span class="dv">128</span><span class="op">];</span>   <span class="co">// Holds the character class</span></span>
<span id="cb1661-9"><a href="wctype.html#cb1661-9"></a></span>
<span id="cb1661-10"><a href="wctype.html#cb1661-10"></a>    <span class="co">// Get the character and classification from the user</span></span>
<span id="cb1661-11"><a href="wctype.html#cb1661-11"></a>    wprintf<span class="op">(</span>L<span class="st">"Enter a character and character class: "</span><span class="op">);</span></span>
<span id="cb1661-12"><a href="wctype.html#cb1661-12"></a>    fflush<span class="op">(</span>stdout<span class="op">);</span></span>
<span id="cb1661-13"><a href="wctype.html#cb1661-13"></a>    wscanf<span class="op">(</span>L<span class="st">"%lc %s"</span><span class="op">,</span> <span class="op">&amp;</span>c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1661-14"><a href="wctype.html#cb1661-14"></a></span>
<span id="cb1661-15"><a href="wctype.html#cb1661-15"></a>    <span class="co">// Compute the type from the given class</span></span>
<span id="cb1661-16"><a href="wctype.html#cb1661-16"></a>    wctype_t t <span class="op">=</span> wctype<span class="op">(</span>desc<span class="op">);</span></span>
<span id="cb1661-17"><a href="wctype.html#cb1661-17"></a></span>
<span id="cb1661-18"><a href="wctype.html#cb1661-18"></a>    <span class="cf">if</span> <span class="op">(</span>t <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1661-19"><a href="wctype.html#cb1661-19"></a>        <span class="co">// If the type is 0, it's an unknown class</span></span>
<span id="cb1661-20"><a href="wctype.html#cb1661-20"></a>        wprintf<span class="op">(</span>L<span class="st">"Unknown character class: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1661-21"><a href="wctype.html#cb1661-21"></a>    <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1661-22"><a href="wctype.html#cb1661-22"></a>        <span class="co">// Otherwise, let's test the character and see if its that</span></span>
<span id="cb1661-23"><a href="wctype.html#cb1661-23"></a>        <span class="co">// classification</span></span>
<span id="cb1661-24"><a href="wctype.html#cb1661-24"></a>        <span class="cf">if</span> <span class="op">(</span>iswctype<span class="op">(</span>c<span class="op">,</span> t<span class="op">))</span></span>
<span id="cb1661-25"><a href="wctype.html#cb1661-25"></a>            wprintf<span class="op">(</span>L<span class="st">"Yes! '%lc' is %s!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1661-26"><a href="wctype.html#cb1661-26"></a>        <span class="cf">else</span></span>
<span id="cb1661-27"><a href="wctype.html#cb1661-27"></a>            wprintf<span class="op">(</span>L<span class="st">"Nope! '%lc' is not %s.</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1661-28"><a href="wctype.html#cb1661-28"></a>    <span class="op">}</span></span>
<span id="cb1661-29"><a href="wctype.html#cb1661-29"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1662"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1662-1"><a href="wctype.html#cb1662-1" aria-hidden="true" tabindex="-1"></a>Enter a character and character class: 5 digit</span>
<span id="cb1662-2"><a href="wctype.html#cb1662-2" aria-hidden="true" tabindex="-1"></a>Yes! '5' is digit!</span>
<span id="cb1662-3"><a href="wctype.html#cb1662-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1662-4"><a href="wctype.html#cb1662-4" aria-hidden="true" tabindex="-1"></a>Enter a character and character class: b digit</span>
<span id="cb1662-5"><a href="wctype.html#cb1662-5" aria-hidden="true" tabindex="-1"></a>Nope! 'b' is not digit.</span>
<span id="cb1662-6"><a href="wctype.html#cb1662-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1662-7"><a href="wctype.html#cb1662-7" aria-hidden="true" tabindex="-1"></a>Enter a character and character class: x alnum</span>
<span id="cb1662-8"><a href="wctype.html#cb1662-8" aria-hidden="true" tabindex="-1"></a>Yes! 'x' is alnum!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-266">See Also</h3>
<p><a href="wctype.html#man-wctype"><code>wctype()</code></a></p>
<hr>
<h2 data-number="70.14" id="man-wctype"><span class="header-section-number">70.14</span> <code>wctype()</code></h2>
<p>Helper function for <code>iswctype()</code></p>
<h3 class="unnumbered unlisted" id="synopsis-280">Synopsis</h3>
<div class="sourceCode" id="cb1663"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1663-1"><a href="wctype.html#cb1663-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1663-2"><a href="wctype.html#cb1663-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1663-3"><a href="wctype.html#cb1663-3" aria-hidden="true" tabindex="-1"></a>wctype_t wctype<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>property<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-280">Description</h3>
<p>This function returns an opaque value for the given
<code>property</code> that is meant to be passed as the second argument
to <a href="wctype.html#man-iswctype"><code>iswctype()</code></a>.</p>
<p>The returned value is of type <code>wctype_t</code>.</p>
<p>Valid properties in all locales are:</p>
<div class="sourceCode" id="cb1664"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1664-1"><a href="wctype.html#cb1664-1" aria-hidden="true" tabindex="-1"></a><span class="st">"alnum"</span>   <span class="st">"alpha"</span>   <span class="st">"blank"</span>   <span class="st">"cntrl"</span></span>
<span id="cb1664-2"><a href="wctype.html#cb1664-2" aria-hidden="true" tabindex="-1"></a><span class="st">"digit"</span>   <span class="st">"graph"</span>   <span class="st">"lower"</span>   <span class="st">"print"</span></span>
<span id="cb1664-3"><a href="wctype.html#cb1664-3" aria-hidden="true" tabindex="-1"></a><span class="st">"punct"</span>   <span class="st">"space"</span>   <span class="st">"upper"</span>   <span class="st">"xdigit"</span></span></code></pre></div>
<p>Other properties might be defined as determined by the
<code>LC_CTYPE</code> category of the current locale.</p>
<p>See the <a href="wctype.html#man-iswctype"><code>iswctype()</code> reference
page</a> for more usage details.</p>
<h3 class="unnumbered unlisted" id="return-value-278">Return Value</h3>
<p>Returns the <code>wctype_t</code> value associated with the given
<code>property</code>.</p>
<p>If an invalid value is passed for <code>property</code>, returns
<code>0</code>.</p>
<h3 class="unnumbered unlisted" id="example-282">Example</h3>
<p>Test for a given character classification at when the classification
isn’t known at compile time:</p>
<div class="sourceCode" id="cb1665"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1665-1"><a href="wctype.html#cb1665-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">  </span><span class="co">// for fflush(stdout)</span></span>
<span id="cb1665-2"><a href="wctype.html#cb1665-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1665-3"><a href="wctype.html#cb1665-3"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1665-4"><a href="wctype.html#cb1665-4"></a></span>
<span id="cb1665-5"><a href="wctype.html#cb1665-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1665-6"><a href="wctype.html#cb1665-6"></a><span class="op">{</span></span>
<span id="cb1665-7"><a href="wctype.html#cb1665-7"></a>    <span class="dt">wchar_t</span> c<span class="op">;</span>        <span class="co">// Holds a single wide character (to test)</span></span>
<span id="cb1665-8"><a href="wctype.html#cb1665-8"></a>    <span class="dt">char</span> desc<span class="op">[</span><span class="dv">128</span><span class="op">];</span>   <span class="co">// Holds the character class</span></span>
<span id="cb1665-9"><a href="wctype.html#cb1665-9"></a></span>
<span id="cb1665-10"><a href="wctype.html#cb1665-10"></a>    <span class="co">// Get the character and classification from the user</span></span>
<span id="cb1665-11"><a href="wctype.html#cb1665-11"></a>    wprintf<span class="op">(</span>L<span class="st">"Enter a character and character class: "</span><span class="op">);</span></span>
<span id="cb1665-12"><a href="wctype.html#cb1665-12"></a>    fflush<span class="op">(</span>stdout<span class="op">);</span></span>
<span id="cb1665-13"><a href="wctype.html#cb1665-13"></a>    wscanf<span class="op">(</span>L<span class="st">"%lc %s"</span><span class="op">,</span> <span class="op">&amp;</span>c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1665-14"><a href="wctype.html#cb1665-14"></a></span>
<span id="cb1665-15"><a href="wctype.html#cb1665-15"></a>    <span class="co">// Compute the type from the given class</span></span>
<span id="cb1665-16"><a href="wctype.html#cb1665-16"></a>    wctype_t t <span class="op">=</span> wctype<span class="op">(</span>desc<span class="op">);</span></span>
<span id="cb1665-17"><a href="wctype.html#cb1665-17"></a></span>
<span id="cb1665-18"><a href="wctype.html#cb1665-18"></a>    <span class="cf">if</span> <span class="op">(</span>t <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1665-19"><a href="wctype.html#cb1665-19"></a>        <span class="co">// If the type is 0, it's an unknown class</span></span>
<span id="cb1665-20"><a href="wctype.html#cb1665-20"></a>        wprintf<span class="op">(</span>L<span class="st">"Unknown character class: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1665-21"><a href="wctype.html#cb1665-21"></a>    <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1665-22"><a href="wctype.html#cb1665-22"></a>        <span class="co">// Otherwise, let's test the character and see if its that</span></span>
<span id="cb1665-23"><a href="wctype.html#cb1665-23"></a>        <span class="co">// classification</span></span>
<span id="cb1665-24"><a href="wctype.html#cb1665-24"></a>        <span class="cf">if</span> <span class="op">(</span>iswctype<span class="op">(</span>c<span class="op">,</span> t<span class="op">))</span></span>
<span id="cb1665-25"><a href="wctype.html#cb1665-25"></a>            wprintf<span class="op">(</span>L<span class="st">"Yes! '%lc' is %s!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1665-26"><a href="wctype.html#cb1665-26"></a>        <span class="cf">else</span></span>
<span id="cb1665-27"><a href="wctype.html#cb1665-27"></a>            wprintf<span class="op">(</span>L<span class="st">"Nope! '%lc' is not %s.</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1665-28"><a href="wctype.html#cb1665-28"></a>    <span class="op">}</span></span>
<span id="cb1665-29"><a href="wctype.html#cb1665-29"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1666"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1666-1"><a href="wctype.html#cb1666-1" aria-hidden="true" tabindex="-1"></a>Enter a character and character class: 5 digit</span>
<span id="cb1666-2"><a href="wctype.html#cb1666-2" aria-hidden="true" tabindex="-1"></a>Yes! '5' is digit!</span>
<span id="cb1666-3"><a href="wctype.html#cb1666-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1666-4"><a href="wctype.html#cb1666-4" aria-hidden="true" tabindex="-1"></a>Enter a character and character class: b digit</span>
<span id="cb1666-5"><a href="wctype.html#cb1666-5" aria-hidden="true" tabindex="-1"></a>Nope! 'b' is not digit.</span>
<span id="cb1666-6"><a href="wctype.html#cb1666-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1666-7"><a href="wctype.html#cb1666-7" aria-hidden="true" tabindex="-1"></a>Enter a character and character class: x alnum</span>
<span id="cb1666-8"><a href="wctype.html#cb1666-8" aria-hidden="true" tabindex="-1"></a>Yes! 'x' is alnum!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-267">See Also</h3>
<p><a href="wctype.html#man-iswctype"><code>iswctype()</code></a></p>
<hr>
<h2 data-number="70.15" id="man-towlower"><span class="header-section-number">70.15</span> <code>towlower()</code></h2>
<p>Convert an uppercase wide character to lowercase</p>
<h3 class="unnumbered unlisted" id="synopsis-281">Synopsis</h3>
<div class="sourceCode" id="cb1667"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1667-1"><a href="wctype.html#cb1667-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1667-2"><a href="wctype.html#cb1667-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1667-3"><a href="wctype.html#cb1667-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> towlower<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-281">Description</h3>
<p>If the character is upper (i.e.&nbsp;<code>iswupper(c)</code> is true),
this function returns the corresponding lowercase letter.</p>
<p>Different locales might have different upper and lowercase
letters.</p>
<h3 class="unnumbered unlisted" id="return-value-279">Return Value</h3>
<p>If the letter <code>wc</code> is uppercase, a lowercase version of
that letter will be returned according to the current locale.</p>
<p>If the letter is not uppercase, <code>wc</code> is returned
unchanged.</p>
<h3 class="unnumbered unlisted" id="example-283">Example</h3>
<div class="sourceCode" id="cb1668"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1668-1"><a href="wctype.html#cb1668-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1668-2"><a href="wctype.html#cb1668-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1668-3"><a href="wctype.html#cb1668-3"></a></span>
<span id="cb1668-4"><a href="wctype.html#cb1668-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1668-5"><a href="wctype.html#cb1668-5"></a><span class="op">{</span></span>
<span id="cb1668-6"><a href="wctype.html#cb1668-6"></a>    <span class="co">//                  changing this char</span></span>
<span id="cb1668-7"><a href="wctype.html#cb1668-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1668-8"><a href="wctype.html#cb1668-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> towlower<span class="op">(</span>L<span class="ch">'B'</span><span class="op">));</span>  <span class="co">// b (made lowercase!)</span></span>
<span id="cb1668-9"><a href="wctype.html#cb1668-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> towlower<span class="op">(</span>L<span class="ch">'e'</span><span class="op">));</span>  <span class="co">// e (unchanged)</span></span>
<span id="cb1668-10"><a href="wctype.html#cb1668-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> towlower<span class="op">(</span>L<span class="ch">'!'</span><span class="op">));</span>  <span class="co">// ! (unchanged)</span></span>
<span id="cb1668-11"><a href="wctype.html#cb1668-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-268">See Also</h3>
<p><a href="ctype.html#man-tolower"><code>tolower()</code></a>, <a href="#man-towupper"><code>towupper()</code></a>, <a href="#man-iswlower"><code>iswlower()</code></a>, <a href="#man-iswupper"><code>iswupper()</code></a></p>
<hr>
<h2 data-number="70.16" id="man-towupper"><span class="header-section-number">70.16</span> <code>towupper()</code></h2>
<p>Convert a lowercase wide character to uppercase</p>
<h3 class="unnumbered unlisted" id="synopsis-282">Synopsis</h3>
<div class="sourceCode" id="cb1669"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1669-1"><a href="wctype.html#cb1669-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1669-2"><a href="wctype.html#cb1669-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1669-3"><a href="wctype.html#cb1669-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> towupper<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-282">Description</h3>
<p>If the character is lower (i.e.&nbsp;<code>iswlower(c)</code> is true),
this function returns the corresponding uppercase letter.</p>
<p>Different locales might have different upper and lowercase
letters.</p>
<h3 class="unnumbered unlisted" id="return-value-280">Return Value</h3>
<p>If the letter <code>wc</code> is lowercase, an uppercase version of
that letter will be returned according to the current locale.</p>
<p>If the letter is not lowercase, <code>wc</code> is returned
unchanged.</p>
<h3 class="unnumbered unlisted" id="example-284">Example</h3>
<div class="sourceCode" id="cb1670"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1670-1"><a href="wctype.html#cb1670-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1670-2"><a href="wctype.html#cb1670-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1670-3"><a href="wctype.html#cb1670-3"></a></span>
<span id="cb1670-4"><a href="wctype.html#cb1670-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1670-5"><a href="wctype.html#cb1670-5"></a><span class="op">{</span></span>
<span id="cb1670-6"><a href="wctype.html#cb1670-6"></a>    <span class="co">//                  changing this char</span></span>
<span id="cb1670-7"><a href="wctype.html#cb1670-7"></a>    <span class="co">//                           v</span></span>
<span id="cb1670-8"><a href="wctype.html#cb1670-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> towupper<span class="op">(</span>L<span class="ch">'B'</span><span class="op">));</span>  <span class="co">// B (unchanged)</span></span>
<span id="cb1670-9"><a href="wctype.html#cb1670-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> towupper<span class="op">(</span>L<span class="ch">'e'</span><span class="op">));</span>  <span class="co">// E (made uppercase!)</span></span>
<span id="cb1670-10"><a href="wctype.html#cb1670-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> towupper<span class="op">(</span>L<span class="ch">'!'</span><span class="op">));</span>  <span class="co">// ! (unchanged)</span></span>
<span id="cb1670-11"><a href="wctype.html#cb1670-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-269">See Also</h3>
<p><a href="ctype.html#man-toupper"><code>toupper()</code></a>, <a href="#man-towlower"><code>towlower()</code></a>, <a href="#man-iswlower"><code>iswlower()</code></a>, <a href="#man-iswupper"><code>iswupper()</code></a></p>
<hr>
<h2 data-number="70.17" id="man-towctrans"><span class="header-section-number">70.17</span> <code>towctrans()</code></h2>
<p>Convert wide characters to upper or lowercase</p>
<h3 class="unnumbered unlisted" id="synopsis-283">Synopsis</h3>
<div class="sourceCode" id="cb1671"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1671-1"><a href="wctype.html#cb1671-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1671-2"><a href="wctype.html#cb1671-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1671-3"><a href="wctype.html#cb1671-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> towctrans<span class="op">(</span><span class="dt">wint_t</span> wc<span class="op">,</span> wctrans_t desc<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-283">Description</h3>
<p>This is the Swiss Army knife of character conversion functions; it’s
all the other ones rolled into one. And by “all the other ones” I mean
<code>towupper()</code> and <code>towlower()</code>, since those are the
only ones there are.</p>
<p>You call it with something like this:</p>
<div class="sourceCode" id="cb1672"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1672-1"><a href="wctype.html#cb1672-1" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> <span class="op">(</span>towctrans<span class="op">(</span>c<span class="op">,</span> wctrans<span class="op">(</span><span class="st">"toupper"</span><span class="op">)))</span>  <span class="co">// or "tolower"</span></span></code></pre></div>
<p>and it behaves just like you’d called:</p>
<div class="sourceCode" id="cb1673"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1673-1"><a href="wctype.html#cb1673-1" aria-hidden="true" tabindex="-1"></a>towupper<span class="op">(</span>c<span class="op">);</span></span></code></pre></div>
<p>The difference is that you can specify the type of conversion you
want to do as a string at runtime, which might be convenient.</p>
<p><code>towctrans()</code> relies on the return value from the <a href="#man-wctrans"><code>wctrans()</code></a> call to get its work
done.</p>
<table>
<thead>
<tr class="header">
<th><code>towctrans()</code> call</th>
<th>Hard-coded equivalent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>towctrans(c, wctrans("toupper"))</code></td>
<td><code>towupper(c)</code></td>
</tr>
<tr class="even">
<td><code>towctrans(c, wctrans("tolower"))</code></td>
<td><code>towlower(c)</code></td>
</tr>
</tbody>
</table>
<p>See the <a href="wctype.html#man-wctrans"><code>wctrans()</code>
documentation</a> for how that helper function works.</p>
<h3 class="unnumbered unlisted" id="return-value-281">Return Value</h3>
<p>Returns the character <code>wc</code> as if run through
<code>towupper()</code> or <code>towlower()</code>, depending on the
value of <code>desc</code>.</p>
<p>If the character already matches the classification, it is returned
as-is.</p>
<h3 class="unnumbered unlisted" id="example-285">Example</h3>
<div class="sourceCode" id="cb1674"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1674-1"><a href="wctype.html#cb1674-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">  </span><span class="co">// for fflush(stdout)</span></span>
<span id="cb1674-2"><a href="wctype.html#cb1674-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1674-3"><a href="wctype.html#cb1674-3"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1674-4"><a href="wctype.html#cb1674-4"></a></span>
<span id="cb1674-5"><a href="wctype.html#cb1674-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1674-6"><a href="wctype.html#cb1674-6"></a><span class="op">{</span></span>
<span id="cb1674-7"><a href="wctype.html#cb1674-7"></a>    <span class="dt">wchar_t</span> c<span class="op">;</span>        <span class="co">// Holds a single wide character (to test)</span></span>
<span id="cb1674-8"><a href="wctype.html#cb1674-8"></a>    <span class="dt">char</span> desc<span class="op">[</span><span class="dv">128</span><span class="op">];</span>   <span class="co">// Holds the conversion type</span></span>
<span id="cb1674-9"><a href="wctype.html#cb1674-9"></a></span>
<span id="cb1674-10"><a href="wctype.html#cb1674-10"></a>    <span class="co">// Get the character and conversion type from the user</span></span>
<span id="cb1674-11"><a href="wctype.html#cb1674-11"></a>    wprintf<span class="op">(</span>L<span class="st">"Enter a character and conversion type: "</span><span class="op">);</span></span>
<span id="cb1674-12"><a href="wctype.html#cb1674-12"></a>    fflush<span class="op">(</span>stdout<span class="op">);</span></span>
<span id="cb1674-13"><a href="wctype.html#cb1674-13"></a>    wscanf<span class="op">(</span>L<span class="st">"%lc %s"</span><span class="op">,</span> <span class="op">&amp;</span>c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1674-14"><a href="wctype.html#cb1674-14"></a></span>
<span id="cb1674-15"><a href="wctype.html#cb1674-15"></a>    <span class="co">// Compute the type from the given conversion type</span></span>
<span id="cb1674-16"><a href="wctype.html#cb1674-16"></a>    wctrans_t t <span class="op">=</span> wctrans<span class="op">(</span>desc<span class="op">);</span></span>
<span id="cb1674-17"><a href="wctype.html#cb1674-17"></a></span>
<span id="cb1674-18"><a href="wctype.html#cb1674-18"></a>    <span class="cf">if</span> <span class="op">(</span>t <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1674-19"><a href="wctype.html#cb1674-19"></a>        <span class="co">// If the type is 0, it's an unknown conversion type</span></span>
<span id="cb1674-20"><a href="wctype.html#cb1674-20"></a>        wprintf<span class="op">(</span>L<span class="st">"Unknown conversion: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1674-21"><a href="wctype.html#cb1674-21"></a>    <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1674-22"><a href="wctype.html#cb1674-22"></a>        <span class="co">// Otherwise, let's do the conversion</span></span>
<span id="cb1674-23"><a href="wctype.html#cb1674-23"></a>        <span class="dt">wint_t</span> result <span class="op">=</span> towctrans<span class="op">(</span>c<span class="op">,</span> t<span class="op">);</span></span>
<span id="cb1674-24"><a href="wctype.html#cb1674-24"></a>        wprintf<span class="op">(</span>L<span class="st">"'%lc' -&gt; %s -&gt; '%lc'</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">,</span> desc<span class="op">,</span> result<span class="op">);</span></span>
<span id="cb1674-25"><a href="wctype.html#cb1674-25"></a>    <span class="op">}</span></span>
<span id="cb1674-26"><a href="wctype.html#cb1674-26"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1675"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1675-1"><a href="wctype.html#cb1675-1" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: b toupper</span>
<span id="cb1675-2"><a href="wctype.html#cb1675-2" aria-hidden="true" tabindex="-1"></a>'b' -&gt; toupper -&gt; 'B'</span>
<span id="cb1675-3"><a href="wctype.html#cb1675-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1675-4"><a href="wctype.html#cb1675-4" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: B toupper</span>
<span id="cb1675-5"><a href="wctype.html#cb1675-5" aria-hidden="true" tabindex="-1"></a>'B' -&gt; toupper -&gt; 'B'</span>
<span id="cb1675-6"><a href="wctype.html#cb1675-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1675-7"><a href="wctype.html#cb1675-7" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: B tolower</span>
<span id="cb1675-8"><a href="wctype.html#cb1675-8" aria-hidden="true" tabindex="-1"></a>'B' -&gt; tolower -&gt; 'b'</span>
<span id="cb1675-9"><a href="wctype.html#cb1675-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1675-10"><a href="wctype.html#cb1675-10" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: ! toupper</span>
<span id="cb1675-11"><a href="wctype.html#cb1675-11" aria-hidden="true" tabindex="-1"></a>'!' -&gt; toupper -&gt; '!'</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-270">See Also</h3>
<p><a href="wctype.html#man-wctrans"><code>wctrans()</code></a>, <a href="#man-towupper"><code>towupper()</code></a>, <a href="#man-towlower"><code>towlower()</code></a></p>
<hr>
<h2 data-number="70.18" id="man-wctrans"><span class="header-section-number">70.18</span> <code>wctrans()</code></h2>
<p>Helper function for <code>towctrans()</code></p>
<h3 class="unnumbered unlisted" id="synopsis-284">Synopsis</h3>
<div class="sourceCode" id="cb1676"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1676-1"><a href="wctype.html#cb1676-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1676-2"><a href="wctype.html#cb1676-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1676-3"><a href="wctype.html#cb1676-3" aria-hidden="true" tabindex="-1"></a>wctrans_t wctrans<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>property<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-284">Description</h3>
<p>This is a helper function for generating the second argument to <a href="#man-towctrans"><code>towctrans()</code></a>.</p>
<p>You can pass in one of two things for the <code>property</code>:</p>
<ul>
<li><code>toupper</code> to make <code>towctrans()</code> behave like
<code>towupper()</code></li>
<li><code>tolower</code> to make <code>towctrans()</code> behave like
<code>towlower()</code></li>
</ul>
<h3 class="unnumbered unlisted" id="return-value-282">Return Value</h3>
<p>On success, returns a value that can be used as the <code>desc</code>
argument to <code>towctrans()</code>.</p>
<p>Otherwise, if the <code>property</code> isn’t recognized, returns
<code>0</code>.</p>
<h3 class="unnumbered unlisted" id="example-286">Example</h3>
<div class="sourceCode" id="cb1677"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1677-1"><a href="wctype.html#cb1677-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">  </span><span class="co">// for fflush(stdout)</span></span>
<span id="cb1677-2"><a href="wctype.html#cb1677-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1677-3"><a href="wctype.html#cb1677-3"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1677-4"><a href="wctype.html#cb1677-4"></a></span>
<span id="cb1677-5"><a href="wctype.html#cb1677-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1677-6"><a href="wctype.html#cb1677-6"></a><span class="op">{</span></span>
<span id="cb1677-7"><a href="wctype.html#cb1677-7"></a>    <span class="dt">wchar_t</span> c<span class="op">;</span>        <span class="co">// Holds a single wide character (to test)</span></span>
<span id="cb1677-8"><a href="wctype.html#cb1677-8"></a>    <span class="dt">char</span> desc<span class="op">[</span><span class="dv">128</span><span class="op">];</span>   <span class="co">// Holds the conversion type</span></span>
<span id="cb1677-9"><a href="wctype.html#cb1677-9"></a></span>
<span id="cb1677-10"><a href="wctype.html#cb1677-10"></a>    <span class="co">// Get the character and conversion type from the user</span></span>
<span id="cb1677-11"><a href="wctype.html#cb1677-11"></a>    wprintf<span class="op">(</span>L<span class="st">"Enter a character and conversion type: "</span><span class="op">);</span></span>
<span id="cb1677-12"><a href="wctype.html#cb1677-12"></a>    fflush<span class="op">(</span>stdout<span class="op">);</span></span>
<span id="cb1677-13"><a href="wctype.html#cb1677-13"></a>    wscanf<span class="op">(</span>L<span class="st">"%lc %s"</span><span class="op">,</span> <span class="op">&amp;</span>c<span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1677-14"><a href="wctype.html#cb1677-14"></a></span>
<span id="cb1677-15"><a href="wctype.html#cb1677-15"></a>    <span class="co">// Compute the type from the given conversion type</span></span>
<span id="cb1677-16"><a href="wctype.html#cb1677-16"></a>    wctrans_t t <span class="op">=</span> wctrans<span class="op">(</span>desc<span class="op">);</span></span>
<span id="cb1677-17"><a href="wctype.html#cb1677-17"></a></span>
<span id="cb1677-18"><a href="wctype.html#cb1677-18"></a>    <span class="cf">if</span> <span class="op">(</span>t <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1677-19"><a href="wctype.html#cb1677-19"></a>        <span class="co">// If the type is 0, it's an unknown conversion type</span></span>
<span id="cb1677-20"><a href="wctype.html#cb1677-20"></a>        wprintf<span class="op">(</span>L<span class="st">"Unknown conversion: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> desc<span class="op">);</span></span>
<span id="cb1677-21"><a href="wctype.html#cb1677-21"></a>    <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1677-22"><a href="wctype.html#cb1677-22"></a>        <span class="co">// Otherwise, let's do the conversion</span></span>
<span id="cb1677-23"><a href="wctype.html#cb1677-23"></a>        <span class="dt">wint_t</span> result <span class="op">=</span> towctrans<span class="op">(</span>c<span class="op">,</span> t<span class="op">);</span></span>
<span id="cb1677-24"><a href="wctype.html#cb1677-24"></a>        wprintf<span class="op">(</span>L<span class="st">"'%lc' -&gt; %s -&gt; '%lc'</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">,</span> desc<span class="op">,</span> result<span class="op">);</span></span>
<span id="cb1677-25"><a href="wctype.html#cb1677-25"></a>    <span class="op">}</span></span>
<span id="cb1677-26"><a href="wctype.html#cb1677-26"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1678"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1678-1"><a href="wctype.html#cb1678-1" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: b toupper</span>
<span id="cb1678-2"><a href="wctype.html#cb1678-2" aria-hidden="true" tabindex="-1"></a>'b' -&gt; toupper -&gt; 'B'</span>
<span id="cb1678-3"><a href="wctype.html#cb1678-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1678-4"><a href="wctype.html#cb1678-4" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: B toupper</span>
<span id="cb1678-5"><a href="wctype.html#cb1678-5" aria-hidden="true" tabindex="-1"></a>'B' -&gt; toupper -&gt; 'B'</span>
<span id="cb1678-6"><a href="wctype.html#cb1678-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1678-7"><a href="wctype.html#cb1678-7" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: B tolower</span>
<span id="cb1678-8"><a href="wctype.html#cb1678-8" aria-hidden="true" tabindex="-1"></a>'B' -&gt; tolower -&gt; 'b'</span>
<span id="cb1678-9"><a href="wctype.html#cb1678-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1678-10"><a href="wctype.html#cb1678-10" aria-hidden="true" tabindex="-1"></a>Enter a character and conversion type: ! toupper</span>
<span id="cb1678-11"><a href="wctype.html#cb1678-11" aria-hidden="true" tabindex="-1"></a>'!' -&gt; toupper -&gt; '!'</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-271">See Also</h3>
<p><a href="wctype.html#man-towctrans"><code>towctrans()</code></a></p>


</body>