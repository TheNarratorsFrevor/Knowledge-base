<body>

<hr>
<h1 data-number="54" id="signal"><span class="header-section-number">54</span> <code>&lt;signal.h&gt;</code>
signal handling</h1>
<table>
<thead>
<tr class="header">
<th>Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="signal.html#man-signal"><code>signal()</code></a></td>
<td>Set a signal handler for a given signal</td>
</tr>
<tr class="even">
<td><a href="signal.html#man-raise"><code>raise()</code></a></td>
<td>Cause a signal to be raised</td>
</tr>
</tbody>
</table>
<p>Handle signals in a portable way, kind of!</p>
<p>These signals get raised for a variety of reasons such as CTRL-C
being hit, requests to terminate for external programs, memory access
violations, and so on.</p>
<p>Your OS likely defines a plethora of other signals, as well.</p>
<p>This system is pretty limited, as seen below. If you’re on Unix, it’s
almost certain your OS has far superior signal handling capabilities
than the C standard library. Check out <a href="https://man.archlinux.org/man/sigaction.2.en"><code>sigaction</code></a><a href="#fn242" class="footnote-ref" id="fnref242" role="doc-noteref"><sup>242</sup></a>.</p>
<hr>
<h2 data-number="54.1" id="man-signal"><span class="header-section-number">54.1</span> <code>signal()</code></h2>
<p>Set a signal handler for a given signal</p>
<h3 class="unnumbered unlisted" id="synopsis-114">Synopsis</h3>
<div class="sourceCode" id="cb1126"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1126-1"><a href="signal.html#cb1126-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb1126-2"><a href="signal.html#cb1126-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1126-3"><a href="signal.html#cb1126-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">(*</span>signal<span class="op">(</span><span class="dt">int</span> sig<span class="op">,</span> <span class="dt">void</span> <span class="op">(*</span>func<span class="op">)(</span><span class="dt">int</span><span class="op">)))(</span><span class="dt">int</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-114">Description</h3>
<p>How’s <em>that</em> for a function declaration?</p>
<p>Let’s ignore it for a moment and just talk about what this function
does.</p>
<p>When a signal is raised, <em>something</em> is going to happen. This
function lets you decide to do one of these things when the signal is
raised:</p>
<ul>
<li>Ignore the signal</li>
<li>Perform the default action</li>
<li>Have a specific function called</li>
</ul>
<p>The <code>signal()</code> function takes two arguments. The first,
<code>sig</code>, is the name of the signal to handle.</p>
<table>
<thead>
<tr class="header">
<th>Signal</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>SIGABRT</code></td>
<td>Raised when <code>abort()</code> is called</td>
</tr>
<tr class="even">
<td><code>SIGFPE</code></td>
<td>Floating-point arithmetic exception</td>
</tr>
<tr class="odd">
<td><code>SIGILL</code></td>
<td>CPU tried to execute an illegal instruction</td>
</tr>
<tr class="even">
<td><code>SIGINT</code></td>
<td>Interrupt signal, as if <code>CTRL-C</code> were pressed</td>
</tr>
<tr class="odd">
<td><code>SIGSEGV</code></td>
<td>Segmention Violation: attempted to access restricted memory</td>
</tr>
<tr class="even">
<td><code>SIGTERM</code></td>
<td>Termination request<a href="footnotes.html#fn243" class="footnote-ref" id="fnref243" role="doc-noteref"><sup>243</sup></a></td>
</tr>
</tbody>
</table>
<p>So that’s the first bit when you call <code>signal()</code>—tell it
the signal in question:</p>
<div class="sourceCode" id="cb1127"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1127-1"><a href="signal.html#cb1127-1" aria-hidden="true" tabindex="-1"></a>signal<span class="op">(</span>SIGINT<span class="op">,</span> <span class="op">...</span></span></code></pre></div>
<p>But what’s that <code>func</code> parameter?</p>
<p>For spoilers, it’s a pointer to a function that takes an
<code>int</code> argument and returns <code>void</code>. We can use this
to call an arbitrary function when the signal occurs.</p>
<p>Before we do that, though, let’s look at the easy ones: telling the
system to ignore the signal or perform the default action (which it does
by default if you never call <code>signal()</code>).</p>
<p>You can set <code>func</code> to one of two special values to make
this happen:</p>
<table>
<thead>
<tr class="header">
<th><code>func</code></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>SIG_DFL</code></td>
<td>Perform the default action on this signal</td>
</tr>
<tr class="even">
<td><code>SIG_IGN</code></td>
<td>Ignore this signal</td>
</tr>
</tbody>
</table>
<p>For example:</p>
<div class="sourceCode" id="cb1128"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1128-1"><a href="signal.html#cb1128-1" aria-hidden="true" tabindex="-1"></a>signal<span class="op">(</span>SIGTERM<span class="op">,</span> SIG_DFL<span class="op">);</span>  <span class="co">// Default action on SIGTERM</span></span>
<span id="cb1128-2"><a href="signal.html#cb1128-2" aria-hidden="true" tabindex="-1"></a>signal<span class="op">(</span>SIGINT<span class="op">,</span> SIG_IGN<span class="op">);</span>   <span class="co">// Ignore SIGINT</span></span></code></pre></div>
<p>But what if you want to have your own handler do something instead of
the default or ignoring it? You can pass in your own function to be
called. That’s what the crazy function signature is partially about.
It’s saying that the argument can be a pointer to a function that takes
an <code>int</code> argument and returns <code>void</code>.</p>
<p>So if you wanted to call your handler, you could have code like
this:</p>
<div class="sourceCode" id="cb1129"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1129-1"><a href="signal.html#cb1129-1" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> handler<span class="op">(</span><span class="dt">int</span> sig<span class="op">)</span></span>
<span id="cb1129-2"><a href="signal.html#cb1129-2" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1129-3"><a href="signal.html#cb1129-3" aria-hidden="true" tabindex="-1"></a>    <span class="co">// Handle the signal</span></span>
<span id="cb1129-4"><a href="signal.html#cb1129-4" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span>
<span id="cb1129-5"><a href="signal.html#cb1129-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1129-6"><a href="signal.html#cb1129-6" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1129-7"><a href="signal.html#cb1129-7" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1129-8"><a href="signal.html#cb1129-8" aria-hidden="true" tabindex="-1"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> handler<span class="op">);</span></span></code></pre></div>
<p>What can you do in the signal handler? Not much.</p>
<p>If the signal is due to <code>abort()</code> or <code>raise()</code>,
the handler can’t call <code>raise()</code>.</p>
<p>If the signal is <strong>not</strong> due to <code>abort()</code> or
<code>raise()</code>, you’re only allowed to call these functions from
the standard library (though the spec doesn’t prohibit calling other
non-library functions):</p>
<ul>
<li><a href="stdlib.html#man-abort"><code>abort()</code></a></li>
<li><a href="stdlib.html#man-exit"><code>_Exit()</code></a></li>
<li><a href="stdlib.html#man-exit"><code>quick_exit()</code></a></li>
<li>Functions in <a href="#stdatomic"><code>&lt;stdatomic.h&gt;</code></a> when the atomic
arguments are lock-free</li>
<li><code>signal()</code> with a first argument equivalent to the
argument that was passed into the handler</li>
</ul>
<p>In addition, if the signal was <strong>not</strong> due to
<code>abort()</code> or <code>raise()</code>, the handler can’t access
any object with static or thread-storage duration unless it’s
lock-free.</p>
<p>An exception is that you can assign to (but not read from!) a
variable of type <code>volatile sig_atomic_t</code>.</p>
<p>It’s up to the implementation, but the signal handler might be reset
to <code>SIG_DFL</code> just before the handler is called.</p>
<p>It’s undefined behavior to call <code>signal()</code> in a
multithreaded program.</p>
<p>It’s undefined behavior to return from the handler for
<code>SIGFPE</code>, <code>SIGILL</code>, <code>SIGSEGV</code>, or any
implementation-defined value. You must exit.</p>
<p>The implementation might or might not prevent other signals from
arising while in the signal handler.</p>
<h3 class="unnumbered unlisted" id="return-value-113">Return Value</h3>
<p>On success, <code>signal()</code> returns a pointer to the previous
signal handler set by a call to <code>signal()</code> for that
particular signal number. If you haven’t called it set, returns
<code>SIG_DFL</code>.</p>
<p>On failure, <code>SIG_ERR</code> is returned and <code>errno</code>
is set to a positive value.</p>
<h3 class="unnumbered unlisted" id="example-114">Example</h3>
<p>Here’s a program that causes <code>SIGINT</code> to be ignored.
Commonly you trigger this signal by hitting <code>CTRL-C</code>.</p>
<div class="sourceCode" id="cb1130"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1130-1"><a href="signal.html#cb1130-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1130-2"><a href="signal.html#cb1130-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb1130-3"><a href="signal.html#cb1130-3"></a></span>
<span id="cb1130-4"><a href="signal.html#cb1130-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1130-5"><a href="signal.html#cb1130-5"></a><span class="op">{</span></span>
<span id="cb1130-6"><a href="signal.html#cb1130-6"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> SIG_IGN<span class="op">);</span></span>
<span id="cb1130-7"><a href="signal.html#cb1130-7"></a></span>
<span id="cb1130-8"><a href="signal.html#cb1130-8"></a>    printf<span class="op">(</span><span class="st">"You can't hit CTRL-C to exit this program. Try it!</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1130-9"><a href="signal.html#cb1130-9"></a>    printf<span class="op">(</span><span class="st">"Press return to exit, instead."</span><span class="op">);</span></span>
<span id="cb1130-10"><a href="signal.html#cb1130-10"></a>    fflush<span class="op">(</span>stdout<span class="op">);</span></span>
<span id="cb1130-11"><a href="signal.html#cb1130-11"></a>    getchar<span class="op">();</span></span>
<span id="cb1130-12"><a href="signal.html#cb1130-12"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1131"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1131-1"><a href="signal.html#cb1131-1" aria-hidden="true" tabindex="-1"></a>You can't hit CTRL-C to exit this program. Try it!</span>
<span id="cb1131-2"><a href="signal.html#cb1131-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1131-3"><a href="signal.html#cb1131-3" aria-hidden="true" tabindex="-1"></a>Press return to exit, instead.^C^C^C^C^C^C^C^C^C^C^C</span></code></pre></div>
<p>This program sets the signal handler, then raises the signal. The
signal handler fires.</p>
<div class="sourceCode" id="cb1132"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1132-1"><a href="signal.html#cb1132-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1132-2"><a href="signal.html#cb1132-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb1132-3"><a href="signal.html#cb1132-3"></a></span>
<span id="cb1132-4"><a href="signal.html#cb1132-4"></a><span class="dt">void</span> handler<span class="op">(</span><span class="dt">int</span> sig<span class="op">)</span></span>
<span id="cb1132-5"><a href="signal.html#cb1132-5"></a><span class="op">{</span></span>
<span id="cb1132-6"><a href="signal.html#cb1132-6"></a>    <span class="co">// Undefined behavior to call printf() if this handler was not</span></span>
<span id="cb1132-7"><a href="signal.html#cb1132-7"></a>    <span class="co">// as the result of a raise(), i.e. if you hit CTRL-C.</span></span>
<span id="cb1132-8"><a href="signal.html#cb1132-8"></a></span>
<span id="cb1132-9"><a href="signal.html#cb1132-9"></a>    printf<span class="op">(</span><span class="st">"Got signal %d!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> sig<span class="op">);</span></span>
<span id="cb1132-10"><a href="signal.html#cb1132-10"></a></span>
<span id="cb1132-11"><a href="signal.html#cb1132-11"></a>    <span class="co">// Common to reset the handler just in case the implementation set</span></span>
<span id="cb1132-12"><a href="signal.html#cb1132-12"></a>    <span class="co">// it to SIG_DFL when the signal occurred.</span></span>
<span id="cb1132-13"><a href="signal.html#cb1132-13"></a></span>
<span id="cb1132-14"><a href="signal.html#cb1132-14"></a>    signal<span class="op">(</span>sig<span class="op">,</span> handler<span class="op">);</span></span>
<span id="cb1132-15"><a href="signal.html#cb1132-15"></a><span class="op">}</span></span>
<span id="cb1132-16"><a href="signal.html#cb1132-16"></a></span>
<span id="cb1132-17"><a href="signal.html#cb1132-17"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1132-18"><a href="signal.html#cb1132-18"></a><span class="op">{</span></span>
<span id="cb1132-19"><a href="signal.html#cb1132-19"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> handler<span class="op">);</span></span>
<span id="cb1132-20"><a href="signal.html#cb1132-20"></a></span>
<span id="cb1132-21"><a href="signal.html#cb1132-21"></a>    raise<span class="op">(</span>SIGINT<span class="op">);</span></span>
<span id="cb1132-22"><a href="signal.html#cb1132-22"></a>    raise<span class="op">(</span>SIGINT<span class="op">);</span></span>
<span id="cb1132-23"><a href="signal.html#cb1132-23"></a>    raise<span class="op">(</span>SIGINT<span class="op">);</span></span>
<span id="cb1132-24"><a href="signal.html#cb1132-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1133"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1133-1"><a href="signal.html#cb1133-1" aria-hidden="true" tabindex="-1"></a>Got signal 2!</span>
<span id="cb1133-2"><a href="signal.html#cb1133-2" aria-hidden="true" tabindex="-1"></a>Got signal 2!</span>
<span id="cb1133-3"><a href="signal.html#cb1133-3" aria-hidden="true" tabindex="-1"></a>Got signal 2!</span></code></pre></div>
<p>This example catches <code>SIGINT</code> but then sets a flag to
<code>1</code>. Then the main loop sees the flag and exits.</p>
<div class="sourceCode" id="cb1134"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1134-1"><a href="signal.html#cb1134-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1134-2"><a href="signal.html#cb1134-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb1134-3"><a href="signal.html#cb1134-3"></a></span>
<span id="cb1134-4"><a href="signal.html#cb1134-4"></a><span class="dt">volatile</span> <span class="dt">sig_atomic_t</span> x<span class="op">;</span></span>
<span id="cb1134-5"><a href="signal.html#cb1134-5"></a></span>
<span id="cb1134-6"><a href="signal.html#cb1134-6"></a><span class="dt">void</span> handler<span class="op">(</span><span class="dt">int</span> sig<span class="op">)</span></span>
<span id="cb1134-7"><a href="signal.html#cb1134-7"></a><span class="op">{</span></span>
<span id="cb1134-8"><a href="signal.html#cb1134-8"></a>    x <span class="op">=</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1134-9"><a href="signal.html#cb1134-9"></a><span class="op">}</span></span>
<span id="cb1134-10"><a href="signal.html#cb1134-10"></a></span>
<span id="cb1134-11"><a href="signal.html#cb1134-11"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1134-12"><a href="signal.html#cb1134-12"></a><span class="op">{</span></span>
<span id="cb1134-13"><a href="signal.html#cb1134-13"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> handler<span class="op">);</span></span>
<span id="cb1134-14"><a href="signal.html#cb1134-14"></a></span>
<span id="cb1134-15"><a href="signal.html#cb1134-15"></a>    printf<span class="op">(</span><span class="st">"Hit CTRL-C to exit</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1134-16"><a href="signal.html#cb1134-16"></a>    <span class="cf">while</span> <span class="op">(</span>x <span class="op">!=</span> <span class="dv">1</span><span class="op">);</span></span>
<span id="cb1134-17"><a href="signal.html#cb1134-17"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-107">See Also</h3>
<p><a href="signal.html#man-raise"><code>raise()</code></a>, <a href="#man-abort"><code>abort()</code></a></p>
<hr>
<h2 data-number="54.2" id="man-raise"><span class="header-section-number">54.2</span> <code>raise()</code></h2>
<p>Cause a signal to be raised</p>
<h3 class="unnumbered unlisted" id="synopsis-115">Synopsis</h3>
<div class="sourceCode" id="cb1135"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1135-1"><a href="signal.html#cb1135-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb1135-2"><a href="signal.html#cb1135-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1135-3"><a href="signal.html#cb1135-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> raise<span class="op">(</span><span class="dt">int</span> sig<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-115">Description</h3>
<p>Causes the signal handler for the signal <code>sig</code> to be
called. If the handler is <code>SIG_DFL</code> or <code>SIG_IGN</code>,
then the default action or no action happens.</p>
<p><code>raise()</code> returns after the signal handler has finished
running.</p>
<p>Interestingly, if you cause a signal to happen with
<code>raise()</code>, you can call library functions from within the
signal handler without causing undefined behavior. I’m not sure how this
fact is practically useful, though.</p>
<h3 class="unnumbered unlisted" id="return-value-114">Return Value</h3>
<p>Returns <code>0</code> on success. Nonzero otherwise.</p>
<h3 class="unnumbered unlisted" id="example-115">Example</h3>
<p>This program sets the signal handler, then raises the signal. The
signal handler fires.</p>
<div class="sourceCode" id="cb1136"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1136-1"><a href="signal.html#cb1136-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1136-2"><a href="signal.html#cb1136-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb1136-3"><a href="signal.html#cb1136-3"></a></span>
<span id="cb1136-4"><a href="signal.html#cb1136-4"></a><span class="dt">void</span> handler<span class="op">(</span><span class="dt">int</span> sig<span class="op">)</span></span>
<span id="cb1136-5"><a href="signal.html#cb1136-5"></a><span class="op">{</span></span>
<span id="cb1136-6"><a href="signal.html#cb1136-6"></a>    <span class="co">// Undefined behavior to call printf() if this handler was not</span></span>
<span id="cb1136-7"><a href="signal.html#cb1136-7"></a>    <span class="co">// as the result of a raise(), i.e. if you hit CTRL-C.</span></span>
<span id="cb1136-8"><a href="signal.html#cb1136-8"></a></span>
<span id="cb1136-9"><a href="signal.html#cb1136-9"></a>    printf<span class="op">(</span><span class="st">"Got signal %d!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> sig<span class="op">);</span></span>
<span id="cb1136-10"><a href="signal.html#cb1136-10"></a></span>
<span id="cb1136-11"><a href="signal.html#cb1136-11"></a>    <span class="co">// Common to reset the handler just in case the implementation set</span></span>
<span id="cb1136-12"><a href="signal.html#cb1136-12"></a>    <span class="co">// it to SIG_DFL when the signal occurred.</span></span>
<span id="cb1136-13"><a href="signal.html#cb1136-13"></a></span>
<span id="cb1136-14"><a href="signal.html#cb1136-14"></a>    signal<span class="op">(</span>sig<span class="op">,</span> handler<span class="op">);</span></span>
<span id="cb1136-15"><a href="signal.html#cb1136-15"></a><span class="op">}</span></span>
<span id="cb1136-16"><a href="signal.html#cb1136-16"></a></span>
<span id="cb1136-17"><a href="signal.html#cb1136-17"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1136-18"><a href="signal.html#cb1136-18"></a><span class="op">{</span></span>
<span id="cb1136-19"><a href="signal.html#cb1136-19"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> handler<span class="op">);</span></span>
<span id="cb1136-20"><a href="signal.html#cb1136-20"></a></span>
<span id="cb1136-21"><a href="signal.html#cb1136-21"></a>    raise<span class="op">(</span>SIGINT<span class="op">);</span></span>
<span id="cb1136-22"><a href="signal.html#cb1136-22"></a>    raise<span class="op">(</span>SIGINT<span class="op">);</span></span>
<span id="cb1136-23"><a href="signal.html#cb1136-23"></a>    raise<span class="op">(</span>SIGINT<span class="op">);</span></span>
<span id="cb1136-24"><a href="signal.html#cb1136-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1137"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1137-1"><a href="signal.html#cb1137-1" aria-hidden="true" tabindex="-1"></a>Got signal 2!</span>
<span id="cb1137-2"><a href="signal.html#cb1137-2" aria-hidden="true" tabindex="-1"></a>Got signal 2!</span>
<span id="cb1137-3"><a href="signal.html#cb1137-3" aria-hidden="true" tabindex="-1"></a>Got signal 2!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-108">See Also</h3>
<p><a href="signal.html#man-signal"><code>signal()</code></a></p>


</body>