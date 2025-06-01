<body>

<hr>
<h1 data-number="69" id="wchar"><span class="header-section-number">69</span> <code>&lt;wchar.h&gt;</code>
Wide Character Handling</h1>
<table>
<colgroup>
<col style="width: 19%">
<col style="width: 80%">
</colgroup>
<thead>
<tr class="header">
<th>Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="wchar.html#man-btowc"><code>btowc()</code></a></td>
<td>Convert a single byte character to a wide character</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-getwc"><code>fgetwc()</code></a></td>
<td>Get a wide character from a wide stream</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-fgetws"><code>fgetws()</code></a></td>
<td>Read a wide string from a wide stream</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-putwc"><code>fputwc()</code></a></td>
<td>Write a wide character to a wide stream</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-fputws"><code>fputws()</code></a></td>
<td>Write a wide string to a wide stream</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-fwide"><code>fwide()</code></a></td>
<td>Get or set the orientation of the stream</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wprintf"><code>fwprintf()</code></a></td>
<td>Formatted wide output to a wide stream</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wscanf"><code>fwscanf()</code></a></td>
<td>Formatted wide input from a wide stream</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-getwc"><code>getwchar()</code></a></td>
<td>Get a wide character from <code>stdin</code></td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-getwc"><code>getwc()</code></a></td>
<td>Get a wide character from <code>stdin</code></td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-mbrlen"><code>mbrlen()</code></a></td>
<td>Compute the number of bytes in a multibyte character
restartably</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-mbrtowc"><code>mbrtowc()</code></a></td>
<td>Convert multibyte to wide characters restartably</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-mbsinit"><code>mbsinit()</code></a></td>
<td>Test if an <code>mbstate_t</code> is in the initial conversion
state</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-mbsrtowcs"><code>mbsrtowcs()</code></a></td>
<td>Convert a multibyte string to a wide character string
restartably</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-putwc"><code>putwchar()</code></a></td>
<td>Write a wide character to <code>stdout</code></td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-putwc"><code>putwc()</code></a></td>
<td>Write a wide character to <code>stdout</code></td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wprintf"><code>swprintf()</code></a></td>
<td>Formatted wide output to a wide string</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wscanf"><code>swscanf()</code></a></td>
<td>Formatted wide input from a wide string</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-ungetwc"><code>ungetwc()</code></a></td>
<td>Pushes a wide character back into the input stream</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wprintf"><code>vfwprintf()</code></a></td>
<td>Variadic formatted wide output to a wide stream</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wscanf"><code>vfwscanf()</code></a></td>
<td>Variadic formatted wide input from a wide stream</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wprintf"><code>vswprintf()</code></a></td>
<td>Variadic formatted wide output to a wide string</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wscanf"><code>vswscanf()</code></a></td>
<td>Variadic formatted wide input from a wide string</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wprintf"><code>vwprintf()</code></a></td>
<td>Variadic formatted wide output</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wscanf"><code>vwscanf()</code></a></td>
<td>Variadic formatted wide input</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcscat"><code>wcscat()</code></a></td>
<td>Concatenate wide strings dangerously</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcschr"><code>wcschr()</code></a></td>
<td>Find a wide character in a wide string</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcscmp"><code>wcscmp()</code></a></td>
<td>Compare wide strings</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcscoll"><code>wcscoll()</code></a></td>
<td>Compare two wide strings accounting for locale</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcscpy"><code>wcscpy()</code></a></td>
<td>Copy a wide string dangerously</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcsspn"><code>wcscspn()</code></a></td>
<td>Count characters not from a start at the front of a wide string</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcsftime"><code>wcsftime()</code></a></td>
<td>Formatted date and time output</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcslen"><code>wcslen()</code></a></td>
<td>Returns the length of a wide string</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcscat"><code>wcsncat()</code></a></td>
<td>Concatenate wide strings more safely</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcscmp"><code>wcsncmp()</code></a></td>
<td>Compare wide strings, length limited</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcscpy"><code>wcsncpy()</code></a></td>
<td>Copy a wide string more safely</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcspbrk"><code>wcspbrk()</code></a></td>
<td>Search a wide string for one of a set of wide characters</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcschr"><code>wcsrchr()</code></a></td>
<td>Find a wide character in a wide string from the end</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcsrtombs"><code>wcsrtombs()</code></a></td>
<td>Convert a wide character string to a multibyte string
restartably</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcsspn"><code>wcsspn()</code></a></td>
<td>Count characters from a set at the front of a wide string</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcsstr"><code>wcsstr()</code></a></td>
<td>Find a wide string in another wide string</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcstod"><code>wcstod()</code></a></td>
<td>Convert a wide string to a <code>double</code></td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcstod"><code>wcstof()</code></a></td>
<td>Convert a wide string to a <code>float</code></td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcstok"><code>wcstok()</code></a></td>
<td>Tokenize a wide string</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcstod"><code>wcstold()</code></a></td>
<td>Convert a wide string to a <code>long double</code></td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcstol"><code>wcstoll()</code></a></td>
<td>Convert a wide string to a <code>long long</code></td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcstol"><code>wcstol()</code></a></td>
<td>Convert a wide string to a <code>long</code></td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcstol"><code>wcstoull()</code></a></td>
<td>Convert a wide string to an <code>unsigned long long</code></td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcstol"><code>wcstoul()</code></a></td>
<td>Convert a wide string to an <code>unsigned long</code></td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcsxfrm"><code>wcsxfrm()</code></a></td>
<td>Transform a wide string for comparing based on locale</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-btowc"><code>wctob()</code></a></td>
<td>Convert a wide character to a single byte character</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wcrtomb"><code>wctombr()</code></a></td>
<td>Convert wide to multibyte characters restartably</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wcscmp"><code>wmemcmp()</code></a></td>
<td>Compare wide characters in memory</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wmemcpy"><code>wmemcpy()</code></a></td>
<td>Copy wide character memory</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wmemcpy"><code>wmemmove()</code></a></td>
<td>Copy wide character memory, potentially overlapping</td>
</tr>
<tr class="even">
<td><a href="wchar.html#man-wprintf"><code>wprintf()</code></a></td>
<td>Formatted wide output</td>
</tr>
<tr class="odd">
<td><a href="wchar.html#man-wscanf"><code>wscanf()</code></a></td>
<td>Formatted wide input</td>
</tr>
</tbody>
</table>
<p>These are the wide character variants of the functions found in <a href="#stdio"><code>&lt;stdio.h&gt;</code></a>.</p>
<p>Remember that you can’t mix-and-match multibyte output functions
(like <a href="stdio.html#man-printf"><code>printf()</code></a>) with wide
character output functions (like <a href="#man-wprintf"><code>wprintf()</code></a>). The output stream has
an <a href="unicode-wide-characters-and-all-that.html#io-stream-orientation"><em>orientation</em></a> to either
multibyte or wide that gets set on the first I/O call to that stream.
(Or it can be set with <a href="#man-fwide"><code>fwide()</code></a>.)</p>
<p>So choose one or the other and stick with it.</p>
<p>And you can specify wide character constants and string literals by
prefixing <code>L</code> to the front of it:</p>
<div class="sourceCode" id="cb1539"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1539-1"><a href="wchar.html#cb1539-1" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>s <span class="op">=</span> L<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb1539-2"><a href="wchar.html#cb1539-2" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> c <span class="op">=</span> L<span class="ch">'B'</span><span class="op">;</span></span></code></pre></div>
<p>This header also introduces a type <code>wint_t</code> that is used
by the character I/O functions. It’s a type that can hold any single
wide character, but <em>also</em> the macro <code>WEOF</code> to
indicate wide end-of-file.</p>
<h2 data-number="69.1" id="restartable-functions"><span class="header-section-number">69.1</span> Restartable Functions</h2>
<p>Finally, a note on the “restartable” functions that are included
here. When conversion is happening, some encodings require C to keep
track of some <em>state</em> about the progress of the conversion so
far.</p>
<p>For a lot of the functions, C uses an internal variable for the state
that is shared between function calls. The problem is if you’re writing
multithreaded code, this state might get trampled by other threads.</p>
<p>To avoid this, each thread needs to maintain its own state in a
variable of the opaque type <code>mbstate_t</code>. And the
“restartable” functions allow you to pass in this state so that each
thread can use their own.</p>
<hr>
<h2 data-number="69.2" id="man-wprintf"><span class="header-section-number">69.2</span> <code>wprintf()</code>,
<code>fwprintf()</code>, <code>swprintf()</code></h2>
<p>Formatted output with a wide string</p>
<h3 class="unnumbered unlisted" id="synopsis-235">Synopsis</h3>
<div class="sourceCode" id="cb1540"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1540-1"><a href="wchar.html#cb1540-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// For fwprintf()</span></span>
<span id="cb1540-2"><a href="wchar.html#cb1540-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1540-3"><a href="wchar.html#cb1540-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1540-4"><a href="wchar.html#cb1540-4" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wprintf<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="op">...);</span></span>
<span id="cb1540-5"><a href="wchar.html#cb1540-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1540-6"><a href="wchar.html#cb1540-6" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fwprintf<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span> <span class="dt">restrict</span> stream<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="op">...);</span></span>
<span id="cb1540-7"><a href="wchar.html#cb1540-7" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1540-8"><a href="wchar.html#cb1540-8" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> swprintf<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">,</span></span>
<span id="cb1540-9"><a href="wchar.html#cb1540-9" aria-hidden="true" tabindex="-1"></a>             <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="op">...);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-235">Description</h3>
<p>These are the wide versions of <a href="#man-printf"><code>printf()</code></a>, <a href="#man-printf"><code>fprintf()](#man-printf), and [</code>sprintf()`</a>.</p>
<p>See those pages for exact substantial usage.</p>
<p>These are the same except the <code>format</code> string is a wide
character string instead of a multibyte string.</p>
<p>And that <code>swprintf()</code> is analogous to
<code>snprintf()</code> in that they both take the size of the
destination array as an argument.</p>
<p>And one more thing: the precision specified for a <code>%s</code>
specifier corresponds to the number of wide characters printed, not the
number of bytes. If you know of other difference, let me know.</p>
<h3 class="unnumbered unlisted" id="return-value-233">Return Value</h3>
<p>Returns the number of wide characters outputted, or <code>-1</code>
if there’s an error.</p>
<h3 class="unnumbered unlisted" id="example-237">Example</h3>
<div class="sourceCode" id="cb1541"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1541-1"><a href="wchar.html#cb1541-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1541-2"><a href="wchar.html#cb1541-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1541-3"><a href="wchar.html#cb1541-3"></a></span>
<span id="cb1541-4"><a href="wchar.html#cb1541-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1541-5"><a href="wchar.html#cb1541-5"></a><span class="op">{</span></span>
<span id="cb1541-6"><a href="wchar.html#cb1541-6"></a>    <span class="dt">char</span> <span class="op">*</span>mbs <span class="op">=</span> <span class="st">"multibyte"</span><span class="op">;</span></span>
<span id="cb1541-7"><a href="wchar.html#cb1541-7"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>ws <span class="op">=</span> L<span class="st">"wide"</span><span class="op">;</span></span>
<span id="cb1541-8"><a href="wchar.html#cb1541-8"></a></span>
<span id="cb1541-9"><a href="wchar.html#cb1541-9"></a>    wprintf<span class="op">(</span>L<span class="st">"We're all wide for %s and %ls!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbs<span class="op">,</span> ws<span class="op">);</span></span>
<span id="cb1541-10"><a href="wchar.html#cb1541-10"></a></span>
<span id="cb1541-11"><a href="wchar.html#cb1541-11"></a>    <span class="dt">double</span> pi <span class="op">=</span> <span class="fl">3.14159265358979</span><span class="op">;</span></span>
<span id="cb1541-12"><a href="wchar.html#cb1541-12"></a>    wprintf<span class="op">(</span>L<span class="st">"pi = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pi<span class="op">);</span></span>
<span id="cb1541-13"><a href="wchar.html#cb1541-13"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1542"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1542-1"><a href="wchar.html#cb1542-1" aria-hidden="true" tabindex="-1"></a>We're all wide for multibyte and wide!</span>
<span id="cb1542-2"><a href="wchar.html#cb1542-2" aria-hidden="true" tabindex="-1"></a>pi = 3.141593</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-223">See Also</h3>
<p><a href="stdio.html#man-printf"><code>printf()</code></a>, <a href="#man-vwprintf"><code>vwprintf()</code></a></p>
<hr>
<h2 data-number="69.3" id="man-wscanf"><span class="header-section-number">69.3</span> <code>wscanf()</code>
<code>fwscanf()</code> <code>swscanf()</code></h2>
<p>Scan a wide stream or wide string for formatted input</p>
<h3 class="unnumbered unlisted" id="synopsis-236">Synopsis</h3>
<div class="sourceCode" id="cb1543"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1543-1"><a href="wchar.html#cb1543-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">  </span><span class="co">// for fwscanf()</span></span>
<span id="cb1543-2"><a href="wchar.html#cb1543-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1543-3"><a href="wchar.html#cb1543-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1543-4"><a href="wchar.html#cb1543-4" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wscanf<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="op">...);</span></span>
<span id="cb1543-5"><a href="wchar.html#cb1543-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1543-6"><a href="wchar.html#cb1543-6" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fwscanf<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span> <span class="dt">restrict</span> stream<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="op">...);</span></span>
<span id="cb1543-7"><a href="wchar.html#cb1543-7" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1543-8"><a href="wchar.html#cb1543-8" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> swscanf<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="op">...);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-236">Description</h3>
<p>These are the wide variants of <a href="#man-scanf"><code>scanf()</code></a>, <a href="#man-scanf"><code>fscanf()</code></a>, and <a href="#man-scanf"><code>sscanf()</code></a>.</p>
<p>See the <a href="stdio.html#man-scanf"><code>scanf()</code></a> page for all
the details.</p>
<h3 class="unnumbered unlisted" id="return-value-234">Return Value</h3>
<p>Returns the number of items successfully scanned, or <code>EOF</code>
on some kind of input failure.</p>
<h3 class="unnumbered unlisted" id="example-238">Example</h3>
<div class="sourceCode" id="cb1544"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1544-1"><a href="wchar.html#cb1544-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1544-2"><a href="wchar.html#cb1544-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1544-3"><a href="wchar.html#cb1544-3"></a></span>
<span id="cb1544-4"><a href="wchar.html#cb1544-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1544-5"><a href="wchar.html#cb1544-5"></a><span class="op">{</span></span>
<span id="cb1544-6"><a href="wchar.html#cb1544-6"></a>    <span class="dt">int</span> quantity<span class="op">;</span></span>
<span id="cb1544-7"><a href="wchar.html#cb1544-7"></a>    <span class="dt">wchar_t</span> item<span class="op">[</span><span class="dv">100</span><span class="op">];</span></span>
<span id="cb1544-8"><a href="wchar.html#cb1544-8"></a></span>
<span id="cb1544-9"><a href="wchar.html#cb1544-9"></a>    wprintf<span class="op">(</span>L<span class="st">"Enter </span><span class="sc">\"</span><span class="st">quantity: item</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1544-10"><a href="wchar.html#cb1544-10"></a>    </span>
<span id="cb1544-11"><a href="wchar.html#cb1544-11"></a>    <span class="cf">if</span> <span class="op">(</span>wscanf<span class="op">(</span>L<span class="st">"%d:%99ls"</span><span class="op">,</span> <span class="op">&amp;</span>quantity<span class="op">,</span> item<span class="op">)</span> <span class="op">!=</span> <span class="dv">2</span><span class="op">)</span></span>
<span id="cb1544-12"><a href="wchar.html#cb1544-12"></a>        wprintf<span class="op">(</span>L<span class="st">"Malformed input!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1544-13"><a href="wchar.html#cb1544-13"></a>    <span class="cf">else</span></span>
<span id="cb1544-14"><a href="wchar.html#cb1544-14"></a>        wprintf<span class="op">(</span>L<span class="st">"You entered: %d %ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> quantity<span class="op">,</span> item<span class="op">);</span></span>
<span id="cb1544-15"><a href="wchar.html#cb1544-15"></a><span class="op">}</span></span></code></pre></div>
<p>Output (input of <code>12: apples</code>):</p>
<div class="sourceCode" id="cb1545"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1545-1"><a href="wchar.html#cb1545-1" aria-hidden="true" tabindex="-1"></a>Enter "quantity: item"</span>
<span id="cb1545-2"><a href="wchar.html#cb1545-2" aria-hidden="true" tabindex="-1"></a>12: apples</span>
<span id="cb1545-3"><a href="wchar.html#cb1545-3" aria-hidden="true" tabindex="-1"></a>You entered: 12 apples</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-224">See Also</h3>
<p><a href="stdio.html#man-scanf"><code>scanf()</code></a>, <a href="#man-vwscanf"><code>vwscanf()</code></a></p>
<hr>
<h2 data-number="69.4" id="man-vwprintf"><span class="header-section-number">69.4</span> <code>vwprintf()</code>
<code>vfwprintf()</code> <code>vswprintf()</code></h2>
<p><code>wprintf()</code> variants using variable argument lists
(<code>va_list</code>)</p>
<h3 class="unnumbered unlisted" id="synopsis-237">Synopsis</h3>
<div class="sourceCode" id="cb1546"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1546-1"><a href="wchar.html#cb1546-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// For vfwprintf()</span></span>
<span id="cb1546-2"><a href="wchar.html#cb1546-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1546-3"><a href="wchar.html#cb1546-3" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1546-4"><a href="wchar.html#cb1546-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1546-5"><a href="wchar.html#cb1546-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> vwprintf<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="dt">va_list</span> arg<span class="op">);</span></span>
<span id="cb1546-6"><a href="wchar.html#cb1546-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1546-7"><a href="wchar.html#cb1546-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> vswprintf<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">,</span></span>
<span id="cb1546-8"><a href="wchar.html#cb1546-8" aria-hidden="true" tabindex="-1"></a>              <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="dt">va_list</span> arg<span class="op">);</span> </span>
<span id="cb1546-9"><a href="wchar.html#cb1546-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1546-10"><a href="wchar.html#cb1546-10" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> vfwprintf<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span> <span class="dt">restrict</span> stream<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span></span>
<span id="cb1546-11"><a href="wchar.html#cb1546-11" aria-hidden="true" tabindex="-1"></a>              <span class="dt">va_list</span> arg<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-237">Description</h3>
<p>These functions are the wide character variants of the <a href="#man-vprintf"><code>vprintf()</code></a>, functions. You can <a href="#man-vprintf">refer to that reference page</a> for more
details.</p>
<h3 class="unnumbered unlisted" id="return-value-235">Return Value</h3>
<p>Returns the number of wide characters stored, or a negative value on
error.</p>
<h3 class="unnumbered unlisted" id="example-239">Example</h3>
<p>In this example, we make our own version of <code>wprintf()</code>
called <code>wlogger()</code> that timestamps output. Notice how the
calls to <code>wlogger()</code> have all the bells and whistles of
<code>wprintf()</code>.</p>
<div class="sourceCode" id="cb1547"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1547-1"><a href="wchar.html#cb1547-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1547-2"><a href="wchar.html#cb1547-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1547-3"><a href="wchar.html#cb1547-3"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1547-4"><a href="wchar.html#cb1547-4"></a></span>
<span id="cb1547-5"><a href="wchar.html#cb1547-5"></a><span class="dt">int</span> wlogger<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span>format<span class="op">,</span> <span class="op">...)</span></span>
<span id="cb1547-6"><a href="wchar.html#cb1547-6"></a><span class="op">{</span></span>
<span id="cb1547-7"><a href="wchar.html#cb1547-7"></a>    <span class="dt">va_list</span> va<span class="op">;</span></span>
<span id="cb1547-8"><a href="wchar.html#cb1547-8"></a>    <span class="dt">time_t</span> now_secs <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1547-9"><a href="wchar.html#cb1547-9"></a>    <span class="kw">struct</span> tm <span class="op">*</span>now <span class="op">=</span> gmtime<span class="op">(&amp;</span>now_secs<span class="op">);</span></span>
<span id="cb1547-10"><a href="wchar.html#cb1547-10"></a></span>
<span id="cb1547-11"><a href="wchar.html#cb1547-11"></a>    <span class="co">// Output timestamp in format "YYYY-MM-DD hh:mm:ss : "</span></span>
<span id="cb1547-12"><a href="wchar.html#cb1547-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%04d-%02d-%02d %02d:%02d:%02d : "</span><span class="op">,</span></span>
<span id="cb1547-13"><a href="wchar.html#cb1547-13"></a>        now<span class="op">-&gt;</span>tm_year <span class="op">+</span> <span class="dv">1900</span><span class="op">,</span> now<span class="op">-&gt;</span>tm_mon <span class="op">+</span> <span class="dv">1</span><span class="op">,</span> now<span class="op">-&gt;</span>tm_mday<span class="op">,</span></span>
<span id="cb1547-14"><a href="wchar.html#cb1547-14"></a>        now<span class="op">-&gt;</span>tm_hour<span class="op">,</span> now<span class="op">-&gt;</span>tm_min<span class="op">,</span> now<span class="op">-&gt;</span>tm_sec<span class="op">);</span></span>
<span id="cb1547-15"><a href="wchar.html#cb1547-15"></a></span>
<span id="cb1547-16"><a href="wchar.html#cb1547-16"></a>    va_start<span class="op">(</span>va<span class="op">,</span> format<span class="op">);</span></span>
<span id="cb1547-17"><a href="wchar.html#cb1547-17"></a>    <span class="dt">int</span> result <span class="op">=</span> vwprintf<span class="op">(</span>format<span class="op">,</span> va<span class="op">);</span></span>
<span id="cb1547-18"><a href="wchar.html#cb1547-18"></a>    va_end<span class="op">(</span>va<span class="op">);</span></span>
<span id="cb1547-19"><a href="wchar.html#cb1547-19"></a></span>
<span id="cb1547-20"><a href="wchar.html#cb1547-20"></a>    wprintf<span class="op">(</span>L<span class="st">"</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1547-21"><a href="wchar.html#cb1547-21"></a></span>
<span id="cb1547-22"><a href="wchar.html#cb1547-22"></a>    <span class="cf">return</span> result<span class="op">;</span></span>
<span id="cb1547-23"><a href="wchar.html#cb1547-23"></a><span class="op">}</span></span>
<span id="cb1547-24"><a href="wchar.html#cb1547-24"></a></span>
<span id="cb1547-25"><a href="wchar.html#cb1547-25"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1547-26"><a href="wchar.html#cb1547-26"></a><span class="op">{</span></span>
<span id="cb1547-27"><a href="wchar.html#cb1547-27"></a>    <span class="dt">int</span> x <span class="op">=</span> <span class="dv">12</span><span class="op">;</span></span>
<span id="cb1547-28"><a href="wchar.html#cb1547-28"></a>    <span class="dt">float</span> y <span class="op">=</span> <span class="fl">3.2</span><span class="op">;</span></span>
<span id="cb1547-29"><a href="wchar.html#cb1547-29"></a></span>
<span id="cb1547-30"><a href="wchar.html#cb1547-30"></a>    wlogger<span class="op">(</span>L<span class="st">"Hello!"</span><span class="op">);</span></span>
<span id="cb1547-31"><a href="wchar.html#cb1547-31"></a>    wlogger<span class="op">(</span>L<span class="st">"x = %d and y = %.2f"</span><span class="op">,</span> x<span class="op">,</span> y<span class="op">);</span></span>
<span id="cb1547-32"><a href="wchar.html#cb1547-32"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1548"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1548-1"><a href="wchar.html#cb1548-1" aria-hidden="true" tabindex="-1"></a>2021-03-30 04:25:49 : Hello!</span>
<span id="cb1548-2"><a href="wchar.html#cb1548-2" aria-hidden="true" tabindex="-1"></a>2021-03-30 04:25:49 : x = 12 and y = 3.20</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-225">See Also</h3>
<p><a href="stdio.html#man-printf"><code>printf()</code></a>, <a href="#man-vprintf"><code>vprintf()</code></a></p>
<hr>
<h2 data-number="69.5" id="man-vwscanf"><span class="header-section-number">69.5</span> <code>vwscanf()</code>,
<code>vfwscanf()</code>, <code>vswscanf()</code></h2>
<p><code>wscanf()</code> variants using variable argument lists
(<code>va_list</code>)</p>
<h3 class="unnumbered unlisted" id="synopsis-238">Synopsis</h3>
<div class="sourceCode" id="cb1549"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1549-1"><a href="wchar.html#cb1549-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// For vfwscanf()</span></span>
<span id="cb1549-2"><a href="wchar.html#cb1549-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1549-3"><a href="wchar.html#cb1549-3" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1549-4"><a href="wchar.html#cb1549-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1549-5"><a href="wchar.html#cb1549-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> vwscanf<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span> <span class="dt">va_list</span> arg<span class="op">);</span></span>
<span id="cb1549-6"><a href="wchar.html#cb1549-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1549-7"><a href="wchar.html#cb1549-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> vfwscanf<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span> <span class="dt">restrict</span> stream<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span></span>
<span id="cb1549-8"><a href="wchar.html#cb1549-8" aria-hidden="true" tabindex="-1"></a>             <span class="dt">va_list</span> arg<span class="op">);</span> </span>
<span id="cb1549-9"><a href="wchar.html#cb1549-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1549-10"><a href="wchar.html#cb1549-10" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> vswscanf<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span></span>
<span id="cb1549-11"><a href="wchar.html#cb1549-11" aria-hidden="true" tabindex="-1"></a>             <span class="dt">va_list</span> arg<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-238">Description</h3>
<p>These are the wide counterparts to the <a href="#man-vscanf"><code>vscanf()</code></a> collection of functions.
See their <a href="stdio.html#man-vscanf">reference page for details</a>.</p>
<h3 class="unnumbered unlisted" id="return-value-236">Return Value</h3>
<p>Returns the number of items successfully scanned, or <code>EOF</code>
on some kind of input failure.</p>
<h3 class="unnumbered unlisted" id="example-240">Example</h3>
<p>I have to admit I was wracking my brain to think of when you’d ever
want to use this. The best example I could find was <a href="https://stackoverflow.com/questions/17017331/c99-vscanf-for-dummies/17018046#17018046">one
on Stack Overflow</a><a href="footnotes.html#fn284" class="footnote-ref" id="fnref284" role="doc-noteref"><sup>284</sup></a> that error-checks the return value
from <code>scanf()</code> against the expected. A variant of that is
shown below.</p>
<div class="sourceCode" id="cb1550"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1550-1"><a href="wchar.html#cb1550-1"></a><span class="pp">#include </span><span class="im">&lt;stdarg.h&gt;</span></span>
<span id="cb1550-2"><a href="wchar.html#cb1550-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1550-3"><a href="wchar.html#cb1550-3"></a><span class="pp">#include </span><span class="im">&lt;assert.h&gt;</span></span>
<span id="cb1550-4"><a href="wchar.html#cb1550-4"></a></span>
<span id="cb1550-5"><a href="wchar.html#cb1550-5"></a><span class="dt">int</span> error_check_wscanf<span class="op">(</span><span class="dt">int</span> expected_count<span class="op">,</span> <span class="dt">wchar_t</span> <span class="op">*</span>format<span class="op">,</span> <span class="op">...)</span></span>
<span id="cb1550-6"><a href="wchar.html#cb1550-6"></a><span class="op">{</span></span>
<span id="cb1550-7"><a href="wchar.html#cb1550-7"></a>    <span class="dt">va_list</span> va<span class="op">;</span></span>
<span id="cb1550-8"><a href="wchar.html#cb1550-8"></a></span>
<span id="cb1550-9"><a href="wchar.html#cb1550-9"></a>    va_start<span class="op">(</span>va<span class="op">,</span> format<span class="op">);</span></span>
<span id="cb1550-10"><a href="wchar.html#cb1550-10"></a>    <span class="dt">int</span> count <span class="op">=</span> vwscanf<span class="op">(</span>format<span class="op">,</span> va<span class="op">);</span></span>
<span id="cb1550-11"><a href="wchar.html#cb1550-11"></a>    va_end<span class="op">(</span>va<span class="op">);</span></span>
<span id="cb1550-12"><a href="wchar.html#cb1550-12"></a></span>
<span id="cb1550-13"><a href="wchar.html#cb1550-13"></a>    <span class="co">// This line will crash the program if the condition is false:</span></span>
<span id="cb1550-14"><a href="wchar.html#cb1550-14"></a>    assert<span class="op">(</span>count <span class="op">==</span> expected_count<span class="op">);</span></span>
<span id="cb1550-15"><a href="wchar.html#cb1550-15"></a></span>
<span id="cb1550-16"><a href="wchar.html#cb1550-16"></a>    <span class="cf">return</span> count<span class="op">;</span></span>
<span id="cb1550-17"><a href="wchar.html#cb1550-17"></a><span class="op">}</span></span>
<span id="cb1550-18"><a href="wchar.html#cb1550-18"></a></span>
<span id="cb1550-19"><a href="wchar.html#cb1550-19"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1550-20"><a href="wchar.html#cb1550-20"></a><span class="op">{</span></span>
<span id="cb1550-21"><a href="wchar.html#cb1550-21"></a>    <span class="dt">int</span> a<span class="op">,</span> b<span class="op">;</span></span>
<span id="cb1550-22"><a href="wchar.html#cb1550-22"></a>    <span class="dt">float</span> c<span class="op">;</span></span>
<span id="cb1550-23"><a href="wchar.html#cb1550-23"></a></span>
<span id="cb1550-24"><a href="wchar.html#cb1550-24"></a>    error_check_wscanf<span class="op">(</span><span class="dv">3</span><span class="op">,</span> L<span class="st">"%d, %d/%f"</span><span class="op">,</span> <span class="op">&amp;</span>a<span class="op">,</span> <span class="op">&amp;</span>b<span class="op">,</span> <span class="op">&amp;</span>c<span class="op">);</span></span>
<span id="cb1550-25"><a href="wchar.html#cb1550-25"></a>    error_check_wscanf<span class="op">(</span><span class="dv">2</span><span class="op">,</span> L<span class="st">"%d"</span><span class="op">,</span> <span class="op">&amp;</span>a<span class="op">);</span></span>
<span id="cb1550-26"><a href="wchar.html#cb1550-26"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-226">See Also</h3>
<p><a href="wchar.html#man-wscanf"><code>wscanf()</code></a></p>
<hr>
<h2 data-number="69.6" id="man-getwc"><span class="header-section-number">69.6</span> <code>getwc()</code>
<code>fgetwc()</code> <code>getwchar()</code></h2>
<p>Get a wide character from an input stream</p>
<h3 class="unnumbered unlisted" id="synopsis-239">Synopsis</h3>
<div class="sourceCode" id="cb1551"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1551-1"><a href="wchar.html#cb1551-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// For getwc() and fgetwc()</span></span>
<span id="cb1551-2"><a href="wchar.html#cb1551-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1551-3"><a href="wchar.html#cb1551-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1551-4"><a href="wchar.html#cb1551-4" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> getwchar<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span>
<span id="cb1551-5"><a href="wchar.html#cb1551-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1551-6"><a href="wchar.html#cb1551-6" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> getwc<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span>stream<span class="op">);</span></span>
<span id="cb1551-7"><a href="wchar.html#cb1551-7" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1551-8"><a href="wchar.html#cb1551-8" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> fgetwc<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span>stream<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-239">Description</h3>
<p>These are the wide variants of <a href="#man-getc"><code>fgetc()</code></a>.</p>
<p><code>fgetwc()</code> and <code>getwc()</code> are identical except
that <code>getwc()</code> might be implemented as a macro and is allowed
to evaluate <code>stream</code> multiple times.</p>
<p><code>getwchar()</code> is identical to <code>getwc()</code> with
<code>stream</code> set to <code>stdin</code>.</p>
<p>I don’t know why you’d ever use <code>getwc()</code> instead of
<code>fgetwc()</code>, but if anyone knows, drop me a line.</p>
<h3 class="unnumbered unlisted" id="return-value-237">Return Value</h3>
<p>Returns the next wide character in the input stream. Return
<code>WEOF</code> on end-of-file or error.</p>
<p>If an I/O error occurs, the error flag is also set on the stream.</p>
<p>If an invalid byte sequence is encountered, <code>errno</code> is set
to <code>ILSEQ</code>.</p>
<h3 class="unnumbered unlisted" id="example-241">Example</h3>
<p>Reads all the characters from a file, outputting only the letter ’b’s
it finds in the file:</p>
<div class="sourceCode" id="cb1552"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1552-1"><a href="wchar.html#cb1552-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1552-2"><a href="wchar.html#cb1552-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1552-3"><a href="wchar.html#cb1552-3"></a></span>
<span id="cb1552-4"><a href="wchar.html#cb1552-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1552-5"><a href="wchar.html#cb1552-5"></a><span class="op">{</span></span>
<span id="cb1552-6"><a href="wchar.html#cb1552-6"></a>    <span class="dt">FILE</span> <span class="op">*</span>fp<span class="op">;</span></span>
<span id="cb1552-7"><a href="wchar.html#cb1552-7"></a>    <span class="dt">wint_t</span> c<span class="op">;</span></span>
<span id="cb1552-8"><a href="wchar.html#cb1552-8"></a></span>
<span id="cb1552-9"><a href="wchar.html#cb1552-9"></a>    fp <span class="op">=</span> fopen<span class="op">(</span><span class="st">"datafile.txt"</span><span class="op">,</span> <span class="st">"r"</span><span class="op">);</span> <span class="co">// error check this!</span></span>
<span id="cb1552-10"><a href="wchar.html#cb1552-10"></a></span>
<span id="cb1552-11"><a href="wchar.html#cb1552-11"></a>    <span class="co">// this while-statement assigns into c, and then checks against EOF:</span></span>
<span id="cb1552-12"><a href="wchar.html#cb1552-12"></a></span>
<span id="cb1552-13"><a href="wchar.html#cb1552-13"></a>    <span class="cf">while</span><span class="op">((</span>c <span class="op">=</span> fgetc<span class="op">(</span>fp<span class="op">))</span> <span class="op">!=</span> WEOF<span class="op">)</span> </span>
<span id="cb1552-14"><a href="wchar.html#cb1552-14"></a>        <span class="cf">if</span> <span class="op">(</span>c <span class="op">==</span> L<span class="ch">'b'</span><span class="op">)</span></span>
<span id="cb1552-15"><a href="wchar.html#cb1552-15"></a>            fputwc<span class="op">(</span>c<span class="op">,</span> stdout<span class="op">);</span></span>
<span id="cb1552-16"><a href="wchar.html#cb1552-16"></a></span>
<span id="cb1552-17"><a href="wchar.html#cb1552-17"></a>    fclose<span class="op">(</span>fp<span class="op">);</span></span>
<span id="cb1552-18"><a href="wchar.html#cb1552-18"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-227">See Also</h3>
<p><a href="wchar.html#man-putwc"><code>fputwc</code></a>, <a href="#man-fgetws"><code>fgetws</code></a>, <a href="#errno"><code>errno</code></a></p>
<hr>
<h2 data-number="69.7" id="man-fgetws"><span class="header-section-number">69.7</span> <code>fgetws()</code></h2>
<p>Read a wide string from a file</p>
<h3 class="unnumbered unlisted" id="synopsis-240">Synopsis</h3>
<div class="sourceCode" id="cb1553"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1553-1"><a href="wchar.html#cb1553-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1553-2"><a href="wchar.html#cb1553-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1553-3"><a href="wchar.html#cb1553-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1553-4"><a href="wchar.html#cb1553-4" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>fgetws<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">int</span> n<span class="op">,</span> <span class="dt">FILE</span> <span class="op">*</span> <span class="dt">restrict</span> stream<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-240">Description</h3>
<p>This is the wide version of <a href="#man-gets"><code>fgets()</code></a>. See <a href="stdio.html#man-gets">its
reference page for details</a>.</p>
<p>A wide <code>NUL</code> character is used to terminate the
string.</p>
<h3 class="unnumbered unlisted" id="return-value-238">Return Value</h3>
<p>Returns <code>s</code> on success, or a <code>NULL</code> pointer on
end-of-file or error.</p>
<h3 class="unnumbered unlisted" id="example-242">Example</h3>
<p>The following example reads lines from a file and prepends them with
numbers:</p>
<div class="sourceCode" id="cb1554"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1554-1"><a href="wchar.html#cb1554-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1554-2"><a href="wchar.html#cb1554-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1554-3"><a href="wchar.html#cb1554-3"></a></span>
<span id="cb1554-4"><a href="wchar.html#cb1554-4"></a><span class="pp">#define BUF_SIZE 1024</span></span>
<span id="cb1554-5"><a href="wchar.html#cb1554-5"></a></span>
<span id="cb1554-6"><a href="wchar.html#cb1554-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1554-7"><a href="wchar.html#cb1554-7"></a><span class="op">{</span></span>
<span id="cb1554-8"><a href="wchar.html#cb1554-8"></a>    <span class="dt">FILE</span> <span class="op">*</span>fp<span class="op">;</span></span>
<span id="cb1554-9"><a href="wchar.html#cb1554-9"></a>    <span class="dt">wchar_t</span> buf<span class="op">[</span>BUF_SIZE<span class="op">];</span></span>
<span id="cb1554-10"><a href="wchar.html#cb1554-10"></a></span>
<span id="cb1554-11"><a href="wchar.html#cb1554-11"></a>    fp <span class="op">=</span> fopen<span class="op">(</span><span class="st">"textfile.txt"</span><span class="op">,</span> <span class="st">"r"</span><span class="op">);</span> <span class="co">// error check this!</span></span>
<span id="cb1554-12"><a href="wchar.html#cb1554-12"></a></span>
<span id="cb1554-13"><a href="wchar.html#cb1554-13"></a>    <span class="dt">int</span> line_count <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1554-14"><a href="wchar.html#cb1554-14"></a></span>
<span id="cb1554-15"><a href="wchar.html#cb1554-15"></a>    <span class="cf">while</span> <span class="op">((</span>fgetws<span class="op">(</span>buf<span class="op">,</span> BUF_SIZE<span class="op">,</span> fp<span class="op">))</span> <span class="op">!=</span> NULL<span class="op">)</span> </span>
<span id="cb1554-16"><a href="wchar.html#cb1554-16"></a>        wprintf<span class="op">(</span>L<span class="st">"%04d: %ls"</span><span class="op">,</span> <span class="op">++</span>line_count<span class="op">,</span> buf<span class="op">);</span></span>
<span id="cb1554-17"><a href="wchar.html#cb1554-17"></a></span>
<span id="cb1554-18"><a href="wchar.html#cb1554-18"></a>    fclose<span class="op">(</span>fp<span class="op">);</span></span>
<span id="cb1554-19"><a href="wchar.html#cb1554-19"></a><span class="op">}</span></span></code></pre></div>
<p>Example output for a file with these lines in them (without the
prepended numbers):</p>
<div class="sourceCode" id="cb1555"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1555-1"><a href="wchar.html#cb1555-1" aria-hidden="true" tabindex="-1"></a>0001: line 1</span>
<span id="cb1555-2"><a href="wchar.html#cb1555-2" aria-hidden="true" tabindex="-1"></a>0002: line 2</span>
<span id="cb1555-3"><a href="wchar.html#cb1555-3" aria-hidden="true" tabindex="-1"></a>0003: something</span>
<span id="cb1555-4"><a href="wchar.html#cb1555-4" aria-hidden="true" tabindex="-1"></a>0004: line 4</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-228">See Also</h3>
<p><a href="wchar.html#man-getwc"><code>fgetwc()</code></a>, <a href="#man-gets"><code>fgets()</code></a></p>
<hr>
<h2 data-number="69.8" id="man-putwc"><span class="header-section-number">69.8</span> <code>putwchar()</code>
<code>putwc()</code> <code>fputwc()</code></h2>
<p>Write a single wide character to the console or to a file</p>
<h3 class="unnumbered unlisted" id="synopsis-241">Synopsis</h3>
<div class="sourceCode" id="cb1556"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1556-1"><a href="wchar.html#cb1556-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// For putwc() and fputwc()</span></span>
<span id="cb1556-2"><a href="wchar.html#cb1556-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1556-3"><a href="wchar.html#cb1556-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1556-4"><a href="wchar.html#cb1556-4" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> putwchar<span class="op">(</span><span class="dt">wchar_t</span> c<span class="op">);</span></span>
<span id="cb1556-5"><a href="wchar.html#cb1556-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1556-6"><a href="wchar.html#cb1556-6" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> putwc<span class="op">(</span><span class="dt">wchar_t</span> c<span class="op">,</span> <span class="dt">FILE</span> <span class="op">*</span>stream<span class="op">);</span></span>
<span id="cb1556-7"><a href="wchar.html#cb1556-7" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1556-8"><a href="wchar.html#cb1556-8" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> fputwc<span class="op">(</span><span class="dt">wchar_t</span> c<span class="op">,</span> <span class="dt">FILE</span> <span class="op">*</span>stream<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-241">Description</h3>
<p>These are the wide character equivalents to the <a href="#man-putc">‘fputc()’</a> group of functions. You can find more
information <a href="stdio.html#man-putc">‘in that reference section’</a>.</p>
<p><code>fputwc()</code> and <code>putwc()</code> are identical except
that <code>putwc()</code> might be implemented as a macro and is allowed
to evaluate <code>stream</code> multiple times.</p>
<p><code>putwchar()</code> is identical to <code>putwc()</code> with
<code>stream</code> set to <code>stdin</code>.</p>
<p>I don’t know why you’d ever use <code>putwc()</code> instead of
<code>fputwc()</code>, but if anyone knows, drop me a line.</p>
<h3 class="unnumbered unlisted" id="return-value-239">Return Value</h3>
<p>Returns the wide character written, or <code>WEOF</code> on
error.</p>
<p>If it’s an I/O error, the error flag will be set for the stream.</p>
<p>If it’s an encoding error, <code>errno</code> will be set to
<code>EILSEQ</code>.</p>
<h3 class="unnumbered unlisted" id="example-243">Example</h3>
<p>Read all characters from a file, outputting only the letter ’b’s it
finds in the file:</p>
<div class="sourceCode" id="cb1557"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1557-1"><a href="wchar.html#cb1557-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1557-2"><a href="wchar.html#cb1557-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1557-3"><a href="wchar.html#cb1557-3"></a></span>
<span id="cb1557-4"><a href="wchar.html#cb1557-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1557-5"><a href="wchar.html#cb1557-5"></a><span class="op">{</span></span>
<span id="cb1557-6"><a href="wchar.html#cb1557-6"></a>    <span class="dt">FILE</span> <span class="op">*</span>fp<span class="op">;</span></span>
<span id="cb1557-7"><a href="wchar.html#cb1557-7"></a>    <span class="dt">wint_t</span> c<span class="op">;</span></span>
<span id="cb1557-8"><a href="wchar.html#cb1557-8"></a></span>
<span id="cb1557-9"><a href="wchar.html#cb1557-9"></a>    fp <span class="op">=</span> fopen<span class="op">(</span><span class="st">"datafile.txt"</span><span class="op">,</span> <span class="st">"r"</span><span class="op">);</span> <span class="co">// error check this!</span></span>
<span id="cb1557-10"><a href="wchar.html#cb1557-10"></a></span>
<span id="cb1557-11"><a href="wchar.html#cb1557-11"></a>    <span class="co">// this while-statement assigns into c, and then checks against EOF:</span></span>
<span id="cb1557-12"><a href="wchar.html#cb1557-12"></a></span>
<span id="cb1557-13"><a href="wchar.html#cb1557-13"></a>    <span class="cf">while</span><span class="op">((</span>c <span class="op">=</span> fgetc<span class="op">(</span>fp<span class="op">))</span> <span class="op">!=</span> WEOF<span class="op">)</span> </span>
<span id="cb1557-14"><a href="wchar.html#cb1557-14"></a>        <span class="cf">if</span> <span class="op">(</span>c <span class="op">==</span> L<span class="ch">'b'</span><span class="op">)</span></span>
<span id="cb1557-15"><a href="wchar.html#cb1557-15"></a>            fputwc<span class="op">(</span>c<span class="op">,</span> stdout<span class="op">);</span></span>
<span id="cb1557-16"><a href="wchar.html#cb1557-16"></a></span>
<span id="cb1557-17"><a href="wchar.html#cb1557-17"></a>    fclose<span class="op">(</span>fp<span class="op">);</span></span>
<span id="cb1557-18"><a href="wchar.html#cb1557-18"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-229">See Also</h3>
<p><a href="wchar.html#man-getwc"><code>fgetwc()</code></a>, <a href="#man-putc"><code>fputc()</code></a>, <a href="#errno"><code>errno</code></a></p>
<hr>
<h2 data-number="69.9" id="man-fputws"><span class="header-section-number">69.9</span> <code>fputws()</code></h2>
<p>Write a wide string to a file</p>
<h3 class="unnumbered unlisted" id="synopsis-242">Synopsis</h3>
<div class="sourceCode" id="cb1558"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1558-1"><a href="wchar.html#cb1558-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1558-2"><a href="wchar.html#cb1558-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1558-3"><a href="wchar.html#cb1558-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1558-4"><a href="wchar.html#cb1558-4" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fputws<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">FILE</span> <span class="op">*</span> <span class="dt">restrict</span> stream<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-242">Description</h3>
<p>This is the wide version of <a href="#man-puts"><code>fputs()</code></a>.</p>
<p>Pass in a wide string and an output stream, and it will so be
written.</p>
<h3 class="unnumbered unlisted" id="return-value-240">Return Value</h3>
<p>Returns a non-negative value on success, or <code>EOF</code> on
error.</p>
<h3 class="unnumbered unlisted" id="example-244">Example</h3>
<div class="sourceCode" id="cb1559"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1559-1"><a href="wchar.html#cb1559-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1559-2"><a href="wchar.html#cb1559-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1559-3"><a href="wchar.html#cb1559-3"></a></span>
<span id="cb1559-4"><a href="wchar.html#cb1559-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1559-5"><a href="wchar.html#cb1559-5"></a><span class="op">{</span></span>
<span id="cb1559-6"><a href="wchar.html#cb1559-6"></a>    fputws<span class="op">(</span>L<span class="st">"Hello, world!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> stdout<span class="op">);</span></span>
<span id="cb1559-7"><a href="wchar.html#cb1559-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-230">See Also</h3>
<p><a href="wchar.html#man-putwc"><code>fputwc()</code></a> <a href="#man-puts"><code>fputs()</code></a></p>
<hr>
<h2 data-number="69.10" id="man-fwide"><span class="header-section-number">69.10</span> <code>fwide()</code></h2>
<p>Get or set the orientation of the stream</p>
<h3 class="unnumbered unlisted" id="synopsis-243">Synopsis</h3>
<div class="sourceCode" id="cb1560"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1560-1"><a href="wchar.html#cb1560-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1560-2"><a href="wchar.html#cb1560-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1560-3"><a href="wchar.html#cb1560-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1560-4"><a href="wchar.html#cb1560-4" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fwide<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span>stream<span class="op">,</span> <span class="dt">int</span> mode<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-243">Description</h3>
<p>Streams can be either wide-oriented (meaning the wide functions are
in use) or byte-oriented (that the regular multibyte functions are in
use). Or, before an orientation is chosen, unoriented.</p>
<p>There are two ways to set the orientation of an unoriented
stream:</p>
<ul>
<li><p>Implicitly: just use a function like <code>printf()</code> (byte
oriented) or <code>wprintf()</code> (wide oriented), and the orientation
will be set.</p></li>
<li><p>Explicitly: use this function to set it.</p></li>
</ul>
<p>You can set the orientation for the stream by passing different
numbers to <code>mode</code>:</p>
<table>
<thead>
<tr class="header">
<th><code>mode</code></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>0</code></td>
<td>Do not alter the orientation</td>
</tr>
<tr class="even">
<td><code>-1</code></td>
<td>Set stream to byte-oriented</td>
</tr>
<tr class="odd">
<td><code>1</code></td>
<td>Set stream to wide-oriented</td>
</tr>
</tbody>
</table>
<p>(I said <code>-1</code> and <code>1</code> there, but really it could
be any positive or negative number.)</p>
<p>Most people choose the wide or byte functions (<code>printf()</code>
or <code>wprintf()</code>) and just start using them and never use
<code>fwide()</code> to set the orientation.</p>
<p>And once the orientation is set, you can’t change it. So you can’t
use <code>fwide()</code> for that, either.</p>
<p>So what can you use it for?</p>
<p>You can <em>test</em> to see what orientation a stream is in by
passing <code>0</code> as the <code>mode</code> and checking the return
value.</p>
<h3 class="unnumbered unlisted" id="return-value-241">Return Value</h3>
<p>Returns greater than zero if the stream is wide-oriented.</p>
<p>Returns less than zero if the stream is byte-oriented.</p>
<p>Returns zero if the stream is unoriented.</p>
<h3 class="unnumbered unlisted" id="example-245">Example</h3>
<p>Example setting to byte-oriented:</p>
<div class="sourceCode" id="cb1561"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1561-1"><a href="wchar.html#cb1561-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1561-2"><a href="wchar.html#cb1561-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1561-3"><a href="wchar.html#cb1561-3"></a></span>
<span id="cb1561-4"><a href="wchar.html#cb1561-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1561-5"><a href="wchar.html#cb1561-5"></a><span class="op">{</span></span>
<span id="cb1561-6"><a href="wchar.html#cb1561-6"></a>    printf<span class="op">(</span><span class="st">"Hello world!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// Implicitly set to byte</span></span>
<span id="cb1561-7"><a href="wchar.html#cb1561-7"></a></span>
<span id="cb1561-8"><a href="wchar.html#cb1561-8"></a>    <span class="dt">int</span> mode <span class="op">=</span> fwide<span class="op">(</span>stdout<span class="op">,</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb1561-9"><a href="wchar.html#cb1561-9"></a></span>
<span id="cb1561-10"><a href="wchar.html#cb1561-10"></a>    printf<span class="op">(</span><span class="st">"Stream is %s-oriented</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mode <span class="op">&lt;</span> <span class="dv">0</span><span class="op">?</span> <span class="st">"byte"</span><span class="op">:</span> <span class="st">"wide"</span><span class="op">);</span></span>
<span id="cb1561-11"><a href="wchar.html#cb1561-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1562"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1562-1"><a href="wchar.html#cb1562-1" aria-hidden="true" tabindex="-1"></a>Hello world!</span>
<span id="cb1562-2"><a href="wchar.html#cb1562-2" aria-hidden="true" tabindex="-1"></a>Stream is byte-oriented</span></code></pre></div>
<p>Example setting to wide-oriented:</p>
<div class="sourceCode" id="cb1563"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1563-1"><a href="wchar.html#cb1563-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1563-2"><a href="wchar.html#cb1563-2"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1563-3"><a href="wchar.html#cb1563-3"></a></span>
<span id="cb1563-4"><a href="wchar.html#cb1563-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1563-5"><a href="wchar.html#cb1563-5"></a><span class="op">{</span></span>
<span id="cb1563-6"><a href="wchar.html#cb1563-6"></a>    wprintf<span class="op">(</span>L<span class="st">"Hello world!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>  <span class="co">// Implicitly set to wide</span></span>
<span id="cb1563-7"><a href="wchar.html#cb1563-7"></a></span>
<span id="cb1563-8"><a href="wchar.html#cb1563-8"></a>    <span class="dt">int</span> mode <span class="op">=</span> fwide<span class="op">(</span>stdout<span class="op">,</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb1563-9"><a href="wchar.html#cb1563-9"></a></span>
<span id="cb1563-10"><a href="wchar.html#cb1563-10"></a>    wprintf<span class="op">(</span>L<span class="st">"Stream is %ls-oriented</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mode <span class="op">&lt;</span> <span class="dv">0</span><span class="op">?</span> L<span class="st">"byte"</span><span class="op">:</span> L<span class="st">"wide"</span><span class="op">);</span></span>
<span id="cb1563-11"><a href="wchar.html#cb1563-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1564"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1564-1"><a href="wchar.html#cb1564-1" aria-hidden="true" tabindex="-1"></a>Hello world!</span>
<span id="cb1564-2"><a href="wchar.html#cb1564-2" aria-hidden="true" tabindex="-1"></a>Stream is wide-oriented</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="69.11" id="man-ungetwc"><span class="header-section-number">69.11</span> <code>ungetwc()</code></h2>
<p>Pushes a wide character back into the input stream</p>
<h3 class="unnumbered unlisted" id="synopsis-244">Synopsis</h3>
<div class="sourceCode" id="cb1565"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1565-1"><a href="wchar.html#cb1565-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1565-2"><a href="wchar.html#cb1565-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1565-3"><a href="wchar.html#cb1565-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1565-4"><a href="wchar.html#cb1565-4" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> ungetwc<span class="op">(</span><span class="dt">wint_t</span> c<span class="op">,</span> <span class="dt">FILE</span> <span class="op">*</span>stream<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-244">Description</h3>
<p>This is the wide character variant of <a href="#man-ungetc"><code>ungetc()</code></a>.</p>
<p>It performs the reverse operation of <a href="#man-getwc"><code>fgetwc()</code></a>, pushing a character back on
the input stream.</p>
<p>The spec guarantees you can do this one time in a row. You can
probably do it more times, but it’s up to the implementation. If you do
too many calls without an intervening read, an error could be
returned.</p>
<p>Setting the file position discards any characters pushed by
<code>ungetwc()</code> without being subsequently read.</p>
<p>The end-of-file flag is cleared after a successful call.</p>
<h3 class="unnumbered unlisted" id="return-value-242">Return Value</h3>
<p>Returns the value of the pushed character on success, or
<code>WEOF</code> on failure.</p>
<h3 class="unnumbered unlisted" id="example-246">Example</h3>
<p>This example reads a piece of punctuation, then everything after it
up to the next piece of punctuation. It returns the leading punctuation,
and stores the rest in a string.</p>
<div class="sourceCode" id="cb1566"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1566-1"><a href="wchar.html#cb1566-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1566-2"><a href="wchar.html#cb1566-2"></a><span class="pp">#include </span><span class="im">&lt;wctype.h&gt;</span></span>
<span id="cb1566-3"><a href="wchar.html#cb1566-3"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1566-4"><a href="wchar.html#cb1566-4"></a></span>
<span id="cb1566-5"><a href="wchar.html#cb1566-5"></a><span class="dt">wint_t</span> read_punctstring<span class="op">(</span><span class="dt">FILE</span> <span class="op">*</span>fp<span class="op">,</span> <span class="dt">wchar_t</span> <span class="op">*</span>s<span class="op">)</span></span>
<span id="cb1566-6"><a href="wchar.html#cb1566-6"></a><span class="op">{</span></span>
<span id="cb1566-7"><a href="wchar.html#cb1566-7"></a>    <span class="dt">wint_t</span> origpunct<span class="op">,</span> c<span class="op">;</span></span>
<span id="cb1566-8"><a href="wchar.html#cb1566-8"></a>    </span>
<span id="cb1566-9"><a href="wchar.html#cb1566-9"></a>    origpunct <span class="op">=</span> fgetwc<span class="op">(</span>fp<span class="op">);</span></span>
<span id="cb1566-10"><a href="wchar.html#cb1566-10"></a></span>
<span id="cb1566-11"><a href="wchar.html#cb1566-11"></a>    <span class="cf">if</span> <span class="op">(</span>origpunct <span class="op">==</span> WEOF<span class="op">)</span>  <span class="co">// return EOF on end-of-file</span></span>
<span id="cb1566-12"><a href="wchar.html#cb1566-12"></a>        <span class="cf">return</span> WEOF<span class="op">;</span></span>
<span id="cb1566-13"><a href="wchar.html#cb1566-13"></a></span>
<span id="cb1566-14"><a href="wchar.html#cb1566-14"></a>    <span class="cf">while</span> <span class="op">(</span>c <span class="op">=</span> fgetwc<span class="op">(</span>fp<span class="op">),</span> <span class="op">!</span>iswpunct<span class="op">(</span>c<span class="op">)</span> <span class="op">&amp;&amp;</span> c <span class="op">!=</span> WEOF<span class="op">)</span></span>
<span id="cb1566-15"><a href="wchar.html#cb1566-15"></a>        <span class="op">*</span>s<span class="op">++</span> <span class="op">=</span> c<span class="op">;</span>  <span class="co">// save it in the string</span></span>
<span id="cb1566-16"><a href="wchar.html#cb1566-16"></a></span>
<span id="cb1566-17"><a href="wchar.html#cb1566-17"></a>    <span class="op">*</span>s <span class="op">=</span> L<span class="ch">'\0'</span><span class="op">;</span> <span class="co">// nul-terminate the string</span></span>
<span id="cb1566-18"><a href="wchar.html#cb1566-18"></a></span>
<span id="cb1566-19"><a href="wchar.html#cb1566-19"></a>    <span class="co">// if we read punctuation last, ungetc it so we can fgetc it next</span></span>
<span id="cb1566-20"><a href="wchar.html#cb1566-20"></a>    <span class="co">// time:</span></span>
<span id="cb1566-21"><a href="wchar.html#cb1566-21"></a>    <span class="cf">if</span> <span class="op">(</span>iswpunct<span class="op">(</span>c<span class="op">))</span></span>
<span id="cb1566-22"><a href="wchar.html#cb1566-22"></a>        ungetwc<span class="op">(</span>c<span class="op">,</span> fp<span class="op">);</span></span>
<span id="cb1566-23"><a href="wchar.html#cb1566-23"></a></span>
<span id="cb1566-24"><a href="wchar.html#cb1566-24"></a>    <span class="cf">return</span> origpunct<span class="op">;</span></span>
<span id="cb1566-25"><a href="wchar.html#cb1566-25"></a><span class="op">}</span></span>
<span id="cb1566-26"><a href="wchar.html#cb1566-26"></a></span>
<span id="cb1566-27"><a href="wchar.html#cb1566-27"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1566-28"><a href="wchar.html#cb1566-28"></a><span class="op">{</span></span>
<span id="cb1566-29"><a href="wchar.html#cb1566-29"></a>    <span class="dt">wchar_t</span> s<span class="op">[</span><span class="dv">128</span><span class="op">];</span></span>
<span id="cb1566-30"><a href="wchar.html#cb1566-30"></a>    <span class="dt">wint_t</span> c<span class="op">;</span></span>
<span id="cb1566-31"><a href="wchar.html#cb1566-31"></a></span>
<span id="cb1566-32"><a href="wchar.html#cb1566-32"></a>    <span class="cf">while</span> <span class="op">((</span>c <span class="op">=</span> read_punctstring<span class="op">(</span>stdin<span class="op">,</span> s<span class="op">))</span> <span class="op">!=</span> WEOF<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1566-33"><a href="wchar.html#cb1566-33"></a>        wprintf<span class="op">(</span>L<span class="st">"%lc: %ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">,</span> s<span class="op">);</span></span>
<span id="cb1566-34"><a href="wchar.html#cb1566-34"></a>    <span class="op">}</span></span>
<span id="cb1566-35"><a href="wchar.html#cb1566-35"></a><span class="op">}</span></span></code></pre></div>
<p>Sample Input:</p>
<div class="sourceCode" id="cb1567"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1567-1"><a href="wchar.html#cb1567-1" aria-hidden="true" tabindex="-1"></a>!foo#bar*baz</span></code></pre></div>
<p>Sample output:</p>
<div class="sourceCode" id="cb1568"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1568-1"><a href="wchar.html#cb1568-1" aria-hidden="true" tabindex="-1"></a>!: foo</span>
<span id="cb1568-2"><a href="wchar.html#cb1568-2" aria-hidden="true" tabindex="-1"></a>#: bar</span>
<span id="cb1568-3"><a href="wchar.html#cb1568-3" aria-hidden="true" tabindex="-1"></a>*: baz</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-231">See Also</h3>
<p><a href="wchar.html#man-getwc"><code>fgetwc()</code></a>, <a href="#man-ungetc"><code>ungetc()</code></a></p>
<hr>
<h2 data-number="69.12" id="man-wcstod"><span class="header-section-number">69.12</span> <code>wcstod()</code>
<code>wcstof()</code> <code>wcstold()</code></h2>
<p>Convert a wide string to a floating point number</p>
<h3 class="unnumbered unlisted" id="synopsis-245">Synopsis</h3>
<div class="sourceCode" id="cb1569"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1569-1"><a href="wchar.html#cb1569-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1569-2"><a href="wchar.html#cb1569-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1569-3"><a href="wchar.html#cb1569-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> wcstod<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">);</span></span>
<span id="cb1569-4"><a href="wchar.html#cb1569-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1569-5"><a href="wchar.html#cb1569-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> wcstof<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">);</span></span>
<span id="cb1569-6"><a href="wchar.html#cb1569-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1569-7"><a href="wchar.html#cb1569-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> wcstold<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span> <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-245">Description</h3>
<p>These are the wide counterparts to the <a href="#man-strtod"><code>strtod()</code></a> family of functions. See <a href="#man-strtod">their reference pages for details</a>.</p>
<h3 class="unnumbered unlisted" id="return-value-243">Return Value</h3>
<p>Returns the string converted to a floating point value.</p>
<p>Returns <code>0</code> if there’s no valid number in the string.</p>
<p>On overflow, returns an apporpriately-signed <code>HUGE_VAL</code>,
<code>HUGE_VALF</code>. or <code>HUGE_VALL</code> depending on the
return type, and <code>errno</code> is set to <code>ERANGE</code>.</p>
<p>On underflow, returns a number no greater than the smallest
normalized positive number, appropriately signed. The implemention
<em>might</em> set <code>errno</code> to <code>ERANGE</code>.</p>
<h3 class="unnumbered unlisted" id="example-247">Example</h3>
<div class="sourceCode" id="cb1570"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1570-1"><a href="wchar.html#cb1570-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1570-2"><a href="wchar.html#cb1570-2"></a></span>
<span id="cb1570-3"><a href="wchar.html#cb1570-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1570-4"><a href="wchar.html#cb1570-4"></a><span class="op">{</span></span>
<span id="cb1570-5"><a href="wchar.html#cb1570-5"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>inp <span class="op">=</span> L<span class="st">"   123.4567beej"</span><span class="op">;</span></span>
<span id="cb1570-6"><a href="wchar.html#cb1570-6"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>badchar<span class="op">;</span></span>
<span id="cb1570-7"><a href="wchar.html#cb1570-7"></a></span>
<span id="cb1570-8"><a href="wchar.html#cb1570-8"></a>    <span class="dt">double</span> val <span class="op">=</span> wcstod<span class="op">(</span>inp<span class="op">,</span> <span class="op">&amp;</span>badchar<span class="op">);</span></span>
<span id="cb1570-9"><a href="wchar.html#cb1570-9"></a></span>
<span id="cb1570-10"><a href="wchar.html#cb1570-10"></a>    wprintf<span class="op">(</span>L<span class="st">"Converted string to %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">);</span></span>
<span id="cb1570-11"><a href="wchar.html#cb1570-11"></a>    wprintf<span class="op">(</span>L<span class="st">"Encountered bad characters: %ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> badchar<span class="op">);</span></span>
<span id="cb1570-12"><a href="wchar.html#cb1570-12"></a></span>
<span id="cb1570-13"><a href="wchar.html#cb1570-13"></a>    val <span class="op">=</span> wcstod<span class="op">(</span>L<span class="st">"987.654321beej"</span><span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1570-14"><a href="wchar.html#cb1570-14"></a>    wprintf<span class="op">(</span>L<span class="st">"Ignoring bad chars: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">);</span></span>
<span id="cb1570-15"><a href="wchar.html#cb1570-15"></a></span>
<span id="cb1570-16"><a href="wchar.html#cb1570-16"></a>    val <span class="op">=</span> wcstod<span class="op">(</span>L<span class="st">"11.2233"</span><span class="op">,</span> <span class="op">&amp;</span>badchar<span class="op">);</span></span>
<span id="cb1570-17"><a href="wchar.html#cb1570-17"></a></span>
<span id="cb1570-18"><a href="wchar.html#cb1570-18"></a>    <span class="cf">if</span> <span class="op">(*</span>badchar <span class="op">==</span> L<span class="ch">'\0'</span><span class="op">)</span></span>
<span id="cb1570-19"><a href="wchar.html#cb1570-19"></a>        wprintf<span class="op">(</span>L<span class="st">"No bad chars: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">);</span></span>
<span id="cb1570-20"><a href="wchar.html#cb1570-20"></a>    <span class="cf">else</span></span>
<span id="cb1570-21"><a href="wchar.html#cb1570-21"></a>        wprintf<span class="op">(</span>L<span class="st">"Found bad chars: %f, %ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> val<span class="op">,</span> badchar<span class="op">);</span></span>
<span id="cb1570-22"><a href="wchar.html#cb1570-22"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1571"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1571-1"><a href="wchar.html#cb1571-1" aria-hidden="true" tabindex="-1"></a>Converted string to 123.456700</span>
<span id="cb1571-2"><a href="wchar.html#cb1571-2" aria-hidden="true" tabindex="-1"></a>Encountered bad characters: beej</span>
<span id="cb1571-3"><a href="wchar.html#cb1571-3" aria-hidden="true" tabindex="-1"></a>Ignoring bad chars: 987.654321</span>
<span id="cb1571-4"><a href="wchar.html#cb1571-4" aria-hidden="true" tabindex="-1"></a>No bad chars: 11.223300</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-232">See Also</h3>
<p><a href="wchar.html#man-wcstol"><code>wcstol()</code></a>, <a href="#man-strtod"><code>strtod()</code></a>, <a href="#errno"><code>errno</code></a></p>
<hr>
<h2 data-number="69.13" id="man-wcstol"><span class="header-section-number">69.13</span> <code>wcstol()</code>
<code>wcstoll()</code> <code>wcstoul()</code>
<code>wcstoull()</code></h2>
<p>Convert a wide string to an integer value</p>
<h3 class="unnumbered unlisted" id="synopsis-246">Synopsis</h3>
<div class="sourceCode" id="cb1572"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1572-1"><a href="wchar.html#cb1572-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1572-2"><a href="wchar.html#cb1572-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1572-3"><a href="wchar.html#cb1572-3" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> wcstol<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1572-4"><a href="wchar.html#cb1572-4" aria-hidden="true" tabindex="-1"></a>                <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb1572-5"><a href="wchar.html#cb1572-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1572-6"><a href="wchar.html#cb1572-6" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> wcstoll<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1572-7"><a href="wchar.html#cb1572-7" aria-hidden="true" tabindex="-1"></a>                      <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb1572-8"><a href="wchar.html#cb1572-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1572-9"><a href="wchar.html#cb1572-9" aria-hidden="true" tabindex="-1"></a><span class="dt">unsigned</span> <span class="dt">long</span> <span class="dt">int</span> wcstoul<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1572-10"><a href="wchar.html#cb1572-10" aria-hidden="true" tabindex="-1"></a>                          <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span>
<span id="cb1572-11"><a href="wchar.html#cb1572-11" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1572-12"><a href="wchar.html#cb1572-12" aria-hidden="true" tabindex="-1"></a><span class="dt">unsigned</span> <span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> wcstoull<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> nptr<span class="op">,</span></span>
<span id="cb1572-13"><a href="wchar.html#cb1572-13" aria-hidden="true" tabindex="-1"></a>                                <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> endptr<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-246">Description</h3>
<p>These are the wide counterparts to the <a href="#man-strtol"><code>strtol()</code></a> family of functions, so see
<a href="stdlib.html#man-strtol">their reference pages for the details</a>.</p>
<h3 class="unnumbered unlisted" id="return-value-244">Return Value</h3>
<p>Returns the integer value of the string.</p>
<p>If nothing can be found, <code>0</code> is returned.</p>
<p>If the result is out of range, the value returned is one of
<code>LONG_MIN</code>, <code>LONG_MAX</code>, <code>LLONG_MIN</code>,
<code>LLONG_MAX</code>, <code>ULONG_MAX</code> or
<code>ULLONG_MAX</code>, as appropriate. And <code>errno</code> is set
to <code>ERANGE</code>.</p>
<h3 class="unnumbered unlisted" id="example-248">Example</h3>
<div class="sourceCode" id="cb1573"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1573-1"><a href="wchar.html#cb1573-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1573-2"><a href="wchar.html#cb1573-2"></a></span>
<span id="cb1573-3"><a href="wchar.html#cb1573-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1573-4"><a href="wchar.html#cb1573-4"></a><span class="op">{</span></span>
<span id="cb1573-5"><a href="wchar.html#cb1573-5"></a>    <span class="co">// All output in decimal (base 10)</span></span>
<span id="cb1573-6"><a href="wchar.html#cb1573-6"></a></span>
<span id="cb1573-7"><a href="wchar.html#cb1573-7"></a>    wprintf<span class="op">(</span>L<span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcstol<span class="op">(</span>L<span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span>     <span class="co">// 123</span></span>
<span id="cb1573-8"><a href="wchar.html#cb1573-8"></a>    wprintf<span class="op">(</span>L<span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcstol<span class="op">(</span>L<span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">10</span><span class="op">));</span>    <span class="co">// 123</span></span>
<span id="cb1573-9"><a href="wchar.html#cb1573-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcstol<span class="op">(</span>L<span class="st">"101010"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">2</span><span class="op">));</span>  <span class="co">// binary, 42</span></span>
<span id="cb1573-10"><a href="wchar.html#cb1573-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcstol<span class="op">(</span>L<span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">8</span><span class="op">));</span>     <span class="co">// octal, 83</span></span>
<span id="cb1573-11"><a href="wchar.html#cb1573-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcstol<span class="op">(</span>L<span class="st">"123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">16</span><span class="op">));</span>    <span class="co">// hex, 291</span></span>
<span id="cb1573-12"><a href="wchar.html#cb1573-12"></a></span>
<span id="cb1573-13"><a href="wchar.html#cb1573-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcstol<span class="op">(</span>L<span class="st">"0123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span>    <span class="co">// octal, 83</span></span>
<span id="cb1573-14"><a href="wchar.html#cb1573-14"></a>    wprintf<span class="op">(</span>L<span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcstol<span class="op">(</span>L<span class="st">"0x123"</span><span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span>   <span class="co">// hex, 291</span></span>
<span id="cb1573-15"><a href="wchar.html#cb1573-15"></a></span>
<span id="cb1573-16"><a href="wchar.html#cb1573-16"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>badchar<span class="op">;</span></span>
<span id="cb1573-17"><a href="wchar.html#cb1573-17"></a>    <span class="dt">long</span> <span class="dt">int</span> x <span class="op">=</span> wcstol<span class="op">(</span>L<span class="st">"   1234beej"</span><span class="op">,</span> <span class="op">&amp;</span>badchar<span class="op">,</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb1573-18"><a href="wchar.html#cb1573-18"></a></span>
<span id="cb1573-19"><a href="wchar.html#cb1573-19"></a>    wprintf<span class="op">(</span>L<span class="st">"Value is %ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span>                  <span class="co">// Value is 1234</span></span>
<span id="cb1573-20"><a href="wchar.html#cb1573-20"></a>    wprintf<span class="op">(</span>L<span class="st">"Bad chars at </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> badchar<span class="op">);</span>    <span class="co">// Bad chars at "beej"</span></span>
<span id="cb1573-21"><a href="wchar.html#cb1573-21"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1574"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1574-1"><a href="wchar.html#cb1574-1" aria-hidden="true" tabindex="-1"></a>123</span>
<span id="cb1574-2"><a href="wchar.html#cb1574-2" aria-hidden="true" tabindex="-1"></a>123</span>
<span id="cb1574-3"><a href="wchar.html#cb1574-3" aria-hidden="true" tabindex="-1"></a>42</span>
<span id="cb1574-4"><a href="wchar.html#cb1574-4" aria-hidden="true" tabindex="-1"></a>83</span>
<span id="cb1574-5"><a href="wchar.html#cb1574-5" aria-hidden="true" tabindex="-1"></a>291</span>
<span id="cb1574-6"><a href="wchar.html#cb1574-6" aria-hidden="true" tabindex="-1"></a>83</span>
<span id="cb1574-7"><a href="wchar.html#cb1574-7" aria-hidden="true" tabindex="-1"></a>291</span>
<span id="cb1574-8"><a href="wchar.html#cb1574-8" aria-hidden="true" tabindex="-1"></a>Value is 1234</span>
<span id="cb1574-9"><a href="wchar.html#cb1574-9" aria-hidden="true" tabindex="-1"></a>Bad chars at "beej"</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-233">See Also</h3>
<p><a href="wchar.html#man-wcstod"><code>wcstod()</code></a>, <a href="#man-strtol"><code>strtol()</code></a>, <a href="#errno"><code>errno</code></a>, <a href="#man-wcstoimax"><code>wcstoimax()</code></a>, <a href="#man-wcstoimax"><code>wcstoumax()</code></a></p>
<hr>
<h2 data-number="69.14" id="man-wcscpy"><span class="header-section-number">69.14</span> <code>wcscpy()</code>
<code>wcsncpy()</code></h2>
<p>Copy a wide string</p>
<h3 class="unnumbered unlisted" id="synopsis-247">Synopsis</h3>
<div class="sourceCode" id="cb1575"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1575-1"><a href="wchar.html#cb1575-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1575-2"><a href="wchar.html#cb1575-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1575-3"><a href="wchar.html#cb1575-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcscpy<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">);</span></span>
<span id="cb1575-4"><a href="wchar.html#cb1575-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1575-5"><a href="wchar.html#cb1575-5" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcsncpy<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span></span>
<span id="cb1575-6"><a href="wchar.html#cb1575-6" aria-hidden="true" tabindex="-1"></a>                 <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-247">Description</h3>
<p>These are the wide versions of <a href="#man-strcpy"><code>strcpy()</code></a> and <a href="#man-strcpy"><code>strncpy()</code></a>.</p>
<p>They’ll copy a string up to a wide NUL. Or, in the case of the safer
<code>wcsncpy()</code>, until then or until <code>n</code> wide
characters are copied.</p>
<p>If the string in <code>s1</code> is shorter than <code>n</code>,
<code>wcsncpy()</code> will pad <code>s2</code> with wide NUL characters
until the <code>n</code>th wide character is reached.</p>
<p>Even though <code>wcsncpy()</code> is safer because it will never
overrun the end of <code>s2</code> (assuming you set <code>n</code>
correctly), it’s still unsafe a NUL is not found in <code>s1</code> in
the first <code>n</code> characters. In that case, <code>s2</code> will
not be NUL-terminated. Always make sure <code>n</code> is greater than
the string length of <code>s1</code>!</p>
<h3 class="unnumbered unlisted" id="return-value-245">Return Value</h3>
<p>Returns <code>s1</code>.</p>
<h3 class="unnumbered unlisted" id="example-249">Example</h3>
<div class="sourceCode" id="cb1576"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1576-1"><a href="wchar.html#cb1576-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1576-2"><a href="wchar.html#cb1576-2"></a></span>
<span id="cb1576-3"><a href="wchar.html#cb1576-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1576-4"><a href="wchar.html#cb1576-4"></a><span class="op">{</span></span>
<span id="cb1576-5"><a href="wchar.html#cb1576-5"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s1 <span class="op">=</span> L<span class="st">"Hello!"</span><span class="op">;</span></span>
<span id="cb1576-6"><a href="wchar.html#cb1576-6"></a>    <span class="dt">wchar_t</span> s2<span class="op">[</span><span class="dv">10</span><span class="op">];</span></span>
<span id="cb1576-7"><a href="wchar.html#cb1576-7"></a></span>
<span id="cb1576-8"><a href="wchar.html#cb1576-8"></a>    wcsncpy<span class="op">(</span>s2<span class="op">,</span> s1<span class="op">,</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb1576-9"><a href="wchar.html#cb1576-9"></a></span>
<span id="cb1576-10"><a href="wchar.html#cb1576-10"></a>    wprintf<span class="op">(</span>L<span class="st">"</span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> s2<span class="op">);</span>  <span class="co">// "Hello!"</span></span>
<span id="cb1576-11"><a href="wchar.html#cb1576-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-234">See Also</h3>
<p><a href="wchar.html#man-wmemcpy"><code>wmemcpy()</code></a>, <a href="#man-wmemcpy"><code>wmemmove()</code></a> <a href="#man-strcpy"><code>strcpy()</code></a>, <a href="#man-strcpy"><code>strncpy()</code></a></p>
<hr>
<h2 data-number="69.15" id="man-wmemcpy"><span class="header-section-number">69.15</span> <code>wmemcpy()</code>
<code>wmemmove()</code></h2>
<p>Copy wide characters</p>
<h3 class="unnumbered unlisted" id="synopsis-248">Synopsis</h3>
<div class="sourceCode" id="cb1577"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1577-1"><a href="wchar.html#cb1577-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1577-2"><a href="wchar.html#cb1577-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1577-3"><a href="wchar.html#cb1577-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wmemcpy<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span></span>
<span id="cb1577-4"><a href="wchar.html#cb1577-4" aria-hidden="true" tabindex="-1"></a>                 <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span>
<span id="cb1577-5"><a href="wchar.html#cb1577-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1577-6"><a href="wchar.html#cb1577-6" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wmemmove<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-248">Description</h3>
<p>These are the wide versions of <a href="#man-memcpy"><code>memcpy()</code></a> and <a href="#man-memcpy"><code>memmove()</code></a>.</p>
<p>They copy <code>n</code> wide characters from <code>s2</code> to
<code>s1</code>.</p>
<p>They’re the same except that <code>wmemmove()</code> is guaranteed to
work with overlapping memory regions, and <code>wmemcpy()</code> is
not.</p>
<h3 class="unnumbered unlisted" id="return-value-246">Return Value</h3>
<p>Both functions return the pointer <code>s1</code>.</p>
<h3 class="unnumbered unlisted" id="example-250">Example</h3>
<div class="sourceCode" id="cb1578"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1578-1"><a href="wchar.html#cb1578-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1578-2"><a href="wchar.html#cb1578-2"></a></span>
<span id="cb1578-3"><a href="wchar.html#cb1578-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1578-4"><a href="wchar.html#cb1578-4"></a><span class="op">{</span></span>
<span id="cb1578-5"><a href="wchar.html#cb1578-5"></a>    <span class="dt">wchar_t</span> s<span class="op">[</span><span class="dv">100</span><span class="op">]</span> <span class="op">=</span> L<span class="st">"Goats"</span><span class="op">;</span></span>
<span id="cb1578-6"><a href="wchar.html#cb1578-6"></a>    <span class="dt">wchar_t</span> t<span class="op">[</span><span class="dv">100</span><span class="op">];</span></span>
<span id="cb1578-7"><a href="wchar.html#cb1578-7"></a></span>
<span id="cb1578-8"><a href="wchar.html#cb1578-8"></a>    wmemcpy<span class="op">(</span>t<span class="op">,</span> s<span class="op">,</span> <span class="dv">6</span><span class="op">);</span>       <span class="co">// Copy non-overlapping memory</span></span>
<span id="cb1578-9"><a href="wchar.html#cb1578-9"></a></span>
<span id="cb1578-10"><a href="wchar.html#cb1578-10"></a>    wmemmove<span class="op">(</span>s <span class="op">+</span> <span class="dv">2</span><span class="op">,</span> s<span class="op">,</span> <span class="dv">6</span><span class="op">);</span>  <span class="co">// Copy overlapping memory</span></span>
<span id="cb1578-11"><a href="wchar.html#cb1578-11"></a></span>
<span id="cb1578-12"><a href="wchar.html#cb1578-12"></a>    wprintf<span class="op">(</span>L<span class="st">"s is </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span></span>
<span id="cb1578-13"><a href="wchar.html#cb1578-13"></a>    wprintf<span class="op">(</span>L<span class="st">"t is </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> t<span class="op">);</span></span>
<span id="cb1578-14"><a href="wchar.html#cb1578-14"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1579"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1579-1"><a href="wchar.html#cb1579-1" aria-hidden="true" tabindex="-1"></a>s is "GoGoats"</span>
<span id="cb1579-2"><a href="wchar.html#cb1579-2" aria-hidden="true" tabindex="-1"></a>t is "Goats"</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-235">See Also</h3>
<p><a href="wchar.html#man-wcscpy"><code>wcscpy()</code></a>, <a href="#man-wcscpy"><code>wcsncpy()</code></a>, <a href="#man-memcpy"><code>memcpy()</code></a>, <a href="#man-memcpy"><code>memmove()</code></a></p>
<hr>
<h2 data-number="69.16" id="man-wcscat"><span class="header-section-number">69.16</span> <code>wcscat()</code>
<code>wcsncat()</code></h2>
<p>Concatenate wide strings</p>
<h3 class="unnumbered unlisted" id="synopsis-249">Synopsis</h3>
<div class="sourceCode" id="cb1580"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1580-1"><a href="wchar.html#cb1580-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1580-2"><a href="wchar.html#cb1580-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1580-3"><a href="wchar.html#cb1580-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcscat<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">);</span></span>
<span id="cb1580-4"><a href="wchar.html#cb1580-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1580-5"><a href="wchar.html#cb1580-5" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcsncat<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span></span>
<span id="cb1580-6"><a href="wchar.html#cb1580-6" aria-hidden="true" tabindex="-1"></a>                 <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-249">Description</h3>
<p>These are the wide variants of <a href="#man-strcat"><code>strcat()</code></a> and <a href="#man-strcat"><code>strncat()</code></a>.</p>
<p>They concatenate <code>s2</code> onto the end of <code>s1</code>.</p>
<p>They’re the same except <code>wcsncat()</code> gives you the option
to limit the number of wide characters appended.</p>
<p>Note that <code>wcsncat()</code> always adds a NUL terminator to the
end, even if <code>n</code> characters were appended. So be sure to
leave room for that.</p>
<h3 class="unnumbered unlisted" id="return-value-247">Return Value</h3>
<p>Both functions return the pointer <code>s1</code>.</p>
<h3 class="unnumbered unlisted" id="example-251">Example</h3>
<div class="sourceCode" id="cb1581"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1581-1"><a href="wchar.html#cb1581-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1581-2"><a href="wchar.html#cb1581-2"></a></span>
<span id="cb1581-3"><a href="wchar.html#cb1581-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1581-4"><a href="wchar.html#cb1581-4"></a><span class="op">{</span></span>
<span id="cb1581-5"><a href="wchar.html#cb1581-5"></a>    <span class="dt">wchar_t</span> dest<span class="op">[</span><span class="dv">30</span><span class="op">]</span> <span class="op">=</span> L<span class="st">"Hello"</span><span class="op">;</span></span>
<span id="cb1581-6"><a href="wchar.html#cb1581-6"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>src <span class="op">=</span> L<span class="st">", World!"</span><span class="op">;</span></span>
<span id="cb1581-7"><a href="wchar.html#cb1581-7"></a>    <span class="dt">wchar_t</span> numbers<span class="op">[]</span> <span class="op">=</span> L<span class="st">"12345678"</span><span class="op">;</span></span>
<span id="cb1581-8"><a href="wchar.html#cb1581-8"></a></span>
<span id="cb1581-9"><a href="wchar.html#cb1581-9"></a>    wprintf<span class="op">(</span>L<span class="st">"dest before strcat: </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span> <span class="co">// "Hello"</span></span>
<span id="cb1581-10"><a href="wchar.html#cb1581-10"></a></span>
<span id="cb1581-11"><a href="wchar.html#cb1581-11"></a>    wcscat<span class="op">(</span>dest<span class="op">,</span> src<span class="op">);</span></span>
<span id="cb1581-12"><a href="wchar.html#cb1581-12"></a>    wprintf<span class="op">(</span>L<span class="st">"dest after strcat:  </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span> <span class="co">// "Hello, world!"</span></span>
<span id="cb1581-13"><a href="wchar.html#cb1581-13"></a></span>
<span id="cb1581-14"><a href="wchar.html#cb1581-14"></a>    wcsncat<span class="op">(</span>dest<span class="op">,</span> numbers<span class="op">,</span> <span class="dv">3</span><span class="op">);</span> <span class="co">// strcat first 3 chars of numbers</span></span>
<span id="cb1581-15"><a href="wchar.html#cb1581-15"></a>    wprintf<span class="op">(</span>L<span class="st">"dest after strncat: </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span> <span class="co">// "Hello, world!123"</span></span>
<span id="cb1581-16"><a href="wchar.html#cb1581-16"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-236">See Also</h3>
<p><a href="stringref.html#man-strcat"><code>strcat()</code></a>, <a href="#man-strcat"><code>strncat()</code></a></p>
<hr>
<h2 data-number="69.17" id="man-wcscmp"><span class="header-section-number">69.17</span> <code>wcscmp()</code>,
<code>wcsncmp()</code>, <code>wmemcmp()</code></h2>
<p>Compare wide strings or memory</p>
<h3 class="unnumbered unlisted" id="synopsis-250">Synopsis</h3>
<div class="sourceCode" id="cb1582"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1582-1"><a href="wchar.html#cb1582-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1582-2"><a href="wchar.html#cb1582-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1582-3"><a href="wchar.html#cb1582-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wcscmp<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">);</span></span>
<span id="cb1582-4"><a href="wchar.html#cb1582-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1582-5"><a href="wchar.html#cb1582-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wcsncmp<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span>
<span id="cb1582-6"><a href="wchar.html#cb1582-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1582-7"><a href="wchar.html#cb1582-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wmemcmp<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-250">Description</h3>
<p>These are the wide variants of <a href="#man-strcmp"><code>memcmp()</code></a>, <a href="#man-strcmp"><code>strcmp()</code></a>, and <a href="#man-strcmp"><code>strncmp()</code></a>.</p>
<p><code>wcscmp()</code> and <code>wcsncmp()</code> both compare strings
until a NUL character.</p>
<p><code>wcsncmp()</code> also has the additional restriction that it
will only compare the first <code>n</code> characters.</p>
<p><code>wmemcmp()</code> is like <code>wcsncmp()</code> except it won’t
stop at a NUL.</p>
<p>The comparison is done against the character value (which might (or
might not) be its Unicode code point).</p>
<h3 class="unnumbered unlisted" id="return-value-248">Return Value</h3>
<p>Returns zero if both regions are equal.</p>
<p>Returns a negative number if the region pointed to by <code>s1</code>
is less than <code>s2</code>.</p>
<p>Returns a positive number if the region pointed to by <code>s1</code>
is greater than <code>s2</code>.</p>
<h3 class="unnumbered unlisted" id="example-252">Example</h3>
<div class="sourceCode" id="cb1583"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1583-1"><a href="wchar.html#cb1583-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1583-2"><a href="wchar.html#cb1583-2"></a></span>
<span id="cb1583-3"><a href="wchar.html#cb1583-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1583-4"><a href="wchar.html#cb1583-4"></a><span class="op">{</span></span>
<span id="cb1583-5"><a href="wchar.html#cb1583-5"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s1 <span class="op">=</span> L<span class="st">"Muffin"</span><span class="op">;</span></span>
<span id="cb1583-6"><a href="wchar.html#cb1583-6"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s2 <span class="op">=</span> L<span class="st">"Muffin Sandwich"</span><span class="op">;</span></span>
<span id="cb1583-7"><a href="wchar.html#cb1583-7"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s3 <span class="op">=</span> L<span class="st">"Muffin"</span><span class="op">;</span></span>
<span id="cb1583-8"><a href="wchar.html#cb1583-8"></a></span>
<span id="cb1583-9"><a href="wchar.html#cb1583-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcscmp<span class="op">(</span>L<span class="st">"Biscuits"</span><span class="op">,</span> L<span class="st">"Kittens"</span><span class="op">));</span> <span class="co">// &lt;0 since 'B' &lt; 'K'</span></span>
<span id="cb1583-10"><a href="wchar.html#cb1583-10"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcscmp<span class="op">(</span>L<span class="st">"Kittens"</span><span class="op">,</span> L<span class="st">"Biscuits"</span><span class="op">));</span> <span class="co">// &gt;0 since 'K' &gt; 'B'</span></span>
<span id="cb1583-11"><a href="wchar.html#cb1583-11"></a></span>
<span id="cb1583-12"><a href="wchar.html#cb1583-12"></a>    <span class="cf">if</span> <span class="op">(</span>wcscmp<span class="op">(</span>s1<span class="op">,</span> s2<span class="op">)</span> <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1583-13"><a href="wchar.html#cb1583-13"></a>        wprintf<span class="op">(</span>L<span class="st">"This won't get printed because the strings differ</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1583-14"><a href="wchar.html#cb1583-14"></a></span>
<span id="cb1583-15"><a href="wchar.html#cb1583-15"></a>    <span class="cf">if</span> <span class="op">(</span>wcscmp<span class="op">(</span>s1<span class="op">,</span> s3<span class="op">)</span> <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1583-16"><a href="wchar.html#cb1583-16"></a>        wprintf<span class="op">(</span>L<span class="st">"This will print because s1 and s3 are the same</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1583-17"><a href="wchar.html#cb1583-17"></a></span>
<span id="cb1583-18"><a href="wchar.html#cb1583-18"></a>    <span class="co">// this is a little weird...but if the strings are the same, it'll</span></span>
<span id="cb1583-19"><a href="wchar.html#cb1583-19"></a>    <span class="co">// return zero, which can also be thought of as "false". Not-false</span></span>
<span id="cb1583-20"><a href="wchar.html#cb1583-20"></a>    <span class="co">// is "true", so (!wcscmp()) will be true if the strings are the</span></span>
<span id="cb1583-21"><a href="wchar.html#cb1583-21"></a>    <span class="co">// same. yes, it's odd, but you see this all the time in the wild</span></span>
<span id="cb1583-22"><a href="wchar.html#cb1583-22"></a>    <span class="co">// so you might as well get used to it:</span></span>
<span id="cb1583-23"><a href="wchar.html#cb1583-23"></a></span>
<span id="cb1583-24"><a href="wchar.html#cb1583-24"></a>    <span class="cf">if</span> <span class="op">(!</span>wcscmp<span class="op">(</span>s1<span class="op">,</span> s3<span class="op">))</span></span>
<span id="cb1583-25"><a href="wchar.html#cb1583-25"></a>        wprintf<span class="op">(</span>L<span class="st">"The strings are the same!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1583-26"><a href="wchar.html#cb1583-26"></a></span>
<span id="cb1583-27"><a href="wchar.html#cb1583-27"></a>    <span class="cf">if</span> <span class="op">(!</span>wcsncmp<span class="op">(</span>s1<span class="op">,</span> s2<span class="op">,</span> <span class="dv">6</span><span class="op">))</span></span>
<span id="cb1583-28"><a href="wchar.html#cb1583-28"></a>        wprintf<span class="op">(</span>L<span class="st">"The first 6 characters of s1 and s2 are the same</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1583-29"><a href="wchar.html#cb1583-29"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1584"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1584-1"><a href="wchar.html#cb1584-1" aria-hidden="true" tabindex="-1"></a>-1</span>
<span id="cb1584-2"><a href="wchar.html#cb1584-2" aria-hidden="true" tabindex="-1"></a>1</span>
<span id="cb1584-3"><a href="wchar.html#cb1584-3" aria-hidden="true" tabindex="-1"></a>This will print because s1 and s3 are the same</span>
<span id="cb1584-4"><a href="wchar.html#cb1584-4" aria-hidden="true" tabindex="-1"></a>The strings are the same!</span>
<span id="cb1584-5"><a href="wchar.html#cb1584-5" aria-hidden="true" tabindex="-1"></a>The first 6 characters of s1 and s2 are the same</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-237">See Also</h3>
<p><a href="wchar.html#man-wcscoll"><code>wcscoll()</code></a>, <a href="#man-strcmp"><code>memcmp()</code></a>, <a href="#man-strcmp"><code>strcmp()</code></a>, <a href="#man-strcmp"><code>strncmp()</code></a></p>
<hr>
<h2 data-number="69.18" id="man-wcscoll"><span class="header-section-number">69.18</span> <code>wcscoll()</code></h2>
<p>Compare two wide strings accounting for locale</p>
<h3 class="unnumbered unlisted" id="synopsis-251">Synopsis</h3>
<div class="sourceCode" id="cb1585"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1585-1"><a href="wchar.html#cb1585-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1585-2"><a href="wchar.html#cb1585-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1585-3"><a href="wchar.html#cb1585-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wcscoll<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-251">Description</h3>
<p>This is the wide version of <a href="#man-strcoll"><code>strcoll()</code></a>. See <a href="#man-strcoll"><code>that reference page</code></a> for
details.</p>
<p>This is slower than <code>wcscmp()</code>, so only use it if you need
the locale-specific compare.</p>
<h3 class="unnumbered unlisted" id="return-value-249">Return Value</h3>
<p>Returns zero if both regions are equal in this locale.</p>
<p>Returns a negative number if the region pointed to by <code>s1</code>
is less than <code>s2</code> in this locale.</p>
<p>Returns a positive number if the region pointed to by <code>s1</code>
is greater than <code>s2</code> in this locale.</p>
<h3 class="unnumbered unlisted" id="example-253">Example</h3>
<div class="sourceCode" id="cb1586"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1586-1"><a href="wchar.html#cb1586-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1586-2"><a href="wchar.html#cb1586-2"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1586-3"><a href="wchar.html#cb1586-3"></a></span>
<span id="cb1586-4"><a href="wchar.html#cb1586-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1586-5"><a href="wchar.html#cb1586-5"></a><span class="op">{</span></span>
<span id="cb1586-6"><a href="wchar.html#cb1586-6"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1586-7"><a href="wchar.html#cb1586-7"></a></span>
<span id="cb1586-8"><a href="wchar.html#cb1586-8"></a>    <span class="co">// If your source character set doesn't support "é" in a string</span></span>
<span id="cb1586-9"><a href="wchar.html#cb1586-9"></a>    <span class="co">// you can replace it with `\u00e9`, the Unicode code point</span></span>
<span id="cb1586-10"><a href="wchar.html#cb1586-10"></a>    <span class="co">// for "é".</span></span>
<span id="cb1586-11"><a href="wchar.html#cb1586-11"></a></span>
<span id="cb1586-12"><a href="wchar.html#cb1586-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcscmp<span class="op">(</span>L<span class="st">"é"</span><span class="op">,</span> L<span class="st">"f"</span><span class="op">));</span>   <span class="co">// Reports é &gt; f, yuck.</span></span>
<span id="cb1586-13"><a href="wchar.html#cb1586-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcscoll<span class="op">(</span>L<span class="st">"é"</span><span class="op">,</span> L<span class="st">"f"</span><span class="op">));</span>  <span class="co">// Reports é &lt; f, yay!</span></span>
<span id="cb1586-14"><a href="wchar.html#cb1586-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-238">See Also</h3>
<p><a href="wchar.html#man-wcscmp"><code>wcscmp()</code></a>, <a href="#man-wcsxfrm"><code>wcsxfrm()</code></a>, <a href="#man-strcoll"><code>strcoll()</code></a></p>
<hr>
<h2 data-number="69.19" id="man-wcsxfrm"><span class="header-section-number">69.19</span> <code>wcsxfrm()</code></h2>
<p>Transform a wide string for comparing based on locale</p>
<h3 class="unnumbered unlisted" id="synopsis-252">Synopsis</h3>
<div class="sourceCode" id="cb1587"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1587-1"><a href="wchar.html#cb1587-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1587-2"><a href="wchar.html#cb1587-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1587-3"><a href="wchar.html#cb1587-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcsxfrm<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span></span>
<span id="cb1587-4"><a href="wchar.html#cb1587-4" aria-hidden="true" tabindex="-1"></a>               <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-252">Description</h3>
<p>This is the wide variant of <a href="#man-strxfrm"><code>strxfrm()</code></a>. See <a href="#man-strxfrm">that reference page</a> for details.</p>
<h3 class="unnumbered unlisted" id="return-value-250">Return Value</h3>
<p>Returns the length of the transformed wide string in wide
characters.</p>
<p>If the return value is greater than <code>n</code>, all bets are off
for the result in <code>s1</code>.</p>
<h3 class="unnumbered unlisted" id="example-254">Example</h3>
<div class="sourceCode" id="cb1588"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1588-1"><a href="wchar.html#cb1588-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1588-2"><a href="wchar.html#cb1588-2"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1588-3"><a href="wchar.html#cb1588-3"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1588-4"><a href="wchar.html#cb1588-4"></a></span>
<span id="cb1588-5"><a href="wchar.html#cb1588-5"></a><span class="co">// Transform a string for comparison, returning a malloc'd</span></span>
<span id="cb1588-6"><a href="wchar.html#cb1588-6"></a><span class="co">// result</span></span>
<span id="cb1588-7"><a href="wchar.html#cb1588-7"></a><span class="dt">wchar_t</span> <span class="op">*</span>get_xfrm_str<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span>s<span class="op">)</span></span>
<span id="cb1588-8"><a href="wchar.html#cb1588-8"></a><span class="op">{</span></span>
<span id="cb1588-9"><a href="wchar.html#cb1588-9"></a>    <span class="dt">int</span> len <span class="op">=</span> wcsxfrm<span class="op">(</span>NULL<span class="op">,</span> s<span class="op">,</span> <span class="dv">0</span><span class="op">)</span> <span class="op">+</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1588-10"><a href="wchar.html#cb1588-10"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>d <span class="op">=</span> malloc<span class="op">(</span>len <span class="op">*</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">wchar_t</span><span class="op">));</span></span>
<span id="cb1588-11"><a href="wchar.html#cb1588-11"></a></span>
<span id="cb1588-12"><a href="wchar.html#cb1588-12"></a>    wcsxfrm<span class="op">(</span>d<span class="op">,</span> s<span class="op">,</span> len<span class="op">);</span></span>
<span id="cb1588-13"><a href="wchar.html#cb1588-13"></a></span>
<span id="cb1588-14"><a href="wchar.html#cb1588-14"></a>    <span class="cf">return</span> d<span class="op">;</span></span>
<span id="cb1588-15"><a href="wchar.html#cb1588-15"></a><span class="op">}</span></span>
<span id="cb1588-16"><a href="wchar.html#cb1588-16"></a></span>
<span id="cb1588-17"><a href="wchar.html#cb1588-17"></a><span class="co">// Does half the work of a regular wcscoll() because the second</span></span>
<span id="cb1588-18"><a href="wchar.html#cb1588-18"></a><span class="co">// string arrives already transformed.</span></span>
<span id="cb1588-19"><a href="wchar.html#cb1588-19"></a><span class="dt">int</span> half_wcscoll<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2_transformed<span class="op">)</span></span>
<span id="cb1588-20"><a href="wchar.html#cb1588-20"></a><span class="op">{</span></span>
<span id="cb1588-21"><a href="wchar.html#cb1588-21"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s1_transformed <span class="op">=</span> get_xfrm_str<span class="op">(</span>s1<span class="op">);</span></span>
<span id="cb1588-22"><a href="wchar.html#cb1588-22"></a></span>
<span id="cb1588-23"><a href="wchar.html#cb1588-23"></a>    <span class="dt">int</span> result <span class="op">=</span> wcscmp<span class="op">(</span>s1_transformed<span class="op">,</span> s2_transformed<span class="op">);</span></span>
<span id="cb1588-24"><a href="wchar.html#cb1588-24"></a></span>
<span id="cb1588-25"><a href="wchar.html#cb1588-25"></a>    free<span class="op">(</span>s1_transformed<span class="op">);</span></span>
<span id="cb1588-26"><a href="wchar.html#cb1588-26"></a></span>
<span id="cb1588-27"><a href="wchar.html#cb1588-27"></a>    <span class="cf">return</span> result<span class="op">;</span></span>
<span id="cb1588-28"><a href="wchar.html#cb1588-28"></a><span class="op">}</span></span>
<span id="cb1588-29"><a href="wchar.html#cb1588-29"></a></span>
<span id="cb1588-30"><a href="wchar.html#cb1588-30"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1588-31"><a href="wchar.html#cb1588-31"></a><span class="op">{</span></span>
<span id="cb1588-32"><a href="wchar.html#cb1588-32"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1588-33"><a href="wchar.html#cb1588-33"></a></span>
<span id="cb1588-34"><a href="wchar.html#cb1588-34"></a>    <span class="co">// Pre-transform the string to compare against</span></span>
<span id="cb1588-35"><a href="wchar.html#cb1588-35"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s <span class="op">=</span> get_xfrm_str<span class="op">(</span>L<span class="st">"éfg"</span><span class="op">);</span></span>
<span id="cb1588-36"><a href="wchar.html#cb1588-36"></a></span>
<span id="cb1588-37"><a href="wchar.html#cb1588-37"></a>    <span class="co">// Repeatedly compare against "éfg" </span></span>
<span id="cb1588-38"><a href="wchar.html#cb1588-38"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> half_wcscoll<span class="op">(</span>L<span class="st">"fgh"</span><span class="op">,</span> s<span class="op">));</span>  <span class="co">// "fgh" &gt; "éfg"</span></span>
<span id="cb1588-39"><a href="wchar.html#cb1588-39"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> half_wcscoll<span class="op">(</span>L<span class="st">"àbc"</span><span class="op">,</span> s<span class="op">));</span>  <span class="co">// "àbc" &lt; "éfg"</span></span>
<span id="cb1588-40"><a href="wchar.html#cb1588-40"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> half_wcscoll<span class="op">(</span>L<span class="st">"ĥij"</span><span class="op">,</span> s<span class="op">));</span>  <span class="co">// "ĥij" &gt; "éfg"</span></span>
<span id="cb1588-41"><a href="wchar.html#cb1588-41"></a>    </span>
<span id="cb1588-42"><a href="wchar.html#cb1588-42"></a>    free<span class="op">(</span>s<span class="op">);</span></span>
<span id="cb1588-43"><a href="wchar.html#cb1588-43"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1589"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1589-1"><a href="wchar.html#cb1589-1" aria-hidden="true" tabindex="-1"></a>1</span>
<span id="cb1589-2"><a href="wchar.html#cb1589-2" aria-hidden="true" tabindex="-1"></a>-1</span>
<span id="cb1589-3"><a href="wchar.html#cb1589-3" aria-hidden="true" tabindex="-1"></a>1</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-239">See Also</h3>
<p><a href="wchar.html#man-wcscmp"><code>wcscmp()</code></a>, <a href="#man-wcscoll"><code>wcscoll()</code></a>, <a href="#man-strxfrm"><code>strxfrm()</code></a></p>
<hr>
<h2 data-number="69.20" id="man-wcschr"><span class="header-section-number">69.20</span> <code>wcschr()</code>
<code>wcsrchr()</code></h2>
<p>Find a wide character in a wide string</p>
<h3 class="unnumbered unlisted" id="synopsis-253">Synopsis</h3>
<div class="sourceCode" id="cb1590"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1590-1"><a href="wchar.html#cb1590-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1590-2"><a href="wchar.html#cb1590-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1590-3"><a href="wchar.html#cb1590-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcschr<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s<span class="op">,</span> <span class="dt">wchar_t</span> c<span class="op">);</span></span>
<span id="cb1590-4"><a href="wchar.html#cb1590-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1590-5"><a href="wchar.html#cb1590-5" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcsrchr<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s<span class="op">,</span> <span class="dt">wchar_t</span> c<span class="op">);</span></span>
<span id="cb1590-6"><a href="wchar.html#cb1590-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1590-7"><a href="wchar.html#cb1590-7" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wmemchr<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s<span class="op">,</span> <span class="dt">wchar_t</span> c<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-253">Description</h3>
<p>These are the wide equivalents to <a href="#man-strchr"><code>strchr()</code></a>, <a href="#man-strchr"><code>strrchr()</code></a>, and <a href="#man-strchr"><code>memchr()</code></a>.</p>
<p>They search for wide characters in a wide string from the front
(<code>wcschr()</code>), the end (<code>wcsrchr()</code>) or for an
arbitrary number of wide characters (<code>wmemchr()</code>).</p>
<h3 class="unnumbered unlisted" id="return-value-251">Return Value</h3>
<p>All three functions return a pointer to the wide character found, or
<code>NULL</code> if the character, sadly, isn’t found.</p>
<h3 class="unnumbered unlisted" id="example-255">Example</h3>
<div class="sourceCode" id="cb1591"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1591-1"><a href="wchar.html#cb1591-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1591-2"><a href="wchar.html#cb1591-2"></a></span>
<span id="cb1591-3"><a href="wchar.html#cb1591-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1591-4"><a href="wchar.html#cb1591-4"></a><span class="op">{</span></span>
<span id="cb1591-5"><a href="wchar.html#cb1591-5"></a>    <span class="co">// "Hello, world!"</span></span>
<span id="cb1591-6"><a href="wchar.html#cb1591-6"></a>    <span class="co">//       ^  ^   ^</span></span>
<span id="cb1591-7"><a href="wchar.html#cb1591-7"></a>    <span class="co">//       A  B   C</span></span>
<span id="cb1591-8"><a href="wchar.html#cb1591-8"></a></span>
<span id="cb1591-9"><a href="wchar.html#cb1591-9"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>str <span class="op">=</span> L<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb1591-10"><a href="wchar.html#cb1591-10"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>p<span class="op">;</span></span>
<span id="cb1591-11"><a href="wchar.html#cb1591-11"></a></span>
<span id="cb1591-12"><a href="wchar.html#cb1591-12"></a>    p <span class="op">=</span> wcschr<span class="op">(</span>str<span class="op">,</span> <span class="ch">','</span><span class="op">);</span>       <span class="co">// p now points at position A</span></span>
<span id="cb1591-13"><a href="wchar.html#cb1591-13"></a>    p <span class="op">=</span> wcsrchr<span class="op">(</span>str<span class="op">,</span> <span class="ch">'o'</span><span class="op">);</span>      <span class="co">// p now points at position B</span></span>
<span id="cb1591-14"><a href="wchar.html#cb1591-14"></a></span>
<span id="cb1591-15"><a href="wchar.html#cb1591-15"></a>    p <span class="op">=</span> wmemchr<span class="op">(</span>str<span class="op">,</span> <span class="ch">'!'</span><span class="op">,</span> <span class="dv">13</span><span class="op">);</span>   <span class="co">// p now points at position C</span></span>
<span id="cb1591-16"><a href="wchar.html#cb1591-16"></a></span>
<span id="cb1591-17"><a href="wchar.html#cb1591-17"></a>    <span class="co">// repeatedly find all occurrences of the letter 'B'</span></span>
<span id="cb1591-18"><a href="wchar.html#cb1591-18"></a>    str <span class="op">=</span> L<span class="st">"A BIG BROWN BAT BIT BEEJ"</span><span class="op">;</span></span>
<span id="cb1591-19"><a href="wchar.html#cb1591-19"></a></span>
<span id="cb1591-20"><a href="wchar.html#cb1591-20"></a>    <span class="cf">for</span><span class="op">(</span>p <span class="op">=</span> wcschr<span class="op">(</span>str<span class="op">,</span> <span class="ch">'B'</span><span class="op">);</span> p <span class="op">!=</span> NULL<span class="op">;</span> p <span class="op">=</span> wcschr<span class="op">(</span>p <span class="op">+</span> <span class="dv">1</span><span class="op">,</span> <span class="ch">'B'</span><span class="op">))</span> <span class="op">{</span></span>
<span id="cb1591-21"><a href="wchar.html#cb1591-21"></a>        wprintf<span class="op">(</span>L<span class="st">"Found a 'B' here: %ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p<span class="op">);</span></span>
<span id="cb1591-22"><a href="wchar.html#cb1591-22"></a>    <span class="op">}</span></span>
<span id="cb1591-23"><a href="wchar.html#cb1591-23"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1592"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1592-1"><a href="wchar.html#cb1592-1" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BIG BROWN BAT BIT BEEJ</span>
<span id="cb1592-2"><a href="wchar.html#cb1592-2" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BROWN BAT BIT BEEJ</span>
<span id="cb1592-3"><a href="wchar.html#cb1592-3" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BAT BIT BEEJ</span>
<span id="cb1592-4"><a href="wchar.html#cb1592-4" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BIT BEEJ</span>
<span id="cb1592-5"><a href="wchar.html#cb1592-5" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BEEJ</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-240">See Also</h3>
<p><a href="stringref.html#man-strchr"><code>strchr()</code></a>, <a href="#man-strchr"><code>strrchr()</code></a>, <a href="#man-strchr"><code>memchr()</code></a></p>
<hr>
<h2 data-number="69.21" id="man-wcsspn"><span class="header-section-number">69.21</span> <code>wcsspn()</code>
<code>wcscspn()</code></h2>
<p>Return the length of a wide string consisting entirely of a set of
wide characters, or of not a set of wide characters</p>
<h3 class="unnumbered unlisted" id="synopsis-254">Synopsis</h3>
<div class="sourceCode" id="cb1593"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1593-1"><a href="wchar.html#cb1593-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1593-2"><a href="wchar.html#cb1593-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1593-3"><a href="wchar.html#cb1593-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcsspn<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">);</span></span>
<span id="cb1593-4"><a href="wchar.html#cb1593-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1593-5"><a href="wchar.html#cb1593-5" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcscspn<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-254">Description</h3>
<p>The are the wide character counterparts to [<code>strspn()</code>]
(#man-strspn)and <a href="stringref.html#man-strspn"><code>strcspn()</code></a>.</p>
<p>They compute the length of the string pointed to by <code>s1</code>
consisting entirely of the characters found in <code>s2</code>. Or, in
the case of <code>wcscspn()</code>, the characters <em>not</em> found in
<code>s2</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-252">Return Value</h3>
<p>The length of the string pointed to by <code>s1</code> consisting
solely of the characters in <code>s2</code> (in the case of
<code>wcsspn()</code>) or of the characters <em>not</em> in
<code>s2</code> (in th ecase of <code>wcscspn()</code>).</p>
<h3 class="unnumbered unlisted" id="example-256">Example</h3>
<div class="sourceCode" id="cb1594"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1594-1"><a href="wchar.html#cb1594-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1594-2"><a href="wchar.html#cb1594-2"></a></span>
<span id="cb1594-3"><a href="wchar.html#cb1594-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1594-4"><a href="wchar.html#cb1594-4"></a><span class="op">{</span></span>
<span id="cb1594-5"><a href="wchar.html#cb1594-5"></a>    <span class="dt">wchar_t</span> str1<span class="op">[]</span> <span class="op">=</span> L<span class="st">"a banana"</span><span class="op">;</span></span>
<span id="cb1594-6"><a href="wchar.html#cb1594-6"></a>    <span class="dt">wchar_t</span> str2<span class="op">[]</span> <span class="op">=</span> L<span class="st">"the bolivian navy on maneuvers in the south pacific"</span><span class="op">;</span></span>
<span id="cb1594-7"><a href="wchar.html#cb1594-7"></a>    <span class="dt">int</span> n<span class="op">;</span></span>
<span id="cb1594-8"><a href="wchar.html#cb1594-8"></a></span>
<span id="cb1594-9"><a href="wchar.html#cb1594-9"></a>    <span class="co">// how many letters in str1 until we reach something that's not a vowel?</span></span>
<span id="cb1594-10"><a href="wchar.html#cb1594-10"></a>    n <span class="op">=</span> wcsspn<span class="op">(</span>str1<span class="op">,</span> L<span class="st">"aeiou"</span><span class="op">);</span></span>
<span id="cb1594-11"><a href="wchar.html#cb1594-11"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> n<span class="op">);</span>  <span class="co">// n == 1, just "a"</span></span>
<span id="cb1594-12"><a href="wchar.html#cb1594-12"></a></span>
<span id="cb1594-13"><a href="wchar.html#cb1594-13"></a>    <span class="co">// how many letters in str1 until we reach something that's not a, b,</span></span>
<span id="cb1594-14"><a href="wchar.html#cb1594-14"></a>    <span class="co">// or space?</span></span>
<span id="cb1594-15"><a href="wchar.html#cb1594-15"></a>    n <span class="op">=</span> wcsspn<span class="op">(</span>str1<span class="op">,</span> L<span class="st">"ab "</span><span class="op">);</span></span>
<span id="cb1594-16"><a href="wchar.html#cb1594-16"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> n<span class="op">);</span>  <span class="co">// n == 4, "a ba"</span></span>
<span id="cb1594-17"><a href="wchar.html#cb1594-17"></a></span>
<span id="cb1594-18"><a href="wchar.html#cb1594-18"></a>    <span class="co">// how many letters in str2 before we get a "y"?</span></span>
<span id="cb1594-19"><a href="wchar.html#cb1594-19"></a>    n <span class="op">=</span> wcscspn<span class="op">(</span>str2<span class="op">,</span> L<span class="st">"y"</span><span class="op">);</span></span>
<span id="cb1594-20"><a href="wchar.html#cb1594-20"></a>    wprintf<span class="op">(</span>L<span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> n<span class="op">);</span>  <span class="co">// n = 16, "the bolivian nav"</span></span>
<span id="cb1594-21"><a href="wchar.html#cb1594-21"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-241">See Also</h3>
<p><a href="wchar.html#man-wcschr"><code>wcschr()</code></a>, <a href="#man-wcschr"><code>wcsrchr()</code></a>, <a href="#man-strspn"><code>strspn()</code></a></p>
<hr>
<h2 data-number="69.22" id="man-wcspbrk"><span class="header-section-number">69.22</span> <code>wcspbrk()</code></h2>
<p>Search a wide string for one of a set of wide characters</p>
<h3 class="unnumbered unlisted" id="synopsis-255">Synopsis</h3>
<div class="sourceCode" id="cb1595"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1595-1"><a href="wchar.html#cb1595-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1595-2"><a href="wchar.html#cb1595-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1595-3"><a href="wchar.html#cb1595-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcspbrk<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-255">Description</h3>
<p>This is the wide character variant of <a href="#man-strpbrk"><code>strpbrk()</code></a>.</p>
<p>It finds the first occurrance of any of a set of wide characters in a
wide string.</p>
<h3 class="unnumbered unlisted" id="return-value-253">Return Value</h3>
<p>Returns a pointer to the first character in the string
<code>s1</code> that exists in the string <code>s2</code>.</p>
<p>Or <code>NULL</code> if none of the characters in <code>s2</code> can
be found in <code>s1</code>.</p>
<h3 class="unnumbered unlisted" id="example-257">Example</h3>
<div class="sourceCode" id="cb1596"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1596-1"><a href="wchar.html#cb1596-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1596-2"><a href="wchar.html#cb1596-2"></a></span>
<span id="cb1596-3"><a href="wchar.html#cb1596-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1596-4"><a href="wchar.html#cb1596-4"></a><span class="op">{</span></span>
<span id="cb1596-5"><a href="wchar.html#cb1596-5"></a>    <span class="co">//  p points here after wcspbrk</span></span>
<span id="cb1596-6"><a href="wchar.html#cb1596-6"></a>    <span class="co">//                  v</span></span>
<span id="cb1596-7"><a href="wchar.html#cb1596-7"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s1 <span class="op">=</span> L<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb1596-8"><a href="wchar.html#cb1596-8"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s2 <span class="op">=</span> L<span class="st">"dow!"</span><span class="op">;</span>  <span class="co">// Match any of these chars</span></span>
<span id="cb1596-9"><a href="wchar.html#cb1596-9"></a></span>
<span id="cb1596-10"><a href="wchar.html#cb1596-10"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>p <span class="op">=</span> wcspbrk<span class="op">(</span>s1<span class="op">,</span> s2<span class="op">);</span>  <span class="co">// p points to the o</span></span>
<span id="cb1596-11"><a href="wchar.html#cb1596-11"></a></span>
<span id="cb1596-12"><a href="wchar.html#cb1596-12"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p<span class="op">);</span>  <span class="co">// "o, world!"</span></span>
<span id="cb1596-13"><a href="wchar.html#cb1596-13"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-242">See Also</h3>
<p><a href="wchar.html#man-wcschr"><code>wcschr()</code></a>, <a href="#man-wcschr"><code>wmemchr()</code></a>, <a href="#man-strpbrk"><code>strpbrk()</code></a></p>
<hr>
<h2 data-number="69.23" id="man-wcsstr"><span class="header-section-number">69.23</span> <code>wcsstr()</code></h2>
<p>Find a wide string in another wide string</p>
<h3 class="unnumbered unlisted" id="synopsis-256">Synopsis</h3>
<div class="sourceCode" id="cb1597"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1597-1"><a href="wchar.html#cb1597-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1597-2"><a href="wchar.html#cb1597-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1597-3"><a href="wchar.html#cb1597-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcsstr<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s2<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-256">Description</h3>
<p>This is the wide variant of <a href="#man-strstr"><code>strstr()</code></a>.</p>
<p>It locates a substring in a string.</p>
<h3 class="unnumbered unlisted" id="return-value-254">Return Value</h3>
<p>Returns a pointer to the location in <code>s1</code> that contains
<code>s2</code>.</p>
<p>Or <code>NULL</code> if <code>s2</code> cannot be found in
<code>s1</code>.</p>
<h3 class="unnumbered unlisted" id="example-258">Example</h3>
<div class="sourceCode" id="cb1598"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1598-1"><a href="wchar.html#cb1598-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1598-2"><a href="wchar.html#cb1598-2"></a></span>
<span id="cb1598-3"><a href="wchar.html#cb1598-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1598-4"><a href="wchar.html#cb1598-4"></a><span class="op">{</span></span>
<span id="cb1598-5"><a href="wchar.html#cb1598-5"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>str <span class="op">=</span> L<span class="st">"The quick brown fox jumped over the lazy dogs."</span><span class="op">;</span></span>
<span id="cb1598-6"><a href="wchar.html#cb1598-6"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>p<span class="op">;</span></span>
<span id="cb1598-7"><a href="wchar.html#cb1598-7"></a></span>
<span id="cb1598-8"><a href="wchar.html#cb1598-8"></a>    p <span class="op">=</span> wcsstr<span class="op">(</span>str<span class="op">,</span> L<span class="st">"lazy"</span><span class="op">);</span></span>
<span id="cb1598-9"><a href="wchar.html#cb1598-9"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p <span class="op">==</span> NULL<span class="op">?</span> L<span class="st">"null"</span><span class="op">:</span> p<span class="op">);</span> <span class="co">// "lazy dogs."</span></span>
<span id="cb1598-10"><a href="wchar.html#cb1598-10"></a></span>
<span id="cb1598-11"><a href="wchar.html#cb1598-11"></a>    <span class="co">// p is NULL after this, since the string "wombat" isn't in str:</span></span>
<span id="cb1598-12"><a href="wchar.html#cb1598-12"></a>    p <span class="op">=</span> wcsstr<span class="op">(</span>str<span class="op">,</span> L<span class="st">"wombat"</span><span class="op">);</span></span>
<span id="cb1598-13"><a href="wchar.html#cb1598-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p <span class="op">==</span> NULL<span class="op">?</span> L<span class="st">"null"</span><span class="op">:</span> p<span class="op">);</span> <span class="co">// "null"</span></span>
<span id="cb1598-14"><a href="wchar.html#cb1598-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-243">See Also</h3>
<p><a href="wchar.html#man-wcschr"><code>wcschr()</code></a>, <a href="#man-wcschr"><code>wcsrchr()</code></a>, <a href="#man-wcsspn"><code>wcsspn()</code></a>, <a href="#man-wcsspn"><code>wcscspn()</code></a>, <a href="#man-strstr"><code>strstr()</code></a></p>
<hr>
<h2 data-number="69.24" id="man-wcstok"><span class="header-section-number">69.24</span> <code>wcstok()</code></h2>
<p>Tokenize a wide string</p>
<h3 class="unnumbered unlisted" id="synopsis-257">Synopsis</h3>
<div class="sourceCode" id="cb1599"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1599-1"><a href="wchar.html#cb1599-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1599-2"><a href="wchar.html#cb1599-2" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>wcstok<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">,</span></span>
<span id="cb1599-3"><a href="wchar.html#cb1599-3" aria-hidden="true" tabindex="-1"></a>                <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> ptr<span class="op">);</span> </span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-257">Description</h3>
<p>This is the wide version of <a href="#man-strtok"><code>strtok()</code></a>.</p>
<p>And, like that one, it modifies the string <code>s1</code>. So make a
copy of it first if you want to preserve the original.</p>
<p>One key difference is that <code>wcstok()</code> can be threadsafe
because you pass in the pointer <code>ptr</code> to the current state of
the transformation. This gets initializers for you when <code>s1</code>
is initially passed in as non-<code>NULL</code>. (Subsequent calls with
a <code>NULL</code> <code>s1</code> cause the state to update.)</p>
<h3 class="unnumbered unlisted" id="return-value-255">Return Value</h3>
<h3 class="unnumbered unlisted" id="example-259">Example</h3>
<div class="sourceCode" id="cb1600"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1600-1"><a href="wchar.html#cb1600-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1600-2"><a href="wchar.html#cb1600-2"></a></span>
<span id="cb1600-3"><a href="wchar.html#cb1600-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1600-4"><a href="wchar.html#cb1600-4"></a><span class="op">{</span></span>
<span id="cb1600-5"><a href="wchar.html#cb1600-5"></a>    <span class="co">// break up the string into a series of space or</span></span>
<span id="cb1600-6"><a href="wchar.html#cb1600-6"></a>    <span class="co">// punctuation-separated words</span></span>
<span id="cb1600-7"><a href="wchar.html#cb1600-7"></a>    <span class="dt">wchar_t</span> str<span class="op">[]</span> <span class="op">=</span> L<span class="st">"Where is my bacon, dude?"</span><span class="op">;</span></span>
<span id="cb1600-8"><a href="wchar.html#cb1600-8"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>token<span class="op">;</span></span>
<span id="cb1600-9"><a href="wchar.html#cb1600-9"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>state<span class="op">;</span></span>
<span id="cb1600-10"><a href="wchar.html#cb1600-10"></a></span>
<span id="cb1600-11"><a href="wchar.html#cb1600-11"></a>    <span class="co">// Note that the following if-do-while construct is very very</span></span>
<span id="cb1600-12"><a href="wchar.html#cb1600-12"></a>    <span class="co">// very very very common to see when using strtok().</span></span>
<span id="cb1600-13"><a href="wchar.html#cb1600-13"></a></span>
<span id="cb1600-14"><a href="wchar.html#cb1600-14"></a>    <span class="co">// grab the first token (making sure there is a first token!)</span></span>
<span id="cb1600-15"><a href="wchar.html#cb1600-15"></a>    <span class="cf">if</span> <span class="op">((</span>token <span class="op">=</span> wcstok<span class="op">(</span>str<span class="op">,</span> L<span class="st">".,?! "</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">))</span> <span class="op">!=</span> NULL<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1600-16"><a href="wchar.html#cb1600-16"></a>        <span class="cf">do</span> <span class="op">{</span></span>
<span id="cb1600-17"><a href="wchar.html#cb1600-17"></a>            wprintf<span class="op">(</span>L<span class="st">"Word: </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> token<span class="op">);</span></span>
<span id="cb1600-18"><a href="wchar.html#cb1600-18"></a></span>
<span id="cb1600-19"><a href="wchar.html#cb1600-19"></a>            <span class="co">// now, the while continuation condition grabs the</span></span>
<span id="cb1600-20"><a href="wchar.html#cb1600-20"></a>            <span class="co">// next token (by passing NULL as the first param)</span></span>
<span id="cb1600-21"><a href="wchar.html#cb1600-21"></a>            <span class="co">// and continues if the token's not NULL:</span></span>
<span id="cb1600-22"><a href="wchar.html#cb1600-22"></a>        <span class="op">}</span> <span class="cf">while</span> <span class="op">((</span>token <span class="op">=</span> wcstok<span class="op">(</span>NULL<span class="op">,</span> L<span class="st">".,?! "</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">))</span> <span class="op">!=</span> NULL<span class="op">);</span></span>
<span id="cb1600-23"><a href="wchar.html#cb1600-23"></a>    <span class="op">}</span></span>
<span id="cb1600-24"><a href="wchar.html#cb1600-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1601"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1601-1"><a href="wchar.html#cb1601-1" aria-hidden="true" tabindex="-1"></a>Word: "Where"</span>
<span id="cb1601-2"><a href="wchar.html#cb1601-2" aria-hidden="true" tabindex="-1"></a>Word: "is"</span>
<span id="cb1601-3"><a href="wchar.html#cb1601-3" aria-hidden="true" tabindex="-1"></a>Word: "my"</span>
<span id="cb1601-4"><a href="wchar.html#cb1601-4" aria-hidden="true" tabindex="-1"></a>Word: "bacon"</span>
<span id="cb1601-5"><a href="wchar.html#cb1601-5" aria-hidden="true" tabindex="-1"></a>Word: "dude"</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-244">See Also</h3>
<p><a href="stringref.html#man-strtok"><code>strtok()</code></a></p>
<hr>
<h2 data-number="69.25" id="man-wcslen"><span class="header-section-number">69.25</span> <code>wcslen()</code></h2>
<p>Returns the length of a wide string</p>
<h3 class="unnumbered unlisted" id="synopsis-258">Synopsis</h3>
<div class="sourceCode" id="cb1602"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1602-1"><a href="wchar.html#cb1602-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1602-2"><a href="wchar.html#cb1602-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1602-3"><a href="wchar.html#cb1602-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcslen<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>s<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-258">Description</h3>
<p>This is the wide counterpart to <a href="#man-strlen"><code>strlen()</code></a>.</p>
<h3 class="unnumbered unlisted" id="return-value-256">Return Value</h3>
<p>Returns the number of wide characters before the wide NUL
terminator.</p>
<h3 class="unnumbered unlisted" id="example-260">Example</h3>
<div class="sourceCode" id="cb1603"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1603-1"><a href="wchar.html#cb1603-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1603-2"><a href="wchar.html#cb1603-2"></a></span>
<span id="cb1603-3"><a href="wchar.html#cb1603-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1603-4"><a href="wchar.html#cb1603-4"></a><span class="op">{</span></span>
<span id="cb1603-5"><a href="wchar.html#cb1603-5"></a>    <span class="dt">wchar_t</span> <span class="op">*</span>s <span class="op">=</span> L<span class="st">"Hello, world!"</span><span class="op">;</span> <span class="co">// 13 characters</span></span>
<span id="cb1603-6"><a href="wchar.html#cb1603-6"></a></span>
<span id="cb1603-7"><a href="wchar.html#cb1603-7"></a>    <span class="co">// prints "The string is 13 characters long.":</span></span>
<span id="cb1603-8"><a href="wchar.html#cb1603-8"></a></span>
<span id="cb1603-9"><a href="wchar.html#cb1603-9"></a>    wprintf<span class="op">(</span>L<span class="st">"The string is %zu characters long.</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcslen<span class="op">(</span>s<span class="op">));</span></span>
<span id="cb1603-10"><a href="wchar.html#cb1603-10"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-245">See Also</h3>
<p><a href="stringref.html#man-strlen"><code>strlen()</code></a></p>
<hr>
<h2 data-number="69.26" id="man-wcsftime"><span class="header-section-number">69.26</span> <code>wcsftime()</code></h2>
<p>Formatted date and time output</p>
<h3 class="unnumbered unlisted" id="synopsis-259">Synopsis</h3>
<div class="sourceCode" id="cb1604"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1604-1"><a href="wchar.html#cb1604-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1604-2"><a href="wchar.html#cb1604-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1604-3"><a href="wchar.html#cb1604-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1604-4"><a href="wchar.html#cb1604-4" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcsftime<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> maxsize<span class="op">,</span></span>
<span id="cb1604-5"><a href="wchar.html#cb1604-5" aria-hidden="true" tabindex="-1"></a>                <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span></span>
<span id="cb1604-6"><a href="wchar.html#cb1604-6" aria-hidden="true" tabindex="-1"></a>                <span class="dt">const</span> <span class="kw">struct</span> tm <span class="op">*</span> <span class="dt">restrict</span> timeptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-259">Description</h3>
<p>This is the wide equivalent to <a href="#man-strftime"><code>strftime()</code></a>. See that reference
page for details.</p>
<p><code>maxsize</code> here refers to the maximum number of wide
characters that can be in the result string.</p>
<h3 class="unnumbered unlisted" id="return-value-257">Return Value</h3>
<p>If successful, returns the number of wide characters written.</p>
<p>If not successful because the result couldn’t fit in the space
alloted, <code>0</code> is returned and the contents of the string could
be anything.</p>
<h3 class="unnumbered unlisted" id="example-261">Example</h3>
<div class="sourceCode" id="cb1605"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1605-1"><a href="wchar.html#cb1605-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1605-2"><a href="wchar.html#cb1605-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1605-3"><a href="wchar.html#cb1605-3"></a></span>
<span id="cb1605-4"><a href="wchar.html#cb1605-4"></a><span class="pp">#define BUFSIZE 128</span></span>
<span id="cb1605-5"><a href="wchar.html#cb1605-5"></a></span>
<span id="cb1605-6"><a href="wchar.html#cb1605-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1605-7"><a href="wchar.html#cb1605-7"></a><span class="op">{</span></span>
<span id="cb1605-8"><a href="wchar.html#cb1605-8"></a>    <span class="dt">wchar_t</span> s<span class="op">[</span>BUFSIZE<span class="op">];</span></span>
<span id="cb1605-9"><a href="wchar.html#cb1605-9"></a>    <span class="dt">time_t</span> now <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1605-10"><a href="wchar.html#cb1605-10"></a></span>
<span id="cb1605-11"><a href="wchar.html#cb1605-11"></a>    <span class="co">// %c: print date as per current locale</span></span>
<span id="cb1605-12"><a href="wchar.html#cb1605-12"></a>    wcsftime<span class="op">(</span>s<span class="op">,</span> BUFSIZE<span class="op">,</span> L<span class="st">"%c"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1605-13"><a href="wchar.html#cb1605-13"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>   <span class="co">// Sun Feb 28 22:29:00 2021</span></span>
<span id="cb1605-14"><a href="wchar.html#cb1605-14"></a></span>
<span id="cb1605-15"><a href="wchar.html#cb1605-15"></a>    <span class="co">// %A: full weekday name</span></span>
<span id="cb1605-16"><a href="wchar.html#cb1605-16"></a>    <span class="co">// %B: full month name</span></span>
<span id="cb1605-17"><a href="wchar.html#cb1605-17"></a>    <span class="co">// %d: day of the month</span></span>
<span id="cb1605-18"><a href="wchar.html#cb1605-18"></a>    wcsftime<span class="op">(</span>s<span class="op">,</span> BUFSIZE<span class="op">,</span> L<span class="st">"%A, %B %d"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1605-19"><a href="wchar.html#cb1605-19"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>   <span class="co">// Sunday, February 28</span></span>
<span id="cb1605-20"><a href="wchar.html#cb1605-20"></a></span>
<span id="cb1605-21"><a href="wchar.html#cb1605-21"></a>    <span class="co">// %I: hour (12 hour clock)</span></span>
<span id="cb1605-22"><a href="wchar.html#cb1605-22"></a>    <span class="co">// %M: minute</span></span>
<span id="cb1605-23"><a href="wchar.html#cb1605-23"></a>    <span class="co">// %S: second</span></span>
<span id="cb1605-24"><a href="wchar.html#cb1605-24"></a>    <span class="co">// %p: AM or PM</span></span>
<span id="cb1605-25"><a href="wchar.html#cb1605-25"></a>    wcsftime<span class="op">(</span>s<span class="op">,</span> BUFSIZE<span class="op">,</span> L<span class="st">"It's %I:%M:%S %p"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1605-26"><a href="wchar.html#cb1605-26"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>   <span class="co">// It's 10:29:00 PM</span></span>
<span id="cb1605-27"><a href="wchar.html#cb1605-27"></a></span>
<span id="cb1605-28"><a href="wchar.html#cb1605-28"></a>    <span class="co">// %F: ISO 8601 yyyy-mm-dd</span></span>
<span id="cb1605-29"><a href="wchar.html#cb1605-29"></a>    <span class="co">// %T: ISO 8601 hh:mm:ss</span></span>
<span id="cb1605-30"><a href="wchar.html#cb1605-30"></a>    <span class="co">// %z: ISO 8601 time zone offset</span></span>
<span id="cb1605-31"><a href="wchar.html#cb1605-31"></a>    wcsftime<span class="op">(</span>s<span class="op">,</span> BUFSIZE<span class="op">,</span> L<span class="st">"ISO 8601: %FT%T%z"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1605-32"><a href="wchar.html#cb1605-32"></a>    wprintf<span class="op">(</span>L<span class="st">"%ls</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>   <span class="co">// ISO 8601: 2021-02-28T22:29:00-0800</span></span>
<span id="cb1605-33"><a href="wchar.html#cb1605-33"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-246">See Also</h3>
<p><a href="time.html#man-strftime"><code>strftime()</code></a></p>
<hr>
<h2 data-number="69.27" id="man-btowc"><span class="header-section-number">69.27</span> <code>btowc()</code>
<code>wctob()</code></h2>
<p>Convert a single byte character to a wide character</p>
<h3 class="unnumbered unlisted" id="synopsis-260">Synopsis</h3>
<div class="sourceCode" id="cb1606"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1606-1"><a href="wchar.html#cb1606-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1606-2"><a href="wchar.html#cb1606-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1606-3"><a href="wchar.html#cb1606-3" aria-hidden="true" tabindex="-1"></a><span class="dt">wint_t</span> btowc<span class="op">(</span><span class="dt">int</span> c<span class="op">);</span></span>
<span id="cb1606-4"><a href="wchar.html#cb1606-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1606-5"><a href="wchar.html#cb1606-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> wctob<span class="op">(</span><span class="dt">wint_t</span> c<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-260">Description</h3>
<p>These functions convert between single byte characters and wide
characters, and vice-versa.</p>
<p>Even though <code>int</code>s are involved, don’t let this mislead
you; they’re effectively converted to <code>unsigned char</code>s
internally.</p>
<p>The characters in the basic character set are guaranteed to be a
single byte.</p>
<h3 class="unnumbered unlisted" id="return-value-258">Return Value</h3>
<p><code>btowc()</code> returns the single-byte character as a wide
character. Returns <code>WEOF</code> if <code>EOF</code> is passed in,
or if the byte doesn’t correspond to a valid wide character.</p>
<p><code>wctob()</code> returns the wide character as a single-byte
character. Returns <code>EOF</code> if <code>WEOF</code> is passed in,
or if the wide character doesn’t correspond to a value single-byte
character.</p>
<p>See <a href="stdlib.html#man-mbtowc"><code>mbtowc()</code></a> and <a href="#man-wctomb"><code>wctomb()</code></a> for multibyte to wide
character conversion.</p>
<h3 class="unnumbered unlisted" id="example-262">Example</h3>
<div class="sourceCode" id="cb1607"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1607-1"><a href="wchar.html#cb1607-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1607-2"><a href="wchar.html#cb1607-2"></a></span>
<span id="cb1607-3"><a href="wchar.html#cb1607-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1607-4"><a href="wchar.html#cb1607-4"></a><span class="op">{</span></span>
<span id="cb1607-5"><a href="wchar.html#cb1607-5"></a>    <span class="dt">wint_t</span> wc <span class="op">=</span> btowc<span class="op">(</span><span class="ch">'B'</span><span class="op">);</span>    <span class="co">// Convert single byte to wide char</span></span>
<span id="cb1607-6"><a href="wchar.html#cb1607-6"></a></span>
<span id="cb1607-7"><a href="wchar.html#cb1607-7"></a>    wprintf<span class="op">(</span>L<span class="st">"Wide character: %lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wc<span class="op">);</span></span>
<span id="cb1607-8"><a href="wchar.html#cb1607-8"></a></span>
<span id="cb1607-9"><a href="wchar.html#cb1607-9"></a>    <span class="dt">unsigned</span> <span class="dt">char</span> c <span class="op">=</span> wctob<span class="op">(</span>wc<span class="op">);</span>  <span class="co">// Convert back to single byte</span></span>
<span id="cb1607-10"><a href="wchar.html#cb1607-10"></a></span>
<span id="cb1607-11"><a href="wchar.html#cb1607-11"></a>    wprintf<span class="op">(</span>L<span class="st">"Single-byte character: %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> c<span class="op">);</span></span>
<span id="cb1607-12"><a href="wchar.html#cb1607-12"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1608"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1608-1"><a href="wchar.html#cb1608-1" aria-hidden="true" tabindex="-1"></a>Wide character: B</span>
<span id="cb1608-2"><a href="wchar.html#cb1608-2" aria-hidden="true" tabindex="-1"></a>Single-byte character: B</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-247">See Also</h3>
<p><a href="stdlib.html#man-mbtowc"><code>mbtowc()</code></a>, <a href="#man-wctomb"><code>wctomb()</code></a></p>
<hr>
<h2 data-number="69.28" id="man-mbsinit"><span class="header-section-number">69.28</span> <code>mbsinit()</code></h2>
<p>Test if an <code>mbstate_t</code> is in the initial conversion
state</p>
<h3 class="unnumbered unlisted" id="synopsis-261">Synopsis</h3>
<div class="sourceCode" id="cb1609"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1609-1"><a href="wchar.html#cb1609-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1609-2"><a href="wchar.html#cb1609-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1609-3"><a href="wchar.html#cb1609-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mbsinit<span class="op">(</span><span class="dt">const</span> mbstate_t <span class="op">*</span>ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-261">Description</h3>
<p>For a given conversion state in a <code>mbstate_t</code> variable,
this function determines if it’s in the initial conversion state.</p>
<h3 class="unnumbered unlisted" id="return-value-259">Return Value</h3>
<p>Returns non-zero if the value pointed to by <code>ps</code> is in the
initial conversion state, or if <code>ps</code> is
<code>NULL</code>.</p>
<p>Returns <code>0</code> if the value pointed to by <code>ps</code> is
<strong>not</strong> in the initial conversion state.</p>
<h3 class="unnumbered unlisted" id="example-263">Example</h3>
<p>For me, this example doesn’t do anything exciting, saying that the
<code>mbstate_t</code> variable is always in the initial state. Yay.</p>
<p>But if have a stateful encoding like 2022-JP, try messing around with
this to see if you can get into an intermediate state.</p>
<p>This program has a bit of code at the top that reports if your
locale’s encoding requires any state.</p>
<div class="sourceCode" id="cb1610"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1610-1"><a href="wchar.html#cb1610-1"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">   </span><span class="co">// For setlocale()</span></span>
<span id="cb1610-2"><a href="wchar.html#cb1610-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">   </span><span class="co">// For memset()</span></span>
<span id="cb1610-3"><a href="wchar.html#cb1610-3"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span><span class="pp">   </span><span class="co">// For mbtowc()</span></span>
<span id="cb1610-4"><a href="wchar.html#cb1610-4"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1610-5"><a href="wchar.html#cb1610-5"></a></span>
<span id="cb1610-6"><a href="wchar.html#cb1610-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1610-7"><a href="wchar.html#cb1610-7"></a><span class="op">{</span></span>
<span id="cb1610-8"><a href="wchar.html#cb1610-8"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1610-9"><a href="wchar.html#cb1610-9"></a>    <span class="dt">wchar_t</span> wc<span class="op">[</span><span class="dv">128</span><span class="op">];</span></span>
<span id="cb1610-10"><a href="wchar.html#cb1610-10"></a></span>
<span id="cb1610-11"><a href="wchar.html#cb1610-11"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1610-12"><a href="wchar.html#cb1610-12"></a></span>
<span id="cb1610-13"><a href="wchar.html#cb1610-13"></a>    <span class="dt">int</span> is_state_dependent <span class="op">=</span> mbtowc<span class="op">(</span>NULL<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb1610-14"><a href="wchar.html#cb1610-14"></a></span>
<span id="cb1610-15"><a href="wchar.html#cb1610-15"></a>    wprintf<span class="op">(</span>L<span class="st">"Is encoding state dependent? %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> is_state_dependent<span class="op">);</span></span>
<span id="cb1610-16"><a href="wchar.html#cb1610-16"></a></span>
<span id="cb1610-17"><a href="wchar.html#cb1610-17"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span>  <span class="co">// Set to initial state</span></span>
<span id="cb1610-18"><a href="wchar.html#cb1610-18"></a></span>
<span id="cb1610-19"><a href="wchar.html#cb1610-19"></a>    wprintf<span class="op">(</span>L<span class="st">"In initial conversion state? %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbsinit<span class="op">(&amp;</span>state<span class="op">));</span></span>
<span id="cb1610-20"><a href="wchar.html#cb1610-20"></a></span>
<span id="cb1610-21"><a href="wchar.html#cb1610-21"></a>    mbrtowc<span class="op">(</span>wc<span class="op">,</span> <span class="st">"B"</span><span class="op">,</span> <span class="dv">5</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1610-22"><a href="wchar.html#cb1610-22"></a></span>
<span id="cb1610-23"><a href="wchar.html#cb1610-23"></a>    wprintf<span class="op">(</span>L<span class="st">"In initial conversion state? %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbsinit<span class="op">(&amp;</span>state<span class="op">));</span></span>
<span id="cb1610-24"><a href="wchar.html#cb1610-24"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-248">See Also</h3>
<p><a href="stdlib.html#man-mbtowc"><code>mbtowc()</code></a>, <a href="#man-wctomb"><code>wctomb()</code></a>, <a href="#man-mbrtowc"><code>mbrtowc()</code></a>, <a href="#man-wcrtomb"><code>wcrtomb()</code></a></p>
<hr>
<h2 data-number="69.29" id="man-mbrlen"><span class="header-section-number">69.29</span> <code>mbrlen()</code></h2>
<p>Compute the number of bytes in a multibyte character, restartably</p>
<h3 class="unnumbered unlisted" id="synopsis-262">Synopsis</h3>
<div class="sourceCode" id="cb1611"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1611-1"><a href="wchar.html#cb1611-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1611-2"><a href="wchar.html#cb1611-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1611-3"><a href="wchar.html#cb1611-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> mbrlen<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">,</span> mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-262">Description</h3>
<p>This is the restartable version of <a href="#man-mblen"><code>mblen()</code></a>.</p>
<p>It inspects at most <code>n</code> bytes of the string <code>s</code>
to see how many bytes in this character.</p>
<p>The conversion state is stored in <code>ps</code>.</p>
<p>This function doesn’t have the functionality of <code>mblen()</code>
that allowed you to query if this character encoding was stateful and to
reset the internal state.</p>
<h3 class="unnumbered unlisted" id="return-value-260">Return Value</h3>
<p>Returns the number of bytes required for this multibyte
character.</p>
<p>Returns <code>(size_t)(-1)</code> if the data in <code>s</code> is
not a valid multibyte character.</p>
<p>Returns <code>(size_t)(-2)</code> if the data is <code>s</code> is a
valid but not complete multibyte character.</p>
<h3 class="unnumbered unlisted" id="example-264">Example</h3>
<p>If your character set doesn’t support the Euro symbol “€”, substitute
the Unicode escape sequence <code>\u20ac</code>, below.</p>
<div class="sourceCode" id="cb1612"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1612-1"><a href="wchar.html#cb1612-1"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">   </span><span class="co">// For setlocale()</span></span>
<span id="cb1612-2"><a href="wchar.html#cb1612-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">   </span><span class="co">// For memset()</span></span>
<span id="cb1612-3"><a href="wchar.html#cb1612-3"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1612-4"><a href="wchar.html#cb1612-4"></a></span>
<span id="cb1612-5"><a href="wchar.html#cb1612-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1612-6"><a href="wchar.html#cb1612-6"></a><span class="op">{</span></span>
<span id="cb1612-7"><a href="wchar.html#cb1612-7"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1612-8"><a href="wchar.html#cb1612-8"></a>    <span class="dt">int</span> len<span class="op">;</span></span>
<span id="cb1612-9"><a href="wchar.html#cb1612-9"></a></span>
<span id="cb1612-10"><a href="wchar.html#cb1612-10"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1612-11"><a href="wchar.html#cb1612-11"></a></span>
<span id="cb1612-12"><a href="wchar.html#cb1612-12"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span>  <span class="co">// Set to initial state</span></span>
<span id="cb1612-13"><a href="wchar.html#cb1612-13"></a></span>
<span id="cb1612-14"><a href="wchar.html#cb1612-14"></a>    len <span class="op">=</span> mbrlen<span class="op">(</span><span class="st">"B"</span><span class="op">,</span> <span class="dv">5</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1612-15"><a href="wchar.html#cb1612-15"></a></span>
<span id="cb1612-16"><a href="wchar.html#cb1612-16"></a>    wprintf<span class="op">(</span>L<span class="st">"Length of 'B' is %d byte(s)</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> len<span class="op">);</span></span>
<span id="cb1612-17"><a href="wchar.html#cb1612-17"></a></span>
<span id="cb1612-18"><a href="wchar.html#cb1612-18"></a>    len <span class="op">=</span> mbrlen<span class="op">(</span><span class="st">"€"</span><span class="op">,</span> <span class="dv">5</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1612-19"><a href="wchar.html#cb1612-19"></a></span>
<span id="cb1612-20"><a href="wchar.html#cb1612-20"></a>    wprintf<span class="op">(</span>L<span class="st">"Length of '€' is %d byte(s)</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> len<span class="op">);</span></span>
<span id="cb1612-21"><a href="wchar.html#cb1612-21"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1613"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1613-1"><a href="wchar.html#cb1613-1" aria-hidden="true" tabindex="-1"></a>Length of 'B' is 1 byte(s)</span>
<span id="cb1613-2"><a href="wchar.html#cb1613-2" aria-hidden="true" tabindex="-1"></a>Length of '€' is 3 byte(s)</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-249">See Also</h3>
<p><a href="stdlib.html#man-mblen"><code>mblen()</code></a></p>
<hr>
<h2 data-number="69.30" id="man-mbrtowc"><span class="header-section-number">69.30</span> <code>mbrtowc()</code></h2>
<p>Convert multibyte to wide characters restartably</p>
<h3 class="unnumbered unlisted" id="synopsis-263">Synopsis</h3>
<div class="sourceCode" id="cb1614"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1614-1"><a href="wchar.html#cb1614-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1614-2"><a href="wchar.html#cb1614-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1614-3"><a href="wchar.html#cb1614-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> mbrtowc<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> pwc<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span></span>
<span id="cb1614-4"><a href="wchar.html#cb1614-4" aria-hidden="true" tabindex="-1"></a>               <span class="dt">size_t</span> n<span class="op">,</span> mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-263">Description</h3>
<p>This is the restartable counterpart to <a href="#man-mbtowc"><code>mbtowc()</code></a>.</p>
<p>It converts individual characters from multibyte to wide, tracking
the conversion state in the variable pointed to by <code>ps</code>.</p>
<p>At most <code>n</code> bytes are inspected for conversion to a wide
character.</p>
<p>These two variants are identical and cause the state pointed to by
<code>ps</code> to be set to the initial conversion state:</p>
<div class="sourceCode" id="cb1615"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1615-1"><a href="wchar.html#cb1615-1" aria-hidden="true" tabindex="-1"></a>mbrtowc<span class="op">(</span>NULL<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1615-2"><a href="wchar.html#cb1615-2" aria-hidden="true" tabindex="-1"></a>mbrtowc<span class="op">(</span>NULL<span class="op">,</span> <span class="st">""</span><span class="op">,</span> <span class="dv">1</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span></code></pre></div>
<p>Also, if you’re just interested in the length in bytes of the
multibyte character, you can pass <code>NULL</code> for <code>pwc</code>
and nothing will be stored for the wide character:</p>
<div class="sourceCode" id="cb1616"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1616-1"><a href="wchar.html#cb1616-1" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> len <span class="op">=</span> mbrtowc<span class="op">(</span>NULL<span class="op">,</span> <span class="st">"€"</span><span class="op">,</span> <span class="dv">5</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span></code></pre></div>
<p>This function doesn’t have the functionality of <code>mbtowc()</code>
that allowed you to query if this character encoding was stateful and to
reset the internal state.</p>
<h3 class="unnumbered unlisted" id="return-value-261">Return Value</h3>
<p>On success, returns a positive number corresponding to the number of
bytes in the multibyte character.</p>
<p>Returns <code>0</code> if the character encoded is a wide NUL
character.</p>
<p>Returns <code>(size_t)(-1)</code> if the data in <code>s</code> is
not a valid multibyte character.</p>
<p>Returns <code>(size_t)(-2)</code> if the data is <code>s</code> is a
valid but not complete multibyte character.</p>
<h3 class="unnumbered unlisted" id="example-265">Example</h3>
<p>If your character set doesn’t support the Euro symbol “€”, substitute
the Unicode escape sequence <code>\u20ac</code>, below.</p>
<div class="sourceCode" id="cb1617"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1617-1"><a href="wchar.html#cb1617-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// For memset()</span></span>
<span id="cb1617-2"><a href="wchar.html#cb1617-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span><span class="pp">  </span><span class="co">// For mbtowc()</span></span>
<span id="cb1617-3"><a href="wchar.html#cb1617-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// For setlocale()</span></span>
<span id="cb1617-4"><a href="wchar.html#cb1617-4"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1617-5"><a href="wchar.html#cb1617-5"></a></span>
<span id="cb1617-6"><a href="wchar.html#cb1617-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1617-7"><a href="wchar.html#cb1617-7"></a><span class="op">{</span></span>
<span id="cb1617-8"><a href="wchar.html#cb1617-8"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1617-9"><a href="wchar.html#cb1617-9"></a></span>
<span id="cb1617-10"><a href="wchar.html#cb1617-10"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span></span>
<span id="cb1617-11"><a href="wchar.html#cb1617-11"></a></span>
<span id="cb1617-12"><a href="wchar.html#cb1617-12"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1617-13"><a href="wchar.html#cb1617-13"></a></span>
<span id="cb1617-14"><a href="wchar.html#cb1617-14"></a>    wprintf<span class="op">(</span>L<span class="st">"State dependency: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbtowc<span class="op">(</span>NULL<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span></span>
<span id="cb1617-15"><a href="wchar.html#cb1617-15"></a></span>
<span id="cb1617-16"><a href="wchar.html#cb1617-16"></a>    <span class="dt">wchar_t</span> wc<span class="op">;</span></span>
<span id="cb1617-17"><a href="wchar.html#cb1617-17"></a>    <span class="dt">int</span> bytes<span class="op">;</span></span>
<span id="cb1617-18"><a href="wchar.html#cb1617-18"></a></span>
<span id="cb1617-19"><a href="wchar.html#cb1617-19"></a>    bytes <span class="op">=</span> mbrtowc<span class="op">(&amp;</span>wc<span class="op">,</span> <span class="st">"€"</span><span class="op">,</span> <span class="dv">5</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1617-20"><a href="wchar.html#cb1617-20"></a></span>
<span id="cb1617-21"><a href="wchar.html#cb1617-21"></a>    wprintf<span class="op">(</span>L<span class="st">"L'%lc' takes %d bytes as multibyte char '€'</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wc<span class="op">,</span> bytes<span class="op">);</span></span>
<span id="cb1617-22"><a href="wchar.html#cb1617-22"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1618"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1618-1"><a href="wchar.html#cb1618-1" aria-hidden="true" tabindex="-1"></a>State dependency: 0</span>
<span id="cb1618-2"><a href="wchar.html#cb1618-2" aria-hidden="true" tabindex="-1"></a>L'€' takes 3 bytes as multibyte char '€'</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-250">See Also</h3>
<p><a href="stdlib.html#man-mbtowc"><code>mbtowc()</code></a>, <a href="#man-wcrtomb"><code>wcrtomb()</code></a></p>
<hr>
<h2 data-number="69.31" id="man-wcrtomb"><span class="header-section-number">69.31</span> <code>wcrtomb()</code></h2>
<p>Convert wide to multibyte characters restartably</p>
<h3 class="unnumbered unlisted" id="synopsis-264">Synopsis</h3>
<div class="sourceCode" id="cb1619"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1619-1"><a href="wchar.html#cb1619-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1619-2"><a href="wchar.html#cb1619-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1619-3"><a href="wchar.html#cb1619-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcrtomb<span class="op">(</span><span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">wchar_t</span> wc<span class="op">,</span> mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-264">Description</h3>
<p>This is the restartable counterpart to <a href="#man-wctomb"><code>wctomb()</code></a>.</p>
<p>It converts individual characters from wide to multibyte, tracking
the conversion state in the variable pointed to by <code>ps</code>.</p>
<p>The destination array <code>s</code> should be at least
<code>MB_CUR_MAX</code><a href="footnotes.html#fn285" class="footnote-ref" id="fnref285" role="doc-noteref"><sup>285</sup></a> bytes in size—you
won’t get anything bigger back from this function.</p>
<p>Note that the values in this result array won’t be
NUL-terminated.</p>
<p>If you pass a wide NUL character in, the result will contain any
bytes needed to restore the conversion state to its initial state
followed by a NUL character, and the state pointed to by <code>ps</code>
will be reset to its initial state:</p>
<div class="sourceCode" id="cb1620"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1620-1"><a href="wchar.html#cb1620-1" aria-hidden="true" tabindex="-1"></a><span class="co">// Reset state</span></span>
<span id="cb1620-2"><a href="wchar.html#cb1620-2" aria-hidden="true" tabindex="-1"></a>wcrtomb<span class="op">(</span>mb<span class="op">,</span> L<span class="ch">'\0'</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">)</span></span></code></pre></div>
<p>If you don’t care about the results (i.e.&nbsp;you’re just interested in
resetting the state or getting the return value), you can do this by
passing <code>NULL</code> for <code>s</code>:</p>
<div class="sourceCode" id="cb1621"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1621-1"><a href="wchar.html#cb1621-1" aria-hidden="true" tabindex="-1"></a>wcrtomb<span class="op">(</span>NULL<span class="op">,</span> L<span class="ch">'\0'</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span>                <span class="co">// Reset state</span></span>
<span id="cb1621-2"><a href="wchar.html#cb1621-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1621-3"><a href="wchar.html#cb1621-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> byte_count <span class="op">=</span> wctomb<span class="op">(</span>NULL<span class="op">,</span> <span class="st">"X"</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span>  <span class="co">// Count bytes in 'X'</span></span></code></pre></div>
<p>This function doesn’t have the functionality of <code>wctomb()</code>
that allowed you to query if this character encoding was stateful and to
reset the internal state.</p>
<h3 class="unnumbered unlisted" id="return-value-262">Return Value</h3>
<p>On success, returns the number of bytes needed to encode this wide
character in the current locale.</p>
<p>If the input is an invalid wide character, <code>errno</code> will be
set to <code>EILSEQ</code> and the function returns
<code>(size_t)(-1)</code>. If this happens, all bets are off for the
conversion state, so you might as well reset it.</p>
<h3 class="unnumbered unlisted" id="example-266">Example</h3>
<p>If your character set doesn’t support the Euro symbol “€”, substitute
the Unicode escape sequence <code>\u20ac</code>, below.</p>
<div class="sourceCode" id="cb1622"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1622-1"><a href="wchar.html#cb1622-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// For memset()</span></span>
<span id="cb1622-2"><a href="wchar.html#cb1622-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span><span class="pp">  </span><span class="co">// For mbtowc()</span></span>
<span id="cb1622-3"><a href="wchar.html#cb1622-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// For setlocale()</span></span>
<span id="cb1622-4"><a href="wchar.html#cb1622-4"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1622-5"><a href="wchar.html#cb1622-5"></a></span>
<span id="cb1622-6"><a href="wchar.html#cb1622-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1622-7"><a href="wchar.html#cb1622-7"></a><span class="op">{</span></span>
<span id="cb1622-8"><a href="wchar.html#cb1622-8"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1622-9"><a href="wchar.html#cb1622-9"></a></span>
<span id="cb1622-10"><a href="wchar.html#cb1622-10"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span></span>
<span id="cb1622-11"><a href="wchar.html#cb1622-11"></a></span>
<span id="cb1622-12"><a href="wchar.html#cb1622-12"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1622-13"><a href="wchar.html#cb1622-13"></a></span>
<span id="cb1622-14"><a href="wchar.html#cb1622-14"></a>    wprintf<span class="op">(</span>L<span class="st">"State dependency: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbtowc<span class="op">(</span>NULL<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">));</span></span>
<span id="cb1622-15"><a href="wchar.html#cb1622-15"></a></span>
<span id="cb1622-16"><a href="wchar.html#cb1622-16"></a>    <span class="dt">char</span> mb<span class="op">[</span><span class="dv">10</span><span class="op">]</span> <span class="op">=</span> <span class="op">{</span><span class="dv">0</span><span class="op">};</span></span>
<span id="cb1622-17"><a href="wchar.html#cb1622-17"></a>    <span class="dt">int</span> bytes <span class="op">=</span> wcrtomb<span class="op">(</span>mb<span class="op">,</span> L'€'<span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1622-18"><a href="wchar.html#cb1622-18"></a></span>
<span id="cb1622-19"><a href="wchar.html#cb1622-19"></a>    wprintf<span class="op">(</span>L<span class="st">"L'€' takes %d bytes as multibyte char '%s'</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> bytes<span class="op">,</span> mb<span class="op">);</span></span>
<span id="cb1622-20"><a href="wchar.html#cb1622-20"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-251">See Also</h3>
<p><a href="wchar.html#man-mbrtowc"><code>mbrtowc()</code></a>, <a href="#man-wctomb"><code>wctomb()</code></a>, <a href="#errno"><code>errno</code></a></p>
<hr>
<h2 data-number="69.32" id="man-mbsrtowcs"><span class="header-section-number">69.32</span> <code>mbsrtowcs()</code></h2>
<p>Convert a multibyte string to a wide character string restartably</p>
<h3 class="unnumbered unlisted" id="synopsis-265">Synopsis</h3>
<div class="sourceCode" id="cb1623"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1623-1"><a href="wchar.html#cb1623-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1623-2"><a href="wchar.html#cb1623-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1623-3"><a href="wchar.html#cb1623-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> mbsrtowcs<span class="op">(</span><span class="dt">wchar_t</span> <span class="op">*</span> <span class="dt">restrict</span> dst<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">**</span> <span class="dt">restrict</span> src<span class="op">,</span></span>
<span id="cb1623-4"><a href="wchar.html#cb1623-4" aria-hidden="true" tabindex="-1"></a>                 <span class="dt">size_t</span> len<span class="op">,</span> mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-265">Description</h3>
<p>This is the restartable version of <a href="#man-mbstowcs"><code>mbstowcs()</code></a>.</p>
<p>It converts a multibyte string to a wide character string.</p>
<p>The result is put in the buffer pointed to by <code>dst</code>, and
the pointer <code>src</code> is updated to indicate how much of the
string was consumed (unless <code>dst</code> is <code>NULL</code>).</p>
<p>At most <code>len</code> wide characters will be stored.</p>
<p>This also takes a pointer to its own <code>mbstate_t</code> variable
in <code>ps</code> for holding the conversion state.</p>
<p>You can set <code>dst</code> to <code>NULL</code> if you only care
about the return value. This could be useful for getting the number of
characters in a multibyte string.</p>
<p>In the normal case, the <code>src</code> string will be consumed up
to the NUL character, and the results will be stored in the
<code>dst</code> buffer, including the wide NUL character. In this case,
the pointer pointed to by <code>src</code> will be set to
<code>NULL</code>. And the conversion state will be set to the initial
conversion state.</p>
<p>If things go wrong because the source string isn’t a valid sequence
of characters, conversion will stop and the pointer pointed to by
<code>src</code> will be set to the address just after the last
successfully-translated multibyte character.</p>
<h3 class="unnumbered unlisted" id="return-value-263">Return Value</h3>
<p>If successful, returns the number of characters converted, not
including any NUL terminator.</p>
<p>If the multibyte sequence is invalid, the function returns
<code>(size_t)(-1)</code> and <code>errno</code> is set to
<code>EILSEQ</code>.</p>
<h3 class="unnumbered unlisted" id="example-267">Example</h3>
<p>Here we’ll convert the string “€5 ± π” into a wide character
string:</p>
<div class="sourceCode" id="cb1624"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1624-1"><a href="wchar.html#cb1624-1"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// For setlocale()</span></span>
<span id="cb1624-2"><a href="wchar.html#cb1624-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// For memset()</span></span>
<span id="cb1624-3"><a href="wchar.html#cb1624-3"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1624-4"><a href="wchar.html#cb1624-4"></a></span>
<span id="cb1624-5"><a href="wchar.html#cb1624-5"></a><span class="pp">#define WIDE_STR_SIZE 10</span></span>
<span id="cb1624-6"><a href="wchar.html#cb1624-6"></a></span>
<span id="cb1624-7"><a href="wchar.html#cb1624-7"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1624-8"><a href="wchar.html#cb1624-8"></a><span class="op">{</span></span>
<span id="cb1624-9"><a href="wchar.html#cb1624-9"></a>    <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>mbs <span class="op">=</span> <span class="st">"€5 ± π"</span><span class="op">;</span>  <span class="co">// That's the exact price range</span></span>
<span id="cb1624-10"><a href="wchar.html#cb1624-10"></a></span>
<span id="cb1624-11"><a href="wchar.html#cb1624-11"></a>    <span class="dt">wchar_t</span> wcs<span class="op">[</span>WIDE_STR_SIZE<span class="op">];</span></span>
<span id="cb1624-12"><a href="wchar.html#cb1624-12"></a></span>
<span id="cb1624-13"><a href="wchar.html#cb1624-13"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1624-14"><a href="wchar.html#cb1624-14"></a>    </span>
<span id="cb1624-15"><a href="wchar.html#cb1624-15"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1624-16"><a href="wchar.html#cb1624-16"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span></span>
<span id="cb1624-17"><a href="wchar.html#cb1624-17"></a></span>
<span id="cb1624-18"><a href="wchar.html#cb1624-18"></a>    <span class="dt">size_t</span> count <span class="op">=</span> mbsrtowcs<span class="op">(</span>wcs<span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">,</span> WIDE_STR_SIZE<span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1624-19"><a href="wchar.html#cb1624-19"></a></span>
<span id="cb1624-20"><a href="wchar.html#cb1624-20"></a>    wprintf<span class="op">(</span>L<span class="st">"Wide string L</span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"</span><span class="st"> is %d characters</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wcs<span class="op">,</span> count<span class="op">);</span></span>
<span id="cb1624-21"><a href="wchar.html#cb1624-21"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1625"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1625-1"><a href="wchar.html#cb1625-1" aria-hidden="true" tabindex="-1"></a>Wide string L"€5 ± π" is 6 characters</span></code></pre></div>
<p>Here’s another example of using <code>mbsrtowcs()</code> to get the
length in characters of a multibyte string even if the string is full of
multibyte characters. This is in contrast to <code>strlen()</code>,
which returns the total number of bytes in the string.</p>
<div class="sourceCode" id="cb1626"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1626-1"><a href="wchar.html#cb1626-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span><span class="pp">   </span><span class="co">// For printf()</span></span>
<span id="cb1626-2"><a href="wchar.html#cb1626-2"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// For setlocale()</span></span>
<span id="cb1626-3"><a href="wchar.html#cb1626-3"></a></span>
<span id="cb1626-4"><a href="wchar.html#cb1626-4"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// For memset()</span></span>
<span id="cb1626-5"><a href="wchar.html#cb1626-5"></a><span class="pp">#include </span><span class="im">&lt;stdint.h&gt;</span><span class="pp">  </span><span class="co">// For SIZE_MAX</span></span>
<span id="cb1626-6"><a href="wchar.html#cb1626-6"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1626-7"><a href="wchar.html#cb1626-7"></a></span>
<span id="cb1626-8"><a href="wchar.html#cb1626-8"></a><span class="dt">size_t</span> mbstrlen<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>mbs<span class="op">)</span></span>
<span id="cb1626-9"><a href="wchar.html#cb1626-9"></a><span class="op">{</span></span>
<span id="cb1626-10"><a href="wchar.html#cb1626-10"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1626-11"><a href="wchar.html#cb1626-11"></a></span>
<span id="cb1626-12"><a href="wchar.html#cb1626-12"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span></span>
<span id="cb1626-13"><a href="wchar.html#cb1626-13"></a></span>
<span id="cb1626-14"><a href="wchar.html#cb1626-14"></a>    <span class="cf">return</span> mbsrtowcs<span class="op">(</span>NULL<span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">,</span> SIZE_MAX<span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1626-15"><a href="wchar.html#cb1626-15"></a><span class="op">}</span></span>
<span id="cb1626-16"><a href="wchar.html#cb1626-16"></a></span>
<span id="cb1626-17"><a href="wchar.html#cb1626-17"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1626-18"><a href="wchar.html#cb1626-18"></a><span class="op">{</span></span>
<span id="cb1626-19"><a href="wchar.html#cb1626-19"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1626-20"><a href="wchar.html#cb1626-20"></a>    </span>
<span id="cb1626-21"><a href="wchar.html#cb1626-21"></a>    <span class="dt">char</span> <span class="op">*</span>mbs <span class="op">=</span> <span class="st">"€5 ± π"</span><span class="op">;</span>  <span class="co">// That's the exact price range</span></span>
<span id="cb1626-22"><a href="wchar.html#cb1626-22"></a></span>
<span id="cb1626-23"><a href="wchar.html#cb1626-23"></a>    printf<span class="op">(</span><span class="st">"</span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"</span><span class="st"> is %zu characters...</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbs<span class="op">,</span> mbstrlen<span class="op">(</span>mbs<span class="op">));</span> </span>
<span id="cb1626-24"><a href="wchar.html#cb1626-24"></a>    printf<span class="op">(</span><span class="st">"but it's %zu bytes!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strlen<span class="op">(</span>mbs<span class="op">));</span></span>
<span id="cb1626-25"><a href="wchar.html#cb1626-25"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1627"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1627-1"><a href="wchar.html#cb1627-1" aria-hidden="true" tabindex="-1"></a>"€5 ± π" is 6 characters...</span>
<span id="cb1627-2"><a href="wchar.html#cb1627-2" aria-hidden="true" tabindex="-1"></a>but it's 10 bytes!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-252">See Also</h3>
<p><a href="wchar.html#man-mbrtowc"><code>mbrtowc()</code></a>, <a href="#man-mbstowcs"><code>mbstowcs()</code></a>, <a href="#man-wcsrtombs"><code>wcsrtombs()</code></a>, <a href="#man-strlen"><code>strlen()</code></a>, <a href="#errno"><code>errno</code></a></p>
<hr>
<h2 data-number="69.33" id="man-wcsrtombs"><span class="header-section-number">69.33</span> <code>wcsrtombs()</code></h2>
<p>Convert a wide character string to a multibyte string restartably</p>
<h3 class="unnumbered unlisted" id="synopsis-266">Synopsis</h3>
<div class="sourceCode" id="cb1628"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1628-1"><a href="wchar.html#cb1628-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1628-2"><a href="wchar.html#cb1628-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1628-3"><a href="wchar.html#cb1628-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> wcsrtombs<span class="op">(</span><span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> dst<span class="op">,</span> <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">**</span> <span class="dt">restrict</span> src<span class="op">,</span></span>
<span id="cb1628-4"><a href="wchar.html#cb1628-4" aria-hidden="true" tabindex="-1"></a>                 <span class="dt">size_t</span> len<span class="op">,</span> mbstate_t <span class="op">*</span> <span class="dt">restrict</span> ps<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-266">Description</h3>
<p>If you have a wide character string, you can convert it to a
multibyte character string in the current locale using this
function.</p>
<p>At most <code>len</code> bytes of data will be stored in the buffer
pointed to by <code>dst</code>. Conversion will stop just after the NUL
terminator is copied, or <code>len</code> bytes get copied, or some
other error occurs.</p>
<p>If <code>dst</code> is a <code>NULL</code> pointer, no result is
stored. You might do this if you’re just interested in the return value
(nominally the number of bytes this would use in a multibyte string, not
including the NUL terminator).</p>
<p>If <code>dst</code> is not a <code>NULL</code> pointer, the pointer
pointed to by <code>src</code> will get modified to indicate how much of
the data was copied. If it contains <code>NULL</code> at the end, it
means everything went well. In this case, the state <code>ps</code> will
be set to the initial conversion state.</p>
<p>If <code>len</code> was reached or an error occurred, it’ll point one
address past <code>dst+len</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-264">Return Value</h3>
<p>If everything goes well, returns the number of bytes needed for the
multibyte string, not counting the NUL terminator.</p>
<p>If any character in the string doesn’t correspond to a valid
multibyte character in the currently locale, it returns
<code>(size_t)(-1)</code> and <code>EILSEQ</code> is stored in
<code>errno</code>.</p>
<h3 class="unnumbered unlisted" id="example-268">Example</h3>
<p>Here we’ll convert the wide string “€5 ± π” into a multibyte
character string:</p>
<div class="sourceCode" id="cb1629"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1629-1"><a href="wchar.html#cb1629-1"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// For setlocale()</span></span>
<span id="cb1629-2"><a href="wchar.html#cb1629-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// For memset()</span></span>
<span id="cb1629-3"><a href="wchar.html#cb1629-3"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1629-4"><a href="wchar.html#cb1629-4"></a></span>
<span id="cb1629-5"><a href="wchar.html#cb1629-5"></a><span class="pp">#define MB_STR_SIZE 20</span></span>
<span id="cb1629-6"><a href="wchar.html#cb1629-6"></a></span>
<span id="cb1629-7"><a href="wchar.html#cb1629-7"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1629-8"><a href="wchar.html#cb1629-8"></a><span class="op">{</span></span>
<span id="cb1629-9"><a href="wchar.html#cb1629-9"></a>    <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>wcs <span class="op">=</span> L<span class="st">"€5 ± π"</span><span class="op">;</span>  <span class="co">// That's the exact price range</span></span>
<span id="cb1629-10"><a href="wchar.html#cb1629-10"></a></span>
<span id="cb1629-11"><a href="wchar.html#cb1629-11"></a>    <span class="dt">char</span> mbs<span class="op">[</span>MB_STR_SIZE<span class="op">];</span></span>
<span id="cb1629-12"><a href="wchar.html#cb1629-12"></a></span>
<span id="cb1629-13"><a href="wchar.html#cb1629-13"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1629-14"><a href="wchar.html#cb1629-14"></a>    </span>
<span id="cb1629-15"><a href="wchar.html#cb1629-15"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1629-16"><a href="wchar.html#cb1629-16"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span></span>
<span id="cb1629-17"><a href="wchar.html#cb1629-17"></a></span>
<span id="cb1629-18"><a href="wchar.html#cb1629-18"></a>    <span class="dt">size_t</span> count <span class="op">=</span> wcsrtombs<span class="op">(</span>mbs<span class="op">,</span> <span class="op">&amp;</span>wcs<span class="op">,</span> MB_STR_SIZE<span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1629-19"><a href="wchar.html#cb1629-19"></a></span>
<span id="cb1629-20"><a href="wchar.html#cb1629-20"></a>    wprintf<span class="op">(</span>L<span class="st">"Multibyte string </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"</span><span class="st"> is %d bytes</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mbs<span class="op">,</span> count<span class="op">);</span></span>
<span id="cb1629-21"><a href="wchar.html#cb1629-21"></a><span class="op">}</span></span></code></pre></div>
<p>Here’s another example helper function that <code>malloc()</code>s
just enough memory to hold the converted string, then returns the
result. (Which must later be freed, of course, to prevent leaking
memory.)</p>
<div class="sourceCode" id="cb1630"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1630-1"><a href="wchar.html#cb1630-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span><span class="pp">  </span><span class="co">// For malloc()</span></span>
<span id="cb1630-2"><a href="wchar.html#cb1630-2"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span><span class="pp">  </span><span class="co">// For setlocale()</span></span>
<span id="cb1630-3"><a href="wchar.html#cb1630-3"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span><span class="pp">  </span><span class="co">// For memset()</span></span>
<span id="cb1630-4"><a href="wchar.html#cb1630-4"></a><span class="pp">#include </span><span class="im">&lt;stdint.h&gt;</span><span class="pp">  </span><span class="co">// For SIZE_MAX</span></span>
<span id="cb1630-5"><a href="wchar.html#cb1630-5"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb1630-6"><a href="wchar.html#cb1630-6"></a></span>
<span id="cb1630-7"><a href="wchar.html#cb1630-7"></a><span class="dt">char</span> <span class="op">*</span>get_mb_string<span class="op">(</span><span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>wcs<span class="op">)</span></span>
<span id="cb1630-8"><a href="wchar.html#cb1630-8"></a><span class="op">{</span></span>
<span id="cb1630-9"><a href="wchar.html#cb1630-9"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1630-10"><a href="wchar.html#cb1630-10"></a></span>
<span id="cb1630-11"><a href="wchar.html#cb1630-11"></a>    mbstate_t state<span class="op">;</span></span>
<span id="cb1630-12"><a href="wchar.html#cb1630-12"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span></span>
<span id="cb1630-13"><a href="wchar.html#cb1630-13"></a></span>
<span id="cb1630-14"><a href="wchar.html#cb1630-14"></a>    <span class="co">// Need a copy of this because wcsrtombs changes it</span></span>
<span id="cb1630-15"><a href="wchar.html#cb1630-15"></a>    <span class="dt">const</span> <span class="dt">wchar_t</span> <span class="op">*</span>p <span class="op">=</span> wcs<span class="op">;</span></span>
<span id="cb1630-16"><a href="wchar.html#cb1630-16"></a></span>
<span id="cb1630-17"><a href="wchar.html#cb1630-17"></a>    <span class="co">// Compute the number of bytes needed to hold the result</span></span>
<span id="cb1630-18"><a href="wchar.html#cb1630-18"></a>    <span class="dt">size_t</span> bytes_needed <span class="op">=</span> wcsrtombs<span class="op">(</span>NULL<span class="op">,</span> <span class="op">&amp;</span>p<span class="op">,</span> SIZE_MAX<span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1630-19"><a href="wchar.html#cb1630-19"></a></span>
<span id="cb1630-20"><a href="wchar.html#cb1630-20"></a>    <span class="co">// If we didn't get a good full conversion, forget it</span></span>
<span id="cb1630-21"><a href="wchar.html#cb1630-21"></a>    <span class="cf">if</span> <span class="op">(</span>bytes_needed <span class="op">==</span> <span class="op">(</span><span class="dt">size_t</span><span class="op">)(-</span><span class="dv">1</span><span class="op">))</span></span>
<span id="cb1630-22"><a href="wchar.html#cb1630-22"></a>        <span class="cf">return</span> NULL<span class="op">;</span></span>
<span id="cb1630-23"><a href="wchar.html#cb1630-23"></a></span>
<span id="cb1630-24"><a href="wchar.html#cb1630-24"></a>    <span class="co">// Allocate space for result</span></span>
<span id="cb1630-25"><a href="wchar.html#cb1630-25"></a>    <span class="dt">char</span> <span class="op">*</span>mbs <span class="op">=</span> malloc<span class="op">(</span>bytes_needed <span class="op">+</span> <span class="dv">1</span><span class="op">);</span>  <span class="co">// +1 for NUL terminator</span></span>
<span id="cb1630-26"><a href="wchar.html#cb1630-26"></a></span>
<span id="cb1630-27"><a href="wchar.html#cb1630-27"></a>    <span class="co">// Set conversion state to initial state</span></span>
<span id="cb1630-28"><a href="wchar.html#cb1630-28"></a>    memset<span class="op">(&amp;</span>state<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> state<span class="op">);</span></span>
<span id="cb1630-29"><a href="wchar.html#cb1630-29"></a></span>
<span id="cb1630-30"><a href="wchar.html#cb1630-30"></a>    <span class="co">// Convert and store result</span></span>
<span id="cb1630-31"><a href="wchar.html#cb1630-31"></a>    wcsrtombs<span class="op">(</span>mbs<span class="op">,</span> <span class="op">&amp;</span>wcs<span class="op">,</span> bytes_needed <span class="op">+</span> <span class="dv">1</span><span class="op">,</span> <span class="op">&amp;</span>state<span class="op">);</span></span>
<span id="cb1630-32"><a href="wchar.html#cb1630-32"></a></span>
<span id="cb1630-33"><a href="wchar.html#cb1630-33"></a>    <span class="co">// Make sure things went well</span></span>
<span id="cb1630-34"><a href="wchar.html#cb1630-34"></a>    <span class="cf">if</span> <span class="op">(</span>wcs <span class="op">!=</span> NULL<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1630-35"><a href="wchar.html#cb1630-35"></a>        free<span class="op">(</span>mbs<span class="op">);</span></span>
<span id="cb1630-36"><a href="wchar.html#cb1630-36"></a>        <span class="cf">return</span> NULL<span class="op">;</span></span>
<span id="cb1630-37"><a href="wchar.html#cb1630-37"></a>    <span class="op">}</span></span>
<span id="cb1630-38"><a href="wchar.html#cb1630-38"></a></span>
<span id="cb1630-39"><a href="wchar.html#cb1630-39"></a>    <span class="co">// Success!</span></span>
<span id="cb1630-40"><a href="wchar.html#cb1630-40"></a>    <span class="cf">return</span> mbs<span class="op">;</span></span>
<span id="cb1630-41"><a href="wchar.html#cb1630-41"></a><span class="op">}</span></span>
<span id="cb1630-42"><a href="wchar.html#cb1630-42"></a></span>
<span id="cb1630-43"><a href="wchar.html#cb1630-43"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1630-44"><a href="wchar.html#cb1630-44"></a><span class="op">{</span></span>
<span id="cb1630-45"><a href="wchar.html#cb1630-45"></a>    <span class="dt">char</span> <span class="op">*</span>mbs <span class="op">=</span> get_mb_string<span class="op">(</span>L<span class="st">"€5 ± π"</span><span class="op">);</span></span>
<span id="cb1630-46"><a href="wchar.html#cb1630-46"></a></span>
<span id="cb1630-47"><a href="wchar.html#cb1630-47"></a>    wprintf<span class="op">(</span>L<span class="st">"Multibyte result: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> mbs<span class="op">);</span></span>
<span id="cb1630-48"><a href="wchar.html#cb1630-48"></a></span>
<span id="cb1630-49"><a href="wchar.html#cb1630-49"></a>    free<span class="op">(</span>mbs<span class="op">);</span></span>
<span id="cb1630-50"><a href="wchar.html#cb1630-50"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-253">See Also</h3>
<p><a href="wchar.html#man-wcrtomb"><code>wcrtomb()</code></a>, <a href="#man-wcstombs"><code>wcstombs()</code></a>, <a href="#man-mbsrtowcs"><code>mbsrtowcs()</code></a>, <a href="#errno"><code>errno</code></a></p>




</body>