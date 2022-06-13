<body>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="assert.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="ctype.html">Next»</a></div>
<hr>
<h1 data-number="43" id="complex"><span class="header-section-number">43</span> <code>&lt;complex.h&gt;</code>
Complex Number Functionality</h1>
<p>The complex functions in this reference section come in three flavors
each: <code>double complex</code>, <code>float complex</code>, and
<code>long double complex</code>.</p>
<p>The <code>float</code> variants end with <code>f</code> and the
<code>long double</code> variants end with <code>l</code>, e.g.&nbsp;for
complex cosine:</p>
<div class="sourceCode" id="cb793"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb793-1"><a href="complex.html#cb793-1" aria-hidden="true" tabindex="-1"></a>ccos<span class="op">()</span>   <span class="dt">double</span> <span class="dt">complex</span></span>
<span id="cb793-2"><a href="complex.html#cb793-2" aria-hidden="true" tabindex="-1"></a>ccosf<span class="op">()</span>  <span class="dt">float</span> <span class="dt">complex</span></span>
<span id="cb793-3"><a href="complex.html#cb793-3" aria-hidden="true" tabindex="-1"></a>ccosl<span class="op">()</span>  <span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span></span></code></pre></div>
<p>The table below only lists the <code>double complex</code> version
for brevity.</p>
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
<td><a href="complex.html#man-cabs"><code>cabs()</code></a></td>
<td>Compute the complex absolute value</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-cacos"><code>cacos()</code></a></td>
<td>Compute the complex arc-cosine</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-cacosh"><code>cacosh()</code></a></td>
<td>Compute the complex arc hyperbolic cosine</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-carg"><code>carg()</code></a></td>
<td>Compute the complex argument</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-casin"><code>casin()</code></a></td>
<td>Compute the complex arc-sine</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-casinh"><code>casinh()</code></a></td>
<td>Compute the complex arc hyperbolic sine</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-catan"><code>catan()</code></a></td>
<td>Compute the complex arc-tangent</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-catanh"><code>catanh()</code></a></td>
<td>Compute the complex arc hyperbolic tangent</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-ccos"><code>ccos()</code></a></td>
<td>Compute the complex cosine</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-ccosh"><code>ccosh()</code></a></td>
<td>Compute the complex hyperbolic cosine</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-cexp"><code>cexp()</code></a></td>
<td>Compute the complex base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span>
exponential</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-cimag"><code>cimag()</code></a></td>
<td>Returns the imaginary part of a complex number</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-clog"><code>clog()</code></a></td>
<td>Compute the complex logarithm</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-CMPLX"><code>CMPLX()</code></a></td>
<td>Build a complex value from real and imaginary types</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-conj"><code>conj()</code></a></td>
<td>Compute the conjugate of a complex number</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-cproj"><code>cproj()</code></a></td>
<td>Compute the projection of a complex number</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-creal"><code>creal()</code></a></td>
<td>Returns the real part of a complex number</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-csin"><code>csin()</code></a></td>
<td>Compute the complex sine</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-csinh"><code>csinh()</code></a></td>
<td>Compute the complex hyperbolic sine</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-csqrt"><code>csqrt()</code></a></td>
<td>Compute the complex square root</td>
</tr>
<tr class="odd">
<td><a href="complex.html#man-ctan"><code>ctan()</code></a></td>
<td>Compute the complex tangent</td>
</tr>
<tr class="even">
<td><a href="complex.html#man-ctanh"><code>ctanh()</code></a></td>
<td>Compute the complex hyperbolic tangent</td>
</tr>
</tbody>
</table>
<p>You can test for complex number support by looking at the
<code>__STDC_NO_COMPLEX__</code> macro. If it’s defined, complex numbers
aren’t available.</p>
<p>There are possibly two types of numbers defined: <em>complex</em> and
<em>imaginary</em>. No system I’m currently aware of implements
imaginary types.</p>
<p>The complex types, which are a real value plus a multiple of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></mjx-assistive-mml></mjx-container></span>, are:</p>
<div class="sourceCode" id="cb794"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb794-1"><a href="complex.html#cb794-1" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span></span>
<span id="cb794-2"><a href="complex.html#cb794-2" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span></span>
<span id="cb794-3"><a href="complex.html#cb794-3" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span></span></code></pre></div>
<p>The imaginary types, which hold a multiple of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></mjx-assistive-mml></mjx-container></span>, are:</p>
<div class="sourceCode" id="cb795"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb795-1"><a href="complex.html#cb795-1" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">imaginary</span></span>
<span id="cb795-2"><a href="complex.html#cb795-2" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">imaginary</span></span>
<span id="cb795-3"><a href="complex.html#cb795-3" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">imaginary</span></span></code></pre></div>
<p>The mathematical value <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-msqrt space="4"><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.134em;"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-box></mjx-sqrt></mjx-msqrt></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi><mo>=</mo><msqrt><mo>−</mo><mn>1</mn></msqrt></math></mjx-assistive-mml></mjx-container></span> is represented by the symbol
<code>_Complex_I</code> or <code>_Imaginary_I</code>, if it exists.</p>
<p>The The macro <code>I</code> will be preferentially set to
<code>_Imaginary_I</code> (if it exists), or to <code>_Complex_I</code>
otherwise.</p>
<p>You can write imaginary literals (if supported) using this
notation:</p>
<div class="sourceCode" id="cb796"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb796-1"><a href="complex.html#cb796-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">imaginary</span> x <span class="op">=</span> <span class="fl">3.4</span> <span class="op">*</span> I<span class="op">;</span></span></code></pre></div>
<p>You can write complex literals using regular complex notation:</p>
<div class="sourceCode" id="cb797"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb797-1"><a href="complex.html#cb797-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="fl">1.2</span> <span class="op">+</span> <span class="fl">3.4</span> <span class="op">*</span> I<span class="op">;</span></span></code></pre></div>
<p>or build them with the <code>CMPLX()</code> macro:</p>
<div class="sourceCode" id="cb798"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb798-1"><a href="complex.html#cb798-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> CMPLX<span class="op">(</span><span class="fl">1.2</span><span class="op">,</span> <span class="fl">3.4</span><span class="op">);</span>  <span class="co">// Like 1.2 + 3.4 * I</span></span></code></pre></div>
<p>The latter has the advantage of handing special cases of complex
numbers correctly (like those involving infinity or signed zeroes) as if
<code>_Imaginary_I</code> were present, even if it’s not.</p>
<p>All angular values are in radians.</p>
<p>Some functions have discontinuities called <em>branch cuts</em>. Now,
I’m no mathematician so I can’t really talk sensibly about this, but if
you’re here, I like to think you know what you’re doing when it comes to
this side of things.</p>
<p>If you system has signed zeroes, you can tell which side of the cut
you’re on by the sign. And you can’t if you don’t. The spec
elaborates:</p>
<blockquote>
<p>Implementations that do not support a signed zero […] cannot
distinguish the sides of branch cuts. These implementations shall map a
cut so the function is continuous as the cut is approached coming around
the finite endpoint of the cut in a counter clockwise direction. (Branch
cuts for the functions specified here have just one finite endpoint.)
For example, for the square root function, coming counter clockwise
around the finite endpoint of the cut along the negative real axis
approaches the cut from above, so the cut maps to the positive imaginary
axis.</p>
</blockquote>
<p>Finally, there’s a pragma called <code>CX_LIMITED_RANGE</code> that
can be turned on and off (default is off). You can turn it on with:</p>
<div class="sourceCode" id="cb799"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb799-1"><a href="complex.html#cb799-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#pragma STDC CX_LIMITED_RANGE ON</span></span></code></pre></div>
<p>It allows for certain intermediate operations to underflow, overflow,
or deal badly with infinity, presumably for a tradeoff in speed. If
you’re sure these types of errors won’t occur with the numbers you’re
using AND you’re trying to get as much speed out as you can, you could
turn this macro on.</p>
<p>The spec also elaborates here:</p>
<blockquote>
<p>The purpose of the pragma is to allow the implementation to use the
formulas:</p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D462 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D463 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D462 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D463 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D462 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D463 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">(</mo><mi>x</mi><mo>+</mo><mi>i</mi><mi>y</mi><mo stretchy="false">)</mo><mo>×</mo><mo stretchy="false">(</mo><mi>u</mi><mo>+</mo><mi>i</mi><mi>v</mi><mo stretchy="false">)</mo><mo>=</mo><mo stretchy="false">(</mo><mi>x</mi><mi>u</mi><mo>−</mo><mi>y</mi><mi>v</mi><mo stretchy="false">)</mo><mo>+</mo><mi>i</mi><mo stretchy="false">(</mo><mi>y</mi><mi>u</mi><mo>+</mo><mi>x</mi><mi>v</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span></p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D462 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D463 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D462 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D463 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D462 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D463 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D462 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D463 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">(</mo><mi>x</mi><mo>+</mo><mi>i</mi><mi>y</mi><mo stretchy="false">)</mo><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mo stretchy="false">(</mo><mi>u</mi><mo>+</mo><mi>i</mi><mi>v</mi><mo stretchy="false">)</mo><mo>=</mo><mo stretchy="false">[</mo><mo stretchy="false">(</mo><mi>x</mi><mi>u</mi><mo>+</mo><mi>y</mi><mi>v</mi><mo stretchy="false">)</mo><mo>+</mo><mi>i</mi><mo stretchy="false">(</mo><mi>y</mi><mi>u</mi><mo>−</mo><mi>x</mi><mi>v</mi><mo stretchy="false">)</mo><mo stretchy="false">]</mo><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mo stretchy="false">(</mo><msup><mi>u</mi><mn>2</mn></msup><mo>+</mo><msup><mi>v</mi><mn>2</mn></msup><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span></p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-msqrt space="4"><mjx-sqrt><mjx-surd><mjx-mo class="mjx-sop"><mjx-c class="mjx-c221A TEX-S1"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.125em;"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.289em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.289em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup></mjx-box></mjx-sqrt></mjx-msqrt></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>x</mi><mo>+</mo><mi>i</mi><mi>y</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mo>=</mo><msqrt><msup><mi>x</mi><mn>2</mn></msup><mo>+</mo><msup><mi>y</mi><mn>2</mn></msup></msqrt></math></mjx-assistive-mml></mjx-container></span></p>
<p>where the programmer can determine they are safe.</p>
</blockquote>
<hr>
<h2 data-number="43.1" id="man-cacos"><span class="header-section-number">43.1</span> <code>cacos()</code>
<code>cacosf()</code> <code>cacosl()</code></h2>
<p>Compute the complex arc-cosine</p>
<h3 class="unnumbered unlisted" id="synopsis-2">Synopsis</h3>
<div class="sourceCode" id="cb800"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb800-1"><a href="complex.html#cb800-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb800-2"><a href="complex.html#cb800-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb800-3"><a href="complex.html#cb800-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> cacos<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb800-4"><a href="complex.html#cb800-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb800-5"><a href="complex.html#cb800-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> cacosf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb800-6"><a href="complex.html#cb800-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb800-7"><a href="complex.html#cb800-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> cacosl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-2">Description</h3>
<p>Computes the complex arc-cosine of a complex number.</p>
<p>The complex number <code>z</code> will have an imaginary component in
the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>0</mn><mo>,</mo><mi>π</mi><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span>, and the real
component is unbounded.</p>
<p>There are branch cuts outside the interval <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mn>1</mn><mo>,</mo><mo>+</mo><mn>1</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the real axis.</p>
<h3 class="unnumbered unlisted" id="return-value-2">Return Value</h3>
<p>Returns the complex arc-cosine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-2">Example</h3>
<div class="sourceCode" id="cb801"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb801-1"><a href="complex.html#cb801-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb801-2"><a href="complex.html#cb801-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb801-3"><a href="complex.html#cb801-3"></a></span>
<span id="cb801-4"><a href="complex.html#cb801-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb801-5"><a href="complex.html#cb801-5"></a><span class="op">{</span></span>
<span id="cb801-6"><a href="complex.html#cb801-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb801-7"><a href="complex.html#cb801-7"></a></span>
<span id="cb801-8"><a href="complex.html#cb801-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> cacos<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb801-9"><a href="complex.html#cb801-9"></a></span>
<span id="cb801-10"><a href="complex.html#cb801-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb801-11"><a href="complex.html#cb801-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb802"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb802-1"><a href="complex.html#cb802-1" aria-hidden="true" tabindex="-1"></a>Result: 0.195321 + -2.788006i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-2">See Also</h3>
<p><a href="complex.html#man-ccos"><code>ccos()</code></a>, <a href="#man-casin"><code>casin()</code></a>, <a href="#man-catan"><code>catan()</code></a></p>
<hr>
<h2 data-number="43.2" id="man-casin"><span class="header-section-number">43.2</span> <code>casin()</code>
<code>casinf()</code> <code>casinl()</code></h2>
<p>Compute the complex arc-sine</p>
<h3 class="unnumbered unlisted" id="synopsis-3">Synopsis</h3>
<div class="sourceCode" id="cb803"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb803-1"><a href="complex.html#cb803-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb803-2"><a href="complex.html#cb803-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb803-3"><a href="complex.html#cb803-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> casin<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb803-4"><a href="complex.html#cb803-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb803-5"><a href="complex.html#cb803-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> casinf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb803-6"><a href="complex.html#cb803-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb803-7"><a href="complex.html#cb803-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> casinl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-3">Description</h3>
<p>Computes the complex arc-sine of a complex number.</p>
<p>The complex number <code>z</code> will have an imaginary component in
the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo>,</mo><mo>+</mo><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span>, and the
real component is unbounded.</p>
<p>There are branch cuts outside the interval <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mn>1</mn><mo>,</mo><mo>+</mo><mn>1</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the real axis.</p>
<h3 class="unnumbered unlisted" id="return-value-3">Return Value</h3>
<p>Returns the complex arc-sine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-3">Example</h3>
<div class="sourceCode" id="cb804"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb804-1"><a href="complex.html#cb804-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb804-2"><a href="complex.html#cb804-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb804-3"><a href="complex.html#cb804-3"></a></span>
<span id="cb804-4"><a href="complex.html#cb804-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb804-5"><a href="complex.html#cb804-5"></a><span class="op">{</span></span>
<span id="cb804-6"><a href="complex.html#cb804-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb804-7"><a href="complex.html#cb804-7"></a></span>
<span id="cb804-8"><a href="complex.html#cb804-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> casin<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb804-9"><a href="complex.html#cb804-9"></a></span>
<span id="cb804-10"><a href="complex.html#cb804-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb804-11"><a href="complex.html#cb804-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb805"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb805-1"><a href="complex.html#cb805-1" aria-hidden="true" tabindex="-1"></a>Result: 1.375476 + 2.788006i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-3">See Also</h3>
<p><a href="complex.html#man-csin"><code>csin()</code></a>, <a href="#man-cacos"><code>cacos()</code></a>, <a href="#man-catan"><code>catan()</code></a></p>
<hr>
<h2 data-number="43.3" id="man-catan"><span class="header-section-number">43.3</span> <code>catan()</code>
<code>catanf()</code> <code>catanl()</code></h2>
<p>Compute the complex arc-tangent</p>
<h3 class="unnumbered unlisted" id="synopsis-4">Synopsis</h3>
<div class="sourceCode" id="cb806"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb806-1"><a href="complex.html#cb806-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb806-2"><a href="complex.html#cb806-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb806-3"><a href="complex.html#cb806-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> catan<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb806-4"><a href="complex.html#cb806-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb806-5"><a href="complex.html#cb806-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> catanf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb806-6"><a href="complex.html#cb806-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb806-7"><a href="complex.html#cb806-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> catanl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-4">Description</h3>
<p>Computes the complex arc-tangent of a complex number.</p>
<p>The complex number <code>z</code> will have an real component in the
range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo>,</mo><mo>+</mo><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span>, and the
imaginary component is unbounded.</p>
<p>There are branch cuts outside the interval <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="12" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>i</mi><mo>,</mo><mo>+</mo><mi>i</mi><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the imaginary axis.</p>
<h3 class="unnumbered unlisted" id="return-value-4">Return Value</h3>
<p>Returns the complex arc-tangent of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-4">Example</h3>
<div class="sourceCode" id="cb807"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb807-1"><a href="complex.html#cb807-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb807-2"><a href="complex.html#cb807-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb807-3"><a href="complex.html#cb807-3"></a></span>
<span id="cb807-4"><a href="complex.html#cb807-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb807-5"><a href="complex.html#cb807-5"></a><span class="op">{</span></span>
<span id="cb807-6"><a href="complex.html#cb807-6"></a>    <span class="dt">double</span> wheat <span class="op">=</span> <span class="dv">8</span><span class="op">;</span></span>
<span id="cb807-7"><a href="complex.html#cb807-7"></a>    <span class="dt">double</span> sheep <span class="op">=</span> <span class="fl">1.5708</span><span class="op">;</span></span>
<span id="cb807-8"><a href="complex.html#cb807-8"></a></span>
<span id="cb807-9"><a href="complex.html#cb807-9"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> wheat <span class="op">+</span> sheep <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb807-10"><a href="complex.html#cb807-10"></a></span>
<span id="cb807-11"><a href="complex.html#cb807-11"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> catan<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb807-12"><a href="complex.html#cb807-12"></a></span>
<span id="cb807-13"><a href="complex.html#cb807-13"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb807-14"><a href="complex.html#cb807-14"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb808"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb808-1"><a href="complex.html#cb808-1" aria-hidden="true" tabindex="-1"></a>Result: 1.450947 + 0.023299i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-4">See Also</h3>
<p><a href="complex.html#man-ctan"><code>ctan()</code></a>, <a href="#man-cacos"><code>cacos()</code></a>, <a href="#man-casin"><code>casin()</code></a></p>
<hr>
<h2 data-number="43.4" id="man-ccos"><span class="header-section-number">43.4</span> <code>ccos()</code>
<code>ccosf()</code> <code>ccosl()</code></h2>
<p>Compute the complex cosine</p>
<h3 class="unnumbered unlisted" id="synopsis-5">Synopsis</h3>
<div class="sourceCode" id="cb809"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb809-1"><a href="complex.html#cb809-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb809-2"><a href="complex.html#cb809-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb809-3"><a href="complex.html#cb809-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> ccos<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb809-4"><a href="complex.html#cb809-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb809-5"><a href="complex.html#cb809-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> ccosf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb809-6"><a href="complex.html#cb809-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb809-7"><a href="complex.html#cb809-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> ccosl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-5">Description</h3>
<p>Computes the complex cosine of a complex number.</p>
<h3 class="unnumbered unlisted" id="return-value-5">Return Value</h3>
<p>Returns the complex cosine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-5">Example</h3>
<div class="sourceCode" id="cb810"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb810-1"><a href="complex.html#cb810-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb810-2"><a href="complex.html#cb810-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb810-3"><a href="complex.html#cb810-3"></a></span>
<span id="cb810-4"><a href="complex.html#cb810-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb810-5"><a href="complex.html#cb810-5"></a><span class="op">{</span></span>
<span id="cb810-6"><a href="complex.html#cb810-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb810-7"><a href="complex.html#cb810-7"></a></span>
<span id="cb810-8"><a href="complex.html#cb810-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> ccos<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb810-9"><a href="complex.html#cb810-9"></a></span>
<span id="cb810-10"><a href="complex.html#cb810-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb810-11"><a href="complex.html#cb810-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb811"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb811-1"><a href="complex.html#cb811-1" aria-hidden="true" tabindex="-1"></a>Result: -0.365087 + -2.276818i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-5">See Also</h3>
<p><a href="complex.html#man-csin"><code>csin()</code></a>, <a href="#man-ctan"><code>ctan()</code></a>, <a href="#man-cacos"><code>cacos()</code></a></p>
<hr>
<h2 data-number="43.5" id="man-csin"><span class="header-section-number">43.5</span> <code>csin()</code>
<code>csinf()</code> <code>csinl()</code></h2>
<p>Compute the complex sine</p>
<h3 class="unnumbered unlisted" id="synopsis-6">Synopsis</h3>
<div class="sourceCode" id="cb812"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb812-1"><a href="complex.html#cb812-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb812-2"><a href="complex.html#cb812-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb812-3"><a href="complex.html#cb812-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> csin<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb812-4"><a href="complex.html#cb812-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb812-5"><a href="complex.html#cb812-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> csinf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb812-6"><a href="complex.html#cb812-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb812-7"><a href="complex.html#cb812-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> csinl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-6">Description</h3>
<p>Computes the complex sine of a complex number.</p>
<h3 class="unnumbered unlisted" id="return-value-6">Return Value</h3>
<p>Returns the complex sine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-6">Example</h3>
<div class="sourceCode" id="cb813"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb813-1"><a href="complex.html#cb813-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb813-2"><a href="complex.html#cb813-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb813-3"><a href="complex.html#cb813-3"></a></span>
<span id="cb813-4"><a href="complex.html#cb813-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb813-5"><a href="complex.html#cb813-5"></a><span class="op">{</span></span>
<span id="cb813-6"><a href="complex.html#cb813-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb813-7"><a href="complex.html#cb813-7"></a></span>
<span id="cb813-8"><a href="complex.html#cb813-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> csin<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb813-9"><a href="complex.html#cb813-9"></a></span>
<span id="cb813-10"><a href="complex.html#cb813-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb813-11"><a href="complex.html#cb813-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb814"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb814-1"><a href="complex.html#cb814-1" aria-hidden="true" tabindex="-1"></a>Result: 2.482485 + -0.334840i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-6">See Also</h3>
<p><a href="complex.html#man-ccos"><code>ccos()</code></a>, <a href="#man-ctan"><code>ctan()</code></a>, <a href="#man-casin"><code>casin()</code></a></p>
<hr>
<h2 data-number="43.6" id="man-ctan"><span class="header-section-number">43.6</span> <code>ctan()</code>
<code>ctanf()</code> <code>ctanl()</code></h2>
<p>Compute the complex tangent</p>
<h3 class="unnumbered unlisted" id="synopsis-7">Synopsis</h3>
<div class="sourceCode" id="cb815"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb815-1"><a href="complex.html#cb815-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb815-2"><a href="complex.html#cb815-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb815-3"><a href="complex.html#cb815-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> ctan<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb815-4"><a href="complex.html#cb815-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb815-5"><a href="complex.html#cb815-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> ctanf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb815-6"><a href="complex.html#cb815-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb815-7"><a href="complex.html#cb815-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> ctanl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-7">Description</h3>
<p>Computes the complex tangent of a complex number.</p>
<h3 class="unnumbered unlisted" id="return-value-7">Return Value</h3>
<p>Returns the complex tangent of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-7">Example</h3>
<div class="sourceCode" id="cb816"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb816-1"><a href="complex.html#cb816-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb816-2"><a href="complex.html#cb816-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb816-3"><a href="complex.html#cb816-3"></a></span>
<span id="cb816-4"><a href="complex.html#cb816-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb816-5"><a href="complex.html#cb816-5"></a><span class="op">{</span></span>
<span id="cb816-6"><a href="complex.html#cb816-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb816-7"><a href="complex.html#cb816-7"></a></span>
<span id="cb816-8"><a href="complex.html#cb816-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> ctan<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb816-9"><a href="complex.html#cb816-9"></a></span>
<span id="cb816-10"><a href="complex.html#cb816-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb816-11"><a href="complex.html#cb816-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb817"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb817-1"><a href="complex.html#cb817-1" aria-hidden="true" tabindex="-1"></a>Result: -0.027073 + 1.085990i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-7">See Also</h3>
<p><a href="complex.html#man-ccos"><code>ccos()</code></a>, <a href="#man-csin"><code>csin()</code></a>, <a href="#man-catan"><code>catan()</code></a></p>
<hr>
<h2 data-number="43.7" id="man-cacosh"><span class="header-section-number">43.7</span> <code>cacosh()</code>
<code>cacoshf()</code> <code>cacoshl()</code></h2>
<p>Compute the complex arc hyperbolic cosine</p>
<h3 class="unnumbered unlisted" id="synopsis-8">Synopsis</h3>
<div class="sourceCode" id="cb818"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb818-1"><a href="complex.html#cb818-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb818-2"><a href="complex.html#cb818-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb818-3"><a href="complex.html#cb818-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> cacosh<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb818-4"><a href="complex.html#cb818-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb818-5"><a href="complex.html#cb818-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> cacoshf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb818-6"><a href="complex.html#cb818-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb818-7"><a href="complex.html#cb818-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> cacoshl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-8">Description</h3>
<p>Computes the complex arc hyperbolic cosine of a complex number.</p>
<p>There is a branch cut at values less than <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="13" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> on the real axis.</p>
<p>The return value will be non-negative on the real number axis, and in
the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="14" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>i</mi><mi>π</mi><mo>,</mo><mo>+</mo><mi>i</mi><mi>π</mi><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the
imaginary axis.</p>
<h3 class="unnumbered unlisted" id="return-value-8">Return Value</h3>
<p>Returns the complex arc hyperbolic cosine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-8">Example</h3>
<div class="sourceCode" id="cb819"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb819-1"><a href="complex.html#cb819-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb819-2"><a href="complex.html#cb819-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb819-3"><a href="complex.html#cb819-3"></a></span>
<span id="cb819-4"><a href="complex.html#cb819-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb819-5"><a href="complex.html#cb819-5"></a><span class="op">{</span></span>
<span id="cb819-6"><a href="complex.html#cb819-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb819-7"><a href="complex.html#cb819-7"></a></span>
<span id="cb819-8"><a href="complex.html#cb819-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> cacosh<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb819-9"><a href="complex.html#cb819-9"></a></span>
<span id="cb819-10"><a href="complex.html#cb819-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb819-11"><a href="complex.html#cb819-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb820"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb820-1"><a href="complex.html#cb820-1" aria-hidden="true" tabindex="-1"></a>Result: 2.788006 + 0.195321i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-8">See Also</h3>
<p><a href="complex.html#man-casinh"><code>casinh()</code></a>, <a href="#man-catanh"><code>catanh()</code></a>, <a href="#man-acosh"><code>acosh()</code></a></p>
<hr>
<h2 data-number="43.8" id="man-casinh"><span class="header-section-number">43.8</span> <code>casinh()</code>
<code>casinhf()</code> <code>casinhl()</code></h2>
<p>Compute the complex arc hyperbolic sine</p>
<h3 class="unnumbered unlisted" id="synopsis-9">Synopsis</h3>
<div class="sourceCode" id="cb821"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb821-1"><a href="complex.html#cb821-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb821-2"><a href="complex.html#cb821-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb821-3"><a href="complex.html#cb821-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> casinh<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb821-4"><a href="complex.html#cb821-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb821-5"><a href="complex.html#cb821-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> casinhf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb821-6"><a href="complex.html#cb821-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb821-7"><a href="complex.html#cb821-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> casinhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-9">Description</h3>
<p>Computes the complex arc hyperbolic sine of a complex number.</p>
<p>There are branch cuts outside <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="15" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>i</mi><mo>,</mo><mo>+</mo><mi>i</mi><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the imaginary axis.</p>
<p>The return value will be unbounded on the real number axis, and in
the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="16" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>i</mi><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo>,</mo><mo>+</mo><mi>i</mi><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the
imaginary axis.</p>
<h3 class="unnumbered unlisted" id="return-value-9">Return Value</h3>
<p>Returns the complex arc hyperbolic sine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-9">Example</h3>
<div class="sourceCode" id="cb822"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb822-1"><a href="complex.html#cb822-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb822-2"><a href="complex.html#cb822-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb822-3"><a href="complex.html#cb822-3"></a></span>
<span id="cb822-4"><a href="complex.html#cb822-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb822-5"><a href="complex.html#cb822-5"></a><span class="op">{</span></span>
<span id="cb822-6"><a href="complex.html#cb822-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb822-7"><a href="complex.html#cb822-7"></a></span>
<span id="cb822-8"><a href="complex.html#cb822-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> casinh<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb822-9"><a href="complex.html#cb822-9"></a></span>
<span id="cb822-10"><a href="complex.html#cb822-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb822-11"><a href="complex.html#cb822-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb823"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb823-1"><a href="complex.html#cb823-1" aria-hidden="true" tabindex="-1"></a>Result: 2.794970 + 0.192476i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-9">See Also</h3>
<p><a href="complex.html#man-cacosh"><code>cacosh()</code></a>, <a href="#man-catanh"><code>catanh()</code></a>, <a href="#man-asinh"><code>asinh()</code></a></p>
<hr>
<h2 data-number="43.9" id="man-catanh"><span class="header-section-number">43.9</span> <code>catanh()</code>
<code>catanhf()</code> <code>catanhl()</code></h2>
<p>Compute the complex arc hyperbolic tangent</p>
<h3 class="unnumbered unlisted" id="synopsis-10">Synopsis</h3>
<div class="sourceCode" id="cb824"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb824-1"><a href="complex.html#cb824-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb824-2"><a href="complex.html#cb824-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb824-3"><a href="complex.html#cb824-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> catanh<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb824-4"><a href="complex.html#cb824-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb824-5"><a href="complex.html#cb824-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> catanhf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb824-6"><a href="complex.html#cb824-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb824-7"><a href="complex.html#cb824-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> catanhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-10">Description</h3>
<p>Computes the complex arc hyperbolic tangent of a complex number.</p>
<p>There are branch cuts outside <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="17" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mn>1</mn><mo>,</mo><mo>+</mo><mn>1</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the real axis.</p>
<p>The return value will be unbounded on the real number axis, and in
the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="18" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>i</mi><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo>,</mo><mo>+</mo><mi>i</mi><mi>π</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the
imaginary axis.</p>
<h3 class="unnumbered unlisted" id="return-value-10">Return Value</h3>
<p>Returns the complex arc hyperbolic tangent of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-10">Example</h3>
<div class="sourceCode" id="cb825"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb825-1"><a href="complex.html#cb825-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb825-2"><a href="complex.html#cb825-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb825-3"><a href="complex.html#cb825-3"></a></span>
<span id="cb825-4"><a href="complex.html#cb825-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb825-5"><a href="complex.html#cb825-5"></a><span class="op">{</span></span>
<span id="cb825-6"><a href="complex.html#cb825-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb825-7"><a href="complex.html#cb825-7"></a></span>
<span id="cb825-8"><a href="complex.html#cb825-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> catanh<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb825-9"><a href="complex.html#cb825-9"></a></span>
<span id="cb825-10"><a href="complex.html#cb825-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb825-11"><a href="complex.html#cb825-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb826"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb826-1"><a href="complex.html#cb826-1" aria-hidden="true" tabindex="-1"></a>Result: 0.120877 + 1.546821i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-10">See Also</h3>
<p><a href="complex.html#man-cacosh"><code>cacosh()</code></a>, <a href="#man-casinh"><code>casinh()</code></a>, <a href="#man-atanh"><code>atanh()</code></a></p>
<hr>
<h2 data-number="43.10" id="man-ccosh"><span class="header-section-number">43.10</span> <code>ccosh()</code>
<code>ccoshf()</code> <code>ccoshl()</code></h2>
<p>Compute the complex hyperbolic cosine</p>
<h3 class="unnumbered unlisted" id="synopsis-11">Synopsis</h3>
<div class="sourceCode" id="cb827"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb827-1"><a href="complex.html#cb827-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb827-2"><a href="complex.html#cb827-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb827-3"><a href="complex.html#cb827-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> ccosh<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb827-4"><a href="complex.html#cb827-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb827-5"><a href="complex.html#cb827-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> ccoshf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb827-6"><a href="complex.html#cb827-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb827-7"><a href="complex.html#cb827-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> ccoshl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-11">Description</h3>
<p>Computes the complex hyperbolic cosine of a complex number.</p>
<h3 class="unnumbered unlisted" id="return-value-11">Return Value</h3>
<p>Returns the complex hyperbolic cosine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-11">Example</h3>
<div class="sourceCode" id="cb828"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb828-1"><a href="complex.html#cb828-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb828-2"><a href="complex.html#cb828-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb828-3"><a href="complex.html#cb828-3"></a></span>
<span id="cb828-4"><a href="complex.html#cb828-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb828-5"><a href="complex.html#cb828-5"></a><span class="op">{</span></span>
<span id="cb828-6"><a href="complex.html#cb828-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb828-7"><a href="complex.html#cb828-7"></a></span>
<span id="cb828-8"><a href="complex.html#cb828-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> ccosh<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb828-9"><a href="complex.html#cb828-9"></a></span>
<span id="cb828-10"><a href="complex.html#cb828-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb828-11"><a href="complex.html#cb828-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb829"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb829-1"><a href="complex.html#cb829-1" aria-hidden="true" tabindex="-1"></a>Result: -0.005475 + 1490.478826i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-11">See Also</h3>
<p><a href="complex.html#man-csinh"><code>csinh()</code></a>, <a href="#man-ctanh"><code>ctanh()</code></a>, <a href="#man-ccos"><code>ccos()</code></a></p>
<hr>
<h2 data-number="43.11" id="man-csinh"><span class="header-section-number">43.11</span> <code>csinh()</code>
<code>csinhf()</code> <code>csinhl()</code></h2>
<p>Compute the complex hyperbolic sine</p>
<h3 class="unnumbered unlisted" id="synopsis-12">Synopsis</h3>
<div class="sourceCode" id="cb830"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb830-1"><a href="complex.html#cb830-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb830-2"><a href="complex.html#cb830-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb830-3"><a href="complex.html#cb830-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> csinh<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb830-4"><a href="complex.html#cb830-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb830-5"><a href="complex.html#cb830-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> csinhf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb830-6"><a href="complex.html#cb830-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb830-7"><a href="complex.html#cb830-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> csinhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-12">Description</h3>
<p>Computes the complex hyperbolic sine of a complex number.</p>
<h3 class="unnumbered unlisted" id="return-value-12">Return Value</h3>
<p>Returns the complex hyperbolic sine of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-12">Example</h3>
<div class="sourceCode" id="cb831"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb831-1"><a href="complex.html#cb831-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb831-2"><a href="complex.html#cb831-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb831-3"><a href="complex.html#cb831-3"></a></span>
<span id="cb831-4"><a href="complex.html#cb831-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb831-5"><a href="complex.html#cb831-5"></a><span class="op">{</span></span>
<span id="cb831-6"><a href="complex.html#cb831-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb831-7"><a href="complex.html#cb831-7"></a></span>
<span id="cb831-8"><a href="complex.html#cb831-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> csinh<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb831-9"><a href="complex.html#cb831-9"></a></span>
<span id="cb831-10"><a href="complex.html#cb831-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb831-11"><a href="complex.html#cb831-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb832"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb832-1"><a href="complex.html#cb832-1" aria-hidden="true" tabindex="-1"></a>Result: -0.005475 + 1490.479161i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-12">See Also</h3>
<p><a href="complex.html#man-ccosh"><code>ccosh()</code></a>, <a href="#man-ctanh"><code>ctanh()</code></a>, <a href="#man-csin"><code>csin()</code></a></p>
<hr>
<h2 data-number="43.12" id="man-ctanh"><span class="header-section-number">43.12</span> <code>ctanh()</code>
<code>ctanhf()</code> <code>ctanhl()</code></h2>
<p>Compute the complex hyperbolic tangent</p>
<h3 class="unnumbered unlisted" id="synopsis-13">Synopsis</h3>
<div class="sourceCode" id="cb833"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb833-1"><a href="complex.html#cb833-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb833-2"><a href="complex.html#cb833-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb833-3"><a href="complex.html#cb833-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> ctanh<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb833-4"><a href="complex.html#cb833-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb833-5"><a href="complex.html#cb833-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> ctanhf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb833-6"><a href="complex.html#cb833-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb833-7"><a href="complex.html#cb833-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> ctanhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-13">Description</h3>
<p>Computes the complex hyperbolic tangent of a complex number.</p>
<h3 class="unnumbered unlisted" id="return-value-13">Return Value</h3>
<p>Returns the complex hyperbolic tangent of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-13">Example</h3>
<div class="sourceCode" id="cb834"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb834-1"><a href="complex.html#cb834-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb834-2"><a href="complex.html#cb834-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb834-3"><a href="complex.html#cb834-3"></a></span>
<span id="cb834-4"><a href="complex.html#cb834-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb834-5"><a href="complex.html#cb834-5"></a><span class="op">{</span></span>
<span id="cb834-6"><a href="complex.html#cb834-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">8</span> <span class="op">+</span> <span class="fl">1.5708</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb834-7"><a href="complex.html#cb834-7"></a></span>
<span id="cb834-8"><a href="complex.html#cb834-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> ctanh<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb834-9"><a href="complex.html#cb834-9"></a></span>
<span id="cb834-10"><a href="complex.html#cb834-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb834-11"><a href="complex.html#cb834-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb835"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb835-1"><a href="complex.html#cb835-1" aria-hidden="true" tabindex="-1"></a>Result: 1.000000 + -0.000000i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-13">See Also</h3>
<p><a href="complex.html#man-ccosh"><code>ccosh()</code></a>, <a href="#man-csinh"><code>csinh()</code></a>, <a href="#man-ctan"><code>ctan()</code></a></p>
<hr>
<h2 data-number="43.13" id="man-cexp"><span class="header-section-number">43.13</span> <code>cexp()</code>
<code>cexpf()</code> <code>cexpl()</code></h2>
<p>Compute the complex base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="19" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span>
exponential</p>
<h3 class="unnumbered unlisted" id="synopsis-14">Synopsis</h3>
<div class="sourceCode" id="cb836"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb836-1"><a href="complex.html#cb836-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb836-2"><a href="complex.html#cb836-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb836-3"><a href="complex.html#cb836-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> cexp<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb836-4"><a href="complex.html#cb836-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb836-5"><a href="complex.html#cb836-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> cexpf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb836-6"><a href="complex.html#cb836-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb836-7"><a href="complex.html#cb836-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> cexpl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-14">Description</h3>
<p>Computes the complex base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="20" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span>
exponential of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-14">Return Value</h3>
<p>Returns the complex base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="21" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span>
exponential of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-14">Example</h3>
<div class="sourceCode" id="cb837"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb837-1"><a href="complex.html#cb837-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb837-2"><a href="complex.html#cb837-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb837-3"><a href="complex.html#cb837-3"></a></span>
<span id="cb837-4"><a href="complex.html#cb837-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb837-5"><a href="complex.html#cb837-5"></a><span class="op">{</span></span>
<span id="cb837-6"><a href="complex.html#cb837-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb837-7"><a href="complex.html#cb837-7"></a></span>
<span id="cb837-8"><a href="complex.html#cb837-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> cexp<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb837-9"><a href="complex.html#cb837-9"></a></span>
<span id="cb837-10"><a href="complex.html#cb837-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb837-11"><a href="complex.html#cb837-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb838"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb838-1"><a href="complex.html#cb838-1" aria-hidden="true" tabindex="-1"></a>Result: -1.131204 + 2.471727i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-14">See Also</h3>
<p><a href="complex.html#man-cpow"><code>cpow()</code></a>, <a href="#man-clog"><code>clog()</code></a>, <a href="#man-exp"><code>exp()</code></a></p>
<hr>
<h2 data-number="43.14" id="man-clog"><span class="header-section-number">43.14</span> <code>clog()</code>
<code>clogf()</code> <code>clogl()</code></h2>
<p>Compute the complex logarithm</p>
<h3 class="unnumbered unlisted" id="synopsis-15">Synopsis</h3>
<div class="sourceCode" id="cb839"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb839-1"><a href="complex.html#cb839-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb839-2"><a href="complex.html#cb839-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb839-3"><a href="complex.html#cb839-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> clog<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb839-4"><a href="complex.html#cb839-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb839-5"><a href="complex.html#cb839-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> clogf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb839-6"><a href="complex.html#cb839-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb839-7"><a href="complex.html#cb839-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> clogl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-15">Description</h3>
<p>Compute the base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="22" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> complex
logarithm of <code>z</code>. There is a branch cut on the negative real
axis.</p>
<p>The returns value is unbounded on the real axis and in the range
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="23" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>i</mi><mi>π</mi><mo>,</mo><mo>+</mo><mi>i</mi><mi>π</mi><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span> on the imaginary
axis.</p>
<h3 class="unnumbered unlisted" id="return-value-15">Return Value</h3>
<p>Returns the base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="24" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> complex
logarithm of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-15">Example</h3>
<div class="sourceCode" id="cb840"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb840-1"><a href="complex.html#cb840-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb840-2"><a href="complex.html#cb840-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb840-3"><a href="complex.html#cb840-3"></a></span>
<span id="cb840-4"><a href="complex.html#cb840-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb840-5"><a href="complex.html#cb840-5"></a><span class="op">{</span></span>
<span id="cb840-6"><a href="complex.html#cb840-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb840-7"><a href="complex.html#cb840-7"></a></span>
<span id="cb840-8"><a href="complex.html#cb840-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> clog<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb840-9"><a href="complex.html#cb840-9"></a></span>
<span id="cb840-10"><a href="complex.html#cb840-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb840-11"><a href="complex.html#cb840-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb841"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb841-1"><a href="complex.html#cb841-1" aria-hidden="true" tabindex="-1"></a>Result: 0.804719 + 1.107149i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-15">See Also</h3>
<p><a href="complex.html#man-cexp"><code>cexp()</code></a>, <a href="#man-log"><code>log()</code></a></p>
<hr>
<h2 data-number="43.15" id="man-cabs"><span class="header-section-number">43.15</span> <code>cabs()</code>
<code>cabsf()</code> <code>cabsl()</code></h2>
<p>Compute the complex absolute value</p>
<h3 class="unnumbered unlisted" id="synopsis-16">Synopsis</h3>
<div class="sourceCode" id="cb842"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb842-1"><a href="complex.html#cb842-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb842-2"><a href="complex.html#cb842-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb842-3"><a href="complex.html#cb842-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> cabs<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb842-4"><a href="complex.html#cb842-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb842-5"><a href="complex.html#cb842-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> cabsf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb842-6"><a href="complex.html#cb842-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb842-7"><a href="complex.html#cb842-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> cabsl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-16">Description</h3>
<p>Computes the complex absolute value of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-16">Return Value</h3>
<p>Returns the complex absolute value of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-16">Example</h3>
<div class="sourceCode" id="cb843"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb843-1"><a href="complex.html#cb843-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb843-2"><a href="complex.html#cb843-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb843-3"><a href="complex.html#cb843-3"></a></span>
<span id="cb843-4"><a href="complex.html#cb843-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb843-5"><a href="complex.html#cb843-5"></a><span class="op">{</span></span>
<span id="cb843-6"><a href="complex.html#cb843-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb843-7"><a href="complex.html#cb843-7"></a></span>
<span id="cb843-8"><a href="complex.html#cb843-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> cabs<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb843-9"><a href="complex.html#cb843-9"></a></span>
<span id="cb843-10"><a href="complex.html#cb843-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb843-11"><a href="complex.html#cb843-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb844"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb844-1"><a href="complex.html#cb844-1" aria-hidden="true" tabindex="-1"></a>Result: 2.236068 + 0.000000i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-16">See Also</h3>
<p><a href="math.html#man-fabs"><code>fabs()</code></a>, <a href="#man-abs"><code>abs()</code></a></p>
<hr>
<h2 data-number="43.16" id="man-cpow"><span class="header-section-number">43.16</span> <code>cpow()</code>
<code>cpowf()</code> <code>cpowl()</code></h2>
<p>Compute complex power</p>
<h3 class="unnumbered unlisted" id="synopsis-17">Synopsis</h3>
<div class="sourceCode" id="cb845"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb845-1"><a href="complex.html#cb845-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb845-2"><a href="complex.html#cb845-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb845-3"><a href="complex.html#cb845-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> cpow<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> x<span class="op">,</span> <span class="dt">double</span> <span class="dt">complex</span> y<span class="op">);</span></span>
<span id="cb845-4"><a href="complex.html#cb845-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb845-5"><a href="complex.html#cb845-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> cpowf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> x<span class="op">,</span> <span class="dt">float</span> <span class="dt">complex</span> y<span class="op">);</span></span>
<span id="cb845-6"><a href="complex.html#cb845-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb845-7"><a href="complex.html#cb845-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> cpowl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> x<span class="op">,</span></span>
<span id="cb845-8"><a href="complex.html#cb845-8" aria-hidden="true" tabindex="-1"></a>                          <span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-17">Description</h3>
<p>Computes the complex <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="25" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>x</mi><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>There is a branch cut for <code>x</code> along the negative real
axis.</p>
<h3 class="unnumbered unlisted" id="return-value-17">Return Value</h3>
<p>Returns the complex <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="26" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>x</mi><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-17">Example</h3>
<div class="sourceCode" id="cb846"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb846-1"><a href="complex.html#cb846-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb846-2"><a href="complex.html#cb846-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb846-3"><a href="complex.html#cb846-3"></a></span>
<span id="cb846-4"><a href="complex.html#cb846-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb846-5"><a href="complex.html#cb846-5"></a><span class="op">{</span></span>
<span id="cb846-6"><a href="complex.html#cb846-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb846-7"><a href="complex.html#cb846-7"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> <span class="dv">3</span> <span class="op">+</span> <span class="dv">4</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb846-8"><a href="complex.html#cb846-8"></a></span>
<span id="cb846-9"><a href="complex.html#cb846-9"></a>    <span class="dt">double</span> r <span class="op">=</span> cpow<span class="op">(</span>x<span class="op">,</span> y<span class="op">);</span></span>
<span id="cb846-10"><a href="complex.html#cb846-10"></a></span>
<span id="cb846-11"><a href="complex.html#cb846-11"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>r<span class="op">),</span> cimag<span class="op">(</span>r<span class="op">));</span></span>
<span id="cb846-12"><a href="complex.html#cb846-12"></a><span class="op">}</span></span></code></pre></div>
<p>Result:</p>
<div class="sourceCode" id="cb847"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb847-1"><a href="complex.html#cb847-1" aria-hidden="true" tabindex="-1"></a>Result: 0.129010 + 0.000000i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-17">See Also</h3>
<p><a href="complex.html#man-csqrt"><code>csqrt()</code></a>, <a href="#man-cexp"><code>cexp()</code></a></p>
<hr>
<h2 data-number="43.17" id="man-csqrt"><span class="header-section-number">43.17</span> <code>csqrt()</code>
<code>csqrtf()</code> <code>csqrtl()</code></h2>
<p>Compute the complex square root</p>
<h3 class="unnumbered unlisted" id="synopsis-18">Synopsis</h3>
<div class="sourceCode" id="cb848"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb848-1"><a href="complex.html#cb848-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb848-2"><a href="complex.html#cb848-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb848-3"><a href="complex.html#cb848-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> csqrt<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb848-4"><a href="complex.html#cb848-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb848-5"><a href="complex.html#cb848-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> csqrtf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb848-6"><a href="complex.html#cb848-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb848-7"><a href="complex.html#cb848-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> csqrtl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-18">Description</h3>
<p>Computes the complex square root of <code>z</code>.</p>
<p>There is a branch cut along the negative real axis.</p>
<p>The return value is in the right half of the complex plane and
includes the imaginary axis.</p>
<h3 class="unnumbered unlisted" id="return-value-18">Return Value</h3>
<p>Returns the complex square root of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-18">Example</h3>
<div class="sourceCode" id="cb849"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb849-1"><a href="complex.html#cb849-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb849-2"><a href="complex.html#cb849-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb849-3"><a href="complex.html#cb849-3"></a></span>
<span id="cb849-4"><a href="complex.html#cb849-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb849-5"><a href="complex.html#cb849-5"></a><span class="op">{</span></span>
<span id="cb849-6"><a href="complex.html#cb849-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb849-7"><a href="complex.html#cb849-7"></a></span>
<span id="cb849-8"><a href="complex.html#cb849-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> csqrt<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb849-9"><a href="complex.html#cb849-9"></a></span>
<span id="cb849-10"><a href="complex.html#cb849-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb849-11"><a href="complex.html#cb849-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb850"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb850-1"><a href="complex.html#cb850-1" aria-hidden="true" tabindex="-1"></a>Result: 1.272020 + 0.786151i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-18">See Also</h3>
<p><a href="complex.html#man-cpow"><code>cpow()</code></a>, <a href="#man-sqrt"><code>sqrt()</code></a></p>
<hr>
<h2 data-number="43.18" id="man-carg"><span class="header-section-number">43.18</span> <code>carg()</code>
<code>cargf()</code> <code>cargl()</code></h2>
<p>Compute the complex argument</p>
<h3 class="unnumbered unlisted" id="synopsis-19">Synopsis</h3>
<div class="sourceCode" id="cb851"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb851-1"><a href="complex.html#cb851-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb851-2"><a href="complex.html#cb851-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb851-3"><a href="complex.html#cb851-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> carg<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb851-4"><a href="complex.html#cb851-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb851-5"><a href="complex.html#cb851-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> cargf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb851-6"><a href="complex.html#cb851-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb851-7"><a href="complex.html#cb851-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> cargl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-19">Description</h3>
<p>Computes the complex argument (AKA phase angle) of
<code>z</code>.</p>
<p>There is a branch cut along the negative real axis.</p>
<p>Returns a value in the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="27" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mi>π</mi><mo>,</mo><mo>+</mo><mi>π</mi><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="return-value-19">Return Value</h3>
<p>Returns the complex argument of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-19">Example</h3>
<div class="sourceCode" id="cb852"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb852-1"><a href="complex.html#cb852-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb852-2"><a href="complex.html#cb852-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb852-3"><a href="complex.html#cb852-3"></a></span>
<span id="cb852-4"><a href="complex.html#cb852-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb852-5"><a href="complex.html#cb852-5"></a><span class="op">{</span></span>
<span id="cb852-6"><a href="complex.html#cb852-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb852-7"><a href="complex.html#cb852-7"></a></span>
<span id="cb852-8"><a href="complex.html#cb852-8"></a>    <span class="dt">double</span> y <span class="op">=</span> carg<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb852-9"><a href="complex.html#cb852-9"></a></span>
<span id="cb852-10"><a href="complex.html#cb852-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> y<span class="op">);</span></span>
<span id="cb852-11"><a href="complex.html#cb852-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb853"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb853-1"><a href="complex.html#cb853-1" aria-hidden="true" tabindex="-1"></a>Result: 1.107149</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="43.19" id="man-cimag"><span class="header-section-number">43.19</span> <code>cimag()</code>
<code>cimagf()</code> <code>cimagl()</code></h2>
<p>Returns the imaginary part of a complex number</p>
<h3 class="unnumbered unlisted" id="synopsis-20">Synopsis</h3>
<div class="sourceCode" id="cb854"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb854-1"><a href="complex.html#cb854-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb854-2"><a href="complex.html#cb854-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb854-3"><a href="complex.html#cb854-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> cimag<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb854-4"><a href="complex.html#cb854-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb854-5"><a href="complex.html#cb854-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> cimagf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb854-6"><a href="complex.html#cb854-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb854-7"><a href="complex.html#cb854-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> cimagl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-20">Description</h3>
<p>Returns the imaginary part of <code>z</code>.</p>
<p>As a footnote, the spec points out that any complex number
<code>x</code> is part of the following equivalency:</p>
<div class="sourceCode" id="cb855"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb855-1"><a href="complex.html#cb855-1" aria-hidden="true" tabindex="-1"></a>x <span class="op">==</span> creal<span class="op">(</span>x<span class="op">)</span> <span class="op">+</span> cimag<span class="op">(</span>x<span class="op">)</span> <span class="op">*</span> I<span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-20">Return Value</h3>
<p>Returns the imaginary part of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-20">Example</h3>
<div class="sourceCode" id="cb856"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb856-1"><a href="complex.html#cb856-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb856-2"><a href="complex.html#cb856-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb856-3"><a href="complex.html#cb856-3"></a></span>
<span id="cb856-4"><a href="complex.html#cb856-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb856-5"><a href="complex.html#cb856-5"></a><span class="op">{</span></span>
<span id="cb856-6"><a href="complex.html#cb856-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb856-7"><a href="complex.html#cb856-7"></a></span>
<span id="cb856-8"><a href="complex.html#cb856-8"></a>    <span class="dt">double</span> y <span class="op">=</span> cimag<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb856-9"><a href="complex.html#cb856-9"></a></span>
<span id="cb856-10"><a href="complex.html#cb856-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> y<span class="op">);</span></span>
<span id="cb856-11"><a href="complex.html#cb856-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output—just the imaginary part:</p>
<div class="sourceCode" id="cb857"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb857-1"><a href="complex.html#cb857-1" aria-hidden="true" tabindex="-1"></a>Result: 2.000000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-19">See Also</h3>
<p><a href="complex.html#man-creal"><code>creal()</code></a></p>
<hr>
<h2 data-number="43.20" id="man-CMPLX"><span class="header-section-number">43.20</span> <code>CMPLX()</code>
<code>CMPLXF()</code> <code>CMPLXL()</code></h2>
<p>Build a complex value from real and imaginary types</p>
<h3 class="unnumbered unlisted" id="synopsis-21">Synopsis</h3>
<div class="sourceCode" id="cb858"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb858-1"><a href="complex.html#cb858-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb858-2"><a href="complex.html#cb858-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb858-3"><a href="complex.html#cb858-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> CMPLX<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb858-4"><a href="complex.html#cb858-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb858-5"><a href="complex.html#cb858-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> CMPLXF<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb858-6"><a href="complex.html#cb858-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb858-7"><a href="complex.html#cb858-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> CMPLXL<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-21">Description</h3>
<p>These macros build a complex value from real and imaginary types.</p>
<p>Now I know what you’re thinking. “But I can already build a complex
value from real and imaginary types using the <code>I</code> macro, like
in the example you’re about to give us.”</p>
<div class="sourceCode" id="cb859"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb859-1"><a href="complex.html#cb859-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span></code></pre></div>
<p>And that’s true.</p>
<p>But the reality of the matter is weird and complex.</p>
<p>Maybe <code>I</code> got undefined, or maybe you redefined it.</p>
<p>Or maybe <code>I</code> was defined as <code>_Complex_I</code> which
doesn’t necessarily preserve the sign of a zero value.</p>
<p>As the spec points out, these macros build complex numbers as if
<code>_Imaginary_I</code> were defined (thus preserving your zero sign)
even if it’s not. That is, they are defined equivalently to:</p>
<div class="sourceCode" id="cb860"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb860-1"><a href="complex.html#cb860-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#define CMPLX(x, y)  ((double complex)((double)(x) + \</span></span>
<span id="cb860-2"><a href="complex.html#cb860-2" aria-hidden="true" tabindex="-1"></a><span class="pp">                     _Imaginary_I * (double)(y)))</span></span>
<span id="cb860-3"><a href="complex.html#cb860-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb860-4"><a href="complex.html#cb860-4" aria-hidden="true" tabindex="-1"></a><span class="pp">#define CMPLXF(x, y) ((float complex)((float)(x) + \</span></span>
<span id="cb860-5"><a href="complex.html#cb860-5" aria-hidden="true" tabindex="-1"></a><span class="pp">                     _Imaginary_I * (float)(y)))</span></span>
<span id="cb860-6"><a href="complex.html#cb860-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb860-7"><a href="complex.html#cb860-7" aria-hidden="true" tabindex="-1"></a><span class="pp">#define CMPLXL(x, y) ((long double complex)((long double)(x) + \</span></span>
<span id="cb860-8"><a href="complex.html#cb860-8" aria-hidden="true" tabindex="-1"></a><span class="pp">                     _Imaginary_I * (long double)(y)))</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-21">Return Value</h3>
<p>Returns the complex number for the given real <code>x</code> and
imaginary <code>y</code> components.</p>
<h3 class="unnumbered unlisted" id="example-21">Example</h3>
<div class="sourceCode" id="cb861"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb861-1"><a href="complex.html#cb861-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb861-2"><a href="complex.html#cb861-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb861-3"><a href="complex.html#cb861-3"></a></span>
<span id="cb861-4"><a href="complex.html#cb861-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb861-5"><a href="complex.html#cb861-5"></a><span class="op">{</span></span>
<span id="cb861-6"><a href="complex.html#cb861-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> CMPLX<span class="op">(</span><span class="dv">1</span><span class="op">,</span> <span class="dv">2</span><span class="op">);</span>  <span class="co">// Like 1 + 2 * I</span></span>
<span id="cb861-7"><a href="complex.html#cb861-7"></a></span>
<span id="cb861-8"><a href="complex.html#cb861-8"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>x<span class="op">),</span> cimag<span class="op">(</span>x<span class="op">));</span></span>
<span id="cb861-9"><a href="complex.html#cb861-9"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb862"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb862-1"><a href="complex.html#cb862-1" aria-hidden="true" tabindex="-1"></a>Result: 1.000000 + 2.000000i</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-20">See Also</h3>
<p><a href="complex.html#man-creal"><code>creal()</code></a>, <a href="#man-cimag"><code>cimag()</code></a></p>
<hr>
<h2 data-number="43.21" id="man-conj"><span class="header-section-number">43.21</span> <code>conj()</code>
<code>conjf()</code> <code>conjl()</code></h2>
<p>Compute the conjugate of a complex number</p>
<h3 class="unnumbered unlisted" id="synopsis-22">Synopsis</h3>
<div class="sourceCode" id="cb863"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb863-1"><a href="complex.html#cb863-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb863-2"><a href="complex.html#cb863-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb863-3"><a href="complex.html#cb863-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> conj<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb863-4"><a href="complex.html#cb863-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb863-5"><a href="complex.html#cb863-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> conjf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb863-6"><a href="complex.html#cb863-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb863-7"><a href="complex.html#cb863-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> conjl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-22">Description</h3>
<p>This function computes the <a href="https://en.wikipedia.org/wiki/Complex_conjugate">complex
conjugate</a><a href="footnotes.html#fn220" class="footnote-ref" id="fnref220" role="doc-noteref"><sup>220</sup></a> of <code>z</code>. Apparently it
does this by reversing the sign of the imaginary part, but dammit, I’m a
programmer not a mathematician, Jim!</p>
<h3 class="unnumbered unlisted" id="return-value-22">Return Value</h3>
<p>Returns the complex conjugate of <code>z</code></p>
<h3 class="unnumbered unlisted" id="example-22">Example</h3>
<div class="sourceCode" id="cb864"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb864-1"><a href="complex.html#cb864-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb864-2"><a href="complex.html#cb864-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb864-3"><a href="complex.html#cb864-3"></a></span>
<span id="cb864-4"><a href="complex.html#cb864-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb864-5"><a href="complex.html#cb864-5"></a><span class="op">{</span></span>
<span id="cb864-6"><a href="complex.html#cb864-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb864-7"><a href="complex.html#cb864-7"></a></span>
<span id="cb864-8"><a href="complex.html#cb864-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> conj<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb864-9"><a href="complex.html#cb864-9"></a></span>
<span id="cb864-10"><a href="complex.html#cb864-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb864-11"><a href="complex.html#cb864-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb865"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb865-1"><a href="complex.html#cb865-1" aria-hidden="true" tabindex="-1"></a>Result: 1.000000 + -2.000000i</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="43.22" id="man-cproj"><span class="header-section-number">43.22</span> <code>cproj()</code>
<code>cproj()</code> <code>cproj()</code></h2>
<p>Compute the projection of a complex number</p>
<h3 class="unnumbered unlisted" id="synopsis-23">Synopsis</h3>
<div class="sourceCode" id="cb866"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb866-1"><a href="complex.html#cb866-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb866-2"><a href="complex.html#cb866-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb866-3"><a href="complex.html#cb866-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> cproj<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb866-4"><a href="complex.html#cb866-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb866-5"><a href="complex.html#cb866-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> cprojf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb866-6"><a href="complex.html#cb866-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb866-7"><a href="complex.html#cb866-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> cprojl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-23">Description</h3>
<p>Computes the projection of <code>z</code> onto a <a href="https://en.wikipedia.org/wiki/Riemann_sphere">Riemann sphere</a><a href="#fn221" class="footnote-ref" id="fnref221" role="doc-noteref"><sup>221</sup></a>.</p>
<p>Now we’re <em>really</em> outside my expertise. The spec has this to
say, which I’m quoting verbatim because I’m not knowledgable enough to
rewrite it sensibly. Hopefully it makes sense to anyone who would need
to use this function.</p>
<blockquote>
<p><code>z</code> projects to <code>z</code> except that all complex
infinities (even those with one infinite part and one <code>NaN</code>
part) project to positive infinity on the real axis. If <code>z</code>
has an infinite part, then <code>cproj(z)</code> is equivalent to</p>
<pre><code>INFINITY + I * copysign(0.0, cimag(z))</code></pre>
</blockquote>
<p>So there you have it.</p>
<h3 class="unnumbered unlisted" id="return-value-23">Return Value</h3>
<p>Returns the projection of <code>z</code> onto a Riemann sphere.</p>
<h3 class="unnumbered unlisted" id="example-23">Example</h3>
<p>Fingers crossed this is a remotely sane example…</p>
<div class="sourceCode" id="cb868"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb868-1"><a href="complex.html#cb868-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb868-2"><a href="complex.html#cb868-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb868-3"><a href="complex.html#cb868-3"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb868-4"><a href="complex.html#cb868-4"></a></span>
<span id="cb868-5"><a href="complex.html#cb868-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb868-6"><a href="complex.html#cb868-6"></a><span class="op">{</span></span>
<span id="cb868-7"><a href="complex.html#cb868-7"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb868-8"><a href="complex.html#cb868-8"></a></span>
<span id="cb868-9"><a href="complex.html#cb868-9"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> cproj<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb868-10"><a href="complex.html#cb868-10"></a></span>
<span id="cb868-11"><a href="complex.html#cb868-11"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb868-12"><a href="complex.html#cb868-12"></a></span>
<span id="cb868-13"><a href="complex.html#cb868-13"></a>    x <span class="op">=</span> INFINITY <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb868-14"><a href="complex.html#cb868-14"></a>    y <span class="op">=</span> cproj<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb868-15"><a href="complex.html#cb868-15"></a></span>
<span id="cb868-16"><a href="complex.html#cb868-16"></a>    printf<span class="op">(</span><span class="st">"Result: %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span>
<span id="cb868-17"><a href="complex.html#cb868-17"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb869"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb869-1"><a href="complex.html#cb869-1" aria-hidden="true" tabindex="-1"></a>Result: 1.000000 + 2.000000i</span>
<span id="cb869-2"><a href="complex.html#cb869-2" aria-hidden="true" tabindex="-1"></a>Result: inf + 0.000000i</span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="43.23" id="man-creal"><span class="header-section-number">43.23</span> <code>creal()</code>
<code>crealf()</code> <code>creall()</code></h2>
<p>Returns the real part of a complex number</p>
<h3 class="unnumbered unlisted" id="synopsis-24">Synopsis</h3>
<div class="sourceCode" id="cb870"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb870-1"><a href="complex.html#cb870-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb870-2"><a href="complex.html#cb870-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb870-3"><a href="complex.html#cb870-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> creal<span class="op">(</span><span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb870-4"><a href="complex.html#cb870-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb870-5"><a href="complex.html#cb870-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> crealf<span class="op">(</span><span class="dt">float</span> <span class="dt">complex</span> z<span class="op">);</span></span>
<span id="cb870-6"><a href="complex.html#cb870-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb870-7"><a href="complex.html#cb870-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> creall<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-24">Description</h3>
<p>Returns the real part of <code>z</code>.</p>
<p>As a footnote, the spec points out that any complex number
<code>x</code> is part of the following equivalency:</p>
<div class="sourceCode" id="cb871"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb871-1"><a href="complex.html#cb871-1" aria-hidden="true" tabindex="-1"></a>x <span class="op">==</span> creal<span class="op">(</span>x<span class="op">)</span> <span class="op">+</span> cimag<span class="op">(</span>x<span class="op">)</span> <span class="op">*</span> I<span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-24">Return Value</h3>
<p>Returns the real part of <code>z</code>.</p>
<h3 class="unnumbered unlisted" id="example-24">Example</h3>
<div class="sourceCode" id="cb872"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb872-1"><a href="complex.html#cb872-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb872-2"><a href="complex.html#cb872-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb872-3"><a href="complex.html#cb872-3"></a></span>
<span id="cb872-4"><a href="complex.html#cb872-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb872-5"><a href="complex.html#cb872-5"></a><span class="op">{</span></span>
<span id="cb872-6"><a href="complex.html#cb872-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span> <span class="op">*</span> I<span class="op">;</span></span>
<span id="cb872-7"><a href="complex.html#cb872-7"></a></span>
<span id="cb872-8"><a href="complex.html#cb872-8"></a>    <span class="dt">double</span> y <span class="op">=</span> creal<span class="op">(</span>x<span class="op">);</span></span>
<span id="cb872-9"><a href="complex.html#cb872-9"></a></span>
<span id="cb872-10"><a href="complex.html#cb872-10"></a>    printf<span class="op">(</span><span class="st">"Result: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> y<span class="op">);</span></span>
<span id="cb872-11"><a href="complex.html#cb872-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output—just the real part:</p>
<div class="sourceCode" id="cb873"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb873-1"><a href="complex.html#cb873-1" aria-hidden="true" tabindex="-1"></a>Result: 1.000000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-21">See Also</h3>
<p><a href="complex.html#man-cimag"><code>cimag()</code></a></p>

<hr>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="assert.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="ctype.html">Next»</a></div>

</body>