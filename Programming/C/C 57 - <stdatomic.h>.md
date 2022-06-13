<body>

<hr>
<h1 data-number="57" id="stdatomic"><span class="header-section-number">57</span> <code>&lt;stdatomic.h&gt;</code>
Atomic-Related Functions</h1>
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
<td><a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong_explicit()</code></a></td>
<td>Atomic compare and exchange, strong, explicit</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong()</code></a></td>
<td>Atomic compare and exchange, strong</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak_explicit()</code></a></td>
<td>Atomic compare and exchange, weak, explicit</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak()</code></a></td>
<td>Atomic compare and exchange, weak</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_exchange"><code>atomic_exchange_explicit()</code></a></td>
<td>Replace a value in an atomic object, explicit</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_exchange"><code>atomic_exchange()</code></a></td>
<td>Replace a value in an atomic object</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_fetch"><code>atomic_fetch_add_explicit()</code></a></td>
<td>Atomically add to an atomic integer, explicit</td>
</tr>
<tr class="even">
<td><a href="stdatomic.html#man-atomic_fetch"><code>atomic_fetch_add()</code></a></td>
<td>Atomically add to an atomic integer</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_fetch"><code>atomic_fetch_and_explicit()</code></a></td>
<td>Atomically bitwise-AND an atomic integer, explicit</td>
</tr>
<tr class="even">
<td><a href="stdatomic.html#man-atomic_fetch"><code>atomic_fetch_and()</code></a></td>
<td>Atomically bitwise-AND an atomic integer</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_fetch"><code>atomic_fetch_or_explicit()</code></a></td>
<td>Atomically bitwise-OR an atomic integer, explicit</td>
</tr>
<tr class="even">
<td><a href="stdatomic.html#man-atomic_fetch"><code>atomic_fetch_or()</code></a></td>
<td>Atomically bitwise-OR an atomic integer</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_fetch"><code>atomic_fetch_sub_explicit()</code></a></td>
<td>Atomically subtract from an atomic integer, explicit</td>
</tr>
<tr class="even">
<td><a href="stdatomic.html#man-atomic_fetch"><code>atomic_fetch_sub()</code></a></td>
<td>Atomically subtract from an atomic integer</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_fetch"><code>atomic_fetch_xor_explicit()</code></a></td>
<td>Atomically bitwise-XOR an atomic integer, explicit</td>
</tr>
<tr class="even">
<td><a href="stdatomic.html#man-atomic_fetch"><code>atomic_fetch_xor()</code></a></td>
<td>Atomically bitwise-XOR an atomic integer</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_flag_clear"><code>atomic_flag_clear_explicit()</code></a></td>
<td>Clear an atomic flag, explicit</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_flag_clear"><code>atomic_flag_clear()</code></a></td>
<td>Clear an atomic flag</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_flag_test_and_set"><code>atomic_flag_test_and_set_explicit()</code></a></td>
<td>Test and set an atomic flag, explicit</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_flag_test_and_set"><code>atomic_flag_test_and_set()</code></a></td>
<td>Test and set an atomic flag</td>
</tr>
<tr class="odd">
<td><a href="stdatomic.html#man-atomic_init"><code>atomic_init()</code></a></td>
<td>Initialize an atomic variable</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_is_lock_free"><code>atomic_is_lock_free()</code></a></td>
<td>Determine if an atomic type is lock free</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_load"><code>atomic_load_explicit()</code></a></td>
<td>Return a value from an atomic variable, explicit</td>
</tr>
<tr class="even">
<td><a href="stdatomic.html#man-atomic_load"><code>atomic_load()</code></a></td>
<td>Return a value from an atomic variable</td>
</tr>
<tr class="odd">
<td><a href="#man-atomic_signal_fence"><code>atomic_signal_fence()</code></a></td>
<td>Fence for intra-thread signal handlers</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_store"><code>atomic_store_explicit()</code></a></td>
<td>Store a value in an atomic variable, explicit</td>
</tr>
<tr class="odd">
<td><a href="stdatomic.html#man-atomic_store"><code>atomic_store()</code></a></td>
<td>Store a value in an atomic variable</td>
</tr>
<tr class="even">
<td><a href="#man-atomic_thread_fence"><code>atomic_thread_fence()</code></a></td>
<td>Set up a fence</td>
</tr>
<tr class="odd">
<td><a href="#man-ATOMIC_VAR_INIT"><code>ATOMIC_VAR_INIT()</code></a></td>
<td>Create an initializer for an atomic variable</td>
</tr>
<tr class="even">
<td><a href="#man-kill_dependency"><code>kill_dependency()</code></a></td>
<td>End a dependency chain</td>
</tr>
</tbody>
</table>
<p>You might need to add <code>-latomic</code> to your compilation
command line on Unix-like operating systems.</p>
<h2 data-number="57.1" id="atomic-types"><span class="header-section-number">57.1</span> Atomic Types</h2>
<p>A bunch of types are predefined by this header:</p>
<table>
<thead>
<tr class="header">
<th>Atomic type</th>
<th>Longhand equivalent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>atomic_bool</code></td>
<td><code>_Atomic _Bool</code></td>
</tr>
<tr class="even">
<td><code>atomic_char</code></td>
<td><code>_Atomic char</code></td>
</tr>
<tr class="odd">
<td><code>atomic_schar</code></td>
<td><code>_Atomic signed char</code></td>
</tr>
<tr class="even">
<td><code>atomic_uchar</code></td>
<td><code>_Atomic unsigned char</code></td>
</tr>
<tr class="odd">
<td><code>atomic_short</code></td>
<td><code>_Atomic short</code></td>
</tr>
<tr class="even">
<td><code>atomic_ushort</code></td>
<td><code>_Atomic unsigned short</code></td>
</tr>
<tr class="odd">
<td><code>atomic_int</code></td>
<td><code>_Atomic int</code></td>
</tr>
<tr class="even">
<td><code>atomic_uint</code></td>
<td><code>_Atomic unsigned int</code></td>
</tr>
<tr class="odd">
<td><code>atomic_long</code></td>
<td><code>_Atomic long</code></td>
</tr>
<tr class="even">
<td><code>atomic_ulong</code></td>
<td><code>_Atomic unsigned long</code></td>
</tr>
<tr class="odd">
<td><code>atomic_llong</code></td>
<td><code>_Atomic long long</code></td>
</tr>
<tr class="even">
<td><code>atomic_ullong</code></td>
<td><code>_Atomic unsigned long long</code></td>
</tr>
<tr class="odd">
<td><code>atomic_char16_t</code></td>
<td><code>_Atomic char16_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_char32_t</code></td>
<td><code>_Atomic char32_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_wchar_t</code></td>
<td><code>_Atomic wchar_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_least8_t</code></td>
<td><code>_Atomic int_least8_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_least8_t</code></td>
<td><code>_Atomic uint_least8_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_least16_t</code></td>
<td><code>_Atomic int_least16_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_least16_t</code></td>
<td><code>_Atomic uint_least16_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_least32_t</code></td>
<td><code>_Atomic int_least32_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_least32_t</code></td>
<td><code>_Atomic uint_least32_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_least64_t</code></td>
<td><code>_Atomic int_least64_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_least64_t</code></td>
<td><code>_Atomic uint_least64_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_fast8_t</code></td>
<td><code>_Atomic int_fast8_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_fast8_t</code></td>
<td><code>_Atomic uint_fast8_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_fast16_t</code></td>
<td><code>_Atomic int_fast16_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_fast16_t</code></td>
<td><code>_Atomic uint_fast16_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_fast32_t</code></td>
<td><code>_Atomic int_fast32_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_fast32_t</code></td>
<td><code>_Atomic uint_fast32_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_int_fast64_t</code></td>
<td><code>_Atomic int_fast64_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uint_fast64_t</code></td>
<td><code>_Atomic uint_fast64_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_intptr_t</code></td>
<td><code>_Atomic intptr_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uintptr_t</code></td>
<td><code>_Atomic uintptr_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_size_t</code></td>
<td><code>_Atomic size_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_ptrdiff_t</code></td>
<td><code>_Atomic ptrdiff_t</code></td>
</tr>
<tr class="even">
<td><code>atomic_intmax_t</code></td>
<td><code>_Atomic intmax_t</code></td>
</tr>
<tr class="odd">
<td><code>atomic_uintmax_t</code></td>
<td><code>_Atomic uintmax_t</code></td>
</tr>
</tbody>
</table>
<p>You can make your own additional types with the <code>_Atomic</code>
type qualifier:</p>
<div class="sourceCode" id="cb1161"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1161-1"><a href="stdatomic.html#cb1161-1" aria-hidden="true" tabindex="-1"></a><span class="kw">_Atomic</span> <span class="dt">double</span> x<span class="op">;</span></span></code></pre></div>
<p>or the <code>_Atomic()</code> type specifier:</p>
<div class="sourceCode" id="cb1162"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1162-1"><a href="stdatomic.html#cb1162-1" aria-hidden="true" tabindex="-1"></a><span class="kw">_Atomic</span><span class="op">(</span><span class="dt">double</span><span class="op">)</span> x<span class="op">;</span></span></code></pre></div>
<h2 data-number="57.2" id="lock-free-macros"><span class="header-section-number">57.2</span> Lock-free Macros</h2>
<p>These macros let you know if a type is lock-free or not. Maybe.</p>
<p>They can be used at compile time with <code>#if</code>. They apply to
both signed and unsigned types.</p>
<table>
<thead>
<tr class="header">
<th>Atomic Type</th>
<th>Lock Free Macro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>atomic_bool</code></td>
<td><code>ATOMIC_BOOL_LOCK_FREE</code></td>
</tr>
<tr class="even">
<td><code>atomic_char</code></td>
<td><code>ATOMIC_CHAR_LOCK_FREE</code></td>
</tr>
<tr class="odd">
<td><code>atomic_char16_t</code></td>
<td><code>ATOMIC_CHAR16_T_LOCK_FREE</code></td>
</tr>
<tr class="even">
<td><code>atomic_char32_t</code></td>
<td><code>ATOMIC_CHAR32_T_LOCK_FREE</code></td>
</tr>
<tr class="odd">
<td><code>atomic_wchar_t</code></td>
<td><code>ATOMIC_WCHAR_T_LOCK_FREE</code></td>
</tr>
<tr class="even">
<td><code>atomic_short</code></td>
<td><code>ATOMIC_SHORT_LOCK_FREE</code></td>
</tr>
<tr class="odd">
<td><code>atomic_int</code></td>
<td><code>ATOMIC_INT_LOCK_FREE</code></td>
</tr>
<tr class="even">
<td><code>atomic_long</code></td>
<td><code>ATOMIC_LONG_LOCK_FREE</code></td>
</tr>
<tr class="odd">
<td><code>atomic_llong</code></td>
<td><code>ATOMIC_LLONG_LOCK_FREE</code></td>
</tr>
<tr class="even">
<td><code>atomic_intptr_t</code></td>
<td><code>ATOMIC_POINTER_LOCK_FREE</code></td>
</tr>
</tbody>
</table>
<p>These macros can interestingly have <em>three</em> different
values:</p>
<table>
<thead>
<tr class="header">
<th>Value</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>0</code></td>
<td>Never lock-free.</td>
</tr>
<tr class="even">
<td><code>1</code></td>
<td><em>Sometimes</em> lock-free<a href="footnotes.html#fn245" class="footnote-ref" id="fnref245" role="doc-noteref"><sup>245</sup></a>.</td>
</tr>
<tr class="odd">
<td><code>2</code></td>
<td>Always lock-free.</td>
</tr>
</tbody>
</table>
<h2 data-number="57.3" id="atomic-flag"><span class="header-section-number">57.3</span> Atomic Flag</h2>
<p>The <code>atomic_flag</code> opaque type is the only time guaranteed
to be lock-free. Though your PC implementation probably does a lot
more.</p>
<p>It is accessed through the <a href="#man-atomic_flag_test_and_set"><code>atomic_flag_test_and_set()</code></a>
and <a href="#man-atomic_flag_clear"><code>atomic_flag_clear()</code></a>
functions.</p>
<p>Before use, it can be initialized to a clear state with:</p>
<div class="sourceCode" id="cb1163"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1163-1"><a href="stdatomic.html#cb1163-1" aria-hidden="true" tabindex="-1"></a>atomic_flag f <span class="op">=</span> ATOMIC_FLAG_INIT<span class="op">;</span></span></code></pre></div>
<h2 data-number="57.4" id="memory-order-1"><span class="header-section-number">57.4</span> Memory Order</h2>
<p>This header introduces a new <code>enum</code> type called
<code>memory_order</code>. This is used by a bunch of the functions to
specify memory orders other than sequential consistency.</p>
<table>
<thead>
<tr class="header">
<th><code>memory_order</code></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>memory_order_seq_cst</code></td>
<td>Sequential Consistency</td>
</tr>
<tr class="even">
<td><code>memory_order_acq_rel</code></td>
<td>Acquire/Release</td>
</tr>
<tr class="odd">
<td><code>memory_order_release</code></td>
<td>Release</td>
</tr>
<tr class="even">
<td><code>memory_order_acquire</code></td>
<td>Acquire</td>
</tr>
<tr class="odd">
<td><code>memory_order_consume</code></td>
<td>Consume</td>
</tr>
<tr class="even">
<td><code>memory_order_relaxed</code></td>
<td>Relaxed</td>
</tr>
</tbody>
</table>
<p>You can feed these into atomic functions with the
<code>_explicit</code> suffix.</p>
<p>The non-<code>_explcit</code> versions of the functions are the same
as if you’d called the <code>_explicit</code> counterpart with
<code>memory_order_seq_cst</code>.</p>
<hr>
<h2 data-number="57.5" id="man-ATOMIC_VAR_INIT"><span class="header-section-number">57.5</span>
<code>ATOMIC_VAR_INIT()</code></h2>
<p>Create an initializer for an atomic variable</p>
<h3 class="unnumbered unlisted" id="synopsis-122">Synopsis</h3>
<div class="sourceCode" id="cb1164"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1164-1"><a href="stdatomic.html#cb1164-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1164-2"><a href="stdatomic.html#cb1164-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1164-3"><a href="stdatomic.html#cb1164-3" aria-hidden="true" tabindex="-1"></a><span class="pp">#define ATOMIC_VAR_INIT(C value)   </span><span class="co">// Deprecated</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-122">Description</h3>
<p>This macro expands to an initializer, so you can use it when a
variable is defined.</p>
<p>The type of the <code>value</code> should be the base type of the
atomic variable.</p>
<p>The initialization itself is <em>not</em> an atomic operation,
ironically.</p>
<p><a href="https://en.cppreference.com/w/cpp/atomic/ATOMIC_VAR_INIT">CPPReference
says this is deprecated</a><a href="footnotes.html#fn246" class="footnote-ref" id="fnref246" role="doc-noteref"><sup>246</sup></a> and likely to be
removed. Standards document <a href="http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1138r0.pdf">p1138r0</a><a href="#fn247" class="footnote-ref" id="fnref247" role="doc-noteref"><sup>247</sup></a> elaborates that the macro is
limited in that it can’t properly initialize atomic
<code>struct</code>s, and its original <em>raison d’être</em> turned out
to not be useful.</p>
<p>Just initialize the variable straight-up, instead.</p>
<h3 class="unnumbered unlisted" id="return-value-120">Return Value</h3>
<p>Expands to an initializer suitable for this atomic variable.</p>
<h3 class="unnumbered unlisted" id="example-122">Example</h3>
<div class="sourceCode" id="cb1165"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1165-1"><a href="stdatomic.html#cb1165-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1165-2"><a href="stdatomic.html#cb1165-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1165-3"><a href="stdatomic.html#cb1165-3"></a></span>
<span id="cb1165-4"><a href="stdatomic.html#cb1165-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1165-5"><a href="stdatomic.html#cb1165-5"></a><span class="op">{</span></span>
<span id="cb1165-6"><a href="stdatomic.html#cb1165-6"></a>    atomic_int x <span class="op">=</span> ATOMIC_VAR_INIT<span class="op">(</span><span class="dv">3490</span><span class="op">);</span>  <span class="co">// Deprecated</span></span>
<span id="cb1165-7"><a href="stdatomic.html#cb1165-7"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb1165-8"><a href="stdatomic.html#cb1165-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-115">See Also</h3>
<p><a href="stdatomic.html#man-atomic_init"><code>atomic_init()</code></a></p>
<hr>
<h2 data-number="57.6" id="man-atomic_init"><span class="header-section-number">57.6</span>
<code>atomic_init()</code></h2>
<p>Initialize an atomic variable</p>
<h3 class="unnumbered unlisted" id="synopsis-123">Synopsis</h3>
<div class="sourceCode" id="cb1166"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1166-1"><a href="stdatomic.html#cb1166-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1166-2"><a href="stdatomic.html#cb1166-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1166-3"><a href="stdatomic.html#cb1166-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> atomic_init<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>obj<span class="op">,</span> C value<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-123">Description</h3>
<p>You can use this to initialize an atomic variable.</p>
<p>The type of the <code>value</code> should be the base type of the
atomic variable.</p>
<p>The initialization itself is <em>not</em> an atomic operation,
ironically.</p>
<p>As far as I can tell, there’s no difference between this and
assigning directly to the atomic variable. The spec says it’s there to
allow the compiler to inject any additional initialization that needs
doing, but everything seems fine without it. If anyone has more info,
send it my way.</p>
<h3 class="unnumbered unlisted" id="return-value-121">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-123">Example</h3>
<div class="sourceCode" id="cb1167"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1167-1"><a href="stdatomic.html#cb1167-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1167-2"><a href="stdatomic.html#cb1167-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1167-3"><a href="stdatomic.html#cb1167-3"></a></span>
<span id="cb1167-4"><a href="stdatomic.html#cb1167-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1167-5"><a href="stdatomic.html#cb1167-5"></a><span class="op">{</span></span>
<span id="cb1167-6"><a href="stdatomic.html#cb1167-6"></a>    atomic_int x<span class="op">;</span></span>
<span id="cb1167-7"><a href="stdatomic.html#cb1167-7"></a>    </span>
<span id="cb1167-8"><a href="stdatomic.html#cb1167-8"></a>    atomic_init<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">3490</span><span class="op">);</span></span>
<span id="cb1167-9"><a href="stdatomic.html#cb1167-9"></a></span>
<span id="cb1167-10"><a href="stdatomic.html#cb1167-10"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb1167-11"><a href="stdatomic.html#cb1167-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-116">See Also</h3>
<p><a href="stdatomic.html#man-ATOMIC_VAR_INIT"><code>ATOMIC_VAR_INIT()</code></a>, <a href="#man-atomic_store"><code>atomic_store()</code></a>, <a href="#man-atomic_store"><code>atomic_store_explicit()</code></a></p>
<hr>
<h2 data-number="57.7" id="man-kill_dependency"><span class="header-section-number">57.7</span>
<code>kill_dependency()</code></h2>
<p>End a dependency chain</p>
<h3 class="unnumbered unlisted" id="synopsis-124">Synopsis</h3>
<div class="sourceCode" id="cb1168"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1168-1"><a href="stdatomic.html#cb1168-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1168-2"><a href="stdatomic.html#cb1168-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1168-3"><a href="stdatomic.html#cb1168-3" aria-hidden="true" tabindex="-1"></a>type kill_dependency<span class="op">(</span>type y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-124">Description</h3>
<p>This is potentially useful for optimizing if you’re using
<code>memory_order_consume</code> anywhere.</p>
<p>And if you know what you’re doing. If unsure, learn more before
trying to use this.</p>
<h3 class="unnumbered unlisted" id="return-value-122">Return Value</h3>
<p>Returns the value passed in.</p>
<h3 class="unnumbered unlisted" id="example-124">Example</h3>
<p>In this example, <code>i</code> carries a dependency into
<code>x</code>. And would do into <code>y</code>, except for the call to
<code>kill_dependency()</code>.</p>
<div class="sourceCode" id="cb1169"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1169-1"><a href="stdatomic.html#cb1169-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1169-2"><a href="stdatomic.html#cb1169-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1169-3"><a href="stdatomic.html#cb1169-3"></a></span>
<span id="cb1169-4"><a href="stdatomic.html#cb1169-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1169-5"><a href="stdatomic.html#cb1169-5"></a><span class="op">{</span></span>
<span id="cb1169-6"><a href="stdatomic.html#cb1169-6"></a>    atomic_int a<span class="op">;</span></span>
<span id="cb1169-7"><a href="stdatomic.html#cb1169-7"></a>    <span class="dt">int</span> i <span class="op">=</span> <span class="dv">10</span><span class="op">,</span> x<span class="op">,</span> y<span class="op">;</span></span>
<span id="cb1169-8"><a href="stdatomic.html#cb1169-8"></a></span>
<span id="cb1169-9"><a href="stdatomic.html#cb1169-9"></a>    atomic_store_explicit<span class="op">(&amp;</span>a<span class="op">,</span> <span class="dv">3490</span><span class="op">,</span> memory_order_release<span class="op">);</span></span>
<span id="cb1169-10"><a href="stdatomic.html#cb1169-10"></a></span>
<span id="cb1169-11"><a href="stdatomic.html#cb1169-11"></a>    i <span class="op">=</span> atomic_load_explicit<span class="op">(&amp;</span>a<span class="op">,</span> memory_order_consume<span class="op">);</span></span>
<span id="cb1169-12"><a href="stdatomic.html#cb1169-12"></a>    x <span class="op">=</span> i<span class="op">;</span></span>
<span id="cb1169-13"><a href="stdatomic.html#cb1169-13"></a>    y <span class="op">=</span> kill_dependency<span class="op">(</span>i<span class="op">);</span></span>
<span id="cb1169-14"><a href="stdatomic.html#cb1169-14"></a></span>
<span id="cb1169-15"><a href="stdatomic.html#cb1169-15"></a>    printf<span class="op">(</span><span class="st">"%d %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">,</span> y<span class="op">);</span>  <span class="co">// 3490 and either 3490 or 10</span></span>
<span id="cb1169-16"><a href="stdatomic.html#cb1169-16"></a><span class="op">}</span></span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="57.8" id="man-atomic_thread_fence"><span class="header-section-number">57.8</span>
<code>atomic_thread_fence()</code></h2>
<p>Set up a fence</p>
<h3 class="unnumbered unlisted" id="synopsis-125">Synopsis</h3>
<div class="sourceCode" id="cb1170"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1170-1"><a href="stdatomic.html#cb1170-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1170-2"><a href="stdatomic.html#cb1170-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1170-3"><a href="stdatomic.html#cb1170-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> atomic_thread_fence<span class="op">(</span>memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-125">Description</h3>
<p>This sets up a memory fence with the specified
<code>order</code>.</p>
<table>
<thead>
<tr class="header">
<th><code>order</code></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>memory_order_seq_cst</code></td>
<td>Sequentially consistency acquire/release fence</td>
</tr>
<tr class="even">
<td><code>memory_order_acq_rel</code></td>
<td>Acquire/release dence</td>
</tr>
<tr class="odd">
<td><code>memory_order_release</code></td>
<td>Release fence</td>
</tr>
<tr class="even">
<td><code>memory_order_acquire</code></td>
<td>Acquire fence</td>
</tr>
<tr class="odd">
<td><code>memory_order_consume</code></td>
<td>Acquire fence (again)</td>
</tr>
<tr class="even">
<td><code>memory_order_relaxed</code></td>
<td>No fence at all—no point in calling with this</td>
</tr>
</tbody>
</table>
<p>You might try to avoid using these and just stick with the different
modes with <a href="#man-atomic_store"><code>atomic_store_explicit()</code></a> and <a href="#man-atomic_load"><code>atomic_load_explicit()</code></a>. Or
not.</p>
<h3 class="unnumbered unlisted" id="return-value-123">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-125">Example</h3>
<div class="sourceCode" id="cb1171"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1171-1"><a href="stdatomic.html#cb1171-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1171-2"><a href="stdatomic.html#cb1171-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1171-3"><a href="stdatomic.html#cb1171-3"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1171-4"><a href="stdatomic.html#cb1171-4"></a></span>
<span id="cb1171-5"><a href="stdatomic.html#cb1171-5"></a>atomic_int shared_1 <span class="op">=</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1171-6"><a href="stdatomic.html#cb1171-6"></a>atomic_int shared_2 <span class="op">=</span> <span class="dv">2</span><span class="op">;</span></span>
<span id="cb1171-7"><a href="stdatomic.html#cb1171-7"></a></span>
<span id="cb1171-8"><a href="stdatomic.html#cb1171-8"></a><span class="dt">int</span> thread_1<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1171-9"><a href="stdatomic.html#cb1171-9"></a><span class="op">{</span></span>
<span id="cb1171-10"><a href="stdatomic.html#cb1171-10"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1171-11"><a href="stdatomic.html#cb1171-11"></a></span>
<span id="cb1171-12"><a href="stdatomic.html#cb1171-12"></a>    atomic_store_explicit<span class="op">(&amp;</span>shared_1<span class="op">,</span> <span class="dv">10</span><span class="op">,</span> memory_order_relaxed<span class="op">);</span></span>
<span id="cb1171-13"><a href="stdatomic.html#cb1171-13"></a></span>
<span id="cb1171-14"><a href="stdatomic.html#cb1171-14"></a>    atomic_thread_fence<span class="op">(</span>memory_order_release<span class="op">);</span></span>
<span id="cb1171-15"><a href="stdatomic.html#cb1171-15"></a></span>
<span id="cb1171-16"><a href="stdatomic.html#cb1171-16"></a>    atomic_store_explicit<span class="op">(&amp;</span>shared_2<span class="op">,</span> <span class="dv">20</span><span class="op">,</span> memory_order_relaxed<span class="op">);</span></span>
<span id="cb1171-17"><a href="stdatomic.html#cb1171-17"></a></span>
<span id="cb1171-18"><a href="stdatomic.html#cb1171-18"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1171-19"><a href="stdatomic.html#cb1171-19"></a><span class="op">}</span></span>
<span id="cb1171-20"><a href="stdatomic.html#cb1171-20"></a></span>
<span id="cb1171-21"><a href="stdatomic.html#cb1171-21"></a><span class="dt">int</span> thread_2<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1171-22"><a href="stdatomic.html#cb1171-22"></a><span class="op">{</span></span>
<span id="cb1171-23"><a href="stdatomic.html#cb1171-23"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1171-24"><a href="stdatomic.html#cb1171-24"></a></span>
<span id="cb1171-25"><a href="stdatomic.html#cb1171-25"></a>    <span class="co">// If this fence runs after the release fence, we're</span></span>
<span id="cb1171-26"><a href="stdatomic.html#cb1171-26"></a>    <span class="co">// guaranteed to see thread_1's changes to the shared</span></span>
<span id="cb1171-27"><a href="stdatomic.html#cb1171-27"></a>    <span class="co">// varaibles.</span></span>
<span id="cb1171-28"><a href="stdatomic.html#cb1171-28"></a></span>
<span id="cb1171-29"><a href="stdatomic.html#cb1171-29"></a>    atomic_thread_fence<span class="op">(</span>memory_order_acquire<span class="op">);</span></span>
<span id="cb1171-30"><a href="stdatomic.html#cb1171-30"></a></span>
<span id="cb1171-31"><a href="stdatomic.html#cb1171-31"></a>    <span class="cf">if</span> <span class="op">(</span>shared_2 <span class="op">==</span> <span class="dv">20</span><span class="op">)</span> <span class="op">{</span></span>
<span id="cb1171-32"><a href="stdatomic.html#cb1171-32"></a>        printf<span class="op">(</span><span class="st">"Shared_1 better be 10 and it's %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> shared_1<span class="op">);</span></span>
<span id="cb1171-33"><a href="stdatomic.html#cb1171-33"></a>    <span class="op">}</span> <span class="cf">else</span> <span class="op">{</span></span>
<span id="cb1171-34"><a href="stdatomic.html#cb1171-34"></a>        printf<span class="op">(</span><span class="st">"Anything's possible: %d %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> shared_1<span class="op">,</span> shared_2<span class="op">);</span></span>
<span id="cb1171-35"><a href="stdatomic.html#cb1171-35"></a>    <span class="op">}</span></span>
<span id="cb1171-36"><a href="stdatomic.html#cb1171-36"></a></span>
<span id="cb1171-37"><a href="stdatomic.html#cb1171-37"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1171-38"><a href="stdatomic.html#cb1171-38"></a><span class="op">}</span></span>
<span id="cb1171-39"><a href="stdatomic.html#cb1171-39"></a></span>
<span id="cb1171-40"><a href="stdatomic.html#cb1171-40"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1171-41"><a href="stdatomic.html#cb1171-41"></a><span class="op">{</span></span>
<span id="cb1171-42"><a href="stdatomic.html#cb1171-42"></a>    thrd_t t1<span class="op">,</span> t2<span class="op">;</span></span>
<span id="cb1171-43"><a href="stdatomic.html#cb1171-43"></a></span>
<span id="cb1171-44"><a href="stdatomic.html#cb1171-44"></a>    thrd_create<span class="op">(&amp;</span>t2<span class="op">,</span> thread_2<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1171-45"><a href="stdatomic.html#cb1171-45"></a>    thrd_create<span class="op">(&amp;</span>t1<span class="op">,</span> thread_1<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1171-46"><a href="stdatomic.html#cb1171-46"></a></span>
<span id="cb1171-47"><a href="stdatomic.html#cb1171-47"></a>    thrd_join<span class="op">(</span>t1<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1171-48"><a href="stdatomic.html#cb1171-48"></a>    thrd_join<span class="op">(</span>t2<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1171-49"><a href="stdatomic.html#cb1171-49"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-117">See Also</h3>
<p><a href="stdatomic.html#man-atomic_store"><code>atomic_store_explicit()</code></a>,
<a href="stdatomic.html#man-atomic_load"><code>atomic_load_explicit()</code></a>, <a href="#man-atomic_signal_fence"><code>atomic_signal_fence()</code></a></p>
<hr>
<h2 data-number="57.9" id="man-atomic_signal_fence"><span class="header-section-number">57.9</span>
<code>atomic_signal_fence()</code></h2>
<p>Fence for intra-thread signal handlers</p>
<h3 class="unnumbered unlisted" id="synopsis-126">Synopsis</h3>
<div class="sourceCode" id="cb1172"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1172-1"><a href="stdatomic.html#cb1172-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1172-2"><a href="stdatomic.html#cb1172-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1172-3"><a href="stdatomic.html#cb1172-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> atomic_signal_fence<span class="op">(</span>memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-126">Description</h3>
<p>This works like <code>atomic_thread_fence()</code> except its purpose
is within in a single thread; notably for use in a signal handler in
that thread.</p>
<p>Since signals can happen at any time, we might need a way to be
certain that any writes by the thread that happened before the signal
handler be visible within that signal handler.</p>
<h3 class="unnumbered unlisted" id="return-value-124">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-126">Example</h3>
<p>Partial demo. (Note that it’s technically undefined behavior to call
<code>printf()</code> in a signal handler.)</p>
<div class="sourceCode" id="cb1173"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1173-1"><a href="stdatomic.html#cb1173-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1173-2"><a href="stdatomic.html#cb1173-2"></a><span class="pp">#include </span><span class="im">&lt;signal.h&gt;</span></span>
<span id="cb1173-3"><a href="stdatomic.html#cb1173-3"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1173-4"><a href="stdatomic.html#cb1173-4"></a></span>
<span id="cb1173-5"><a href="stdatomic.html#cb1173-5"></a><span class="dt">int</span> global<span class="op">;</span></span>
<span id="cb1173-6"><a href="stdatomic.html#cb1173-6"></a></span>
<span id="cb1173-7"><a href="stdatomic.html#cb1173-7"></a><span class="dt">void</span> handler<span class="op">(</span><span class="dt">int</span> sig<span class="op">)</span></span>
<span id="cb1173-8"><a href="stdatomic.html#cb1173-8"></a><span class="op">{</span></span>
<span id="cb1173-9"><a href="stdatomic.html#cb1173-9"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>sig<span class="op">;</span></span>
<span id="cb1173-10"><a href="stdatomic.html#cb1173-10"></a></span>
<span id="cb1173-11"><a href="stdatomic.html#cb1173-11"></a>    <span class="co">// If this runs before the release, the handler will</span></span>
<span id="cb1173-12"><a href="stdatomic.html#cb1173-12"></a>    <span class="co">// potentially see global == 0.</span></span>
<span id="cb1173-13"><a href="stdatomic.html#cb1173-13"></a>    <span class="co">//</span></span>
<span id="cb1173-14"><a href="stdatomic.html#cb1173-14"></a>    <span class="co">// Otherwise, it will definitely see global == 10.</span></span>
<span id="cb1173-15"><a href="stdatomic.html#cb1173-15"></a></span>
<span id="cb1173-16"><a href="stdatomic.html#cb1173-16"></a>    atomic_signal_fence<span class="op">(</span>memory_order_acquire<span class="op">);</span></span>
<span id="cb1173-17"><a href="stdatomic.html#cb1173-17"></a></span>
<span id="cb1173-18"><a href="stdatomic.html#cb1173-18"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> global<span class="op">);</span></span>
<span id="cb1173-19"><a href="stdatomic.html#cb1173-19"></a><span class="op">}</span></span>
<span id="cb1173-20"><a href="stdatomic.html#cb1173-20"></a></span>
<span id="cb1173-21"><a href="stdatomic.html#cb1173-21"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1173-22"><a href="stdatomic.html#cb1173-22"></a><span class="op">{</span></span>
<span id="cb1173-23"><a href="stdatomic.html#cb1173-23"></a>    signal<span class="op">(</span>SIGINT<span class="op">,</span> handler<span class="op">);</span></span>
<span id="cb1173-24"><a href="stdatomic.html#cb1173-24"></a></span>
<span id="cb1173-25"><a href="stdatomic.html#cb1173-25"></a>    global <span class="op">=</span> <span class="dv">10</span><span class="op">;</span></span>
<span id="cb1173-26"><a href="stdatomic.html#cb1173-26"></a></span>
<span id="cb1173-27"><a href="stdatomic.html#cb1173-27"></a>    atomic_signal_fence<span class="op">(</span>memory_order_release<span class="op">);</span></span>
<span id="cb1173-28"><a href="stdatomic.html#cb1173-28"></a></span>
<span id="cb1173-29"><a href="stdatomic.html#cb1173-29"></a>    <span class="co">// If the signal handler runs after the release</span></span>
<span id="cb1173-30"><a href="stdatomic.html#cb1173-30"></a>    <span class="co">// it will definitely see the value 10 in global.</span></span>
<span id="cb1173-31"><a href="stdatomic.html#cb1173-31"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-118">See Also</h3>
<p><a href="#man-atomic_thread_fence"><code>atomic_thread_fence()</code></a>,
<a href="signal.html#man-signal"><code>signal()</code></a></p>
<hr>
<h2 data-number="57.10" id="man-atomic_is_lock_free"><span class="header-section-number">57.10</span>
<code>atomic_is_lock_free()</code></h2>
<p>Determine if an atomic type is lock free</p>
<h3 class="unnumbered unlisted" id="synopsis-127">Synopsis</h3>
<div class="sourceCode" id="cb1174"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1174-1"><a href="stdatomic.html#cb1174-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1174-2"><a href="stdatomic.html#cb1174-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1174-3"><a href="stdatomic.html#cb1174-3" aria-hidden="true" tabindex="-1"></a><span class="dt">_Bool</span> atomic_is_lock_free<span class="op">(</span><span class="dt">const</span> <span class="dt">volatile</span> A <span class="op">*</span>obj<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-127">Description</h3>
<p>Determines if the variable <code>obj</code> of type <code>A</code> is
lock-free. Can be used with any type.</p>
<p>Unlike the <a href="stdatomic.html#lock-free-macros">lock-free macros</a> which can
be used at compile-time, this is strictly a run-time function. So in
places where the macros say “maybe”, this function will definitely tell
you one way or another if the atomic variable is lock-free.</p>
<p>This is useful when you’re defining your own atomic variables and
want to know their lock-free status.</p>
<h3 class="unnumbered unlisted" id="return-value-125">Return Value</h3>
<p>True if the variable is lock-free, false otherwise.</p>
<h3 class="unnumbered unlisted" id="example-127">Example</h3>
<p>Test if a couple <code>struct</code>s and an atomic
<code>double</code> are lock-free. On my system, the larger
<code>struct</code> is too big to be lock-free, but the other two are
OK.</p>
<div class="sourceCode" id="cb1175"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1175-1"><a href="stdatomic.html#cb1175-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1175-2"><a href="stdatomic.html#cb1175-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1175-3"><a href="stdatomic.html#cb1175-3"></a></span>
<span id="cb1175-4"><a href="stdatomic.html#cb1175-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1175-5"><a href="stdatomic.html#cb1175-5"></a><span class="op">{</span></span>
<span id="cb1175-6"><a href="stdatomic.html#cb1175-6"></a>    <span class="kw">struct</span> foo <span class="op">{</span></span>
<span id="cb1175-7"><a href="stdatomic.html#cb1175-7"></a>        <span class="dt">int</span> x<span class="op">,</span> y<span class="op">;</span></span>
<span id="cb1175-8"><a href="stdatomic.html#cb1175-8"></a>    <span class="op">};</span></span>
<span id="cb1175-9"><a href="stdatomic.html#cb1175-9"></a></span>
<span id="cb1175-10"><a href="stdatomic.html#cb1175-10"></a>    <span class="kw">struct</span> bar <span class="op">{</span></span>
<span id="cb1175-11"><a href="stdatomic.html#cb1175-11"></a>        <span class="dt">int</span> x<span class="op">,</span> y<span class="op">,</span> z<span class="op">;</span></span>
<span id="cb1175-12"><a href="stdatomic.html#cb1175-12"></a>    <span class="op">};</span></span>
<span id="cb1175-13"><a href="stdatomic.html#cb1175-13"></a></span>
<span id="cb1175-14"><a href="stdatomic.html#cb1175-14"></a>    <span class="kw">_Atomic</span><span class="op">(</span><span class="dt">double</span><span class="op">)</span> a<span class="op">;</span></span>
<span id="cb1175-15"><a href="stdatomic.html#cb1175-15"></a>    <span class="kw">struct</span> foo b<span class="op">;</span></span>
<span id="cb1175-16"><a href="stdatomic.html#cb1175-16"></a>    <span class="kw">struct</span> bar c<span class="op">;</span></span>
<span id="cb1175-17"><a href="stdatomic.html#cb1175-17"></a></span>
<span id="cb1175-18"><a href="stdatomic.html#cb1175-18"></a>    printf<span class="op">(</span><span class="st">"a is lock-free: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> atomic_is_lock_free<span class="op">(&amp;</span>a<span class="op">));</span></span>
<span id="cb1175-19"><a href="stdatomic.html#cb1175-19"></a>    printf<span class="op">(</span><span class="st">"b is lock-free: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> atomic_is_lock_free<span class="op">(&amp;</span>b<span class="op">));</span></span>
<span id="cb1175-20"><a href="stdatomic.html#cb1175-20"></a>    printf<span class="op">(</span><span class="st">"c is lock-free: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> atomic_is_lock_free<span class="op">(&amp;</span>c<span class="op">));</span></span>
<span id="cb1175-21"><a href="stdatomic.html#cb1175-21"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system (YMMV):</p>
<div class="sourceCode" id="cb1176"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1176-1"><a href="stdatomic.html#cb1176-1" aria-hidden="true" tabindex="-1"></a>a is lock-free: 1</span>
<span id="cb1176-2"><a href="stdatomic.html#cb1176-2" aria-hidden="true" tabindex="-1"></a>b is lock-free: 1</span>
<span id="cb1176-3"><a href="stdatomic.html#cb1176-3" aria-hidden="true" tabindex="-1"></a>c is lock-free: 0</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-119">See Also</h3>
<p><a href="stdatomic.html#lock-free-macros">Lock-free Macros</a></p>
<hr>
<h2 data-number="57.11" id="man-atomic_store"><span class="header-section-number">57.11</span>
<code>atomic_store()</code></h2>
<p>Store a value in an atomic variable</p>
<h3 class="unnumbered unlisted" id="synopsis-128">Synopsis</h3>
<div class="sourceCode" id="cb1177"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1177-1"><a href="stdatomic.html#cb1177-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1177-2"><a href="stdatomic.html#cb1177-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1177-3"><a href="stdatomic.html#cb1177-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> atomic_store<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span> C desired<span class="op">);</span></span>
<span id="cb1177-4"><a href="stdatomic.html#cb1177-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1177-5"><a href="stdatomic.html#cb1177-5" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> atomic_store_explicit<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span></span>
<span id="cb1177-6"><a href="stdatomic.html#cb1177-6" aria-hidden="true" tabindex="-1"></a>                           C desired<span class="op">,</span> memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-128">Description</h3>
<p>Store a value in an atomic variable, possible synchronized.</p>
<p>This is like a plain assignment, but with more flexibility.</p>
<p>These have the same storage effect for an
<code>atomic_int x</code>:</p>
<div class="sourceCode" id="cb1178"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1178-1"><a href="stdatomic.html#cb1178-1" aria-hidden="true" tabindex="-1"></a>x <span class="op">=</span> <span class="dv">10</span><span class="op">;</span></span>
<span id="cb1178-2"><a href="stdatomic.html#cb1178-2" aria-hidden="true" tabindex="-1"></a>atomic_store<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb1178-3"><a href="stdatomic.html#cb1178-3" aria-hidden="true" tabindex="-1"></a>atomic_store_explicit<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">10</span><span class="op">,</span> memory_order_seq_cst<span class="op">);</span></span></code></pre></div>
<p>But the last function, <code>atomic_store_explicit()</code>, lets you
specify the memory order.</p>
<p>Since this is a “release-y” operation, none of the “acquire-y” memory
orders are legal. <code>order</code> can be only be
<code>memory_order_seq_cst</code>, <code>memory_order_release</code>, or
<code>memory_order_relaxed</code>.</p>
<p><code>order</code> cannot be <code>memory_order_acq_rel</code>,
<code>memory_order_acquire</code>, or
<code>memory_order_consume</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-126">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-128">Example</h3>
<div class="sourceCode" id="cb1179"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1179-1"><a href="stdatomic.html#cb1179-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1179-2"><a href="stdatomic.html#cb1179-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1179-3"><a href="stdatomic.html#cb1179-3"></a></span>
<span id="cb1179-4"><a href="stdatomic.html#cb1179-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1179-5"><a href="stdatomic.html#cb1179-5"></a><span class="op">{</span></span>
<span id="cb1179-6"><a href="stdatomic.html#cb1179-6"></a>    atomic_int x <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1179-7"><a href="stdatomic.html#cb1179-7"></a>    atomic_int y <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1179-8"><a href="stdatomic.html#cb1179-8"></a></span>
<span id="cb1179-9"><a href="stdatomic.html#cb1179-9"></a>    atomic_store<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb1179-10"><a href="stdatomic.html#cb1179-10"></a></span>
<span id="cb1179-11"><a href="stdatomic.html#cb1179-11"></a>    atomic_store_explicit<span class="op">(&amp;</span>y<span class="op">,</span> <span class="dv">20</span><span class="op">,</span> memory_order_relaxed<span class="op">);</span></span>
<span id="cb1179-12"><a href="stdatomic.html#cb1179-12"></a></span>
<span id="cb1179-13"><a href="stdatomic.html#cb1179-13"></a>    <span class="co">// Will print either "10 20" or "10 0":</span></span>
<span id="cb1179-14"><a href="stdatomic.html#cb1179-14"></a>    printf<span class="op">(</span><span class="st">"%d %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">,</span> y<span class="op">);</span></span>
<span id="cb1179-15"><a href="stdatomic.html#cb1179-15"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-120">See Also</h3>
<p><a href="stdatomic.html#man-atomic_init"><code>atomic_init()</code></a>, <a href="#man-atomic_load"><code>atomic_load()</code></a>, <a href="#man-atomic_load"><code>atomic_load_explicit()</code></a>, <a href="#man-atomic_exchange"><code>atomic_exchange()</code></a>,<br>
<a href="#man-atomic_exchange"><code>atomic_exchange_explicit()</code></a>,
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong()</code></a>,<br>
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong_explicit()</code></a>,
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak()</code></a>,<br>
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak_explicit()</code></a>,
<a href="stdatomic.html#man-atomic_fetch"><code>atomic_fetch_*()</code></a></p>
<hr>
<h2 data-number="57.12" id="man-atomic_load"><span class="header-section-number">57.12</span>
<code>atomic_load()</code></h2>
<p>Return a value from an atomic variable</p>
<h3 class="unnumbered unlisted" id="synopsis-129">Synopsis</h3>
<div class="sourceCode" id="cb1180"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1180-1"><a href="stdatomic.html#cb1180-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1180-2"><a href="stdatomic.html#cb1180-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1180-3"><a href="stdatomic.html#cb1180-3" aria-hidden="true" tabindex="-1"></a>C atomic_load<span class="op">(</span><span class="dt">const</span> <span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">);</span></span>
<span id="cb1180-4"><a href="stdatomic.html#cb1180-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1180-5"><a href="stdatomic.html#cb1180-5" aria-hidden="true" tabindex="-1"></a>C atomic_load_explicit<span class="op">(</span><span class="dt">const</span> <span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span> memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-129">Description</h3>
<p>For a pointer to an <code>object</code> of type <code>A</code>,
atomically returns its value <code>C</code>. This is a generic function
that can be used with any type.</p>
<p>The function <code>atomic_load_explicit()</code> lets you specify the
memory order.</p>
<p>Since this is an “acquire-y” operation, none of the “release-y”
memory orders are legal. <code>order</code> can be only be
<code>memory_order_seq_cst</code>, <code>memory_order_acquire</code>,
<code>memory_order_consume</code>, or
<code>memory_order_relaxed</code>.</p>
<p><code>order</code> cannot be <code>memory_order_acq_rel</code> or
<code>memory_order_release</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-127">Return Value</h3>
<p>Returns the value stored in <code>object</code>.</p>
<h3 class="unnumbered unlisted" id="example-129">Example</h3>
<div class="sourceCode" id="cb1181"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1181-1"><a href="stdatomic.html#cb1181-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1181-2"><a href="stdatomic.html#cb1181-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1181-3"><a href="stdatomic.html#cb1181-3"></a></span>
<span id="cb1181-4"><a href="stdatomic.html#cb1181-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1181-5"><a href="stdatomic.html#cb1181-5"></a><span class="op">{</span></span>
<span id="cb1181-6"><a href="stdatomic.html#cb1181-6"></a>    atomic_int x <span class="op">=</span> <span class="dv">10</span><span class="op">;</span></span>
<span id="cb1181-7"><a href="stdatomic.html#cb1181-7"></a></span>
<span id="cb1181-8"><a href="stdatomic.html#cb1181-8"></a>    <span class="dt">int</span> v <span class="op">=</span> atomic_load<span class="op">(&amp;</span>x<span class="op">);</span></span>
<span id="cb1181-9"><a href="stdatomic.html#cb1181-9"></a></span>
<span id="cb1181-10"><a href="stdatomic.html#cb1181-10"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> v<span class="op">);</span>  <span class="co">// 10</span></span>
<span id="cb1181-11"><a href="stdatomic.html#cb1181-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-121">See Also</h3>
<p><a href="stdatomic.html#man-atomic_store"><code>atomic_store()</code></a>, <a href="#man-atomic_store"><code>atomic_store_explicit()</code></a></p>
<hr>
<h2 data-number="57.13" id="man-atomic_exchange"><span class="header-section-number">57.13</span>
<code>atomic_exchange()</code></h2>
<p>Replace a value in an atomic object</p>
<h3 class="unnumbered unlisted" id="synopsis-130">Synopsis</h3>
<div class="sourceCode" id="cb1182"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1182-1"><a href="stdatomic.html#cb1182-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1182-2"><a href="stdatomic.html#cb1182-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1182-3"><a href="stdatomic.html#cb1182-3" aria-hidden="true" tabindex="-1"></a>C atomic_exchange<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span> C desired<span class="op">);</span></span>
<span id="cb1182-4"><a href="stdatomic.html#cb1182-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1182-5"><a href="stdatomic.html#cb1182-5" aria-hidden="true" tabindex="-1"></a>C atomic_exchange_explicit<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span> C desired<span class="op">,</span></span>
<span id="cb1182-6"><a href="stdatomic.html#cb1182-6" aria-hidden="true" tabindex="-1"></a>                           memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-130">Description</h3>
<p>Sets the value in <code>object</code> to <code>desired</code>.</p>
<p><code>object</code> is type <code>A</code>, some atomic type.</p>
<p><code>desired</code> is type <code>C</code>, the respective
non-atomic type to <code>A</code>.</p>
<p>This is very similar to <code>atomic_store()</code>, except the
previous value is atomically returned.</p>
<h3 class="unnumbered unlisted" id="return-value-128">Return Value</h3>
<p>Returns the previous value of <code>object</code>.</p>
<h3 class="unnumbered unlisted" id="example-130">Example</h3>
<div class="sourceCode" id="cb1183"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1183-1"><a href="stdatomic.html#cb1183-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1183-2"><a href="stdatomic.html#cb1183-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1183-3"><a href="stdatomic.html#cb1183-3"></a></span>
<span id="cb1183-4"><a href="stdatomic.html#cb1183-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1183-5"><a href="stdatomic.html#cb1183-5"></a><span class="op">{</span></span>
<span id="cb1183-6"><a href="stdatomic.html#cb1183-6"></a>    atomic_int x <span class="op">=</span> <span class="dv">10</span><span class="op">;</span></span>
<span id="cb1183-7"><a href="stdatomic.html#cb1183-7"></a></span>
<span id="cb1183-8"><a href="stdatomic.html#cb1183-8"></a>    <span class="dt">int</span> previous <span class="op">=</span> atomic_exchange<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">20</span><span class="op">);</span></span>
<span id="cb1183-9"><a href="stdatomic.html#cb1183-9"></a></span>
<span id="cb1183-10"><a href="stdatomic.html#cb1183-10"></a>    printf<span class="op">(</span><span class="st">"x is  %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb1183-11"><a href="stdatomic.html#cb1183-11"></a>    printf<span class="op">(</span><span class="st">"x was %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> previous<span class="op">);</span></span>
<span id="cb1183-12"><a href="stdatomic.html#cb1183-12"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1184"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1184-1"><a href="stdatomic.html#cb1184-1" aria-hidden="true" tabindex="-1"></a>x is  20</span>
<span id="cb1184-2"><a href="stdatomic.html#cb1184-2" aria-hidden="true" tabindex="-1"></a>x was 10</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-122">See Also</h3>
<p><a href="stdatomic.html#man-atomic_init"><code>atomic_init()</code></a>, <a href="#man-atomic_load"><code>atomic_load()</code></a>, <a href="#man-atomic_load"><code>atomic_load_explicit()</code></a>, <a href="#man-atomic_store"><code>atomic_store()</code></a>,<br>
<a href="stdatomic.html#man-atomic_store"><code>atomic_store_explicit()</code></a> <a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong()</code></a>,<br>
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong_explicit()</code></a>,
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak()</code></a>,<br>
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak_explicit()</code></a></p>
<hr>
<h2 data-number="57.14" id="man-atomic_compare_exchange"><span class="header-section-number">57.14</span>
<code>atomic_compare_exchange_*()</code></h2>
<p>Atomic compare and exchange</p>
<h3 class="unnumbered unlisted" id="synopsis-131">Synopsis</h3>
<div class="sourceCode" id="cb1185"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1185-1"><a href="stdatomic.html#cb1185-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1185-2"><a href="stdatomic.html#cb1185-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1185-3"><a href="stdatomic.html#cb1185-3" aria-hidden="true" tabindex="-1"></a><span class="dt">_Bool</span> atomic_compare_exchange_strong<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span></span>
<span id="cb1185-4"><a href="stdatomic.html#cb1185-4" aria-hidden="true" tabindex="-1"></a>                                     C <span class="op">*</span>expected<span class="op">,</span> C desired<span class="op">);</span></span>
<span id="cb1185-5"><a href="stdatomic.html#cb1185-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1185-6"><a href="stdatomic.html#cb1185-6" aria-hidden="true" tabindex="-1"></a><span class="dt">_Bool</span> atomic_compare_exchange_strong_explicit<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span></span>
<span id="cb1185-7"><a href="stdatomic.html#cb1185-7" aria-hidden="true" tabindex="-1"></a>                                              C <span class="op">*</span>expected<span class="op">,</span> C desired<span class="op">,</span></span>
<span id="cb1185-8"><a href="stdatomic.html#cb1185-8" aria-hidden="true" tabindex="-1"></a>                                              memory_order success<span class="op">,</span></span>
<span id="cb1185-9"><a href="stdatomic.html#cb1185-9" aria-hidden="true" tabindex="-1"></a>                                              memory_order failure<span class="op">);</span></span>
<span id="cb1185-10"><a href="stdatomic.html#cb1185-10" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1185-11"><a href="stdatomic.html#cb1185-11" aria-hidden="true" tabindex="-1"></a><span class="dt">_Bool</span> atomic_compare_exchange_weak<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span></span>
<span id="cb1185-12"><a href="stdatomic.html#cb1185-12" aria-hidden="true" tabindex="-1"></a>                                   C <span class="op">*</span>expected<span class="op">,</span> C desired<span class="op">);</span></span>
<span id="cb1185-13"><a href="stdatomic.html#cb1185-13" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1185-14"><a href="stdatomic.html#cb1185-14" aria-hidden="true" tabindex="-1"></a><span class="dt">_Bool</span> atomic_compare_exchange_weak_explicit<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span></span>
<span id="cb1185-15"><a href="stdatomic.html#cb1185-15" aria-hidden="true" tabindex="-1"></a>                                            C <span class="op">*</span>expected<span class="op">,</span> C desired<span class="op">,</span></span>
<span id="cb1185-16"><a href="stdatomic.html#cb1185-16" aria-hidden="true" tabindex="-1"></a>                                            memory_order success<span class="op">,</span></span>
<span id="cb1185-17"><a href="stdatomic.html#cb1185-17" aria-hidden="true" tabindex="-1"></a>                                            memory_order failure<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-131">Description</h3>
<p>The venerable basis for some many things lock-free: compare and
exchange.</p>
<p>In the above prototypes, <code>A</code> is the type of the atomic
object, and <code>C</code> is the equivalent base type.</p>
<p>Ignoring the <code>_explicit</code> versions for a moment, what these
do is:</p>
<ul>
<li><p>If the value pointed to by <code>object</code> is equal to the
value pointed to by <code>expected</code>, then the value pointed to by
<code>object</code> is set to <code>desired</code>. And the function
returns <code>true</code> indicating the exchange did take
place.</p></li>
<li><p>Else the value pointed to by <code>expected</code> (yes,
<code>expected</code>) is set to <code>desired</code> and the function
returns <code>false</code> indicating the exchange did not take
place.</p></li>
</ul>
<p>Pseudocode for the exchange would look like this<a href="footnotes.html#fn248" class="footnote-ref" id="fnref248" role="doc-noteref"><sup>248</sup></a>:</p>
<div class="sourceCode" id="cb1186"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1186-1"><a href="stdatomic.html#cb1186-1" aria-hidden="true" tabindex="-1"></a><span class="dt">bool</span> compare_exchange<span class="op">(</span>atomic_A <span class="op">*</span>object<span class="op">,</span> C <span class="op">*</span>expected<span class="op">,</span> C desired<span class="op">)</span></span>
<span id="cb1186-2"><a href="stdatomic.html#cb1186-2" aria-hidden="true" tabindex="-1"></a><span class="op">{</span></span>
<span id="cb1186-3"><a href="stdatomic.html#cb1186-3" aria-hidden="true" tabindex="-1"></a>    <span class="cf">if</span> <span class="op">(*</span>object is the same as <span class="op">*</span>expected<span class="op">)</span> <span class="op">{</span></span>
<span id="cb1186-4"><a href="stdatomic.html#cb1186-4" aria-hidden="true" tabindex="-1"></a>        <span class="op">*</span>object <span class="op">=</span> desired</span>
<span id="cb1186-5"><a href="stdatomic.html#cb1186-5" aria-hidden="true" tabindex="-1"></a>        <span class="cf">return</span> true</span>
<span id="cb1186-6"><a href="stdatomic.html#cb1186-6" aria-hidden="true" tabindex="-1"></a>    <span class="op">}</span></span>
<span id="cb1186-7"><a href="stdatomic.html#cb1186-7" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1186-8"><a href="stdatomic.html#cb1186-8" aria-hidden="true" tabindex="-1"></a>    <span class="op">*</span>expected <span class="op">=</span> desired</span>
<span id="cb1186-9"><a href="stdatomic.html#cb1186-9" aria-hidden="true" tabindex="-1"></a>    <span class="cf">return</span> false</span>
<span id="cb1186-10"><a href="stdatomic.html#cb1186-10" aria-hidden="true" tabindex="-1"></a><span class="op">}</span></span></code></pre></div>
<p>The <code>_weak</code> variants might spontaneously fail, so even if
<code>*object == *desired</code>, it might not change the value and will
return <code>false</code>. So you’ll want that in a loop if you use it<a href="#fn249" class="footnote-ref" id="fnref249" role="doc-noteref"><sup>249</sup></a>.</p>
<p>The <code>_explicit</code> variants have two memory orders:
<code>success</code> if <code>*object</code> is set to
<code>desired</code>, and <code>failure</code> if it is not.</p>
<p>These are test-and-set functions, so you can use
<code>memory_order_acq_rel</code> with the <code>_explicit</code>
variants.</p>
<h3 class="unnumbered unlisted" id="return-value-129">Return Value</h3>
<p>Returns <code>true</code> if <code>*object</code> was
<code>*expected</code>. Otherwise, <code>false</code>.</p>
<h3 class="unnumbered unlisted" id="example-131">Example</h3>
<p>A contrived example where multiple threads add <code>2</code> to a
shared value in a lock-free way.</p>
<p>(It would be better to use <code>+= 2</code> to get this done in real
life unless you were using some <code>_explicit</code> wizardry.)</p>
<div class="sourceCode" id="cb1187"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1187-1"><a href="stdatomic.html#cb1187-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1187-2"><a href="stdatomic.html#cb1187-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1187-3"><a href="stdatomic.html#cb1187-3"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1187-4"><a href="stdatomic.html#cb1187-4"></a></span>
<span id="cb1187-5"><a href="stdatomic.html#cb1187-5"></a><span class="pp">#define LOOP_COUNT 10000</span></span>
<span id="cb1187-6"><a href="stdatomic.html#cb1187-6"></a></span>
<span id="cb1187-7"><a href="stdatomic.html#cb1187-7"></a>atomic_int value<span class="op">;</span></span>
<span id="cb1187-8"><a href="stdatomic.html#cb1187-8"></a></span>
<span id="cb1187-9"><a href="stdatomic.html#cb1187-9"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1187-10"><a href="stdatomic.html#cb1187-10"></a><span class="op">{</span></span>
<span id="cb1187-11"><a href="stdatomic.html#cb1187-11"></a>    <span class="op">(</span><span class="dt">void</span><span class="op">)</span>arg<span class="op">;</span></span>
<span id="cb1187-12"><a href="stdatomic.html#cb1187-12"></a></span>
<span id="cb1187-13"><a href="stdatomic.html#cb1187-13"></a>    <span class="cf">for</span><span class="op">(</span><span class="dt">int</span> i <span class="op">=</span> <span class="dv">0</span><span class="op">;</span> i <span class="op">&lt;</span> LOOP_COUNT<span class="op">;</span> i<span class="op">++)</span> <span class="op">{</span></span>
<span id="cb1187-14"><a href="stdatomic.html#cb1187-14"></a></span>
<span id="cb1187-15"><a href="stdatomic.html#cb1187-15"></a>        <span class="dt">int</span> cur <span class="op">=</span> value<span class="op">;</span></span>
<span id="cb1187-16"><a href="stdatomic.html#cb1187-16"></a>        <span class="dt">int</span> next<span class="op">;</span></span>
<span id="cb1187-17"><a href="stdatomic.html#cb1187-17"></a></span>
<span id="cb1187-18"><a href="stdatomic.html#cb1187-18"></a>        <span class="cf">do</span> <span class="op">{</span></span>
<span id="cb1187-19"><a href="stdatomic.html#cb1187-19"></a>            next <span class="op">=</span> cur <span class="op">+</span> <span class="dv">2</span><span class="op">;</span></span>
<span id="cb1187-20"><a href="stdatomic.html#cb1187-20"></a>        <span class="op">}</span> <span class="cf">while</span> <span class="op">(!</span>atomic_compare_exchange_strong<span class="op">(&amp;</span>value<span class="op">,</span> <span class="op">&amp;</span>cur<span class="op">,</span> next<span class="op">));</span></span>
<span id="cb1187-21"><a href="stdatomic.html#cb1187-21"></a>    <span class="op">}</span></span>
<span id="cb1187-22"><a href="stdatomic.html#cb1187-22"></a></span>
<span id="cb1187-23"><a href="stdatomic.html#cb1187-23"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1187-24"><a href="stdatomic.html#cb1187-24"></a><span class="op">}</span></span>
<span id="cb1187-25"><a href="stdatomic.html#cb1187-25"></a></span>
<span id="cb1187-26"><a href="stdatomic.html#cb1187-26"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1187-27"><a href="stdatomic.html#cb1187-27"></a><span class="op">{</span></span>
<span id="cb1187-28"><a href="stdatomic.html#cb1187-28"></a>    thrd_t t1<span class="op">,</span> t2<span class="op">;</span></span>
<span id="cb1187-29"><a href="stdatomic.html#cb1187-29"></a></span>
<span id="cb1187-30"><a href="stdatomic.html#cb1187-30"></a>    thrd_create<span class="op">(&amp;</span>t1<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1187-31"><a href="stdatomic.html#cb1187-31"></a>    thrd_create<span class="op">(&amp;</span>t2<span class="op">,</span> run<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1187-32"><a href="stdatomic.html#cb1187-32"></a></span>
<span id="cb1187-33"><a href="stdatomic.html#cb1187-33"></a>    thrd_join<span class="op">(</span>t1<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1187-34"><a href="stdatomic.html#cb1187-34"></a>    thrd_join<span class="op">(</span>t2<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1187-35"><a href="stdatomic.html#cb1187-35"></a>    </span>
<span id="cb1187-36"><a href="stdatomic.html#cb1187-36"></a>    printf<span class="op">(</span><span class="st">"%d should equal %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> value<span class="op">,</span> LOOP_COUNT <span class="op">*</span> <span class="dv">4</span><span class="op">);</span></span>
<span id="cb1187-37"><a href="stdatomic.html#cb1187-37"></a><span class="op">}</span></span></code></pre></div>
<p>Just replacing this with <code>value = value + 2</code> causes data
trampling.</p>
<h3 class="unnumbered unlisted" id="see-also-123">See Also</h3>
<p><a href="stdatomic.html#man-atomic_load"><code>atomic_load()</code></a>, <a href="#man-atomic_load"><code>atomic_load_explicit()</code></a>, <a href="#man-atomic_store"><code>atomic_store()</code></a>, <a href="#man-atomic_store"><code>atomic_store_explicit()</code></a>, <a href="#man-atomic_exchange"><code>atomic_exchange()</code></a>, <a href="#man-atomic_exchange"><code>atomic_exchange_explicit()</code></a>,
<a href="stdatomic.html#man-atomic_fetch"><code>atomic_fetch_*()</code></a></p>
<hr>
<h2 data-number="57.15" id="man-atomic_fetch"><span class="header-section-number">57.15</span>
<code>atomic_fetch_*()</code></h2>
<p>Atomically modify atomic variables</p>
<h3 class="unnumbered unlisted" id="synopsis-132">Synopsis</h3>
<div class="sourceCode" id="cb1188"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1188-1"><a href="stdatomic.html#cb1188-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1188-2"><a href="stdatomic.html#cb1188-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1188-3"><a href="stdatomic.html#cb1188-3" aria-hidden="true" tabindex="-1"></a>C atomic_fetch_KEY<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span> M operand<span class="op">);</span></span>
<span id="cb1188-4"><a href="stdatomic.html#cb1188-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1188-5"><a href="stdatomic.html#cb1188-5" aria-hidden="true" tabindex="-1"></a>C atomic_fetch_KEY_explicit<span class="op">(</span><span class="dt">volatile</span> A <span class="op">*</span>object<span class="op">,</span> M operand<span class="op">,</span></span>
<span id="cb1188-6"><a href="stdatomic.html#cb1188-6" aria-hidden="true" tabindex="-1"></a>                            memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-132">Description</h3>
<p>These are actually a group of 10 functions. You substitute one of the
following for <code>KEY</code> to perform that operation:</p>
<ul>
<li><code>add</code></li>
<li><code>sub</code></li>
<li><code>or</code></li>
<li><code>xor</code></li>
<li><code>and</code></li>
</ul>
<p>So these functions can add or subtract values to or from an atomic
variable, or can perform bitwise-OR, XOR, or AND on them.</p>
<p>Use it with integer or pointer types. Though the spec is a little
vague on the matter, other types make C unhappy. It goes out of its way
to avoid undefined behavior with signed integers, as well:</p>
<p>C18 §7.17.7.5 ¶3:</p>
<blockquote>
<p>For signed integer types, arithmetic is defined to use two’s
complement representation with silent wrap-around on overflow; there are
no undefined results.</p>
</blockquote>
<p>In the synopsis, above, <code>A</code> is an atomic type, and
<code>M</code> is the corresponding non-atomic type for <code>A</code>
(or <code>ptrdiff_t</code> for atomic pointers), and <code>C</code> is
the corresponding non-atomic type for <code>A</code>.</p>
<p>For example, here are some operations on an
<code>atomic_int</code>.</p>
<div class="sourceCode" id="cb1189"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1189-1"><a href="stdatomic.html#cb1189-1" aria-hidden="true" tabindex="-1"></a>atomic_fetch_add<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">20</span><span class="op">);</span></span>
<span id="cb1189-2"><a href="stdatomic.html#cb1189-2" aria-hidden="true" tabindex="-1"></a>atomic_fetch_sub<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">37</span><span class="op">);</span></span>
<span id="cb1189-3"><a href="stdatomic.html#cb1189-3" aria-hidden="true" tabindex="-1"></a>atomic_fetch_xor<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">3490</span><span class="op">);</span></span></code></pre></div>
<p>They are the same as <code>+=</code>, <code>-=</code>,
<code>|=</code>, <code>^=</code> and <code>&amp;=</code>, except the
return value is the <em>previous</em> value of the atomic object. (With
the assignment operators, the value of the expression is that
<em>after</em> its evaluation.)</p>
<div class="sourceCode" id="cb1190"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1190-1"><a href="stdatomic.html#cb1190-1" aria-hidden="true" tabindex="-1"></a>atomic_int x <span class="op">=</span> <span class="dv">10</span><span class="op">;</span></span>
<span id="cb1190-2"><a href="stdatomic.html#cb1190-2" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> prev <span class="op">=</span> atomic_fetch_add<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">20</span><span class="op">);</span></span>
<span id="cb1190-3"><a href="stdatomic.html#cb1190-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%d %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> prev<span class="op">,</span> x<span class="op">);</span>  <span class="co">// 10 30</span></span></code></pre></div>
<p>versus:</p>
<div class="sourceCode" id="cb1191"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1191-1"><a href="stdatomic.html#cb1191-1" aria-hidden="true" tabindex="-1"></a>atomic_int x <span class="op">=</span> <span class="dv">10</span><span class="op">;</span></span>
<span id="cb1191-2"><a href="stdatomic.html#cb1191-2" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> prev <span class="op">=</span> <span class="op">(</span>x <span class="op">+=</span> <span class="dv">20</span><span class="op">);</span></span>
<span id="cb1191-3"><a href="stdatomic.html#cb1191-3" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"%d %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> prev<span class="op">,</span> x<span class="op">);</span>  <span class="co">// 30 30</span></span></code></pre></div>
<p>And, of course, the <code>_explicit</code> version allows you to
specify a memory order and all the assignment operators are
<code>memory_order_seq_cst</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-130">Return Value</h3>
<p>Returns the previous value of the atomic object before the
modification.</p>
<h3 class="unnumbered unlisted" id="example-132">Example</h3>
<div class="sourceCode" id="cb1192"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1192-1"><a href="stdatomic.html#cb1192-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1192-2"><a href="stdatomic.html#cb1192-2"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1192-3"><a href="stdatomic.html#cb1192-3"></a></span>
<span id="cb1192-4"><a href="stdatomic.html#cb1192-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1192-5"><a href="stdatomic.html#cb1192-5"></a><span class="op">{</span></span>
<span id="cb1192-6"><a href="stdatomic.html#cb1192-6"></a>    atomic_int x <span class="op">=</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1192-7"><a href="stdatomic.html#cb1192-7"></a>    <span class="dt">int</span> prev<span class="op">;</span></span>
<span id="cb1192-8"><a href="stdatomic.html#cb1192-8"></a></span>
<span id="cb1192-9"><a href="stdatomic.html#cb1192-9"></a>    atomic_fetch_add<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">3490</span><span class="op">);</span></span>
<span id="cb1192-10"><a href="stdatomic.html#cb1192-10"></a>    atomic_fetch_sub<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">12</span><span class="op">);</span></span>
<span id="cb1192-11"><a href="stdatomic.html#cb1192-11"></a>    atomic_fetch_xor<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">444</span><span class="op">);</span></span>
<span id="cb1192-12"><a href="stdatomic.html#cb1192-12"></a>    atomic_fetch_or<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">12</span><span class="op">);</span></span>
<span id="cb1192-13"><a href="stdatomic.html#cb1192-13"></a>    prev <span class="op">=</span> atomic_fetch_and<span class="op">(&amp;</span>x<span class="op">,</span> <span class="dv">42</span><span class="op">);</span></span>
<span id="cb1192-14"><a href="stdatomic.html#cb1192-14"></a></span>
<span id="cb1192-15"><a href="stdatomic.html#cb1192-15"></a>    printf<span class="op">(</span><span class="st">"%d %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> prev<span class="op">,</span> x<span class="op">);</span>   <span class="co">// 3118 42</span></span>
<span id="cb1192-16"><a href="stdatomic.html#cb1192-16"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-124">See Also</h3>
<p><a href="stdatomic.html#man-atomic_exchange"><code>atomic_exchange()</code></a>, <a href="#man-atomic_exchange"><code>atomic_exchange_explicit()</code></a>,
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong()</code></a>,<br>
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_strong_explicit()</code></a>,
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak()</code></a>,<br>
<a href="#man-atomic_compare_exchange"><code>atomic_compare_exchange_weak_explicit()</code></a></p>
<hr>
<h2 data-number="57.16" id="man-atomic_flag_test_and_set"><span class="header-section-number">57.16</span>
<code>atomic_flag_test_and_set()</code></h2>
<p>Test and set an atomic flag</p>
<h3 class="unnumbered unlisted" id="synopsis-133">Synopsis</h3>
<div class="sourceCode" id="cb1193"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1193-1"><a href="stdatomic.html#cb1193-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1193-2"><a href="stdatomic.html#cb1193-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1193-3"><a href="stdatomic.html#cb1193-3" aria-hidden="true" tabindex="-1"></a><span class="dt">_Bool</span> atomic_flag_test_and_set<span class="op">(</span><span class="dt">volatile</span> atomic_flag <span class="op">*</span>object<span class="op">);</span></span>
<span id="cb1193-4"><a href="stdatomic.html#cb1193-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1193-5"><a href="stdatomic.html#cb1193-5" aria-hidden="true" tabindex="-1"></a><span class="dt">_Bool</span> atomic_flag_test_and_set_explicit<span class="op">(</span><span class="dt">volatile</span> atomic_flag <span class="op">*</span>object<span class="op">,</span></span>
<span id="cb1193-6"><a href="stdatomic.html#cb1193-6" aria-hidden="true" tabindex="-1"></a>                                        memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-133">Description</h3>
<p>One of the venerable old functions of lock-free programming, this
function sets the given atomic flag in <code>object</code>, and returns
the previous value of the flag.</p>
<p>As usual, the <code>_explicit</code> allows you to specify an
alternate memory order.</p>
<h3 class="unnumbered unlisted" id="return-value-131">Return Value</h3>
<p>Returns <code>true</code> if the flag was set previously, and
<code>false</code> if it wasn’t.</p>
<h3 class="unnumbered unlisted" id="example-133">Example</h3>
<p>Using test-and-set to implement a spin lock<a href="footnotes.html#fn250" class="footnote-ref" id="fnref250" role="doc-noteref"><sup>250</sup></a>:</p>
<div class="sourceCode" id="cb1194"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1194-1"><a href="stdatomic.html#cb1194-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1194-2"><a href="stdatomic.html#cb1194-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1194-3"><a href="stdatomic.html#cb1194-3"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1194-4"><a href="stdatomic.html#cb1194-4"></a></span>
<span id="cb1194-5"><a href="stdatomic.html#cb1194-5"></a><span class="co">// Shared non-atomic struct</span></span>
<span id="cb1194-6"><a href="stdatomic.html#cb1194-6"></a><span class="kw">struct</span> <span class="op">{</span></span>
<span id="cb1194-7"><a href="stdatomic.html#cb1194-7"></a>    <span class="dt">int</span> x<span class="op">,</span> y<span class="op">,</span> z<span class="op">;</span></span>
<span id="cb1194-8"><a href="stdatomic.html#cb1194-8"></a><span class="op">}</span> s <span class="op">=</span> <span class="op">{</span><span class="dv">1</span><span class="op">,</span> <span class="dv">2</span><span class="op">,</span> <span class="dv">3</span><span class="op">};</span></span>
<span id="cb1194-9"><a href="stdatomic.html#cb1194-9"></a></span>
<span id="cb1194-10"><a href="stdatomic.html#cb1194-10"></a>atomic_flag f <span class="op">=</span> ATOMIC_FLAG_INIT<span class="op">;</span></span>
<span id="cb1194-11"><a href="stdatomic.html#cb1194-11"></a></span>
<span id="cb1194-12"><a href="stdatomic.html#cb1194-12"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1194-13"><a href="stdatomic.html#cb1194-13"></a><span class="op">{</span></span>
<span id="cb1194-14"><a href="stdatomic.html#cb1194-14"></a>    <span class="dt">int</span> tid <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span></span>
<span id="cb1194-15"><a href="stdatomic.html#cb1194-15"></a></span>
<span id="cb1194-16"><a href="stdatomic.html#cb1194-16"></a>    printf<span class="op">(</span><span class="st">"Thread %d: waiting for lock...</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">);</span></span>
<span id="cb1194-17"><a href="stdatomic.html#cb1194-17"></a></span>
<span id="cb1194-18"><a href="stdatomic.html#cb1194-18"></a>    <span class="cf">while</span> <span class="op">(</span>atomic_flag_test_and_set<span class="op">(&amp;</span>f<span class="op">));</span></span>
<span id="cb1194-19"><a href="stdatomic.html#cb1194-19"></a></span>
<span id="cb1194-20"><a href="stdatomic.html#cb1194-20"></a>    printf<span class="op">(</span><span class="st">"Thread %d: got lock, s is {%d, %d, %d}</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">,</span></span>
<span id="cb1194-21"><a href="stdatomic.html#cb1194-21"></a>                                                       s<span class="op">.</span>x<span class="op">,</span> s<span class="op">.</span>y<span class="op">,</span> s<span class="op">.</span>z<span class="op">);</span></span>
<span id="cb1194-22"><a href="stdatomic.html#cb1194-22"></a>    s<span class="op">.</span>x <span class="op">=</span> <span class="op">(</span>tid <span class="op">+</span> <span class="dv">1</span><span class="op">)</span> <span class="op">*</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1194-23"><a href="stdatomic.html#cb1194-23"></a>    s<span class="op">.</span>y <span class="op">=</span> <span class="op">(</span>tid <span class="op">+</span> <span class="dv">1</span><span class="op">)</span> <span class="op">*</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1194-24"><a href="stdatomic.html#cb1194-24"></a>    s<span class="op">.</span>z <span class="op">=</span> <span class="op">(</span>tid <span class="op">+</span> <span class="dv">1</span><span class="op">)</span> <span class="op">*</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">2</span><span class="op">;</span></span>
<span id="cb1194-25"><a href="stdatomic.html#cb1194-25"></a>    printf<span class="op">(</span><span class="st">"Thread %d: set s to {%d, %d, %d}</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">,</span> s<span class="op">.</span>x<span class="op">,</span> s<span class="op">.</span>y<span class="op">,</span> s<span class="op">.</span>z<span class="op">);</span></span>
<span id="cb1194-26"><a href="stdatomic.html#cb1194-26"></a></span>
<span id="cb1194-27"><a href="stdatomic.html#cb1194-27"></a>    printf<span class="op">(</span><span class="st">"Thread %d: releasing lock...</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">);</span></span>
<span id="cb1194-28"><a href="stdatomic.html#cb1194-28"></a>    atomic_flag_clear<span class="op">(&amp;</span>f<span class="op">);</span></span>
<span id="cb1194-29"><a href="stdatomic.html#cb1194-29"></a></span>
<span id="cb1194-30"><a href="stdatomic.html#cb1194-30"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1194-31"><a href="stdatomic.html#cb1194-31"></a><span class="op">}</span></span>
<span id="cb1194-32"><a href="stdatomic.html#cb1194-32"></a></span>
<span id="cb1194-33"><a href="stdatomic.html#cb1194-33"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1194-34"><a href="stdatomic.html#cb1194-34"></a><span class="op">{</span></span>
<span id="cb1194-35"><a href="stdatomic.html#cb1194-35"></a>    thrd_t t1<span class="op">,</span> t2<span class="op">;</span></span>
<span id="cb1194-36"><a href="stdatomic.html#cb1194-36"></a>    <span class="dt">int</span> tid<span class="op">[]</span> <span class="op">=</span> <span class="op">{</span><span class="dv">0</span><span class="op">,</span> <span class="dv">1</span><span class="op">};</span></span>
<span id="cb1194-37"><a href="stdatomic.html#cb1194-37"></a></span>
<span id="cb1194-38"><a href="stdatomic.html#cb1194-38"></a>    thrd_create<span class="op">(&amp;</span>t1<span class="op">,</span> run<span class="op">,</span> tid<span class="op">+</span><span class="dv">0</span><span class="op">);</span></span>
<span id="cb1194-39"><a href="stdatomic.html#cb1194-39"></a>    thrd_create<span class="op">(&amp;</span>t2<span class="op">,</span> run<span class="op">,</span> tid<span class="op">+</span><span class="dv">1</span><span class="op">);</span></span>
<span id="cb1194-40"><a href="stdatomic.html#cb1194-40"></a></span>
<span id="cb1194-41"><a href="stdatomic.html#cb1194-41"></a>    thrd_join<span class="op">(</span>t1<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1194-42"><a href="stdatomic.html#cb1194-42"></a>    thrd_join<span class="op">(</span>t2<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1194-43"><a href="stdatomic.html#cb1194-43"></a><span class="op">}</span></span></code></pre></div>
<p>Example output (varies run to run):</p>
<div class="sourceCode" id="cb1195"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1195-1"><a href="stdatomic.html#cb1195-1" aria-hidden="true" tabindex="-1"></a>Thread 0: waiting for lock...</span>
<span id="cb1195-2"><a href="stdatomic.html#cb1195-2" aria-hidden="true" tabindex="-1"></a>Thread 0: got lock, s is {1, 2, 3}</span>
<span id="cb1195-3"><a href="stdatomic.html#cb1195-3" aria-hidden="true" tabindex="-1"></a>Thread 1: waiting for lock...</span>
<span id="cb1195-4"><a href="stdatomic.html#cb1195-4" aria-hidden="true" tabindex="-1"></a>Thread 0: set s to {5, 6, 7}</span>
<span id="cb1195-5"><a href="stdatomic.html#cb1195-5" aria-hidden="true" tabindex="-1"></a>Thread 0: releasing lock...</span>
<span id="cb1195-6"><a href="stdatomic.html#cb1195-6" aria-hidden="true" tabindex="-1"></a>Thread 1: got lock, s is {5, 6, 7}</span>
<span id="cb1195-7"><a href="stdatomic.html#cb1195-7" aria-hidden="true" tabindex="-1"></a>Thread 1: set s to {10, 11, 12}</span>
<span id="cb1195-8"><a href="stdatomic.html#cb1195-8" aria-hidden="true" tabindex="-1"></a>Thread 1: releasing lock...</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-125">See Also</h3>
<p><a href="#man-atomic_flag_clear"><code>atomic_flag_clear()</code></a></p>
<hr>
<h2 data-number="57.17" id="man-atomic_flag_clear"><span class="header-section-number">57.17</span>
<code>atomic_flag_clear()</code></h2>
<p>Clear an atomic flag</p>
<h3 class="unnumbered unlisted" id="synopsis-134">Synopsis</h3>
<div class="sourceCode" id="cb1196"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1196-1"><a href="stdatomic.html#cb1196-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1196-2"><a href="stdatomic.html#cb1196-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1196-3"><a href="stdatomic.html#cb1196-3" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> atomic_flag_clear<span class="op">(</span><span class="dt">volatile</span> atomic_flag <span class="op">*</span>object<span class="op">);</span></span>
<span id="cb1196-4"><a href="stdatomic.html#cb1196-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1196-5"><a href="stdatomic.html#cb1196-5" aria-hidden="true" tabindex="-1"></a><span class="dt">void</span> atomic_flag_clear_explicit<span class="op">(</span><span class="dt">volatile</span> atomic_flag <span class="op">*</span>object<span class="op">,</span></span>
<span id="cb1196-6"><a href="stdatomic.html#cb1196-6" aria-hidden="true" tabindex="-1"></a>                                memory_order order<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-134">Description</h3>
<p>Clears an atomic flag.</p>
<p>As usual, the <code>_explicit</code> allows you to specify an
alternate memory order.</p>
<h3 class="unnumbered unlisted" id="return-value-132">Return Value</h3>
<p>Returns nothing!</p>
<h3 class="unnumbered unlisted" id="example-134">Example</h3>
<p>Using test-and-set to implement a spin lock<a href="footnotes.html#fn251" class="footnote-ref" id="fnref251" role="doc-noteref"><sup>251</sup></a>:</p>
<div class="sourceCode" id="cb1197"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1197-1"><a href="stdatomic.html#cb1197-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1197-2"><a href="stdatomic.html#cb1197-2"></a><span class="pp">#include </span><span class="im">&lt;threads.h&gt;</span></span>
<span id="cb1197-3"><a href="stdatomic.html#cb1197-3"></a><span class="pp">#include </span><span class="im">&lt;stdatomic.h&gt;</span></span>
<span id="cb1197-4"><a href="stdatomic.html#cb1197-4"></a></span>
<span id="cb1197-5"><a href="stdatomic.html#cb1197-5"></a><span class="co">// Shared non-atomic struct</span></span>
<span id="cb1197-6"><a href="stdatomic.html#cb1197-6"></a><span class="kw">struct</span> <span class="op">{</span></span>
<span id="cb1197-7"><a href="stdatomic.html#cb1197-7"></a>    <span class="dt">int</span> x<span class="op">,</span> y<span class="op">,</span> z<span class="op">;</span></span>
<span id="cb1197-8"><a href="stdatomic.html#cb1197-8"></a><span class="op">}</span> s <span class="op">=</span> <span class="op">{</span><span class="dv">1</span><span class="op">,</span> <span class="dv">2</span><span class="op">,</span> <span class="dv">3</span><span class="op">};</span></span>
<span id="cb1197-9"><a href="stdatomic.html#cb1197-9"></a></span>
<span id="cb1197-10"><a href="stdatomic.html#cb1197-10"></a>atomic_flag f <span class="op">=</span> ATOMIC_FLAG_INIT<span class="op">;</span></span>
<span id="cb1197-11"><a href="stdatomic.html#cb1197-11"></a></span>
<span id="cb1197-12"><a href="stdatomic.html#cb1197-12"></a><span class="dt">int</span> run<span class="op">(</span><span class="dt">void</span> <span class="op">*</span>arg<span class="op">)</span></span>
<span id="cb1197-13"><a href="stdatomic.html#cb1197-13"></a><span class="op">{</span></span>
<span id="cb1197-14"><a href="stdatomic.html#cb1197-14"></a>    <span class="dt">int</span> tid <span class="op">=</span> <span class="op">*(</span><span class="dt">int</span><span class="op">*)</span>arg<span class="op">;</span></span>
<span id="cb1197-15"><a href="stdatomic.html#cb1197-15"></a></span>
<span id="cb1197-16"><a href="stdatomic.html#cb1197-16"></a>    printf<span class="op">(</span><span class="st">"Thread %d: waiting for lock...</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">);</span></span>
<span id="cb1197-17"><a href="stdatomic.html#cb1197-17"></a></span>
<span id="cb1197-18"><a href="stdatomic.html#cb1197-18"></a>    <span class="cf">while</span> <span class="op">(</span>atomic_flag_test_and_set<span class="op">(&amp;</span>f<span class="op">));</span></span>
<span id="cb1197-19"><a href="stdatomic.html#cb1197-19"></a></span>
<span id="cb1197-20"><a href="stdatomic.html#cb1197-20"></a>    printf<span class="op">(</span><span class="st">"Thread %d: got lock, s is {%d, %d, %d}</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">,</span></span>
<span id="cb1197-21"><a href="stdatomic.html#cb1197-21"></a>                                                       s<span class="op">.</span>x<span class="op">,</span> s<span class="op">.</span>y<span class="op">,</span> s<span class="op">.</span>z<span class="op">);</span></span>
<span id="cb1197-22"><a href="stdatomic.html#cb1197-22"></a>    s<span class="op">.</span>x <span class="op">=</span> <span class="op">(</span>tid <span class="op">+</span> <span class="dv">1</span><span class="op">)</span> <span class="op">*</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1197-23"><a href="stdatomic.html#cb1197-23"></a>    s<span class="op">.</span>y <span class="op">=</span> <span class="op">(</span>tid <span class="op">+</span> <span class="dv">1</span><span class="op">)</span> <span class="op">*</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">1</span><span class="op">;</span></span>
<span id="cb1197-24"><a href="stdatomic.html#cb1197-24"></a>    s<span class="op">.</span>z <span class="op">=</span> <span class="op">(</span>tid <span class="op">+</span> <span class="dv">1</span><span class="op">)</span> <span class="op">*</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">2</span><span class="op">;</span></span>
<span id="cb1197-25"><a href="stdatomic.html#cb1197-25"></a>    printf<span class="op">(</span><span class="st">"Thread %d: set s to {%d, %d, %d}</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">,</span> s<span class="op">.</span>x<span class="op">,</span> s<span class="op">.</span>y<span class="op">,</span> s<span class="op">.</span>z<span class="op">);</span></span>
<span id="cb1197-26"><a href="stdatomic.html#cb1197-26"></a></span>
<span id="cb1197-27"><a href="stdatomic.html#cb1197-27"></a>    printf<span class="op">(</span><span class="st">"Thread %d: releasing lock...</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tid<span class="op">);</span></span>
<span id="cb1197-28"><a href="stdatomic.html#cb1197-28"></a>    atomic_flag_clear<span class="op">(&amp;</span>f<span class="op">);</span></span>
<span id="cb1197-29"><a href="stdatomic.html#cb1197-29"></a></span>
<span id="cb1197-30"><a href="stdatomic.html#cb1197-30"></a>    <span class="cf">return</span> <span class="dv">0</span><span class="op">;</span></span>
<span id="cb1197-31"><a href="stdatomic.html#cb1197-31"></a><span class="op">}</span></span>
<span id="cb1197-32"><a href="stdatomic.html#cb1197-32"></a></span>
<span id="cb1197-33"><a href="stdatomic.html#cb1197-33"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1197-34"><a href="stdatomic.html#cb1197-34"></a><span class="op">{</span></span>
<span id="cb1197-35"><a href="stdatomic.html#cb1197-35"></a>    thrd_t t1<span class="op">,</span> t2<span class="op">;</span></span>
<span id="cb1197-36"><a href="stdatomic.html#cb1197-36"></a>    <span class="dt">int</span> tid<span class="op">[]</span> <span class="op">=</span> <span class="op">{</span><span class="dv">0</span><span class="op">,</span> <span class="dv">1</span><span class="op">};</span></span>
<span id="cb1197-37"><a href="stdatomic.html#cb1197-37"></a></span>
<span id="cb1197-38"><a href="stdatomic.html#cb1197-38"></a>    thrd_create<span class="op">(&amp;</span>t1<span class="op">,</span> run<span class="op">,</span> tid<span class="op">+</span><span class="dv">0</span><span class="op">);</span></span>
<span id="cb1197-39"><a href="stdatomic.html#cb1197-39"></a>    thrd_create<span class="op">(&amp;</span>t2<span class="op">,</span> run<span class="op">,</span> tid<span class="op">+</span><span class="dv">1</span><span class="op">);</span></span>
<span id="cb1197-40"><a href="stdatomic.html#cb1197-40"></a></span>
<span id="cb1197-41"><a href="stdatomic.html#cb1197-41"></a>    thrd_join<span class="op">(</span>t1<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1197-42"><a href="stdatomic.html#cb1197-42"></a>    thrd_join<span class="op">(</span>t2<span class="op">,</span> NULL<span class="op">);</span></span>
<span id="cb1197-43"><a href="stdatomic.html#cb1197-43"></a><span class="op">}</span></span></code></pre></div>
<p>Example output (varies run to run):</p>
<div class="sourceCode" id="cb1198"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1198-1"><a href="stdatomic.html#cb1198-1" aria-hidden="true" tabindex="-1"></a>Thread 0: waiting for lock...</span>
<span id="cb1198-2"><a href="stdatomic.html#cb1198-2" aria-hidden="true" tabindex="-1"></a>Thread 0: got lock, s is {1, 2, 3}</span>
<span id="cb1198-3"><a href="stdatomic.html#cb1198-3" aria-hidden="true" tabindex="-1"></a>Thread 1: waiting for lock...</span>
<span id="cb1198-4"><a href="stdatomic.html#cb1198-4" aria-hidden="true" tabindex="-1"></a>Thread 0: set s to {5, 6, 7}</span>
<span id="cb1198-5"><a href="stdatomic.html#cb1198-5" aria-hidden="true" tabindex="-1"></a>Thread 0: releasing lock...</span>
<span id="cb1198-6"><a href="stdatomic.html#cb1198-6" aria-hidden="true" tabindex="-1"></a>Thread 1: got lock, s is {5, 6, 7}</span>
<span id="cb1198-7"><a href="stdatomic.html#cb1198-7" aria-hidden="true" tabindex="-1"></a>Thread 1: set s to {10, 11, 12}</span>
<span id="cb1198-8"><a href="stdatomic.html#cb1198-8" aria-hidden="true" tabindex="-1"></a>Thread 1: releasing lock...</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-126">See Also</h3>
<p><a href="#man-atomic_flag_test_and_set"><code>atomic_flag_test_and_set()</code></a></p>


</body>