<body>

<hr>
<h1 data-number="65" id="tgmath"><span class="header-section-number">65</span> <code>&lt;tgmath.h&gt;</code>
Type-Generic Math Functions</h1>
<p>These are type-generic macros that are wrappers around the math
functions in <a href="math.html"><code>&lt;math.h&gt;</code></a> and <a href="#complex"><code>&lt;complex.h&gt;</code></a>. This header includes
both of those.</p>
<p>Deep down, these are implemented using type generics as described in
the <a href="types-part-v-compound-literals-and-generic-selections.html#type-generics">Types Part V chapter</a>.</p>
<p>But on the surface, you can think of them as being able to use, say,
the <code>sqrt()</code> function with any type without needed to think
about if it’s <code>double</code> or <code>long double</code> or even
<code>complex</code>.</p>
<p>These are the defined macros—some of them don’t have a counterpart in
the real or complex space. Type suffixes are omitted in the table on the
Real and Complex columns. None of the generic macros have type
suffixes.</p>
<table>
<thead>
<tr class="header">
<th>Real Function</th>
<th>Complex Function</th>
<th>Generic Macro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>acos</code></td>
<td><code>cacos</code></td>
<td><code>acos</code></td>
</tr>
<tr class="even">
<td><code>asin</code></td>
<td><code>casin</code></td>
<td><code>asin</code></td>
</tr>
<tr class="odd">
<td><code>atan</code></td>
<td><code>catan</code></td>
<td><code>atan</code></td>
</tr>
<tr class="even">
<td><code>acosh</code></td>
<td><code>cacosh</code></td>
<td><code>acosh</code></td>
</tr>
<tr class="odd">
<td><code>asinh</code></td>
<td><code>casinh</code></td>
<td><code>asinh</code></td>
</tr>
<tr class="even">
<td><code>atanh</code></td>
<td><code>catanh</code></td>
<td><code>atanh</code></td>
</tr>
<tr class="odd">
<td><code>cos</code></td>
<td><code>ccos</code></td>
<td><code>cos</code></td>
</tr>
<tr class="even">
<td><code>sin</code></td>
<td><code>csin</code></td>
<td><code>sin</code></td>
</tr>
<tr class="odd">
<td><code>tan</code></td>
<td><code>ctan</code></td>
<td><code>tan</code></td>
</tr>
<tr class="even">
<td><code>cosh</code></td>
<td><code>ccosh</code></td>
<td><code>cosh</code></td>
</tr>
<tr class="odd">
<td><code>sinh</code></td>
<td><code>csinh</code></td>
<td><code>sinh</code></td>
</tr>
<tr class="even">
<td><code>tanh</code></td>
<td><code>ctanh</code></td>
<td><code>tanh</code></td>
</tr>
<tr class="odd">
<td><code>exp</code></td>
<td><code>cexp</code></td>
<td><code>exp</code></td>
</tr>
<tr class="even">
<td><code>log</code></td>
<td><code>clog</code></td>
<td><code>log</code></td>
</tr>
<tr class="odd">
<td><code>pow</code></td>
<td><code>cpow</code></td>
<td><code>pow</code></td>
</tr>
<tr class="even">
<td><code>sqrt</code></td>
<td><code>csqrt</code></td>
<td><code>sqrt</code></td>
</tr>
<tr class="odd">
<td><code>fabs</code></td>
<td><code>cabs</code></td>
<td><code>fabs</code></td>
</tr>
<tr class="even">
<td><code>atan2</code></td>
<td>—</td>
<td><code>atan2</code></td>
</tr>
<tr class="odd">
<td><code>fdim</code></td>
<td>—</td>
<td><code>fdim</code></td>
</tr>
<tr class="even">
<td><code>cbrt</code></td>
<td>—</td>
<td><code>cbrt</code></td>
</tr>
<tr class="odd">
<td><code>floor</code></td>
<td>—</td>
<td><code>floor</code></td>
</tr>
<tr class="even">
<td><code>ceil</code></td>
<td>—</td>
<td><code>ceil</code></td>
</tr>
<tr class="odd">
<td><code>fma</code></td>
<td>—</td>
<td><code>fma</code></td>
</tr>
<tr class="even">
<td><code>copysign</code></td>
<td>—</td>
<td><code>copysign</code></td>
</tr>
<tr class="odd">
<td><code>fmax</code></td>
<td>—</td>
<td><code>fmax</code></td>
</tr>
<tr class="even">
<td><code>erf</code></td>
<td>—</td>
<td><code>erf</code></td>
</tr>
<tr class="odd">
<td><code>fmin</code></td>
<td>—</td>
<td><code>fmin</code></td>
</tr>
<tr class="even">
<td><code>erfc</code></td>
<td>—</td>
<td><code>erfc</code></td>
</tr>
<tr class="odd">
<td><code>fmod</code></td>
<td>—</td>
<td><code>fmod</code></td>
</tr>
<tr class="even">
<td><code>exp2</code></td>
<td>—</td>
<td><code>exp2</code></td>
</tr>
<tr class="odd">
<td><code>frexp</code></td>
<td>—</td>
<td><code>frexp</code></td>
</tr>
<tr class="even">
<td><code>expm1</code></td>
<td>—</td>
<td><code>expm1</code></td>
</tr>
<tr class="odd">
<td><code>hypot</code></td>
<td>—</td>
<td><code>hypot</code></td>
</tr>
<tr class="even">
<td><code>ilogb</code></td>
<td>—</td>
<td><code>ilogb</code></td>
</tr>
<tr class="odd">
<td><code>ldexp</code></td>
<td>—</td>
<td><code>ldexp</code></td>
</tr>
<tr class="even">
<td><code>lgamma</code></td>
<td>—</td>
<td><code>lgamma</code></td>
</tr>
<tr class="odd">
<td><code>llrint</code></td>
<td>—</td>
<td><code>llrint</code></td>
</tr>
<tr class="even">
<td><code>llround</code></td>
<td>—</td>
<td><code>llround</code></td>
</tr>
<tr class="odd">
<td><code>log10</code></td>
<td>—</td>
<td><code>log10</code></td>
</tr>
<tr class="even">
<td><code>log1p</code></td>
<td>—</td>
<td><code>log1p</code></td>
</tr>
<tr class="odd">
<td><code>log2</code></td>
<td>—</td>
<td><code>log2</code></td>
</tr>
<tr class="even">
<td><code>logb</code></td>
<td>—</td>
<td><code>logb</code></td>
</tr>
<tr class="odd">
<td><code>lrint</code></td>
<td>—</td>
<td><code>lrint</code></td>
</tr>
<tr class="even">
<td><code>lround</code></td>
<td>—</td>
<td><code>lround</code></td>
</tr>
<tr class="odd">
<td><code>nearbyint</code></td>
<td>—</td>
<td><code>nearbyint</code></td>
</tr>
<tr class="even">
<td><code>nextafter</code></td>
<td>—</td>
<td><code>nextafter</code></td>
</tr>
<tr class="odd">
<td><code>nexttoward</code></td>
<td>—</td>
<td><code>nexttoward</code></td>
</tr>
<tr class="even">
<td><code>remainder</code></td>
<td>—</td>
<td><code>remainder</code></td>
</tr>
<tr class="odd">
<td><code>remquo</code></td>
<td>—</td>
<td><code>remquo</code></td>
</tr>
<tr class="even">
<td><code>rint</code></td>
<td>—</td>
<td><code>rint</code></td>
</tr>
<tr class="odd">
<td><code>round</code></td>
<td>—</td>
<td><code>round</code></td>
</tr>
<tr class="even">
<td><code>scalbn</code></td>
<td>—</td>
<td><code>scalbn</code></td>
</tr>
<tr class="odd">
<td><code>scalbln</code></td>
<td>—</td>
<td><code>scalbln</code></td>
</tr>
<tr class="even">
<td><code>tgamma</code></td>
<td>—</td>
<td><code>tgamma</code></td>
</tr>
<tr class="odd">
<td><code>trunc</code></td>
<td>—</td>
<td><code>trunc</code></td>
</tr>
<tr class="even">
<td>—</td>
<td><code>carg</code></td>
<td><code>carg</code></td>
</tr>
<tr class="odd">
<td>—</td>
<td><code>cimag</code></td>
<td><code>cimag</code></td>
</tr>
<tr class="even">
<td>—</td>
<td><code>conj</code></td>
<td><code>conj</code></td>
</tr>
<tr class="odd">
<td>—</td>
<td><code>cproj</code></td>
<td><code>cproj</code></td>
</tr>
<tr class="even">
<td>—</td>
<td><code>creal</code></td>
<td><code>creal</code></td>
</tr>
</tbody>
</table>
<h2 data-number="65.1" id="example-199"><span class="header-section-number">65.1</span> Example</h2>
<p>Here’s an example where we call the type-generic <code>sqrt()</code>
function on a variety of types.</p>
<div class="sourceCode" id="cb1408"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1408-1"><a href="tgmath.html#cb1408-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1408-2"><a href="tgmath.html#cb1408-2"></a><span class="pp">#include </span><span class="im">&lt;tgmath.h&gt;</span></span>
<span id="cb1408-3"><a href="tgmath.html#cb1408-3"></a></span>
<span id="cb1408-4"><a href="tgmath.html#cb1408-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1408-5"><a href="tgmath.html#cb1408-5"></a><span class="op">{</span></span>
<span id="cb1408-6"><a href="tgmath.html#cb1408-6"></a>    <span class="dt">double</span> x <span class="op">=</span> <span class="fl">12.8</span><span class="op">;</span></span>
<span id="cb1408-7"><a href="tgmath.html#cb1408-7"></a>    <span class="dt">long</span> <span class="dt">double</span> y <span class="op">=</span> <span class="fl">34.9</span><span class="op">;</span></span>
<span id="cb1408-8"><a href="tgmath.html#cb1408-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> z <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb1408-9"><a href="tgmath.html#cb1408-9"></a></span>
<span id="cb1408-10"><a href="tgmath.html#cb1408-10"></a>    <span class="dt">double</span> x_result<span class="op">;</span></span>
<span id="cb1408-11"><a href="tgmath.html#cb1408-11"></a>    <span class="dt">long</span> <span class="dt">double</span> y_result<span class="op">;</span></span>
<span id="cb1408-12"><a href="tgmath.html#cb1408-12"></a>    <span class="dt">double</span> <span class="dt">complex</span> z_result<span class="op">;</span></span>
<span id="cb1408-13"><a href="tgmath.html#cb1408-13"></a></span>
<span id="cb1408-14"><a href="tgmath.html#cb1408-14"></a>    <span class="co">// We call the same sqrt() function--it's type-generic!</span></span>
<span id="cb1408-15"><a href="tgmath.html#cb1408-15"></a>    x_result <span class="op">=</span> sqrt<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb1408-16"><a href="tgmath.html#cb1408-16"></a>    y_result <span class="op">=</span> sqrt<span class="op">(</span>y<span class="op">);</span></span>
<span id="cb1408-17"><a href="tgmath.html#cb1408-17"></a>    z_result <span class="op">=</span> sqrt<span class="op">(</span>z<span class="op">);</span></span>
<span id="cb1408-18"><a href="tgmath.html#cb1408-18"></a></span>
<span id="cb1408-19"><a href="tgmath.html#cb1408-19"></a>    printf<span class="op">(</span><span class="st">"x_result: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x_result<span class="op">);</span></span>
<span id="cb1408-20"><a href="tgmath.html#cb1408-20"></a>    printf<span class="op">(</span><span class="st">"y_result: %Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> y_result<span class="op">);</span></span>
<span id="cb1408-21"><a href="tgmath.html#cb1408-21"></a>    printf<span class="op">(</span><span class="st">"z_result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>z_result<span class="op">),</span> cimag<span class="op">(</span>z_result<span class="op">));</span></span>
<span id="cb1408-22"><a href="tgmath.html#cb1408-22"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1409"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1409-1"><a href="tgmath.html#cb1409-1" aria-hidden="true" tabindex="-1"></a>x_result: 3.577709</span>
<span id="cb1409-2"><a href="tgmath.html#cb1409-2" aria-hidden="true" tabindex="-1"></a>y_result: 5.907622</span>
<span id="cb1409-3"><a href="tgmath.html#cb1409-3" aria-hidden="true" tabindex="-1"></a>z_result: 1.272020 + 0.786151i</span></code></pre></div>


</body>