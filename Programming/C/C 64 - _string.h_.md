<body>

<hr>
<h1 data-number="64" id="stringref"><span class="header-section-number">64</span> <code>&lt;string.h&gt;</code>
String Manipulation</h1>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="stringref.html#man-strchr"><code>memchr()</code></a></td>
<td>Find the first occurrence of a character in memory.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strcmp"><code>memcmp()</code></a></td>
<td>Compare two regions of memory.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-memcpy"><code>memcpy()</code></a></td>
<td>Copy a region of memory to another.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-memcpy"><code>memmove()</code></a></td>
<td>Move a (potentially overlapping) region of memory.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-memset"><code>memset()</code></a></td>
<td>Set a region of memory to a value.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strcat"><code>strcat()</code></a></td>
<td>Concatenate (join) two strings together.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strchr"><code>strchr()</code></a></td>
<td>Find the first occurrence of a character in a string.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strcmp"><code>strcmp()</code></a></td>
<td>Compare two strings.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strcoll"><code>strcoll()</code></a></td>
<td>Compare two strings accounting for locale.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strcpy"><code>strcpy()</code></a></td>
<td>Copy a string.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strspn"><code>strcspn()</code></a></td>
<td>Find length of a string not consisting of a set of characters.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strerror"><code>strerror()</code></a></td>
<td>Return a human-readable error message for a given code.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strlen"><code>strlen()</code></a></td>
<td>Return the length of a string.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strcat"><code>strncat()</code></a></td>
<td>Concatenate (join) two strings, length-limited.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strcmp"><code>strncmp()</code></a></td>
<td>Compare two strings, length-limited.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strcpy"><code>strncpy()</code></a></td>
<td>Copy two strings, length-limited.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strpbrk"><code>strpbrk()</code></a></td>
<td>Search a string for one of a set of character.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strchr"><code>strrchr()</code></a></td>
<td>Find the last occurrence of a character in a string.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strspn"><code>strspn()</code></a></td>
<td>Find length of a string consisting of a set of characters.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strstr"><code>strstr()</code></a></td>
<td>Find a substring in a string.</td>
</tr>
<tr class="odd">
<td><a href="stringref.html#man-strtok"><code>strtok()</code></a></td>
<td>Tokenize a string.</td>
</tr>
<tr class="even">
<td><a href="stringref.html#man-strxfrm"><code>strxfrm()</code></a></td>
<td>Prepare a string for comparison as if by
<code>strcoll()</code>.</td>
</tr>
</tbody>
</table>
<p>As has been mentioned earlier in the guide, a string in C is a
sequence of bytes in memory, terminated by a NUL character
(‘<code>\0</code>’). The NUL at the end is important, since it lets all
these string functions (and <code>printf()</code> and
<code>puts()</code> and everything else that deals with a string) know
where the end of the string actually is.</p>
<p>Fortunately, when you operate on a string using one of these many
functions available to you, they add the NUL terminator on for you, so
you actually rarely have to keep track of it yourself. (Sometimes you
do, especially if you’re building a string from scratch a character at a
time or something.)</p>
<p>In this section you’ll find functions for pulling substrings out of
strings, concatenating strings together, getting the length of a string,
and so forth and so on.</p>
<hr>
<h2 data-number="64.1" id="man-memcpy"><span class="header-section-number">64.1</span> <code>memcpy()</code>,
<code>memmove()</code></h2>
<p>Copy bytes of memory from one location to another</p>
<h3 class="unnumbered unlisted" id="synopsis-184">Synopsis</h3>
<div class="sourceCode" id="cb1375"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1375-1"><a href="stringref.html#cb1375-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1375-2"><a href="stringref.html#cb1375-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1375-3"><a href="stringref.html#cb1375-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>memcpy<span class="op">(</span><span class="dt">void</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span>
<span id="cb1375-4"><a href="stringref.html#cb1375-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1375-5"><a href="stringref.html#cb1375-5" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>memmove<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-184">Description</h3>
<p>These functions copy memory—as many bytes as you want! From source to
destination!</p>
<p>The main difference between the two is that <code>memcpy()</code>
cannot safely copy overlapping memory regions, whereas
<code>memmove()</code> can.</p>
<p>On the one hand, I’m not sure why you’d want to ever use
<code>memcpy()</code> instead of <code>memmove()</code>, but I’ll bet
it’s possibly more performant.</p>
<p>The parameters are in a particular order: destination first, then
source. I remember this order because it behaves like an
“<code>=</code>” assignment: the destination is on the left.</p>
<h3 class="unnumbered unlisted" id="return-value-182">Return Value</h3>
<p>Both functions return whatever you passed in for parameter
<code>s1</code> for your convenience.</p>
<h3 class="unnumbered unlisted" id="example-185">Example</h3>
<div class="sourceCode" id="cb1376"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1376-1"><a href="stringref.html#cb1376-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1376-2"><a href="stringref.html#cb1376-2"></a></span>
<span id="cb1376-3"><a href="stringref.html#cb1376-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1376-4"><a href="stringref.html#cb1376-4"></a><span class="op">{</span></span>
<span id="cb1376-5"><a href="stringref.html#cb1376-5"></a>    <span class="dt">char</span> s<span class="op">[</span><span class="dv">100</span><span class="op">]</span> <span class="op">=</span> <span class="st">"Goats"</span><span class="op">;</span></span>
<span id="cb1376-6"><a href="stringref.html#cb1376-6"></a>    <span class="dt">char</span> t<span class="op">[</span><span class="dv">100</span><span class="op">];</span></span>
<span id="cb1376-7"><a href="stringref.html#cb1376-7"></a></span>
<span id="cb1376-8"><a href="stringref.html#cb1376-8"></a>    memcpy<span class="op">(</span>t<span class="op">,</span> s<span class="op">,</span> <span class="dv">6</span><span class="op">);</span>       <span class="co">// Copy non-overlapping memory</span></span>
<span id="cb1376-9"><a href="stringref.html#cb1376-9"></a></span>
<span id="cb1376-10"><a href="stringref.html#cb1376-10"></a>    memmove<span class="op">(</span>s <span class="op">+</span> <span class="dv">2</span><span class="op">,</span> s<span class="op">,</span> <span class="dv">6</span><span class="op">);</span>  <span class="co">// Copy overlapping memory</span></span>
<span id="cb1376-11"><a href="stringref.html#cb1376-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-174">See Also</h3>
<p><a href="stringref.html#man-strcpy"><code>strcpy()</code></a>, <a href="#man-strcpy"><code>strncpy()</code></a></p>
<hr>
<h2 data-number="64.2" id="man-strcpy"><span class="header-section-number">64.2</span> <code>strcpy()</code>,
<code>strncpy()</code></h2>
<p>Copy a string</p>
<h3 class="unnumbered unlisted" id="synopsis-185">Synopsis</h3>
<div class="sourceCode" id="cb1377"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1377-1"><a href="stringref.html#cb1377-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1377-2"><a href="stringref.html#cb1377-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1377-3"><a href="stringref.html#cb1377-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strcpy<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>dest<span class="op">,</span> <span class="dt">char</span> <span class="op">*</span>src<span class="op">);</span></span>
<span id="cb1377-4"><a href="stringref.html#cb1377-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1377-5"><a href="stringref.html#cb1377-5" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strncpy<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>dest<span class="op">,</span> <span class="dt">char</span> <span class="op">*</span>src<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-185">Description</h3>
<p>These functions copy a string from one address to another, stopping
at the NUL terminator on the <code>src</code>string.</p>
<p><code>strncpy()</code> is just like <code>strcpy()</code>, except
only the first <code>n</code> characters are actually copied. Beware
that if you hit the limit, <code>n</code> before you get a NUL
terminator on the <code>src</code> string, your <code>dest</code> string
won’t be NUL-terminated. Beware! BEWARE!</p>
<p>(If the <code>src</code> string has fewer than <code>n</code>
characters, it works just like <code>strcpy()</code>.)</p>
<p>You can terminate the string yourself by sticking the
<code>'\0'</code> in there yourself:</p>
<div class="sourceCode" id="cb1378"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1378-1"><a href="stringref.html#cb1378-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> s<span class="op">[</span><span class="dv">10</span><span class="op">];</span></span>
<span id="cb1378-2"><a href="stringref.html#cb1378-2" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> foo <span class="op">=</span> <span class="st">"My hovercraft is full of eels."</span><span class="op">;</span> <span class="co">// more than 10 chars</span></span>
<span id="cb1378-3"><a href="stringref.html#cb1378-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1378-4"><a href="stringref.html#cb1378-4" aria-hidden="true" tabindex="-1"></a>strncpy<span class="op">(</span>s<span class="op">,</span> foo<span class="op">,</span> <span class="dv">9</span><span class="op">);</span> <span class="co">// only copy 9 chars into positions 0-8</span></span>
<span id="cb1378-5"><a href="stringref.html#cb1378-5" aria-hidden="true" tabindex="-1"></a>s<span class="op">[</span><span class="dv">9</span><span class="op">]</span> <span class="op">=</span> <span class="ch">'\0'</span><span class="op">;</span>        <span class="co">// position 9 gets the terminator</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-183">Return Value</h3>
<p>Both functions return <code>dest</code> for your convenience, at no
extra charge.</p>
<h3 class="unnumbered unlisted" id="example-186">Example</h3>
<div class="sourceCode" id="cb1379"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1379-1"><a href="stringref.html#cb1379-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1379-2"><a href="stringref.html#cb1379-2"></a></span>
<span id="cb1379-3"><a href="stringref.html#cb1379-3"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1379-4"><a href="stringref.html#cb1379-4"></a><span class="op">{</span></span>
<span id="cb1379-5"><a href="stringref.html#cb1379-5"></a>    <span class="dt">char</span> <span class="op">*</span>src <span class="op">=</span> <span class="st">"hockey hockey hockey hockey hockey hockey hockey hockey"</span><span class="op">;</span></span>
<span id="cb1379-6"><a href="stringref.html#cb1379-6"></a>    <span class="dt">char</span> dest<span class="op">[</span><span class="dv">20</span><span class="op">];</span></span>
<span id="cb1379-7"><a href="stringref.html#cb1379-7"></a></span>
<span id="cb1379-8"><a href="stringref.html#cb1379-8"></a>    <span class="dt">int</span> len<span class="op">;</span></span>
<span id="cb1379-9"><a href="stringref.html#cb1379-9"></a></span>
<span id="cb1379-10"><a href="stringref.html#cb1379-10"></a>    strcpy<span class="op">(</span>dest<span class="op">,</span> <span class="st">"I like "</span><span class="op">);</span> <span class="co">// dest is now "I like "</span></span>
<span id="cb1379-11"><a href="stringref.html#cb1379-11"></a></span>
<span id="cb1379-12"><a href="stringref.html#cb1379-12"></a>    len <span class="op">=</span> strlen<span class="op">(</span>dest<span class="op">);</span></span>
<span id="cb1379-13"><a href="stringref.html#cb1379-13"></a></span>
<span id="cb1379-14"><a href="stringref.html#cb1379-14"></a>    <span class="co">// tricky, but let's use some pointer arithmetic and math to append</span></span>
<span id="cb1379-15"><a href="stringref.html#cb1379-15"></a>    <span class="co">// as much of src as possible onto the end of dest, -1 on the length to</span></span>
<span id="cb1379-16"><a href="stringref.html#cb1379-16"></a>    <span class="co">// leave room for the terminator:</span></span>
<span id="cb1379-17"><a href="stringref.html#cb1379-17"></a>    strncpy<span class="op">(</span>dest<span class="op">+</span>len<span class="op">,</span> src<span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span>dest<span class="op">)-</span>len<span class="op">-</span><span class="dv">1</span><span class="op">);</span></span>
<span id="cb1379-18"><a href="stringref.html#cb1379-18"></a></span>
<span id="cb1379-19"><a href="stringref.html#cb1379-19"></a>    <span class="co">// remember that sizeof() returns the size of the array in bytes</span></span>
<span id="cb1379-20"><a href="stringref.html#cb1379-20"></a>    <span class="co">// and a char is a byte:</span></span>
<span id="cb1379-21"><a href="stringref.html#cb1379-21"></a>    dest<span class="op">[</span><span class="kw">sizeof</span><span class="op">(</span>dest<span class="op">)-</span><span class="dv">1</span><span class="op">]</span> <span class="op">=</span> <span class="ch">'\0'</span><span class="op">;</span> <span class="co">// terminate</span></span>
<span id="cb1379-22"><a href="stringref.html#cb1379-22"></a></span>
<span id="cb1379-23"><a href="stringref.html#cb1379-23"></a>    <span class="co">// dest is now:       v null terminator</span></span>
<span id="cb1379-24"><a href="stringref.html#cb1379-24"></a>    <span class="co">// I like hockey hocke </span></span>
<span id="cb1379-25"><a href="stringref.html#cb1379-25"></a>    <span class="co">// 01234567890123456789012345</span></span>
<span id="cb1379-26"><a href="stringref.html#cb1379-26"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-175">See Also</h3>
<p><a href="stringref.html#man-memcpy"><code>memcpy()</code></a>, <a href="#man-strcat"><code>strcat()</code></a>, <a href="#man-strcat"><code>strncat()</code></a></p>
<hr>
<h2 data-number="64.3" id="man-strcat"><span class="header-section-number">64.3</span> <code>strcat()</code>,
<code>strncat()</code></h2>
<p>Concatenate two strings into a single string</p>
<h3 class="unnumbered unlisted" id="synopsis-186">Synopsis</h3>
<div class="sourceCode" id="cb1380"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1380-1"><a href="stringref.html#cb1380-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1380-2"><a href="stringref.html#cb1380-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1380-3"><a href="stringref.html#cb1380-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> strcat<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>dest<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>src<span class="op">);</span></span>
<span id="cb1380-4"><a href="stringref.html#cb1380-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1380-5"><a href="stringref.html#cb1380-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> strncat<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>dest<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>src<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-186">Description</h3>
<p>“Concatenate”, for those not in the know, means to “stick together”.
These functions take two strings, and stick them together, storing the
result in the first string.</p>
<p>These functions don’t take the size of the first string into account
when it does the concatenation. What this means in practical terms is
that you can try to stick a 2 megabyte string into a 10 byte space. This
will lead to unintended consequences, unless you intended to lead to
unintended consequences, in which case it will lead to intended
unintended consequences.</p>
<p>Technical banter aside, your boss and/or professor will be irate.</p>
<p>If you want to make sure you don’t overrun the first string, be sure
to check the lengths of the strings first and use some highly technical
subtraction to make sure things fit.</p>
<p>You can actually only concatenate the first <code>n</code> characters
of the second string by using <code>strncat()</code> and specifying the
maximum number of characters to copy.</p>
<h3 class="unnumbered unlisted" id="return-value-184">Return Value</h3>
<p>Both functions return a pointer to the destination string, like most
of the string-oriented functions.</p>
<h3 class="unnumbered unlisted" id="example-187">Example</h3>
<div class="sourceCode" id="cb1381"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1381-1"><a href="stringref.html#cb1381-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1381-2"><a href="stringref.html#cb1381-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1381-3"><a href="stringref.html#cb1381-3"></a></span>
<span id="cb1381-4"><a href="stringref.html#cb1381-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1381-5"><a href="stringref.html#cb1381-5"></a><span class="op">{</span></span>
<span id="cb1381-6"><a href="stringref.html#cb1381-6"></a>    <span class="dt">char</span> dest<span class="op">[</span><span class="dv">30</span><span class="op">]</span> <span class="op">=</span> <span class="st">"Hello"</span><span class="op">;</span></span>
<span id="cb1381-7"><a href="stringref.html#cb1381-7"></a>    <span class="dt">char</span> <span class="op">*</span>src <span class="op">=</span> <span class="st">", World!"</span><span class="op">;</span></span>
<span id="cb1381-8"><a href="stringref.html#cb1381-8"></a>    <span class="dt">char</span> numbers<span class="op">[]</span> <span class="op">=</span> <span class="st">"12345678"</span><span class="op">;</span></span>
<span id="cb1381-9"><a href="stringref.html#cb1381-9"></a></span>
<span id="cb1381-10"><a href="stringref.html#cb1381-10"></a>    printf<span class="op">(</span><span class="st">"dest before strcat: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span> <span class="co">// "Hello"</span></span>
<span id="cb1381-11"><a href="stringref.html#cb1381-11"></a></span>
<span id="cb1381-12"><a href="stringref.html#cb1381-12"></a>    strcat<span class="op">(</span>dest<span class="op">,</span> src<span class="op">);</span></span>
<span id="cb1381-13"><a href="stringref.html#cb1381-13"></a>    printf<span class="op">(</span><span class="st">"dest after strcat:  </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span> <span class="co">// "Hello, world!"</span></span>
<span id="cb1381-14"><a href="stringref.html#cb1381-14"></a></span>
<span id="cb1381-15"><a href="stringref.html#cb1381-15"></a>    strncat<span class="op">(</span>dest<span class="op">,</span> numbers<span class="op">,</span> <span class="dv">3</span><span class="op">);</span> <span class="co">// strcat first 3 chars of numbers</span></span>
<span id="cb1381-16"><a href="stringref.html#cb1381-16"></a>    printf<span class="op">(</span><span class="st">"dest after strncat: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> dest<span class="op">);</span> <span class="co">// "Hello, world!123"</span></span>
<span id="cb1381-17"><a href="stringref.html#cb1381-17"></a><span class="op">}</span></span></code></pre></div>
<p>Notice I mixed and matched pointer and array notation there with
<code>src</code> and <code>numbers</code>; this is just fine with string
functions.</p>
<h3 class="unnumbered unlisted" id="see-also-176">See Also</h3>
<p><a href="stringref.html#man-strlen"><code>strlen()</code></a></p>
<hr>
<h2 data-number="64.4" id="man-strcmp"><span class="header-section-number">64.4</span> <code>strcmp()</code>,
<code>strncmp()</code>, <code>memcmp()</code></h2>
<p>Compare two strings or memory regions and return a difference</p>
<h3 class="unnumbered unlisted" id="synopsis-187">Synopsis</h3>
<div class="sourceCode" id="cb1382"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1382-1"><a href="stringref.html#cb1382-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1382-2"><a href="stringref.html#cb1382-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1382-3"><a href="stringref.html#cb1382-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> strcmp<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s2<span class="op">);</span></span>
<span id="cb1382-4"><a href="stringref.html#cb1382-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1382-5"><a href="stringref.html#cb1382-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> strncmp<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span>
<span id="cb1382-6"><a href="stringref.html#cb1382-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1382-7"><a href="stringref.html#cb1382-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> memcmp<span class="op">(</span><span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-187">Description</h3>
<p>All these functions compare chunks of bytes in memory.</p>
<p><code>strcmp()</code> and <code>strncmp()</code> operate on
NUL-terminated strings, whereas <code>memcmp()</code> will compare the
number of bytes you specify, brazenly ignoring any NUL characters it
finds along the way.</p>
<p><code>strcmp()</code> compares the entire string down to the end,
while <code>strncmp()</code> only compares the first <code>n</code>
characters of the strings.</p>
<p>It’s a little funky what they return. Basically it’s a difference of
the strings, so if the strings are the same, it’ll return zero (since
the difference is zero). It’ll return non-zero if the strings differ;
basically it will find the first mismatched character and return
less-than zero if that character in <code>s1</code> is less than the
corresponding character in <code>s2</code>. It’ll return greater-than
zero if that character in <code>s1</code> is greater than that in
<code>s2</code>.</p>
<p>So if they return <code>0</code>, the comparison was equal (i.e.&nbsp;the
difference was <code>0</code>.)</p>
<p>These functions can be used as comparison functions for <a href="#man-qsort"><code>qsort()</code></a> if you have an array of
<code>char*</code>s you want to sort.</p>
<h3 class="unnumbered unlisted" id="return-value-185">Return Value</h3>
<p>Returns zero if the strings or memory are the same, less-than zero if
the first different character in <code>s1</code> is less than that in
<code>s2</code>, or greater-than zero if the first difference character
in <code>s1</code> is greater than than in <code>s2</code>.</p>
<h3 class="unnumbered unlisted" id="example-188">Example</h3>
<div class="sourceCode" id="cb1383"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1383-1"><a href="stringref.html#cb1383-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1383-2"><a href="stringref.html#cb1383-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1383-3"><a href="stringref.html#cb1383-3"></a></span>
<span id="cb1383-4"><a href="stringref.html#cb1383-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1383-5"><a href="stringref.html#cb1383-5"></a><span class="op">{</span></span>
<span id="cb1383-6"><a href="stringref.html#cb1383-6"></a>    <span class="dt">char</span> <span class="op">*</span>s1 <span class="op">=</span> <span class="st">"Muffin"</span><span class="op">;</span></span>
<span id="cb1383-7"><a href="stringref.html#cb1383-7"></a>    <span class="dt">char</span> <span class="op">*</span>s2 <span class="op">=</span> <span class="st">"Muffin Sandwich"</span><span class="op">;</span></span>
<span id="cb1383-8"><a href="stringref.html#cb1383-8"></a>    <span class="dt">char</span> <span class="op">*</span>s3 <span class="op">=</span> <span class="st">"Muffin"</span><span class="op">;</span></span>
<span id="cb1383-9"><a href="stringref.html#cb1383-9"></a></span>
<span id="cb1383-10"><a href="stringref.html#cb1383-10"></a>    <span class="dt">int</span> r1 <span class="op">=</span> strcmp<span class="op">(</span><span class="st">"Biscuits"</span><span class="op">,</span> <span class="st">"Kittens"</span><span class="op">);</span></span>
<span id="cb1383-11"><a href="stringref.html#cb1383-11"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r1<span class="op">);</span> <span class="co">// prints &lt; 0 since 'B' &lt; 'K'</span></span>
<span id="cb1383-12"><a href="stringref.html#cb1383-12"></a></span>
<span id="cb1383-13"><a href="stringref.html#cb1383-13"></a>    <span class="dt">int</span> r2 <span class="op">=</span> strcmp<span class="op">(</span><span class="st">"Kittens"</span><span class="op">,</span> <span class="st">"Biscuits"</span><span class="op">);</span></span>
<span id="cb1383-14"><a href="stringref.html#cb1383-14"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> r2<span class="op">);</span> <span class="co">// prints &gt; 0 since 'K' &gt; 'B'</span></span>
<span id="cb1383-15"><a href="stringref.html#cb1383-15"></a></span>
<span id="cb1383-16"><a href="stringref.html#cb1383-16"></a>    <span class="cf">if</span> <span class="op">(</span>strcmp<span class="op">(</span>s1<span class="op">,</span> s2<span class="op">)</span> <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1383-17"><a href="stringref.html#cb1383-17"></a>        printf<span class="op">(</span><span class="st">"This won't get printed because the strings differ</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1383-18"><a href="stringref.html#cb1383-18"></a></span>
<span id="cb1383-19"><a href="stringref.html#cb1383-19"></a>    <span class="cf">if</span> <span class="op">(</span>strcmp<span class="op">(</span>s1<span class="op">,</span> s3<span class="op">)</span> <span class="op">==</span> <span class="dv">0</span><span class="op">)</span></span>
<span id="cb1383-20"><a href="stringref.html#cb1383-20"></a>        printf<span class="op">(</span><span class="st">"This will print because s1 and s3 are the same</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1383-21"><a href="stringref.html#cb1383-21"></a></span>
<span id="cb1383-22"><a href="stringref.html#cb1383-22"></a>    <span class="co">// this is a little weird...but if the strings are the same, it'll</span></span>
<span id="cb1383-23"><a href="stringref.html#cb1383-23"></a>    <span class="co">// return zero, which can also be thought of as "false". Not-false</span></span>
<span id="cb1383-24"><a href="stringref.html#cb1383-24"></a>    <span class="co">// is "true", so (!strcmp()) will be true if the strings are the</span></span>
<span id="cb1383-25"><a href="stringref.html#cb1383-25"></a>    <span class="co">// same. yes, it's odd, but you see this all the time in the wild</span></span>
<span id="cb1383-26"><a href="stringref.html#cb1383-26"></a>    <span class="co">// so you might as well get used to it:</span></span>
<span id="cb1383-27"><a href="stringref.html#cb1383-27"></a></span>
<span id="cb1383-28"><a href="stringref.html#cb1383-28"></a>    <span class="cf">if</span> <span class="op">(!</span>strcmp<span class="op">(</span>s1<span class="op">,</span> s3<span class="op">))</span></span>
<span id="cb1383-29"><a href="stringref.html#cb1383-29"></a>        printf<span class="op">(</span><span class="st">"The strings are the same!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1383-30"><a href="stringref.html#cb1383-30"></a></span>
<span id="cb1383-31"><a href="stringref.html#cb1383-31"></a>    <span class="cf">if</span> <span class="op">(!</span>strncmp<span class="op">(</span>s1<span class="op">,</span> s2<span class="op">,</span> <span class="dv">6</span><span class="op">))</span></span>
<span id="cb1383-32"><a href="stringref.html#cb1383-32"></a>        printf<span class="op">(</span><span class="st">"The first 6 characters of s1 and s2 are the same</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1383-33"><a href="stringref.html#cb1383-33"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-177">See Also</h3>
<p><a href="stringref.html#man-strcmp"><code>memcmp()</code></a>, <a href="#man-qsort"><code>qsort()</code></a></p>
<hr>
<h2 data-number="64.5" id="man-strcoll"><span class="header-section-number">64.5</span> <code>strcoll()</code></h2>
<p>Compare two strings accounting for locale</p>
<h3 class="unnumbered unlisted" id="synopsis-188">Synopsis</h3>
<div class="sourceCode" id="cb1384"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1384-1"><a href="stringref.html#cb1384-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1384-2"><a href="stringref.html#cb1384-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1384-3"><a href="stringref.html#cb1384-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> strcoll<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s2<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-188">Description</h3>
<p>This is basically <code>strcmp()</code>, except that it handles
accented characters better depending on the locale.</p>
<p>For example, my <code>strcmp()</code> reports that the character “é”
(with accent) is greater than “f”. But that’s hardly useful for
alphabetizing.</p>
<p>By setting the <code>LC_COLLATE</code> locale value (either by name
or via <code>LC_ALL</code>), you can have <code>strcoll()</code> sort in
a way that’s more meaningful by the current locale. For example, by
having “é” appear sanely <em>before</em> “f”.</p>
<p>It’s also a lot slower than <code>strcmp()</code> so use it only if
you have to. See <a href="stringref.html#man-strxfrm"><code>strxfrm()</code></a> for a
potential speedup.</p>
<h3 class="unnumbered unlisted" id="return-value-186">Return Value</h3>
<p>Like the other string comparison functions, <code>strcoll()</code>
returns a negative value if <code>s1</code> is less than
<code>s2</code>, or a positive value if <code>s1</code> is greater than
<code>s2</code>. Or <code>0</code> if they are equal.</p>
<h3 class="unnumbered unlisted" id="example-189">Example</h3>
<div class="sourceCode" id="cb1385"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1385-1"><a href="stringref.html#cb1385-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1385-2"><a href="stringref.html#cb1385-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1385-3"><a href="stringref.html#cb1385-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1385-4"><a href="stringref.html#cb1385-4"></a></span>
<span id="cb1385-5"><a href="stringref.html#cb1385-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1385-6"><a href="stringref.html#cb1385-6"></a><span class="op">{</span></span>
<span id="cb1385-7"><a href="stringref.html#cb1385-7"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1385-8"><a href="stringref.html#cb1385-8"></a></span>
<span id="cb1385-9"><a href="stringref.html#cb1385-9"></a>    <span class="co">// If your source character set doesn't support "é" in a string</span></span>
<span id="cb1385-10"><a href="stringref.html#cb1385-10"></a>    <span class="co">// you can replace it with `\u00e9`, the Unicode code point</span></span>
<span id="cb1385-11"><a href="stringref.html#cb1385-11"></a>    <span class="co">// for "é".</span></span>
<span id="cb1385-12"><a href="stringref.html#cb1385-12"></a></span>
<span id="cb1385-13"><a href="stringref.html#cb1385-13"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strcmp<span class="op">(</span><span class="st">"é"</span><span class="op">,</span> <span class="st">"f"</span><span class="op">));</span>   <span class="co">// Reports é &gt; f, yuck.</span></span>
<span id="cb1385-14"><a href="stringref.html#cb1385-14"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strcoll<span class="op">(</span><span class="st">"é"</span><span class="op">,</span> <span class="st">"f"</span><span class="op">));</span>  <span class="co">// Reports é &lt; f, yay!</span></span>
<span id="cb1385-15"><a href="stringref.html#cb1385-15"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-178">See Also</h3>
<p><a href="stringref.html#man-strcmp"><code>strcmp()</code></a></p>
<hr>
<h2 data-number="64.6" id="man-strxfrm"><span class="header-section-number">64.6</span> <code>strxfrm()</code></h2>
<p>Transform a string for comparing based on locale</p>
<h3 class="unnumbered unlisted" id="synopsis-189">Synopsis</h3>
<div class="sourceCode" id="cb1386"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1386-1"><a href="stringref.html#cb1386-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1386-2"><a href="stringref.html#cb1386-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1386-3"><a href="stringref.html#cb1386-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> strxfrm<span class="op">(</span><span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s2<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-189">Description</h3>
<p>This is a strange little function, so bear with me.</p>
<p>Firstly, if you haven’t done so, get familiar with <a href="#man-strcoll"><code>strcoll()</code></a> because this is closely
related to that.</p>
<p>OK! Now that you’re back, you can think of <code>strxfrm()</code> as
the first part of the <code>strcoll()</code> internals. Basically,
<code>strcoll()</code> has to transform a string into a form that can be
compared with <code>strcmp()</code>. And it does this with
<code>strxfrm()</code> for both strings every time you call it.</p>
<p><code>strxform()</code> takes string <code>s2</code> and transforms
it (readies it for <code>strcmp()</code>) storing the result in
<code>s1</code>. It writes no more than <code>n</code> bytes, protecting
us from terrible buffer overflows.</p>
<p>But hang on—there’s another mode! If you pass <code>NULL</code> for
<code>s1</code> and <code>0</code> for <code>n</code>, it will return
the number of bytes that the transformed string <em>would have</em>
used<a href="footnotes.html#fn271" class="footnote-ref" id="fnref271" role="doc-noteref"><sup>271</sup></a>. This is useful if you need to
allocate some space to hold the transformed string before you
<code>strcmp()</code> it against another.</p>
<p>What I’m getting at, not to be too blunt, is that
<code>strcoll()</code> is slow compared to <code>strcmp()</code>. It
does a lot of extra work running <code>strxfrm()</code> on all its
strings.</p>
<p>In fact, we can see how it works by writing our own like this:</p>
<div class="sourceCode" id="cb1387"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1387-1"><a href="stringref.html#cb1387-1"></a><span class="dt">int</span> my_strcoll<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">char</span> <span class="op">*</span>s2<span class="op">)</span></span>
<span id="cb1387-2"><a href="stringref.html#cb1387-2"></a><span class="op">{</span></span>
<span id="cb1387-3"><a href="stringref.html#cb1387-3"></a>    <span class="co">// Use n = 0 to just get the lengths of the transformed strings</span></span>
<span id="cb1387-4"><a href="stringref.html#cb1387-4"></a>    <span class="dt">int</span> len1 <span class="op">=</span> strxfrm<span class="op">(</span>NULL<span class="op">,</span> s1<span class="op">,</span> <span class="dv">0</span><span class="op">)</span> <span class="op">+</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1387-5"><a href="stringref.html#cb1387-5"></a>    <span class="dt">int</span> len2 <span class="op">=</span> strxfrm<span class="op">(</span>NULL<span class="op">,</span> s2<span class="op">,</span> <span class="dv">0</span><span class="op">)</span> <span class="op">+</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1387-6"><a href="stringref.html#cb1387-6"></a></span>
<span id="cb1387-7"><a href="stringref.html#cb1387-7"></a>    <span class="co">// Allocate enough room for each</span></span>
<span id="cb1387-8"><a href="stringref.html#cb1387-8"></a>    <span class="dt">char</span> <span class="op">*</span>d1 <span class="op">=</span> malloc<span class="op">(</span>len1<span class="op">);</span></span>
<span id="cb1387-9"><a href="stringref.html#cb1387-9"></a>    <span class="dt">char</span> <span class="op">*</span>d2 <span class="op">=</span> malloc<span class="op">(</span>len2<span class="op">);</span></span>
<span id="cb1387-10"><a href="stringref.html#cb1387-10"></a></span>
<span id="cb1387-11"><a href="stringref.html#cb1387-11"></a>    <span class="co">// Transform the strings for comparison</span></span>
<span id="cb1387-12"><a href="stringref.html#cb1387-12"></a>    strxfrm<span class="op">(</span>d1<span class="op">,</span> s1<span class="op">,</span> len1<span class="op">);</span></span>
<span id="cb1387-13"><a href="stringref.html#cb1387-13"></a>    strxfrm<span class="op">(</span>d2<span class="op">,</span> s2<span class="op">,</span> len2<span class="op">);</span></span>
<span id="cb1387-14"><a href="stringref.html#cb1387-14"></a></span>
<span id="cb1387-15"><a href="stringref.html#cb1387-15"></a>    <span class="co">// Compare the transformed strings</span></span>
<span id="cb1387-16"><a href="stringref.html#cb1387-16"></a>    <span class="dt">int</span> result <span class="op">=</span> strcmp<span class="op">(</span>d1<span class="op">,</span> d2<span class="op">);</span></span>
<span id="cb1387-17"><a href="stringref.html#cb1387-17"></a></span>
<span id="cb1387-18"><a href="stringref.html#cb1387-18"></a>    <span class="co">// Free up the transformed strings</span></span>
<span id="cb1387-19"><a href="stringref.html#cb1387-19"></a>    free<span class="op">(</span>d2<span class="op">);</span></span>
<span id="cb1387-20"><a href="stringref.html#cb1387-20"></a>    free<span class="op">(</span>d1<span class="op">);</span></span>
<span id="cb1387-21"><a href="stringref.html#cb1387-21"></a></span>
<span id="cb1387-22"><a href="stringref.html#cb1387-22"></a>    <span class="cf">return</span> result<span class="op">;</span></span>
<span id="cb1387-23"><a href="stringref.html#cb1387-23"></a><span class="op">}</span></span></code></pre></div>
<p>You see on lines 12, 13, and 16, above how we transform the two input
strings and then call <code>strcmp()</code> on the result.</p>
<p>So why do we have this function? Can’t we just call
<code>strcoll()</code> and be done with it?</p>
<p>The idea is that if you have one string that you’re going to be
comparing against a whole lot of other ones, maybe you just want to
transform that string one time, then use the faster
<code>strcmp()</code> saving yourself a bunch of the work we had to do
in the function, above.</p>
<p>We’ll do that in the example.</p>
<h3 class="unnumbered unlisted" id="return-value-187">Return Value</h3>
<p>Returns the number of bytes in the transformed sequence. If the value
is greater than <code>n</code>, the results in <code>s1</code> are
meaningless.</p>
<h3 class="unnumbered unlisted" id="example-190">Example</h3>
<div class="sourceCode" id="cb1388"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1388-1"><a href="stringref.html#cb1388-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1388-2"><a href="stringref.html#cb1388-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1388-3"><a href="stringref.html#cb1388-3"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb1388-4"><a href="stringref.html#cb1388-4"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1388-5"><a href="stringref.html#cb1388-5"></a></span>
<span id="cb1388-6"><a href="stringref.html#cb1388-6"></a><span class="co">// Transform a string for comparison, returning a malloc'd</span></span>
<span id="cb1388-7"><a href="stringref.html#cb1388-7"></a><span class="co">// result</span></span>
<span id="cb1388-8"><a href="stringref.html#cb1388-8"></a><span class="dt">char</span> <span class="op">*</span>get_xfrm_str<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>s<span class="op">)</span></span>
<span id="cb1388-9"><a href="stringref.html#cb1388-9"></a><span class="op">{</span></span>
<span id="cb1388-10"><a href="stringref.html#cb1388-10"></a>    <span class="dt">int</span> len <span class="op">=</span> strxfrm<span class="op">(</span>NULL<span class="op">,</span> s<span class="op">,</span> <span class="dv">0</span><span class="op">)</span> <span class="op">+</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1388-11"><a href="stringref.html#cb1388-11"></a>    <span class="dt">char</span> <span class="op">*</span>d <span class="op">=</span> malloc<span class="op">(</span>len<span class="op">);</span></span>
<span id="cb1388-12"><a href="stringref.html#cb1388-12"></a></span>
<span id="cb1388-13"><a href="stringref.html#cb1388-13"></a>    strxfrm<span class="op">(</span>d<span class="op">,</span> s<span class="op">,</span> len<span class="op">);</span></span>
<span id="cb1388-14"><a href="stringref.html#cb1388-14"></a></span>
<span id="cb1388-15"><a href="stringref.html#cb1388-15"></a>    <span class="cf">return</span> d<span class="op">;</span></span>
<span id="cb1388-16"><a href="stringref.html#cb1388-16"></a><span class="op">}</span></span>
<span id="cb1388-17"><a href="stringref.html#cb1388-17"></a></span>
<span id="cb1388-18"><a href="stringref.html#cb1388-18"></a><span class="co">// Does half the work of a regular strcoll() because the second</span></span>
<span id="cb1388-19"><a href="stringref.html#cb1388-19"></a><span class="co">// string arrives already transformed.</span></span>
<span id="cb1388-20"><a href="stringref.html#cb1388-20"></a><span class="dt">int</span> half_strcoll<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">char</span> <span class="op">*</span>s2_transformed<span class="op">)</span></span>
<span id="cb1388-21"><a href="stringref.html#cb1388-21"></a><span class="op">{</span></span>
<span id="cb1388-22"><a href="stringref.html#cb1388-22"></a>    <span class="dt">char</span> <span class="op">*</span>s1_transformed <span class="op">=</span> get_xfrm_str<span class="op">(</span>s1<span class="op">);</span></span>
<span id="cb1388-23"><a href="stringref.html#cb1388-23"></a></span>
<span id="cb1388-24"><a href="stringref.html#cb1388-24"></a>    <span class="dt">int</span> result <span class="op">=</span> strcmp<span class="op">(</span>s1_transformed<span class="op">,</span> s2_transformed<span class="op">);</span></span>
<span id="cb1388-25"><a href="stringref.html#cb1388-25"></a></span>
<span id="cb1388-26"><a href="stringref.html#cb1388-26"></a>    free<span class="op">(</span>s1_transformed<span class="op">);</span></span>
<span id="cb1388-27"><a href="stringref.html#cb1388-27"></a></span>
<span id="cb1388-28"><a href="stringref.html#cb1388-28"></a>    <span class="cf">return</span> result<span class="op">;</span></span>
<span id="cb1388-29"><a href="stringref.html#cb1388-29"></a><span class="op">}</span></span>
<span id="cb1388-30"><a href="stringref.html#cb1388-30"></a></span>
<span id="cb1388-31"><a href="stringref.html#cb1388-31"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1388-32"><a href="stringref.html#cb1388-32"></a><span class="op">{</span></span>
<span id="cb1388-33"><a href="stringref.html#cb1388-33"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb1388-34"><a href="stringref.html#cb1388-34"></a></span>
<span id="cb1388-35"><a href="stringref.html#cb1388-35"></a>    <span class="co">// Pre-transform the string to compare against</span></span>
<span id="cb1388-36"><a href="stringref.html#cb1388-36"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> get_xfrm_str<span class="op">(</span><span class="st">"éfg"</span><span class="op">);</span></span>
<span id="cb1388-37"><a href="stringref.html#cb1388-37"></a></span>
<span id="cb1388-38"><a href="stringref.html#cb1388-38"></a>    <span class="co">// Repeatedly compare against "éfg" </span></span>
<span id="cb1388-39"><a href="stringref.html#cb1388-39"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> half_strcoll<span class="op">(</span><span class="st">"fgh"</span><span class="op">,</span> s<span class="op">));</span>  <span class="co">// "fgh" &gt; "éfg"</span></span>
<span id="cb1388-40"><a href="stringref.html#cb1388-40"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> half_strcoll<span class="op">(</span><span class="st">"àbc"</span><span class="op">,</span> s<span class="op">));</span>  <span class="co">// "àbc" &lt; "éfg"</span></span>
<span id="cb1388-41"><a href="stringref.html#cb1388-41"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> half_strcoll<span class="op">(</span><span class="st">"ĥij"</span><span class="op">,</span> s<span class="op">));</span>  <span class="co">// "ĥij" &gt; "éfg"</span></span>
<span id="cb1388-42"><a href="stringref.html#cb1388-42"></a>    </span>
<span id="cb1388-43"><a href="stringref.html#cb1388-43"></a>    free<span class="op">(</span>s<span class="op">);</span></span>
<span id="cb1388-44"><a href="stringref.html#cb1388-44"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-179">See Also</h3>
<p><a href="stringref.html#man-strcoll"><code>strcoll()</code></a></p>
<hr>
<h2 data-number="64.7" id="man-strchr"><span class="header-section-number">64.7</span> <code>strchr()</code>,
<code>strrchr()</code>, <code>memchr()</code></h2>
<p>Find a character in a string</p>
<h3 class="unnumbered unlisted" id="synopsis-190">Synopsis</h3>
<div class="sourceCode" id="cb1389"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1389-1"><a href="stringref.html#cb1389-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1389-2"><a href="stringref.html#cb1389-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1389-3"><a href="stringref.html#cb1389-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strchr<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>str<span class="op">,</span> <span class="dt">int</span> c<span class="op">);</span></span>
<span id="cb1389-4"><a href="stringref.html#cb1389-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1389-5"><a href="stringref.html#cb1389-5" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strrchr<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>str<span class="op">,</span> <span class="dt">int</span> c<span class="op">);</span></span>
<span id="cb1389-6"><a href="stringref.html#cb1389-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1389-7"><a href="stringref.html#cb1389-7" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>memchr<span class="op">(</span><span class="dt">const</span> <span class="dt">void</span> <span class="op">*</span>s<span class="op">,</span> <span class="dt">int</span> c<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-190">Description</h3>
<p>The functions <code>strchr()</code> and <code>strrchr</code> find the
first or last occurrence of a letter in a string, respectively. (The
extra “r” in <code>strrchr()</code> stands for “reverse”–it looks
starting at the end of the string and working backward.) Each function
returns a pointer to the char in question, or <code>NULL</code> if the
letter isn’t found in the string.</p>
<p><code>memchr()</code> is similar, except that instead of stopping on
the first NUL character, it continues searching for however many bytes
you specify.</p>
<p>Quite straightforward.</p>
<p>One thing you can do if you want to find the next occurrence of the
letter after finding the first, is call the function again with the
previous return value plus one. (Remember pointer arithmetic?) Or minus
one if you’re looking in reverse. Don’t accidentally go off the end of
the string!</p>
<h3 class="unnumbered unlisted" id="return-value-188">Return Value</h3>
<p>Returns a pointer to the occurrence of the letter in the string, or
<code>NULL</code> if the letter is not found.</p>
<h3 class="unnumbered unlisted" id="example-191">Example</h3>
<div class="sourceCode" id="cb1390"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1390-1"><a href="stringref.html#cb1390-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1390-2"><a href="stringref.html#cb1390-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1390-3"><a href="stringref.html#cb1390-3"></a></span>
<span id="cb1390-4"><a href="stringref.html#cb1390-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1390-5"><a href="stringref.html#cb1390-5"></a><span class="op">{</span></span>
<span id="cb1390-6"><a href="stringref.html#cb1390-6"></a>    <span class="co">// "Hello, world!"</span></span>
<span id="cb1390-7"><a href="stringref.html#cb1390-7"></a>    <span class="co">//       ^  ^   ^</span></span>
<span id="cb1390-8"><a href="stringref.html#cb1390-8"></a>    <span class="co">//       A  B   C</span></span>
<span id="cb1390-9"><a href="stringref.html#cb1390-9"></a></span>
<span id="cb1390-10"><a href="stringref.html#cb1390-10"></a>    <span class="dt">char</span> <span class="op">*</span>str <span class="op">=</span> <span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb1390-11"><a href="stringref.html#cb1390-11"></a>    <span class="dt">char</span> <span class="op">*</span>p<span class="op">;</span></span>
<span id="cb1390-12"><a href="stringref.html#cb1390-12"></a></span>
<span id="cb1390-13"><a href="stringref.html#cb1390-13"></a>    p <span class="op">=</span> strchr<span class="op">(</span>str<span class="op">,</span> <span class="ch">','</span><span class="op">);</span>       <span class="co">// p now points at position A</span></span>
<span id="cb1390-14"><a href="stringref.html#cb1390-14"></a>    p <span class="op">=</span> strrchr<span class="op">(</span>str<span class="op">,</span> <span class="ch">'o'</span><span class="op">);</span>      <span class="co">// p now points at position B</span></span>
<span id="cb1390-15"><a href="stringref.html#cb1390-15"></a></span>
<span id="cb1390-16"><a href="stringref.html#cb1390-16"></a>    p <span class="op">=</span> memchr<span class="op">(</span>str<span class="op">,</span> <span class="ch">'!'</span><span class="op">,</span> <span class="dv">13</span><span class="op">);</span>   <span class="co">// p now points at position C</span></span>
<span id="cb1390-17"><a href="stringref.html#cb1390-17"></a></span>
<span id="cb1390-18"><a href="stringref.html#cb1390-18"></a>    <span class="co">// repeatedly find all occurrences of the letter 'B'</span></span>
<span id="cb1390-19"><a href="stringref.html#cb1390-19"></a>    str <span class="op">=</span> <span class="st">"A BIG BROWN BAT BIT BEEJ"</span><span class="op">;</span></span>
<span id="cb1390-20"><a href="stringref.html#cb1390-20"></a></span>
<span id="cb1390-21"><a href="stringref.html#cb1390-21"></a>    <span class="cf">for</span><span class="op">(</span>p <span class="op">=</span> strchr<span class="op">(</span>str<span class="op">,</span> <span class="ch">'B'</span><span class="op">);</span> p <span class="op">!=</span> NULL<span class="op">;</span> p <span class="op">=</span> strchr<span class="op">(</span>p <span class="op">+</span> <span class="dv">1</span><span class="op">,</span> <span class="ch">'B'</span><span class="op">))</span> <span class="op">{</span></span>
<span id="cb1390-22"><a href="stringref.html#cb1390-22"></a>        printf<span class="op">(</span><span class="st">"Found a 'B' here: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p<span class="op">);</span></span>
<span id="cb1390-23"><a href="stringref.html#cb1390-23"></a>    <span class="op">}</span></span>
<span id="cb1390-24"><a href="stringref.html#cb1390-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1391"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1391-1"><a href="stringref.html#cb1391-1" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BIG BROWN BAT BIT BEEJ</span>
<span id="cb1391-2"><a href="stringref.html#cb1391-2" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BROWN BAT BIT BEEJ</span>
<span id="cb1391-3"><a href="stringref.html#cb1391-3" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BAT BIT BEEJ</span>
<span id="cb1391-4"><a href="stringref.html#cb1391-4" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BIT BEEJ</span>
<span id="cb1391-5"><a href="stringref.html#cb1391-5" aria-hidden="true" tabindex="-1"></a>Found a 'B' here: BEEJ</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}
-->
<hr>
<h2 data-number="64.8" id="man-strspn"><span class="header-section-number">64.8</span> <code>strspn()</code>,
<code>strcspn()</code></h2>
<p>Return the length of a string consisting entirely of a set of
characters, or of not a set of characters</p>
<h3 class="unnumbered unlisted" id="synopsis-191">Synopsis</h3>
<div class="sourceCode" id="cb1392"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1392-1"><a href="stringref.html#cb1392-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1392-2"><a href="stringref.html#cb1392-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1392-3"><a href="stringref.html#cb1392-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> strspn<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>str<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>accept<span class="op">);</span></span>
<span id="cb1392-4"><a href="stringref.html#cb1392-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1392-5"><a href="stringref.html#cb1392-5" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> strcspn<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>str<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>reject<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-191">Description</h3>
<p><code>strspn()</code> will tell you the length of a string consisting
entirely of the set of characters in <code>accept</code>. That is, it
starts walking down <code>str</code> until it finds a character that is
<em>not</em> in the set (that is, a character that is not to be
accepted), and returns the length of the string so far.</p>
<p><code>strcspn()</code> works much the same way, except that it walks
down <code>str</code> until it finds a character in the
<code>reject</code> set (that is, a character that is to be rejected.)
It then returns the length of the string so far.</p>
<h3 class="unnumbered unlisted" id="return-value-189">Return Value</h3>
<p>The length of the string consisting of all characters in
<code>accept</code> (for <code>strspn()</code>), or the length of the
string consisting of all characters except <code>reject</code> (for
<code>strcspn()</code>).</p>
<h3 class="unnumbered unlisted" id="example-192">Example</h3>
<div class="sourceCode" id="cb1393"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1393-1"><a href="stringref.html#cb1393-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1393-2"><a href="stringref.html#cb1393-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1393-3"><a href="stringref.html#cb1393-3"></a></span>
<span id="cb1393-4"><a href="stringref.html#cb1393-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1393-5"><a href="stringref.html#cb1393-5"></a><span class="op">{</span></span>
<span id="cb1393-6"><a href="stringref.html#cb1393-6"></a>    <span class="dt">char</span> str1<span class="op">[]</span> <span class="op">=</span> <span class="st">"a banana"</span><span class="op">;</span></span>
<span id="cb1393-7"><a href="stringref.html#cb1393-7"></a>    <span class="dt">char</span> str2<span class="op">[]</span> <span class="op">=</span> <span class="st">"the bolivian navy on maenuvers in the south pacific"</span><span class="op">;</span></span>
<span id="cb1393-8"><a href="stringref.html#cb1393-8"></a>    <span class="dt">int</span> n<span class="op">;</span></span>
<span id="cb1393-9"><a href="stringref.html#cb1393-9"></a></span>
<span id="cb1393-10"><a href="stringref.html#cb1393-10"></a>    <span class="co">// how many letters in str1 until we reach something that's not a vowel?</span></span>
<span id="cb1393-11"><a href="stringref.html#cb1393-11"></a>    n <span class="op">=</span> strspn<span class="op">(</span>str1<span class="op">,</span> <span class="st">"aeiou"</span><span class="op">);</span></span>
<span id="cb1393-12"><a href="stringref.html#cb1393-12"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> n<span class="op">);</span>  <span class="co">// n == 1, just "a"</span></span>
<span id="cb1393-13"><a href="stringref.html#cb1393-13"></a></span>
<span id="cb1393-14"><a href="stringref.html#cb1393-14"></a>    <span class="co">// how many letters in str1 until we reach something that's not a, b,</span></span>
<span id="cb1393-15"><a href="stringref.html#cb1393-15"></a>    <span class="co">// or space?</span></span>
<span id="cb1393-16"><a href="stringref.html#cb1393-16"></a>    n <span class="op">=</span> strspn<span class="op">(</span>str1<span class="op">,</span> <span class="st">"ab "</span><span class="op">);</span></span>
<span id="cb1393-17"><a href="stringref.html#cb1393-17"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> n<span class="op">);</span>  <span class="co">// n == 4, "a ba"</span></span>
<span id="cb1393-18"><a href="stringref.html#cb1393-18"></a></span>
<span id="cb1393-19"><a href="stringref.html#cb1393-19"></a>    <span class="co">// how many letters in str2 before we get a "y"?</span></span>
<span id="cb1393-20"><a href="stringref.html#cb1393-20"></a>    n <span class="op">=</span> strcspn<span class="op">(</span>str2<span class="op">,</span> <span class="st">"y"</span><span class="op">);</span></span>
<span id="cb1393-21"><a href="stringref.html#cb1393-21"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> n<span class="op">);</span>  <span class="co">// n = 16, "the bolivian nav"</span></span>
<span id="cb1393-22"><a href="stringref.html#cb1393-22"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-180">See Also</h3>
<p><a href="stringref.html#man-strchr"><code>strchr()</code></a>, <a href="#man-strchr"><code>strrchr()</code></a></p>
<hr>
<h2 data-number="64.9" id="man-strpbrk"><span class="header-section-number">64.9</span> <code>strpbrk()</code></h2>
<p>Search a string for one of a set of characters</p>
<h3 class="unnumbered unlisted" id="synopsis-192">Synopsis</h3>
<div class="sourceCode" id="cb1394"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1394-1"><a href="stringref.html#cb1394-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1394-2"><a href="stringref.html#cb1394-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1394-3"><a href="stringref.html#cb1394-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strpbrk<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s1<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s2<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-192">Description</h3>
<p>This function searches string <code>s1</code> for any of the
characters that are found in string <code>s2</code>.</p>
<p>It’s just like how <code>strchr()</code> searches for a specific
character in a string, except it will match <em>any</em> of the
characters found in <code>s2</code>.</p>
<p>Think of the power!</p>
<h3 class="unnumbered unlisted" id="return-value-190">Return Value</h3>
<p>Returns a pointer to the first character matched in <code>s1</code>,
or NULL if the string isn’t found.</p>
<h3 class="unnumbered unlisted" id="example-193">Example</h3>
<div class="sourceCode" id="cb1395"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1395-1"><a href="stringref.html#cb1395-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1395-2"><a href="stringref.html#cb1395-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1395-3"><a href="stringref.html#cb1395-3"></a></span>
<span id="cb1395-4"><a href="stringref.html#cb1395-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1395-5"><a href="stringref.html#cb1395-5"></a><span class="op">{</span></span>
<span id="cb1395-6"><a href="stringref.html#cb1395-6"></a>    <span class="co">//  p points here after strpbrk</span></span>
<span id="cb1395-7"><a href="stringref.html#cb1395-7"></a>    <span class="co">//              v</span></span>
<span id="cb1395-8"><a href="stringref.html#cb1395-8"></a>    <span class="dt">char</span> <span class="op">*</span>s1 <span class="op">=</span> <span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb1395-9"><a href="stringref.html#cb1395-9"></a>    <span class="dt">char</span> <span class="op">*</span>s2 <span class="op">=</span> <span class="st">"dow!"</span><span class="op">;</span>  <span class="co">// Match any of these chars</span></span>
<span id="cb1395-10"><a href="stringref.html#cb1395-10"></a></span>
<span id="cb1395-11"><a href="stringref.html#cb1395-11"></a>    <span class="dt">char</span> <span class="op">*</span>p <span class="op">=</span> strpbrk<span class="op">(</span>s1<span class="op">,</span> s2<span class="op">);</span>  <span class="co">// p points to the o</span></span>
<span id="cb1395-12"><a href="stringref.html#cb1395-12"></a></span>
<span id="cb1395-13"><a href="stringref.html#cb1395-13"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p<span class="op">);</span>  <span class="co">// "o, world!"</span></span>
<span id="cb1395-14"><a href="stringref.html#cb1395-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-181">See Also</h3>
<p><a href="stringref.html#man-strchr"><code>strchr()</code></a>, <a href="#man-strchr"><code>memchr()</code></a></p>
<hr>
<h2 data-number="64.10" id="man-strstr"><span class="header-section-number">64.10</span> <code>strstr()</code></h2>
<p>Find a string in another string</p>
<h3 class="unnumbered unlisted" id="synopsis-193">Synopsis</h3>
<div class="sourceCode" id="cb1396"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1396-1"><a href="stringref.html#cb1396-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1396-2"><a href="stringref.html#cb1396-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1396-3"><a href="stringref.html#cb1396-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strstr<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>str<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>substr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-193">Description</h3>
<p>Let’s say you have a big long string, and you want to find a word, or
whatever substring strikes your fancy, inside the first string. Then
<code>strstr()</code> is for you! It’ll return a pointer to the
<code>substr</code> within the <code>str</code>!</p>
<h3 class="unnumbered unlisted" id="return-value-191">Return Value</h3>
<p>You get back a pointer to the occurrence of the <code>substr</code>
inside the <code>str</code>, or <code>NULL</code> if the substring can’t
be found.</p>
<h3 class="unnumbered unlisted" id="example-194">Example</h3>
<div class="sourceCode" id="cb1397"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1397-1"><a href="stringref.html#cb1397-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1397-2"><a href="stringref.html#cb1397-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1397-3"><a href="stringref.html#cb1397-3"></a></span>
<span id="cb1397-4"><a href="stringref.html#cb1397-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1397-5"><a href="stringref.html#cb1397-5"></a><span class="op">{</span></span>
<span id="cb1397-6"><a href="stringref.html#cb1397-6"></a>    <span class="dt">char</span> <span class="op">*</span>str <span class="op">=</span> <span class="st">"The quick brown fox jumped over the lazy dogs."</span><span class="op">;</span></span>
<span id="cb1397-7"><a href="stringref.html#cb1397-7"></a>    <span class="dt">char</span> <span class="op">*</span>p<span class="op">;</span></span>
<span id="cb1397-8"><a href="stringref.html#cb1397-8"></a></span>
<span id="cb1397-9"><a href="stringref.html#cb1397-9"></a>    p <span class="op">=</span> strstr<span class="op">(</span>str<span class="op">,</span> <span class="st">"lazy"</span><span class="op">);</span></span>
<span id="cb1397-10"><a href="stringref.html#cb1397-10"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p <span class="op">==</span> NULL<span class="op">?</span> <span class="st">"null"</span><span class="op">:</span> p<span class="op">);</span> <span class="co">// "lazy dogs."</span></span>
<span id="cb1397-11"><a href="stringref.html#cb1397-11"></a></span>
<span id="cb1397-12"><a href="stringref.html#cb1397-12"></a>    <span class="co">// p is NULL after this, since the string "wombat" isn't in str:</span></span>
<span id="cb1397-13"><a href="stringref.html#cb1397-13"></a>    p <span class="op">=</span> strstr<span class="op">(</span>str<span class="op">,</span> <span class="st">"wombat"</span><span class="op">);</span></span>
<span id="cb1397-14"><a href="stringref.html#cb1397-14"></a>    printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> p <span class="op">==</span> NULL<span class="op">?</span> <span class="st">"null"</span><span class="op">:</span> p<span class="op">);</span> <span class="co">// "null"</span></span>
<span id="cb1397-15"><a href="stringref.html#cb1397-15"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-182">See Also</h3>
<p><a href="stringref.html#man-strchr"><code>strchr()</code></a>, <a href="#man-strchr"><code>strrchr()</code></a>, <a href="#man-strspn"><code>strspn()</code></a>, <a href="#man-strspn"><code>strcspn()</code></a></p>
<hr>
<h2 data-number="64.11" id="man-strtok"><span class="header-section-number">64.11</span> <code>strtok()</code></h2>
<p>Tokenize a string</p>
<h3 class="unnumbered unlisted" id="synopsis-194">Synopsis</h3>
<div class="sourceCode" id="cb1398"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1398-1"><a href="stringref.html#cb1398-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1398-2"><a href="stringref.html#cb1398-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1398-3"><a href="stringref.html#cb1398-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strtok<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>str<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>delim<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-194">Description</h3>
<p>If you have a string that has a bunch of separators in it, and you
want to break that string up into individual pieces, this function can
do it for you.</p>
<p>The usage is a little bit weird, but at least whenever you see the
function in the wild, it’s consistently weird.</p>
<p>Basically, the first time you call it, you pass the string,
<code>str</code> that you want to break up in as the first argument. For
each subsequent call to get more tokens out of the string, you pass
<code>NULL</code>. This is a little weird, but <code>strtok()</code>
remembers the string you originally passed in, and continues to strip
tokens off for you.</p>
<p>Note that it does this by actually putting a NUL terminator after the
token, and then returning a pointer to the start of the token. So the
original string you pass in is destroyed, as it were. If you need to
preserve the string, be sure to pass a copy of it to
<code>strtok()</code> so the original isn’t destroyed.</p>
<h3 class="unnumbered unlisted" id="return-value-192">Return Value</h3>
<p>A pointer to the next token. If you’re out of tokens,
<code>NULL</code> is returned.</p>
<h3 class="unnumbered unlisted" id="example-195">Example</h3>
<div class="sourceCode" id="cb1399"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1399-1"><a href="stringref.html#cb1399-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1399-2"><a href="stringref.html#cb1399-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1399-3"><a href="stringref.html#cb1399-3"></a></span>
<span id="cb1399-4"><a href="stringref.html#cb1399-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1399-5"><a href="stringref.html#cb1399-5"></a><span class="op">{</span></span>
<span id="cb1399-6"><a href="stringref.html#cb1399-6"></a>    <span class="co">// break up the string into a series of space or</span></span>
<span id="cb1399-7"><a href="stringref.html#cb1399-7"></a>    <span class="co">// punctuation-separated words</span></span>
<span id="cb1399-8"><a href="stringref.html#cb1399-8"></a>    <span class="dt">char</span> str<span class="op">[]</span> <span class="op">=</span> <span class="st">"Where is my bacon, dude?"</span><span class="op">;</span></span>
<span id="cb1399-9"><a href="stringref.html#cb1399-9"></a>    <span class="dt">char</span> <span class="op">*</span>token<span class="op">;</span></span>
<span id="cb1399-10"><a href="stringref.html#cb1399-10"></a></span>
<span id="cb1399-11"><a href="stringref.html#cb1399-11"></a>    <span class="co">// Note that the following if-do-while construct is very very</span></span>
<span id="cb1399-12"><a href="stringref.html#cb1399-12"></a>    <span class="co">// very very very common to see when using strtok().</span></span>
<span id="cb1399-13"><a href="stringref.html#cb1399-13"></a></span>
<span id="cb1399-14"><a href="stringref.html#cb1399-14"></a>    <span class="co">// grab the first token (making sure there is a first token!)</span></span>
<span id="cb1399-15"><a href="stringref.html#cb1399-15"></a>    <span class="cf">if</span> <span class="op">((</span>token <span class="op">=</span> strtok<span class="op">(</span>str<span class="op">,</span> <span class="st">".,?! "</span><span class="op">))</span> <span class="op">!=</span> NULL<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1399-16"><a href="stringref.html#cb1399-16"></a>        <span class="cf">do</span> <span class="op">{</span></span>
<span id="cb1399-17"><a href="stringref.html#cb1399-17"></a>            printf<span class="op">(</span><span class="st">"Word: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"\n</span><span class="st">"</span><span class="op">,</span> token<span class="op">);</span></span>
<span id="cb1399-18"><a href="stringref.html#cb1399-18"></a></span>
<span id="cb1399-19"><a href="stringref.html#cb1399-19"></a>            <span class="co">// now, the while continuation condition grabs the</span></span>
<span id="cb1399-20"><a href="stringref.html#cb1399-20"></a>            <span class="co">// next token (by passing NULL as the first param)</span></span>
<span id="cb1399-21"><a href="stringref.html#cb1399-21"></a>            <span class="co">// and continues if the token's not NULL:</span></span>
<span id="cb1399-22"><a href="stringref.html#cb1399-22"></a>        <span class="op">}</span> <span class="cf">while</span> <span class="op">((</span>token <span class="op">=</span> strtok<span class="op">(</span>NULL<span class="op">,</span> <span class="st">".,?! "</span><span class="op">))</span> <span class="op">!=</span> NULL<span class="op">);</span></span>
<span id="cb1399-23"><a href="stringref.html#cb1399-23"></a>    <span class="op">}</span></span>
<span id="cb1399-24"><a href="stringref.html#cb1399-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1400"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1400-1"><a href="stringref.html#cb1400-1" aria-hidden="true" tabindex="-1"></a>Word: "Where"</span>
<span id="cb1400-2"><a href="stringref.html#cb1400-2" aria-hidden="true" tabindex="-1"></a>Word: "is"</span>
<span id="cb1400-3"><a href="stringref.html#cb1400-3" aria-hidden="true" tabindex="-1"></a>Word: "my"</span>
<span id="cb1400-4"><a href="stringref.html#cb1400-4" aria-hidden="true" tabindex="-1"></a>Word: "bacon"</span>
<span id="cb1400-5"><a href="stringref.html#cb1400-5" aria-hidden="true" tabindex="-1"></a>Word: "dude"</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-183">See Also</h3>
<p><a href="stringref.html#man-strchr"><code>strchr()</code></a>, <a href="#man-strchr"><code>strrchr()</code></a>, <a href="#man-strspn"><code>strspn()</code></a>, <a href="#man-strspn"><code>strcspn()</code></a></p>
<hr>
<h2 data-number="64.12" id="man-memset"><span class="header-section-number">64.12</span> <code>memset()</code></h2>
<p>Set a region of memory to a certain value</p>
<h3 class="unnumbered unlisted" id="synopsis-195">Synopsis</h3>
<div class="sourceCode" id="cb1401"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1401-1"><a href="stringref.html#cb1401-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1401-2"><a href="stringref.html#cb1401-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1401-3"><a href="stringref.html#cb1401-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>memset<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>s<span class="op">,</span> <span class="dt">int</span> c<span class="op">,</span> <span class="dt">size_t</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-195">Description</h3>
<p>This function is what you use to set a region of memory to a
particular value, namely <code>c</code> converted into
<code>unsigned char</code>.</p>
<p>The most common usage is to zero out an array or
<code>struct</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-193">Return Value</h3>
<p><code>memset()</code> returns whatever you passed in as
<code>s</code> for happy convenience.</p>
<h3 class="unnumbered unlisted" id="example-196">Example</h3>
<div class="sourceCode" id="cb1402"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1402-1"><a href="stringref.html#cb1402-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1402-2"><a href="stringref.html#cb1402-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1402-3"><a href="stringref.html#cb1402-3"></a></span>
<span id="cb1402-4"><a href="stringref.html#cb1402-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1402-5"><a href="stringref.html#cb1402-5"></a><span class="op">{</span></span>
<span id="cb1402-6"><a href="stringref.html#cb1402-6"></a>    <span class="kw">struct</span> banana <span class="op">{</span></span>
<span id="cb1402-7"><a href="stringref.html#cb1402-7"></a>        <span class="dt">float</span> ripeness<span class="op">;</span></span>
<span id="cb1402-8"><a href="stringref.html#cb1402-8"></a>        <span class="dt">char</span> <span class="op">*</span>peel_color<span class="op">;</span></span>
<span id="cb1402-9"><a href="stringref.html#cb1402-9"></a>        <span class="dt">int</span> grams<span class="op">;</span></span>
<span id="cb1402-10"><a href="stringref.html#cb1402-10"></a>    <span class="op">};</span></span>
<span id="cb1402-11"><a href="stringref.html#cb1402-11"></a></span>
<span id="cb1402-12"><a href="stringref.html#cb1402-12"></a>    <span class="kw">struct</span> banana b<span class="op">;</span></span>
<span id="cb1402-13"><a href="stringref.html#cb1402-13"></a></span>
<span id="cb1402-14"><a href="stringref.html#cb1402-14"></a>    memset<span class="op">(&amp;</span>b<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> b<span class="op">);</span></span>
<span id="cb1402-15"><a href="stringref.html#cb1402-15"></a></span>
<span id="cb1402-16"><a href="stringref.html#cb1402-16"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> b<span class="op">.</span>ripeness <span class="op">==</span> <span class="fl">0.0</span><span class="op">);</span>     <span class="co">// True</span></span>
<span id="cb1402-17"><a href="stringref.html#cb1402-17"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> b<span class="op">.</span>peel_color <span class="op">==</span> NULL<span class="op">);</span>  <span class="co">// True</span></span>
<span id="cb1402-18"><a href="stringref.html#cb1402-18"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> b<span class="op">.</span>grams <span class="op">==</span> <span class="dv">0</span><span class="op">);</span>          <span class="co">// True</span></span>
<span id="cb1402-19"><a href="stringref.html#cb1402-19"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-184">See Also</h3>
<p><a href="stringref.html#man-memcpy"><code>memcpy()</code></a>, <a href="#man-memcpy"><code>memmove()</code></a></p>
<hr>
<h2 data-number="64.13" id="man-strerror"><span class="header-section-number">64.13</span> <code>strerror()</code></h2>
<p>Get a string version of an error number</p>
<h3 class="unnumbered unlisted" id="synopsis-196">Synopsis</h3>
<div class="sourceCode" id="cb1403"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1403-1"><a href="stringref.html#cb1403-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1403-2"><a href="stringref.html#cb1403-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1403-3"><a href="stringref.html#cb1403-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>strerror<span class="op">(</span><span class="dt">int</span> errnum<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-196">Description</h3>
<p>This function ties closely into <code>perror()</code> (which prints a
human-readable error message corresponding to <code>errno</code>). But
instead of printing, <code>strerror()</code> returns a pointer to the
locale-specific error message string.</p>
<p>So if you ever need that string back for some reason (e.g.&nbsp;you’re
going to <code>fprintf()</code> it to a file or something), this
function will give it to you. All you need to do is pass in
<code>errno</code> as an argument. (Recall that <code>errno</code> gets
set as an error status by a variety of functions.)</p>
<p>You can actually pass in any integer for <code>errnum</code> you
want. The function will return <em>some</em> message, even if the number
doesn’t correspond to any known value for <code>errno</code>.</p>
<p>The values of <code>errno</code> and the strings returned by
<code>strerror()</code> are system-dependent.</p>
<h3 class="unnumbered unlisted" id="return-value-194">Return Value</h3>
<p>A string error message corresponding to the given error number.</p>
<p>You are not allowed to modify the returned string.</p>
<h3 class="unnumbered unlisted" id="example-197">Example</h3>
<div class="sourceCode" id="cb1404"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1404-1"><a href="stringref.html#cb1404-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1404-2"><a href="stringref.html#cb1404-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1404-3"><a href="stringref.html#cb1404-3"></a><span class="pp">#include </span><span class="im">&lt;errno.h&gt;</span></span>
<span id="cb1404-4"><a href="stringref.html#cb1404-4"></a></span>
<span id="cb1404-5"><a href="stringref.html#cb1404-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1404-6"><a href="stringref.html#cb1404-6"></a><span class="op">{</span></span>
<span id="cb1404-7"><a href="stringref.html#cb1404-7"></a>    <span class="dt">FILE</span> <span class="op">*</span>fp <span class="op">=</span> fopen<span class="op">(</span><span class="st">"NONEXISTENT_FILE.TXT"</span><span class="op">,</span> <span class="st">"r"</span><span class="op">);</span></span>
<span id="cb1404-8"><a href="stringref.html#cb1404-8"></a></span>
<span id="cb1404-9"><a href="stringref.html#cb1404-9"></a>    <span class="cf">if</span> <span class="op">(</span>fp <span class="op">==</span> NULL<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1404-10"><a href="stringref.html#cb1404-10"></a>        <span class="dt">char</span> <span class="op">*</span>errmsg <span class="op">=</span> strerror<span class="op">(</span>errno<span class="op">);</span></span>
<span id="cb1404-11"><a href="stringref.html#cb1404-11"></a>        printf<span class="op">(</span><span class="st">"Error %d opening file: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> errno<span class="op">,</span> errmsg<span class="op">);</span></span>
<span id="cb1404-12"><a href="stringref.html#cb1404-12"></a>    <span class="op">}</span></span>
<span id="cb1404-13"><a href="stringref.html#cb1404-13"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1405"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1405-1"><a href="stringref.html#cb1405-1" aria-hidden="true" tabindex="-1"></a>Error 2 opening file: No such file or directory</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-185">See Also</h3>
<p><a href="stdio.html#man-perror"><code>perror()</code></a></p>
<hr>
<h2 data-number="64.14" id="man-strlen"><span class="header-section-number">64.14</span> <code>strlen()</code></h2>
<p>Returns the length of a string</p>
<h3 class="unnumbered unlisted" id="synopsis-197">Synopsis</h3>
<div class="sourceCode" id="cb1406"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1406-1"><a href="stringref.html#cb1406-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1406-2"><a href="stringref.html#cb1406-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1406-3"><a href="stringref.html#cb1406-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> strlen<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>s<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-197">Description</h3>
<p>This function returns the length of the passed null-terminated string
(not counting the NUL character at the end). It does this by walking
down the string and counting the bytes until the NUL character, so it’s
a little time consuming. If you have to get the length of the same
string repeatedly, save it off in a variable somewhere.</p>
<h3 class="unnumbered unlisted" id="return-value-195">Return Value</h3>
<p>Returns the number of bytes in the string. Note that this might be
different than the number of characters in a multibyte string.</p>
<h3 class="unnumbered unlisted" id="example-198">Example</h3>
<div class="sourceCode" id="cb1407"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1407-1"><a href="stringref.html#cb1407-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1407-2"><a href="stringref.html#cb1407-2"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb1407-3"><a href="stringref.html#cb1407-3"></a></span>
<span id="cb1407-4"><a href="stringref.html#cb1407-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1407-5"><a href="stringref.html#cb1407-5"></a><span class="op">{</span></span>
<span id="cb1407-6"><a href="stringref.html#cb1407-6"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"Hello, world!"</span><span class="op">;</span> <span class="co">// 13 characters</span></span>
<span id="cb1407-7"><a href="stringref.html#cb1407-7"></a></span>
<span id="cb1407-8"><a href="stringref.html#cb1407-8"></a>    <span class="co">// prints "The string is 13 characters long.":</span></span>
<span id="cb1407-9"><a href="stringref.html#cb1407-9"></a></span>
<span id="cb1407-10"><a href="stringref.html#cb1407-10"></a>    printf<span class="op">(</span><span class="st">"The string is %zu characters long.</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strlen<span class="op">(</span>s<span class="op">));</span></span>
<span id="cb1407-11"><a href="stringref.html#cb1407-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-186">See Also</h3>


</body>