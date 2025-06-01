<body>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="exiting-a-program.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="variable-length-arrays-vlas.html">Next»</a></div>
<hr>
<h1 data-number="29" id="signal-handling"><span class="header-section-number">29</span> Signal Handling</h1>
<p></p>
<p>Before we start, I’m just going to advise you to generally ignore
this entire chapter and use your OS’s (very likely) superior signal
handling functions. Unix-likes have the <code>sigaction()</code> family
of functions, and Windows has… whatever it does<a href="footnotes.html#fn159" class="footnote-ref" id="fnref159" role="doc-noteref"><sup>159</sup></a>.</p>
<p>With that out of the way, what are signals?</p>
<h2 data-number="29.1" id="what-are-signals"><span class="header-section-number">29.1</span> What Are Signals?</h2>
<p>A <em>signal</em> is <em>raised</em> on a variety of external events.
Your program can be configured to be interrupted to <em>handle</em> the
signal, and, optionally, continue where it left off once the signal has
been handled.</p>
<p>Think of it like a function that’s automatically called when one of
these external events occurs.</p>
<p>What are these events? On your system, there are probably a lot of
them, but in the C spec there are just a few:</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th>Signal</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>SIGABRT</code></td>
<td>Abnormal termination—what happens when <code>abort()</code> is
called.</td>
</tr>
<tr class="even">
<td><code>SIGFPE</code></td>
<td>Floating point exception.</td>
</tr>
<tr class="odd">
<td><code>SIGILL</code></td>
<td>Illegal instruction.</td>
</tr>
<tr class="even">
<td><code>SIGINT</code></td>
<td>Interrupt—usually the result of <code>CTRL-C</code> being hit.</td>
</tr>
<tr class="odd">
<td><code>SIGSEGV</code></td>
<td>“Segmentation Violation”: invalid memory access.</td>
</tr>
<tr class="even">
<td><code>SIGTERM</code></td>
<td>Termination requested.</td>
</tr>
</tbody>
</table>
<p>You can set up your program to ignore, handle, or allow the default
action for each of these by using the <code>signal()</code>
function.</p>
<h2 data-number="29.2" id="handling-signals-with-signal"><span class="header-section-number">29.2</span> Handling Signals with
<code>signal()</code></h2>
<p></p>
<p>The <code>signal()</code> call takes two parameters: the signal in
question, and an action to take when that signal is raised.</p>
<p>The action can be one of three things:</p>
<ul>
<li>A pointer to a handler function.</li>
<li><code>SIG_IGN</code> to ignore the signal.</li>
<li><code>SIG_DFL</code> to restore the default handler for the
signal.</li>
</ul>
<p>Let’s write a program that you can’t <code>CTRL-C</code> out of.
(Don’t fret—in the following program, you can also hit
<code>RETURN</code> and it’ll exit.)</p>
<p></p>
<div class="sourceCode" id="cb558"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb558-1"><a href="signal-handling.html#cb558-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb558-2"><a href="signal-handling.html#cb558-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb558-3"><a href="signal-handling.html#cb558-3"></a></span>
<span id="cb558-4"><a href="signal-handling.html#cb558-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb558-5"><a href="signal-handling.html#cb558-5"></a><span class="op">{</span></span>
<span id="cb558-6"><a href="signal-handling.html#cb558-6"></a>    <span class="dt">char</span> s<span class="op">[</span><span class="dv">1024</span><span class="op">];</span></span>
<span id="cb558-7"><a href="signal-handling.html#cb558-7"></a></span>
<span id="cb558-8"><a href="signal-handling.html#cb558-8"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> SIG_IGN<span class="op">);</span>    <span class="co">// Ignore SIGINT, caused by ^C</span></span>
<span id="cb558-9"><a href="signal-handling.html#cb558-9"></a></span>
<span id="cb558-10"><a href="signal-handling.html#cb558-10"></a>    printf<span class="op">(</span><span class="st">"Try hitting ^C... (hit RETURN to exit)</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb558-11"><a href="signal-handling.html#cb558-11"></a></span>
<span id="cb558-12"><a href="signal-handling.html#cb558-12"></a>    <span class="co">// Wait for a line of input so the program doesn't just exit</span></span>
<span id="cb558-13"><a href="signal-handling.html#cb558-13"></a>    fgets<span class="op">(</span>s<span class="op">,</span> <span class="kw">sizeof</span> s<span class="op">,</span> stdin<span class="op">);</span></span>
<span id="cb558-14"><a href="signal-handling.html#cb558-14"></a><span class="op">}</span></span></code></pre></div>
<p>Check out line 8—we tell the program to ignore <code>SIGINT</code>,
the interrupt signal that’s raised when <code>CTRL-C</code> is hit. No
matter how much you hit it, the signal remains ignored. If you comment
out line 8, you’ll see you can <code>CTRL-C</code> with impunity and
quit the program on the spot.</p>
<p> </p>
<h2 data-number="29.3" id="writing-signal-handlers"><span class="header-section-number">29.3</span> Writing Signal Handlers</h2>
<p>I mentioned you could also write a handler function that gets called
with the signal is raised.</p>
<p>These are pretty straightforward, are also very capability-limited
when it comes to the spec.</p>
<p></p>
<p>Before we start, let’s look at the function prototype for the
<code>signal()</code> call:</p>
<div class="sourceCode" id="cb559"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb559-1"><a href="signal-handling.html#cb559-1" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">(*</span>signal<span class="op">(</span><span class="dt">int</span> sig<span class="op">,</span> <span class="dt">void</span> <span class="op">(*</span>func<span class="op">)(</span><span class="dt">int</span><span class="op">)))(</span><span class="dt">int</span><span class="op">);</span></span></code></pre></div>
<p>Pretty easy to read, right?</p>
<p><em>WRONG!</em> <code>:)</code></p>
<p>Let’s take a moment to take it apart for practice.</p>
<p><code>signal()</code> takes two arguments: an integer
<code>sig</code> representing the signal, and a pointer
<code>func</code> to the handler (the handler returns <code>void</code>
and takes an <code>int</code> as an argument), highlighted below:</p>
<div class="sourceCode" id="cb560"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb560-1"><a href="signal-handling.html#cb560-1" aria-hidden="true" tabindex="-1"></a>                sig          func</span>
<span id="cb560-2"><a href="signal-handling.html#cb560-2" aria-hidden="true" tabindex="-1"></a>              <span class="op">|-----|</span>  <span class="op">|---------------|</span></span>
<span id="cb560-3"><a href="signal-handling.html#cb560-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">(*</span>signal<span class="op">(</span><span class="dt">int</span> sig<span class="op">,</span> <span class="dt">void</span> <span class="op">(*</span>func<span class="op">)(</span><span class="dt">int</span><span class="op">)))(</span><span class="dt">int</span><span class="op">);</span></span></code></pre></div>
<p></p>
<p>Basically, we’re going to pass in the signal number we’re interesting
in catching, and we’re going to pass a pointer to a function of the
form:</p>
<div class="sourceCode" id="cb561"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb561-1"><a href="signal-handling.html#cb561-1" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> f<span class="op">(</span><span class="dt">int</span> x<span class="op">);</span></span></code></pre></div>
<p>that will do the actual catching.</p>
<p>Now—what about the rest of that prototype? It’s basically all the
return type. See, <code>signal()</code> will return whatever you passed
as <code>func</code> on success… so that means it’s returning a pointer
to a function that returns <code>void</code> and takes an
<code>int</code> as an argument.</p>
<div class="sourceCode" id="cb562"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb562-1"><a href="signal-handling.html#cb562-1" aria-hidden="true" tabindex="-1"></a>returned</span>
<span id="cb562-2"><a href="signal-handling.html#cb562-2" aria-hidden="true" tabindex="-1"></a>function    indicates we're              and</span>
<span id="cb562-3"><a href="signal-handling.html#cb562-3" aria-hidden="true" tabindex="-1"></a>returns     returning a                  that function</span>
<span id="cb562-4"><a href="signal-handling.html#cb562-4" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span>        pointer to function          takes an <span class="dt">int</span></span>
<span id="cb562-5"><a href="signal-handling.html#cb562-5" aria-hidden="true" tabindex="-1"></a><span class="op">|--|</span>        <span class="op">|</span>                                   <span class="op">|---|</span></span>
<span id="cb562-6"><a href="signal-handling.html#cb562-6" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span>       <span class="op">(*</span>signal<span class="op">(</span><span class="dt">int</span> sig<span class="op">,</span> <span class="dt">void</span> <span class="op">(*</span>func<span class="op">)(</span><span class="dt">int</span><span class="op">)))(</span><span class="dt">int</span><span class="op">);</span></span></code></pre></div>
<p>Also, it can return <code>SIG_ERR</code> in case of an error.</p>
<p>Let’s do an example where we make it so you have to hit
<code>CTRL-C</code> twice to exit.</p>
<p>I want to be clear that this program engages in undefined behavior in
a couple ways. But it’ll probably work for you, and it’s hard to come up
with portable non-trivial demos.</p>
<p> </p>
<div class="sourceCode" id="cb563"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb563-1"><a href="signal-handling.html#cb563-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb563-2"><a href="signal-handling.html#cb563-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb563-3"><a href="signal-handling.html#cb563-3"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb563-4"><a href="signal-handling.html#cb563-4"></a></span>
<span id="cb563-5"><a href="signal-handling.html#cb563-5"></a><span class="dt">int</span> count <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb563-6"><a href="signal-handling.html#cb563-6"></a></span>
<span id="cb563-7"><a href="signal-handling.html#cb563-7"></a><span class="dt">void</span> sigint_handler<span class="op">(</span><span class="dt">int</span> signum<span class="op">)</span></span>
<span id="cb563-8"><a href="signal-handling.html#cb563-8"></a><span class="op">{</span></span>
<span id="cb563-9"><a href="signal-handling.html#cb563-9"></a>    <span class="co">// The compiler is allowed to run:</span></span>
<span id="cb563-10"><a href="signal-handling.html#cb563-10"></a>    <span class="co">//</span></span>
<span id="cb563-11"><a href="signal-handling.html#cb563-11"></a>    <span class="co">//   signal(signum, SIG_DFL)</span></span>
<span id="cb563-12"><a href="signal-handling.html#cb563-12"></a>    <span class="co">//</span></span>
<span id="cb563-13"><a href="signal-handling.html#cb563-13"></a>    <span class="co">// when the handler is called. So we reset the handler here:</span></span>
<span id="cb563-14"><a href="signal-handling.html#cb563-14"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> sigint_handler<span class="op">);</span></span>
<span id="cb563-15"><a href="signal-handling.html#cb563-15"></a></span>
<span id="cb563-16"><a href="signal-handling.html#cb563-16"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>signum<span class="op">;</span>   <span class="co">// Get rid of unused variable warning</span></span>
<span id="cb563-17"><a href="signal-handling.html#cb563-17"></a></span>
<span id="cb563-18"><a href="signal-handling.html#cb563-18"></a>    count<span class="op">++;</span>                       <span class="co">// Undefined behavior</span></span>
<span id="cb563-19"><a href="signal-handling.html#cb563-19"></a>    printf<span class="op">(</span><span class="st">"Count: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> count<span class="op">);</span>  <span class="co">// Undefined behavior</span></span>
<span id="cb563-20"><a href="signal-handling.html#cb563-20"></a></span>
<span id="cb563-21"><a href="signal-handling.html#cb563-21"></a>    <span class="cf">if</span> <span class="op">(</span>count <span class="op">==</span> <span class="dv">2</span><span class="op">)</span> <span class="op">{</span></span>
<span id="cb563-22"><a href="signal-handling.html#cb563-22"></a>        printf<span class="op">(</span><span class="st">"Exiting!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span>      <span class="co">// Undefined behavior</span></span>
<span id="cb563-23"><a href="signal-handling.html#cb563-23"></a>        exit<span class="op">(</span><span class="dv">0</span><span class="op">);</span></span>
<span id="cb563-24"><a href="signal-handling.html#cb563-24"></a>    <span class="op">}</span></span>
<span id="cb563-25"><a href="signal-handling.html#cb563-25"></a><span class="op">}</span></span>
<span id="cb563-26"><a href="signal-handling.html#cb563-26"></a></span>
<span id="cb563-27"><a href="signal-handling.html#cb563-27"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb563-28"><a href="signal-handling.html#cb563-28"></a><span class="op">{</span></span>
<span id="cb563-29"><a href="signal-handling.html#cb563-29"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> sigint_handler<span class="op">);</span></span>
<span id="cb563-30"><a href="signal-handling.html#cb563-30"></a></span>
<span id="cb563-31"><a href="signal-handling.html#cb563-31"></a>    printf<span class="op">(</span><span class="st">"Try hitting ^C...</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb563-32"><a href="signal-handling.html#cb563-32"></a></span>
<span id="cb563-33"><a href="signal-handling.html#cb563-33"></a>    <span class="cf">for</span><span class="op">(;;);</span>  <span class="co">// Wait here forever</span></span>
<span id="cb563-34"><a href="signal-handling.html#cb563-34"></a><span class="op">}</span></span></code></pre></div>
<p></p>
<p>One of the things you’ll notice is that on line 14 we reset the
signal handler. This is because C has the option of resetting the signal
handler to its <code>SIG_DFL</code> behavior before running your custom
handler. In other words, it could be a one-off. So we reset it first
thing so that we handle it again for the next one.</p>
<p>We’re ignoring the return value from <code>signal()</code> in this
case. If we’d set it to a different handler earlier, it would return a
pointer to that handler, which we could get like this:</p>
<div class="sourceCode" id="cb564"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb564-1"><a href="signal-handling.html#cb564-1" aria-hidden="true" tabindex="-1"></a><span class="co">// old_handler is type "pointer to function that takes a single</span></span>
<span id="cb564-2"><a href="signal-handling.html#cb564-2" aria-hidden="true" tabindex="-1"></a><span class="co">// int parameter and returns void":</span></span>
<span id="cb564-3"><a href="signal-handling.html#cb564-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb564-4"><a href="signal-handling.html#cb564-4" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">(*</span>old_handler<span class="op">)(</span><span class="dt">int</span><span class="op">);</span></span>
<span id="cb564-5"><a href="signal-handling.html#cb564-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb564-6"><a href="signal-handling.html#cb564-6" aria-hidden="true" tabindex="-1"></a>old_handler <span class="op">=</span> signal<span class="op">(</span>SIGINT<span class="op">,</span> sigint_handler<span class="op">);</span></span></code></pre></div>
<p></p>
<p>That said, I’m not sure of a common use case for this. But if you
need the old handler for some reason, you can get it that way.</p>
<p>Quick note on line 16—that’s just to tell the compiler to not warn
that we’re not using this variable. It’s like saying, “I know I’m not
using it; you don’t have to warn me.”</p>
<p>And lastly you’ll see that I’ve marked undefined behavior in a couple
places. More on that in the next section.</p>
<h2 data-number="29.4" id="what-can-we-actually-do"><span class="header-section-number">29.4</span> What Can We Actually Do?</h2>
<p>Turns out we’re pretty limited in what we can and can’t do in our
signal handlers. This is one of the reasons why I say you shouldn’t even
bother with this and instead use your OS’s signal handling instead (e.g.
<code>sigaction()</code> for Unix-like systems).</p>
<p>Wikipedia goes so far as to say the only really portable thing you
can do is call <code>signal()</code> with <code>SIG_IGN</code> or
<code>SIG_DFL</code> and that’s it.</p>
<p>Here’s what we <strong>can’t</strong> portably do:</p>
<p></p>
<ul>
<li>Call any standard library function.
<ul>
<li>Like <code>printf()</code>, for example.</li>
<li>I think it’s probably safe to call restartable/reentrant functions,
but the spec doesn’t allow that liberty.</li>
</ul></li>
<li>Get or set values from a local <code>static</code>, file scope, or
thread-local variable.
<ul>
<li>Unless it’s a lock-free atomic object or…</li>
<li>You’re assigning into a variable of type
<code>volatile sig_atomic_t</code>.</li>
</ul></li>
</ul>
<p></p>
<p>That last bit–<code>sig_atomic_t</code>–is your ticket to getting
data out of a signal handler. (Unless you want to use lock-free atomic
objects, which is outside the scope of this section<a href="footnotes.html#fn160" class="footnote-ref" id="fnref160" role="doc-noteref"><sup>160</sup></a>.) It’s an integer type that might
or might not be signed. And it’s bounded by what you can put in
there.</p>
<p>You can look at the minimum and maximum allowable values in the
macros <code>SIG_ATOMIC_MIN</code> and <code>SIG_ATOMIC_MAX</code><a href="#fn161" class="footnote-ref" id="fnref161" role="doc-noteref"><sup>161</sup></a>.</p>
<p>Confusingly, the spec also says you can’t refer “to any object with
static or thread storage duration that is not a lock-free atomic object
other than by assigning a value to an object declared as
<code>volatile sig_atomic_t</code> […]”</p>
<p>My read on this is that you can’t read or write anything that’s not a
lock-free atomic object. Also you can assign to an object that’s
<code>volatile sig_atomic_t</code>.</p>
<p>But can you read from it? I honestly don’t see why not, except that
the spec is very pointed about mentioning assigning into. But if you
have to read it and make any kind of decision based on it, you might be
opening up room for some kind of race conditions.</p>
<p></p>
<p>With that in mind, we can rewrite our “hit <code>CTRL-C</code> twice
to exit” code to be a little more portable, albeit less verbose on the
output.</p>
<p>Let’s change our <code>SIGINT</code> handler to do nothing except
increment a value that’s of type <code>volatile sig_atomic_t</code>. So
it’ll count the number of <code>CTRL-C</code>s that have been hit.</p>
<p>Then in our main loop, we’ll check to see if that counter is over
<code>2</code>, then bail out if it is.</p>
<div class="sourceCode" id="cb565"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb565-1"><a href="signal-handling.html#cb565-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb565-2"><a href="signal-handling.html#cb565-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb565-3"><a href="signal-handling.html#cb565-3"></a></span>
<span id="cb565-4"><a href="signal-handling.html#cb565-4"></a><span class="dt">volatile</span> <span class="dt">sig_atomic_t</span> count <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb565-5"><a href="signal-handling.html#cb565-5"></a></span>
<span id="cb565-6"><a href="signal-handling.html#cb565-6"></a><span class="dt">void</span> sigint_handler<span class="op">(</span><span class="dt">int</span> signum<span class="op">)</span></span>
<span id="cb565-7"><a href="signal-handling.html#cb565-7"></a><span class="op">{</span></span>
<span id="cb565-8"><a href="signal-handling.html#cb565-8"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>signum<span class="op">;</span>                    <span class="co">// Unused variable warning</span></span>
<span id="cb565-9"><a href="signal-handling.html#cb565-9"></a></span>
<span id="cb565-10"><a href="signal-handling.html#cb565-10"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> sigint_handler<span class="op">);</span>  <span class="co">// Reset signal handler</span></span>
<span id="cb565-11"><a href="signal-handling.html#cb565-11"></a></span>
<span id="cb565-12"><a href="signal-handling.html#cb565-12"></a>    count<span class="op">++;</span>                         <span class="co">// Undefined behavior</span></span>
<span id="cb565-13"><a href="signal-handling.html#cb565-13"></a><span class="op">}</span></span>
<span id="cb565-14"><a href="signal-handling.html#cb565-14"></a></span>
<span id="cb565-15"><a href="signal-handling.html#cb565-15"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb565-16"><a href="signal-handling.html#cb565-16"></a><span class="op">{</span></span>
<span id="cb565-17"><a href="signal-handling.html#cb565-17"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> sigint_handler<span class="op">);</span></span>
<span id="cb565-18"><a href="signal-handling.html#cb565-18"></a></span>
<span id="cb565-19"><a href="signal-handling.html#cb565-19"></a>    printf<span class="op">(</span><span class="st">"Hit ^C twice to exit.</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb565-20"><a href="signal-handling.html#cb565-20"></a></span>
<span id="cb565-21"><a href="signal-handling.html#cb565-21"></a>    <span class="cf">while</span><span class="op">(</span>count <span class="op">&lt;</span> <span class="dv">2</span><span class="op">);</span></span>
<span id="cb565-22"><a href="signal-handling.html#cb565-22"></a><span class="op">}</span></span></code></pre></div>
<p></p>
<p>Undefined behavior again? It’s my read that this is, because we have
to read the value in order to increment and store it.</p>
<p>If we only want to postpone the exit by one hitting of
<code>CTRL-C</code>, we can do that without too much trouble. But any
more postponement would require some ridiculous function chaining.</p>
<p>What we’ll do is handle it once, and the handler will reset the
signal to its default behavior (that is, to exit):</p>
<p></p>
<div class="sourceCode" id="cb566"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb566-1"><a href="signal-handling.html#cb566-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb566-2"><a href="signal-handling.html#cb566-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb566-3"><a href="signal-handling.html#cb566-3"></a></span>
<span id="cb566-4"><a href="signal-handling.html#cb566-4"></a><span class="dt">void</span> sigint_handler<span class="op">(</span><span class="dt">int</span> signum<span class="op">)</span></span>
<span id="cb566-5"><a href="signal-handling.html#cb566-5"></a><span class="op">{</span></span>
<span id="cb566-6"><a href="signal-handling.html#cb566-6"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>signum<span class="op">;</span>                      <span class="co">// Unused variable warning</span></span>
<span id="cb566-7"><a href="signal-handling.html#cb566-7"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> SIG_DFL<span class="op">);</span>           <span class="co">// Reset signal handler</span></span>
<span id="cb566-8"><a href="signal-handling.html#cb566-8"></a><span class="op">}</span></span>
<span id="cb566-9"><a href="signal-handling.html#cb566-9"></a></span>
<span id="cb566-10"><a href="signal-handling.html#cb566-10"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb566-11"><a href="signal-handling.html#cb566-11"></a><span class="op">{</span></span>
<span id="cb566-12"><a href="signal-handling.html#cb566-12"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> sigint_handler<span class="op">);</span></span>
<span id="cb566-13"><a href="signal-handling.html#cb566-13"></a></span>
<span id="cb566-14"><a href="signal-handling.html#cb566-14"></a>    printf<span class="op">(</span><span class="st">"Hit ^C twice to exit.</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb566-15"><a href="signal-handling.html#cb566-15"></a></span>
<span id="cb566-16"><a href="signal-handling.html#cb566-16"></a>    <span class="cf">while</span><span class="op">(</span><span class="dv">1</span><span class="op">);</span></span>
<span id="cb566-17"><a href="signal-handling.html#cb566-17"></a><span class="op">}</span></span></code></pre></div>
<p></p>
<p>Later when we look at lock-free atomic variables, we’ll see a way to
fix the <code>count</code> version (assuming lock-free atomic variables
are available on your particular system).</p>
<p>This is why at the beginning, I was suggesting checking out your OS’s
built-in signal system as a probably-superior alternative.</p>
<h2 data-number="29.5" id="friends-dont-let-friends-signal"><span class="header-section-number">29.5</span> Friends Don’t Let Friends
<code>signal()</code></h2>
<p>Again, use your OS’s built-in signal handling or the equivalent. It’s
not in the spec, not as portable, but probably is far more capable. Plus
your OS probably has a number of signals defined that aren’t in the C
spec. And it’s difficult to write portable code using
<code>signal()</code> anyway.</p>
<p> </p>
<!-- Beej's guide to C

# vim: ts=4:sw=4:nosi:et:tw=72
-->
<hr>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="exiting-a-program.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="variable-length-arrays-vlas.html">Next»</a></div>

</body>