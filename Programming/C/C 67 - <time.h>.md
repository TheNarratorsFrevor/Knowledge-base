<body>

<hr>
<h1 data-number="67" id="time"><span class="header-section-number">67</span> <code>&lt;time.h&gt;</code> Date
and Time Functions</h1>
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
<td><a href="time.html#man-clock"><code>clock()</code></a></td>
<td>How much processor time has been used by this process</td>
</tr>
<tr class="even">
<td><a href="time.html#man-difftime"><code>difftime()</code></a></td>
<td>Compute the difference between two times</td>
</tr>
<tr class="odd">
<td><a href="man-mktime"><code>mktime()</code></a></td>
<td>Convert a <code>struct tm</code> into a <code>time_t</code></td>
</tr>
<tr class="even">
<td><a href="time.html#man-time"><code>time()</code></a></td>
<td>Get the current calendar time</td>
</tr>
<tr class="odd">
<td><a href="time.html#man-timespec_get"><code>timespec_get()</code></a></td>
<td>Get a higher resolution time, probably now</td>
</tr>
<tr class="even">
<td><a href="time.html#man-asctime"><code>asctime()</code></a></td>
<td>Return a human-readable version of a <code>struct tm</code></td>
</tr>
<tr class="odd">
<td><a href="time.html#man-ctime"><code>ctime()</code></a></td>
<td>Return a human-readable version of a <code>time_t</code></td>
</tr>
<tr class="even">
<td><a href="time.html#man-gmtime"><code>gmtime()</code></a></td>
<td>Convert a calendar time into a UTC broken-down time</td>
</tr>
<tr class="odd">
<td><a href="time.html#man-localtime"><code>localtime()</code></a></td>
<td>Convert a calendar time into a broken-down local time</td>
</tr>
<tr class="even">
<td><a href="time.html#man-strftime"><code>strftime()</code></a></td>
<td>Formatted date and time output</td>
</tr>
</tbody>
</table>
<p>When it comes to time and C, there are two main types to look
for:</p>
<ul>
<li><p><strong><code>time_t</code></strong> holds a <em>calendar
time</em>. This is an potentially opaque numeric type that represents an
absolute time that can be converted to UTC<a href="footnotes.html#fn276" class="footnote-ref" id="fnref276" role="doc-noteref"><sup>276</sup></a>
or local time.</p></li>
<li><p><strong><code>struct tm</code></strong> holds a <em>broken-down
time</em>. This has things like the day of the week, the day of the
month, the hour, the minute, the second, etc.</p></li>
</ul>
<p>On POSIX systems and Windows, <code>time_t</code> is an integer and
represents the number of seconds that have elapsed since January 1, 1970
at 00:00 UTC.</p>
<p>A <code>struct tm</code> contains the following fields:</p>
<div class="sourceCode" id="cb1488"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1488-1"><a href="time.html#cb1488-1" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> tm <span class="op">{</span></span>
<span id="cb1488-2"><a href="time.html#cb1488-2" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_sec<span class="op">;</span>    <span class="co">// seconds after the minute -- [0, 60]</span></span>
<span id="cb1488-3"><a href="time.html#cb1488-3" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_min<span class="op">;</span>    <span class="co">// minutes after the hour -- [0, 59]</span></span>
<span id="cb1488-4"><a href="time.html#cb1488-4" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_hour<span class="op">;</span>   <span class="co">// hours since midnight -- [0, 23]</span></span>
<span id="cb1488-5"><a href="time.html#cb1488-5" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_mday<span class="op">;</span>   <span class="co">// day of the month -- [1, 31]</span></span>
<span id="cb1488-6"><a href="time.html#cb1488-6" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_mon<span class="op">;</span>    <span class="co">// months since January -- [0, 11]</span></span>
<span id="cb1488-7"><a href="time.html#cb1488-7" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_year<span class="op">;</span>   <span class="co">// years since 1900</span></span>
<span id="cb1488-8"><a href="time.html#cb1488-8" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_wday<span class="op">;</span>   <span class="co">// days since Sunday -- [0, 6]</span></span>
<span id="cb1488-9"><a href="time.html#cb1488-9" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_yday<span class="op">;</span>   <span class="co">// days since January 1 -- [0, 365]</span></span>
<span id="cb1488-10"><a href="time.html#cb1488-10" aria-hidden="true" tabindex="-1"></a>    <span class="dt">int</span> tm_isdst<span class="op">;</span>  <span class="co">// Daylight Saving Time flag</span></span>
<span id="cb1488-11"><a href="time.html#cb1488-11" aria-hidden="true" tabindex="-1"></a><span class="op">};</span></span></code></pre></div>
<p>You can convert between the two with <code>mktime()</code>,
<code>gmtime()</code>, and <code>localtime()</code>.</p>
<p>You can print time information to strings with <code>ctime()</code>,
<code>asctime()</code>, and <code>strftime()</code>.</p>
<h2 data-number="67.1" id="thread-safety-warning"><span class="header-section-number">67.1</span> Thread Safety Warning</h2>
<p><code>asctime()</code>, <code>ctime()</code>: These two functions
return a pointer to a <code>static</code> memory region. They both might
return the same pointer. If you need thread safety, you’ll need a mutex
across them. If you need both results at once, <code>strcpy()</code> one
of them out.</p>
<p>All these problems with <code>asctime()</code> and
<code>ctime()</code> can be avoided by using the more flexible and
thread-safe <code>strftime()</code> function instead.</p>
<p><code>localtime()</code>, <code>gmtime()</code>: These other two
functions also return a pointer to a <code>static</code> memory region.
They both might return the same pointer. If you need thread safety,
you’ll need a mutex across them. If you need both results at once, copy
the <code>struct</code> to another.</p>
<hr>
<h2 data-number="67.2" id="man-clock"><span class="header-section-number">67.2</span> <code>clock()</code></h2>
<p>How much processor time has been used by this process</p>
<h3 class="unnumbered unlisted" id="synopsis-223">Synopsis</h3>
<div class="sourceCode" id="cb1489"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1489-1"><a href="time.html#cb1489-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1489-2"><a href="time.html#cb1489-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1489-3"><a href="time.html#cb1489-3" aria-hidden="true" tabindex="-1"></a>clock_t clock<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-223">Description</h3>
<p>Your processor is juggling a lot of things right now. Just because a
process has been alive for 20 minutes doesn’t mean that it used 20
minutes of “CPU time”.</p>
<p>Most of the time your average process spends asleep, and that doesn’t
count toward the CPU time spent.</p>
<p>This function returns an opaque type representing the number of
“clock ticks”<a href="footnotes.html#fn277" class="footnote-ref" id="fnref277" role="doc-noteref"><sup>277</sup></a> the process has spent in
operation.</p>
<p>You can get the number of seconds out of that by dividing by the
macro <code>CLOCKS_PER_SEC</code>. This is an integer, so you will have
to cast part of the expression to a floating type to get a fractional
time.</p>
<p>Note that this is not the “wall clock time” of the program. If you
want to get that loosely use <code>time()</code> and
<code>difftime()</code> (which might only offer 1-second resolution) or
<code>timespec_get()</code> (which might only also offer low resolution,
but at least it <em>might</em> go to nanosecond level).</p>
<h3 class="unnumbered unlisted" id="return-value-221">Return Value</h3>
<p>Returns the amount of CPU time spent by this process. This comes back
in a form that can be divided by <code>CLOCKS_PER_SEC</code> to
determine the time in seconds.</p>
<h3 class="unnumbered unlisted" id="example-225">Example</h3>
<div class="sourceCode" id="cb1490"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1490-1"><a href="time.html#cb1490-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1490-2"><a href="time.html#cb1490-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1490-3"><a href="time.html#cb1490-3"></a></span>
<span id="cb1490-4"><a href="time.html#cb1490-4"></a><span class="co">// Deliberately naive Fibonacci</span></span>
<span id="cb1490-5"><a href="time.html#cb1490-5"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> fib<span class="op">(</span><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> n<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1490-6"><a href="time.html#cb1490-6"></a>    <span class="cf">if</span> <span class="op">(</span>n <span class="op">&lt;=</span> <span class="dv">1</span><span class="op">)</span> <span class="cf">return</span> n<span class="op">;</span></span>
<span id="cb1490-7"><a href="time.html#cb1490-7"></a></span>
<span id="cb1490-8"><a href="time.html#cb1490-8"></a>    <span class="cf">return</span> fib<span class="op">(</span>n<span class="op">-</span><span class="dv">1</span><span class="op">)</span> <span class="op">+</span> fib<span class="op">(</span>n<span class="op">-</span><span class="dv">2</span><span class="op">);</span></span>
<span id="cb1490-9"><a href="time.html#cb1490-9"></a><span class="op">}</span></span>
<span id="cb1490-10"><a href="time.html#cb1490-10"></a></span>
<span id="cb1490-11"><a href="time.html#cb1490-11"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1490-12"><a href="time.html#cb1490-12"></a><span class="op">{</span></span>
<span id="cb1490-13"><a href="time.html#cb1490-13"></a>    printf<span class="op">(</span><span class="st">"The 42nd Fibonacci Number is %lld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fib<span class="op">(</span><span class="dv">42</span><span class="op">));</span></span>
<span id="cb1490-14"><a href="time.html#cb1490-14"></a></span>
<span id="cb1490-15"><a href="time.html#cb1490-15"></a>    printf<span class="op">(</span><span class="st">"CPU time: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> clock<span class="op">()</span> <span class="op">/</span> <span class="op">(</span><span class="dt">double</span><span class="op">)</span>CLOCKS_PER_SEC<span class="op">);</span></span>
<span id="cb1490-16"><a href="time.html#cb1490-16"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1491"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1491-1"><a href="time.html#cb1491-1" aria-hidden="true" tabindex="-1"></a>The 42nd Fibonacci Number is 267914296</span>
<span id="cb1491-2"><a href="time.html#cb1491-2" aria-hidden="true" tabindex="-1"></a>CPU time: 1.863078</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-211">See Also</h3>
<p><a href="time.html#man-time"><code>time()</code></a>, <a href="#man-difftime"><code>difftime()</code></a>, <a href="#man-timespec_get"><code>timespec_get()</code></a></p>
<hr>
<h2 data-number="67.3" id="man-difftime"><span class="header-section-number">67.3</span> <code>difftime()</code></h2>
<p>Compute the difference between two times</p>
<h3 class="unnumbered unlisted" id="synopsis-224">Synopsis</h3>
<div class="sourceCode" id="cb1492"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1492-1"><a href="time.html#cb1492-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1492-2"><a href="time.html#cb1492-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1492-3"><a href="time.html#cb1492-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> difftime<span class="op">(</span><span class="dt">time_t</span> time1<span class="op">,</span> <span class="dt">time_t</span> time0<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-224">Description</h3>
<p>Since the <code>time_t</code> type is technically opaque, you can’t
just straight-up subtract to get the difference between two of them<a href="#fn278" class="footnote-ref" id="fnref278" role="doc-noteref"><sup>278</sup></a>. Use this function to do it.</p>
<p>There is no guarantee as to the resolution of this difference, but
it’s probably to the second.</p>
<h3 class="unnumbered unlisted" id="return-value-222">Return Value</h3>
<p>Returns the difference between two <code>time_t</code>s in
seconds.</p>
<h3 class="unnumbered unlisted" id="example-226">Example</h3>
<div class="sourceCode" id="cb1493"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1493-1"><a href="time.html#cb1493-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1493-2"><a href="time.html#cb1493-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1493-3"><a href="time.html#cb1493-3"></a></span>
<span id="cb1493-4"><a href="time.html#cb1493-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1493-5"><a href="time.html#cb1493-5"></a><span class="op">{</span></span>
<span id="cb1493-6"><a href="time.html#cb1493-6"></a>    <span class="co">// April 12, 1982 and change</span></span>
<span id="cb1493-7"><a href="time.html#cb1493-7"></a>    <span class="kw">struct</span> tm time_a <span class="op">=</span> <span class="op">{</span> <span class="op">.</span>tm_year<span class="op">=</span><span class="dv">82</span><span class="op">,</span> <span class="op">.</span>tm_mon<span class="op">=</span><span class="dv">3</span><span class="op">,</span> <span class="op">.</span>tm_mday<span class="op">=</span><span class="dv">12</span><span class="op">,</span></span>
<span id="cb1493-8"><a href="time.html#cb1493-8"></a>        <span class="op">.</span>tm_hour<span class="op">=</span><span class="dv">4</span><span class="op">,</span> <span class="op">.</span>tm_min<span class="op">=</span><span class="bn">00</span><span class="op">,</span> <span class="op">.</span>tm_sec<span class="op">=</span><span class="bn">04</span><span class="op">,</span> <span class="op">.</span>tm_isdst<span class="op">=-</span><span class="dv">1</span><span class="op">,</span></span>
<span id="cb1493-9"><a href="time.html#cb1493-9"></a>    <span class="op">};</span></span>
<span id="cb1493-10"><a href="time.html#cb1493-10"></a></span>
<span id="cb1493-11"><a href="time.html#cb1493-11"></a>    <span class="co">// November 15, 2020 and change</span></span>
<span id="cb1493-12"><a href="time.html#cb1493-12"></a>    <span class="kw">struct</span> tm time_b <span class="op">=</span> <span class="op">{</span> <span class="op">.</span>tm_year<span class="op">=</span><span class="dv">120</span><span class="op">,</span> <span class="op">.</span>tm_mon<span class="op">=</span><span class="dv">10</span><span class="op">,</span> <span class="op">.</span>tm_mday<span class="op">=</span><span class="dv">15</span><span class="op">,</span></span>
<span id="cb1493-13"><a href="time.html#cb1493-13"></a>        <span class="op">.</span>tm_hour<span class="op">=</span><span class="dv">16</span><span class="op">,</span> <span class="op">.</span>tm_min<span class="op">=</span><span class="dv">27</span><span class="op">,</span> <span class="op">.</span>tm_sec<span class="op">=</span><span class="bn">00</span><span class="op">,</span> <span class="op">.</span>tm_isdst<span class="op">=-</span><span class="dv">1</span><span class="op">,</span></span>
<span id="cb1493-14"><a href="time.html#cb1493-14"></a>    <span class="op">};</span></span>
<span id="cb1493-15"><a href="time.html#cb1493-15"></a></span>
<span id="cb1493-16"><a href="time.html#cb1493-16"></a>    <span class="dt">time_t</span> cal_a <span class="op">=</span> mktime<span class="op">(&amp;</span>time_a<span class="op">);</span></span>
<span id="cb1493-17"><a href="time.html#cb1493-17"></a>    <span class="dt">time_t</span> cal_b <span class="op">=</span> mktime<span class="op">(&amp;</span>time_b<span class="op">);</span></span>
<span id="cb1493-18"><a href="time.html#cb1493-18"></a></span>
<span id="cb1493-19"><a href="time.html#cb1493-19"></a>    <span class="dt">double</span> diff <span class="op">=</span> difftime<span class="op">(</span>cal_b<span class="op">,</span> cal_a<span class="op">);</span></span>
<span id="cb1493-20"><a href="time.html#cb1493-20"></a></span>
<span id="cb1493-21"><a href="time.html#cb1493-21"></a>    <span class="dt">double</span> years <span class="op">=</span> diff <span class="op">/</span> <span class="dv">60</span> <span class="op">/</span> <span class="dv">60</span> <span class="op">/</span> <span class="dv">24</span> <span class="op">/</span> <span class="fl">365.2425</span><span class="op">;</span>  <span class="co">// close enough</span></span>
<span id="cb1493-22"><a href="time.html#cb1493-22"></a></span>
<span id="cb1493-23"><a href="time.html#cb1493-23"></a>    printf<span class="op">(</span><span class="st">"%f seconds (%f years) between events</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> diff<span class="op">,</span> years<span class="op">);</span></span>
<span id="cb1493-24"><a href="time.html#cb1493-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1494"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1494-1"><a href="time.html#cb1494-1" aria-hidden="true" tabindex="-1"></a>1217996816.000000 seconds (38.596783 years) between events</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-212">See Also</h3>
<p><a href="time.html#man-time"><code>time()</code></a>, <a href="#man-mktime"><code>mktime()</code></a></p>
<hr>
<h2 data-number="67.4" id="man-mktime"><span class="header-section-number">67.4</span> <code>mktime()</code></h2>
<p>Convert a <code>struct tm</code> into a <code>time_t</code></p>
<h3 class="unnumbered unlisted" id="synopsis-225">Synopsis</h3>
<div class="sourceCode" id="cb1495"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1495-1"><a href="time.html#cb1495-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1495-2"><a href="time.html#cb1495-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1495-3"><a href="time.html#cb1495-3" aria-hidden="true" tabindex="-1"></a><span class="dt">time_t</span> mktime<span class="op">(</span><span class="kw">struct</span> tm <span class="op">*</span>timeptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-225">Description</h3>
<p>If you have a local date and time and want it converted to a
<code>time_t</code> (so that you can <code>difftime()</code> it or
whatever), you can convert it with this function.</p>
<p>Basically you fill out the fields in your <code>struct tm</code> in
local time and <code>mktime()</code> will convert those to the UTC
<code>time_t</code> equivalent.</p>
<p>A couple notes:</p>
<ul>
<li><p>Don’t bother filling out <code>tm_wday</code> or
<code>tm_yday</code>. <code>mktime()</code> will fill these out for
you.</p></li>
<li><p>You can set <code>tm_isdst</code> to <code>0</code> to indicate
your time isn’t Daylight Saving Time (DST), <code>1</code> to indicate
it is, and <code>-1</code> to have <code>mktime()</code> fill it in
according to your locale’s preference.</p></li>
</ul>
<p>If you need input in UTC, see the non-standard functions <a href="https://man.archlinux.org/man/timegm.3.en"><code>timegm()</code></a><a href="#fn279" class="footnote-ref" id="fnref279" role="doc-noteref"><sup>279</sup></a> for Unix-likes and <a href="https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64?view=msvc-160"><code>_mkgmtime()</code></a><a href="#fn280" class="footnote-ref" id="fnref280" role="doc-noteref"><sup>280</sup></a> for Windows.</p>
<h3 class="unnumbered unlisted" id="return-value-223">Return Value</h3>
<p>Returns the local time in the <code>struct tm</code> as a
<code>time_t</code> calendar time.</p>
<p>Returns <code>(time_t)(-1)</code> on error.</p>
<h3 class="unnumbered unlisted" id="example-227">Example</h3>
<p>In the following example, we have <code>mktime()</code> tell us if
that time was DST or not.</p>
<div class="sourceCode" id="cb1496"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1496-1"><a href="time.html#cb1496-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1496-2"><a href="time.html#cb1496-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1496-3"><a href="time.html#cb1496-3"></a></span>
<span id="cb1496-4"><a href="time.html#cb1496-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1496-5"><a href="time.html#cb1496-5"></a><span class="op">{</span></span>
<span id="cb1496-6"><a href="time.html#cb1496-6"></a>    <span class="kw">struct</span> tm broken_down_time <span class="op">=</span> <span class="op">{</span></span>
<span id="cb1496-7"><a href="time.html#cb1496-7"></a>        <span class="op">.</span>tm_year<span class="op">=</span><span class="dv">82</span><span class="op">,</span>   <span class="co">// years since 1900</span></span>
<span id="cb1496-8"><a href="time.html#cb1496-8"></a>        <span class="op">.</span>tm_mon<span class="op">=</span><span class="dv">3</span><span class="op">,</span>     <span class="co">// months since January -- [0, 11]</span></span>
<span id="cb1496-9"><a href="time.html#cb1496-9"></a>        <span class="op">.</span>tm_mday<span class="op">=</span><span class="dv">12</span><span class="op">,</span>   <span class="co">// day of the month -- [1, 31]</span></span>
<span id="cb1496-10"><a href="time.html#cb1496-10"></a>        <span class="op">.</span>tm_hour<span class="op">=</span><span class="dv">4</span><span class="op">,</span>    <span class="co">// hours since midnight -- [0, 23]</span></span>
<span id="cb1496-11"><a href="time.html#cb1496-11"></a>        <span class="op">.</span>tm_min<span class="op">=</span><span class="bn">00</span><span class="op">,</span>    <span class="co">// minutes after the hour -- [0, 59]</span></span>
<span id="cb1496-12"><a href="time.html#cb1496-12"></a>        <span class="op">.</span>tm_sec<span class="op">=</span><span class="bn">04</span><span class="op">,</span>    <span class="co">// seconds after the minute -- [0, 60]</span></span>
<span id="cb1496-13"><a href="time.html#cb1496-13"></a>        <span class="op">.</span>tm_isdst<span class="op">=-</span><span class="dv">1</span><span class="op">,</span>  <span class="co">// Daylight Saving Time flag</span></span>
<span id="cb1496-14"><a href="time.html#cb1496-14"></a>    <span class="op">};</span></span>
<span id="cb1496-15"><a href="time.html#cb1496-15"></a></span>
<span id="cb1496-16"><a href="time.html#cb1496-16"></a>    <span class="dt">time_t</span> calendar_time <span class="op">=</span> mktime<span class="op">(&amp;</span>broken_down_time<span class="op">);</span></span>
<span id="cb1496-17"><a href="time.html#cb1496-17"></a></span>
<span id="cb1496-18"><a href="time.html#cb1496-18"></a>    <span class="dt">char</span> <span class="op">*</span>days<span class="op">[]</span> <span class="op">=</span> <span class="op">{</span><span class="st">"Sunday"</span><span class="op">,</span> <span class="st">"Monday"</span><span class="op">,</span> <span class="st">"Tuesday"</span><span class="op">,</span></span>
<span id="cb1496-19"><a href="time.html#cb1496-19"></a>        <span class="st">"Wednesday"</span><span class="op">,</span> <span class="st">"Furzeday"</span><span class="op">,</span> <span class="st">"Friday"</span><span class="op">,</span> <span class="st">"Saturday"</span><span class="op">};</span></span>
<span id="cb1496-20"><a href="time.html#cb1496-20"></a></span>
<span id="cb1496-21"><a href="time.html#cb1496-21"></a>    <span class="co">// This will print what was in broken_down_time</span></span>
<span id="cb1496-22"><a href="time.html#cb1496-22"></a>    printf<span class="op">(</span><span class="st">"Local time : %s"</span><span class="op">,</span> asctime<span class="op">(</span>localtime<span class="op">(&amp;</span>calendar_time<span class="op">)));</span></span>
<span id="cb1496-23"><a href="time.html#cb1496-23"></a>    printf<span class="op">(</span><span class="st">"Is DST     : %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> broken_down_time<span class="op">.</span>tm_isdst<span class="op">);</span></span>
<span id="cb1496-24"><a href="time.html#cb1496-24"></a>    printf<span class="op">(</span><span class="st">"Day of week: %s</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> days<span class="op">[</span>broken_down_time<span class="op">.</span>tm_wday<span class="op">]);</span></span>
<span id="cb1496-25"><a href="time.html#cb1496-25"></a></span>
<span id="cb1496-26"><a href="time.html#cb1496-26"></a>    <span class="co">// This will print UTC for the local time, above</span></span>
<span id="cb1496-27"><a href="time.html#cb1496-27"></a>    printf<span class="op">(</span><span class="st">"UTC        : %s"</span><span class="op">,</span> asctime<span class="op">(</span>gmtime<span class="op">(&amp;</span>calendar_time<span class="op">)));</span></span>
<span id="cb1496-28"><a href="time.html#cb1496-28"></a><span class="op">}</span></span></code></pre></div>
<p>Output (for me in Pacific Time—UTC is 8 hours ahead):</p>
<div class="sourceCode" id="cb1497"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1497-1"><a href="time.html#cb1497-1" aria-hidden="true" tabindex="-1"></a>Local time : Mon Apr 12 04:00:04 1982</span>
<span id="cb1497-2"><a href="time.html#cb1497-2" aria-hidden="true" tabindex="-1"></a>Is DST     : 0</span>
<span id="cb1497-3"><a href="time.html#cb1497-3" aria-hidden="true" tabindex="-1"></a>Day of week: Monday</span>
<span id="cb1497-4"><a href="time.html#cb1497-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1497-5"><a href="time.html#cb1497-5" aria-hidden="true" tabindex="-1"></a>UTC        : Mon Apr 12 12:00:04 1982</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-213">See Also</h3>
<p><a href="time.html#man-localtime"><code>localtime()</code></a>, <a href="#man-gmtime"><code>gmtime()</code></a></p>
<hr>
<h2 data-number="67.5" id="man-time"><span class="header-section-number">67.5</span> <code>time()</code></h2>
<p>Get the current calendar time</p>
<h3 class="unnumbered unlisted" id="synopsis-226">Synopsis</h3>
<div class="sourceCode" id="cb1498"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1498-1"><a href="time.html#cb1498-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1498-2"><a href="time.html#cb1498-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1498-3"><a href="time.html#cb1498-3" aria-hidden="true" tabindex="-1"></a><span class="dt">time_t</span> time<span class="op">(</span><span class="dt">time_t</span> <span class="op">*</span>timer<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-226">Description</h3>
<p>Returns the current calendar time right now. I mean, now. No,
now!</p>
<p>If <code>timer</code> is not <code>NULL</code>, it gets loaded with
the current time, as well.</p>
<p>This can be converted into a <code>struct tm</code> with
<code>localtime()</code> or <code>gmtime()</code>, or printed directly
with <code>ctime()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-224">Return Value</h3>
<p>Returns the current calendar time. Also loads <code>timer</code> with
the current time if it’s not <code>NULL</code>.</p>
<p>Or returns <code>(time_t)(-1)</code> if the time isn’t available
because you’ve fallen out of the space-time continuum and/or the system
doesn’t support times.</p>
<h3 class="unnumbered unlisted" id="example-228">Example</h3>
<div class="sourceCode" id="cb1499"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1499-1"><a href="time.html#cb1499-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1499-2"><a href="time.html#cb1499-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1499-3"><a href="time.html#cb1499-3"></a></span>
<span id="cb1499-4"><a href="time.html#cb1499-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1499-5"><a href="time.html#cb1499-5"></a><span class="op">{</span></span>
<span id="cb1499-6"><a href="time.html#cb1499-6"></a>    <span class="dt">time_t</span> now <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1499-7"><a href="time.html#cb1499-7"></a></span>
<span id="cb1499-8"><a href="time.html#cb1499-8"></a>    printf<span class="op">(</span><span class="st">"The local time is %s"</span><span class="op">,</span> ctime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1499-9"><a href="time.html#cb1499-9"></a><span class="op">}</span></span></code></pre></div>
<p>Example output:</p>
<div class="sourceCode" id="cb1500"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1500-1"><a href="time.html#cb1500-1" aria-hidden="true" tabindex="-1"></a>The local time is Mon Mar  1 18:45:14 2021</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-214">See Also</h3>
<p><a href="time.html#man-localtime"><code>localtime()</code></a>, <a href="#man-gmtime"><code>gmtime()</code></a>, <a href="#man-ctime"><code>ctime()</code></a></p>
<hr>
<h2 data-number="67.6" id="man-timespec_get"><span class="header-section-number">67.6</span>
<code>timespec_get()</code></h2>
<p>Get a higher resolution time, probably now</p>
<h3 class="unnumbered unlisted" id="synopsis-227">Synopsis</h3>
<div class="sourceCode" id="cb1501"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1501-1"><a href="time.html#cb1501-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1501-2"><a href="time.html#cb1501-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1501-3"><a href="time.html#cb1501-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> timespec_get<span class="op">(</span><span class="kw">struct</span> timespec <span class="op">*</span>ts<span class="op">,</span> <span class="dt">int</span> base<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-227">Description</h3>
<p>This function loads the current time UTC (unless directed otherwise)
into the given <code>struct timespec</code>, <code>ts</code>.</p>
<p>That structure has two fields:</p>
<div class="sourceCode" id="cb1502"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1502-1"><a href="time.html#cb1502-1" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> timespec <span class="op">{</span></span>
<span id="cb1502-2"><a href="time.html#cb1502-2" aria-hidden="true" tabindex="-1"></a>    <span class="dt">time_t</span> tv_sec<span class="op">;</span>   <span class="co">// Whole seconds</span></span>
<span id="cb1502-3"><a href="time.html#cb1502-3" aria-hidden="true" tabindex="-1"></a>    <span class="dt">long</span>   tv_nsec<span class="op">;</span>  <span class="co">// Nanoseconds, 0-999999999</span></span>
<span id="cb1502-4"><a href="time.html#cb1502-4" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span></code></pre></div>
<p>Nanoseconds are billionths of a second. You can divide by
1000000000.0 to convert to seconds.</p>
<p>The <code>base</code> parameter has only one defined value, by the
spec: <code>TIME_UTC</code>. So portably make it that. This will load
<code>ts</code> with the current time in seconds since a system-defined
<a href="https://en.wikipedia.org/wiki/Unix_time">Epoch</a><a href="#fn281" class="footnote-ref" id="fnref281" role="doc-noteref"><sup>281</sup></a>, often January 1, 1970 at 00:00
UTC.</p>
<p>Your implementation might define other values for
<code>base</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-225">Return Value</h3>
<p>When <code>base</code> is <code>TIME_UTC</code>, loads
<code>ts</code> with the current UTC time.</p>
<p>On success, returns <code>base</code>, valid values for which will
always be non-zero. On error, returns <code>0</code>.</p>
<h3 class="unnumbered unlisted" id="example-229">Example</h3>
<div class="sourceCode" id="cb1503"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1503-1"><a href="time.html#cb1503-1"></a><span class="kw">struct</span> timespec ts<span class="op">;</span></span>
<span id="cb1503-2"><a href="time.html#cb1503-2"></a></span>
<span id="cb1503-3"><a href="time.html#cb1503-3"></a>timespec_get<span class="op">(&amp;</span>ts<span class="op">,</span> TIME_UTC<span class="op">);</span></span>
<span id="cb1503-4"><a href="time.html#cb1503-4"></a></span>
<span id="cb1503-5"><a href="time.html#cb1503-5"></a>printf<span class="op">(</span><span class="st">"%ld s, %ld ns</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ts<span class="op">.</span>tv_sec<span class="op">,</span> ts<span class="op">.</span>tv_nsec<span class="op">);</span></span>
<span id="cb1503-6"><a href="time.html#cb1503-6"></a></span>
<span id="cb1503-7"><a href="time.html#cb1503-7"></a><span class="dt">double</span> float_time <span class="op">=</span> ts<span class="op">.</span>tv_sec <span class="op">+</span> ts<span class="op">.</span>tv_nsec<span class="op">/</span><span class="fl">1000000000.0</span><span class="op">;</span></span>
<span id="cb1503-8"><a href="time.html#cb1503-8"></a>printf<span class="op">(</span><span class="st">"%f seconds since epoch</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> float_time<span class="op">);</span></span></code></pre></div>
<p>Example output:</p>
<div class="sourceCode" id="cb1504"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1504-1"><a href="time.html#cb1504-1" aria-hidden="true" tabindex="-1"></a>1614654187 s, 825540756 ns</span>
<span id="cb1504-2"><a href="time.html#cb1504-2" aria-hidden="true" tabindex="-1"></a>1614654187.825541 seconds since epoch</span></code></pre></div>
<p>Here’s a helper function to add values to a
<code>struct timespec</code> that handles negative values and nanosecond
overflow.</p>
<div class="sourceCode" id="cb1505"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1505-1"><a href="time.html#cb1505-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1505-2"><a href="time.html#cb1505-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1505-3"><a href="time.html#cb1505-3" aria-hidden="true" tabindex="-1"></a><span class="co">// Add delta seconds and delta nanoseconds to ts.</span></span>
<span id="cb1505-4"><a href="time.html#cb1505-4" aria-hidden="true" tabindex="-1"></a><span class="co">// Negative values are allowed. Each component is added individually.</span></span>
<span id="cb1505-5"><a href="time.html#cb1505-5" aria-hidden="true" tabindex="-1"></a><span class="co">//</span></span>
<span id="cb1505-6"><a href="time.html#cb1505-6" aria-hidden="true" tabindex="-1"></a><span class="co">// Subtract 1.5 seconds from the current value:</span></span>
<span id="cb1505-7"><a href="time.html#cb1505-7" aria-hidden="true" tabindex="-1"></a><span class="co">//</span></span>
<span id="cb1505-8"><a href="time.html#cb1505-8" aria-hidden="true" tabindex="-1"></a><span class="co">// timespec_add(&amp;ts, -1, -500000000L);</span></span>
<span id="cb1505-9"><a href="time.html#cb1505-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1505-10"><a href="time.html#cb1505-10" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> timespec <span class="op">*</span>timespec_add<span class="op">(</span><span class="kw">struct</span> timespec <span class="op">*</span>ts<span class="op">,</span> <span class="dt">long</span> dsec<span class="op">,</span> <span class="dt">long</span> dnsec<span class="op">)</span></span>
<span id="cb1505-11"><a href="time.html#cb1505-11" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1505-12"><a href="time.html#cb1505-12" aria-hidden="true" tabindex="-1"></a>    <span class="dt">long</span> sec <span class="op">=</span> <span class="op">(</span><span class="dt">long</span><span class="op">)</span>ts<span class="op">-&gt;</span>tv_sec <span class="op">+</span> dsec<span class="op">;</span></span>
<span id="cb1505-13"><a href="time.html#cb1505-13" aria-hidden="true" tabindex="-1"></a>    <span class="dt">long</span> nsec <span class="op">=</span> ts<span class="op">-&gt;</span>tv_nsec <span class="op">+</span> dnsec<span class="op">;</span></span>
<span id="cb1505-14"><a href="time.html#cb1505-14" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1505-15"><a href="time.html#cb1505-15" aria-hidden="true" tabindex="-1"></a>    ldiv_t qr <span class="op">=</span> ldiv<span class="op">(</span>nsec<span class="op">,</span> <span class="dv">1000000000</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb1505-16"><a href="time.html#cb1505-16" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1505-17"><a href="time.html#cb1505-17" aria-hidden="true" tabindex="-1"></a>    <span class="cf">if</span> <span class="op">(</span>qr<span class="op">.</span>rem <span class="op">&lt;</span> <span class="dv">0</span><span class="op">)</span> <span class="op">{</span></span>
<span id="cb1505-18"><a href="time.html#cb1505-18" aria-hidden="true" tabindex="-1"></a>        nsec <span class="op">=</span> <span class="dv">1000000000</span><span class="bu">L</span> <span class="op">+</span> qr<span class="op">.</span>rem<span class="op">;</span></span>
<span id="cb1505-19"><a href="time.html#cb1505-19" aria-hidden="true" tabindex="-1"></a>        sec <span class="op">+=</span> qr<span class="op">.</span>quot <span class="op">-</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1505-20"><a href="time.html#cb1505-20" aria-hidden="true" tabindex="-1"></a>    <span class="op">}</span> <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1505-21"><a href="time.html#cb1505-21" aria-hidden="true" tabindex="-1"></a>        nsec <span class="op">=</span> qr<span class="op">.</span>rem<span class="op">;</span></span>
<span id="cb1505-22"><a href="time.html#cb1505-22" aria-hidden="true" tabindex="-1"></a>        sec <span class="op">+=</span> qr<span class="op">.</span>quot<span class="op">;</span></span>
<span id="cb1505-23"><a href="time.html#cb1505-23" aria-hidden="true" tabindex="-1"></a>    <span class="op">}</span></span>
<span id="cb1505-24"><a href="time.html#cb1505-24" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1505-25"><a href="time.html#cb1505-25" aria-hidden="true" tabindex="-1"></a>    ts<span class="op">-&gt;</span>tv_sec <span class="op">=</span> sec<span class="op">;</span></span>
<span id="cb1505-26"><a href="time.html#cb1505-26" aria-hidden="true" tabindex="-1"></a>    ts<span class="op">-&gt;</span>tv_nsec <span class="op">=</span> nsec<span class="op">;</span></span>
<span id="cb1505-27"><a href="time.html#cb1505-27" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1505-28"><a href="time.html#cb1505-28" aria-hidden="true" tabindex="-1"></a>    <span class="cf">return</span> ts<span class="op">;</span></span>
<span id="cb1505-29"><a href="time.html#cb1505-29" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span></code></pre></div>
<p>And here are some functions to convert from <code>long double</code>
to <code>struct timespec</code> and back, just in case you like thinking
in decimals. This is more limited in significant figures than using the
integer values.</p>
<div class="sourceCode" id="cb1506"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1506-1"><a href="time.html#cb1506-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1506-2"><a href="time.html#cb1506-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1506-3"><a href="time.html#cb1506-3" aria-hidden="true" tabindex="-1"></a><span class="co">// Convert a struct timespec into a long double</span></span>
<span id="cb1506-4"><a href="time.html#cb1506-4" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> timespec_to_ld<span class="op">(</span><span class="kw">struct</span> timespec <span class="op">*</span>ts<span class="op">)</span></span>
<span id="cb1506-5"><a href="time.html#cb1506-5" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1506-6"><a href="time.html#cb1506-6" aria-hidden="true" tabindex="-1"></a>    <span class="cf">return</span> ts<span class="op">-&gt;</span>tv_sec <span class="op">+</span> ts<span class="op">-&gt;</span>tv_nsec <span class="op">/</span> <span class="fl">1000000000.0</span><span class="op">;</span></span>
<span id="cb1506-7"><a href="time.html#cb1506-7" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span>
<span id="cb1506-8"><a href="time.html#cb1506-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1506-9"><a href="time.html#cb1506-9" aria-hidden="true" tabindex="-1"></a><span class="co">// Convert a long double to a struct timespec</span></span>
<span id="cb1506-10"><a href="time.html#cb1506-10" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> timespec ld_to_timespec<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> t<span class="op">)</span></span>
<span id="cb1506-11"><a href="time.html#cb1506-11" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1506-12"><a href="time.html#cb1506-12" aria-hidden="true" tabindex="-1"></a>    <span class="dt">long</span> <span class="dt">double</span> f<span class="op">;</span></span>
<span id="cb1506-13"><a href="time.html#cb1506-13" aria-hidden="true" tabindex="-1"></a>    <span class="kw">struct</span> timespec ts<span class="op">;</span></span>
<span id="cb1506-14"><a href="time.html#cb1506-14" aria-hidden="true" tabindex="-1"></a>    ts<span class="op">.</span>tv_nsec <span class="op">=</span> modfl<span class="op">(</span>t<span class="op">,</span> <span class="op">&amp;</span>f<span class="op">)</span> <span class="op">*</span> <span class="dv">1000000000</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1506-15"><a href="time.html#cb1506-15" aria-hidden="true" tabindex="-1"></a>    ts<span class="op">.</span>tv_sec <span class="op">=</span> f<span class="op">;</span></span>
<span id="cb1506-16"><a href="time.html#cb1506-16" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1506-17"><a href="time.html#cb1506-17" aria-hidden="true" tabindex="-1"></a>    <span class="cf">return</span> ts<span class="op">;</span></span>
<span id="cb1506-18"><a href="time.html#cb1506-18" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-215">See Also</h3>
<p><a href="time.html#man-time"><code>time()</code></a>, <a href="#man-mtx_timedlock"><code>mtx_timedlock()</code></a>, <a href="#man-cnd_timedwait"><code>cnd_timedwait()</code></a></p>
<hr>
<h2 data-number="67.7" id="man-asctime"><span class="header-section-number">67.7</span> <code>asctime()</code></h2>
<p>Return a human-readable version of a <code>struct tm</code></p>
<h3 class="unnumbered unlisted" id="synopsis-228">Synopsis</h3>
<div class="sourceCode" id="cb1507"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1507-1"><a href="time.html#cb1507-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1507-2"><a href="time.html#cb1507-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1507-3"><a href="time.html#cb1507-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>asctime<span class="op">(</span><span class="dt">const</span> <span class="kw">struct</span> tm <span class="op">*</span>timeptr<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-228">Description</h3>
<p>This takes a time in a <code>struct tm</code> and returns a string
with that date in the form:</p>
<div class="sourceCode" id="cb1508"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1508-1"><a href="time.html#cb1508-1" aria-hidden="true" tabindex="-1"></a>Sun Sep 16 01:03:52 1973</span></code></pre></div>
<p>with a newline included at the end, rather unhelpfully. (<a href="#man-strftime"><code>strftime()</code></a> will give you more
flexibility.)</p>
<p>It’s just like <code>ctime()</code>, except it takes a
<code>struct tm</code> instead of a <code>time_t</code>.</p>
<p><strong>WARNING</strong>: This function returns a pointer to a
<code>static char*</code> region that isn’t thread-safe and might be
shared with the <code>ctime()</code> function. If you need thread
safety, use <code>strftime()</code> or use a mutex that covers
<code>ctime()</code> and <code>asctime()</code>.</p>
<p>Behavior is undefined for:</p>
<ul>
<li>Years less than 1000</li>
<li>Years greater than 9999</li>
<li>Any members of <code>timeptr</code> are out of range</li>
</ul>
<h3 class="unnumbered unlisted" id="return-value-226">Return Value</h3>
<p>Returns a pointer to the human-readable date string.</p>
<h3 class="unnumbered unlisted" id="example-230">Example</h3>
<div class="sourceCode" id="cb1509"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1509-1"><a href="time.html#cb1509-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1509-2"><a href="time.html#cb1509-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1509-3"><a href="time.html#cb1509-3"></a></span>
<span id="cb1509-4"><a href="time.html#cb1509-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1509-5"><a href="time.html#cb1509-5"></a><span class="op">{</span></span>
<span id="cb1509-6"><a href="time.html#cb1509-6"></a>    <span class="dt">time_t</span> now <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1509-7"><a href="time.html#cb1509-7"></a></span>
<span id="cb1509-8"><a href="time.html#cb1509-8"></a>    printf<span class="op">(</span><span class="st">"Local: %s"</span><span class="op">,</span> asctime<span class="op">(</span>localtime<span class="op">(&amp;</span>now<span class="op">)));</span></span>
<span id="cb1509-9"><a href="time.html#cb1509-9"></a>    printf<span class="op">(</span><span class="st">"UTC  : %s"</span><span class="op">,</span> asctime<span class="op">(</span>gmtime<span class="op">(&amp;</span>now<span class="op">)));</span></span>
<span id="cb1509-10"><a href="time.html#cb1509-10"></a><span class="op">}</span></span></code></pre></div>
<p>Sample output:</p>
<div class="sourceCode" id="cb1510"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1510-1"><a href="time.html#cb1510-1" aria-hidden="true" tabindex="-1"></a>Local: Mon Mar  1 21:17:34 2021</span>
<span id="cb1510-2"><a href="time.html#cb1510-2" aria-hidden="true" tabindex="-1"></a>UTC  : Tue Mar  2 05:17:34 2021</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-216">See Also</h3>
<p><a href="time.html#man-ctime"><code>ctime()</code></a>, <a href="#man-localtime"><code>localtime()</code></a>, <a href="#man-gmtime"><code>gmtime()</code></a></p>
<hr>
<h2 data-number="67.8" id="man-ctime"><span class="header-section-number">67.8</span> <code>ctime()</code></h2>
<p>Return a human-readable version of a <code>time_t</code></p>
<h3 class="unnumbered unlisted" id="synopsis-229">Synopsis</h3>
<div class="sourceCode" id="cb1511"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1511-1"><a href="time.html#cb1511-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1511-2"><a href="time.html#cb1511-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1511-3"><a href="time.html#cb1511-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>ctime<span class="op">(</span><span class="dt">const</span> <span class="dt">time_t</span> <span class="op">*</span>timer<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-229">Description</h3>
<p>This takes a time in a <code>time_t</code> and returns a string with
the local time and date in the form:</p>
<div class="sourceCode" id="cb1512"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1512-1"><a href="time.html#cb1512-1" aria-hidden="true" tabindex="-1"></a>Sun Sep 16 01:03:52 1973</span></code></pre></div>
<p>with a newline included at the end, rather unhelpfully. (<a href="#man-strftime"><code>strftime()</code></a> will give you more
flexibility.)</p>
<p>It’s just like <code>asctime()</code>, except it takes a
<code>time_t</code> instead of a <code>struct tm</code>.</p>
<p><strong>WARNING</strong>: This function returns a pointer to a
<code>static char*</code> region that isn’t thread-safe and might be
shared with the <code>asctime()</code> function. If you need thread
safety, use <code>strftime()</code> or use a mutex that covers
<code>ctime()</code> and <code>asctime()</code>.</p>
<p>Behavior is undefined for:</p>
<ul>
<li>Years less than 1000</li>
<li>Years greater than 9999</li>
<li>Any members of <code>timeptr</code> are out of range</li>
</ul>
<h3 class="unnumbered unlisted" id="return-value-227">Return Value</h3>
<p>A pointer to the human-readable local time and data string.</p>
<h3 class="unnumbered unlisted" id="example-231">Example</h3>
<div class="sourceCode" id="cb1513"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1513-1"><a href="time.html#cb1513-1"></a><span class="dt">time_t</span> now <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1513-2"><a href="time.html#cb1513-2"></a></span>
<span id="cb1513-3"><a href="time.html#cb1513-3"></a>printf<span class="op">(</span><span class="st">"Local: %s"</span><span class="op">,</span> ctime<span class="op">(&amp;</span>now<span class="op">));</span></span></code></pre></div>
<p>Sample output:</p>
<div class="sourceCode" id="cb1514"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1514-1"><a href="time.html#cb1514-1" aria-hidden="true" tabindex="-1"></a>Local: Mon Mar  1 21:32:23 2021</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-217">See Also</h3>
<p><a href="time.html#man-asctime"><code>asctime()</code></a></p>
<hr>
<h2 data-number="67.9" id="man-gmtime"><span class="header-section-number">67.9</span> <code>gmtime()</code></h2>
<p>Convert a calendar time into a UTC broken-down time</p>
<h3 class="unnumbered unlisted" id="synopsis-230">Synopsis</h3>
<div class="sourceCode" id="cb1515"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1515-1"><a href="time.html#cb1515-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1515-2"><a href="time.html#cb1515-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1515-3"><a href="time.html#cb1515-3" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> tm <span class="op">*</span>gmtime<span class="op">(</span><span class="dt">const</span> <span class="dt">time_t</span> <span class="op">*</span>timer<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-230">Description</h3>
<p>If you have a <code>time_t</code>, you can run it through this
function to get a <code>struct tm</code> back full of the corresponding
broken-down UTC time information.</p>
<p>This is just like <code>localtime()</code>, except it does UTC
instead of local time.</p>
<p>Once you have that <code>struct tm</code>, you can feed it to
<code>strftime()</code> to print it out.</p>
<p><strong>WARNING</strong>: This function returns a pointer to a
<code>static struct tm*</code> region that isn’t thread-safe and might
be shared with the <code>localtime()</code> function. If you need thread
safety use a mutex that covers <code>gmtime()</code> and
<code>localtime()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-228">Return Value</h3>
<p>Returns a pointer to the broken-down UTC time, or <code>NULL</code>
if it can’t be obtained.</p>
<h3 class="unnumbered unlisted" id="example-232">Example</h3>
<div class="sourceCode" id="cb1516"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1516-1"><a href="time.html#cb1516-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1516-2"><a href="time.html#cb1516-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1516-3"><a href="time.html#cb1516-3"></a></span>
<span id="cb1516-4"><a href="time.html#cb1516-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1516-5"><a href="time.html#cb1516-5"></a><span class="op">{</span></span>
<span id="cb1516-6"><a href="time.html#cb1516-6"></a>    <span class="dt">time_t</span> now <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1516-7"><a href="time.html#cb1516-7"></a></span>
<span id="cb1516-8"><a href="time.html#cb1516-8"></a>    printf<span class="op">(</span><span class="st">"UTC  : %s"</span><span class="op">,</span> asctime<span class="op">(</span>gmtime<span class="op">(&amp;</span>now<span class="op">)));</span></span>
<span id="cb1516-9"><a href="time.html#cb1516-9"></a>    printf<span class="op">(</span><span class="st">"Local: %s"</span><span class="op">,</span> asctime<span class="op">(</span>localtime<span class="op">(&amp;</span>now<span class="op">)));</span></span>
<span id="cb1516-10"><a href="time.html#cb1516-10"></a><span class="op">}</span></span></code></pre></div>
<p>Sample output:</p>
<div class="sourceCode" id="cb1517"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1517-1"><a href="time.html#cb1517-1" aria-hidden="true" tabindex="-1"></a>UTC  : Tue Mar  2 05:40:05 2021</span>
<span id="cb1517-2"><a href="time.html#cb1517-2" aria-hidden="true" tabindex="-1"></a>Local: Mon Mar  1 21:40:05 2021</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-218">See Also</h3>
<p><a href="time.html#man-localtime"><code>localtime()</code></a>, <a href="#man-asctime"><code>asctime()</code></a>, <a href="#man-strftime"><code>strftime()</code></a></p>
<hr>
<h2 data-number="67.10" id="man-localtime"><span class="header-section-number">67.10</span> <code>localtime()</code></h2>
<p>Convert a calendar time into a broken-down local time</p>
<h3 class="unnumbered unlisted" id="synopsis-231">Synopsis</h3>
<div class="sourceCode" id="cb1518"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1518-1"><a href="time.html#cb1518-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1518-2"><a href="time.html#cb1518-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1518-3"><a href="time.html#cb1518-3" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> tm <span class="op">*</span>localtime<span class="op">(</span><span class="dt">const</span> <span class="dt">time_t</span> <span class="op">*</span>timer<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-231">Description</h3>
<p>If you have a <code>time_t</code>, you can run it through this
function to get a <code>struct tm</code> back full of the corresponding
broken-down local time information.</p>
<p>This is just like <code>gmtime()</code>, except it does local time
instead of UTC.</p>
<p>Once you have that <code>struct tm</code>, you can feed it to
<code>strftime()</code> to print it out.</p>
<p><strong>WARNING</strong>: This function returns a pointer to a
<code>static struct tm*</code> region that isn’t thread-safe and might
be shared with the <code>gmtime()</code> function. If you need thread
safety use a mutex that covers <code>gmtime()</code> and
<code>localtime()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-229">Return Value</h3>
<p>Returns a pointer to the broken-down local time, or <code>NULL</code>
if it can’t be obtained.</p>
<h3 class="unnumbered unlisted" id="example-233">Example</h3>
<div class="sourceCode" id="cb1519"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1519-1"><a href="time.html#cb1519-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1519-2"><a href="time.html#cb1519-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1519-3"><a href="time.html#cb1519-3"></a></span>
<span id="cb1519-4"><a href="time.html#cb1519-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1519-5"><a href="time.html#cb1519-5"></a><span class="op">{</span></span>
<span id="cb1519-6"><a href="time.html#cb1519-6"></a>    <span class="dt">time_t</span> now <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1519-7"><a href="time.html#cb1519-7"></a></span>
<span id="cb1519-8"><a href="time.html#cb1519-8"></a>    printf<span class="op">(</span><span class="st">"Local: %s"</span><span class="op">,</span> asctime<span class="op">(</span>localtime<span class="op">(&amp;</span>now<span class="op">)));</span></span>
<span id="cb1519-9"><a href="time.html#cb1519-9"></a>    printf<span class="op">(</span><span class="st">"UTC  : %s"</span><span class="op">,</span> asctime<span class="op">(</span>gmtime<span class="op">(&amp;</span>now<span class="op">)));</span></span>
<span id="cb1519-10"><a href="time.html#cb1519-10"></a><span class="op">}</span></span></code></pre></div>
<p>Sample output:</p>
<div class="sourceCode" id="cb1520"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1520-1"><a href="time.html#cb1520-1" aria-hidden="true" tabindex="-1"></a>Local: Mon Mar  1 21:40:05 2021</span>
<span id="cb1520-2"><a href="time.html#cb1520-2" aria-hidden="true" tabindex="-1"></a>UTC  : Tue Mar  2 05:40:05 2021</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-219">See Also</h3>
<p><a href="time.html#man-gmtime"><code>gmtime()</code></a>, <a href="#man-asctime"><code>asctime()</code></a>, <a href="#man-strftime"><code>strftime()</code></a></p>
<hr>
<h2 data-number="67.11" id="man-strftime"><span class="header-section-number">67.11</span> <code>strftime()</code></h2>
<p>Formatted date and time output</p>
<h3 class="unnumbered unlisted" id="synopsis-232">Synopsis</h3>
<div class="sourceCode" id="cb1521"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1521-1"><a href="time.html#cb1521-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1521-2"><a href="time.html#cb1521-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1521-3"><a href="time.html#cb1521-3" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> strftime<span class="op">(</span><span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> s<span class="op">,</span> <span class="dt">size_t</span> maxsize<span class="op">,</span></span>
<span id="cb1521-4"><a href="time.html#cb1521-4" aria-hidden="true" tabindex="-1"></a>                <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span> <span class="dt">restrict</span> format<span class="op">,</span></span>
<span id="cb1521-5"><a href="time.html#cb1521-5" aria-hidden="true" tabindex="-1"></a>                <span class="dt">const</span> <span class="kw">struct</span> tm <span class="op">*</span> <span class="dt">restrict</span> timeptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-232">Description</h3>
<p>This is the <a href="stdio.html#man-printf"><code>sprintf()</code></a> of date
and time functions. It’ll take a <code>struct tm</code> and produce a
string in just about whatever form you desire, for example:</p>
<div class="sourceCode" id="cb1522"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1522-1"><a href="time.html#cb1522-1" aria-hidden="true" tabindex="-1"></a>2021-03-01</span>
<span id="cb1522-2"><a href="time.html#cb1522-2" aria-hidden="true" tabindex="-1"></a>Monday, March 1 at 9:54 PM</span>
<span id="cb1522-3"><a href="time.html#cb1522-3" aria-hidden="true" tabindex="-1"></a>It's Monday!</span></code></pre></div>
<p>It’s a super flexible version of <code>asctime()</code>. And
thread-safe, besides, since it doesn’t rely on a static buffer to hold
the results.</p>
<p>Basically what you do is give it a destination, <code>s</code>, and
its max size in bytes in <code>maxsize</code>. Also, provide a
<code>format</code> string that’s analogous to <code>printf()</code>’s
format string, but with different format specifiers. And lastly, a
<code>struct tm</code> with the broken-down time information to use for
printing.</p>
<p>The <code>format</code> string works like this, for example:</p>
<div class="sourceCode" id="cb1523"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1523-1"><a href="time.html#cb1523-1" aria-hidden="true" tabindex="-1"></a><span class="st">"It's %A, %B %d!"</span></span></code></pre></div>
<p>Which produces:</p>
<div class="sourceCode" id="cb1524"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1524-1"><a href="time.html#cb1524-1" aria-hidden="true" tabindex="-1"></a>It's Monday, March 1!</span></code></pre></div>
<p>The <code>%A</code> is the full day-of-week name, the <code>%B</code>
is the full month name, and the <code>%d</code> is the day of the month.
<code>strftime()</code> substitutes the right thing to produce the
result. Brilliant!</p>
<p>So what are all the format specifiers? Glad you asked!</p>
<p>I’m going to be lazy and just drop this table in right from the
spec.</p>
<table>
<colgroup>
<col style="width: 10%">
<col style="width: 89%">
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>%a</code></td>
<td>Locale’s abbreviated weekday name. [<code>tm_wday</code>]</td>
</tr>
<tr class="even">
<td><code>%A</code></td>
<td>Locale’s full weekday name. [<code>tm_wday</code>]</td>
</tr>
<tr class="odd">
<td><code>%b</code></td>
<td>Locale’s abbreviated month name. [<code>tm_mon</code>]</td>
</tr>
<tr class="even">
<td><code>%B</code></td>
<td>Locale’s full month name. [<code>tm_mon</code>]</td>
</tr>
<tr class="odd">
<td><code>%c</code></td>
<td>Locale’s appropriate date and time representation.</td>
</tr>
<tr class="even">
<td><code>%C</code></td>
<td>Year divided by 100 and truncated to an integer, as a decimal number
(00–99). [<code>tm_year</code>]</td>
</tr>
<tr class="odd">
<td><code>%d</code></td>
<td>Day of the month as a decimal number (01–31).
[<code>tm_mday</code>]</td>
</tr>
<tr class="even">
<td><code>%D</code></td>
<td>Equivalent to <code>"%m/%d/%y"</code>. [<code>tm_mon</code>,
<code>tm_mday</code>, <code>tm_year</code>]</td>
</tr>
<tr class="odd">
<td><code>%e</code></td>
<td>Day of the month as a decimal number (1–31); a single digit is
preceded by a space. [<code>tm_mday</code>]</td>
</tr>
<tr class="even">
<td><code>%F</code></td>
<td>Equivalent to “%Y-%m-%d” (the ISO 8601 date format).
[<code>tm_year</code>, <code>tm_mon</code>, <code>tm_mday</code>]</td>
</tr>
<tr class="odd">
<td><code>%g</code></td>
<td>Last 2 digits of the week-based year (see below) as a decimal number
(00–99). [<code>tm_year</code>, <code>tm_wday</code>,
<code>tm_yday</code>]</td>
</tr>
<tr class="even">
<td><code>%G</code></td>
<td>Week-based year (see below) as a decimal number (e.g., 1997).
[<code>tm_year</code>, <code>tm_wday</code>, <code>tm_yday</code>]</td>
</tr>
<tr class="odd">
<td><code>%h</code></td>
<td>Equivalent to “%b”. [<code>tm_mon</code>]</td>
</tr>
<tr class="even">
<td><code>%H</code></td>
<td>Hour (24-hour clock) as a decimal number (00–23).
[<code>tm_hour</code>]</td>
</tr>
<tr class="odd">
<td><code>%I</code></td>
<td>Hour (12-hour clock) as a decimal number (01–12).
[<code>tm_hour</code>]</td>
</tr>
<tr class="even">
<td><code>%j</code></td>
<td>Day of the year as a decimal number (001–366).
[<code>tm_yday</code>]</td>
</tr>
<tr class="odd">
<td><code>%m</code></td>
<td>Month as a decimal number (01–12).</td>
</tr>
<tr class="even">
<td><code>%M</code></td>
<td>Minute as a decimal number (00–59). [<code>tm_min</code>]</td>
</tr>
<tr class="odd">
<td><code>%n</code></td>
<td>A new-line character.</td>
</tr>
<tr class="even">
<td><code>%p</code></td>
<td>Locale’s equivalent of the AM/PM designations associated with a
12-hour clock. [<code>tm_hour</code>]</td>
</tr>
<tr class="odd">
<td><code>%r</code></td>
<td>Locale’s 12-hour clock time. [<code>tm_hour</code>,
<code>tm_min</code>, <code>tm_sec</code>]</td>
</tr>
<tr class="even">
<td><code>%R</code></td>
<td>Equivalent to <code>"%H:%M"</code>. [<code>tm_hour</code>,
<code>tm_min</code>]</td>
</tr>
<tr class="odd">
<td><code>%S</code></td>
<td>Second as a decimal number (00–60). [<code>tm_sec</code>]</td>
</tr>
<tr class="even">
<td><code>%t</code></td>
<td>A horizontal-tab character.</td>
</tr>
<tr class="odd">
<td><code>%T</code></td>
<td>Equivalent to <code>"%H:%M:%S"</code> (the ISO 8601 time format).
[<code>tm_hour</code>, <code>tm_min</code>, <code>tm_sec</code>]</td>
</tr>
<tr class="even">
<td><code>%u</code></td>
<td>ISO 8601 weekday as a decimal number (1–7), where Monday is 1.
[<code>tm_wday</code>]</td>
</tr>
<tr class="odd">
<td><code>%U</code></td>
<td>Week number of the year (the first Sunday as the first day of week
1) as a decimal number (00–53). [<code>tm_year</code>,
<code>tm_wday</code>, <code>tm_yday</code>]</td>
</tr>
<tr class="even">
<td><code>%V</code></td>
<td>ISO 8601 week number (see below) as a decimal number (01–53).
[<code>tm_year</code>, <code>tm_wday</code>, <code>tm_yday</code>]</td>
</tr>
<tr class="odd">
<td><code>%w</code></td>
<td>Weekday as a decimal number (0–6), where Sunday is 0.</td>
</tr>
<tr class="even">
<td><code>%W</code></td>
<td>Week number of the year (the first Monday as the first day of week
1) as a decimal number (00–53). [<code>tm_year</code>,
<code>tm_wday</code>, <code>tm_yday</code>]</td>
</tr>
<tr class="odd">
<td><code>%x</code></td>
<td>Locale’s appropriate date representation.</td>
</tr>
<tr class="even">
<td><code>%X</code></td>
<td>Locale’s appropriate time representation.</td>
</tr>
<tr class="odd">
<td><code>%y</code></td>
<td>Last 2 digits of the year as a decimal number (00–99).
[<code>tm_year</code>]</td>
</tr>
<tr class="even">
<td><code>%Y</code></td>
<td>Year as a decimal number (e.g., 1997). [<code>tm_year</code>]</td>
</tr>
<tr class="odd">
<td><code>%z</code></td>
<td>Offset from UTC in the ISO 8601 format <code>"-0430"</code> (meaning
4 hours 30 minutes behind UTC, west of Greenwich), or by no characters
if no time zone is determinable. [<code>tm_isdst</code>]</td>
</tr>
<tr class="even">
<td><code>%Z</code></td>
<td>Locale’s time zone name or abbreviation, or by no characters if no
time zone is determinable. [<code>tm_isdst</code>]</td>
</tr>
<tr class="odd">
<td><code>%%</code></td>
<td>A plain ol’ %</td>
</tr>
</tbody>
</table>
<p>Phew. That’s love.</p>
<p><code>%G</code>, <code>%g</code>, and <code>%v</code> are a little
funky in that they use something called the ISO 8601 week-based year.
I’d never heard of it. But, again stealing from the spec, these are the
rules:</p>
<blockquote>
<p><code>%g</code>, <code>%G</code>, and <code>%V</code> give values
according to the ISO 8601 week-based year. In this system, weeks begin
on a Monday and week 1 of the year is the week that includes January
4th, which is also the week that includes the first Thursday of the
year, and is also the first week that contains at least four days in the
year. If the first Monday of January is the 2nd, 3rd, or 4th, the
preceding days are part of the last week of the preceding year; thus,
for Saturday 2nd January 1999, <code>%G</code> is replaced by
<code>1998</code> and <code>%V</code> is replaced by <code>53</code>. If
December 29th, 30th, or 31st is a Monday, it and any following days are
part of week 1 of the following year. Thus, for Tuesday 30th December
1997, <code>%G</code> is replaced by <code>1998</code> and
<code>%V</code> is replaced by <code>01</code>.</p>
</blockquote>
<p>Learn something new every day! If you want to know more, <a href="https://en.wikipedia.org/wiki/ISO_week_date">Wikipedia has a page
on it</a><a href="footnotes.html#fn282" class="footnote-ref" id="fnref282" role="doc-noteref"><sup>282</sup></a>.</p>
<p>If you’re in the “C” locale, the specifiers produce the following
(again, stolen from the spec):</p>
<table>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>%a</code></td>
<td>The first three characters of <code>%A</code>.</td>
</tr>
<tr class="even">
<td><code>%A</code></td>
<td>One of <code>Sunday</code>, <code>Monday</code>, … ,
<code>Saturday</code>.</td>
</tr>
<tr class="odd">
<td><code>%b</code></td>
<td>The first three characters of <code>%B</code>.</td>
</tr>
<tr class="even">
<td><code>%B</code></td>
<td>One of <code>January</code>, <code>February</code>, … ,
<code>December</code>.</td>
</tr>
<tr class="odd">
<td><code>%c</code></td>
<td>Equivalent to <code>%a %b %e %T %Y</code>.</td>
</tr>
<tr class="even">
<td><code>%p</code></td>
<td>One of <code>AM</code> or <code>PM</code>.</td>
</tr>
<tr class="odd">
<td><code>%r</code></td>
<td>Equivalent to <code>%I:%M:%S %p</code>.</td>
</tr>
<tr class="even">
<td><code>%x</code></td>
<td>Equivalent to <code>%m/%d/%y</code>.</td>
</tr>
<tr class="odd">
<td><code>%X</code></td>
<td>Equivalent to <code>%T</code>.</td>
</tr>
<tr class="even">
<td><code>%Z</code></td>
<td>Implementation-defined.</td>
</tr>
</tbody>
</table>
<p>There are additional variants of the format specifiers that indicate
you want to use a locale’s alternative format. These don’t exist for all
locales. It’s one of the format specifies above, with either an
<code>E</code> or <code>O</code> prefix:</p>
<div class="sourceCode" id="cb1525"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1525-1"><a href="time.html#cb1525-1" aria-hidden="true" tabindex="-1"></a>%Ec %EC %Ex %EX %Ey %EY %Od %Oe %OH %OI</span>
<span id="cb1525-2"><a href="time.html#cb1525-2" aria-hidden="true" tabindex="-1"></a>%Om %OM %OS %Ou %OU %OV %Ow %OW %Oy</span></code></pre></div>
<p>The <code>E</code> and <code>O</code> prefixes are ignored in the “C”
locale.</p>
<h3 class="unnumbered unlisted" id="return-value-230">Return Value</h3>
<p>Returns the total number of bytes put into the result string, not
including the NUL terminator.</p>
<p>If the result doesn’t fit in the string, zero is returned and the
value in <code>s</code> is indeterminate.</p>
<h3 class="unnumbered unlisted" id="example-234">Example</h3>
<div class="sourceCode" id="cb1526"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1526-1"><a href="time.html#cb1526-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1526-2"><a href="time.html#cb1526-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1526-3"><a href="time.html#cb1526-3"></a></span>
<span id="cb1526-4"><a href="time.html#cb1526-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1526-5"><a href="time.html#cb1526-5"></a><span class="op">{</span></span>
<span id="cb1526-6"><a href="time.html#cb1526-6"></a>    <span class="dt">char</span> s<span class="op">[</span><span class="dv">128</span><span class="op">];</span></span>
<span id="cb1526-7"><a href="time.html#cb1526-7"></a>    <span class="dt">time_t</span> now <span class="op">=</span> time<span class="op">(</span>NULL<span class="op">);</span></span>
<span id="cb1526-8"><a href="time.html#cb1526-8"></a></span>
<span id="cb1526-9"><a href="time.html#cb1526-9"></a>    <span class="co">// %c: print date as per current locale</span></span>
<span id="cb1526-10"><a href="time.html#cb1526-10"></a>    strftime<span class="op">(</span>s<span class="op">,</span> <span class="kw">sizeof</span> s<span class="op">,</span> <span class="st">"%c"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1526-11"><a href="time.html#cb1526-11"></a>    puts<span class="op">(</span>s<span class="op">);</span>   <span class="co">// Sun Feb 28 22:29:00 2021</span></span>
<span id="cb1526-12"><a href="time.html#cb1526-12"></a></span>
<span id="cb1526-13"><a href="time.html#cb1526-13"></a>    <span class="co">// %A: full weekday name</span></span>
<span id="cb1526-14"><a href="time.html#cb1526-14"></a>    <span class="co">// %B: full month name</span></span>
<span id="cb1526-15"><a href="time.html#cb1526-15"></a>    <span class="co">// %d: day of the month</span></span>
<span id="cb1526-16"><a href="time.html#cb1526-16"></a>    strftime<span class="op">(</span>s<span class="op">,</span> <span class="kw">sizeof</span> s<span class="op">,</span> <span class="st">"%A, %B %d"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1526-17"><a href="time.html#cb1526-17"></a>    puts<span class="op">(</span>s<span class="op">);</span>   <span class="co">// Sunday, February 28</span></span>
<span id="cb1526-18"><a href="time.html#cb1526-18"></a></span>
<span id="cb1526-19"><a href="time.html#cb1526-19"></a>    <span class="co">// %I: hour (12 hour clock)</span></span>
<span id="cb1526-20"><a href="time.html#cb1526-20"></a>    <span class="co">// %M: minute</span></span>
<span id="cb1526-21"><a href="time.html#cb1526-21"></a>    <span class="co">// %S: second</span></span>
<span id="cb1526-22"><a href="time.html#cb1526-22"></a>    <span class="co">// %p: AM or PM</span></span>
<span id="cb1526-23"><a href="time.html#cb1526-23"></a>    strftime<span class="op">(</span>s<span class="op">,</span> <span class="kw">sizeof</span> s<span class="op">,</span> <span class="st">"It's %I:%M:%S %p"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1526-24"><a href="time.html#cb1526-24"></a>    puts<span class="op">(</span>s<span class="op">);</span>   <span class="co">// It's 10:29:00 PM</span></span>
<span id="cb1526-25"><a href="time.html#cb1526-25"></a></span>
<span id="cb1526-26"><a href="time.html#cb1526-26"></a>    <span class="co">// %F: ISO 8601 yyyy-mm-dd</span></span>
<span id="cb1526-27"><a href="time.html#cb1526-27"></a>    <span class="co">// %T: ISO 8601 hh:mm:ss</span></span>
<span id="cb1526-28"><a href="time.html#cb1526-28"></a>    <span class="co">// %z: ISO 8601 time zone offset</span></span>
<span id="cb1526-29"><a href="time.html#cb1526-29"></a>    strftime<span class="op">(</span>s<span class="op">,</span> <span class="kw">sizeof</span> s<span class="op">,</span> <span class="st">"ISO 8601: %FT%T%z"</span><span class="op">,</span> localtime<span class="op">(&amp;</span>now<span class="op">));</span></span>
<span id="cb1526-30"><a href="time.html#cb1526-30"></a>    puts<span class="op">(</span>s<span class="op">);</span>   <span class="co">// ISO 8601: 2021-02-28T22:29:00-0800</span></span>
<span id="cb1526-31"><a href="time.html#cb1526-31"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-220">See Also</h3>
<p><a href="time.html#man-ctime"><code>ctime()</code></a>, <a href="#man-asctime"><code>asctime()</code></a></p>


</body>