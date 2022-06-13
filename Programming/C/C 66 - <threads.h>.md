<body>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="tgmath.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="time.html">Next»</a></div>
<hr>
<h1 data-number="66" id="threads"><span class="header-section-number">66</span> <code>&lt;threads.h&gt;</code>
Multithreading Functions</h1>
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
<td><a href="threads.html#man-call_once"><code>call_once()</code></a></td>
<td>Call a function one time no matter how many threads try</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-cnd_broadcast"><code>cnd_broadcast()</code></a></td>
<td>Wake up all threads waiting on a condition variable</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-cnd_destroy"><code>cnd_destroy()</code></a></td>
<td>Free up resources from a condition variable</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-cnd_init"><code>cnd_init()</code></a></td>
<td>Initialize a condition variable to make it ready for use</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-cnd_signal"><code>cnd_signal()</code></a></td>
<td>Wake up a thread waiting on a condition variable</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-cnd_timedwait"><code>cnd_timedwait()</code></a></td>
<td>Wait on a condition variable with a timeout</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-cnd_wait"><code>cnd_wait()</code></a></td>
<td>Wait for a signal on a condition variable</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-mtx_destroy"><code>mtx_destroy()</code></a></td>
<td>Cleanup a mutex when done with it</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-mtx_init"><code>mtx_init()</code></a></td>
<td>Initialize a mutex for use</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-mtx_lock"><code>mtx_lock()</code></a></td>
<td>Acquire a lock on a mutex</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-mtx_timedlock"><code>mtx_timedlock()</code></a></td>
<td>Lock a mutex allowing for timeout</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-mtx_trylock"><code>mtx_trylock()</code></a></td>
<td>Try to lock a mutex, returning if not possible</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-mtx_unlock"><code>mtx_unlock()</code></a></td>
<td>Free a mutex when you’re done with the critical section</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-thrd_create"><code>thrd_create()</code></a></td>
<td>Create a new thread of execution</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-thrd_current"><code>thrd_current()</code></a></td>
<td>Get the ID of the calling thread</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-thrd_detach"><code>thrd_detach()</code></a></td>
<td>Automatically clean up threads when they exit</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-thrd_equal"><code>thrd_equal()</code></a></td>
<td>Compare two thread descriptors for equality</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-thrd_exit"><code>thrd_exit()</code></a></td>
<td>Stop and exit this thread</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-thrd_join"><code>thrd_join()</code></a></td>
<td>Wait for a thread to exit</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-thrd_yield"><code>thrd_yield()</code></a></td>
<td>Stop running that other threads might run</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-tss_create"><code>tss_create()</code></a></td>
<td>Create new thread-specific storage</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-tss_delete"><code>tss_delete()</code></a></td>
<td>Clean up a thread-specific storage variable</td>
</tr>
<tr class="odd">
<td><a href="threads.html#man-tss_get"><code>tss_get()</code></a></td>
<td>Get thread-specific data</td>
</tr>
<tr class="even">
<td><a href="threads.html#man-tss_set"><code>tss_set()</code></a></td>
<td>Set thread-specific data</td>
</tr>
</tbody>
</table>
<p>We have a bunch of good things at our disposal with this one:</p>
<ul>
<li>Threads</li>
<li>Mutexes</li>
<li>Condition Variables</li>
<li>Thread-Specific Storage</li>
<li>And, last but not least, the always-fun <code>call_once()</code>
function!</li>
</ul>
<p>Enjoy!</p>
<hr>
<h2 data-number="66.1" id="man-call_once"><span class="header-section-number">66.1</span> <code>call_once()</code></h2>
<p>Call a function one time no matter how many threads try</p>
<h3 class="unnumbered unlisted" id="synopsis-198">Synopsis</h3>
<div class="sourceCode" id="cb1410"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1410-1"><a href="threads.html#cb1410-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1410-2"><a href="threads.html#cb1410-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1410-3"><a href="threads.html#cb1410-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> call_once<span class="op">(</span>once_flag <span class="op">*</span>flag<span class="op">,</span> <span class="dt">void</span> <span class="op">(*</span>func<span class="op">)(</span><span class="dt">void</span><span class="op">));</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-198">Description</h3>
<p>If you have a bunch of threads running over the same piece of code
that calls a function, but you only want that function to run one time,
<code>call_once()</code> can help you out.</p>
<p>The catch is the function that is called doesn’t return anything and
takes no arguments.</p>
<p>If you need more than that, you’ll have to set a threadsafe flag such
as <code>atomic_flag</code>, or one that you protect with a mutex.</p>
<p>To use this, you need to pass it a pointer to a function to execute,
<code>func</code>, and also a pointer to a flag of type
<code>once_flag</code>.</p>
<p><code>once_flag</code> is an opaque type, so all you need to know is
that you initialize it to the value <code>ONCE_FLAG_INIT</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-196">Return Value</h3>
<p>Returns nothing.</p>
<h3 class="unnumbered unlisted" id="example-200">Example</h3>
<div class="sourceCode" id="cb1411"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1411-1"><a href="threads.html#cb1411-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1411-2"><a href="threads.html#cb1411-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1411-3"><a href="threads.html#cb1411-3"></a></span>
<span id="cb1411-4"><a href="threads.html#cb1411-4"></a>once_flag of <span class="op">=</span> ONCE_FLAG_INIT<span class="op">;</span>  <span class="co">// Initialize it like this</span></span>
<span id="cb1411-5"><a href="threads.html#cb1411-5"></a></span>
<span id="cb1411-6"><a href="threads.html#cb1411-6"></a><span class="dt">void</span> run_once_function<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1411-7"><a href="threads.html#cb1411-7"></a><span class="op">{</span></span>
<span id="cb1411-8"><a href="threads.html#cb1411-8"></a>    printf<span class="op">(</span><span class="st">"I'll only run once!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1411-9"><a href="threads.html#cb1411-9"></a><span class="op">}</span></span>
<span id="cb1411-10"><a href="threads.html#cb1411-10"></a></span>
<span id="cb1411-11"><a href="threads.html#cb1411-11"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1411-12"><a href="threads.html#cb1411-12"></a><span class="op">{</span></span>
<span id="cb1411-13"><a href="threads.html#cb1411-13"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1411-14"><a href="threads.html#cb1411-14"></a></span>
<span id="cb1411-15"><a href="threads.html#cb1411-15"></a>    printf<span class="op">(</span><span class="st">"Thread running!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1411-16"><a href="threads.html#cb1411-16"></a></span>
<span id="cb1411-17"><a href="threads.html#cb1411-17"></a>    call_once<span class="op">(&amp;</span>of<span class="op">,</span> run_once_function<span class="op">);</span></span>
<span id="cb1411-18"><a href="threads.html#cb1411-18"></a></span>
<span id="cb1411-19"><a href="threads.html#cb1411-19"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1411-20"><a href="threads.html#cb1411-20"></a><span class="op">}</span></span>
<span id="cb1411-21"><a href="threads.html#cb1411-21"></a></span>
<span id="cb1411-22"><a href="threads.html#cb1411-22"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1411-23"><a href="threads.html#cb1411-23"></a></span>
<span id="cb1411-24"><a href="threads.html#cb1411-24"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1411-25"><a href="threads.html#cb1411-25"></a><span class="op">{</span></span>
<span id="cb1411-26"><a href="threads.html#cb1411-26"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1411-27"><a href="threads.html#cb1411-27"></a></span>
<span id="cb1411-28"><a href="threads.html#cb1411-28"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1411-29"><a href="threads.html#cb1411-29"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1411-30"><a href="threads.html#cb1411-30"></a></span>
<span id="cb1411-31"><a href="threads.html#cb1411-31"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1411-32"><a href="threads.html#cb1411-32"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1411-33"><a href="threads.html#cb1411-33"></a><span class="op">}</span></span></code></pre></div>
<p>Output (might vary per run):</p>
<div class="sourceCode" id="cb1412"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1412-1"><a href="threads.html#cb1412-1" aria-hidden="true" tabindex="-1"></a>Thread running!</span>
<span id="cb1412-2"><a href="threads.html#cb1412-2" aria-hidden="true" tabindex="-1"></a>Thread running!</span>
<span id="cb1412-3"><a href="threads.html#cb1412-3" aria-hidden="true" tabindex="-1"></a>I'll only run once!</span>
<span id="cb1412-4"><a href="threads.html#cb1412-4" aria-hidden="true" tabindex="-1"></a>Thread running!</span>
<span id="cb1412-5"><a href="threads.html#cb1412-5" aria-hidden="true" tabindex="-1"></a>Thread running!</span>
<span id="cb1412-6"><a href="threads.html#cb1412-6" aria-hidden="true" tabindex="-1"></a>Thread running!</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="66.2" id="man-cnd_broadcast"><span class="header-section-number">66.2</span>
<code>cnd_broadcast()</code></h2>
<p>Wake up all threads waiting on a condition variable</p>
<h3 class="unnumbered unlisted" id="synopsis-199">Synopsis</h3>
<div class="sourceCode" id="cb1413"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1413-1"><a href="threads.html#cb1413-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1413-2"><a href="threads.html#cb1413-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1413-3"><a href="threads.html#cb1413-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> cnd_broadcast<span class="op">(</span>cnd_t <span class="op">*</span>cond<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-199">Description</h3>
<p>This is just like <code>cnd_signal()</code> in that it wakes up
threads that are waiting on a condition variable…. except instead of
just rousing one thread, it wakes them all.</p>
<p>Of course, only one will get the mutex, and the rest will have to
wait their turn. But instead of being asleep waiting for a signal,
they’ll be asleep waiting to reacquire the mutex. They’re rearin’ to go,
in other words.</p>
<p>This can make a difference in a specific set of circumstances where
<code>cnd_signal()</code> might leave you hanging.</p>
<p>If you’re relying on subsequent threads to issue the next
<code>cnd_signal()</code>, but you have the <code>cnd_wait()</code> in a
<code>while</code> loop<a href="footnotes.html#fn272" class="footnote-ref" id="fnref272" role="doc-noteref"><sup>272</sup></a> that doesn’t allow
any threads to escape, you’ll be stuck. No more threads will be woken up
from the wait.</p>
<p>But if you <code>cnd_broadcast()</code>, all the threads will be
woken, and presumably at least one of them will be allowed to escape the
<code>while</code> loop, freeing it up to broadcast the next wakeup when
its work is done.</p>
<h3 class="unnumbered unlisted" id="return-value-197">Return Value</h3>
<p>Returns <code>thrd_success</code> or <code>thrd_error</code>
depending on how well things went.</p>
<h3 class="unnumbered unlisted" id="example-201">Example</h3>
<p>In the example below, we launch a bunch of threads, but they’re only
allowed to run if their ID matches the current ID. If it doesn’t, they
go back to waiting.</p>
<p>If you <code>cnd_signal()</code> to wake the next thread, it might
not be the one with the proper ID to run. If it’s not, it goes back to
sleep and we hang (because no thread is awake to hit
<code>cnd_signal()</code> again).</p>
<p>But if you <code>cnd_broadcast()</code> to wake them all, then
they’ll all try (one after another) to get out of the <code>while</code>
loop. And one of them will make it.</p>
<p>Try switching the <code>cnd_broadcast()</code> to
<code>cnd_signal()</code> to see likely deadlocks. It doesn’t happen
every time, but usually does.</p>
<div class="sourceCode" id="cb1414"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1414-1"><a href="threads.html#cb1414-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1414-2"><a href="threads.html#cb1414-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1414-3"><a href="threads.html#cb1414-3"></a></span>
<span id="cb1414-4"><a href="threads.html#cb1414-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1414-5"><a href="threads.html#cb1414-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1414-6"><a href="threads.html#cb1414-6"></a></span>
<span id="cb1414-7"><a href="threads.html#cb1414-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1414-8"><a href="threads.html#cb1414-8"></a><span class="op">{</span></span>
<span id="cb1414-9"><a href="threads.html#cb1414-9"></a>    <span class="dt">int</span> id <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span></span>
<span id="cb1414-10"><a href="threads.html#cb1414-10"></a></span>
<span id="cb1414-11"><a href="threads.html#cb1414-11"></a>    <span class="dt">static</span> <span class="dt">int</span> current_id <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1414-12"><a href="threads.html#cb1414-12"></a></span>
<span id="cb1414-13"><a href="threads.html#cb1414-13"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1414-14"><a href="threads.html#cb1414-14"></a></span>
<span id="cb1414-15"><a href="threads.html#cb1414-15"></a>    <span class="cf">while</span> <span class="op">(</span>id <span class="op">!=</span> current_id<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1414-16"><a href="threads.html#cb1414-16"></a>        printf<span class="op">(</span><span class="st">"THREAD %d: waiting</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">);</span></span>
<span id="cb1414-17"><a href="threads.html#cb1414-17"></a>        cnd_wait<span class="op">(&amp;</span>condvar<span class="op">,</span> <span class="op">&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1414-18"><a href="threads.html#cb1414-18"></a></span>
<span id="cb1414-19"><a href="threads.html#cb1414-19"></a>        <span class="cf">if</span> <span class="op">(</span>id <span class="op">!=</span> current_id<span class="op">)</span></span>
<span id="cb1414-20"><a href="threads.html#cb1414-20"></a>            printf<span class="op">(</span><span class="st">"THREAD %d: woke up, but it's not my turn!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">);</span></span>
<span id="cb1414-21"><a href="threads.html#cb1414-21"></a>        <span class="cf">else</span></span>
<span id="cb1414-22"><a href="threads.html#cb1414-22"></a>            printf<span class="op">(</span><span class="st">"THREAD %d: woke up, my turn! Let's go!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">);</span></span>
<span id="cb1414-23"><a href="threads.html#cb1414-23"></a>    <span class="op">}</span></span>
<span id="cb1414-24"><a href="threads.html#cb1414-24"></a></span>
<span id="cb1414-25"><a href="threads.html#cb1414-25"></a>    current_id<span class="op">++;</span></span>
<span id="cb1414-26"><a href="threads.html#cb1414-26"></a></span>
<span id="cb1414-27"><a href="threads.html#cb1414-27"></a>    printf<span class="op">(</span><span class="st">"THREAD %d: signaling thread %d to run</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">,</span> current_id<span class="op">);</span></span>
<span id="cb1414-28"><a href="threads.html#cb1414-28"></a></span>
<span id="cb1414-29"><a href="threads.html#cb1414-29"></a>    <span class="co">//cnd_signal(&amp;condvar);</span></span>
<span id="cb1414-30"><a href="threads.html#cb1414-30"></a>    cnd_broadcast<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1414-31"><a href="threads.html#cb1414-31"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1414-32"><a href="threads.html#cb1414-32"></a></span>
<span id="cb1414-33"><a href="threads.html#cb1414-33"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1414-34"><a href="threads.html#cb1414-34"></a><span class="op">}</span></span>
<span id="cb1414-35"><a href="threads.html#cb1414-35"></a></span>
<span id="cb1414-36"><a href="threads.html#cb1414-36"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1414-37"><a href="threads.html#cb1414-37"></a></span>
<span id="cb1414-38"><a href="threads.html#cb1414-38"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1414-39"><a href="threads.html#cb1414-39"></a><span class="op">{</span></span>
<span id="cb1414-40"><a href="threads.html#cb1414-40"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1414-41"><a href="threads.html#cb1414-41"></a>    <span class="dt">int</span> id<span class="op">[]</span> <span class="op">=</span> <span class="op">{</span><span class="dv">4</span><span class="op">,</span> <span class="dv">3</span><span class="op">,</span> <span class="dv">2</span><span class="op">,</span> <span class="dv">1</span><span class="op">,</span> <span class="dv">0</span><span class="op">};</span></span>
<span id="cb1414-42"><a href="threads.html#cb1414-42"></a></span>
<span id="cb1414-43"><a href="threads.html#cb1414-43"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1414-44"><a href="threads.html#cb1414-44"></a>    cnd_init<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1414-45"><a href="threads.html#cb1414-45"></a></span>
<span id="cb1414-46"><a href="threads.html#cb1414-46"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1414-47"><a href="threads.html#cb1414-47"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> id <span class="op">+</span> i<span class="op">);</span></span>
<span id="cb1414-48"><a href="threads.html#cb1414-48"></a></span>
<span id="cb1414-49"><a href="threads.html#cb1414-49"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1414-50"><a href="threads.html#cb1414-50"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1414-51"><a href="threads.html#cb1414-51"></a></span>
<span id="cb1414-52"><a href="threads.html#cb1414-52"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1414-53"><a href="threads.html#cb1414-53"></a>    cnd_destroy<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1414-54"><a href="threads.html#cb1414-54"></a><span class="op">}</span></span></code></pre></div>
<p>Example run with <code>cnd_broadcast()</code>:</p>
<div class="sourceCode" id="cb1415"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1415-1"><a href="threads.html#cb1415-1" aria-hidden="true" tabindex="-1"></a>THREAD 4: waiting</span>
<span id="cb1415-2"><a href="threads.html#cb1415-2" aria-hidden="true" tabindex="-1"></a>THREAD 1: waiting</span>
<span id="cb1415-3"><a href="threads.html#cb1415-3" aria-hidden="true" tabindex="-1"></a>THREAD 3: waiting</span>
<span id="cb1415-4"><a href="threads.html#cb1415-4" aria-hidden="true" tabindex="-1"></a>THREAD 2: waiting</span>
<span id="cb1415-5"><a href="threads.html#cb1415-5" aria-hidden="true" tabindex="-1"></a>THREAD 0: signaling thread 1 to run</span>
<span id="cb1415-6"><a href="threads.html#cb1415-6" aria-hidden="true" tabindex="-1"></a>THREAD 2: woke up, but it's not my turn!</span>
<span id="cb1415-7"><a href="threads.html#cb1415-7" aria-hidden="true" tabindex="-1"></a>THREAD 2: waiting</span>
<span id="cb1415-8"><a href="threads.html#cb1415-8" aria-hidden="true" tabindex="-1"></a>THREAD 4: woke up, but it's not my turn!</span>
<span id="cb1415-9"><a href="threads.html#cb1415-9" aria-hidden="true" tabindex="-1"></a>THREAD 4: waiting</span>
<span id="cb1415-10"><a href="threads.html#cb1415-10" aria-hidden="true" tabindex="-1"></a>THREAD 3: woke up, but it's not my turn!</span>
<span id="cb1415-11"><a href="threads.html#cb1415-11" aria-hidden="true" tabindex="-1"></a>THREAD 3: waiting</span>
<span id="cb1415-12"><a href="threads.html#cb1415-12" aria-hidden="true" tabindex="-1"></a>THREAD 1: woke up, my turn! Let's go!</span>
<span id="cb1415-13"><a href="threads.html#cb1415-13" aria-hidden="true" tabindex="-1"></a>THREAD 1: signaling thread 2 to run</span>
<span id="cb1415-14"><a href="threads.html#cb1415-14" aria-hidden="true" tabindex="-1"></a>THREAD 4: woke up, but it's not my turn!</span>
<span id="cb1415-15"><a href="threads.html#cb1415-15" aria-hidden="true" tabindex="-1"></a>THREAD 4: waiting</span>
<span id="cb1415-16"><a href="threads.html#cb1415-16" aria-hidden="true" tabindex="-1"></a>THREAD 3: woke up, but it's not my turn!</span>
<span id="cb1415-17"><a href="threads.html#cb1415-17" aria-hidden="true" tabindex="-1"></a>THREAD 3: waiting</span>
<span id="cb1415-18"><a href="threads.html#cb1415-18" aria-hidden="true" tabindex="-1"></a>THREAD 2: woke up, my turn! Let's go!</span>
<span id="cb1415-19"><a href="threads.html#cb1415-19" aria-hidden="true" tabindex="-1"></a>THREAD 2: signaling thread 3 to run</span>
<span id="cb1415-20"><a href="threads.html#cb1415-20" aria-hidden="true" tabindex="-1"></a>THREAD 4: woke up, but it's not my turn!</span>
<span id="cb1415-21"><a href="threads.html#cb1415-21" aria-hidden="true" tabindex="-1"></a>THREAD 4: waiting</span>
<span id="cb1415-22"><a href="threads.html#cb1415-22" aria-hidden="true" tabindex="-1"></a>THREAD 3: woke up, my turn! Let's go!</span>
<span id="cb1415-23"><a href="threads.html#cb1415-23" aria-hidden="true" tabindex="-1"></a>THREAD 3: signaling thread 4 to run</span>
<span id="cb1415-24"><a href="threads.html#cb1415-24" aria-hidden="true" tabindex="-1"></a>THREAD 4: woke up, my turn! Let's go!</span>
<span id="cb1415-25"><a href="threads.html#cb1415-25" aria-hidden="true" tabindex="-1"></a>THREAD 4: signaling thread 5 to run</span></code></pre></div>
<p>Example run with <code>cnd_signal()</code>:</p>
<div class="sourceCode" id="cb1416"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1416-1"><a href="threads.html#cb1416-1" aria-hidden="true" tabindex="-1"></a>THREAD 4: waiting</span>
<span id="cb1416-2"><a href="threads.html#cb1416-2" aria-hidden="true" tabindex="-1"></a>THREAD 1: waiting</span>
<span id="cb1416-3"><a href="threads.html#cb1416-3" aria-hidden="true" tabindex="-1"></a>THREAD 3: waiting</span>
<span id="cb1416-4"><a href="threads.html#cb1416-4" aria-hidden="true" tabindex="-1"></a>THREAD 2: waiting</span>
<span id="cb1416-5"><a href="threads.html#cb1416-5" aria-hidden="true" tabindex="-1"></a>THREAD 0: signaling thread 1 to run</span>
<span id="cb1416-6"><a href="threads.html#cb1416-6" aria-hidden="true" tabindex="-1"></a>THREAD 4: woke up, but it's not my turn!</span>
<span id="cb1416-7"><a href="threads.html#cb1416-7" aria-hidden="true" tabindex="-1"></a>THREAD 4: waiting</span>
<span id="cb1416-8"><a href="threads.html#cb1416-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1416-9"><a href="threads.html#cb1416-9" aria-hidden="true" tabindex="-1"></a>[deadlock at this point]</span></code></pre></div>
<p>See how <code>THREAD 0</code> signaled that it was
<code>THREAD 1</code>’s turn? But—bad news—it was <code>THREAD 4</code>
that got woken up. So no one continued the process.
<code>cnd_broadcast()</code> would have woken them all, so eventually
<code>THREAD 1</code> would have run, gotten out of the
<code>while</code>, and broadcast for the next thread to run.</p>
<h3 class="unnumbered unlisted" id="see-also-187">See Also</h3>
<p><a href="signal.html#man-signal"><code>cnd_signal()</code></a>, <a href="#man-mtx_lock"><code>mtx_lock()</code></a>, <a href="#man-mtx_unlock"><code>mtx_unlock()</code></a></p>
<hr>
<h2 data-number="66.3" id="man-cnd_destroy"><span class="header-section-number">66.3</span>
<code>cnd_destroy()</code></h2>
<p>Free up resources from a condition variable</p>
<h3 class="unnumbered unlisted" id="synopsis-200">Synopsis</h3>
<div class="sourceCode" id="cb1417"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1417-1"><a href="threads.html#cb1417-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1417-2"><a href="threads.html#cb1417-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1417-3"><a href="threads.html#cb1417-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> cnd_destroy<span class="op">(</span>cnd_t <span class="op">*</span>cond<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-200">Description</h3>
<p>This is the opposite of <code>cnd_init()</code> and should be called
when all threads are done using a condition variable.</p>
<h3 class="unnumbered unlisted" id="return-value-198">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-202">Example</h3>
<p>General-purpose condition variable example here, but you can see the
<code>cnd_destroy()</code> down at the end.</p>
<div class="sourceCode" id="cb1418"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1418-1"><a href="threads.html#cb1418-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1418-2"><a href="threads.html#cb1418-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1418-3"><a href="threads.html#cb1418-3"></a></span>
<span id="cb1418-4"><a href="threads.html#cb1418-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1418-5"><a href="threads.html#cb1418-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1418-6"><a href="threads.html#cb1418-6"></a></span>
<span id="cb1418-7"><a href="threads.html#cb1418-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1418-8"><a href="threads.html#cb1418-8"></a><span class="op">{</span></span>
<span id="cb1418-9"><a href="threads.html#cb1418-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1418-10"><a href="threads.html#cb1418-10"></a></span>
<span id="cb1418-11"><a href="threads.html#cb1418-11"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1418-12"><a href="threads.html#cb1418-12"></a></span>
<span id="cb1418-13"><a href="threads.html#cb1418-13"></a>    printf<span class="op">(</span><span class="st">"Thread: waiting...</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1418-14"><a href="threads.html#cb1418-14"></a>    cnd_wait<span class="op">(&amp;</span>condvar<span class="op">,</span> <span class="op">&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1418-15"><a href="threads.html#cb1418-15"></a>    printf<span class="op">(</span><span class="st">"Thread: running again!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1418-16"><a href="threads.html#cb1418-16"></a></span>
<span id="cb1418-17"><a href="threads.html#cb1418-17"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1418-18"><a href="threads.html#cb1418-18"></a></span>
<span id="cb1418-19"><a href="threads.html#cb1418-19"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1418-20"><a href="threads.html#cb1418-20"></a><span class="op">}</span></span>
<span id="cb1418-21"><a href="threads.html#cb1418-21"></a></span>
<span id="cb1418-22"><a href="threads.html#cb1418-22"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1418-23"><a href="threads.html#cb1418-23"></a><span class="op">{</span></span>
<span id="cb1418-24"><a href="threads.html#cb1418-24"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1418-25"><a href="threads.html#cb1418-25"></a></span>
<span id="cb1418-26"><a href="threads.html#cb1418-26"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1418-27"><a href="threads.html#cb1418-27"></a>    cnd_init<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1418-28"><a href="threads.html#cb1418-28"></a></span>
<span id="cb1418-29"><a href="threads.html#cb1418-29"></a>    printf<span class="op">(</span><span class="st">"Main creating thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1418-30"><a href="threads.html#cb1418-30"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1418-31"><a href="threads.html#cb1418-31"></a></span>
<span id="cb1418-32"><a href="threads.html#cb1418-32"></a>    <span class="co">// Sleep 0.1s to allow the other thread to wait</span></span>
<span id="cb1418-33"><a href="threads.html#cb1418-33"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_nsec<span class="op">=</span><span class="dv">100000000</span><span class="bu">L</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1418-34"><a href="threads.html#cb1418-34"></a></span>
<span id="cb1418-35"><a href="threads.html#cb1418-35"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1418-36"><a href="threads.html#cb1418-36"></a>    printf<span class="op">(</span><span class="st">"Main: signaling thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1418-37"><a href="threads.html#cb1418-37"></a>    cnd_signal<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1418-38"><a href="threads.html#cb1418-38"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1418-39"><a href="threads.html#cb1418-39"></a></span>
<span id="cb1418-40"><a href="threads.html#cb1418-40"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1418-41"><a href="threads.html#cb1418-41"></a></span>
<span id="cb1418-42"><a href="threads.html#cb1418-42"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1418-43"><a href="threads.html#cb1418-43"></a>    cnd_destroy<span class="op">(&amp;</span>condvar<span class="op">);</span>  <span class="co">// &lt;-- DESTROY CONDITION VARIABLE</span></span>
<span id="cb1418-44"><a href="threads.html#cb1418-44"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1419"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1419-1"><a href="threads.html#cb1419-1" aria-hidden="true" tabindex="-1"></a>Main creating thread</span>
<span id="cb1419-2"><a href="threads.html#cb1419-2" aria-hidden="true" tabindex="-1"></a>Thread: waiting...</span>
<span id="cb1419-3"><a href="threads.html#cb1419-3" aria-hidden="true" tabindex="-1"></a>Main: signaling thread</span>
<span id="cb1419-4"><a href="threads.html#cb1419-4" aria-hidden="true" tabindex="-1"></a>Thread: running again!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-188">See Also</h3>
<p><a href="threads.html#man-cnd_init"><code>cnd_init()</code></a></p>
<hr>
<h2 data-number="66.4" id="man-cnd_init"><span class="header-section-number">66.4</span> <code>cnd_init()</code></h2>
<p>Initialize a condition variable to make it ready for use</p>
<h3 class="unnumbered unlisted" id="synopsis-201">Synopsis</h3>
<div class="sourceCode" id="cb1420"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1420-1"><a href="threads.html#cb1420-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1420-2"><a href="threads.html#cb1420-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1420-3"><a href="threads.html#cb1420-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> cnd_init<span class="op">(</span>cnd_t <span class="op">*</span>cond<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-201">Description</h3>
<p>This is the opposite of <code>cnd_destroy()</code>. This prepares a
condition variable for use, doing behind-the-scenes work on it.</p>
<p>Don’t use a condition variable without calling this first!</p>
<h3 class="unnumbered unlisted" id="return-value-199">Return Value</h3>
<p>If all goes well, returns <code>thrd_success</code>. It all doesn’t
go well, it could return <code>thrd_nomem</code> if the system is out of
memory, or <code>thread_error</code> in the case of any other error.</p>
<h3 class="unnumbered unlisted" id="example-203">Example</h3>
<p>General-purpose condition variable example here, but you can see the
<code>cnd_init()</code> down at the start of <code>main()</code>.</p>
<div class="sourceCode" id="cb1421"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1421-1"><a href="threads.html#cb1421-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1421-2"><a href="threads.html#cb1421-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1421-3"><a href="threads.html#cb1421-3"></a></span>
<span id="cb1421-4"><a href="threads.html#cb1421-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1421-5"><a href="threads.html#cb1421-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1421-6"><a href="threads.html#cb1421-6"></a></span>
<span id="cb1421-7"><a href="threads.html#cb1421-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1421-8"><a href="threads.html#cb1421-8"></a><span class="op">{</span></span>
<span id="cb1421-9"><a href="threads.html#cb1421-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1421-10"><a href="threads.html#cb1421-10"></a></span>
<span id="cb1421-11"><a href="threads.html#cb1421-11"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1421-12"><a href="threads.html#cb1421-12"></a></span>
<span id="cb1421-13"><a href="threads.html#cb1421-13"></a>    printf<span class="op">(</span><span class="st">"Thread: waiting...</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1421-14"><a href="threads.html#cb1421-14"></a>    cnd_wait<span class="op">(&amp;</span>condvar<span class="op">,</span> <span class="op">&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1421-15"><a href="threads.html#cb1421-15"></a>    printf<span class="op">(</span><span class="st">"Thread: running again!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1421-16"><a href="threads.html#cb1421-16"></a></span>
<span id="cb1421-17"><a href="threads.html#cb1421-17"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1421-18"><a href="threads.html#cb1421-18"></a></span>
<span id="cb1421-19"><a href="threads.html#cb1421-19"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1421-20"><a href="threads.html#cb1421-20"></a><span class="op">}</span></span>
<span id="cb1421-21"><a href="threads.html#cb1421-21"></a></span>
<span id="cb1421-22"><a href="threads.html#cb1421-22"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1421-23"><a href="threads.html#cb1421-23"></a><span class="op">{</span></span>
<span id="cb1421-24"><a href="threads.html#cb1421-24"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1421-25"><a href="threads.html#cb1421-25"></a></span>
<span id="cb1421-26"><a href="threads.html#cb1421-26"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1421-27"><a href="threads.html#cb1421-27"></a>    cnd_init<span class="op">(&amp;</span>condvar<span class="op">);</span>      <span class="co">// &lt;-- INITIALIZE CONDITION VARIABLE</span></span>
<span id="cb1421-28"><a href="threads.html#cb1421-28"></a></span>
<span id="cb1421-29"><a href="threads.html#cb1421-29"></a>    printf<span class="op">(</span><span class="st">"Main creating thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1421-30"><a href="threads.html#cb1421-30"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1421-31"><a href="threads.html#cb1421-31"></a></span>
<span id="cb1421-32"><a href="threads.html#cb1421-32"></a>    <span class="co">// Sleep 0.1s to allow the other thread to wait</span></span>
<span id="cb1421-33"><a href="threads.html#cb1421-33"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_nsec<span class="op">=</span><span class="dv">100000000</span><span class="bu">L</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1421-34"><a href="threads.html#cb1421-34"></a></span>
<span id="cb1421-35"><a href="threads.html#cb1421-35"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1421-36"><a href="threads.html#cb1421-36"></a>    printf<span class="op">(</span><span class="st">"Main: signaling thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1421-37"><a href="threads.html#cb1421-37"></a>    cnd_signal<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1421-38"><a href="threads.html#cb1421-38"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1421-39"><a href="threads.html#cb1421-39"></a></span>
<span id="cb1421-40"><a href="threads.html#cb1421-40"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1421-41"><a href="threads.html#cb1421-41"></a></span>
<span id="cb1421-42"><a href="threads.html#cb1421-42"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1421-43"><a href="threads.html#cb1421-43"></a>    cnd_destroy<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1421-44"><a href="threads.html#cb1421-44"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1422"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1422-1"><a href="threads.html#cb1422-1" aria-hidden="true" tabindex="-1"></a>Main creating thread</span>
<span id="cb1422-2"><a href="threads.html#cb1422-2" aria-hidden="true" tabindex="-1"></a>Thread: waiting...</span>
<span id="cb1422-3"><a href="threads.html#cb1422-3" aria-hidden="true" tabindex="-1"></a>Main: signaling thread</span>
<span id="cb1422-4"><a href="threads.html#cb1422-4" aria-hidden="true" tabindex="-1"></a>Thread: running again!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-189">See Also</h3>
<p><a href="threads.html#man-cnd_destroy"><code>cnd_destroy()</code></a></p>
<hr>
<h2 data-number="66.5" id="man-cnd_signal"><span class="header-section-number">66.5</span> <code>cnd_signal()</code></h2>
<p>Wake up a thread waiting on a condition variable</p>
<h3 class="unnumbered unlisted" id="synopsis-202">Synopsis</h3>
<div class="sourceCode" id="cb1423"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1423-1"><a href="threads.html#cb1423-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1423-2"><a href="threads.html#cb1423-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1423-3"><a href="threads.html#cb1423-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> cnd_signal<span class="op">(</span>cnd_t <span class="op">*</span>cond<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-202">Description</h3>
<p>If you have a thread (or a bunch of threads) waiting on a condition
variable, this function will wake one of them up to run.</p>
<p>Compare to <code>cnd_broadcast()</code> that wakes up all the
threads. See the <a href="#man-cnd_broadcast"><code>cnd_broadcast()</code></a> page for more
information on when you’re want to use that versus this.</p>
<h3 class="unnumbered unlisted" id="return-value-200">Return Value</h3>
<p>Returns <code>thrd_success</code> or <code>thrd_error</code>
depending on how happy your program is.</p>
<h3 class="unnumbered unlisted" id="example-204">Example</h3>
<p>General-purpose condition variable example here, but you can see the
<code>cnd_signal()</code> in the middle of <code>main()</code>.</p>
<div class="sourceCode" id="cb1424"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1424-1"><a href="threads.html#cb1424-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1424-2"><a href="threads.html#cb1424-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1424-3"><a href="threads.html#cb1424-3"></a></span>
<span id="cb1424-4"><a href="threads.html#cb1424-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1424-5"><a href="threads.html#cb1424-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1424-6"><a href="threads.html#cb1424-6"></a></span>
<span id="cb1424-7"><a href="threads.html#cb1424-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1424-8"><a href="threads.html#cb1424-8"></a><span class="op">{</span></span>
<span id="cb1424-9"><a href="threads.html#cb1424-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1424-10"><a href="threads.html#cb1424-10"></a></span>
<span id="cb1424-11"><a href="threads.html#cb1424-11"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1424-12"><a href="threads.html#cb1424-12"></a></span>
<span id="cb1424-13"><a href="threads.html#cb1424-13"></a>    printf<span class="op">(</span><span class="st">"Thread: waiting...</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1424-14"><a href="threads.html#cb1424-14"></a>    cnd_wait<span class="op">(&amp;</span>condvar<span class="op">,</span> <span class="op">&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1424-15"><a href="threads.html#cb1424-15"></a>    printf<span class="op">(</span><span class="st">"Thread: running again!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1424-16"><a href="threads.html#cb1424-16"></a></span>
<span id="cb1424-17"><a href="threads.html#cb1424-17"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1424-18"><a href="threads.html#cb1424-18"></a></span>
<span id="cb1424-19"><a href="threads.html#cb1424-19"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1424-20"><a href="threads.html#cb1424-20"></a><span class="op">}</span></span>
<span id="cb1424-21"><a href="threads.html#cb1424-21"></a></span>
<span id="cb1424-22"><a href="threads.html#cb1424-22"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1424-23"><a href="threads.html#cb1424-23"></a><span class="op">{</span></span>
<span id="cb1424-24"><a href="threads.html#cb1424-24"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1424-25"><a href="threads.html#cb1424-25"></a></span>
<span id="cb1424-26"><a href="threads.html#cb1424-26"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1424-27"><a href="threads.html#cb1424-27"></a>    cnd_init<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1424-28"><a href="threads.html#cb1424-28"></a></span>
<span id="cb1424-29"><a href="threads.html#cb1424-29"></a>    printf<span class="op">(</span><span class="st">"Main creating thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1424-30"><a href="threads.html#cb1424-30"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1424-31"><a href="threads.html#cb1424-31"></a></span>
<span id="cb1424-32"><a href="threads.html#cb1424-32"></a>    <span class="co">// Sleep 0.1s to allow the other thread to wait</span></span>
<span id="cb1424-33"><a href="threads.html#cb1424-33"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_nsec<span class="op">=</span><span class="dv">100000000</span><span class="bu">L</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1424-34"><a href="threads.html#cb1424-34"></a></span>
<span id="cb1424-35"><a href="threads.html#cb1424-35"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1424-36"><a href="threads.html#cb1424-36"></a>    printf<span class="op">(</span><span class="st">"Main: signaling thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1424-37"><a href="threads.html#cb1424-37"></a>    cnd_signal<span class="op">(&amp;</span>condvar<span class="op">);</span>    <span class="co">// &lt;-- SIGNAL CHILD THREAD HERE!</span></span>
<span id="cb1424-38"><a href="threads.html#cb1424-38"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1424-39"><a href="threads.html#cb1424-39"></a></span>
<span id="cb1424-40"><a href="threads.html#cb1424-40"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1424-41"><a href="threads.html#cb1424-41"></a></span>
<span id="cb1424-42"><a href="threads.html#cb1424-42"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1424-43"><a href="threads.html#cb1424-43"></a>    cnd_destroy<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1424-44"><a href="threads.html#cb1424-44"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1425"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1425-1"><a href="threads.html#cb1425-1" aria-hidden="true" tabindex="-1"></a>Main creating thread</span>
<span id="cb1425-2"><a href="threads.html#cb1425-2" aria-hidden="true" tabindex="-1"></a>Thread: waiting...</span>
<span id="cb1425-3"><a href="threads.html#cb1425-3" aria-hidden="true" tabindex="-1"></a>Main: signaling thread</span>
<span id="cb1425-4"><a href="threads.html#cb1425-4" aria-hidden="true" tabindex="-1"></a>Thread: running again!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-190">See Also</h3>
<p><a href="threads.html#man-cnd_init"><code>cnd_init()</code></a>, <a href="#man-cnd_destroy"><code>cnd_destroy()</code></a></p>
<hr>
<h2 data-number="66.6" id="man-cnd_timedwait"><span class="header-section-number">66.6</span>
<code>cnd_timedwait()</code></h2>
<p>Wait on a condition variable with a timeout</p>
<h3 class="unnumbered unlisted" id="synopsis-203">Synopsis</h3>
<div class="sourceCode" id="cb1426"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1426-1"><a href="threads.html#cb1426-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1426-2"><a href="threads.html#cb1426-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1426-3"><a href="threads.html#cb1426-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> cnd_timedwait<span class="op">(</span>cnd_t <span class="op">*</span><span class="dt">restrict</span> cond<span class="op">,</span> mtx_t <span class="op">*</span><span class="dt">restrict</span> mtx<span class="op">,</span></span>
<span id="cb1426-4"><a href="threads.html#cb1426-4" aria-hidden="true" tabindex="-1"></a>                  <span class="dt">const</span> <span class="kw">struct</span> timespec <span class="op">*</span><span class="dt">restrict</span> ts<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-203">Description</h3>
<p>This is like <a href="threads.html#man-cnd_wait"><code>cnd_wait()</code></a>
except we get to specify a timeout, as well.</p>
<p>Note that the thread still must reacquire the mutex to get more work
done even after the timeout. The the main difference is that regular
<code>cnd_wait()</code> will only try to get the mutex after a
<code>cnd_signal()</code> or <code>cnd_broadcast()</code>, whereas
<code>cnd_timedwait()</code> will do that, too, <strong>and</strong> try
to get the mutex after the timeout.</p>
<p>The timeout is specified as an absolute UTC time since Epoch. You can
get this with the <a href="#man-timespec_get"><code>timespec_get()</code></a> function and
then add values on to the result to timeout later than now, as shown in
the example.</p>
<p>Beware that you can’t have more than 999999999 nanoseconds in the
<code>tv_nsec</code> field of the <code>struct timespec</code>. Mod
those so they stay in range.</p>
<h3 class="unnumbered unlisted" id="return-value-201">Return Value</h3>
<p>If the thread wakes up for a non-timeout reason (e.g.&nbsp;signal or
broadcast), returns <code>thrd_success</code>. If woken up due to
timeout, returns <code>thrd_timedout</code>. Otherwise returns
<code>thrd_error</code>.</p>
<h3 class="unnumbered unlisted" id="example-205">Example</h3>
<p>This example has a thread wait on a condition variable for a maximum
of 1.75 seconds. And it always times out because no one ever sends a
signal. Tragic.</p>
<div class="sourceCode" id="cb1427"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1427-1"><a href="threads.html#cb1427-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1427-2"><a href="threads.html#cb1427-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1427-3"><a href="threads.html#cb1427-3"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1427-4"><a href="threads.html#cb1427-4"></a></span>
<span id="cb1427-5"><a href="threads.html#cb1427-5"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1427-6"><a href="threads.html#cb1427-6"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1427-7"><a href="threads.html#cb1427-7"></a></span>
<span id="cb1427-8"><a href="threads.html#cb1427-8"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1427-9"><a href="threads.html#cb1427-9"></a><span class="op">{</span></span>
<span id="cb1427-10"><a href="threads.html#cb1427-10"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1427-11"><a href="threads.html#cb1427-11"></a></span>
<span id="cb1427-12"><a href="threads.html#cb1427-12"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1427-13"><a href="threads.html#cb1427-13"></a></span>
<span id="cb1427-14"><a href="threads.html#cb1427-14"></a>    <span class="kw">struct</span> timespec ts<span class="op">;</span></span>
<span id="cb1427-15"><a href="threads.html#cb1427-15"></a></span>
<span id="cb1427-16"><a href="threads.html#cb1427-16"></a>    <span class="co">// Get the time now</span></span>
<span id="cb1427-17"><a href="threads.html#cb1427-17"></a>    timespec_get<span class="op">(&amp;</span>ts<span class="op">,</span> TIME_UTC<span class="op">);</span></span>
<span id="cb1427-18"><a href="threads.html#cb1427-18"></a></span>
<span id="cb1427-19"><a href="threads.html#cb1427-19"></a>    <span class="co">// Add on 1.75 seconds from now</span></span>
<span id="cb1427-20"><a href="threads.html#cb1427-20"></a>    ts<span class="op">.</span>tv_sec <span class="op">+=</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1427-21"><a href="threads.html#cb1427-21"></a>    ts<span class="op">.</span>tv_nsec <span class="op">+=</span> <span class="dv">750000000</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1427-22"><a href="threads.html#cb1427-22"></a></span>
<span id="cb1427-23"><a href="threads.html#cb1427-23"></a>    <span class="co">// Handle nsec overflow</span></span>
<span id="cb1427-24"><a href="threads.html#cb1427-24"></a>    ts<span class="op">.</span>tv_sec <span class="op">+=</span> ts<span class="op">.</span>tv_nsec <span class="op">/</span> <span class="dv">1000000000</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1427-25"><a href="threads.html#cb1427-25"></a>    ts<span class="op">.</span>tv_nsec <span class="op">=</span> ts<span class="op">.</span>tv_nsec <span class="op">%</span> <span class="dv">1000000000</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1427-26"><a href="threads.html#cb1427-26"></a></span>
<span id="cb1427-27"><a href="threads.html#cb1427-27"></a>    printf<span class="op">(</span><span class="st">"Thread: waiting...</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1427-28"><a href="threads.html#cb1427-28"></a>    <span class="dt">int</span> r <span class="op">=</span> cnd_timedwait<span class="op">(&amp;</span>condvar<span class="op">,</span> <span class="op">&amp;</span>mutex<span class="op">,</span> <span class="op">&amp;</span>ts<span class="op">);</span></span>
<span id="cb1427-29"><a href="threads.html#cb1427-29"></a></span>
<span id="cb1427-30"><a href="threads.html#cb1427-30"></a>    <span class="cf">switch</span> <span class="op">(</span>r<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1427-31"><a href="threads.html#cb1427-31"></a>        <span class="cf">case</span> thrd_success<span class="op">:</span></span>
<span id="cb1427-32"><a href="threads.html#cb1427-32"></a>            printf<span class="op">(</span><span class="st">"Thread: signaled!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1427-33"><a href="threads.html#cb1427-33"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1427-34"><a href="threads.html#cb1427-34"></a></span>
<span id="cb1427-35"><a href="threads.html#cb1427-35"></a>        <span class="cf">case</span> thrd_timedout<span class="op">:</span></span>
<span id="cb1427-36"><a href="threads.html#cb1427-36"></a>            printf<span class="op">(</span><span class="st">"Thread: timed out!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1427-37"><a href="threads.html#cb1427-37"></a>            <span class="cf">return</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1427-38"><a href="threads.html#cb1427-38"></a></span>
<span id="cb1427-39"><a href="threads.html#cb1427-39"></a>        <span class="cf">case</span> thrd_error<span class="op">:</span></span>
<span id="cb1427-40"><a href="threads.html#cb1427-40"></a>            printf<span class="op">(</span><span class="st">"Thread: Some kind of error</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1427-41"><a href="threads.html#cb1427-41"></a>            <span class="cf">return</span> <span class="dv">2</span><span class="op">;</span></span>
<span id="cb1427-42"><a href="threads.html#cb1427-42"></a>    <span class="op">}</span></span>
<span id="cb1427-43"><a href="threads.html#cb1427-43"></a></span>
<span id="cb1427-44"><a href="threads.html#cb1427-44"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1427-45"><a href="threads.html#cb1427-45"></a></span>
<span id="cb1427-46"><a href="threads.html#cb1427-46"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1427-47"><a href="threads.html#cb1427-47"></a><span class="op">}</span></span>
<span id="cb1427-48"><a href="threads.html#cb1427-48"></a></span>
<span id="cb1427-49"><a href="threads.html#cb1427-49"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1427-50"><a href="threads.html#cb1427-50"></a><span class="op">{</span></span>
<span id="cb1427-51"><a href="threads.html#cb1427-51"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1427-52"><a href="threads.html#cb1427-52"></a></span>
<span id="cb1427-53"><a href="threads.html#cb1427-53"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1427-54"><a href="threads.html#cb1427-54"></a>    cnd_init<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1427-55"><a href="threads.html#cb1427-55"></a></span>
<span id="cb1427-56"><a href="threads.html#cb1427-56"></a>    printf<span class="op">(</span><span class="st">"Main creating thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1427-57"><a href="threads.html#cb1427-57"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1427-58"><a href="threads.html#cb1427-58"></a></span>
<span id="cb1427-59"><a href="threads.html#cb1427-59"></a>    <span class="co">// Sleep 3s to allow the other thread to timeout</span></span>
<span id="cb1427-60"><a href="threads.html#cb1427-60"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_sec<span class="op">=</span><span class="dv">3</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1427-61"><a href="threads.html#cb1427-61"></a></span>
<span id="cb1427-62"><a href="threads.html#cb1427-62"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1427-63"><a href="threads.html#cb1427-63"></a></span>
<span id="cb1427-64"><a href="threads.html#cb1427-64"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1427-65"><a href="threads.html#cb1427-65"></a>    cnd_destroy<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1427-66"><a href="threads.html#cb1427-66"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1428"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1428-1"><a href="threads.html#cb1428-1" aria-hidden="true" tabindex="-1"></a>Main creating thread</span>
<span id="cb1428-2"><a href="threads.html#cb1428-2" aria-hidden="true" tabindex="-1"></a>Thread: waiting...</span>
<span id="cb1428-3"><a href="threads.html#cb1428-3" aria-hidden="true" tabindex="-1"></a>Thread: timed out!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-191">See Also</h3>
<p><a href="threads.html#man-cnd_wait"><code>cnd_wait()</code></a>, <a href="#man-timespec_get"><code>timespec_get()</code></a></p>
<hr>
<h2 data-number="66.7" id="man-cnd_wait"><span class="header-section-number">66.7</span> <code>cnd_wait()</code></h2>
<p>Wait for a signal on a condition variable</p>
<h3 class="unnumbered unlisted" id="synopsis-204">Synopsis</h3>
<div class="sourceCode" id="cb1429"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1429-1"><a href="threads.html#cb1429-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1429-2"><a href="threads.html#cb1429-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1429-3"><a href="threads.html#cb1429-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> cnd_wait<span class="op">(</span>cnd_t <span class="op">*</span>cond<span class="op">,</span> mtx_t <span class="op">*</span>mtx<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-204">Description</h3>
<p>This puts the calling thread to sleep until it is awakened by a call
to <code>cnd_signal()</code> or <code>cnd_broadcast()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-202">Return Value</h3>
<p>If everything’s fantastic, returns <code>thrd_success</code>.
Otherwise it returns <code>thrd_error</code> to report that something
has gone fantastically, horribly awry.</p>
<h3 class="unnumbered unlisted" id="example-206">Example</h3>
<p>General-purpose condition variable example here, but you can see the
<code>cnd_wait()</code> in the <code>run()</code> function.</p>
<div class="sourceCode" id="cb1430"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1430-1"><a href="threads.html#cb1430-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1430-2"><a href="threads.html#cb1430-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1430-3"><a href="threads.html#cb1430-3"></a></span>
<span id="cb1430-4"><a href="threads.html#cb1430-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1430-5"><a href="threads.html#cb1430-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1430-6"><a href="threads.html#cb1430-6"></a></span>
<span id="cb1430-7"><a href="threads.html#cb1430-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1430-8"><a href="threads.html#cb1430-8"></a><span class="op">{</span></span>
<span id="cb1430-9"><a href="threads.html#cb1430-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1430-10"><a href="threads.html#cb1430-10"></a></span>
<span id="cb1430-11"><a href="threads.html#cb1430-11"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1430-12"><a href="threads.html#cb1430-12"></a></span>
<span id="cb1430-13"><a href="threads.html#cb1430-13"></a>    printf<span class="op">(</span><span class="st">"Thread: waiting...</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1430-14"><a href="threads.html#cb1430-14"></a>    cnd_wait<span class="op">(&amp;</span>condvar<span class="op">,</span> <span class="op">&amp;</span>mutex<span class="op">);</span>       <span class="co">// &lt;-- WAIT HERE!</span></span>
<span id="cb1430-15"><a href="threads.html#cb1430-15"></a>    printf<span class="op">(</span><span class="st">"Thread: running again!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1430-16"><a href="threads.html#cb1430-16"></a></span>
<span id="cb1430-17"><a href="threads.html#cb1430-17"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1430-18"><a href="threads.html#cb1430-18"></a></span>
<span id="cb1430-19"><a href="threads.html#cb1430-19"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1430-20"><a href="threads.html#cb1430-20"></a><span class="op">}</span></span>
<span id="cb1430-21"><a href="threads.html#cb1430-21"></a></span>
<span id="cb1430-22"><a href="threads.html#cb1430-22"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1430-23"><a href="threads.html#cb1430-23"></a><span class="op">{</span></span>
<span id="cb1430-24"><a href="threads.html#cb1430-24"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1430-25"><a href="threads.html#cb1430-25"></a></span>
<span id="cb1430-26"><a href="threads.html#cb1430-26"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1430-27"><a href="threads.html#cb1430-27"></a>    cnd_init<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1430-28"><a href="threads.html#cb1430-28"></a></span>
<span id="cb1430-29"><a href="threads.html#cb1430-29"></a>    printf<span class="op">(</span><span class="st">"Main creating thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1430-30"><a href="threads.html#cb1430-30"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1430-31"><a href="threads.html#cb1430-31"></a></span>
<span id="cb1430-32"><a href="threads.html#cb1430-32"></a>    <span class="co">// Sleep 0.1s to allow the other thread to wait</span></span>
<span id="cb1430-33"><a href="threads.html#cb1430-33"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_nsec<span class="op">=</span><span class="dv">100000000</span><span class="bu">L</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1430-34"><a href="threads.html#cb1430-34"></a></span>
<span id="cb1430-35"><a href="threads.html#cb1430-35"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1430-36"><a href="threads.html#cb1430-36"></a>    printf<span class="op">(</span><span class="st">"Main: signaling thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1430-37"><a href="threads.html#cb1430-37"></a>    cnd_signal<span class="op">(&amp;</span>condvar<span class="op">);</span>    <span class="co">// &lt;-- SIGNAL CHILD THREAD HERE!</span></span>
<span id="cb1430-38"><a href="threads.html#cb1430-38"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1430-39"><a href="threads.html#cb1430-39"></a></span>
<span id="cb1430-40"><a href="threads.html#cb1430-40"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1430-41"><a href="threads.html#cb1430-41"></a></span>
<span id="cb1430-42"><a href="threads.html#cb1430-42"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1430-43"><a href="threads.html#cb1430-43"></a>    cnd_destroy<span class="op">(&amp;</span>condvar<span class="op">);</span></span>
<span id="cb1430-44"><a href="threads.html#cb1430-44"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1431"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1431-1"><a href="threads.html#cb1431-1" aria-hidden="true" tabindex="-1"></a>Main creating thread</span>
<span id="cb1431-2"><a href="threads.html#cb1431-2" aria-hidden="true" tabindex="-1"></a>Thread: waiting...</span>
<span id="cb1431-3"><a href="threads.html#cb1431-3" aria-hidden="true" tabindex="-1"></a>Main: signaling thread</span>
<span id="cb1431-4"><a href="threads.html#cb1431-4" aria-hidden="true" tabindex="-1"></a>Thread: running again!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-192">See Also</h3>
<p><a href="threads.html#man-cnd_timedwait"><code>cnd_timedwait()</code></a></p>
<hr>
<h2 data-number="66.8" id="man-mtx_destroy"><span class="header-section-number">66.8</span>
<code>mtx_destroy()</code></h2>
<p>Cleanup a mutex when done with it</p>
<h3 class="unnumbered unlisted" id="synopsis-205">Synopsis</h3>
<div class="sourceCode" id="cb1432"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1432-1"><a href="threads.html#cb1432-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1432-2"><a href="threads.html#cb1432-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1432-3"><a href="threads.html#cb1432-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> mtx_destroy<span class="op">(</span>mtx_t <span class="op">*</span>mtx<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-205">Description</h3>
<p>The opposite of <a href="threads.html#man-mtx_init"><code>mtx_init()</code></a>,
this function frees up any resources associated with the given
mutex.</p>
<p>You should call this when all threads are done using the mutex.</p>
<h3 class="unnumbered unlisted" id="return-value-203">Return Value</h3>
<p>Returns nothing, the selfish ingrate!</p>
<h3 class="unnumbered unlisted" id="example-207">Example</h3>
<p>General-purpose mutex example here, but you can see the
<code>mtx_destroy()</code> down at the end.</p>
<div class="sourceCode" id="cb1433"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1433-1"><a href="threads.html#cb1433-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1433-2"><a href="threads.html#cb1433-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1433-3"><a href="threads.html#cb1433-3"></a></span>
<span id="cb1433-4"><a href="threads.html#cb1433-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1433-5"><a href="threads.html#cb1433-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1433-6"><a href="threads.html#cb1433-6"></a></span>
<span id="cb1433-7"><a href="threads.html#cb1433-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1433-8"><a href="threads.html#cb1433-8"></a><span class="op">{</span></span>
<span id="cb1433-9"><a href="threads.html#cb1433-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1433-10"><a href="threads.html#cb1433-10"></a></span>
<span id="cb1433-11"><a href="threads.html#cb1433-11"></a>    <span class="dt">static</span> <span class="dt">int</span> count <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1433-12"><a href="threads.html#cb1433-12"></a></span>
<span id="cb1433-13"><a href="threads.html#cb1433-13"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1433-14"><a href="threads.html#cb1433-14"></a></span>
<span id="cb1433-15"><a href="threads.html#cb1433-15"></a>    printf<span class="op">(</span><span class="st">"Thread: I got %d!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> count<span class="op">);</span></span>
<span id="cb1433-16"><a href="threads.html#cb1433-16"></a>    count<span class="op">++;</span></span>
<span id="cb1433-17"><a href="threads.html#cb1433-17"></a></span>
<span id="cb1433-18"><a href="threads.html#cb1433-18"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1433-19"><a href="threads.html#cb1433-19"></a></span>
<span id="cb1433-20"><a href="threads.html#cb1433-20"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1433-21"><a href="threads.html#cb1433-21"></a><span class="op">}</span></span>
<span id="cb1433-22"><a href="threads.html#cb1433-22"></a></span>
<span id="cb1433-23"><a href="threads.html#cb1433-23"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1433-24"><a href="threads.html#cb1433-24"></a></span>
<span id="cb1433-25"><a href="threads.html#cb1433-25"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1433-26"><a href="threads.html#cb1433-26"></a><span class="op">{</span></span>
<span id="cb1433-27"><a href="threads.html#cb1433-27"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1433-28"><a href="threads.html#cb1433-28"></a></span>
<span id="cb1433-29"><a href="threads.html#cb1433-29"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1433-30"><a href="threads.html#cb1433-30"></a></span>
<span id="cb1433-31"><a href="threads.html#cb1433-31"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1433-32"><a href="threads.html#cb1433-32"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1433-33"><a href="threads.html#cb1433-33"></a></span>
<span id="cb1433-34"><a href="threads.html#cb1433-34"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1433-35"><a href="threads.html#cb1433-35"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1433-36"><a href="threads.html#cb1433-36"></a></span>
<span id="cb1433-37"><a href="threads.html#cb1433-37"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span>   <span class="co">// &lt;-- DESTROY THE MUTEX HERE</span></span>
<span id="cb1433-38"><a href="threads.html#cb1433-38"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1434"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1434-1"><a href="threads.html#cb1434-1" aria-hidden="true" tabindex="-1"></a>Thread: I got 0!</span>
<span id="cb1434-2"><a href="threads.html#cb1434-2" aria-hidden="true" tabindex="-1"></a>Thread: I got 1!</span>
<span id="cb1434-3"><a href="threads.html#cb1434-3" aria-hidden="true" tabindex="-1"></a>Thread: I got 2!</span>
<span id="cb1434-4"><a href="threads.html#cb1434-4" aria-hidden="true" tabindex="-1"></a>Thread: I got 3!</span>
<span id="cb1434-5"><a href="threads.html#cb1434-5" aria-hidden="true" tabindex="-1"></a>Thread: I got 4!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-193">See Also</h3>
<p><a href="threads.html#man-mtx_init"><code>mtx_init()</code></a></p>
<hr>
<h2 data-number="66.9" id="man-mtx_init"><span class="header-section-number">66.9</span> <code>mtx_init()</code></h2>
<p>Initialize a mutex for use</p>
<h3 class="unnumbered unlisted" id="synopsis-206">Synopsis</h3>
<div class="sourceCode" id="cb1435"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1435-1"><a href="threads.html#cb1435-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1435-2"><a href="threads.html#cb1435-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1435-3"><a href="threads.html#cb1435-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mtx_init<span class="op">(</span>mtx_t <span class="op">*</span>mtx<span class="op">,</span> <span class="dt">int</span> type<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-206">Description</h3>
<p>Before you can use a mutex variable, you have to initialize it with
this call to get it all prepped and ready to go.</p>
<p>But wait! It’s not quite that simple. You have to tell it what
<code>type</code> of mutex you want to create.</p>
<table>
<thead>
<tr class="header">
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>mtx_plain</code></td>
<td>Regular ol’ mutex</td>
</tr>
<tr class="even">
<td><code>mtx_timed</code></td>
<td>Mutex that supports timeouts</td>
</tr>
<tr class="odd">
<td><code>mtx_plain|mtx_recursive</code></td>
<td>Recursive mutex</td>
</tr>
<tr class="even">
<td><code>mtx_timed|mtx_recursive</code></td>
<td>Recursive mutex that supports timeouts</td>
</tr>
</tbody>
</table>
<p>As you can see, you can make a plain or timed mutex
<em>recursive</em> by bitwise-ORing the value with
<code>mtx_recursive</code>.</p>
<p>“Recursive” means that the holder of a lock can call
<code>mtx_lock()</code> multiple times on the same lock. (They have to
unlock it an equal number of times before anyone else can take the
mutex.) This might ease coding from time to time, especially if you call
a function that needs to lock the mutex when you already hold the
mutex.</p>
<p>And the timeout gives a thread a chance to <em>try</em> to get the
lock for a while, but then bail out if it can’t get it in that
timeframe. You use the <a href="#man-mtx_timedlock"><code>mtx_timedlock()</code></a> function with
<code>mtx_timed</code> mutexes.</p>
<h3 class="unnumbered unlisted" id="return-value-204">Return Value</h3>
<p>Returns <code>thrd_success</code> in a perfect world, and potentially
<code>thrd_error</code> in an imperfect one.</p>
<h3 class="unnumbered unlisted" id="example-208">Example</h3>
<p>General-purpose mutex example here, but you can see the
<code>mtx_init()</code> down at the top of <code>main()</code>:</p>
<div class="sourceCode" id="cb1436"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1436-1"><a href="threads.html#cb1436-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1436-2"><a href="threads.html#cb1436-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1436-3"><a href="threads.html#cb1436-3"></a></span>
<span id="cb1436-4"><a href="threads.html#cb1436-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1436-5"><a href="threads.html#cb1436-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1436-6"><a href="threads.html#cb1436-6"></a></span>
<span id="cb1436-7"><a href="threads.html#cb1436-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1436-8"><a href="threads.html#cb1436-8"></a><span class="op">{</span></span>
<span id="cb1436-9"><a href="threads.html#cb1436-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1436-10"><a href="threads.html#cb1436-10"></a></span>
<span id="cb1436-11"><a href="threads.html#cb1436-11"></a>    <span class="dt">static</span> <span class="dt">int</span> count <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1436-12"><a href="threads.html#cb1436-12"></a></span>
<span id="cb1436-13"><a href="threads.html#cb1436-13"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1436-14"><a href="threads.html#cb1436-14"></a></span>
<span id="cb1436-15"><a href="threads.html#cb1436-15"></a>    printf<span class="op">(</span><span class="st">"Thread: I got %d!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> count<span class="op">);</span></span>
<span id="cb1436-16"><a href="threads.html#cb1436-16"></a>    count<span class="op">++;</span></span>
<span id="cb1436-17"><a href="threads.html#cb1436-17"></a></span>
<span id="cb1436-18"><a href="threads.html#cb1436-18"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1436-19"><a href="threads.html#cb1436-19"></a></span>
<span id="cb1436-20"><a href="threads.html#cb1436-20"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1436-21"><a href="threads.html#cb1436-21"></a><span class="op">}</span></span>
<span id="cb1436-22"><a href="threads.html#cb1436-22"></a></span>
<span id="cb1436-23"><a href="threads.html#cb1436-23"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1436-24"><a href="threads.html#cb1436-24"></a></span>
<span id="cb1436-25"><a href="threads.html#cb1436-25"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1436-26"><a href="threads.html#cb1436-26"></a><span class="op">{</span></span>
<span id="cb1436-27"><a href="threads.html#cb1436-27"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1436-28"><a href="threads.html#cb1436-28"></a></span>
<span id="cb1436-29"><a href="threads.html#cb1436-29"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span>  <span class="co">// &lt;-- CREATE THE MUTEX HERE</span></span>
<span id="cb1436-30"><a href="threads.html#cb1436-30"></a></span>
<span id="cb1436-31"><a href="threads.html#cb1436-31"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1436-32"><a href="threads.html#cb1436-32"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1436-33"><a href="threads.html#cb1436-33"></a></span>
<span id="cb1436-34"><a href="threads.html#cb1436-34"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1436-35"><a href="threads.html#cb1436-35"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1436-36"><a href="threads.html#cb1436-36"></a></span>
<span id="cb1436-37"><a href="threads.html#cb1436-37"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span>   <span class="co">// &lt;-- DESTROY THE MUTEX HERE</span></span>
<span id="cb1436-38"><a href="threads.html#cb1436-38"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1437"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1437-1"><a href="threads.html#cb1437-1" aria-hidden="true" tabindex="-1"></a>Thread: I got 0!</span>
<span id="cb1437-2"><a href="threads.html#cb1437-2" aria-hidden="true" tabindex="-1"></a>Thread: I got 1!</span>
<span id="cb1437-3"><a href="threads.html#cb1437-3" aria-hidden="true" tabindex="-1"></a>Thread: I got 2!</span>
<span id="cb1437-4"><a href="threads.html#cb1437-4" aria-hidden="true" tabindex="-1"></a>Thread: I got 3!</span>
<span id="cb1437-5"><a href="threads.html#cb1437-5" aria-hidden="true" tabindex="-1"></a>Thread: I got 4!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-194">See Also</h3>
<p><a href="threads.html#man-mtx_destroy"><code>mtx_destroy()</code></a></p>
<hr>
<h2 data-number="66.10" id="man-mtx_lock"><span class="header-section-number">66.10</span> <code>mtx_lock()</code></h2>
<p>Acquire a lock on a mutex</p>
<h3 class="unnumbered unlisted" id="synopsis-207">Synopsis</h3>
<div class="sourceCode" id="cb1438"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1438-1"><a href="threads.html#cb1438-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1438-2"><a href="threads.html#cb1438-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1438-3"><a href="threads.html#cb1438-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mtx_lock<span class="op">(</span>mtx_t <span class="op">*</span>mtx<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-207">Description</h3>
<p>If you’re a thread and want to enter a critical section, do I have
the function for you!</p>
<p>A thread that calls this function will wait until it can acquire the
mutex, then it will grab it, wake up, and run!</p>
<p>If the mutex is recursive and is already locked by this thread, it
will be locked again and the lock count will increase. If the mutex is
not recursive and the thread already holds it, this call will error
out.</p>
<h3 class="unnumbered unlisted" id="return-value-205">Return Value</h3>
<p>Returns <code>thrd_success</code> on goodness and
<code>thrd_error</code> on badness.</p>
<h3 class="unnumbered unlisted" id="example-209">Example</h3>
<p>General-purpose mutex example here, but you can see the
<code>mtx_lock()</code> in the <code>run()</code> function:</p>
<div class="sourceCode" id="cb1439"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1439-1"><a href="threads.html#cb1439-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1439-2"><a href="threads.html#cb1439-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1439-3"><a href="threads.html#cb1439-3"></a></span>
<span id="cb1439-4"><a href="threads.html#cb1439-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1439-5"><a href="threads.html#cb1439-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1439-6"><a href="threads.html#cb1439-6"></a></span>
<span id="cb1439-7"><a href="threads.html#cb1439-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1439-8"><a href="threads.html#cb1439-8"></a><span class="op">{</span></span>
<span id="cb1439-9"><a href="threads.html#cb1439-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1439-10"><a href="threads.html#cb1439-10"></a></span>
<span id="cb1439-11"><a href="threads.html#cb1439-11"></a>    <span class="dt">static</span> <span class="dt">int</span> count <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1439-12"><a href="threads.html#cb1439-12"></a></span>
<span id="cb1439-13"><a href="threads.html#cb1439-13"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span>  <span class="co">// &lt;-- LOCK HERE</span></span>
<span id="cb1439-14"><a href="threads.html#cb1439-14"></a></span>
<span id="cb1439-15"><a href="threads.html#cb1439-15"></a>    printf<span class="op">(</span><span class="st">"Thread: I got %d!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> count<span class="op">);</span></span>
<span id="cb1439-16"><a href="threads.html#cb1439-16"></a>    count<span class="op">++;</span></span>
<span id="cb1439-17"><a href="threads.html#cb1439-17"></a></span>
<span id="cb1439-18"><a href="threads.html#cb1439-18"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1439-19"><a href="threads.html#cb1439-19"></a></span>
<span id="cb1439-20"><a href="threads.html#cb1439-20"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1439-21"><a href="threads.html#cb1439-21"></a><span class="op">}</span></span>
<span id="cb1439-22"><a href="threads.html#cb1439-22"></a></span>
<span id="cb1439-23"><a href="threads.html#cb1439-23"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1439-24"><a href="threads.html#cb1439-24"></a></span>
<span id="cb1439-25"><a href="threads.html#cb1439-25"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1439-26"><a href="threads.html#cb1439-26"></a><span class="op">{</span></span>
<span id="cb1439-27"><a href="threads.html#cb1439-27"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1439-28"><a href="threads.html#cb1439-28"></a></span>
<span id="cb1439-29"><a href="threads.html#cb1439-29"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span>  <span class="co">// &lt;-- CREATE THE MUTEX HERE</span></span>
<span id="cb1439-30"><a href="threads.html#cb1439-30"></a></span>
<span id="cb1439-31"><a href="threads.html#cb1439-31"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1439-32"><a href="threads.html#cb1439-32"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1439-33"><a href="threads.html#cb1439-33"></a></span>
<span id="cb1439-34"><a href="threads.html#cb1439-34"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1439-35"><a href="threads.html#cb1439-35"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1439-36"><a href="threads.html#cb1439-36"></a></span>
<span id="cb1439-37"><a href="threads.html#cb1439-37"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span>   <span class="co">// &lt;-- DESTROY THE MUTEX HERE</span></span>
<span id="cb1439-38"><a href="threads.html#cb1439-38"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1440"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1440-1"><a href="threads.html#cb1440-1" aria-hidden="true" tabindex="-1"></a>Thread: I got 0!</span>
<span id="cb1440-2"><a href="threads.html#cb1440-2" aria-hidden="true" tabindex="-1"></a>Thread: I got 1!</span>
<span id="cb1440-3"><a href="threads.html#cb1440-3" aria-hidden="true" tabindex="-1"></a>Thread: I got 2!</span>
<span id="cb1440-4"><a href="threads.html#cb1440-4" aria-hidden="true" tabindex="-1"></a>Thread: I got 3!</span>
<span id="cb1440-5"><a href="threads.html#cb1440-5" aria-hidden="true" tabindex="-1"></a>Thread: I got 4!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-195">See Also</h3>
<p><a href="threads.html#man-mtx_unlock"><code>mtx_unlock()</code></a>, <a href="#man-mtx_trylock"><code>mtx_trylock()</code></a>, <a href="#man-mtx_timedlock"><code>mtx_timedlock()</code></a></p>
<hr>
<h2 data-number="66.11" id="man-mtx_timedlock"><span class="header-section-number">66.11</span>
<code>mtx_timedlock()</code></h2>
<p>Lock a mutex allowing for timeout</p>
<h3 class="unnumbered unlisted" id="synopsis-208">Synopsis</h3>
<div class="sourceCode" id="cb1441"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1441-1"><a href="threads.html#cb1441-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1441-2"><a href="threads.html#cb1441-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1441-3"><a href="threads.html#cb1441-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mtx_timedlock<span class="op">(</span>mtx_t <span class="op">*</span><span class="dt">restrict</span> mtx<span class="op">,</span> <span class="dt">const</span> <span class="kw">struct</span> timespec <span class="op">*</span><span class="dt">restrict</span> ts<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-208">Description</h3>
<p>This is just like <a href="threads.html#man-mtx_lock"><code>mtx_lock()</code></a>
except you can add a timeout if you don’t want to wait forever.</p>
<p>The timeout is specified as an absolute UTC time since Epoch. You can
get this with the <a href="#man-timespec_get"><code>timespec_get()</code></a> function and
then add values on to the result to timeout later than now, as shown in
the example.</p>
<p>Beware that you can’t have more than 999999999 nanoseconds in the
<code>tv_nsec</code> field of the <code>struct timespec</code>. Mod
those so they stay in range.</p>
<h3 class="unnumbered unlisted" id="return-value-206">Return Value</h3>
<p>If everything works and the mutex is obtained, returns
<code>thrd_success</code>. If a timeout happens first, returns
<code>thrd_timedout</code>.</p>
<p>Otherwise, returns <code>thrd_error</code>. Because if nothing is
right, everything is wrong.</p>
<h3 class="unnumbered unlisted" id="example-210">Example</h3>
<p>This example has a thread wait on a mutex for a maximum of 1.75
seconds. And it always times out because no one ever sends a signal.</p>
<div class="sourceCode" id="cb1442"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1442-1"><a href="threads.html#cb1442-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1442-2"><a href="threads.html#cb1442-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1442-3"><a href="threads.html#cb1442-3"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1442-4"><a href="threads.html#cb1442-4"></a></span>
<span id="cb1442-5"><a href="threads.html#cb1442-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1442-6"><a href="threads.html#cb1442-6"></a></span>
<span id="cb1442-7"><a href="threads.html#cb1442-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1442-8"><a href="threads.html#cb1442-8"></a><span class="op">{</span></span>
<span id="cb1442-9"><a href="threads.html#cb1442-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1442-10"><a href="threads.html#cb1442-10"></a></span>
<span id="cb1442-11"><a href="threads.html#cb1442-11"></a>    <span class="kw">struct</span> timespec ts<span class="op">;</span></span>
<span id="cb1442-12"><a href="threads.html#cb1442-12"></a></span>
<span id="cb1442-13"><a href="threads.html#cb1442-13"></a>    <span class="co">// Get the time now</span></span>
<span id="cb1442-14"><a href="threads.html#cb1442-14"></a>    timespec_get<span class="op">(&amp;</span>ts<span class="op">,</span> TIME_UTC<span class="op">);</span></span>
<span id="cb1442-15"><a href="threads.html#cb1442-15"></a></span>
<span id="cb1442-16"><a href="threads.html#cb1442-16"></a>    <span class="co">// Add on 1.75 seconds from now</span></span>
<span id="cb1442-17"><a href="threads.html#cb1442-17"></a>    ts<span class="op">.</span>tv_sec <span class="op">+=</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1442-18"><a href="threads.html#cb1442-18"></a>    ts<span class="op">.</span>tv_nsec <span class="op">+=</span> <span class="dv">750000000</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1442-19"><a href="threads.html#cb1442-19"></a></span>
<span id="cb1442-20"><a href="threads.html#cb1442-20"></a>    <span class="co">// Handle nsec overflow</span></span>
<span id="cb1442-21"><a href="threads.html#cb1442-21"></a>    ts<span class="op">.</span>tv_sec <span class="op">+=</span> ts<span class="op">.</span>tv_nsec <span class="op">/</span> <span class="dv">1000000000</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1442-22"><a href="threads.html#cb1442-22"></a>    ts<span class="op">.</span>tv_nsec <span class="op">=</span> ts<span class="op">.</span>tv_nsec <span class="op">%</span> <span class="dv">1000000000</span><span class="bu">L</span><span class="op">;</span></span>
<span id="cb1442-23"><a href="threads.html#cb1442-23"></a></span>
<span id="cb1442-24"><a href="threads.html#cb1442-24"></a>    printf<span class="op">(</span><span class="st">"Thread: waiting for lock...</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1442-25"><a href="threads.html#cb1442-25"></a>    <span class="dt">int</span> r <span class="op">=</span> mtx_timedlock<span class="op">(&amp;</span>mutex<span class="op">,</span> <span class="op">&amp;</span>ts<span class="op">);</span></span>
<span id="cb1442-26"><a href="threads.html#cb1442-26"></a></span>
<span id="cb1442-27"><a href="threads.html#cb1442-27"></a>    <span class="cf">switch</span> <span class="op">(</span>r<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1442-28"><a href="threads.html#cb1442-28"></a>        <span class="cf">case</span> thrd_success<span class="op">:</span></span>
<span id="cb1442-29"><a href="threads.html#cb1442-29"></a>            printf<span class="op">(</span><span class="st">"Thread: grabbed lock!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1442-30"><a href="threads.html#cb1442-30"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1442-31"><a href="threads.html#cb1442-31"></a></span>
<span id="cb1442-32"><a href="threads.html#cb1442-32"></a>        <span class="cf">case</span> thrd_timedout<span class="op">:</span></span>
<span id="cb1442-33"><a href="threads.html#cb1442-33"></a>            printf<span class="op">(</span><span class="st">"Thread: timed out!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1442-34"><a href="threads.html#cb1442-34"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1442-35"><a href="threads.html#cb1442-35"></a></span>
<span id="cb1442-36"><a href="threads.html#cb1442-36"></a>        <span class="cf">case</span> thrd_error<span class="op">:</span></span>
<span id="cb1442-37"><a href="threads.html#cb1442-37"></a>            printf<span class="op">(</span><span class="st">"Thread: Some kind of error</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1442-38"><a href="threads.html#cb1442-38"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1442-39"><a href="threads.html#cb1442-39"></a>    <span class="op">}</span></span>
<span id="cb1442-40"><a href="threads.html#cb1442-40"></a></span>
<span id="cb1442-41"><a href="threads.html#cb1442-41"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1442-42"><a href="threads.html#cb1442-42"></a></span>
<span id="cb1442-43"><a href="threads.html#cb1442-43"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1442-44"><a href="threads.html#cb1442-44"></a><span class="op">}</span></span>
<span id="cb1442-45"><a href="threads.html#cb1442-45"></a></span>
<span id="cb1442-46"><a href="threads.html#cb1442-46"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1442-47"><a href="threads.html#cb1442-47"></a><span class="op">{</span></span>
<span id="cb1442-48"><a href="threads.html#cb1442-48"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1442-49"><a href="threads.html#cb1442-49"></a></span>
<span id="cb1442-50"><a href="threads.html#cb1442-50"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1442-51"><a href="threads.html#cb1442-51"></a></span>
<span id="cb1442-52"><a href="threads.html#cb1442-52"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1442-53"><a href="threads.html#cb1442-53"></a></span>
<span id="cb1442-54"><a href="threads.html#cb1442-54"></a>    printf<span class="op">(</span><span class="st">"Main creating thread</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1442-55"><a href="threads.html#cb1442-55"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1442-56"><a href="threads.html#cb1442-56"></a></span>
<span id="cb1442-57"><a href="threads.html#cb1442-57"></a>    <span class="co">// Sleep 3s to allow the other thread to timeout</span></span>
<span id="cb1442-58"><a href="threads.html#cb1442-58"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_sec<span class="op">=</span><span class="dv">3</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1442-59"><a href="threads.html#cb1442-59"></a></span>
<span id="cb1442-60"><a href="threads.html#cb1442-60"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1442-61"><a href="threads.html#cb1442-61"></a></span>
<span id="cb1442-62"><a href="threads.html#cb1442-62"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1442-63"><a href="threads.html#cb1442-63"></a></span>
<span id="cb1442-64"><a href="threads.html#cb1442-64"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1442-65"><a href="threads.html#cb1442-65"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1443"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1443-1"><a href="threads.html#cb1443-1" aria-hidden="true" tabindex="-1"></a>Main creating thread</span>
<span id="cb1443-2"><a href="threads.html#cb1443-2" aria-hidden="true" tabindex="-1"></a>Thread: waiting for lock...</span>
<span id="cb1443-3"><a href="threads.html#cb1443-3" aria-hidden="true" tabindex="-1"></a>Thread: timed out!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-196">See Also</h3>
<p><a href="threads.html#man-mtx_lock"><code>mtx_lock()</code></a>, <a href="#man-mtx_trylock"><code>mtx_trylock()</code></a>, <a href="#man-timespec_get"><code>timespec_get()</code></a></p>
<hr>
<h2 data-number="66.12" id="man-mtx_trylock"><span class="header-section-number">66.12</span>
<code>mtx_trylock()</code></h2>
<p>Try to lock a mutex, returning if not possible</p>
<h3 class="unnumbered unlisted" id="synopsis-209">Synopsis</h3>
<div class="sourceCode" id="cb1444"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1444-1"><a href="threads.html#cb1444-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1444-2"><a href="threads.html#cb1444-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1444-3"><a href="threads.html#cb1444-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mtx_trylock<span class="op">(</span>mtx_t <span class="op">*</span>mtx<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-209">Description</h3>
<p>This works just like <a href="#man-mtx_lock"><code>mtx_lock</code></a> except that it returns
instantly if a lock can’t be obtained.</p>
<p>The spec notes that there’s a chance that <code>mtx_trylock()</code>
might spuriously fail with <code>thrd_busy</code> even if there are no
other threads holding the lock. I’m not sure why this is, but you should
defensively code against it.</p>
<h3 class="unnumbered unlisted" id="return-value-207">Return Value</h3>
<p>Returns <code>thrd_success</code> if all’s well. Or
<code>thrd_busy</code> if some other thread holds the lock. Or
<code>thrd_error</code>, which means something went right. I mean
“wrong”.</p>
<h3 class="unnumbered unlisted" id="example-211">Example</h3>
<div class="sourceCode" id="cb1445"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1445-1"><a href="threads.html#cb1445-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1445-2"><a href="threads.html#cb1445-2"></a><span class="pp">#include </span><span class="im">&lt;time.h&gt;</span></span>
<span id="cb1445-3"><a href="threads.html#cb1445-3"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1445-4"><a href="threads.html#cb1445-4"></a></span>
<span id="cb1445-5"><a href="threads.html#cb1445-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1445-6"><a href="threads.html#cb1445-6"></a></span>
<span id="cb1445-7"><a href="threads.html#cb1445-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1445-8"><a href="threads.html#cb1445-8"></a><span class="op">{</span></span>
<span id="cb1445-9"><a href="threads.html#cb1445-9"></a>    <span class="dt">int</span> id <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span></span>
<span id="cb1445-10"><a href="threads.html#cb1445-10"></a></span>
<span id="cb1445-11"><a href="threads.html#cb1445-11"></a>    <span class="dt">int</span> r <span class="op">=</span> mtx_trylock<span class="op">(&amp;</span>mutex<span class="op">);</span>   <span class="co">// &lt;-- TRY TO GRAB THE LOCK</span></span>
<span id="cb1445-12"><a href="threads.html#cb1445-12"></a></span>
<span id="cb1445-13"><a href="threads.html#cb1445-13"></a>    <span class="cf">switch</span> <span class="op">(</span>r<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1445-14"><a href="threads.html#cb1445-14"></a>        <span class="cf">case</span> thrd_success<span class="op">:</span></span>
<span id="cb1445-15"><a href="threads.html#cb1445-15"></a>            printf<span class="op">(</span><span class="st">"Thread %d: grabbed lock!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">);</span></span>
<span id="cb1445-16"><a href="threads.html#cb1445-16"></a>            <span class="cf">break</span><span class="op">;</span></span>
<span id="cb1445-17"><a href="threads.html#cb1445-17"></a></span>
<span id="cb1445-18"><a href="threads.html#cb1445-18"></a>        <span class="cf">case</span> thrd_busy<span class="op">:</span></span>
<span id="cb1445-19"><a href="threads.html#cb1445-19"></a>            printf<span class="op">(</span><span class="st">"Thread %d: lock already taken :(</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">);</span></span>
<span id="cb1445-20"><a href="threads.html#cb1445-20"></a>            <span class="cf">return</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1445-21"><a href="threads.html#cb1445-21"></a></span>
<span id="cb1445-22"><a href="threads.html#cb1445-22"></a>        <span class="cf">case</span> thrd_error<span class="op">:</span></span>
<span id="cb1445-23"><a href="threads.html#cb1445-23"></a>            printf<span class="op">(</span><span class="st">"Thread %d: Some kind of error</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">);</span></span>
<span id="cb1445-24"><a href="threads.html#cb1445-24"></a>            <span class="cf">return</span> <span class="dv">2</span><span class="op">;</span></span>
<span id="cb1445-25"><a href="threads.html#cb1445-25"></a>    <span class="op">}</span></span>
<span id="cb1445-26"><a href="threads.html#cb1445-26"></a></span>
<span id="cb1445-27"><a href="threads.html#cb1445-27"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1445-28"><a href="threads.html#cb1445-28"></a></span>
<span id="cb1445-29"><a href="threads.html#cb1445-29"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1445-30"><a href="threads.html#cb1445-30"></a><span class="op">}</span></span>
<span id="cb1445-31"><a href="threads.html#cb1445-31"></a></span>
<span id="cb1445-32"><a href="threads.html#cb1445-32"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1445-33"><a href="threads.html#cb1445-33"></a></span>
<span id="cb1445-34"><a href="threads.html#cb1445-34"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1445-35"><a href="threads.html#cb1445-35"></a><span class="op">{</span></span>
<span id="cb1445-36"><a href="threads.html#cb1445-36"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1445-37"><a href="threads.html#cb1445-37"></a>    <span class="dt">int</span> id<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1445-38"><a href="threads.html#cb1445-38"></a></span>
<span id="cb1445-39"><a href="threads.html#cb1445-39"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1445-40"><a href="threads.html#cb1445-40"></a></span>
<span id="cb1445-41"><a href="threads.html#cb1445-41"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1445-42"><a href="threads.html#cb1445-42"></a>        id<span class="op">[</span>i<span class="op">]</span> <span class="op">=</span> i<span class="op">;</span></span>
<span id="cb1445-43"><a href="threads.html#cb1445-43"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> id <span class="op">+</span> i<span class="op">);</span></span>
<span id="cb1445-44"><a href="threads.html#cb1445-44"></a>    <span class="op">}</span></span>
<span id="cb1445-45"><a href="threads.html#cb1445-45"></a></span>
<span id="cb1445-46"><a href="threads.html#cb1445-46"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1445-47"><a href="threads.html#cb1445-47"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1445-48"><a href="threads.html#cb1445-48"></a></span>
<span id="cb1445-49"><a href="threads.html#cb1445-49"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1445-50"><a href="threads.html#cb1445-50"></a><span class="op">}</span></span></code></pre></div>
<p>Output (varies by run):</p>
<div class="sourceCode" id="cb1446"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1446-1"><a href="threads.html#cb1446-1" aria-hidden="true" tabindex="-1"></a>Thread 0: grabbed lock!</span>
<span id="cb1446-2"><a href="threads.html#cb1446-2" aria-hidden="true" tabindex="-1"></a>Thread 1: lock already taken :(</span>
<span id="cb1446-3"><a href="threads.html#cb1446-3" aria-hidden="true" tabindex="-1"></a>Thread 4: lock already taken :(</span>
<span id="cb1446-4"><a href="threads.html#cb1446-4" aria-hidden="true" tabindex="-1"></a>Thread 3: grabbed lock!</span>
<span id="cb1446-5"><a href="threads.html#cb1446-5" aria-hidden="true" tabindex="-1"></a>Thread 2: lock already taken :(</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-197">See Also</h3>
<p><a href="threads.html#man-mtx_lock"><code>mtx_lock()</code></a>, <a href="#man-mtx_timedlock"><code>mtx_timedlock()</code></a>, <a href="#man-mtx_unlock"><code>mtx_unlock()</code></a></p>
<hr>
<h2 data-number="66.13" id="man-mtx_unlock"><span class="header-section-number">66.13</span>
<code>mtx_unlock()</code></h2>
<p>Free a mutex when you’re done with the critical section</p>
<h3 class="unnumbered unlisted" id="synopsis-210">Synopsis</h3>
<div class="sourceCode" id="cb1447"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1447-1"><a href="threads.html#cb1447-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1447-2"><a href="threads.html#cb1447-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1447-3"><a href="threads.html#cb1447-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> mtx_unlock<span class="op">(</span>mtx_t <span class="op">*</span>mtx<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-210">Description</h3>
<p>After you’ve done all the dangerous stuff you have to do, wherein the
involved threads should not be stepping on each other’s toes… you can
free up your stranglehold on the mutex by calling
<code>mtx_unlock()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-208">Return Value</h3>
<p>Returns <code>thrd_success</code> on success. Or
<code>thrd_error</code> on error. It’s not very original in this
regard.</p>
<h3 class="unnumbered unlisted" id="example-212">Example</h3>
<p>General-purpose mutex example here, but you can see the
<code>mtx_unlock()</code> in the <code>run()</code> function:</p>
<div class="sourceCode" id="cb1448"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1448-1"><a href="threads.html#cb1448-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1448-2"><a href="threads.html#cb1448-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1448-3"><a href="threads.html#cb1448-3"></a></span>
<span id="cb1448-4"><a href="threads.html#cb1448-4"></a>cnd_t condvar<span class="op">;</span></span>
<span id="cb1448-5"><a href="threads.html#cb1448-5"></a>mtx_t mutex<span class="op">;</span></span>
<span id="cb1448-6"><a href="threads.html#cb1448-6"></a></span>
<span id="cb1448-7"><a href="threads.html#cb1448-7"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1448-8"><a href="threads.html#cb1448-8"></a><span class="op">{</span></span>
<span id="cb1448-9"><a href="threads.html#cb1448-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1448-10"><a href="threads.html#cb1448-10"></a></span>
<span id="cb1448-11"><a href="threads.html#cb1448-11"></a>    <span class="dt">static</span> <span class="dt">int</span> count <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1448-12"><a href="threads.html#cb1448-12"></a></span>
<span id="cb1448-13"><a href="threads.html#cb1448-13"></a>    mtx_lock<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1448-14"><a href="threads.html#cb1448-14"></a></span>
<span id="cb1448-15"><a href="threads.html#cb1448-15"></a>    printf<span class="op">(</span><span class="st">"Thread: I got %d!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> count<span class="op">);</span></span>
<span id="cb1448-16"><a href="threads.html#cb1448-16"></a>    count<span class="op">++;</span></span>
<span id="cb1448-17"><a href="threads.html#cb1448-17"></a></span>
<span id="cb1448-18"><a href="threads.html#cb1448-18"></a>    mtx_unlock<span class="op">(&amp;</span>mutex<span class="op">);</span>  <span class="co">// &lt;-- UNLOCK HERE</span></span>
<span id="cb1448-19"><a href="threads.html#cb1448-19"></a></span>
<span id="cb1448-20"><a href="threads.html#cb1448-20"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1448-21"><a href="threads.html#cb1448-21"></a><span class="op">}</span></span>
<span id="cb1448-22"><a href="threads.html#cb1448-22"></a></span>
<span id="cb1448-23"><a href="threads.html#cb1448-23"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1448-24"><a href="threads.html#cb1448-24"></a></span>
<span id="cb1448-25"><a href="threads.html#cb1448-25"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1448-26"><a href="threads.html#cb1448-26"></a><span class="op">{</span></span>
<span id="cb1448-27"><a href="threads.html#cb1448-27"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1448-28"><a href="threads.html#cb1448-28"></a></span>
<span id="cb1448-29"><a href="threads.html#cb1448-29"></a>    mtx_init<span class="op">(&amp;</span>mutex<span class="op">,</span> mtx_plain<span class="op">);</span></span>
<span id="cb1448-30"><a href="threads.html#cb1448-30"></a></span>
<span id="cb1448-31"><a href="threads.html#cb1448-31"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1448-32"><a href="threads.html#cb1448-32"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1448-33"><a href="threads.html#cb1448-33"></a></span>
<span id="cb1448-34"><a href="threads.html#cb1448-34"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1448-35"><a href="threads.html#cb1448-35"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1448-36"><a href="threads.html#cb1448-36"></a></span>
<span id="cb1448-37"><a href="threads.html#cb1448-37"></a>    mtx_destroy<span class="op">(&amp;</span>mutex<span class="op">);</span></span>
<span id="cb1448-38"><a href="threads.html#cb1448-38"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1449"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1449-1"><a href="threads.html#cb1449-1" aria-hidden="true" tabindex="-1"></a>Thread: I got 0!</span>
<span id="cb1449-2"><a href="threads.html#cb1449-2" aria-hidden="true" tabindex="-1"></a>Thread: I got 1!</span>
<span id="cb1449-3"><a href="threads.html#cb1449-3" aria-hidden="true" tabindex="-1"></a>Thread: I got 2!</span>
<span id="cb1449-4"><a href="threads.html#cb1449-4" aria-hidden="true" tabindex="-1"></a>Thread: I got 3!</span>
<span id="cb1449-5"><a href="threads.html#cb1449-5" aria-hidden="true" tabindex="-1"></a>Thread: I got 4!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-198">See Also</h3>
<p><a href="threads.html#man-mtx_lock"><code>mtx_lock()</code></a>, <a href="#man-mtx_timedlock"><code>mtx_timedlock()</code></a>, <a href="#man-mtx_trylock"><code>mtx_trylock()</code></a></p>
<hr>
<h2 data-number="66.14" id="man-thrd_create"><span class="header-section-number">66.14</span>
<code>thrd_create()</code></h2>
<p>Create a new thread of execution</p>
<h3 class="unnumbered unlisted" id="synopsis-211">Synopsis</h3>
<div class="sourceCode" id="cb1450"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1450-1"><a href="threads.html#cb1450-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1450-2"><a href="threads.html#cb1450-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1450-3"><a href="threads.html#cb1450-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> thrd_create<span class="op">(</span>thrd_t <span class="op">*</span>thr<span class="op">,</span> thrd_start_t func<span class="op">,</span> <span class="dt">void</span> <span class="op">*</span>arg<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-211">Description</h3>
<p>Now <em>you</em> have the POWER!</p>
<p>Right?</p>
<p>This is how you launch new threads to make your program do multiple
things at once<a href="footnotes.html#fn273" class="footnote-ref" id="fnref273" role="doc-noteref"><sup>273</sup></a>!</p>
<p>In order to make this happen, you need to pass a pointer to a
<code>thrd_t</code> that will be used to represent the thread you’re
spawning.</p>
<p>That thread will start running the function you pass a pointer to in
<code>func</code>. This is a value of type <code>thrd_start_t</code>,
which is a pointer to a function that returns an <code>int</code> and
takes a single <code>void*</code> as a parameter, i.e.:</p>
<div class="sourceCode" id="cb1451"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1451-1"><a href="threads.html#cb1451-1" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> thread_run_func<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span></code></pre></div>
<p>And, as you might have guessed, the pointer you pass to
<code>thrd_create()</code> for the <code>arg</code> parameter is passed
on to the <code>func</code> function. This is how you can give
additional information to the thread when it starts up.</p>
<p>Of course, for <code>arg</code>, you have to be sure to pass a
pointer to an object that is thread-safe or per-thread.</p>
<p>If the thread returns from the function, it exits just as if it had
called <code>thrd_exit()</code>.</p>
<p>Finally, the value that the <code>func</code> function returns can be
picked up by the parent thread with <code>thrd_join()</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-209">Return Value</h3>
<p>In the case of goodness, returns <code>thrd_success</code>. If you’re
out of memory, will return <code>thrd_nomem</code>. Otherwise,
<code>thrd_error</code>.</p>
<h3 class="unnumbered unlisted" id="example-213">Example</h3>
<div class="sourceCode" id="cb1452"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1452-1"><a href="threads.html#cb1452-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1452-2"><a href="threads.html#cb1452-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1452-3"><a href="threads.html#cb1452-3"></a></span>
<span id="cb1452-4"><a href="threads.html#cb1452-4"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1452-5"><a href="threads.html#cb1452-5"></a><span class="op">{</span></span>
<span id="cb1452-6"><a href="threads.html#cb1452-6"></a>    <span class="dt">int</span> id <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span></span>
<span id="cb1452-7"><a href="threads.html#cb1452-7"></a></span>
<span id="cb1452-8"><a href="threads.html#cb1452-8"></a>    printf<span class="op">(</span><span class="st">"Thread %d: I'm alive!!</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> id<span class="op">);</span></span>
<span id="cb1452-9"><a href="threads.html#cb1452-9"></a></span>
<span id="cb1452-10"><a href="threads.html#cb1452-10"></a>    <span class="cf">return</span> id<span class="op">;</span></span>
<span id="cb1452-11"><a href="threads.html#cb1452-11"></a><span class="op">}</span></span>
<span id="cb1452-12"><a href="threads.html#cb1452-12"></a></span>
<span id="cb1452-13"><a href="threads.html#cb1452-13"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1452-14"><a href="threads.html#cb1452-14"></a></span>
<span id="cb1452-15"><a href="threads.html#cb1452-15"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1452-16"><a href="threads.html#cb1452-16"></a><span class="op">{</span></span>
<span id="cb1452-17"><a href="threads.html#cb1452-17"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1452-18"><a href="threads.html#cb1452-18"></a>    <span class="dt">int</span> id<span class="op">[</span>THREAD_COUNT<span class="op">];</span>  <span class="co">// One of these per thread</span></span>
<span id="cb1452-19"><a href="threads.html#cb1452-19"></a></span>
<span id="cb1452-20"><a href="threads.html#cb1452-20"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1452-21"><a href="threads.html#cb1452-21"></a>        id<span class="op">[</span>i<span class="op">]</span> <span class="op">=</span> i<span class="op">;</span> <span class="co">// Let's pass in the thread number as the ID</span></span>
<span id="cb1452-22"><a href="threads.html#cb1452-22"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> id <span class="op">+</span> i<span class="op">);</span></span>
<span id="cb1452-23"><a href="threads.html#cb1452-23"></a>    <span class="op">}</span></span>
<span id="cb1452-24"><a href="threads.html#cb1452-24"></a></span>
<span id="cb1452-25"><a href="threads.html#cb1452-25"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1452-26"><a href="threads.html#cb1452-26"></a>        <span class="dt">int</span> res<span class="op">;</span></span>
<span id="cb1452-27"><a href="threads.html#cb1452-27"></a></span>
<span id="cb1452-28"><a href="threads.html#cb1452-28"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> <span class="op">&amp;</span>res<span class="op">);</span></span>
<span id="cb1452-29"><a href="threads.html#cb1452-29"></a></span>
<span id="cb1452-30"><a href="threads.html#cb1452-30"></a>        printf<span class="op">(</span><span class="st">"Main: thread %d exited with code %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">,</span> res<span class="op">);</span></span>
<span id="cb1452-31"><a href="threads.html#cb1452-31"></a>    <span class="op">}</span></span>
<span id="cb1452-32"><a href="threads.html#cb1452-32"></a><span class="op">}</span></span></code></pre></div>
<p>Output (might vary from run to run):</p>
<div class="sourceCode" id="cb1453"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1453-1"><a href="threads.html#cb1453-1" aria-hidden="true" tabindex="-1"></a>Thread 1: I'm alive!!</span>
<span id="cb1453-2"><a href="threads.html#cb1453-2" aria-hidden="true" tabindex="-1"></a>Thread 0: I'm alive!!</span>
<span id="cb1453-3"><a href="threads.html#cb1453-3" aria-hidden="true" tabindex="-1"></a>Thread 3: I'm alive!!</span>
<span id="cb1453-4"><a href="threads.html#cb1453-4" aria-hidden="true" tabindex="-1"></a>Thread 2: I'm alive!!</span>
<span id="cb1453-5"><a href="threads.html#cb1453-5" aria-hidden="true" tabindex="-1"></a>Main: thread 0 exited with code 0</span>
<span id="cb1453-6"><a href="threads.html#cb1453-6" aria-hidden="true" tabindex="-1"></a>Main: thread 1 exited with code 1</span>
<span id="cb1453-7"><a href="threads.html#cb1453-7" aria-hidden="true" tabindex="-1"></a>Main: thread 2 exited with code 2</span>
<span id="cb1453-8"><a href="threads.html#cb1453-8" aria-hidden="true" tabindex="-1"></a>Main: thread 3 exited with code 3</span>
<span id="cb1453-9"><a href="threads.html#cb1453-9" aria-hidden="true" tabindex="-1"></a>Thread 4: I'm alive!!</span>
<span id="cb1453-10"><a href="threads.html#cb1453-10" aria-hidden="true" tabindex="-1"></a>Main: thread 4 exited with code 4</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-199">See Also</h3>
<p><a href="threads.html#man-thrd_exit"><code>thrd_exit()</code></a>, <a href="#man-thrd_join"><code>thrd_join()</code></a></p>
<hr>
<h2 data-number="66.15" id="man-thrd_current"><span class="header-section-number">66.15</span>
<code>thrd_current()</code></h2>
<p>Get the ID of the calling thread</p>
<h3 class="unnumbered unlisted" id="synopsis-212">Synopsis</h3>
<div class="sourceCode" id="cb1454"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1454-1"><a href="threads.html#cb1454-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1454-2"><a href="threads.html#cb1454-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1454-3"><a href="threads.html#cb1454-3" aria-hidden="true" tabindex="-1"></a>thrd_t thrd_current<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-212">Description</h3>
<p>Each thread has an opaque ID of type <code>thrd_t</code>. This is the
value we see get initialized when we call <a href="#man-thrd_create"><code>thrd_create()</code></a>.</p>
<p>But what if you want to get the ID of the currently running
thread?</p>
<p>No problem! Just call this function and it will be returned to
you.</p>
<p>Why? Who knows!</p>
<p>Well, to be honest, I could see it being used a couple places.</p>
<ol type="1">
<li>You could use it to have a thread detach itself with
<code>thrd_detach()</code>. I’m not sure why you’d want to do this,
however.</li>
<li>You could use it to compare this thread’s ID with another you have
stored in a variable somewhere by using the <code>thrd_equal()</code>
function. Seems like the most legit use.</li>
<li>…</li>
<li>Profit!</li>
</ol>
<p>If anyone has another use, please let me know.</p>
<h3 class="unnumbered unlisted" id="return-value-210">Return Value</h3>
<p>Returns the calling thread’s ID.</p>
<h3 class="unnumbered unlisted" id="example-214">Example</h3>
<p>Here’s a general example that shows getting the current thread ID and
comparing it to a previously-recorded thread ID and taking exciting
action based on the result! Starring Arnold Schwarzenegger!</p>
<div class="sourceCode" id="cb1455"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1455-1"><a href="threads.html#cb1455-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1455-2"><a href="threads.html#cb1455-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1455-3"><a href="threads.html#cb1455-3"></a></span>
<span id="cb1455-4"><a href="threads.html#cb1455-4"></a>thrd_t first_thread_id<span class="op">;</span></span>
<span id="cb1455-5"><a href="threads.html#cb1455-5"></a></span>
<span id="cb1455-6"><a href="threads.html#cb1455-6"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1455-7"><a href="threads.html#cb1455-7"></a><span class="op">{</span></span>
<span id="cb1455-8"><a href="threads.html#cb1455-8"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1455-9"><a href="threads.html#cb1455-9"></a></span>
<span id="cb1455-10"><a href="threads.html#cb1455-10"></a>    thrd_t my_id <span class="op">=</span> thrd_current<span class="op">();</span>   <span class="co">// &lt;-- GET MY THREAD ID</span></span>
<span id="cb1455-11"><a href="threads.html#cb1455-11"></a></span>
<span id="cb1455-12"><a href="threads.html#cb1455-12"></a>    <span class="cf">if</span> <span class="op">(</span>thrd_equal<span class="op">(</span>my_id<span class="op">,</span> first_thread_id<span class="op">))</span></span>
<span id="cb1455-13"><a href="threads.html#cb1455-13"></a>        printf<span class="op">(</span><span class="st">"I'm the first thread!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1455-14"><a href="threads.html#cb1455-14"></a>    <span class="cf">else</span></span>
<span id="cb1455-15"><a href="threads.html#cb1455-15"></a>        printf<span class="op">(</span><span class="st">"I'm not the first!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1455-16"><a href="threads.html#cb1455-16"></a></span>
<span id="cb1455-17"><a href="threads.html#cb1455-17"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1455-18"><a href="threads.html#cb1455-18"></a><span class="op">}</span></span>
<span id="cb1455-19"><a href="threads.html#cb1455-19"></a></span>
<span id="cb1455-20"><a href="threads.html#cb1455-20"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1455-21"><a href="threads.html#cb1455-21"></a><span class="op">{</span></span>
<span id="cb1455-22"><a href="threads.html#cb1455-22"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1455-23"><a href="threads.html#cb1455-23"></a></span>
<span id="cb1455-24"><a href="threads.html#cb1455-24"></a>    thrd_create<span class="op">(&amp;</span>first_thread_id<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1455-25"><a href="threads.html#cb1455-25"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1455-26"><a href="threads.html#cb1455-26"></a></span>
<span id="cb1455-27"><a href="threads.html#cb1455-27"></a>    thrd_join<span class="op">(</span>first_thread_id<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1455-28"><a href="threads.html#cb1455-28"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1455-29"><a href="threads.html#cb1455-29"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1456"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1456-1"><a href="threads.html#cb1456-1" aria-hidden="true" tabindex="-1"></a>Come on, you got what you want, Cohaagen! Give deez people ay-ah!</span></code></pre></div>
<p>No, wait, that’s an Arnold Schwarzenegger quote from <em>Total
Recall</em>, one of the best science fiction films of all time. Watch it
now and then come back to finish this reference page.</p>
<p>Man–what an ending! And Johnny Cab? So excellent. Anyway!</p>
<p>Output:</p>
<div class="sourceCode" id="cb1457"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1457-1"><a href="threads.html#cb1457-1" aria-hidden="true" tabindex="-1"></a>I'm the first thread!</span>
<span id="cb1457-2"><a href="threads.html#cb1457-2" aria-hidden="true" tabindex="-1"></a>I'm not the first!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-200">See Also</h3>
<p><a href="threads.html#man-thrd_equal"><code>thrd_equal()</code></a>, <a href="#man-thrd_detach"><code>thrd_detach()</code></a></p>
<hr>
<h2 data-number="66.16" id="man-thrd_detach"><span class="header-section-number">66.16</span>
<code>thrd_detach()</code></h2>
<p>Automatically clean up threads when they exit</p>
<h3 class="unnumbered unlisted" id="synopsis-213">Synopsis</h3>
<div class="sourceCode" id="cb1458"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1458-1"><a href="threads.html#cb1458-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1458-2"><a href="threads.html#cb1458-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1458-3"><a href="threads.html#cb1458-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> thrd_detach<span class="op">(</span>thrd_t thr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-213">Description</h3>
<p>Normally you have to <code>thrd_join()</code> to get resources
associated with a deceased thread cleaned up. (Most notably, its exit
status is still floating around waiting to get picked up.)</p>
<p>But if you call <code>thrd_detach()</code> on the thread first,
manual cleanup isn’t necessary. They just exit and are cleaned up by the
OS.</p>
<p>(Note that when the main thread dies, all the threads die in any
case.)</p>
<h3 class="unnumbered unlisted" id="return-value-211">Return Value</h3>
<p><code>thrd_success</code> if the thread successfully detaches,
<code>thrd_error</code> otherwise.</p>
<h3 class="unnumbered unlisted" id="example-215">Example</h3>
<div class="sourceCode" id="cb1459"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1459-1"><a href="threads.html#cb1459-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1459-2"><a href="threads.html#cb1459-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1459-3"><a href="threads.html#cb1459-3"></a></span>
<span id="cb1459-4"><a href="threads.html#cb1459-4"></a>thrd_t first_thread_id<span class="op">;</span></span>
<span id="cb1459-5"><a href="threads.html#cb1459-5"></a></span>
<span id="cb1459-6"><a href="threads.html#cb1459-6"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1459-7"><a href="threads.html#cb1459-7"></a><span class="op">{</span></span>
<span id="cb1459-8"><a href="threads.html#cb1459-8"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1459-9"><a href="threads.html#cb1459-9"></a></span>
<span id="cb1459-10"><a href="threads.html#cb1459-10"></a>    printf<span class="op">(</span><span class="st">"Thread running!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1459-11"><a href="threads.html#cb1459-11"></a></span>
<span id="cb1459-12"><a href="threads.html#cb1459-12"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1459-13"><a href="threads.html#cb1459-13"></a><span class="op">}</span></span>
<span id="cb1459-14"><a href="threads.html#cb1459-14"></a></span>
<span id="cb1459-15"><a href="threads.html#cb1459-15"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1459-16"><a href="threads.html#cb1459-16"></a></span>
<span id="cb1459-17"><a href="threads.html#cb1459-17"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1459-18"><a href="threads.html#cb1459-18"></a><span class="op">{</span></span>
<span id="cb1459-19"><a href="threads.html#cb1459-19"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1459-20"><a href="threads.html#cb1459-20"></a></span>
<span id="cb1459-21"><a href="threads.html#cb1459-21"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1459-22"><a href="threads.html#cb1459-22"></a>        thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1459-23"><a href="threads.html#cb1459-23"></a>        thrd_detach<span class="op">(</span>t<span class="op">);</span></span>
<span id="cb1459-24"><a href="threads.html#cb1459-24"></a>    <span class="op">}</span></span>
<span id="cb1459-25"><a href="threads.html#cb1459-25"></a></span>
<span id="cb1459-26"><a href="threads.html#cb1459-26"></a>    <span class="co">// No need to thrd_join()!</span></span>
<span id="cb1459-27"><a href="threads.html#cb1459-27"></a></span>
<span id="cb1459-28"><a href="threads.html#cb1459-28"></a>    <span class="co">// Sleep a quarter second to let them all finish</span></span>
<span id="cb1459-29"><a href="threads.html#cb1459-29"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_nsec<span class="op">=</span><span class="dv">250000000</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1459-30"><a href="threads.html#cb1459-30"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-201">See Also</h3>
<p><a href="threads.html#man-thrd_join"><code>thrd_join()</code></a>, <a href="#man-thrd_exit"><code>thrd_exit()</code></a></p>
<hr>
<h2 data-number="66.17" id="man-thrd_equal"><span class="header-section-number">66.17</span>
<code>thrd_equal()</code></h2>
<p>Compare two thread descriptors for equality</p>
<h3 class="unnumbered unlisted" id="synopsis-214">Synopsis</h3>
<div class="sourceCode" id="cb1460"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1460-1"><a href="threads.html#cb1460-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1460-2"><a href="threads.html#cb1460-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1460-3"><a href="threads.html#cb1460-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> thrd_equal<span class="op">(</span>thrd_t thr0<span class="op">,</span> thrd_t thr1<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-214">Description</h3>
<p>If you have two thread descriptors in <code>thrd_t</code> variables,
you can test them for equality with this function.</p>
<p>For example, maybe one of the threads has special powers the others
don’t, and the run function needs to be able to tell them apart, as in
the example.</p>
<h3 class="unnumbered unlisted" id="return-value-212">Return Value</h3>
<p>Returns non-zero if the threads are equal. Returns <code>0</code> if
they’re not.</p>
<h3 class="unnumbered unlisted" id="example-216">Example</h3>
<p>Here’s a general example that shows getting the current thread ID and
comparing it to a previously-recorded thread ID and taking boring action
based on the result.</p>
<div class="sourceCode" id="cb1461"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1461-1"><a href="threads.html#cb1461-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1461-2"><a href="threads.html#cb1461-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1461-3"><a href="threads.html#cb1461-3"></a></span>
<span id="cb1461-4"><a href="threads.html#cb1461-4"></a>thrd_t first_thread_id<span class="op">;</span></span>
<span id="cb1461-5"><a href="threads.html#cb1461-5"></a></span>
<span id="cb1461-6"><a href="threads.html#cb1461-6"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1461-7"><a href="threads.html#cb1461-7"></a><span class="op">{</span></span>
<span id="cb1461-8"><a href="threads.html#cb1461-8"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1461-9"><a href="threads.html#cb1461-9"></a></span>
<span id="cb1461-10"><a href="threads.html#cb1461-10"></a>    thrd_t my_id <span class="op">=</span> thrd_current<span class="op">();</span></span>
<span id="cb1461-11"><a href="threads.html#cb1461-11"></a></span>
<span id="cb1461-12"><a href="threads.html#cb1461-12"></a>    <span class="cf">if</span> <span class="op">(</span>thrd_equal<span class="op">(</span>my_id<span class="op">,</span> first_thread_id<span class="op">))</span>  <span class="co">// &lt;-- COMPARE!</span></span>
<span id="cb1461-13"><a href="threads.html#cb1461-13"></a>        printf<span class="op">(</span><span class="st">"I'm the first thread!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1461-14"><a href="threads.html#cb1461-14"></a>    <span class="cf">else</span></span>
<span id="cb1461-15"><a href="threads.html#cb1461-15"></a>        printf<span class="op">(</span><span class="st">"I'm not the first!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1461-16"><a href="threads.html#cb1461-16"></a></span>
<span id="cb1461-17"><a href="threads.html#cb1461-17"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1461-18"><a href="threads.html#cb1461-18"></a><span class="op">}</span></span>
<span id="cb1461-19"><a href="threads.html#cb1461-19"></a></span>
<span id="cb1461-20"><a href="threads.html#cb1461-20"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1461-21"><a href="threads.html#cb1461-21"></a><span class="op">{</span></span>
<span id="cb1461-22"><a href="threads.html#cb1461-22"></a>    thrd_t t<span class="op">;</span></span>
<span id="cb1461-23"><a href="threads.html#cb1461-23"></a></span>
<span id="cb1461-24"><a href="threads.html#cb1461-24"></a>    thrd_create<span class="op">(&amp;</span>first_thread_id<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1461-25"><a href="threads.html#cb1461-25"></a>    thrd_create<span class="op">(&amp;</span>t<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1461-26"><a href="threads.html#cb1461-26"></a></span>
<span id="cb1461-27"><a href="threads.html#cb1461-27"></a>    thrd_join<span class="op">(</span>first_thread_id<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1461-28"><a href="threads.html#cb1461-28"></a>    thrd_join<span class="op">(</span>t<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1461-29"><a href="threads.html#cb1461-29"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1462"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1462-1"><a href="threads.html#cb1462-1" aria-hidden="true" tabindex="-1"></a>I'm the first thread!</span>
<span id="cb1462-2"><a href="threads.html#cb1462-2" aria-hidden="true" tabindex="-1"></a>I'm not the first!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-202">See Also</h3>
<p><a href="threads.html#man-thrd_current"><code>thrd_current()</code></a></p>
<hr>
<h2 data-number="66.18" id="man-thrd_exit"><span class="header-section-number">66.18</span> <code>thrd_exit()</code></h2>
<p>Stop and exit this thread</p>
<h3 class="unnumbered unlisted" id="synopsis-215">Synopsis</h3>
<div class="sourceCode" id="cb1463"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1463-1"><a href="threads.html#cb1463-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1463-2"><a href="threads.html#cb1463-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1463-3"><a href="threads.html#cb1463-3" aria-hidden="true" tabindex="-1"></a><span class="kw">_Noreturn</span> <span class="dt">void</span> thrd_exit<span class="op">(</span><span class="dt">int</span> res<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-215">Description</h3>
<p>A thread commonly exits by returning from its run function. But if it
wants to exit early (perhaps from deeper in the call stack), this
function will get that done.</p>
<p>The <code>res</code> code can be picked up by a thread calling
<code>thrd_join()</code>, and is equivalent to returning a value from
the run function.</p>
<p>Like with returning from the run function, this will also properly
clean up all the thread-specific storage associated with this thread—all
the destructors for the threads TSS variables will be called. If there
are any remaining TSS variables with destructors after the first round
of destruction<a href="footnotes.html#fn274" class="footnote-ref" id="fnref274" role="doc-noteref"><sup>274</sup></a>, the remaining destructors will be
called. This happens repeatedly until there are no more, or the number
of rounds of carnage reaches <code>TSS_DTOR_ITERATIONS</code>.</p>
<p>If the main thread calls this, it’s as if you called
<code>exit(EXIT_SUCCESS)</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-213">Return Value</h3>
<p>This function never returns because the thread calling it is killed
in the process. Trippy!</p>
<h3 class="unnumbered unlisted" id="example-217">Example</h3>
<p>Threads in this example exit early with result <code>22</code> if
they get a <code>NULL</code> value for <code>arg</code>.</p>
<div class="sourceCode" id="cb1464"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1464-1"><a href="threads.html#cb1464-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1464-2"><a href="threads.html#cb1464-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1464-3"><a href="threads.html#cb1464-3"></a></span>
<span id="cb1464-4"><a href="threads.html#cb1464-4"></a>thrd_t first_thread_id<span class="op">;</span></span>
<span id="cb1464-5"><a href="threads.html#cb1464-5"></a></span>
<span id="cb1464-6"><a href="threads.html#cb1464-6"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1464-7"><a href="threads.html#cb1464-7"></a><span class="op">{</span></span>
<span id="cb1464-8"><a href="threads.html#cb1464-8"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1464-9"><a href="threads.html#cb1464-9"></a></span>
<span id="cb1464-10"><a href="threads.html#cb1464-10"></a>    <span class="cf">if</span> <span class="op">(</span>arg <span class="op">==</span> NULL<span class="op">)</span></span>
<span id="cb1464-11"><a href="threads.html#cb1464-11"></a>        thrd_exit<span class="op">(</span><span class="dv">22</span><span class="op">);</span></span>
<span id="cb1464-12"><a href="threads.html#cb1464-12"></a></span>
<span id="cb1464-13"><a href="threads.html#cb1464-13"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1464-14"><a href="threads.html#cb1464-14"></a><span class="op">}</span></span>
<span id="cb1464-15"><a href="threads.html#cb1464-15"></a></span>
<span id="cb1464-16"><a href="threads.html#cb1464-16"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1464-17"><a href="threads.html#cb1464-17"></a></span>
<span id="cb1464-18"><a href="threads.html#cb1464-18"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1464-19"><a href="threads.html#cb1464-19"></a><span class="op">{</span></span>
<span id="cb1464-20"><a href="threads.html#cb1464-20"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1464-21"><a href="threads.html#cb1464-21"></a></span>
<span id="cb1464-22"><a href="threads.html#cb1464-22"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1464-23"><a href="threads.html#cb1464-23"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> i <span class="op">==</span> <span class="dv">2</span><span class="op">?</span> NULL<span class="op">:</span> <span class="st">"spatula"</span><span class="op">);</span></span>
<span id="cb1464-24"><a href="threads.html#cb1464-24"></a></span>
<span id="cb1464-25"><a href="threads.html#cb1464-25"></a></span>
<span id="cb1464-26"><a href="threads.html#cb1464-26"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1464-27"><a href="threads.html#cb1464-27"></a>        <span class="dt">int</span> res<span class="op">;</span></span>
<span id="cb1464-28"><a href="threads.html#cb1464-28"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> <span class="op">&amp;</span>res<span class="op">);</span></span>
<span id="cb1464-29"><a href="threads.html#cb1464-29"></a></span>
<span id="cb1464-30"><a href="threads.html#cb1464-30"></a>        printf<span class="op">(</span><span class="st">"Thread %d exited with code %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">,</span> res<span class="op">);</span></span>
<span id="cb1464-31"><a href="threads.html#cb1464-31"></a>    <span class="op">}</span></span>
<span id="cb1464-32"><a href="threads.html#cb1464-32"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1465"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1465-1"><a href="threads.html#cb1465-1" aria-hidden="true" tabindex="-1"></a>Thread 0 exited with code 0</span>
<span id="cb1465-2"><a href="threads.html#cb1465-2" aria-hidden="true" tabindex="-1"></a>Thread 1 exited with code 0</span>
<span id="cb1465-3"><a href="threads.html#cb1465-3" aria-hidden="true" tabindex="-1"></a>Thread 2 exited with code 22</span>
<span id="cb1465-4"><a href="threads.html#cb1465-4" aria-hidden="true" tabindex="-1"></a>Thread 3 exited with code 0</span>
<span id="cb1465-5"><a href="threads.html#cb1465-5" aria-hidden="true" tabindex="-1"></a>Thread 4 exited with code 0</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-203">See Also</h3>
<p><a href="threads.html#man-thrd_join"><code>thrd_join()</code></a></p>
<hr>
<h2 data-number="66.19" id="man-thrd_join"><span class="header-section-number">66.19</span> <code>thrd_join()</code></h2>
<p>Wait for a thread to exit</p>
<h3 class="unnumbered unlisted" id="synopsis-216">Synopsis</h3>
<div class="sourceCode" id="cb1466"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1466-1"><a href="threads.html#cb1466-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1466-2"><a href="threads.html#cb1466-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1466-3"><a href="threads.html#cb1466-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> thrd_join<span class="op">(</span>thrd_t thr<span class="op">,</span> <span class="dt">int</span> <span class="op">*</span>res<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-216">Description</h3>
<p>When a parent thread fires off some child threads, it can wait for
them to complete with this call</p>
<h3 class="unnumbered unlisted" id="return-value-214">Return Value</h3>
<h3 class="unnumbered unlisted" id="example-218">Example</h3>
<p>Threads in this example exit early with result <code>22</code> if
they get a <code>NULL</code> value for <code>arg</code>. The parent
thread picks up this result code with <code>thrd_join()</code>.</p>
<div class="sourceCode" id="cb1467"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1467-1"><a href="threads.html#cb1467-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1467-2"><a href="threads.html#cb1467-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1467-3"><a href="threads.html#cb1467-3"></a></span>
<span id="cb1467-4"><a href="threads.html#cb1467-4"></a>thrd_t first_thread_id<span class="op">;</span></span>
<span id="cb1467-5"><a href="threads.html#cb1467-5"></a></span>
<span id="cb1467-6"><a href="threads.html#cb1467-6"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1467-7"><a href="threads.html#cb1467-7"></a><span class="op">{</span></span>
<span id="cb1467-8"><a href="threads.html#cb1467-8"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1467-9"><a href="threads.html#cb1467-9"></a></span>
<span id="cb1467-10"><a href="threads.html#cb1467-10"></a>    <span class="cf">if</span> <span class="op">(</span>arg <span class="op">==</span> NULL<span class="op">)</span></span>
<span id="cb1467-11"><a href="threads.html#cb1467-11"></a>        thrd_exit<span class="op">(</span><span class="dv">22</span><span class="op">);</span></span>
<span id="cb1467-12"><a href="threads.html#cb1467-12"></a></span>
<span id="cb1467-13"><a href="threads.html#cb1467-13"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1467-14"><a href="threads.html#cb1467-14"></a><span class="op">}</span></span>
<span id="cb1467-15"><a href="threads.html#cb1467-15"></a></span>
<span id="cb1467-16"><a href="threads.html#cb1467-16"></a><span class="pp">#define THREAD_COUNT 5</span></span>
<span id="cb1467-17"><a href="threads.html#cb1467-17"></a></span>
<span id="cb1467-18"><a href="threads.html#cb1467-18"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1467-19"><a href="threads.html#cb1467-19"></a><span class="op">{</span></span>
<span id="cb1467-20"><a href="threads.html#cb1467-20"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1467-21"><a href="threads.html#cb1467-21"></a></span>
<span id="cb1467-22"><a href="threads.html#cb1467-22"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1467-23"><a href="threads.html#cb1467-23"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> i <span class="op">==</span> <span class="dv">2</span><span class="op">?</span> NULL<span class="op">:</span> <span class="st">"spatula"</span><span class="op">);</span></span>
<span id="cb1467-24"><a href="threads.html#cb1467-24"></a></span>
<span id="cb1467-25"><a href="threads.html#cb1467-25"></a></span>
<span id="cb1467-26"><a href="threads.html#cb1467-26"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1467-27"><a href="threads.html#cb1467-27"></a>        <span class="dt">int</span> res<span class="op">;</span></span>
<span id="cb1467-28"><a href="threads.html#cb1467-28"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> <span class="op">&amp;</span>res<span class="op">);</span></span>
<span id="cb1467-29"><a href="threads.html#cb1467-29"></a></span>
<span id="cb1467-30"><a href="threads.html#cb1467-30"></a>        printf<span class="op">(</span><span class="st">"Thread %d exited with code %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">,</span> res<span class="op">);</span></span>
<span id="cb1467-31"><a href="threads.html#cb1467-31"></a>    <span class="op">}</span></span>
<span id="cb1467-32"><a href="threads.html#cb1467-32"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1468"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1468-1"><a href="threads.html#cb1468-1" aria-hidden="true" tabindex="-1"></a>Thread 0 exited with code 0</span>
<span id="cb1468-2"><a href="threads.html#cb1468-2" aria-hidden="true" tabindex="-1"></a>Thread 1 exited with code 0</span>
<span id="cb1468-3"><a href="threads.html#cb1468-3" aria-hidden="true" tabindex="-1"></a>Thread 2 exited with code 22</span>
<span id="cb1468-4"><a href="threads.html#cb1468-4" aria-hidden="true" tabindex="-1"></a>Thread 3 exited with code 0</span>
<span id="cb1468-5"><a href="threads.html#cb1468-5" aria-hidden="true" tabindex="-1"></a>Thread 4 exited with code 0</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-204">See Also</h3>
<p><a href="threads.html#man-thrd_exit"><code>thrd_exit()</code></a></p>
<h2 data-number="66.20" id="man-thrd_sleep"><span class="header-section-number">66.20</span>
<code>thrd_sleep()</code></h2>
<p>Sleep for a specific number of seconds and nanoseconds</p>
<h3 class="unnumbered unlisted" id="synopsis-217">Synopsis</h3>
<div class="sourceCode" id="cb1469"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1469-1"><a href="threads.html#cb1469-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1469-2"><a href="threads.html#cb1469-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1469-3"><a href="threads.html#cb1469-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> thrd_sleep<span class="op">(</span><span class="dt">const</span> <span class="kw">struct</span> timespec <span class="op">*</span>duration<span class="op">,</span> <span class="kw">struct</span> timespec <span class="op">*</span>remaining<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-217">Description</h3>
<p>This function puts the current thread to sleep for a while<a href="#fn275" class="footnote-ref" id="fnref275" role="doc-noteref"><sup>275</sup></a> allowing other threads to run.</p>
<p>The calling thread will wake up after the time has elapsed, or if it
gets interrupted by a signal or something.</p>
<p>If it doesn’t get interrupted, it’ll sleep at least as long as you
asked. Maybe a tad longer. You know how hard it can be to get out of
bed.</p>
<p>The structure looks like this:</p>
<div class="sourceCode" id="cb1470"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1470-1"><a href="threads.html#cb1470-1" aria-hidden="true" tabindex="-1"></a><span class="kw">struct</span> timespec <span class="op">{</span></span>
<span id="cb1470-2"><a href="threads.html#cb1470-2" aria-hidden="true" tabindex="-1"></a>    <span class="dt">time_t</span> tv_sec<span class="op">;</span>   <span class="co">// Seconds</span></span>
<span id="cb1470-3"><a href="threads.html#cb1470-3" aria-hidden="true" tabindex="-1"></a>    <span class="dt">long</span>   tv_nsec<span class="op">;</span>  <span class="co">// Nanoseconds (billionths of a second)</span></span>
<span id="cb1470-4"><a href="threads.html#cb1470-4" aria-hidden="true" tabindex="-1"></a><span class="op">};</span></span></code></pre></div>
<p>Don’t set <code>tv_nsec</code> greater than 999,999,999. I can’t see
what officially happens if you do, but on my system
<code>thrd_sleep()</code> returns <code>-2</code> and fails.</p>
<h3 class="unnumbered unlisted" id="return-value-215">Return Value</h3>
<p>Returns <code>0</code> on timeout, or <code>-1</code> if interrupted
by a signal. Or any negative value on some other error. Weirdly, the
spec allows this “other error negative value” to also be
<code>-1</code>, so good luck with that.</p>
<h3 class="unnumbered unlisted" id="example-219">Example</h3>
<div class="sourceCode" id="cb1471"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1471-1"><a href="threads.html#cb1471-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1471-2"><a href="threads.html#cb1471-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1471-3"><a href="threads.html#cb1471-3"></a></span>
<span id="cb1471-4"><a href="threads.html#cb1471-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1471-5"><a href="threads.html#cb1471-5"></a><span class="op">{</span></span>
<span id="cb1471-6"><a href="threads.html#cb1471-6"></a>    <span class="co">// Sleep for 3.25 seconds</span></span>
<span id="cb1471-7"><a href="threads.html#cb1471-7"></a>    thrd_sleep<span class="op">(&amp;(</span><span class="kw">struct</span> timespec<span class="op">){.</span>tv_sec<span class="op">=</span><span class="dv">3</span><span class="op">,</span> <span class="op">.</span>tv_nsec<span class="op">=</span><span class="dv">250000000</span><span class="op">},</span> NULL<span class="op">);</span></span>
<span id="cb1471-8"><a href="threads.html#cb1471-8"></a></span>
<span id="cb1471-9"><a href="threads.html#cb1471-9"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1471-10"><a href="threads.html#cb1471-10"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-205">See Also</h3>
<p><a href="threads.html#man-thrd_yield"><code>thrd_yield()</code></a></p>
<hr>
<h2 data-number="66.21" id="man-thrd_yield"><span class="header-section-number">66.21</span>
<code>thrd_yield()</code></h2>
<p>Stop running that other threads might run</p>
<h3 class="unnumbered unlisted" id="synopsis-218">Synopsis</h3>
<div class="sourceCode" id="cb1472"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1472-1"><a href="threads.html#cb1472-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1472-2"><a href="threads.html#cb1472-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1472-3"><a href="threads.html#cb1472-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> thrd_yield<span class="op">(</span><span class="dt">void</span><span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-218">Description</h3>
<p>If you have a thread that’s hogging the CPU and you want to give your
other threads time to run, you can call <code>thrd_yield()</code>. If
the system sees fit, it will put the calling thread to sleep and one of
the other threads will run instead.</p>
<p>It’s a good way to be “polite” to the other threads in your program
if you want the encourage them to run instead.</p>
<h3 class="unnumbered unlisted" id="return-value-216">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-220">Example</h3>
<p>This example’s kinda poor because the OS is probably going to
reschedule threads on the output anyway, but it gets the point
across.</p>
<p>The main thread is giving other threads a chance to run after every
block of dumb work it does.</p>
<div class="sourceCode" id="cb1473"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1473-1"><a href="threads.html#cb1473-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1473-2"><a href="threads.html#cb1473-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1473-3"><a href="threads.html#cb1473-3"></a></span>
<span id="cb1473-4"><a href="threads.html#cb1473-4"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1473-5"><a href="threads.html#cb1473-5"></a><span class="op">{</span></span>
<span id="cb1473-6"><a href="threads.html#cb1473-6"></a>    <span class="dt">int</span> main_thread <span class="op">=</span> arg <span class="op">!=</span> NULL<span class="op">;</span></span>
<span id="cb1473-7"><a href="threads.html#cb1473-7"></a></span>
<span id="cb1473-8"><a href="threads.html#cb1473-8"></a>    <span class="cf">if</span> <span class="op">(</span>main_thread<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1473-9"><a href="threads.html#cb1473-9"></a>        <span class="dt">long</span> <span class="dt">int</span> total <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1473-10"><a href="threads.html#cb1473-10"></a></span>
<span id="cb1473-11"><a href="threads.html#cb1473-11"></a>        <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> <span class="dv">10</span><span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1473-12"><a href="threads.html#cb1473-12"></a>            <span class="cf">for</span> <span class="op">(</span><span class="dt">long</span> <span class="dt">int</span> j <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> j <span class="op">&lt;</span> <span class="dv">1000</span><span class="bu">L</span><span class="op">;</span> j<span class="op">++)</span></span>
<span id="cb1473-13"><a href="threads.html#cb1473-13"></a>                total<span class="op">++;</span></span>
<span id="cb1473-14"><a href="threads.html#cb1473-14"></a></span>
<span id="cb1473-15"><a href="threads.html#cb1473-15"></a>            printf<span class="op">(</span><span class="st">"Main thread yielding</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1473-16"><a href="threads.html#cb1473-16"></a>            thrd_yield<span class="op">();</span>                       <span class="co">// &lt;-- YIELD HERE</span></span>
<span id="cb1473-17"><a href="threads.html#cb1473-17"></a>        <span class="op">}</span></span>
<span id="cb1473-18"><a href="threads.html#cb1473-18"></a>    <span class="op">}</span> <span class="cf">else</span></span>
<span id="cb1473-19"><a href="threads.html#cb1473-19"></a>        printf<span class="op">(</span><span class="st">"Other thread running!</span><span class="sc">\n</span><span class="st">"</span><span class="op">);</span></span>
<span id="cb1473-20"><a href="threads.html#cb1473-20"></a></span>
<span id="cb1473-21"><a href="threads.html#cb1473-21"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1473-22"><a href="threads.html#cb1473-22"></a><span class="op">}</span></span>
<span id="cb1473-23"><a href="threads.html#cb1473-23"></a></span>
<span id="cb1473-24"><a href="threads.html#cb1473-24"></a><span class="pp">#define THREAD_COUNT 10</span></span>
<span id="cb1473-25"><a href="threads.html#cb1473-25"></a></span>
<span id="cb1473-26"><a href="threads.html#cb1473-26"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1473-27"><a href="threads.html#cb1473-27"></a><span class="op">{</span></span>
<span id="cb1473-28"><a href="threads.html#cb1473-28"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1473-29"><a href="threads.html#cb1473-29"></a></span>
<span id="cb1473-30"><a href="threads.html#cb1473-30"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1473-31"><a href="threads.html#cb1473-31"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> i <span class="op">==</span> <span class="dv">0</span><span class="op">?</span> <span class="st">"main"</span><span class="op">:</span> NULL<span class="op">);</span></span>
<span id="cb1473-32"><a href="threads.html#cb1473-32"></a></span>
<span id="cb1473-33"><a href="threads.html#cb1473-33"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span></span>
<span id="cb1473-34"><a href="threads.html#cb1473-34"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1473-35"><a href="threads.html#cb1473-35"></a></span>
<span id="cb1473-36"><a href="threads.html#cb1473-36"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1473-37"><a href="threads.html#cb1473-37"></a><span class="op">}</span></span></code></pre></div>
<p>The output will vary from run to run. Notice that even after
<code>thrd_yield()</code> other threads might not yet be ready to run
and the main thread will continue.</p>
<div class="sourceCode" id="cb1474"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1474-1"><a href="threads.html#cb1474-1" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-2"><a href="threads.html#cb1474-2" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-3"><a href="threads.html#cb1474-3" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-4"><a href="threads.html#cb1474-4" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-5"><a href="threads.html#cb1474-5" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-6"><a href="threads.html#cb1474-6" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-7"><a href="threads.html#cb1474-7" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-8"><a href="threads.html#cb1474-8" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-9"><a href="threads.html#cb1474-9" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-10"><a href="threads.html#cb1474-10" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-11"><a href="threads.html#cb1474-11" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-12"><a href="threads.html#cb1474-12" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-13"><a href="threads.html#cb1474-13" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-14"><a href="threads.html#cb1474-14" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-15"><a href="threads.html#cb1474-15" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-16"><a href="threads.html#cb1474-16" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-17"><a href="threads.html#cb1474-17" aria-hidden="true" tabindex="-1"></a>Main thread yielding</span>
<span id="cb1474-18"><a href="threads.html#cb1474-18" aria-hidden="true" tabindex="-1"></a>Other thread running!</span>
<span id="cb1474-19"><a href="threads.html#cb1474-19" aria-hidden="true" tabindex="-1"></a>Other thread running!</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-206">See Also</h3>
<p><a href="threads.html#man-thrd_sleep"><code>thrd_sleep()</code></a></p>
<hr>
<h2 data-number="66.22" id="man-tss_create"><span class="header-section-number">66.22</span>
<code>tss_create()</code></h2>
<p>Create new thread-specific storage</p>
<h3 class="unnumbered unlisted" id="synopsis-219">Synopsis</h3>
<div class="sourceCode" id="cb1475"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1475-1"><a href="threads.html#cb1475-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1475-2"><a href="threads.html#cb1475-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1475-3"><a href="threads.html#cb1475-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> tss_create<span class="op">(</span>tss_t <span class="op">*</span>key<span class="op">,</span> tss_dtor_t dtor<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-219">Description</h3>
<p>This helps when you need per-thread storage of different values.</p>
<p>A common place this comes up is if you have a file scope variable
that is shared between a bunch of functions and often returned. That’s
not threadsafe. One way to refactor is to replace it with
thread-specific storage so that each thread gets their own code and
doesn’t step on other thread’s toes.</p>
<p>To make this work, you pass in a pointer to a <code>tss_t</code>
key—this is the variable you will use in subsequent
<code>tss_set()</code> and <code>tss_get()</code> calls to set and get
the value associated with the key.</p>
<p>The interesting part of this is the <code>dtor</code> destructor
pointer of type <code>tss_dtor_t</code>. This is actually a pointer to a
function that takes a <code>void*</code> argument and returns
<code>void</code>, i.e.</p>
<div class="sourceCode" id="cb1476"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1476-1"><a href="threads.html#cb1476-1" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> dtor<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>p<span class="op">)</span> <span class="op">{</span> <span class="op">...</span> <span class="op">}</span></span></code></pre></div>
<p>This function will be called per thread when the thread exits with
<code>thrd_exit()</code> (or returns from the run function).</p>
<p>It’s unspecified behavior to call this function while other threads’
destructors are running.</p>
<h3 class="unnumbered unlisted" id="return-value-217">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-221">Example</h3>
<p>This is a general-purpose TSS example. Note the TSS variable is
created near the top of <code>main()</code>.</p>
<div class="sourceCode" id="cb1477"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1477-1"><a href="threads.html#cb1477-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1477-2"><a href="threads.html#cb1477-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1477-3"><a href="threads.html#cb1477-3"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1477-4"><a href="threads.html#cb1477-4"></a></span>
<span id="cb1477-5"><a href="threads.html#cb1477-5"></a>tss_t str<span class="op">;</span></span>
<span id="cb1477-6"><a href="threads.html#cb1477-6"></a></span>
<span id="cb1477-7"><a href="threads.html#cb1477-7"></a><span class="dt">void</span> some_function<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1477-8"><a href="threads.html#cb1477-8"></a><span class="op">{</span></span>
<span id="cb1477-9"><a href="threads.html#cb1477-9"></a>    <span class="co">// Retrieve the per-thread value of this string</span></span>
<span id="cb1477-10"><a href="threads.html#cb1477-10"></a>    <span class="dt">char</span> <span class="op">*</span>tss_string <span class="op">=</span> tss_get<span class="op">(</span>str<span class="op">);</span></span>
<span id="cb1477-11"><a href="threads.html#cb1477-11"></a></span>
<span id="cb1477-12"><a href="threads.html#cb1477-12"></a>    <span class="co">// And print it</span></span>
<span id="cb1477-13"><a href="threads.html#cb1477-13"></a>    printf<span class="op">(</span><span class="st">"TSS string: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tss_string<span class="op">);</span></span>
<span id="cb1477-14"><a href="threads.html#cb1477-14"></a><span class="op">}</span></span>
<span id="cb1477-15"><a href="threads.html#cb1477-15"></a></span>
<span id="cb1477-16"><a href="threads.html#cb1477-16"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1477-17"><a href="threads.html#cb1477-17"></a><span class="op">{</span></span>
<span id="cb1477-18"><a href="threads.html#cb1477-18"></a>    <span class="dt">int</span> serial <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span>  <span class="co">// Get this thread's serial number</span></span>
<span id="cb1477-19"><a href="threads.html#cb1477-19"></a>    free<span class="op">(</span>arg<span class="op">);</span></span>
<span id="cb1477-20"><a href="threads.html#cb1477-20"></a></span>
<span id="cb1477-21"><a href="threads.html#cb1477-21"></a>    <span class="co">// malloc() space to hold the data for this thread</span></span>
<span id="cb1477-22"><a href="threads.html#cb1477-22"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> malloc<span class="op">(</span><span class="dv">64</span><span class="op">);</span></span>
<span id="cb1477-23"><a href="threads.html#cb1477-23"></a>    sprintf<span class="op">(</span>s<span class="op">,</span> <span class="st">"thread %d! :)"</span><span class="op">,</span> serial<span class="op">);</span>  <span class="co">// Happy little string</span></span>
<span id="cb1477-24"><a href="threads.html#cb1477-24"></a></span>
<span id="cb1477-25"><a href="threads.html#cb1477-25"></a>    <span class="co">// Set this TSS variable to point at the string</span></span>
<span id="cb1477-26"><a href="threads.html#cb1477-26"></a>    tss_set<span class="op">(</span>str<span class="op">,</span> s<span class="op">);</span></span>
<span id="cb1477-27"><a href="threads.html#cb1477-27"></a></span>
<span id="cb1477-28"><a href="threads.html#cb1477-28"></a>    <span class="co">// Call a function that will get the variable</span></span>
<span id="cb1477-29"><a href="threads.html#cb1477-29"></a>    some_function<span class="op">();</span></span>
<span id="cb1477-30"><a href="threads.html#cb1477-30"></a></span>
<span id="cb1477-31"><a href="threads.html#cb1477-31"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span> <span class="co">// Equivalent to thrd_exit(0); fires destructors</span></span>
<span id="cb1477-32"><a href="threads.html#cb1477-32"></a><span class="op">}</span></span>
<span id="cb1477-33"><a href="threads.html#cb1477-33"></a></span>
<span id="cb1477-34"><a href="threads.html#cb1477-34"></a><span class="pp">#define THREAD_COUNT 15</span></span>
<span id="cb1477-35"><a href="threads.html#cb1477-35"></a></span>
<span id="cb1477-36"><a href="threads.html#cb1477-36"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1477-37"><a href="threads.html#cb1477-37"></a><span class="op">{</span></span>
<span id="cb1477-38"><a href="threads.html#cb1477-38"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1477-39"><a href="threads.html#cb1477-39"></a></span>
<span id="cb1477-40"><a href="threads.html#cb1477-40"></a>    <span class="co">// Make a new TSS variable, the free() function is the destructor</span></span>
<span id="cb1477-41"><a href="threads.html#cb1477-41"></a>    tss_create<span class="op">(&amp;</span>str<span class="op">,</span> free<span class="op">);</span>                  <span class="co">// &lt;-- CREATE TSS VAR!</span></span>
<span id="cb1477-42"><a href="threads.html#cb1477-42"></a></span>
<span id="cb1477-43"><a href="threads.html#cb1477-43"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1477-44"><a href="threads.html#cb1477-44"></a>        <span class="dt">int</span> <span class="op">*</span>n <span class="op">=</span> malloc<span class="op">(</span><span class="kw">sizeof</span> <span class="op">*</span>n<span class="op">);</span>  <span class="co">// Holds a thread serial number</span></span>
<span id="cb1477-45"><a href="threads.html#cb1477-45"></a>        <span class="op">*</span>n <span class="op">=</span> i<span class="op">;</span></span>
<span id="cb1477-46"><a href="threads.html#cb1477-46"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> n<span class="op">);</span></span>
<span id="cb1477-47"><a href="threads.html#cb1477-47"></a>    <span class="op">}</span></span>
<span id="cb1477-48"><a href="threads.html#cb1477-48"></a></span>
<span id="cb1477-49"><a href="threads.html#cb1477-49"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1477-50"><a href="threads.html#cb1477-50"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1477-51"><a href="threads.html#cb1477-51"></a>    <span class="op">}</span></span>
<span id="cb1477-52"><a href="threads.html#cb1477-52"></a></span>
<span id="cb1477-53"><a href="threads.html#cb1477-53"></a>    <span class="co">// And all threads are done, so let's free this</span></span>
<span id="cb1477-54"><a href="threads.html#cb1477-54"></a>    tss_delete<span class="op">(</span>str<span class="op">);</span></span>
<span id="cb1477-55"><a href="threads.html#cb1477-55"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1478"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1478-1"><a href="threads.html#cb1478-1" aria-hidden="true" tabindex="-1"></a>TSS string: thread 0! :)</span>
<span id="cb1478-2"><a href="threads.html#cb1478-2" aria-hidden="true" tabindex="-1"></a>TSS string: thread 2! :)</span>
<span id="cb1478-3"><a href="threads.html#cb1478-3" aria-hidden="true" tabindex="-1"></a>TSS string: thread 1! :)</span>
<span id="cb1478-4"><a href="threads.html#cb1478-4" aria-hidden="true" tabindex="-1"></a>TSS string: thread 5! :)</span>
<span id="cb1478-5"><a href="threads.html#cb1478-5" aria-hidden="true" tabindex="-1"></a>TSS string: thread 3! :)</span>
<span id="cb1478-6"><a href="threads.html#cb1478-6" aria-hidden="true" tabindex="-1"></a>TSS string: thread 6! :)</span>
<span id="cb1478-7"><a href="threads.html#cb1478-7" aria-hidden="true" tabindex="-1"></a>TSS string: thread 4! :)</span>
<span id="cb1478-8"><a href="threads.html#cb1478-8" aria-hidden="true" tabindex="-1"></a>TSS string: thread 7! :)</span>
<span id="cb1478-9"><a href="threads.html#cb1478-9" aria-hidden="true" tabindex="-1"></a>TSS string: thread 8! :)</span>
<span id="cb1478-10"><a href="threads.html#cb1478-10" aria-hidden="true" tabindex="-1"></a>TSS string: thread 9! :)</span>
<span id="cb1478-11"><a href="threads.html#cb1478-11" aria-hidden="true" tabindex="-1"></a>TSS string: thread 10! :)</span>
<span id="cb1478-12"><a href="threads.html#cb1478-12" aria-hidden="true" tabindex="-1"></a>TSS string: thread 13! :)</span>
<span id="cb1478-13"><a href="threads.html#cb1478-13" aria-hidden="true" tabindex="-1"></a>TSS string: thread 12! :)</span>
<span id="cb1478-14"><a href="threads.html#cb1478-14" aria-hidden="true" tabindex="-1"></a>TSS string: thread 11! :)</span>
<span id="cb1478-15"><a href="threads.html#cb1478-15" aria-hidden="true" tabindex="-1"></a>TSS string: thread 14! :)</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-207">See Also</h3>
<p><a href="threads.html#man-tss_delete"><code>tss_delete()</code></a>, <a href="#man-tss_set"><code>tss_set()</code></a>, <a href="#man-tss_get"><code>tss_get()</code></a>, <a href="#man-thrd_exit"><code>thrd_exit()</code></a></p>
<hr>
<h2 data-number="66.23" id="man-tss_delete"><span class="header-section-number">66.23</span>
<code>tss_delete()</code></h2>
<p>Clean up a thread-specific storage variable</p>
<h3 class="unnumbered unlisted" id="synopsis-220">Synopsis</h3>
<div class="sourceCode" id="cb1479"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1479-1"><a href="threads.html#cb1479-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1479-2"><a href="threads.html#cb1479-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1479-3"><a href="threads.html#cb1479-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> tss_delete<span class="op">(</span>tss_t key<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-220">Description</h3>
<p>This is the opposite of <code>tss_create()</code>. You create
(initialize) the TSS variable before using it, then, when all the
threads are done that need it, you delete (deinitialize/free) it with
this.</p>
<p>This doesn’t call any destructors! Those are all called by
<code>thrd_exit()</code>!</p>
<h3 class="unnumbered unlisted" id="return-value-218">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-222">Example</h3>
<p>This is a general-purpose TSS example. Note the TSS variable is
deleted near the bottom of <code>main()</code>.</p>
<div class="sourceCode" id="cb1480"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1480-1"><a href="threads.html#cb1480-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1480-2"><a href="threads.html#cb1480-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1480-3"><a href="threads.html#cb1480-3"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1480-4"><a href="threads.html#cb1480-4"></a></span>
<span id="cb1480-5"><a href="threads.html#cb1480-5"></a>tss_t str<span class="op">;</span></span>
<span id="cb1480-6"><a href="threads.html#cb1480-6"></a></span>
<span id="cb1480-7"><a href="threads.html#cb1480-7"></a><span class="dt">void</span> some_function<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1480-8"><a href="threads.html#cb1480-8"></a><span class="op">{</span></span>
<span id="cb1480-9"><a href="threads.html#cb1480-9"></a>    <span class="co">// Retrieve the per-thread value of this string</span></span>
<span id="cb1480-10"><a href="threads.html#cb1480-10"></a>    <span class="dt">char</span> <span class="op">*</span>tss_string <span class="op">=</span> tss_get<span class="op">(</span>str<span class="op">);</span></span>
<span id="cb1480-11"><a href="threads.html#cb1480-11"></a></span>
<span id="cb1480-12"><a href="threads.html#cb1480-12"></a>    <span class="co">// And print it</span></span>
<span id="cb1480-13"><a href="threads.html#cb1480-13"></a>    printf<span class="op">(</span><span class="st">"TSS string: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tss_string<span class="op">);</span></span>
<span id="cb1480-14"><a href="threads.html#cb1480-14"></a><span class="op">}</span></span>
<span id="cb1480-15"><a href="threads.html#cb1480-15"></a></span>
<span id="cb1480-16"><a href="threads.html#cb1480-16"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1480-17"><a href="threads.html#cb1480-17"></a><span class="op">{</span></span>
<span id="cb1480-18"><a href="threads.html#cb1480-18"></a>    <span class="dt">int</span> serial <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span>  <span class="co">// Get this thread's serial number</span></span>
<span id="cb1480-19"><a href="threads.html#cb1480-19"></a>    free<span class="op">(</span>arg<span class="op">);</span></span>
<span id="cb1480-20"><a href="threads.html#cb1480-20"></a></span>
<span id="cb1480-21"><a href="threads.html#cb1480-21"></a>    <span class="co">// malloc() space to hold the data for this thread</span></span>
<span id="cb1480-22"><a href="threads.html#cb1480-22"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> malloc<span class="op">(</span><span class="dv">64</span><span class="op">);</span></span>
<span id="cb1480-23"><a href="threads.html#cb1480-23"></a>    sprintf<span class="op">(</span>s<span class="op">,</span> <span class="st">"thread %d! :)"</span><span class="op">,</span> serial<span class="op">);</span>  <span class="co">// Happy little string</span></span>
<span id="cb1480-24"><a href="threads.html#cb1480-24"></a></span>
<span id="cb1480-25"><a href="threads.html#cb1480-25"></a>    <span class="co">// Set this TSS variable to point at the string</span></span>
<span id="cb1480-26"><a href="threads.html#cb1480-26"></a>    tss_set<span class="op">(</span>str<span class="op">,</span> s<span class="op">);</span></span>
<span id="cb1480-27"><a href="threads.html#cb1480-27"></a></span>
<span id="cb1480-28"><a href="threads.html#cb1480-28"></a>    <span class="co">// Call a function that will get the variable</span></span>
<span id="cb1480-29"><a href="threads.html#cb1480-29"></a>    some_function<span class="op">();</span></span>
<span id="cb1480-30"><a href="threads.html#cb1480-30"></a></span>
<span id="cb1480-31"><a href="threads.html#cb1480-31"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span> <span class="co">// Equivalent to thrd_exit(0); fires destructors</span></span>
<span id="cb1480-32"><a href="threads.html#cb1480-32"></a><span class="op">}</span></span>
<span id="cb1480-33"><a href="threads.html#cb1480-33"></a></span>
<span id="cb1480-34"><a href="threads.html#cb1480-34"></a><span class="pp">#define THREAD_COUNT 15</span></span>
<span id="cb1480-35"><a href="threads.html#cb1480-35"></a></span>
<span id="cb1480-36"><a href="threads.html#cb1480-36"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1480-37"><a href="threads.html#cb1480-37"></a><span class="op">{</span></span>
<span id="cb1480-38"><a href="threads.html#cb1480-38"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1480-39"><a href="threads.html#cb1480-39"></a></span>
<span id="cb1480-40"><a href="threads.html#cb1480-40"></a>    <span class="co">// Make a new TSS variable, the free() function is the destructor</span></span>
<span id="cb1480-41"><a href="threads.html#cb1480-41"></a>    tss_create<span class="op">(&amp;</span>str<span class="op">,</span> free<span class="op">);</span></span>
<span id="cb1480-42"><a href="threads.html#cb1480-42"></a></span>
<span id="cb1480-43"><a href="threads.html#cb1480-43"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1480-44"><a href="threads.html#cb1480-44"></a>        <span class="dt">int</span> <span class="op">*</span>n <span class="op">=</span> malloc<span class="op">(</span><span class="kw">sizeof</span> <span class="op">*</span>n<span class="op">);</span>  <span class="co">// Holds a thread serial number</span></span>
<span id="cb1480-45"><a href="threads.html#cb1480-45"></a>        <span class="op">*</span>n <span class="op">=</span> i<span class="op">;</span></span>
<span id="cb1480-46"><a href="threads.html#cb1480-46"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> n<span class="op">);</span></span>
<span id="cb1480-47"><a href="threads.html#cb1480-47"></a>    <span class="op">}</span></span>
<span id="cb1480-48"><a href="threads.html#cb1480-48"></a></span>
<span id="cb1480-49"><a href="threads.html#cb1480-49"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1480-50"><a href="threads.html#cb1480-50"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1480-51"><a href="threads.html#cb1480-51"></a>    <span class="op">}</span></span>
<span id="cb1480-52"><a href="threads.html#cb1480-52"></a></span>
<span id="cb1480-53"><a href="threads.html#cb1480-53"></a>    <span class="co">// And all threads are done, so let's free this</span></span>
<span id="cb1480-54"><a href="threads.html#cb1480-54"></a>    tss_delete<span class="op">(</span>str<span class="op">);</span>    <span class="co">// &lt;-- DELETE TSS VARIABLE!</span></span>
<span id="cb1480-55"><a href="threads.html#cb1480-55"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1481"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1481-1"><a href="threads.html#cb1481-1" aria-hidden="true" tabindex="-1"></a>TSS string: thread 0! :)</span>
<span id="cb1481-2"><a href="threads.html#cb1481-2" aria-hidden="true" tabindex="-1"></a>TSS string: thread 2! :)</span>
<span id="cb1481-3"><a href="threads.html#cb1481-3" aria-hidden="true" tabindex="-1"></a>TSS string: thread 1! :)</span>
<span id="cb1481-4"><a href="threads.html#cb1481-4" aria-hidden="true" tabindex="-1"></a>TSS string: thread 5! :)</span>
<span id="cb1481-5"><a href="threads.html#cb1481-5" aria-hidden="true" tabindex="-1"></a>TSS string: thread 3! :)</span>
<span id="cb1481-6"><a href="threads.html#cb1481-6" aria-hidden="true" tabindex="-1"></a>TSS string: thread 6! :)</span>
<span id="cb1481-7"><a href="threads.html#cb1481-7" aria-hidden="true" tabindex="-1"></a>TSS string: thread 4! :)</span>
<span id="cb1481-8"><a href="threads.html#cb1481-8" aria-hidden="true" tabindex="-1"></a>TSS string: thread 7! :)</span>
<span id="cb1481-9"><a href="threads.html#cb1481-9" aria-hidden="true" tabindex="-1"></a>TSS string: thread 8! :)</span>
<span id="cb1481-10"><a href="threads.html#cb1481-10" aria-hidden="true" tabindex="-1"></a>TSS string: thread 9! :)</span>
<span id="cb1481-11"><a href="threads.html#cb1481-11" aria-hidden="true" tabindex="-1"></a>TSS string: thread 10! :)</span>
<span id="cb1481-12"><a href="threads.html#cb1481-12" aria-hidden="true" tabindex="-1"></a>TSS string: thread 13! :)</span>
<span id="cb1481-13"><a href="threads.html#cb1481-13" aria-hidden="true" tabindex="-1"></a>TSS string: thread 12! :)</span>
<span id="cb1481-14"><a href="threads.html#cb1481-14" aria-hidden="true" tabindex="-1"></a>TSS string: thread 11! :)</span>
<span id="cb1481-15"><a href="threads.html#cb1481-15" aria-hidden="true" tabindex="-1"></a>TSS string: thread 14! :)</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-208">See Also</h3>
<p><a href="threads.html#man-tss_create"><code>tss_create()</code></a>, <a href="#man-tss_set"><code>tss_set()</code></a>, <a href="#man-tss_get"><code>tss_get()</code></a>, <a href="#man-thrd_exit"><code>thrd_exit()</code></a></p>
<hr>
<h2 data-number="66.24" id="man-tss_get"><span class="header-section-number">66.24</span> <code>tss_get()</code></h2>
<p>Get thread-specific data</p>
<h3 class="unnumbered unlisted" id="synopsis-221">Synopsis</h3>
<div class="sourceCode" id="cb1482"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1482-1"><a href="threads.html#cb1482-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1482-2"><a href="threads.html#cb1482-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1482-3"><a href="threads.html#cb1482-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> <span class="op">*</span>tss_get<span class="op">(</span>tss_t key<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-221">Description</h3>
<p>Once you’ve set a variable with <code>tss_set()</code>, you can
retrieve the value with <code>tss_get()</code>—just pass in the key and
you’ll get a pointer to the value back.</p>
<p>Don’t call this from a destructor.</p>
<h3 class="unnumbered unlisted" id="return-value-219">Return Value</h3>
<p>Returns the value stored for the given <code>key</code>, or
<code>NULL</code> if there’s trouble.</p>
<h3 class="unnumbered unlisted" id="example-223">Example</h3>
<p>This is a general-purpose TSS example. Note the TSS variable is
retrieved in <code>some_function()</code>, below.</p>
<div class="sourceCode" id="cb1483"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1483-1"><a href="threads.html#cb1483-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1483-2"><a href="threads.html#cb1483-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1483-3"><a href="threads.html#cb1483-3"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1483-4"><a href="threads.html#cb1483-4"></a></span>
<span id="cb1483-5"><a href="threads.html#cb1483-5"></a>tss_t str<span class="op">;</span></span>
<span id="cb1483-6"><a href="threads.html#cb1483-6"></a></span>
<span id="cb1483-7"><a href="threads.html#cb1483-7"></a><span class="dt">void</span> some_function<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1483-8"><a href="threads.html#cb1483-8"></a><span class="op">{</span></span>
<span id="cb1483-9"><a href="threads.html#cb1483-9"></a>    <span class="co">// Retrieve the per-thread value of this string</span></span>
<span id="cb1483-10"><a href="threads.html#cb1483-10"></a>    <span class="dt">char</span> <span class="op">*</span>tss_string <span class="op">=</span> tss_get<span class="op">(</span>str<span class="op">);</span>    <span class="co">// &lt;-- GET THE VALUE</span></span>
<span id="cb1483-11"><a href="threads.html#cb1483-11"></a></span>
<span id="cb1483-12"><a href="threads.html#cb1483-12"></a>    <span class="co">// And print it</span></span>
<span id="cb1483-13"><a href="threads.html#cb1483-13"></a>    printf<span class="op">(</span><span class="st">"TSS string: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tss_string<span class="op">);</span></span>
<span id="cb1483-14"><a href="threads.html#cb1483-14"></a><span class="op">}</span></span>
<span id="cb1483-15"><a href="threads.html#cb1483-15"></a></span>
<span id="cb1483-16"><a href="threads.html#cb1483-16"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1483-17"><a href="threads.html#cb1483-17"></a><span class="op">{</span></span>
<span id="cb1483-18"><a href="threads.html#cb1483-18"></a>    <span class="dt">int</span> serial <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span>  <span class="co">// Get this thread's serial number</span></span>
<span id="cb1483-19"><a href="threads.html#cb1483-19"></a>    free<span class="op">(</span>arg<span class="op">);</span></span>
<span id="cb1483-20"><a href="threads.html#cb1483-20"></a></span>
<span id="cb1483-21"><a href="threads.html#cb1483-21"></a>    <span class="co">// malloc() space to hold the data for this thread</span></span>
<span id="cb1483-22"><a href="threads.html#cb1483-22"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> malloc<span class="op">(</span><span class="dv">64</span><span class="op">);</span></span>
<span id="cb1483-23"><a href="threads.html#cb1483-23"></a>    sprintf<span class="op">(</span>s<span class="op">,</span> <span class="st">"thread %d! :)"</span><span class="op">,</span> serial<span class="op">);</span>  <span class="co">// Happy little string</span></span>
<span id="cb1483-24"><a href="threads.html#cb1483-24"></a></span>
<span id="cb1483-25"><a href="threads.html#cb1483-25"></a>    <span class="co">// Set this TSS variable to point at the string</span></span>
<span id="cb1483-26"><a href="threads.html#cb1483-26"></a>    tss_set<span class="op">(</span>str<span class="op">,</span> s<span class="op">);</span></span>
<span id="cb1483-27"><a href="threads.html#cb1483-27"></a></span>
<span id="cb1483-28"><a href="threads.html#cb1483-28"></a>    <span class="co">// Call a function that will get the variable</span></span>
<span id="cb1483-29"><a href="threads.html#cb1483-29"></a>    some_function<span class="op">();</span></span>
<span id="cb1483-30"><a href="threads.html#cb1483-30"></a></span>
<span id="cb1483-31"><a href="threads.html#cb1483-31"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span> <span class="co">// Equivalent to thrd_exit(0); fires destructors</span></span>
<span id="cb1483-32"><a href="threads.html#cb1483-32"></a><span class="op">}</span></span>
<span id="cb1483-33"><a href="threads.html#cb1483-33"></a></span>
<span id="cb1483-34"><a href="threads.html#cb1483-34"></a><span class="pp">#define THREAD_COUNT 15</span></span>
<span id="cb1483-35"><a href="threads.html#cb1483-35"></a></span>
<span id="cb1483-36"><a href="threads.html#cb1483-36"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1483-37"><a href="threads.html#cb1483-37"></a><span class="op">{</span></span>
<span id="cb1483-38"><a href="threads.html#cb1483-38"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1483-39"><a href="threads.html#cb1483-39"></a></span>
<span id="cb1483-40"><a href="threads.html#cb1483-40"></a>    <span class="co">// Make a new TSS variable, the free() function is the destructor</span></span>
<span id="cb1483-41"><a href="threads.html#cb1483-41"></a>    tss_create<span class="op">(&amp;</span>str<span class="op">,</span> free<span class="op">);</span></span>
<span id="cb1483-42"><a href="threads.html#cb1483-42"></a></span>
<span id="cb1483-43"><a href="threads.html#cb1483-43"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1483-44"><a href="threads.html#cb1483-44"></a>        <span class="dt">int</span> <span class="op">*</span>n <span class="op">=</span> malloc<span class="op">(</span><span class="kw">sizeof</span> <span class="op">*</span>n<span class="op">);</span>  <span class="co">// Holds a thread serial number</span></span>
<span id="cb1483-45"><a href="threads.html#cb1483-45"></a>        <span class="op">*</span>n <span class="op">=</span> i<span class="op">;</span></span>
<span id="cb1483-46"><a href="threads.html#cb1483-46"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> n<span class="op">);</span></span>
<span id="cb1483-47"><a href="threads.html#cb1483-47"></a>    <span class="op">}</span></span>
<span id="cb1483-48"><a href="threads.html#cb1483-48"></a></span>
<span id="cb1483-49"><a href="threads.html#cb1483-49"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1483-50"><a href="threads.html#cb1483-50"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1483-51"><a href="threads.html#cb1483-51"></a>    <span class="op">}</span></span>
<span id="cb1483-52"><a href="threads.html#cb1483-52"></a></span>
<span id="cb1483-53"><a href="threads.html#cb1483-53"></a>    <span class="co">// And all threads are done, so let's free this</span></span>
<span id="cb1483-54"><a href="threads.html#cb1483-54"></a>    tss_delete<span class="op">(</span>str<span class="op">);</span></span>
<span id="cb1483-55"><a href="threads.html#cb1483-55"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1484"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1484-1"><a href="threads.html#cb1484-1" aria-hidden="true" tabindex="-1"></a>TSS string: thread 0! :)</span>
<span id="cb1484-2"><a href="threads.html#cb1484-2" aria-hidden="true" tabindex="-1"></a>TSS string: thread 2! :)</span>
<span id="cb1484-3"><a href="threads.html#cb1484-3" aria-hidden="true" tabindex="-1"></a>TSS string: thread 1! :)</span>
<span id="cb1484-4"><a href="threads.html#cb1484-4" aria-hidden="true" tabindex="-1"></a>TSS string: thread 5! :)</span>
<span id="cb1484-5"><a href="threads.html#cb1484-5" aria-hidden="true" tabindex="-1"></a>TSS string: thread 3! :)</span>
<span id="cb1484-6"><a href="threads.html#cb1484-6" aria-hidden="true" tabindex="-1"></a>TSS string: thread 6! :)</span>
<span id="cb1484-7"><a href="threads.html#cb1484-7" aria-hidden="true" tabindex="-1"></a>TSS string: thread 4! :)</span>
<span id="cb1484-8"><a href="threads.html#cb1484-8" aria-hidden="true" tabindex="-1"></a>TSS string: thread 7! :)</span>
<span id="cb1484-9"><a href="threads.html#cb1484-9" aria-hidden="true" tabindex="-1"></a>TSS string: thread 8! :)</span>
<span id="cb1484-10"><a href="threads.html#cb1484-10" aria-hidden="true" tabindex="-1"></a>TSS string: thread 9! :)</span>
<span id="cb1484-11"><a href="threads.html#cb1484-11" aria-hidden="true" tabindex="-1"></a>TSS string: thread 10! :)</span>
<span id="cb1484-12"><a href="threads.html#cb1484-12" aria-hidden="true" tabindex="-1"></a>TSS string: thread 13! :)</span>
<span id="cb1484-13"><a href="threads.html#cb1484-13" aria-hidden="true" tabindex="-1"></a>TSS string: thread 12! :)</span>
<span id="cb1484-14"><a href="threads.html#cb1484-14" aria-hidden="true" tabindex="-1"></a>TSS string: thread 11! :)</span>
<span id="cb1484-15"><a href="threads.html#cb1484-15" aria-hidden="true" tabindex="-1"></a>TSS string: thread 14! :)</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-209">See Also</h3>
<p><a href="threads.html#man-tss_set"><code>tss_set()</code></a></p>
<hr>
<h2 data-number="66.25" id="man-tss_set"><span class="header-section-number">66.25</span> <code>tss_set()</code></h2>
<p>Set thread-specific data</p>
<h3 class="unnumbered unlisted" id="synopsis-222">Synopsis</h3>
<div class="sourceCode" id="cb1485"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1485-1"><a href="threads.html#cb1485-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1485-2"><a href="threads.html#cb1485-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1485-3"><a href="threads.html#cb1485-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> tss_set<span class="op">(</span>tss_t key<span class="op">,</span> <span class="dt">void</span> <span class="op">*</span>val<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-222">Description</h3>
<p>Once you’ve set up your TSS variable with <code>tss_create()</code>,
you can set it on a per thread basis with <code>tss_set()</code>.</p>
<p><code>key</code> is the identifier for this data, and
<code>val</code> is a pointer to it.</p>
<p>The destructor specified in <code>tss_create()</code> will be called
for the value set when the thread exits.</p>
<p>Also, if there’s a destructor <em>and</em> there is already at value
for this key in place, the destructor will not be called for the
already-existing value. In fact, this function will never cause a
destructor to be called. So you’re on your own, there—best clean up the
old value before overwriting it with the new one.</p>
<h3 class="unnumbered unlisted" id="return-value-220">Return Value</h3>
<p>Returns <code>thrd_success</code> when happy, and
<code>thrd_error</code> when not.</p>
<h3 class="unnumbered unlisted" id="example-224">Example</h3>
<p>This is a general-purpose TSS example. Note the TSS variable is set
in <code>run()</code>, below.</p>
<div class="sourceCode" id="cb1486"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1486-1"><a href="threads.html#cb1486-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1486-2"><a href="threads.html#cb1486-2"></a><span class="pp">#include </span><span class="im">&lt;stdlib.h&gt;</span></span>
<span id="cb1486-3"><a href="threads.html#cb1486-3"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1486-4"><a href="threads.html#cb1486-4"></a></span>
<span id="cb1486-5"><a href="threads.html#cb1486-5"></a>tss_t str<span class="op">;</span></span>
<span id="cb1486-6"><a href="threads.html#cb1486-6"></a></span>
<span id="cb1486-7"><a href="threads.html#cb1486-7"></a><span class="dt">void</span> some_function<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1486-8"><a href="threads.html#cb1486-8"></a><span class="op">{</span></span>
<span id="cb1486-9"><a href="threads.html#cb1486-9"></a>    <span class="co">// Retrieve the per-thread value of this string</span></span>
<span id="cb1486-10"><a href="threads.html#cb1486-10"></a>    <span class="dt">char</span> <span class="op">*</span>tss_string <span class="op">=</span> tss_get<span class="op">(</span>str<span class="op">);</span></span>
<span id="cb1486-11"><a href="threads.html#cb1486-11"></a></span>
<span id="cb1486-12"><a href="threads.html#cb1486-12"></a>    <span class="co">// And print it</span></span>
<span id="cb1486-13"><a href="threads.html#cb1486-13"></a>    printf<span class="op">(</span><span class="st">"TSS string: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tss_string<span class="op">);</span></span>
<span id="cb1486-14"><a href="threads.html#cb1486-14"></a><span class="op">}</span></span>
<span id="cb1486-15"><a href="threads.html#cb1486-15"></a></span>
<span id="cb1486-16"><a href="threads.html#cb1486-16"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1486-17"><a href="threads.html#cb1486-17"></a><span class="op">{</span></span>
<span id="cb1486-18"><a href="threads.html#cb1486-18"></a>    <span class="dt">int</span> serial <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span>  <span class="co">// Get this thread's serial number</span></span>
<span id="cb1486-19"><a href="threads.html#cb1486-19"></a>    free<span class="op">(</span>arg<span class="op">);</span></span>
<span id="cb1486-20"><a href="threads.html#cb1486-20"></a></span>
<span id="cb1486-21"><a href="threads.html#cb1486-21"></a>    <span class="co">// malloc() space to hold the data for this thread</span></span>
<span id="cb1486-22"><a href="threads.html#cb1486-22"></a>    <span class="dt">char</span> <span class="op">*</span>s <span class="op">=</span> malloc<span class="op">(</span><span class="dv">64</span><span class="op">);</span></span>
<span id="cb1486-23"><a href="threads.html#cb1486-23"></a>    sprintf<span class="op">(</span>s<span class="op">,</span> <span class="st">"thread %d! :)"</span><span class="op">,</span> serial<span class="op">);</span>  <span class="co">// Happy little string</span></span>
<span id="cb1486-24"><a href="threads.html#cb1486-24"></a></span>
<span id="cb1486-25"><a href="threads.html#cb1486-25"></a>    <span class="co">// Set this TSS variable to point at the string</span></span>
<span id="cb1486-26"><a href="threads.html#cb1486-26"></a>    tss_set<span class="op">(</span>str<span class="op">,</span> s<span class="op">);</span>    <span class="co">// &lt;-- SET THE TSS VARIABLE</span></span>
<span id="cb1486-27"><a href="threads.html#cb1486-27"></a></span>
<span id="cb1486-28"><a href="threads.html#cb1486-28"></a>    <span class="co">// Call a function that will get the variable</span></span>
<span id="cb1486-29"><a href="threads.html#cb1486-29"></a>    some_function<span class="op">();</span></span>
<span id="cb1486-30"><a href="threads.html#cb1486-30"></a></span>
<span id="cb1486-31"><a href="threads.html#cb1486-31"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span> <span class="co">// Equivalent to thrd_exit(0); fires destructors</span></span>
<span id="cb1486-32"><a href="threads.html#cb1486-32"></a><span class="op">}</span></span>
<span id="cb1486-33"><a href="threads.html#cb1486-33"></a></span>
<span id="cb1486-34"><a href="threads.html#cb1486-34"></a><span class="pp">#define THREAD_COUNT 15</span></span>
<span id="cb1486-35"><a href="threads.html#cb1486-35"></a></span>
<span id="cb1486-36"><a href="threads.html#cb1486-36"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1486-37"><a href="threads.html#cb1486-37"></a><span class="op">{</span></span>
<span id="cb1486-38"><a href="threads.html#cb1486-38"></a>    thrd_t t<span class="op">[</span>THREAD_COUNT<span class="op">];</span></span>
<span id="cb1486-39"><a href="threads.html#cb1486-39"></a></span>
<span id="cb1486-40"><a href="threads.html#cb1486-40"></a>    <span class="co">// Make a new TSS variable, the free() function is the destructor</span></span>
<span id="cb1486-41"><a href="threads.html#cb1486-41"></a>    tss_create<span class="op">(&amp;</span>str<span class="op">,</span> free<span class="op">);</span></span>
<span id="cb1486-42"><a href="threads.html#cb1486-42"></a></span>
<span id="cb1486-43"><a href="threads.html#cb1486-43"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1486-44"><a href="threads.html#cb1486-44"></a>        <span class="dt">int</span> <span class="op">*</span>n <span class="op">=</span> malloc<span class="op">(</span><span class="kw">sizeof</span> <span class="op">*</span>n<span class="op">);</span>  <span class="co">// Holds a thread serial number</span></span>
<span id="cb1486-45"><a href="threads.html#cb1486-45"></a>        <span class="op">*</span>n <span class="op">=</span> i<span class="op">;</span></span>
<span id="cb1486-46"><a href="threads.html#cb1486-46"></a>        thrd_create<span class="op">(</span>t <span class="op">+</span> i<span class="op">,</span> run<span class="op">,</span> n<span class="op">);</span></span>
<span id="cb1486-47"><a href="threads.html#cb1486-47"></a>    <span class="op">}</span></span>
<span id="cb1486-48"><a href="threads.html#cb1486-48"></a></span>
<span id="cb1486-49"><a href="threads.html#cb1486-49"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> THREAD_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1486-50"><a href="threads.html#cb1486-50"></a>        thrd_join<span class="op">(</span>t<span class="op">[</span>i<span class="op">],</span> NULL<span class="op">);</span></span>
<span id="cb1486-51"><a href="threads.html#cb1486-51"></a>    <span class="op">}</span></span>
<span id="cb1486-52"><a href="threads.html#cb1486-52"></a></span>
<span id="cb1486-53"><a href="threads.html#cb1486-53"></a>    <span class="co">// And all threads are done, so let's free this</span></span>
<span id="cb1486-54"><a href="threads.html#cb1486-54"></a>    tss_delete<span class="op">(</span>str<span class="op">);</span></span>
<span id="cb1486-55"><a href="threads.html#cb1486-55"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1487"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1487-1"><a href="threads.html#cb1487-1" aria-hidden="true" tabindex="-1"></a>TSS string: thread 0! :)</span>
<span id="cb1487-2"><a href="threads.html#cb1487-2" aria-hidden="true" tabindex="-1"></a>TSS string: thread 2! :)</span>
<span id="cb1487-3"><a href="threads.html#cb1487-3" aria-hidden="true" tabindex="-1"></a>TSS string: thread 1! :)</span>
<span id="cb1487-4"><a href="threads.html#cb1487-4" aria-hidden="true" tabindex="-1"></a>TSS string: thread 5! :)</span>
<span id="cb1487-5"><a href="threads.html#cb1487-5" aria-hidden="true" tabindex="-1"></a>TSS string: thread 3! :)</span>
<span id="cb1487-6"><a href="threads.html#cb1487-6" aria-hidden="true" tabindex="-1"></a>TSS string: thread 6! :)</span>
<span id="cb1487-7"><a href="threads.html#cb1487-7" aria-hidden="true" tabindex="-1"></a>TSS string: thread 4! :)</span>
<span id="cb1487-8"><a href="threads.html#cb1487-8" aria-hidden="true" tabindex="-1"></a>TSS string: thread 7! :)</span>
<span id="cb1487-9"><a href="threads.html#cb1487-9" aria-hidden="true" tabindex="-1"></a>TSS string: thread 8! :)</span>
<span id="cb1487-10"><a href="threads.html#cb1487-10" aria-hidden="true" tabindex="-1"></a>TSS string: thread 9! :)</span>
<span id="cb1487-11"><a href="threads.html#cb1487-11" aria-hidden="true" tabindex="-1"></a>TSS string: thread 10! :)</span>
<span id="cb1487-12"><a href="threads.html#cb1487-12" aria-hidden="true" tabindex="-1"></a>TSS string: thread 13! :)</span>
<span id="cb1487-13"><a href="threads.html#cb1487-13" aria-hidden="true" tabindex="-1"></a>TSS string: thread 12! :)</span>
<span id="cb1487-14"><a href="threads.html#cb1487-14" aria-hidden="true" tabindex="-1"></a>TSS string: thread 11! :)</span>
<span id="cb1487-15"><a href="threads.html#cb1487-15" aria-hidden="true" tabindex="-1"></a>TSS string: thread 14! :)</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-210">See Also</h3>
<p><a href="threads.html#man-tss_get"><code>tss_get()</code></a></p>

</body>