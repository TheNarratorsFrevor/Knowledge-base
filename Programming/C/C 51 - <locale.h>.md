<body>
<hr>
<h1 data-number="51" id="locale"><span class="header-section-number">51</span> <code>&lt;locale.h&gt;</code>
locale handling</h1>
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
<td><a href="locale.html#man-setlocale"><code>setlocale()</code></a></td>
<td>Set the locale</td>
</tr>
<tr class="even">
<td><a href="locale.html#man-localeconv"><code>localeconv()</code></a></td>
<td>Get information about the current locale</td>
</tr>
</tbody>
</table>
<p>The “locale” is the details of how the program should run given its
physical location on the planet.</p>
<p>For example, in one locale, a unit of money might be printed as
<code>$123</code>, and in another <code>€123</code>.</p>
<p>Or one locale might use ASCII encoding and another UTF-8
encoding.</p>
<p>By default, the program runs in the “C” locale. It has a basic set of
characters with a single-byte encoding. If you try to print UTF-8
characters in the C locale, nothing will print. You have to switch to a
proper locale.</p>
<hr>
<h2 data-number="51.1" id="man-setlocale"><span class="header-section-number">51.1</span> <code>setlocale()</code></h2>
<p>Set the locale</p>
<h3 class="unnumbered unlisted" id="synopsis-52">Synopsis</h3>
<div class="sourceCode" id="cb961"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb961-1"><a href="locale.html#cb961-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb961-2"><a href="locale.html#cb961-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb961-3"><a href="locale.html#cb961-3" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>setlocale<span class="op">(</span><span class="dt">int</span> category<span class="op">,</span> <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>locale<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-52">Description</h3>
<p>Sets the <code>locale</code> for the given <code>category</code>.</p>
<p>Category is one of the following:</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Category</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>LC_ALL</code></td>
<td>All of the following categories</td>
</tr>
<tr class="even">
<td><code>LC_COLLATE</code></td>
<td>Affects the <a href="stringref.html#man-strcoll"><code>strcoll()</code></a> and <a href="#man-strxfrm"><code>strxfrm()</code></a> functions</td>
</tr>
<tr class="odd">
<td><code>LC_CTYPE</code></td>
<td>Affects the functions in <a href="#ctype"><code>&lt;ctype.h&gt;</code></a></td>
</tr>
<tr class="even">
<td><code>LC_MONETARY</code></td>
<td>Affects the monetary information returned from <a href="#man-localeconv"><code>localeconv()</code></a></td>
</tr>
<tr class="odd">
<td><code>LC_NUMERIC</code></td>
<td>Affects the decimal point for formatted I/O and formatted string
functions, and the monetary information returned from <a href="#man-localeconv"><code>localeconv()</code></a></td>
</tr>
<tr class="even">
<td><code>LC_TIME</code></td>
<td>Affects the <a href="time.html#man-strftime"><code>strftime()</code></a> and
<a href="wchar.html#man-wcsftime"><code>wcsftime()</code></a> functions</td>
</tr>
</tbody>
</table>
<p>And there are three portable things you can pass in for
<code>locale</code>; any other string passed in is
implementation-defined and non-portable.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Locale</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>"C"</code></td>
<td>Set the program to the C locale</td>
</tr>
<tr class="even">
<td><code>""</code></td>
<td>(Empty string) Set the program to the native locale of this
system</td>
</tr>
<tr class="odd">
<td><code>NULL</code></td>
<td>Change nothing; just return the current locale</td>
</tr>
<tr class="even">
<td>Other</td>
<td>Set the program to an implementation-defined locale</td>
</tr>
</tbody>
</table>
<p>The most common call, I’d wager, is this:</p>
<div class="sourceCode" id="cb962"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb962-1"><a href="locale.html#cb962-1" aria-hidden="true" tabindex="-1"></a><span class="co">// Set all locale settings to the local, native locale</span></span>
<span id="cb962-2"><a href="locale.html#cb962-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb962-3"><a href="locale.html#cb962-3" aria-hidden="true" tabindex="-1"></a>setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span></code></pre></div>
<p>Handily, <code>setlocale()</code> returns the locale that was just
set, so you could see what the actual locale is on your system.</p>
<h3 class="unnumbered unlisted" id="return-value-51">Return Value</h3>
<p>On success, returns a pointer to the string representing the current
locale. You may not modify this string, and it might be changed by
subsequent calls to <code>setlocale()</code>.</p>
<p>On failure, returns <code>NULL</code>.</p>
<h3 class="unnumbered unlisted" id="example-52">Example</h3>
<p>Here we get the current locale. Then we set it to the native locale,
and print out what that is.</p>
<div class="sourceCode" id="cb963"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb963-1"><a href="locale.html#cb963-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb963-2"><a href="locale.html#cb963-2"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb963-3"><a href="locale.html#cb963-3"></a></span>
<span id="cb963-4"><a href="locale.html#cb963-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb963-5"><a href="locale.html#cb963-5"></a><span class="op">{</span></span>
<span id="cb963-6"><a href="locale.html#cb963-6"></a>    <span class="dt">char</span> <span class="op">*</span>loc<span class="op">;</span></span>
<span id="cb963-7"><a href="locale.html#cb963-7"></a></span>
<span id="cb963-8"><a href="locale.html#cb963-8"></a>    <span class="co">// Get the current locale</span></span>
<span id="cb963-9"><a href="locale.html#cb963-9"></a>    loc <span class="op">=</span> setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb963-10"><a href="locale.html#cb963-10"></a></span>
<span id="cb963-11"><a href="locale.html#cb963-11"></a>    printf<span class="op">(</span><span class="st">"Starting locale: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> loc<span class="op">);</span></span>
<span id="cb963-12"><a href="locale.html#cb963-12"></a></span>
<span id="cb963-13"><a href="locale.html#cb963-13"></a>    <span class="co">// Set (and get) the locale to native locale</span></span>
<span id="cb963-14"><a href="locale.html#cb963-14"></a>    loc <span class="op">=</span> setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb963-15"><a href="locale.html#cb963-15"></a>    </span>
<span id="cb963-16"><a href="locale.html#cb963-16"></a>    printf<span class="op">(</span><span class="st">"Native locale: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> loc<span class="op">);</span></span>
<span id="cb963-17"><a href="locale.html#cb963-17"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb964"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb964-1"><a href="locale.html#cb964-1" aria-hidden="true" tabindex="-1"></a>Starting locale: C</span>
<span id="cb964-2"><a href="locale.html#cb964-2" aria-hidden="true" tabindex="-1"></a>Native locale: en_US.UTF-8</span></code></pre></div>
<p>Note that my native locale (on a Linux box) might be different from
what you see.</p>
<p>Nevertheless, I can explicitly set it on my system without a problem,
or to any other locale I have installed:</p>
<div class="sourceCode" id="cb965" data-startfrom="13"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c" style="counter-reset: source-line 12;"><span id="cb965-13"><a href="locale.html#cb965-13"></a>    loc <span class="op">=</span> setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">"en_US.UTF-8"</span><span class="op">);</span>   <span class="co">// Non-portable</span></span></code></pre></div>
<p>But again, your system might have different locales defined.</p>
<h3 class="unnumbered unlisted" id="see-also-48">See Also</h3>
<p><a href="locale.html#man-localeconv"><code>localeconv()</code></a>, <a href="#man-strcoll"><code>strcoll()</code></a>, <a href="#man-strxfrm"><code>strxfrm()</code></a>, <a href="#man-strftime"><code>strftime()</code></a>, <a href="#man-wcsftime"><code>wcsftime()</code></a>, <a href="#man-printf"><code>printf()</code></a>, <a href="#man-scanf"><code>scanf()</code></a>, <a href="#ctype"><code>&lt;ctype.h&gt;</code></a></p>
<hr>
<h2 data-number="51.2" id="man-localeconv"><span class="header-section-number">51.2</span> <code>localeconv()</code></h2>
<p>Get information about the current locale</p>
<h3 class="unnumbered unlisted" id="synopsis-53">Synopsis</h3>
<div class="sourceCode" id="cb966"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb966-1"><a href="locale.html#cb966-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb966-2"><a href="locale.html#cb966-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb966-3"><a href="locale.html#cb966-3" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> lconv <span class="op">*</span>localeconv<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-53">Description</h3>
<p>This function just returns a pointer to a <code>struct lconv</code>,
but is still a bit of a powerhouse.</p>
<p>The returned structure contains <em>tons</em> of information about
the locale. Here are the fields of <code>struct lconv</code> and their
meanings.</p>
<p>First, some conventions. In the field names, below, a
<code>_p_</code> means “positive”, and <code>_n_</code> means
“negative”, and <code>int_</code> means “international”. Though a lot of
these are type <code>char</code> or <code>char*</code>, most (or the
strings they point to) are actually treated as integers<a href="footnotes.html#fn228" class="footnote-ref" id="fnref228" role="doc-noteref"><sup>228</sup></a>.</p>
<p>Before we go further, know that <code>CHAR_MAX</code> (from
<code>&lt;limits.h&gt;</code>) is the maximum value that can be held in
a <code>char</code>. And that many of the following <code>char</code>
values use that to indicate the value isn’t available in the given
locale.</p>
<table>
<colgroup>
<col style="width: 31%">
<col style="width: 68%">
</colgroup>
<thead>
<tr class="header">
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>char *mon_decimal_point</code></td>
<td>Decimal pointer character for money, e.g.&nbsp;<code>"."</code>.</td>
</tr>
<tr class="even">
<td><code>char *mon_thousands_sep</code></td>
<td>Thousands separator character for money, e.g.&nbsp;<code>","</code>.</td>
</tr>
<tr class="odd">
<td><code>char *mon_grouping</code></td>
<td>Grouping description for money (see below).</td>
</tr>
<tr class="even">
<td><code>char *positive_sign</code></td>
<td>Positive sign for money, e.g.&nbsp;<code>"+"</code> or
<code>""</code>.</td>
</tr>
<tr class="odd">
<td><code>char *negative_sign</code></td>
<td>Negative sign for money, e.g.&nbsp;<code>"-"</code>.</td>
</tr>
<tr class="even">
<td><code>char *currency_symbol</code></td>
<td>Currency symbol, e.g.&nbsp;<code>"$"</code>.</td>
</tr>
<tr class="odd">
<td><code>char frac_digits</code></td>
<td>When printing monetary amounts, how many digits to print past the
decimal point, e.g.&nbsp;<code>2</code>.</td>
</tr>
<tr class="even">
<td><code>char p_cs_precedes</code></td>
<td><code>1</code> if the <code>currency_symbol</code> comes before the
value for a non-negative monetary amount, <code>0</code> if after.</td>
</tr>
<tr class="odd">
<td><code>char n_cs_precedes</code></td>
<td><code>1</code> if the <code>currency_symbol</code> comes before the
value for a negative monetary amount, <code>0</code> if after.</td>
</tr>
<tr class="even">
<td><code>char p_sep_by_space</code></td>
<td>Determines the separation of the <code>currency symbol</code> from
the value for non-negative amounts (see below).</td>
</tr>
<tr class="odd">
<td><code>char n_sep_by_space</code></td>
<td>Determines the separation of the <code>currency symbol</code> from
the value for negative amounts (see below).</td>
</tr>
<tr class="even">
<td><code>char p_sign_posn</code></td>
<td>Determines the <code>positive_sign</code> position for non-negative
values.</td>
</tr>
<tr class="odd">
<td><code>char p_sign_posn</code></td>
<td>Determines the <code>positive_sign</code> position for negative
values.</td>
</tr>
<tr class="even">
<td><code>char *int_curr_symbol</code></td>
<td>International currency symbol, e.g.&nbsp;<code>"USD "</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_frac_digits</code></td>
<td>International value for <code>frac_digits</code>.</td>
</tr>
<tr class="even">
<td><code>char int_p_cs_precedes</code></td>
<td>International value for <code>p_cs_precedes</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_n_cs_precedes</code></td>
<td>International value for <code>n_cs_precedes</code>.</td>
</tr>
<tr class="even">
<td><code>char int_p_sep_by_space</code></td>
<td>International value for <code>p_sep_by_space</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_n_sep_by_space</code></td>
<td>International value for <code>n_sep_by_space</code>.</td>
</tr>
<tr class="even">
<td><code>char int_p_sign_posn</code></td>
<td>International value for <code>p_sign_posn</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_n_sign_posn</code></td>
<td>International value for <code>n_sign_posn</code>.</td>
</tr>
</tbody>
</table>
<p>Even though many of these have <code>char</code> type, the value
stored within is meant to be accessed as an integer.</p>
<p>All the <code>sep_by_space</code> variants deal with spacing around
the currency sign. Valid values are:</p>
<table>
<colgroup>
<col style="width: 25%">
<col style="width: 75%">
</colgroup>
<thead>
<tr class="header">
<th style="text-align: center;">Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>0</code></td>
<td>No space between currency symbol and value.</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>1</code></td>
<td>Separate the currency symbol (and sign, if any) from the value with
a space.</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>2</code></td>
<td>Separate the sign symbol from the currency symbol (if adjacent) with
a space, otherwise separate the sign symbol from the value with a
space.</td>
</tr>
</tbody>
</table>
<p>The <code>sign_posn</code> variants are determined by the following
values:</p>
<table>
<thead>
<tr class="header">
<th style="text-align: center;">Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>0</code></td>
<td>Put parens around the value and the currency symbol.</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>1</code></td>
<td>Put the sign string in front of the currency symbol and value.</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>2</code></td>
<td>Put the sign string after the currency symbol and value.</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>3</code></td>
<td>Put the sign string directly in front of the currency symbol.</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>4</code></td>
<td>Put the sign string directly behind the currency symbol.</td>
</tr>
</tbody>
</table>
<p>For more information on the <code>mon_grouping</code> field, see <a href="#monetary-digit-grouping">“Monetary Digit Grouping” in the “Locale
and Internationalization” chapter</a>.</p>
<h3 class="unnumbered unlisted" id="return-value-52">Return Value</h3>
<p>Returns a pointer to the structure containing the locale
information.</p>
<p>The program may not modify this structure.</p>
<p>Subsequent calls to <code>localeconv()</code> may overwrite this
structure, as might calls to <code>setlocale()</code> with
<code>LC_ALL</code>, <code>LC_MONETARY</code>, or
<code>LC_NUMERIC</code>.</p>
<h3 class="unnumbered unlisted" id="example-53">Example</h3>
<p>Here’s a program to print the locale information for the native
locale.</p>
<div class="sourceCode" id="cb967"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb967-1"><a href="locale.html#cb967-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb967-2"><a href="locale.html#cb967-2"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb967-3"><a href="locale.html#cb967-3"></a><span class="pp">#include </span><span class="im">&lt;limits.h&gt;</span><span class="pp">  </span><span class="co">// for CHAR_MAX</span></span>
<span id="cb967-4"><a href="locale.html#cb967-4"></a></span>
<span id="cb967-5"><a href="locale.html#cb967-5"></a><span class="dt">void</span> print_grouping<span class="op">(</span><span class="dt">char</span> <span class="op">*</span>mg<span class="op">)</span></span>
<span id="cb967-6"><a href="locale.html#cb967-6"></a><span class="op">{</span></span>
<span id="cb967-7"><a href="locale.html#cb967-7"></a>    <span class="dt">int</span> done <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb967-8"><a href="locale.html#cb967-8"></a></span>
<span id="cb967-9"><a href="locale.html#cb967-9"></a>    <span class="cf">while</span> <span class="op">(!</span>done<span class="op">)</span> <span class="op">{</span></span>
<span id="cb967-10"><a href="locale.html#cb967-10"></a>        <span class="cf">if</span> <span class="op">(*</span>mg <span class="op">==</span> CHAR_MAX<span class="op">)</span></span>
<span id="cb967-11"><a href="locale.html#cb967-11"></a>            printf<span class="op">(</span><span class="st">"CHAR_MAX "</span><span class="op">);</span></span>
<span id="cb967-12"><a href="locale.html#cb967-12"></a>        <span class="cf">else</span></span>
<span id="cb967-13"><a href="locale.html#cb967-13"></a>            printf<span class="op">(</span><span class="st">"%c "</span><span class="op">,</span> <span class="op">*</span>mg <span class="op">+</span> <span class="ch">'0'</span><span class="op">);</span></span>
<span id="cb967-14"><a href="locale.html#cb967-14"></a>        done <span class="op">=</span> <span class="op">*</span>mg <span class="op">==</span> CHAR_MAX <span class="op">||</span> <span class="op">*</span>mg <span class="op">==</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb967-15"><a href="locale.html#cb967-15"></a>        mg<span class="op">++;</span></span>
<span id="cb967-16"><a href="locale.html#cb967-16"></a>    <span class="op">}</span></span>
<span id="cb967-17"><a href="locale.html#cb967-17"></a><span class="op">}</span></span>
<span id="cb967-18"><a href="locale.html#cb967-18"></a></span>
<span id="cb967-19"><a href="locale.html#cb967-19"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb967-20"><a href="locale.html#cb967-20"></a><span class="op">{</span></span>
<span id="cb967-21"><a href="locale.html#cb967-21"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb967-22"><a href="locale.html#cb967-22"></a></span>
<span id="cb967-23"><a href="locale.html#cb967-23"></a>    <span class="kw">struct</span> lconv <span class="op">*</span>lc <span class="op">=</span> localeconv<span class="op">();</span></span>
<span id="cb967-24"><a href="locale.html#cb967-24"></a></span>
<span id="cb967-25"><a href="locale.html#cb967-25"></a>    printf<span class="op">(</span><span class="st">"mon_decimal_point : %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>mon_decimal_point<span class="op">);</span></span>
<span id="cb967-26"><a href="locale.html#cb967-26"></a>    printf<span class="op">(</span><span class="st">"mon_thousands_sep : %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>mon_thousands_sep<span class="op">);</span></span>
<span id="cb967-27"><a href="locale.html#cb967-27"></a>    printf<span class="op">(</span><span class="st">"mon_grouping      : "</span><span class="op">);</span></span>
<span id="cb967-28"><a href="locale.html#cb967-28"></a>    print_grouping<span class="op">(</span>lc<span class="op">-&gt;</span>mon_grouping<span class="op">);</span></span>
<span id="cb967-29"><a href="locale.html#cb967-29"></a>    printf<span class="op">(</span><span class="st">"</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb967-30"><a href="locale.html#cb967-30"></a>    printf<span class="op">(</span><span class="st">"positive_sign     : %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>positive_sign<span class="op">);</span></span>
<span id="cb967-31"><a href="locale.html#cb967-31"></a>    printf<span class="op">(</span><span class="st">"negative_sign     : %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>negative_sign<span class="op">);</span></span>
<span id="cb967-32"><a href="locale.html#cb967-32"></a>    printf<span class="op">(</span><span class="st">"currency_symbol   : %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>currency_symbol<span class="op">);</span></span>
<span id="cb967-33"><a href="locale.html#cb967-33"></a>    printf<span class="op">(</span><span class="st">"frac_digits       : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>frac_digits<span class="op">);</span></span>
<span id="cb967-34"><a href="locale.html#cb967-34"></a>    printf<span class="op">(</span><span class="st">"p_cs_precedes     : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>p_cs_precedes<span class="op">);</span></span>
<span id="cb967-35"><a href="locale.html#cb967-35"></a>    printf<span class="op">(</span><span class="st">"n_cs_precedes     : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>n_cs_precedes<span class="op">);</span></span>
<span id="cb967-36"><a href="locale.html#cb967-36"></a>    printf<span class="op">(</span><span class="st">"p_sep_by_space    : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>p_sep_by_space<span class="op">);</span></span>
<span id="cb967-37"><a href="locale.html#cb967-37"></a>    printf<span class="op">(</span><span class="st">"n_sep_by_space    : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>n_sep_by_space<span class="op">);</span></span>
<span id="cb967-38"><a href="locale.html#cb967-38"></a>    printf<span class="op">(</span><span class="st">"p_sign_posn       : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>p_sign_posn<span class="op">);</span></span>
<span id="cb967-39"><a href="locale.html#cb967-39"></a>    printf<span class="op">(</span><span class="st">"p_sign_posn       : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>p_sign_posn<span class="op">);</span></span>
<span id="cb967-40"><a href="locale.html#cb967-40"></a>    printf<span class="op">(</span><span class="st">"int_curr_symbol   : %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_curr_symbol<span class="op">);</span></span>
<span id="cb967-41"><a href="locale.html#cb967-41"></a>    printf<span class="op">(</span><span class="st">"int_frac_digits   : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_frac_digits<span class="op">);</span></span>
<span id="cb967-42"><a href="locale.html#cb967-42"></a>    printf<span class="op">(</span><span class="st">"int_p_cs_precedes : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_p_cs_precedes<span class="op">);</span></span>
<span id="cb967-43"><a href="locale.html#cb967-43"></a>    printf<span class="op">(</span><span class="st">"int_n_cs_precedes : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_n_cs_precedes<span class="op">);</span></span>
<span id="cb967-44"><a href="locale.html#cb967-44"></a>    printf<span class="op">(</span><span class="st">"int_p_sep_by_space: %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_p_sep_by_space<span class="op">);</span></span>
<span id="cb967-45"><a href="locale.html#cb967-45"></a>    printf<span class="op">(</span><span class="st">"int_n_sep_by_space: %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_n_sep_by_space<span class="op">);</span></span>
<span id="cb967-46"><a href="locale.html#cb967-46"></a>    printf<span class="op">(</span><span class="st">"int_p_sign_posn   : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_p_sign_posn<span class="op">);</span></span>
<span id="cb967-47"><a href="locale.html#cb967-47"></a>    printf<span class="op">(</span><span class="st">"int_n_sign_posn   : %c</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lc<span class="op">-&gt;</span>int_n_sign_posn<span class="op">);</span></span>
<span id="cb967-48"><a href="locale.html#cb967-48"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb968"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb968-1"><a href="locale.html#cb968-1" aria-hidden="true" tabindex="-1"></a>mon_decimal_point : .</span>
<span id="cb968-2"><a href="locale.html#cb968-2" aria-hidden="true" tabindex="-1"></a>mon_thousands_sep : ,</span>
<span id="cb968-3"><a href="locale.html#cb968-3" aria-hidden="true" tabindex="-1"></a>mon_grouping      : 3 3 0 </span>
<span id="cb968-4"><a href="locale.html#cb968-4" aria-hidden="true" tabindex="-1"></a>positive_sign     : </span>
<span id="cb968-5"><a href="locale.html#cb968-5" aria-hidden="true" tabindex="-1"></a>negative_sign     : -</span>
<span id="cb968-6"><a href="locale.html#cb968-6" aria-hidden="true" tabindex="-1"></a>currency_symbol   : $</span>
<span id="cb968-7"><a href="locale.html#cb968-7" aria-hidden="true" tabindex="-1"></a>frac_digits       : 2</span>
<span id="cb968-8"><a href="locale.html#cb968-8" aria-hidden="true" tabindex="-1"></a>p_cs_precedes     : 1</span>
<span id="cb968-9"><a href="locale.html#cb968-9" aria-hidden="true" tabindex="-1"></a>n_cs_precedes     : 1</span>
<span id="cb968-10"><a href="locale.html#cb968-10" aria-hidden="true" tabindex="-1"></a>p_sep_by_space    : 0</span>
<span id="cb968-11"><a href="locale.html#cb968-11" aria-hidden="true" tabindex="-1"></a>n_sep_by_space    : 0</span>
<span id="cb968-12"><a href="locale.html#cb968-12" aria-hidden="true" tabindex="-1"></a>p_sign_posn       : 1</span>
<span id="cb968-13"><a href="locale.html#cb968-13" aria-hidden="true" tabindex="-1"></a>p_sign_posn       : 1</span>
<span id="cb968-14"><a href="locale.html#cb968-14" aria-hidden="true" tabindex="-1"></a>int_curr_symbol   : USD </span>
<span id="cb968-15"><a href="locale.html#cb968-15" aria-hidden="true" tabindex="-1"></a>int_frac_digits   : 2</span>
<span id="cb968-16"><a href="locale.html#cb968-16" aria-hidden="true" tabindex="-1"></a>int_p_cs_precedes : 1</span>
<span id="cb968-17"><a href="locale.html#cb968-17" aria-hidden="true" tabindex="-1"></a>int_n_cs_precedes : 1</span>
<span id="cb968-18"><a href="locale.html#cb968-18" aria-hidden="true" tabindex="-1"></a>int_p_sep_by_space: 1</span>
<span id="cb968-19"><a href="locale.html#cb968-19" aria-hidden="true" tabindex="-1"></a>int_n_sep_by_space: 1</span>
<span id="cb968-20"><a href="locale.html#cb968-20" aria-hidden="true" tabindex="-1"></a>int_p_sign_posn   : 1</span>
<span id="cb968-21"><a href="locale.html#cb968-21" aria-hidden="true" tabindex="-1"></a>int_n_sign_posn   : 1</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-49">See Also</h3>
<p><a href="locale.html#man-setlocale"><code>setlocale()</code></a></p>

</body>