<body>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="locale-and-internationalization.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="exiting-a-program.html">Next»</a></div>
<hr>
<h1 data-number="27" id="unicode-wide-characters-and-all-that"><span class="header-section-number">27</span> Unicode, Wide Characters, and
All That</h1>
<p></p>
<p>Before we begin, note that this is an active area of language
development in C as it works to get past some, erm, <em>growing
pains</em>. When C2x comes out, updates here are probable.</p>
<p>Most people are basically interested in the deceptively simple
question, “How do I use such-and-such character set in C?” We’ll get to
that. But as we’ll see, it might already work on your system. Or you
might have to punt to a third-party library.</p>
<p>We’re going to talk about a lot of things this chapter—some are
platform agnostic, and some are C-specific.</p>
<p>Let’s get an outline first of what we’re going to look at:</p>
<ul>
<li>Unicode background</li>
<li>Character encoding background</li>
<li>Source and Execution character Sets</li>
<li>Using Unicode and UTF-8</li>
<li>Using other character types like <code>wchar_t</code>,
<code>char16_t</code>, and <code>char32_t</code></li>
</ul>
<p>Let’s dive in!</p>
<h2 data-number="27.1" id="what-is-unicode"><span class="header-section-number">27.1</span> What is Unicode?</h2>
<p>Back in the day, it was popular in the US and much of the world to
use a 7-bit or 8-bit encoding for characters in memory. This meant we
could have 128 or 256 characters (including non-printable characters)
total. That was fine for a US-centric world, but it turns out there are
actually other alphabets out there—who knew? Chinese has over 50,000
characters, and that’s not fitting in a byte.</p>
<p>So people came up with all kinds of alternate ways to represent their
own custom character sets. And that was fine, but turned into a
compatibility nightmare.</p>
<p>To escape it, Unicode was invented. One character set to rule them
all. It extends off into infinity (effectively) so we’ll never run out
of space for new characters. It has Chinese, Latin, Greek, cuneiform,
chess symbols, emojis… just about everything, really! And more is being
added all the time!</p>
<h2 data-number="27.2" id="code-points"><span class="header-section-number">27.2</span> Code Points</h2>
<p></p>
<p>I want to talk about two concepts here. It’s confusing because
they’re both numbers… different numbers for the same thing. But bear
with me.</p>
<p>Let’s loosely define <em>code point</em> to mean a numeric value
representing a character. (Code points can also represent unprintable
control characters, but just assume I mean something like the letter “B”
or the character “π”.)</p>
<p>Each code point represents a unique character. And each character has
a unique numeric code point associated with it.</p>
<p>For example, in Unicode, the numeric value 66 represents “B”, and 960
represents “π”. Other character mappings that aren’t Unicode use
different values, potentially, but let’s forget them and concentrate on
Unicode, the future!</p>
<p>So that’s one thing: there’s a number that represents each character.
In Unicode, these numbers run from 0 to over 1 million.</p>
<p></p>
<p>Got it?</p>
<p>Because we’re about to flip the table a little.</p>
<h2 data-number="27.3" id="encoding"><span class="header-section-number">27.3</span> Encoding</h2>
<p></p>
<p>If you recall, an 8-bit byte can hold values from 0-255, inclusive.
That’s great for “B” which is 66—that fits in a byte. But “π” is 960,
and that doesn’t fit in a byte! We need another byte. How do we store
all that in memory? Or what about bigger numbers, like 195,024? That’s
going to need a number of bytes to hold.</p>
<p>The Big Question: how are these numbers represented in memory? This
is what we call the <em>encoding</em> of the characters.</p>
<p>So we have two things: one is the code point which tells us
effectively the serial number of a particular character. And we have the
encoding which tells us how we’re going to represent that number in
memory.</p>
<p>There are plenty of encodings. You can make up your own right now, if
you want<a href="footnotes.html#fn146" class="footnote-ref" id="fnref146" role="doc-noteref"><sup>146</sup></a>. But we’re going to look at some
really common encodings that are in use with Unicode.</p>
<p> </p>
<table>
<colgroup>
<col style="width: 23%">
<col style="width: 76%">
</colgroup>
<thead>
<tr class="header">
<th style="text-align: center;">Encoding</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;">UTF-8</td>
<td style="text-align: left;">A byte-oriented encoding that uses a
variable number of bytes per character. This is the one to use.</td>
</tr>
<tr class="even">
<td style="text-align: center;">UTF-16</td>
<td style="text-align: left;">A 16-bit per character<a href="footnotes.html#fn147" class="footnote-ref" id="fnref147" role="doc-noteref"><sup>147</sup></a>
encoding.</td>
</tr>
<tr class="odd">
<td style="text-align: center;">UTF-32</td>
<td style="text-align: left;">A 32-bit per character encoding.</td>
</tr>
</tbody>
</table>
<p>With UTF-16 and UTF-32, the byte order matters, so you might see
UTF-16BE for big-endian and UTF-16LE for little-endian. Same for UTF-32.
Technically, if unspecified, you should assume big-endian. But since
Windows uses UTF-16 extensively and is little-endian, sometimes that is
assumed<a href="footnotes.html#fn148" class="footnote-ref" id="fnref148" role="doc-noteref"><sup>148</sup></a>.</p>
<p>Let’s look at some examples. I’m going to write the values in hex
because that’s exactly two digits per 8-bit byte, and it makes it easier
to see how things are arranged in memory.</p>
<table>
<thead>
<tr class="header">
<th style="text-align: center;">Character</th>
<th style="text-align: center;">Code Point</th>
<th style="text-align: center;">UTF-16BE</th>
<th style="text-align: center;">UTF-32BE</th>
<th style="text-align: center;">UTF-16LE</th>
<th style="text-align: center;">UTF-32LE</th>
<th style="text-align: center;">UTF-8</th>
<th style="text-align: center;"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>A</code></td>
<td style="text-align: center;">41</td>
<td style="text-align: center;">0041</td>
<td style="text-align: center;">00000041</td>
<td style="text-align: center;">4100</td>
<td style="text-align: center;">41000000</td>
<td style="text-align: center;">41</td>
<td style="text-align: center;"></td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>B</code></td>
<td style="text-align: center;">42</td>
<td style="text-align: center;">0042</td>
<td style="text-align: center;">00000042</td>
<td style="text-align: center;">4200</td>
<td style="text-align: center;">42000000</td>
<td style="text-align: center;">42</td>
<td style="text-align: center;"></td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>~</code></td>
<td style="text-align: center;">7E</td>
<td style="text-align: center;">007E</td>
<td style="text-align: center;">0000007E</td>
<td style="text-align: center;">7E00</td>
<td style="text-align: center;">7E000000</td>
<td style="text-align: center;">7E</td>
<td style="text-align: center;"></td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>π</code></td>
<td style="text-align: center;">3C0</td>
<td style="text-align: center;">03C0</td>
<td style="text-align: center;">000003C0</td>
<td style="text-align: center;">C003</td>
<td style="text-align: center;">C0030000</td>
<td style="text-align: center;">CF80</td>
<td style="text-align: center;"></td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>€</code></td>
<td style="text-align: center;">20AC</td>
<td style="text-align: center;">20AC</td>
<td style="text-align: center;">000020AC</td>
<td style="text-align: center;">AC20</td>
<td style="text-align: center;">AC200000</td>
<td style="text-align: center;">E282AC</td>
<td style="text-align: center;"></td>
</tr>
</tbody>
</table>
<p></p>
<p>Look in there for the patterns. Note that UTF-16BE and UTF-32BE are
simply the code point represented directly as 16- and 32-bit values<a href="#fn149" class="footnote-ref" id="fnref149" role="doc-noteref"><sup>149</sup></a>.</p>
<p> </p>
<p>Little-endian is the same, except the bytes are in little-endian
order.</p>
<p></p>
<p>Then we have UTF-8 at the end. First you might notice that the
single-byte code points are represented as a single byte. That’s nice.
You might also notice that different code points take different number
of bytes. This is a variable-width encoding.</p>
<p>So as soon as we get above a certain value, UTF-8 starts using
additional bytes to store the values. And they don’t appear to correlate
with the code point value, either.</p>
<p><a href="https://en.wikipedia.org/wiki/UTF-8">The details of UTF-8
encoding</a><a href="footnotes.html#fn150" class="footnote-ref" id="fnref150" role="doc-noteref"><sup>150</sup></a> are beyond the scope of this
guide, but it’s enough to know that it has a variable number of bytes
per code point, and those byte values don’t match up with the code point
<em>except for the first 128 code points</em>. If you really want to
learn more, <a href="https://www.youtube.com/watch?v=MijmeoH9LT4">Computerphile has a
great UTF-8 video with Tom Scott</a><a href="footnotes.html#fn151" class="footnote-ref" id="fnref151" role="doc-noteref"><sup>151</sup></a>.</p>
<p>That last bit is a neat thing about Unicode and UTF-8 from a North
American perspective: it’s backward compatible with 7-bit ASCII
encoding! So if you’re used to ASCII, UTF-8 is the same! Every
ASCII-encoded document is also UTF-8 encoded! (But not the other way
around, obviously.)</p>
<p>It’s probably that last point more than any other that is driving
UTF-8 to take over the world.</p>
<p> </p>
<h2 data-number="27.4" id="src-exec-charset"><span class="header-section-number">27.4</span> Source and Execution Character
Sets</h2>
<p></p>
<p>When programming in C, there are (at least) three character sets that
are in play:</p>
<ul>
<li>The one that your code exists on disk as.</li>
<li>The one the compiler translates that into just as compilation begins
(the <em>source character set</em>). This might be the same as the one
on disk, or it might not.</li>
<li>The one the compiler translates the source character set into for
execution (the <em>execution character set</em>). This might be the same
as the source character set, or it might not.</li>
</ul>
<p>Your compiler probably has options to select these character sets at
build-time.</p>
<p></p>
<p>The basic character set for both source and execution will contain
the following characters:</p>
<div class="sourceCode" id="cb528"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb528-1"><a href="unicode-wide-characters-and-all-that.html#cb528-1" aria-hidden="true" tabindex="-1"></a>A B C D E F G H I J K L M</span>
<span id="cb528-2"><a href="unicode-wide-characters-and-all-that.html#cb528-2" aria-hidden="true" tabindex="-1"></a>N O P Q R S T U V W X Y Z</span>
<span id="cb528-3"><a href="unicode-wide-characters-and-all-that.html#cb528-3" aria-hidden="true" tabindex="-1"></a>a b c d e f g h i j k l m</span>
<span id="cb528-4"><a href="unicode-wide-characters-and-all-that.html#cb528-4" aria-hidden="true" tabindex="-1"></a>n o p q r s t u v w x y z</span>
<span id="cb528-5"><a href="unicode-wide-characters-and-all-that.html#cb528-5" aria-hidden="true" tabindex="-1"></a>0 1 2 3 4 5 6 7 8 9</span>
<span id="cb528-6"><a href="unicode-wide-characters-and-all-that.html#cb528-6" aria-hidden="true" tabindex="-1"></a>! " # % &amp; ' ( ) * + , - . / :</span>
<span id="cb528-7"><a href="unicode-wide-characters-and-all-that.html#cb528-7" aria-hidden="true" tabindex="-1"></a>; &lt; = &gt; ? [ \ ] ^ _ { | } ~</span>
<span id="cb528-8"><a href="unicode-wide-characters-and-all-that.html#cb528-8" aria-hidden="true" tabindex="-1"></a>space tab vertical-tab</span>
<span id="cb528-9"><a href="unicode-wide-characters-and-all-that.html#cb528-9" aria-hidden="true" tabindex="-1"></a>form-feed end-of-line</span></code></pre></div>
<p>Those are the characters you can use in your source and remain 100%
portable.</p>
<p>The execution character set will additionally have characters for
alert (bell/flash), backspace, carriage return, and newline.</p>
<p>But most people don’t go to that extreme and freely use their
extended character sets in source and executable, especially now that
Unicode and UTF-8 are getting more common. I mean, the basic character
set doesn’t even allow for <code>@</code>, <code>$</code>, or
<code>`</code>!</p>
<p>Notably, it’s a pain (though possible with escape sequences) to enter
Unicode characters using only the basic character set.</p>
<p> </p>
<h2 data-number="27.5" id="unicode-in-c"><span class="header-section-number">27.5</span> Unicode in C</h2>
<p>Before I get into encoding in C, let’s talk about Unicode from a code
point standpoint. There is a way in C to specify Unicode characters and
these will get translated by the compiler into the execution character
set<a href="footnotes.html#fn152" class="footnote-ref" id="fnref152" role="doc-noteref"><sup>152</sup></a>.</p>
<p>So how do we do it?</p>
<p>How about the euro symbol, code point 0x20AC. (I’ve written it in hex
because both ways of representing it in C require hex.) How can we put
that in our C code?</p>
<p> Use the <code>\u</code> escape to put it in a string,
e.g.&nbsp;<code>"\u20AC"</code> (case for the hex doesn’t matter). You must
put <strong>exactly four</strong> hex digits after the <code>\u</code>,
padding with leading zeros if necessary.</p>
<p>Here’s an example:</p>
<div class="sourceCode" id="cb529"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb529-1"><a href="unicode-wide-characters-and-all-that.html#cb529-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"\u20AC1.23"</span><span class="op">;</span></span>
<span id="cb529-2"><a href="unicode-wide-characters-and-all-that.html#cb529-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb529-3"><a href="unicode-wide-characters-and-all-that.html#cb529-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>  <span class="co">// €1.23</span></span></code></pre></div>
<p></p>
<p>So <code>\u</code> works for 16-bit Unicode code points, but what
about ones bigger than 16 bits? For that, we need capitals:
<code>\U</code>.</p>
<p>For example:</p>
<div class="sourceCode" id="cb530"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb530-1"><a href="unicode-wide-characters-and-all-that.html#cb530-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"\U0001D4D1"</span><span class="op">;</span></span>
<span id="cb530-2"><a href="unicode-wide-characters-and-all-that.html#cb530-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb530-3"><a href="unicode-wide-characters-and-all-that.html#cb530-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>  <span class="co">// Prints a mathematical letter "B"</span></span></code></pre></div>
<p>It’s the same as <code>\u</code>, just with 32 bits instead of 16.
These are equivalent:</p>
<div class="sourceCode" id="cb531"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb531-1"><a href="unicode-wide-characters-and-all-that.html#cb531-1" aria-hidden="true" tabindex="-1"></a>\u03C0</span>
<span id="cb531-2"><a href="unicode-wide-characters-and-all-that.html#cb531-2" aria-hidden="true" tabindex="-1"></a>\U000003C0</span></code></pre></div>
<p> </p>
<p>Again, these are translated into the execution character set during
compilation. They represent Unicode code points, not any specific
encoding. Furthermore, if a Unicode code point is not representable in
the execution character set, the compiler can do whatever it wants with
it.</p>
<p>Now, you might wonder why you can’t just do this:</p>
<div class="sourceCode" id="cb532"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb532-1"><a href="unicode-wide-characters-and-all-that.html#cb532-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"€1.23"</span><span class="op">;</span></span>
<span id="cb532-2"><a href="unicode-wide-characters-and-all-that.html#cb532-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb532-3"><a href="unicode-wide-characters-and-all-that.html#cb532-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>  <span class="co">// €1.23</span></span></code></pre></div>
<p>And you probably can, given a modern compiler. The source character
set will be translated for you into the execution character set by the
compiler. But compilers are free to puke out if they find any characters
that aren’t included in their extended character set, and the € symbol
certainly isn’t in the basic character set.</p>
<p> </p>
<p>Caveat from the spec: you can’t use <code>\u</code> or
<code>\U</code> to encode any code points below 0xA0 except for 0x24
(<code>$</code>), 0x40 (<code>@</code>), and 0x60 (<code>`</code>)—yes,
those are precisely the trio of common punctuation marks missing from
the basic character set. Apparently this restriction is relaxed in the
upcoming version of the spec.</p>
<p> </p>
<p>Finally, you can also use these in identifiers in your code, with
some restrictions. But I don’t want to get into that here. We’re all
about string handling in this chapter.</p>
<p>And that’s about it for Unicode in C (except encoding).</p>
<h2 data-number="27.6" id="utf8-quick"><span class="header-section-number">27.6</span> A Quick Note on UTF-8 Before
We Swerve into the Weeds</h2>
<p></p>
<p>It could be that your source file on disk, the extended source
characters, and the extended execution characters are all in UTF-8
format. And the libraries you use expect UTF-8. This is the glorious
future of UTF-8 everywhere.</p>
<p>If that’s the case, and you don’t mind being non-portable to systems
that aren’t like that, then just run with it. Stick Unicode characters
in your source and data at will. Use regular C strings and be happy.</p>
<p>A lot of things will just work (albeit non-portably) because UTF-8
strings can safely be NUL-terminated just like any other C string. But
maybe losing portability in exchange for easier character handling is a
tradeoff that’s worth it to you.</p>
<p>There are some caveats, however:</p>
<ul>
<li><p>Things like <code>strlen()</code> report the number of bytes in a
string, not the number of characters, necessarily. (The
<code>mbstowcs()</code> returns the number of characters in a string
when you convert it to wide characters. POSIX extends this so you can
pass <code>NULL</code> for the first argument if you just want the
character count.)</p></li>
<li><p>The following won’t work properly with characters of more than
one byte: <code>strtok()</code>, <code>strchr()</code> (use
<code>strstr()</code> instead), <code>strspn()</code>-type functions,
<code>toupper()</code>, <code>tolower()</code>,
<code>isalpha()</code>-type functions, and probably more. Beware
anything that operates on bytes.</p></li>
<li><p><code>printf()</code> variants allow for a way to only print so
many bytes of a string<a href="footnotes.html#fn153" class="footnote-ref" id="fnref153" role="doc-noteref"><sup>153</sup></a>. You want to make
certain you print the correct number of bytes to end on a character
boundary.</p></li>
<li><p>If you want to <code>malloc()</code> space for a string, or
declare an array of <code>char</code>s for one, be aware that the
maximum size could be more than you were expecting. Each character could
take up to <code>MB_LEN_MAX</code> bytes (from
<code>&lt;limits.h&gt;</code>)—except characters in the basic character
set which are guaranteed to be one byte.</p></li>
</ul>
<p>And probably others I haven’t discovered. Let me know what pitfalls
there are out there…</p>
<p></p>
<h2 data-number="27.7" id="different-character-types"><span class="header-section-number">27.7</span> Different Character Types</h2>
<p>I want to introduce more character types. We’re used to
<code>char</code>, right?</p>
<p>But that’s too easy. Let’s make things a lot more difficult! Yay!</p>
<h3 data-number="27.7.1" id="multibyte-characters"><span class="header-section-number">27.7.1</span> Multibyte Characters</h3>
<p></p>
<p>First of all, I want to potentially change your thinking about what a
string (array of <code>char</code>s) is. These are <em>multibyte
strings</em> made up of <em>multibyte characters</em>.</p>
<p>That’s right—your run-of-the-mill string of characters is multibyte.
When someone says “C string”, they mean “C multibyte string”.</p>
<p>Even if a particular character in the string is only a single byte,
or if a string is made up of only single characters, it’s known as a
multibyte string.</p>
<p>For example:</p>
<div class="sourceCode" id="cb533"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb533-1"><a href="unicode-wide-characters-and-all-that.html#cb533-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> c<span class="op">[</span><span class="dv">128</span><span class="op">]</span> <span class="op">=</span> <span class="st">"Hello, world!"</span><span class="op">;</span>  <span class="co">// Multibyte string</span></span></code></pre></div>
<p>What we’re saying here is that a particular character that’s not in
the basic character set could be composed of multiple bytes. Up to
<code>MB_LEN_MAX</code> of them (from <code>&lt;limits.h&gt;</code>).
Sure, it only looks like one character on the screen, but it could be
multiple bytes.</p>
<p>You can throw Unicode values in there, as well, as we saw
earlier:</p>
<div class="sourceCode" id="cb534"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb534-1"><a href="unicode-wide-characters-and-all-that.html#cb534-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"\u20AC1.23"</span><span class="op">;</span></span>
<span id="cb534-2"><a href="unicode-wide-characters-and-all-that.html#cb534-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb534-3"><a href="unicode-wide-characters-and-all-that.html#cb534-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>  <span class="co">// €1.23</span></span></code></pre></div>
<p>But here we’re getting into some weirdness, because check this
out:</p>
<p></p>
<div class="sourceCode" id="cb535"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb535-1"><a href="unicode-wide-characters-and-all-that.html#cb535-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> <span class="st">"\u20AC1.23"</span><span class="op">;</span>  <span class="co">// €1.23</span></span>
<span id="cb535-2"><a href="unicode-wide-characters-and-all-that.html#cb535-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb535-3"><a href="unicode-wide-characters-and-all-that.html#cb535-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> strlen<span class="op">(</span>s<span class="op">));</span>  <span class="co">// 7!</span></span></code></pre></div>
<p>The string length of <code>"€1.23"</code> is <code>7</code>?! Yes!
Well, on my system, yes! Remember that <code>strlen()</code> returns the
number of bytes in the string, not the number of characters. (When we
get to “wide characters”, coming up, we’ll see a way to get the number
of characters in the string.)</p>
<p></p>
<p>Note that while C allows individual multibyte <code>char</code>
constants (as opposed to <code>char*</code>), the behavior of these
varies by implementation and your compiler might warn on it.</p>
<p>GCC, for example, warns of multi-character character constants for
the following two lines (and, on my system, prints out the UTF-8
encoding):</p>
<div class="sourceCode" id="cb536"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb536-1"><a href="unicode-wide-characters-and-all-that.html#cb536-1" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> '€'<span class="op">);</span></span>
<span id="cb536-2"><a href="unicode-wide-characters-and-all-that.html#cb536-2" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%x</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> '\u20ac'<span class="op">);</span></span></code></pre></div>
<p></p>
<h3 data-number="27.7.2" id="wide-characters"><span class="header-section-number">27.7.2</span> Wide Characters</h3>
<p></p>
<p>If you’re not a multibyte character, then you’re a <em>wide
character</em>.</p>
<p>A wide character is a single value that can uniquely represent any
character in the current locale. It’s analogous to Unicode code points.
But it might not be. Or it might be.</p>
<p>Basically, where multibyte character strings are arrays of bytes,
wide character strings are arrays of <em>characters</em>. So you can
start thinking on a character-by-character basis rather than a
byte-by-byte basis (the latter of which gets all messy when characters
start taking up variable numbers of bytes).</p>
<p></p>
<p>Wide characters can be represented by a number of types, but the big
standout one is <code>wchar_t</code>. It’s the main one. It’s like
<code>char</code>, except wide.</p>
<p>You might be wondering if you can’t tell if it’s Unicode or not, how
does that allow you much flexibility in terms of writing code?
<code>wchar_t</code> opens some of those doors, as there are a rich set
of functions you can use to deal with <code>wchar_t</code> strings (like
getting the length, etc.) without caring about the encoding.</p>
<h2 data-number="27.8" id="using-wide-characters-and-wchar_t"><span class="header-section-number">27.8</span> Using Wide Characters and
<code>wchar_t</code></h2>
<p>Time for a new type: <code>wchar_t</code>. This is the main wide
character type. Remember how a <code>char</code> is only one byte? And a
byte’s not enough to represent all characters, potentially? Well, this
one is enough.</p>
<p>To use <code>wchar_t</code>, include
<code>&lt;wchar.h&gt;</code>.</p>
<p>How many bytes big is it? Well, it’s not totally clear. Could be 16
bits. Could be 32 bits.</p>
<p>But wait, you’re saying—if it’s only 16 bits, it’s not big enough to
hold all the Unicode code points, is it? You’re right—it’s not. The spec
doesn’t require it to be. It just has to be able to represent all the
characters in the current locale.</p>
<p>This can cause grief with Unicode on platforms with 16-bit
<code>wchar_t</code>s (ahem—Windows). But that’s out of scope for this
guide.</p>
<p></p>
<p>You can declare a string or character of this type with the
<code>L</code> prefix, and you can print them with the <code>%ls</code>
(“ell ess”) format specifier. Or print an individual
<code>wchar_t</code> with <code>%lc</code>.</p>
<div class="sourceCode" id="cb537"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb537-1"><a href="unicode-wide-characters-and-all-that.html#cb537-1" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> <span class="op">*</span>s <span class="op">=</span> L<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb537-2"><a href="unicode-wide-characters-and-all-that.html#cb537-2" aria-hidden="true" tabindex="-1"></a><span class="dt">wchar_t</span> c <span class="op">=</span> L<span class="ch">'B'</span><span class="op">;</span></span>
<span id="cb537-3"><a href="unicode-wide-characters-and-all-that.html#cb537-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb537-4"><a href="unicode-wide-characters-and-all-that.html#cb537-4" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%ls %lc</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">,</span> c<span class="op">);</span></span></code></pre></div>
<p></p>
<p>Now—are those characters stored as Unicode code points, or not?
Depends on the implementation. But you can test if they are with the
macro <code>__STDC_ISO_10646__</code>. If this is defined, the answer
is, “It’s Unicode!”</p>
<p>More detailedly, the value in that macro is an integer in the form
<code>yyyymm</code> that lets you know what Unicode standard you can
rely on—whatever was in effect on that date.</p>
<p>But how do you use them?</p>
<h3 data-number="27.8.1" id="multibyte-to-wchar_t-conversions"><span class="header-section-number">27.8.1</span> Multibyte to
<code>wchar_t</code> Conversions</h3>
<p>So how do we get from the byte-oriented standard strings to the
character-oriented wide strings and back?</p>
<p>We can use a couple string conversion functions to make this
happen.</p>
<p>First, some naming conventions you’ll see in these functions:</p>
<ul>
<li><code>mb</code>: multibyte</li>
<li><code>wc</code>: wide character</li>
<li><code>mbs</code>: multibyte string</li>
<li><code>wcs</code>: wide character string</li>
</ul>
<p>So if we want to convert a multibyte string to a wide character
string, we can call the <code>mbstowcs()</code>. And the other way
around: <code>wcstombs()</code>.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Conversion Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>mbtowc()</code></td>
<td>Convert a multibyte character to a wide character.</td>
</tr>
<tr class="even">
<td><code>wctomb()</code></td>
<td>Convert a wide character to a multibyte character.</td>
</tr>
<tr class="odd">
<td><code>mbstowcs()</code></td>
<td>Convert a multibyte string to a wide string.</td>
</tr>
<tr class="even">
<td><code>wcstombs()</code></td>
<td>Convert a wide string to a multibyte string.</td>
</tr>
</tbody>
</table>
<p>Let’s do a quick demo where we convert a multibyte string to a wide
character string, and compare the string lengths of the two using their
respective functions.</p>
<p></p>
<div class="sourceCode" id="cb538"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb538-1"><a href="unicode-wide-characters-and-all-that.html#cb538-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb538-2"><a href="unicode-wide-characters-and-all-that.html#cb538-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb538-3"><a href="unicode-wide-characters-and-all-that.html#cb538-3"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb538-4"><a href="unicode-wide-characters-and-all-that.html#cb538-4"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb538-5"><a href="unicode-wide-characters-and-all-that.html#cb538-5"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb538-6"><a href="unicode-wide-characters-and-all-that.html#cb538-6"></a></span>
<span id="cb538-7"><a href="unicode-wide-characters-and-all-that.html#cb538-7"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb538-8"><a href="unicode-wide-characters-and-all-that.html#cb538-8"></a><span class="op">{</span></span>
<span id="cb538-9"><a href="unicode-wide-characters-and-all-that.html#cb538-9"></a>    <span class="co">// Get out of the C locale to one that likely has the euro symbol</span></span>
<span id="cb538-10"><a href="unicode-wide-characters-and-all-that.html#cb538-10"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb538-11"><a href="unicode-wide-characters-and-all-that.html#cb538-11"></a></span>
<span id="cb538-12"><a href="unicode-wide-characters-and-all-that.html#cb538-12"></a>    <span class="co">// Original multibyte string with a euro symbol (Unicode point 20ac)</span></span>
<span id="cb538-13"><a href="unicode-wide-characters-and-all-that.html#cb538-13"></a>    <span class="dt">char</span> <span class="op">*</span>mb_string <span class="op">=</span> <span class="st">"The cost is \u20ac1.23"</span><span class="op">;</span>  <span class="co">// €1.23</span></span>
<span id="cb538-14"><a href="unicode-wide-characters-and-all-that.html#cb538-14"></a>    <span class="dt">size_t</span> mb_len <span class="op">=</span> strlen<span class="op">(</span>mb_string<span class="op">);</span></span>
<span id="cb538-15"><a href="unicode-wide-characters-and-all-that.html#cb538-15"></a></span>
<span id="cb538-16"><a href="unicode-wide-characters-and-all-that.html#cb538-16"></a>    <span class="co">// Wide character array that will hold the converted string</span></span>
<span id="cb538-17"><a href="unicode-wide-characters-and-all-that.html#cb538-17"></a>    <span class="dt">wchar_t</span> wc_string<span class="op">[</span><span class="dv">128</span><span class="op">];</span>  <span class="co">// Holds up to 128 wide characters</span></span>
<span id="cb538-18"><a href="unicode-wide-characters-and-all-that.html#cb538-18"></a></span>
<span id="cb538-19"><a href="unicode-wide-characters-and-all-that.html#cb538-19"></a>    <span class="co">// Convert the MB string to WC; this returns the number of wide chars</span></span>
<span id="cb538-20"><a href="unicode-wide-characters-and-all-that.html#cb538-20"></a>    <span class="dt">size_t</span> wc_len <span class="op">=</span> mbstowcs<span class="op">(</span>wc_string<span class="op">,</span> mb_string<span class="op">,</span> <span class="dv">128</span><span class="op">);</span></span>
<span id="cb538-21"><a href="unicode-wide-characters-and-all-that.html#cb538-21"></a></span>
<span id="cb538-22"><a href="unicode-wide-characters-and-all-that.html#cb538-22"></a>    <span class="co">// Print result--note the %ls for wide char strings</span></span>
<span id="cb538-23"><a href="unicode-wide-characters-and-all-that.html#cb538-23"></a>    printf<span class="op">(</span><span class="st">"multibyte: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"</span><span class="st"> (%zu bytes)</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mb_string<span class="op">,</span> mb_len<span class="op">);</span></span>
<span id="cb538-24"><a href="unicode-wide-characters-and-all-that.html#cb538-24"></a>    printf<span class="op">(</span><span class="st">"wide char: </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"</span><span class="st"> (%zu characters)</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wc_string<span class="op">,</span> wc_len<span class="op">);</span></span>
<span id="cb538-25"><a href="unicode-wide-characters-and-all-that.html#cb538-25"></a><span class="op">}</span></span></code></pre></div>
<p></p>
<p>On my system, this outputs:</p>
<div class="sourceCode" id="cb539"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb539-1"><a href="unicode-wide-characters-and-all-that.html#cb539-1" aria-hidden="true" tabindex="-1"></a>multibyte: "The cost is €1.23" (19 bytes)</span>
<span id="cb539-2"><a href="unicode-wide-characters-and-all-that.html#cb539-2" aria-hidden="true" tabindex="-1"></a>wide char: "The cost is €1.23" (17 characters)</span></code></pre></div>
<p>(Your system might vary on the number of bytes depending on your
locale.)</p>
<p>One interesting thing to note is that <code>mbstowcs()</code>, in
addition to converting the multibyte string to wide, returns the length
(in characters) of the wide character string. On POSIX-compliant
systems, you can take advantage of a special mode where it <em>only</em>
returns the length-in-characters of a given multibyte string: you just
pass <code>NULL</code> to the destination, and <code>0</code> to the
maximum number of characters to convert (this value is ignored).</p>
<p>(In the code below, I’m using my extended source character set—you
might have to replace those with <code>\u</code> escapes.)</p>
<div class="sourceCode" id="cb540"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb540-1"><a href="unicode-wide-characters-and-all-that.html#cb540-1" aria-hidden="true" tabindex="-1"></a>setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb540-2"><a href="unicode-wide-characters-and-all-that.html#cb540-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb540-3"><a href="unicode-wide-characters-and-all-that.html#cb540-3" aria-hidden="true" tabindex="-1"></a><span class="co">// The following string has 7 characters</span></span>
<span id="cb540-4"><a href="unicode-wide-characters-and-all-that.html#cb540-4" aria-hidden="true" tabindex="-1"></a><span class="dt">size_t</span> len_in_chars <span class="op">=</span> mbstowcs<span class="op">(</span>NULL<span class="op">,</span> <span class="st">"§¶°±π€•"</span><span class="op">,</span> <span class="dv">0</span><span class="op">);</span></span>
<span id="cb540-5"><a href="unicode-wide-characters-and-all-that.html#cb540-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb540-6"><a href="unicode-wide-characters-and-all-that.html#cb540-6" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%zu"</span><span class="op">,</span> len_in_chars<span class="op">);</span>  <span class="co">// 7</span></span></code></pre></div>
<p></p>
<p>Again, that’s a non-portable POSIX extension.</p>
<p>And, of course, if you want to convert the other way, it’s
<code>wcstombs()</code>.</p>
<h2 data-number="27.9" id="wide-character-functionality"><span class="header-section-number">27.9</span> Wide Character
Functionality</h2>
<p>Once we’re in wide character land, we have all kinds of functionality
at our disposal. I’m just going to summarize a bunch of the functions
here, but basically what we have here are the wide character versions of
the multibyte string functions that we’re use to. (For example, we know
<code>strlen()</code> for multibyte strings; there’s a
<code>wcslen()</code> for wide character strings.)</p>
<h3 data-number="27.9.1" id="wint_t"><span class="header-section-number">27.9.1</span> <code>wint_t</code></h3>
<p></p>
<p>A lot of these functions use a <code>wint_t</code> to hold single
characters, whether they are passed in or returned.</p>
<p>It is related to <code>wchar_t</code> in nature. A
<code>wint_t</code> is an integer that can represent all values in the
extended character set, and also a special end-of-file character,
<code>WEOF</code>.</p>
<p></p>
<p>This is used by a number of single-character-oriented wide character
functions.</p>
<h3 data-number="27.9.2" id="io-stream-orientation"><span class="header-section-number">27.9.2</span> I/O Stream Orientation</h3>
<p></p>
<p>The tl;dr here is to not mix and match byte-oriented functions (like
<code>fprintf()</code>) with wide-oriented functions (like
<code>fwprintf()</code>). Decide if a stream will be byte-oriented or
wide-oriented and stick with those types of I/O functions.</p>
<p>In more detail: streams can be either byte-oriented or wide-oriented.
When a stream is first created, it has no orientation, but the first
read or write will set the orientation.</p>
<p>If you first use a wide operation (like <code>fwprintf()</code>) it
will orient the stream wide.</p>
<p>If you first use a byte operation (like <code>fprintf()</code>) it
will orient the stream by bytes.</p>
<p>You can manually set an unoriented stream one way or the other with a
call to <code>fwide()</code>. You can use that same function to get the
orientation of a stream.</p>
<p>If you need to change the orientation mid-flight, you can do it with
<code>freopen()</code>.</p>
<p></p>
<h3 data-number="27.9.3" id="io-functions"><span class="header-section-number">27.9.3</span> I/O Functions</h3>
<p>Typically include <code>&lt;stdio.h&gt;</code> and
<code>&lt;wchar.h&gt;</code> for these.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>I/O Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>wprintf()</code></td>
<td>Formatted console output.</td>
</tr>
<tr class="even">
<td><code>wscanf()</code></td>
<td>Formatted console input.</td>
</tr>
<tr class="odd">
<td><code>getwchar()</code></td>
<td>Character-based console input.</td>
</tr>
<tr class="even">
<td><code>putwchar()</code></td>
<td>Character-based console output.</td>
</tr>
<tr class="odd">
<td><code>fwprintf()</code></td>
<td>Formatted file output.</td>
</tr>
<tr class="even">
<td><code>fwscanf()</code></td>
<td>Formatted file input.</td>
</tr>
<tr class="odd">
<td><code>fgetwc()</code></td>
<td>Character-based file input.</td>
</tr>
<tr class="even">
<td><code>fputwc()</code></td>
<td>Character-based file output.</td>
</tr>
<tr class="odd">
<td><code>fgetws()</code></td>
<td>String-based file input.</td>
</tr>
<tr class="even">
<td><code>fputws()</code></td>
<td>String-based file output.</td>
</tr>
<tr class="odd">
<td><code>swprintf()</code></td>
<td>Formatted string output.</td>
</tr>
<tr class="even">
<td><code>swscanf()</code></td>
<td>Formatted string input.</td>
</tr>
<tr class="odd">
<td><code>vfwprintf()</code></td>
<td>Variadic formatted file output.</td>
</tr>
<tr class="even">
<td><code>vfwscanf()</code></td>
<td>Variadic formatted file input.</td>
</tr>
<tr class="odd">
<td><code>vswprintf()</code></td>
<td>Variadic formatted string output.</td>
</tr>
<tr class="even">
<td><code>vswscanf()</code></td>
<td>Variadic formatted string input.</td>
</tr>
<tr class="odd">
<td><code>vwprintf()</code></td>
<td>Variadic formatted console output.</td>
</tr>
<tr class="even">
<td><code>vwscanf()</code></td>
<td>Variadic formatted console input.</td>
</tr>
<tr class="odd">
<td><code>ungetwc()</code></td>
<td>Push a wide character back on an output stream.</td>
</tr>
<tr class="even">
<td><code>fwide()</code></td>
<td>Get or set stream multibyte/wide orientation.</td>
</tr>
</tbody>
</table>
<h3 data-number="27.9.4" id="type-conversion-functions"><span class="header-section-number">27.9.4</span> Type Conversion
Functions</h3>
<p>Typically include <code>&lt;wchar.h&gt;</code> for these.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Conversion Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>wcstod()</code></td>
<td>Convert string to <code>double</code>.</td>
</tr>
<tr class="even">
<td><code>wcstof()</code></td>
<td>Convert string to <code>float</code>.</td>
</tr>
<tr class="odd">
<td><code>wcstold()</code></td>
<td>Convert string to <code>long double</code>.</td>
</tr>
<tr class="even">
<td><code>wcstol()</code></td>
<td>Convert string to <code>long</code>.</td>
</tr>
<tr class="odd">
<td><code>wcstoll()</code></td>
<td>Convert string to <code>long long</code>.</td>
</tr>
<tr class="even">
<td><code>wcstoul()</code></td>
<td>Convert string to <code>unsigned long</code>.</td>
</tr>
<tr class="odd">
<td><code>wcstoull()</code></td>
<td>Convert string to <code>unsigned long long</code>.</td>
</tr>
</tbody>
</table>
<h3 data-number="27.9.5" id="string-and-memory-copying-functions"><span class="header-section-number">27.9.5</span> String and Memory Copying
Functions</h3>
<p>Typically include <code>&lt;wchar.h&gt;</code> for these.</p>
<table>
<colgroup>
<col style="width: 8%">
<col style="width: 92%">
</colgroup>
<thead>
<tr class="header">
<th>Copying Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>wcscpy()</code></td>
<td>Copy string.</td>
</tr>
<tr class="even">
<td><code>wcsncpy()</code></td>
<td>Copy string, length-limited.</td>
</tr>
<tr class="odd">
<td><code>wmemcpy()</code></td>
<td>Copy memory.</td>
</tr>
<tr class="even">
<td><code>wmemmove()</code></td>
<td>Copy potentially-overlapping memory.</td>
</tr>
<tr class="odd">
<td><code>wcscat()</code></td>
<td>Concatenate strings.</td>
</tr>
<tr class="even">
<td><code>wcsncat()</code></td>
<td>Concatenate strings, length-limited.</td>
</tr>
</tbody>
</table>
<h3 data-number="27.9.6" id="string-and-memory-comparing-functions"><span class="header-section-number">27.9.6</span> String and Memory Comparing
Functions</h3>
<p>Typically include <code>&lt;wchar.h&gt;</code> for these.</p>
<table>
<colgroup>
<col style="width: 23%">
<col style="width: 76%">
</colgroup>
<thead>
<tr class="header">
<th>Comparing Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>wcscmp()</code></td>
<td>Compare strings lexicographically.</td>
</tr>
<tr class="even">
<td><code>wcsncmp()</code></td>
<td>Compare strings lexicographically, length-limited.</td>
</tr>
<tr class="odd">
<td><code>wcscoll()</code></td>
<td>Compare strings in dictionary order by locale.</td>
</tr>
<tr class="even">
<td><code>wmemcmp()</code></td>
<td>Compare memory lexicographically.</td>
</tr>
<tr class="odd">
<td><code>wcsxfrm()</code></td>
<td>Transform strings into versions such that <code>wcscmp()</code>
behaves like <code>wcscoll()</code><a href="footnotes.html#fn154" class="footnote-ref" id="fnref154" role="doc-noteref"><sup>154</sup></a>.</td>
</tr>
</tbody>
</table>
<h3 data-number="27.9.7" id="string-searching-functions"><span class="header-section-number">27.9.7</span> String Searching
Functions</h3>
<p>Typically include <code>&lt;wchar.h&gt;</code> for these.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Searching Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>wcschr()</code></td>
<td>Find a character in a string.</td>
</tr>
<tr class="even">
<td><code>wcsrchr()</code></td>
<td>Find a character in a string from the back.</td>
</tr>
<tr class="odd">
<td><code>wmemchr()</code></td>
<td>Find a character in memory.</td>
</tr>
<tr class="even">
<td><code>wcsstr()</code></td>
<td>Find a substring in a string.</td>
</tr>
<tr class="odd">
<td><code>wcspbrk()</code></td>
<td>Find any of a set of characters in a string.</td>
</tr>
<tr class="even">
<td><code>wcsspn()</code></td>
<td>Find length of substring including any of a set of characters.</td>
</tr>
<tr class="odd">
<td><code>wcscspn()</code></td>
<td>Find length of substring before any of a set of characters.</td>
</tr>
<tr class="even">
<td><code>wcstok()</code></td>
<td>Find tokens in a string.</td>
</tr>
</tbody>
</table>
<h3 data-number="27.9.8" id="lengthmiscellaneous-functions"><span class="header-section-number">27.9.8</span> Length/Miscellaneous
Functions</h3>
<p>Typically include <code>&lt;wchar.h&gt;</code> for these.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Length/Misc Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>wcslen()</code></td>
<td>Return the length of the string.</td>
</tr>
<tr class="even">
<td><code>wmemset()</code></td>
<td>Set characters in memory.</td>
</tr>
<tr class="odd">
<td><code>wcsftime()</code></td>
<td>Formatted date and time output.</td>
</tr>
</tbody>
</table>
<h3 data-number="27.9.9" id="character-classification-functions"><span class="header-section-number">27.9.9</span> Character Classification
Functions</h3>
<p>Include <code>&lt;wctype.h&gt;</code> for these.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Length/Misc Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>iswalnum()</code></td>
<td>True if the character is alphanumeric.</td>
</tr>
<tr class="even">
<td><code>iswalpha()</code></td>
<td>True if the character is alphabetic.</td>
</tr>
<tr class="odd">
<td><code>iswblank()</code></td>
<td>True if the character is blank (space-ish, but not a newline).</td>
</tr>
<tr class="even">
<td><code>iswcntrl()</code></td>
<td>True if the character is a control character.</td>
</tr>
<tr class="odd">
<td><code>iswdigit()</code></td>
<td>True if the character is a digit.</td>
</tr>
<tr class="even">
<td><code>iswgraph()</code></td>
<td>True if the character is printable (except space).</td>
</tr>
<tr class="odd">
<td><code>iswlower()</code></td>
<td>True if the character is lowercase.</td>
</tr>
<tr class="even">
<td><code>iswprint()</code></td>
<td>True if the character is printable (including space).</td>
</tr>
<tr class="odd">
<td><code>iswpunct()</code></td>
<td>True if the character is punctuation.</td>
</tr>
<tr class="even">
<td><code>iswspace()</code></td>
<td>True if the character is whitespace.</td>
</tr>
<tr class="odd">
<td><code>iswupper()</code></td>
<td>True if the character is uppercase.</td>
</tr>
<tr class="even">
<td><code>iswxdigit()</code></td>
<td>True if the character is a hex digit.</td>
</tr>
<tr class="odd">
<td><code>towlower()</code></td>
<td>Convert character to lowercase.</td>
</tr>
<tr class="even">
<td><code>towupper()</code></td>
<td>Convert character to uppercase.</td>
</tr>
</tbody>
</table>
<h2 data-number="27.10" id="parse-state-restartable-functions"><span class="header-section-number">27.10</span> Parse State, Restartable
Functions</h2>
<p></p>
<p>We’re going to get a little bit into the guts of multibyte
conversion, but this is a good thing to understand, conceptually.</p>
<p>Imagine how your program takes a sequence of multibyte characters and
turns them into wide characters, or vice-versa. It might, at some point,
be partway through parsing a character, or it might have to wait for
more bytes before it makes the determination of the final value.</p>
<p>This parse state is stored in an opaque variable of type
<code>mbstate_t</code> and is used every time conversion is performed.
That’s how the conversion functions keep track of where they are
mid-work.</p>
<p>And if you change to a different character sequence mid-stream, or
try to seek to a different place in your input sequence, it could get
confused over that.</p>
<p>Now you might want to call me on this one: we just did some
conversions, above, and I never mentioned any <code>mbstate_t</code>
anywhere.</p>
<p>That’s because the conversion functions like <code>mbstowcs()</code>,
<code>wctomb()</code>, etc. each have their own <code>mbstate_t</code>
variable that they use. There’s only one per function, though, so if
you’re writing multithreaded code, they’re not safe to use.</p>
<p>Fortunately, C defines <em>restartable</em> versions of these
functions where you can pass in your own <code>mbstate_t</code> on
per-thread basis if you need to. If you’re doing multithreaded stuff,
use these!</p>
<p>Quick note on initializing an <code>mbstate_t</code> variable: just
<code>memset()</code> it to zero. There is no built-in function to force
it to be initialized.</p>
<div class="sourceCode" id="cb541"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb541-1"><a href="unicode-wide-characters-and-all-that.html#cb541-1" aria-hidden="true" tabindex="-1"></a>mbstate_t mbs<span class="op">;</span></span>
<span id="cb541-2"><a href="unicode-wide-characters-and-all-that.html#cb541-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb541-3"><a href="unicode-wide-characters-and-all-that.html#cb541-3" aria-hidden="true" tabindex="-1"></a><span class="co">// Set the state to the initial state</span></span>
<span id="cb541-4"><a href="unicode-wide-characters-and-all-that.html#cb541-4" aria-hidden="true" tabindex="-1"></a>memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span></span></code></pre></div>
<p>Here is a list of the restartable conversion functions—note the
naming convension of putting an “<code>r</code>” after the “from”
type:</p>
<ul>
<li><code>mbrtowc()</code>—multibyte to wide character</li>
<li><code>wcrtomb()</code>—wide character to multibyte</li>
<li><code>mbsrtowcs()</code>—multibyte string to wide character
string</li>
<li><code>wcsrtombs()</code>—wide character string to multibyte
string</li>
</ul>
<p>These are really similar to their non-restartable counterparts,
except they require you pass in a pointer to your own
<code>mbstate_t</code> variable. And also they modify the source string
pointer (to help you out if invalid bytes are found), so it might be
useful to save a copy of the original.</p>
<p>Here’s the example from earlier in the chapter reworked to pass in
our own <code>mbstate_t</code>.</p>
<div class="sourceCode" id="cb542"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb542-1"><a href="unicode-wide-characters-and-all-that.html#cb542-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb542-2"><a href="unicode-wide-characters-and-all-that.html#cb542-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb542-3"><a href="unicode-wide-characters-and-all-that.html#cb542-3"></a><span class="pp">#include </span><span class="im">&lt;stddef.h&gt;</span></span>
<span id="cb542-4"><a href="unicode-wide-characters-and-all-that.html#cb542-4"></a><span class="pp">#include </span><span class="im">&lt;wchar.h&gt;</span></span>
<span id="cb542-5"><a href="unicode-wide-characters-and-all-that.html#cb542-5"></a><span class="pp">#include </span><span class="im">&lt;string.h&gt;</span></span>
<span id="cb542-6"><a href="unicode-wide-characters-and-all-that.html#cb542-6"></a><span class="pp">#include </span><span class="im">&lt;locale.h&gt;</span></span>
<span id="cb542-7"><a href="unicode-wide-characters-and-all-that.html#cb542-7"></a></span>
<span id="cb542-8"><a href="unicode-wide-characters-and-all-that.html#cb542-8"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb542-9"><a href="unicode-wide-characters-and-all-that.html#cb542-9"></a><span class="op">{</span></span>
<span id="cb542-10"><a href="unicode-wide-characters-and-all-that.html#cb542-10"></a>    <span class="co">// Get out of the C locale to one that likely has the euro symbol</span></span>
<span id="cb542-11"><a href="unicode-wide-characters-and-all-that.html#cb542-11"></a>    setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span>
<span id="cb542-12"><a href="unicode-wide-characters-and-all-that.html#cb542-12"></a></span>
<span id="cb542-13"><a href="unicode-wide-characters-and-all-that.html#cb542-13"></a>    <span class="co">// Original multibyte string with a euro symbol (Unicode point 20ac)</span></span>
<span id="cb542-14"><a href="unicode-wide-characters-and-all-that.html#cb542-14"></a>    <span class="dt">char</span> <span class="op">*</span>mb_string <span class="op">=</span> <span class="st">"The cost is \u20ac1.23"</span><span class="op">;</span>  <span class="co">// €1.23</span></span>
<span id="cb542-15"><a href="unicode-wide-characters-and-all-that.html#cb542-15"></a>    <span class="dt">size_t</span> mb_len <span class="op">=</span> strlen<span class="op">(</span>mb_string<span class="op">);</span></span>
<span id="cb542-16"><a href="unicode-wide-characters-and-all-that.html#cb542-16"></a></span>
<span id="cb542-17"><a href="unicode-wide-characters-and-all-that.html#cb542-17"></a>    <span class="co">// Wide character array that will hold the converted string</span></span>
<span id="cb542-18"><a href="unicode-wide-characters-and-all-that.html#cb542-18"></a>    <span class="dt">wchar_t</span> wc_string<span class="op">[</span><span class="dv">128</span><span class="op">];</span>  <span class="co">// Holds up to 128 wide characters</span></span>
<span id="cb542-19"><a href="unicode-wide-characters-and-all-that.html#cb542-19"></a></span>
<span id="cb542-20"><a href="unicode-wide-characters-and-all-that.html#cb542-20"></a>    <span class="co">// Set up the conversion state</span></span>
<span id="cb542-21"><a href="unicode-wide-characters-and-all-that.html#cb542-21"></a>    mbstate_t mbs<span class="op">;</span></span>
<span id="cb542-22"><a href="unicode-wide-characters-and-all-that.html#cb542-22"></a>    memset<span class="op">(&amp;</span>mbs<span class="op">,</span> <span class="dv">0</span><span class="op">,</span> <span class="kw">sizeof</span> mbs<span class="op">);</span>  <span class="co">// Initial state</span></span>
<span id="cb542-23"><a href="unicode-wide-characters-and-all-that.html#cb542-23"></a></span>
<span id="cb542-24"><a href="unicode-wide-characters-and-all-that.html#cb542-24"></a>    <span class="co">// mbsrtowcs() modifies the input pointer to point at the first</span></span>
<span id="cb542-25"><a href="unicode-wide-characters-and-all-that.html#cb542-25"></a>    <span class="co">// invalid character, or NULL if successful. Let's make a copy of</span></span>
<span id="cb542-26"><a href="unicode-wide-characters-and-all-that.html#cb542-26"></a>    <span class="co">// the pointer for mbsrtowcs() to mess with so our original is</span></span>
<span id="cb542-27"><a href="unicode-wide-characters-and-all-that.html#cb542-27"></a>    <span class="co">// unchanged.</span></span>
<span id="cb542-28"><a href="unicode-wide-characters-and-all-that.html#cb542-28"></a>    <span class="co">//</span></span>
<span id="cb542-29"><a href="unicode-wide-characters-and-all-that.html#cb542-29"></a>    <span class="co">// This example will probably be successful, but we check farther</span></span>
<span id="cb542-30"><a href="unicode-wide-characters-and-all-that.html#cb542-30"></a>    <span class="co">// down to see.</span></span>
<span id="cb542-31"><a href="unicode-wide-characters-and-all-that.html#cb542-31"></a>    <span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>invalid <span class="op">=</span> mb_string<span class="op">;</span></span>
<span id="cb542-32"><a href="unicode-wide-characters-and-all-that.html#cb542-32"></a></span>
<span id="cb542-33"><a href="unicode-wide-characters-and-all-that.html#cb542-33"></a>    <span class="co">// Convert the MB string to WC; this returns the number of wide chars</span></span>
<span id="cb542-34"><a href="unicode-wide-characters-and-all-that.html#cb542-34"></a>    <span class="dt">size_t</span> wc_len <span class="op">=</span> mbsrtowcs<span class="op">(</span>wc_string<span class="op">,</span> <span class="op">&amp;</span>invalid<span class="op">,</span> <span class="dv">128</span><span class="op">,</span> <span class="op">&amp;</span>mbs<span class="op">);</span></span>
<span id="cb542-35"><a href="unicode-wide-characters-and-all-that.html#cb542-35"></a></span>
<span id="cb542-36"><a href="unicode-wide-characters-and-all-that.html#cb542-36"></a>    <span class="cf">if</span> <span class="op">(</span>invalid <span class="op">==</span> NULL<span class="op">)</span> <span class="op">{</span></span>
<span id="cb542-37"><a href="unicode-wide-characters-and-all-that.html#cb542-37"></a>        printf<span class="op">(</span><span class="st">"No invalid characters found</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb542-38"><a href="unicode-wide-characters-and-all-that.html#cb542-38"></a></span>
<span id="cb542-39"><a href="unicode-wide-characters-and-all-that.html#cb542-39"></a>        <span class="co">// Print result--note the %ls for wide char strings</span></span>
<span id="cb542-40"><a href="unicode-wide-characters-and-all-that.html#cb542-40"></a>        printf<span class="op">(</span><span class="st">"multibyte: </span><span class="sc">\"</span><span class="st">%s</span><span class="sc">\"</span><span class="st"> (%zu bytes)</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> mb_string<span class="op">,</span> mb_len<span class="op">);</span></span>
<span id="cb542-41"><a href="unicode-wide-characters-and-all-that.html#cb542-41"></a>        printf<span class="op">(</span><span class="st">"wide char: </span><span class="sc">\"</span><span class="st">%ls</span><span class="sc">\"</span><span class="st"> (%zu characters)</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> wc_string<span class="op">,</span> wc_len<span class="op">);</span></span>
<span id="cb542-42"><a href="unicode-wide-characters-and-all-that.html#cb542-42"></a>    <span class="op">}</span> <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb542-43"><a href="unicode-wide-characters-and-all-that.html#cb542-43"></a>        <span class="dt">ptrdiff_t</span> offset <span class="op">=</span> invalid <span class="op">-</span> mb_string<span class="op">;</span></span>
<span id="cb542-44"><a href="unicode-wide-characters-and-all-that.html#cb542-44"></a>        printf<span class="op">(</span><span class="st">"Invalid character at offset %td</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> offset<span class="op">);</span></span>
<span id="cb542-45"><a href="unicode-wide-characters-and-all-that.html#cb542-45"></a>    <span class="op">}</span></span>
<span id="cb542-46"><a href="unicode-wide-characters-and-all-that.html#cb542-46"></a><span class="op">}</span></span></code></pre></div>
<p>For the conversion functions that manage their own state, you can
reset their internal state to the initial one by passing in
<code>NULL</code> for their <code>char*</code> arguments, for
example:</p>
<div class="sourceCode" id="cb543"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb543-1"><a href="unicode-wide-characters-and-all-that.html#cb543-1" aria-hidden="true" tabindex="-1"></a>mbstowcs<span class="op">(</span>NULL<span class="op">,</span> NULL<span class="op">,</span> <span class="dv">0</span><span class="op">);</span>   <span class="co">// Reset the parse state for mbstowcs()</span></span>
<span id="cb543-2"><a href="unicode-wide-characters-and-all-that.html#cb543-2" aria-hidden="true" tabindex="-1"></a>mbstowcs<span class="op">(</span>dest<span class="op">,</span> src<span class="op">,</span> <span class="dv">100</span><span class="op">);</span>  <span class="co">// Parse some stuff</span></span></code></pre></div>
<p>For I/O, each wide stream manages its own <code>mbstate_t</code> and
uses that for input and output conversions as it goes.</p>
<p>And some of the byte-oriented I/O functions like
<code>printf()</code> and <code>scanf()</code> keep their own internal
state while doing their work.</p>
<p>Finally, these restartable conversion functions do actually have
their own internal state if you pass in <code>NULL</code> for the
<code>mbstate_t</code> parameter. This makes them behave more like their
non-restartable counterparts.</p>
<p> </p>
<h2 data-number="27.11" id="unicode-encodings-and-c"><span class="header-section-number">27.11</span> Unicode Encodings and C</h2>
<p>In this section, we’ll see what C can (and can’t) do when it comes to
three specific Unicode encodings: UTF-8, UTF-16, and UTF-32.</p>
<h3 data-number="27.11.1" id="utf-8"><span class="header-section-number">27.11.1</span> UTF-8</h3>
<p></p>
<p>To refresh before this section, read the <a href="unicode-wide-characters-and-all-that.html#utf8-quick">UTF-8
quick note, above</a>.</p>
<p>Aside from that, what are C’s UTF-8 capabilities?</p>
<p>Well, not much, unfortunately.</p>
<p></p>
<p>You can tell C that you specifically want a string literal to be
UTF-8 encoded, and it’ll do it for you. You can prefix a string with
<code>u8</code>:</p>
<div class="sourceCode" id="cb544"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb544-1"><a href="unicode-wide-characters-and-all-that.html#cb544-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> u8<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb544-2"><a href="unicode-wide-characters-and-all-that.html#cb544-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb544-3"><a href="unicode-wide-characters-and-all-that.html#cb544-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> s<span class="op">);</span>   <span class="co">// Hello, world!--if you can output UTF-8</span></span></code></pre></div>
<p>Now, can you put Unicode characters in there?</p>
<div class="sourceCode" id="cb545"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb545-1"><a href="unicode-wide-characters-and-all-that.html#cb545-1" aria-hidden="true" tabindex="-1"></a><span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> u8<span class="st">"€123"</span><span class="op">;</span></span></code></pre></div>
<p></p>
<p>Sure! If the extended source character set supports it. (gcc
does.)</p>
<p>What if it doesn’t? You can specify a Unicode code point with your
friendly neighborhood <code>\u</code> and <code>\U</code>, <a href="#unicode-in-c">as noted above</a>.</p>
<p>But that’s about it. There’s no portable way in the standard library
to take arbirary input and turn it into UTF-8 unless your locale is
UTF-8. Or to parse UTF-8 unless your locale is UTF-8.</p>
<p>So if you want to do it, either be in a UTF-8 locale and:</p>
<p></p>
<div class="sourceCode" id="cb546"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb546-1"><a href="unicode-wide-characters-and-all-that.html#cb546-1" aria-hidden="true" tabindex="-1"></a>setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">""</span><span class="op">);</span></span></code></pre></div>
<p>or figure out a UTF-8 locale name on your local machine and set it
explicitly like so:</p>
<div class="sourceCode" id="cb547"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb547-1"><a href="unicode-wide-characters-and-all-that.html#cb547-1" aria-hidden="true" tabindex="-1"></a>setlocale<span class="op">(</span>LC_ALL<span class="op">,</span> <span class="st">"en_US.UTF-8"</span><span class="op">);</span>  <span class="co">// Non-portable name</span></span></code></pre></div>
<p></p>
<p>Or use a <a href="unicode-wide-characters-and-all-that.html#utf-3rd-party">third-party library</a>.</p>
<p></p>
<h3 data-number="27.11.2" id="utf-16-utf-32-char16_t-and-char32_t"><span class="header-section-number">27.11.2</span> UTF-16, UTF-32,
<code>char16_t</code>, and <code>char32_t</code></h3>
<p> </p>
<p><code>char16_t</code> and <code>char32_t</code> are a couple other
potentially wide character types with sizes of 16 bits and 32 bits,
respectively. Not necessarily wide, because if they can’t represent
every character in the current locale, they lose their wide character
nature. But the spec refers them as “wide character” types all over the
place, so there we are.</p>
<p>These are here to make things a little more Unicode-friendly,
potentially.</p>
<p>To use, include <code>&lt;uchar.h&gt;</code>. (That’s “u”, not
“w”.)</p>
<p>This header file doesn’t exist on OS X—bummer. If you just want the
types, you can:</p>
<div class="sourceCode" id="cb548"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb548-1"><a href="unicode-wide-characters-and-all-that.html#cb548-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdint.h&gt;</span></span>
<span id="cb548-2"><a href="unicode-wide-characters-and-all-that.html#cb548-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb548-3"><a href="unicode-wide-characters-and-all-that.html#cb548-3" aria-hidden="true" tabindex="-1"></a><span class="kw">typedef</span> <span class="dt">int_least16_t</span> char16_t<span class="op">;</span></span>
<span id="cb548-4"><a href="unicode-wide-characters-and-all-that.html#cb548-4" aria-hidden="true" tabindex="-1"></a><span class="kw">typedef</span> <span class="dt">int_least32_t</span> char32_t<span class="op">;</span></span></code></pre></div>
<p>But if you also want the functions, that’s all on you.</p>
<p> </p>
<p>Assuming you’re still good to go, you can declare a string or
character of these types with the <code>u</code> and <code>U</code>
prefixes:</p>
<div class="sourceCode" id="cb549"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb549-1"><a href="unicode-wide-characters-and-all-that.html#cb549-1" aria-hidden="true" tabindex="-1"></a>char16_t <span class="op">*</span>s <span class="op">=</span> u<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb549-2"><a href="unicode-wide-characters-and-all-that.html#cb549-2" aria-hidden="true" tabindex="-1"></a>char16_t c <span class="op">=</span> u<span class="ch">'B'</span><span class="op">;</span></span>
<span id="cb549-3"><a href="unicode-wide-characters-and-all-that.html#cb549-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb549-4"><a href="unicode-wide-characters-and-all-that.html#cb549-4" aria-hidden="true" tabindex="-1"></a>char32_t <span class="op">*</span>t <span class="op">=</span> U<span class="st">"Hello, world!"</span><span class="op">;</span></span>
<span id="cb549-5"><a href="unicode-wide-characters-and-all-that.html#cb549-5" aria-hidden="true" tabindex="-1"></a>char32_t d <span class="op">=</span> U<span class="ch">'B'</span><span class="op">;</span></span></code></pre></div>
<p> </p>
<p>Now—are values in these stored in UTF-16 or UTF-32? Depends on the
implementation.</p>
<p>But you can test to see if they are. If the macros
<code>__STDC_UTF_16__</code> or <code>__STDC_UTF_32__</code> are defined
(to <code>1</code>) it means the types hold UTF-16 or UTF-32,
respectively.</p>
<p>If you’re curious, and I know you are, the values, if UTF-16 or
UTF-32, are stored in the native endianess. That is, you should be able
to compare them straight up to Unicode code point values:</p>
<div class="sourceCode" id="cb550"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb550-1"><a href="unicode-wide-characters-and-all-that.html#cb550-1" aria-hidden="true" tabindex="-1"></a>char16_t pi <span class="op">=</span> u<span class="st">"\u03C0"</span><span class="op">;</span>  <span class="co">// pi symbol</span></span>
<span id="cb550-2"><a href="unicode-wide-characters-and-all-that.html#cb550-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb550-3"><a href="unicode-wide-characters-and-all-that.html#cb550-3" aria-hidden="true" tabindex="-1"></a><span class="pp">#if __STDC_UTF_16__</span></span>
<span id="cb550-4"><a href="unicode-wide-characters-and-all-that.html#cb550-4" aria-hidden="true" tabindex="-1"></a>pi <span class="op">==</span> <span class="bn">0x3C0</span><span class="op">;</span>  <span class="co">// Always true</span></span>
<span id="cb550-5"><a href="unicode-wide-characters-and-all-that.html#cb550-5" aria-hidden="true" tabindex="-1"></a><span class="pp">#else</span></span>
<span id="cb550-6"><a href="unicode-wide-characters-and-all-that.html#cb550-6" aria-hidden="true" tabindex="-1"></a>pi <span class="op">==</span> <span class="bn">0x3C0</span><span class="op">;</span>  <span class="co">// Probably not true</span></span>
<span id="cb550-7"><a href="unicode-wide-characters-and-all-that.html#cb550-7" aria-hidden="true" tabindex="-1"></a><span class="pp">#endif</span></span></code></pre></div>
<p> </p>
<h3 data-number="27.11.3" id="multibyte-conversions"><span class="header-section-number">27.11.3</span> Multibyte Conversions</h3>
<p>You can convert from your multibyte encoding to <code>char16_t</code>
or <code>char32_t</code> with a number of helper functions.</p>
<p>(Like I said, though, the result might not be UTF-16 or UTF-32 unless
the corresponding macro is set to <code>1</code>.)</p>
<p style="">All of these functions are restartable (i.e.&nbsp;you pass in your own
<code>mbstate_t</code>), and all of them operate character by
character<a href="footnotes.html#fn155" class="footnote-ref" id="fnref155" role="doc-noteref"><sup>155</sup></a>.</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Conversion Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>mbrtoc16()</code></td>
<td>Convert a multibyte character to a <code>char16_t</code>
character.</td>
</tr>
<tr class="even">
<td><code>mbrtoc32()</code></td>
<td style="">Convert a multibyte character to a <code>char32_t</code>
character.</td>
</tr>
<tr class="odd">
<td><code>c16rtomb()</code></td>
<td>Convert a <code>char16_t</code> character to a multibyte
character.</td>
</tr>
<tr class="even">
<td><code>c32rtomb()</code></td>
<td>Convert a <code>char32_t</code> character to a multibyte
character.</td>
</tr>
</tbody>
</table>
<h3 data-number="27.11.4" id="utf-3rd-party"><span class="header-section-number">27.11.4</span> Third-Party Libraries</h3>
<p>For heavy-duty conversion between different specific encodings, there
are a couple mature libraries worth checking out. Note that I haven’t
used either of these.</p>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Iconv">iconv</a><a href="#fn156" class="footnote-ref" id="fnref156" role="doc-noteref"><sup>156</sup></a>—Internationalization Conversion, a
common POSIX-standard API available on the major platforms.</li>
<li><a href="http://site.icu-project.org/">ICU</a><a href="footnotes.html#fn157" class="footnote-ref" id="fnref157" role="doc-noteref"><sup>157</sup></a>—International Components for
Unicode. At least one blogger found this easy to use.</li>
</ul>
<p>If you have more noteworthy libraries, let me know.</p>
<p></p>
<!-- Beej's guide to C

# vim: ts=4:sw=4:nosi:et:tw=72
-->
<hr>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="locale-and-internationalization.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="exiting-a-program.html">Next»</a></div>

</body>