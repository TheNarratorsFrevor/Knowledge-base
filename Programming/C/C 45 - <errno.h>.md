<body>
<hr>
<h1 data-number="45" id="errno"><span class="header-section-number">45</span> <code>&lt;errno.h&gt;</code>
Error Information</h1>
<table>
<thead>
<tr class="header">
<th>Variable</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="errno.html#man-errno"><code>errno</code></a></td>
<td>Holds the error status of the last call</td>
</tr>
</tbody>
</table>
<p>This header defines a single variable<a href="footnotes.html#fn222" class="footnote-ref" id="fnref222" role="doc-noteref"><sup>222</sup></a>, <code>errno</code>, that can be
checked to see if an error has occurred.</p>
<p><code>errno</code> is set to <code>0</code> on startup, but no
library function sets it to <code>0</code>. If you’re going to use
solely it to check for errors, set it to <code>0</code> before the call
and then check it after. Not only that, but if there’s no error, all
library functions will leave the value of <code>errno</code>
unchanged.</p>
<p>Often, though, you’ll get some error indication from the function
you’re calling then check <code>errno</code> to see what went wrong.</p>
<p>This is commonly used in conjunction with <a href="#man-perror"><code>perror()</code></a> to get a human-readable
error message that corresponds to the specific error.</p>
<p>Important Safety Tip: You should never make your own variable called
<code>errno</code>—that’s undefined behavior.</p>
<p>Note that the C Spec defines less than a handful of values
<code>errno</code> can take on. <a href="https://man.archlinux.org/man/errno.3.en">Unix defines a bunch
more</a><a href="footnotes.html#fn223" class="footnote-ref" id="fnref223" role="doc-noteref"><sup>223</sup></a>, <a href="https://docs.microsoft.com/en-us/cpp/c-runtime-library/errno-constants?view=msvc-160">as
does Windows</a><a href="footnotes.html#fn224" class="footnote-ref" id="fnref224" role="doc-noteref"><sup>224</sup></a>.</p>
<hr>
<h2 data-number="45.1" id="man-errno"><span class="header-section-number">45.1</span> <code>errno</code></h2>
<p>Holds the error status of the last call</p>
<h3 class="unnumbered unlisted" id="synopsis-39">Synopsis</h3>
<div class="sourceCode" id="cb909"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb909-1"><a href="errno.html#cb909-1" aria-hidden="true" tabindex="-1"></a>errno   <span class="co">// Type is undefined, but it's assignable</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-39">Description</h3>
<p>Indicates the error status of the last call (note that not all calls
will set this value).</p>
<table>
<thead>
<tr class="header">
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>0</code></td>
<td>No error</td>
</tr>
<tr class="even">
<td><code>EDOM</code></td>
<td>Domain error (from math)</td>
</tr>
<tr class="odd">
<td><code>EILSEQ</code></td>
<td>Encoding error (from character conversion)</td>
</tr>
<tr class="even">
<td><code>ERANGE</code></td>
<td>Range error (from math)</td>
</tr>
</tbody>
</table>
<p>If you’re doing a number of math functions, you might come across
<code>EDOM</code> or <code>ERANGE</code>.</p>
<p>With multibyte/wide character conversion functions, you might see
<code>EILSEQ</code>.</p>
<p>And your system might define any other number of values that
<code>errno</code> could be set to, all of which will begin with the
letter <code>E</code>.</p>
<p>Fun Fact: you can use <code>EDOM</code>, <code>EILSEQ</code>, and
<code>ERANGE</code> with preprocessor directives such as
<code>#ifdef</code>. But, frankly, I’m not sure why you’d do that other
than to test their existence.</p>
<!--
### Return Value {.unnumbered .unlisted}
-->
<h3 class="unnumbered unlisted" id="example-39">Example</h3>
<p>The following prints an error message, since passing <code>2.0</code>
to <code>acos()</code> is outside the function’s domain.</p>
<div class="sourceCode" id="cb910"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb910-1"><a href="errno.html#cb910-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb910-2"><a href="errno.html#cb910-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb910-3"><a href="errno.html#cb910-3"></a><span class="pp">#include </span><span class="im">&lt;errno.h&gt;</span></span>
<span id="cb910-4"><a href="errno.html#cb910-4"></a></span>
<span id="cb910-5"><a href="errno.html#cb910-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb910-6"><a href="errno.html#cb910-6"></a><span class="op">{</span></span>
<span id="cb910-7"><a href="errno.html#cb910-7"></a>    <span class="dt">double</span> x<span class="op">;</span></span>
<span id="cb910-8"><a href="errno.html#cb910-8"></a></span>
<span id="cb910-9"><a href="errno.html#cb910-9"></a>    errno <span class="op">=</span> <span class="dv">0</span><span class="op">;</span>       <span class="co">// Make sure this is clear before the call</span></span>
<span id="cb910-10"><a href="errno.html#cb910-10"></a></span>
<span id="cb910-11"><a href="errno.html#cb910-11"></a>    x <span class="op">=</span> acos<span class="op">(</span><span class="fl">2.0</span><span class="op">);</span>   <span class="co">// Invalid argument to acos()</span></span>
<span id="cb910-12"><a href="errno.html#cb910-12"></a></span>
<span id="cb910-13"><a href="errno.html#cb910-13"></a>    <span class="cf">if</span> <span class="op">(</span>errno <span class="op">==</span> EDOM<span class="op">)</span></span>
<span id="cb910-14"><a href="errno.html#cb910-14"></a>        perror<span class="op">(</span><span class="st">"acos"</span><span class="op">);</span></span>
<span id="cb910-15"><a href="errno.html#cb910-15"></a>    <span class="cf">else</span></span>
<span id="cb910-16"><a href="errno.html#cb910-16"></a>        printf<span class="op">(</span><span class="st">"Answer is %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb910-17"><a href="errno.html#cb910-17"></a></span>
<span id="cb910-18"><a href="errno.html#cb910-18"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb910-19"><a href="errno.html#cb910-19"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb911"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb911-1"><a href="errno.html#cb911-1" aria-hidden="true" tabindex="-1"></a>acos: Numerical argument out of domain</span></code></pre></div>
<p>The following prints an error message (on my system), since passing
<code>1e+30</code> to <code>exp()</code> produces a result that’s
outside the range of a <code>double</code>.</p>
<div class="sourceCode" id="cb912"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb912-1"><a href="errno.html#cb912-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb912-2"><a href="errno.html#cb912-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb912-3"><a href="errno.html#cb912-3"></a><span class="pp">#include </span><span class="im">&lt;errno.h&gt;</span></span>
<span id="cb912-4"><a href="errno.html#cb912-4"></a></span>
<span id="cb912-5"><a href="errno.html#cb912-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb912-6"><a href="errno.html#cb912-6"></a><span class="op">{</span></span>
<span id="cb912-7"><a href="errno.html#cb912-7"></a>    <span class="dt">double</span> x<span class="op">;</span></span>
<span id="cb912-8"><a href="errno.html#cb912-8"></a></span>
<span id="cb912-9"><a href="errno.html#cb912-9"></a>    errno <span class="op">=</span> <span class="dv">0</span><span class="op">;</span>       <span class="co">// Make sure this is clear before the call</span></span>
<span id="cb912-10"><a href="errno.html#cb912-10"></a></span>
<span id="cb912-11"><a href="errno.html#cb912-11"></a>    x <span class="op">=</span> exp<span class="op">(</span><span class="fl">1e+30</span><span class="op">);</span>  <span class="co">// Pass in some too-huge number</span></span>
<span id="cb912-12"><a href="errno.html#cb912-12"></a></span>
<span id="cb912-13"><a href="errno.html#cb912-13"></a>    <span class="cf">if</span> <span class="op">(</span>errno <span class="op">==</span> ERANGE<span class="op">)</span></span>
<span id="cb912-14"><a href="errno.html#cb912-14"></a>        perror<span class="op">(</span><span class="st">"exp"</span><span class="op">);</span></span>
<span id="cb912-15"><a href="errno.html#cb912-15"></a>    <span class="cf">else</span></span>
<span id="cb912-16"><a href="errno.html#cb912-16"></a>        printf<span class="op">(</span><span class="st">"Answer is %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb912-17"><a href="errno.html#cb912-17"></a></span>
<span id="cb912-18"><a href="errno.html#cb912-18"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb912-19"><a href="errno.html#cb912-19"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb913"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb913-1"><a href="errno.html#cb913-1" aria-hidden="true" tabindex="-1"></a>exp: Numerical result out of range</span></code></pre></div>
<p>This example tries to convert an invalid character into a wide
character, failing. This sets <code>errno</code> to <code>EILSEQ</code>.
We then use <code>perror()</code> to print an error message.</p>
<div class="sourceCode" id="cb914"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb914-1"><a href="errno.html#cb914-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb914-2"><a href="errno.html#cb914-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb914-3"><a href="errno.html#cb914-3"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb914-4"><a href="errno.html#cb914-4"></a><span class="pp">#include </span><span class="im">&lt;errno.h&gt;</span></span>
<span id="cb914-5"><a href="errno.html#cb914-5"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb914-6"><a href="errno.html#cb914-6"></a></span>
<span id="cb914-7"><a href="errno.html#cb914-7"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb914-8"><a href="errno.html#cb914-8"></a><span class="op">{</span></span>
<span id="cb914-9"><a href="errno.html#cb914-9"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb914-10"><a href="errno.html#cb914-10"></a></span>
<span id="cb914-11"><a href="errno.html#cb914-11"></a>    <span class="dt">char</span> <span class="op">*</span>bad_str <span class="op">=</span> <span class="st">"</span><span class="sc">\xff</span><span class="st">"</span><span class="op">;</span>  <span class="co">// Probably invalid char in this locale</span></span>
<span id="cb914-12"><a href="errno.html#cb914-12"></a>    <span class="dt">wchar_t</span> wc<span class="op">;</span></span>
<span id="cb914-13"><a href="errno.html#cb914-13"></a>    <span class="dt">size_t</span> result<span class="op">;</span></span>
<span id="cb914-14"><a href="errno.html#cb914-14"></a>    mbstate_t ps<span class="op">;</span></span>
<span id="cb914-15"><a href="errno.html#cb914-15"></a></span>
<span id="cb914-16"><a href="errno.html#cb914-16"></a>    memset<span class="op">(&amp;</span>ps<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> ps<span class="op">);</span></span>
<span id="cb914-17"><a href="errno.html#cb914-17"></a></span>
<span id="cb914-18"><a href="errno.html#cb914-18"></a>    result <span class="op">=</span> mbrtowc<span class="op">(&amp;</span>wc<span class="op">,</span> bad_str<span class="op">,</span> <span class="dv">1</span><span class="op">,</span> <span class="op">&amp;</span>ps<span class="op">);</span></span>
<span id="cb914-19"><a href="errno.html#cb914-19"></a></span>
<span id="cb914-20"><a href="errno.html#cb914-20"></a>    <span class="cf">if</span> <span class="op">(</span>result <span class="op">==</span> <span class="op">(</span><span class="dt">size_t</span><span class="op">)(-</span><span class="dv">1</span><span class="op">))</span></span>
<span id="cb914-21"><a href="errno.html#cb914-21"></a>        perror<span class="op">(</span><span class="st">"mbrtowc"</span><span class="op">);</span>  <span class="co">// mbrtowc: Illegal byte sequence</span></span>
<span id="cb914-22"><a href="errno.html#cb914-22"></a>    <span class="cf">else</span></span>
<span id="cb914-23"><a href="errno.html#cb914-23"></a>        printf<span class="op">(</span><span class="st">"Converted to L'%lc'</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wc<span class="op">);</span></span>
<span id="cb914-24"><a href="errno.html#cb914-24"></a></span>
<span id="cb914-25"><a href="errno.html#cb914-25"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb914-26"><a href="errno.html#cb914-26"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb915"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb915-1"><a href="errno.html#cb915-1" aria-hidden="true" tabindex="-1"></a>mbrtowc: Invalid or incomplete multibyte or wide character</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-36">See Also</h3>
<p><a href="stdio.html#man-perror"><code>perror()</code></a>, <a href="#man-mbrtoc16"><code>mbrtoc16()</code></a>, <a href="#man-c16rtomb"><code>c16rtomb()</code></a>, <a href="#man-mbrtoc16"><code>mbrtoc32()</code></a>, <a href="#man-c16rtomb"><code>c32rtomb()</code></a>, <a href="#man-getwc"><code>fgetwc()</code></a>, <a href="#man-putwc"><code>fputwc()</code></a>, <a href="#man-mbrtowc"><code>mbrtowc()</code></a>, <a href="#man-wcrtomb"><code>wcrtomb()</code></a>, <a href="#man-mbsrtowcs"><code>mbsrtowcs()</code></a>, <a href="#man-wcsrtombs"><code>wcsrtombs()</code></a>, <a href="#math"><code>&lt;math.h&gt;</code></a>,</p>

</body>