<body>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="locale.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="setjmp.html">Next»</a></div>
<hr>
<h1 data-number="52" id="math"><span class="header-section-number">52</span> <code>&lt;math.h&gt;</code>
Mathematics</h1>
<p>Many of the following functions have <code>float</code> and
<code>long double</code> variants as described <a href="#func-idioms">below</a> (e.g.&nbsp;<code>pow()</code>,
<code>powf()</code>, <code>powl()</code>). The <code>float</code> and
<code>long double</code> variants are omitted from the following table
to keep your eyeballs from melting out.</p>
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
<td><a href="math.html#man-acos"><code>acos()</code></a></td>
<td>Calculate the arc cosine of a number.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-acosh"><code>acosh()</code></a></td>
<td>Compute arc hyperbolic cosine.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-asin"><code>asin()</code></a></td>
<td>Calculate the arc sine of a number.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-asinh"><code>asinh()</code></a></td>
<td>Compute arc hyperbolic sine.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-atan"><code>atan()</code></a>, <a href="#man-atan"><code>atan2()</code></a></td>
<td>Calculate the arc tangent of a number.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-atanh"><code>atanh()</code></a></td>
<td>Compute the arc hyperbolic tangent.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-cbrt"><code>cbrt()</code></a></td>
<td>Compute the cube root.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-ceil"><code>ceil()</code></a></td>
<td>Ceiling—return the next whole number not smaller than the given
number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-copysign"><code>copysign()</code></a></td>
<td>Copy the sign of one value into another.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-cos"><code>cos()</code></a></td>
<td>Calculate the cosine of a number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-cosh"><code>cosh()</code></a></td>
<td>Compute the hyperbolic cosine.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-erf"><code>erf()</code></a></td>
<td>Compute the error function of the given value.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-erfc"><code>erfc()</code></a></td>
<td>Compute the complementary error function of a value.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-exp"><code>exp()</code></a></td>
<td>Compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> raised to a
power.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-exp2"><code>exp2()</code></a></td>
<td>Compute 2 to a power.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-expm1"><code>expm1()</code></a></td>
<td>Compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>e</mi><mi>x</mi></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-fabs"><code>fabs()</code></a></td>
<td>Compute the absolute value.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-fdim"><code>fdim()</code></a></td>
<td>Return the positive difference between two numbers clamped at
0.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-floor"><code>floor()</code></a></td>
<td>Compute the largest whole number not larger than the given
value.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-fma"><code>fma()</code></a></td>
<td>Floating (AKA “Fast”) multiply and add.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-fmax"><code>fmax()</code></a>, <a href="#man-fmax"><code>fmin()</code></a></td>
<td>Return the maximum or minimum of two numbers.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-fmod"><code>fmod()</code></a></td>
<td>Compute the floating point remainder.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-fpclassify"><code>fpclassify()</code></a></td>
<td>Return the classification of a given floating point number.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-frexp"><code>frexp()</code></a></td>
<td>Break a number into its fraction part and exponent (as a power of
2).</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-hypot"><code>hypot()</code></a></td>
<td>Compute the length of the hypotenuse of a triangle.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-ilogb"><code>ilogb()</code></a></td>
<td>Return the exponent of a floating point number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-isnan"><code>isfinite()</code></a></td>
<td>True if the number is not infinite or NaN.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-isgreater"><code>isgreater()</code></a></td>
<td>True if one argument is greater than another.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-isgreater"><code>isgreatereequal()</code></a></td>
<td>True if one argument is greater than or equal to another.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-isnan"><code>isinf()</code></a></td>
<td>True if the number is infinite.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-isgreater"><code>isless()</code></a></td>
<td>True if one argument is less than another.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-isgreater"><code>islesseequal()</code></a></td>
<td>True if one argument is less than or equal to another.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-islessgreater"><code>islessgreater()</code></a></td>
<td>Test if a floating point number is less than or greater than
another.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-isnan"><code>isnan()</code></a></td>
<td>True if the number is Not-a-Number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-isnan"><code>isnormal()</code></a></td>
<td>True if the number is normal.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-isunordered"><code>isunordered()</code></a></td>
<td>Macro returns true if either floating point argument is NaN.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-ldexp"><code>ldexp()</code></a></td>
<td>Multiply a number by an integral power of 2.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-lgamma"><code>lgamma()</code></a></td>
<td>Compute the natural logarithm of the absolute value of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-log"><code>log()</code></a></td>
<td>Compute the natural logarithm.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-log10"><code>log10()</code></a></td>
<td>Compute the log-base-10 of a number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-log2"><code>log2()</code></a></td>
<td>Compute the base-2 logarithm of a number.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-logb"><code>logb()</code></a></td>
<td>Extract the exponent of a number given <code>FLT_RADIX</code>.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-log1p"><code>log1p()</code></a></td>
<td>Compute the natural logarithm of a number plus 1.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-lrint"><code>lrint()</code></a></td>
<td>Returns <code>x</code> rounded in the current rounding direction as
an integer.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-lround"><code>lround()</code></a>, <a href="#man-lround"><code>llround()</code></a></td>
<td>Round a number in the good old-fashioned way, returning an
integer.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-modf"><code>modf()</code></a></td>
<td>Extract the integral and fractional parts of a number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-nan"><code>nan()</code></a></td>
<td>Return <code>NAN</code>.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-nearbyint"><code>nearbyint()</code></a></td>
<td>Rounds a value in the current rounding direction.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-nextafter"><code>nextafter()</code></a></td>
<td>Get the next (or previous) representable floating point value.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-nexttoward"><code>nexttoward()</code></a></td>
<td>Get the next (or previous) representable floating point value.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-pow"><code>pow()</code></a></td>
<td>Compute a value raised to a power.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-remainder"><code>remainder()</code></a></td>
<td>Compute the remainder IEC 60559-style.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-remquo"><code>remquo()</code></a></td>
<td>Compute the remainder and (some of the) quotient.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-rint"><code>rint()</code></a></td>
<td>Rounds a value in the current rounding direction.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-round"><code>round()</code></a></td>
<td>Round a number in the good old-fashioned way.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-scalb"><code>scalbn()</code></a>, <a href="#man-scalb"><code>scalbln()</code></a></td>
<td>Efficiently compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>×</mo><msup><mi>r</mi><mi>n</mi></msup></math></mjx-assistive-mml></mjx-container></span>, where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is
<code>FLT_RADIX</code>.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-signbit"><code>signbit()</code></a></td>
<td>Return the sign of a number.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-sin"><code>sin()</code></a></td>
<td>Calculate the sine of a number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-sqrt"><code>sqrt()</code></a></td>
<td>Calculate the square root of a number.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-tan"><code>tan()</code></a></td>
<td>Calculate the tangent of a number.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-tanh"><code>tanh()</code></a></td>
<td>Compute the hyperbolic tangent.</td>
</tr>
<tr class="even">
<td><a href="math.html#man-tgamma"><code>tgamma()</code></a></td>
<td>Compute the gamma function, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</td>
</tr>
<tr class="odd">
<td><a href="math.html#man-trunc"><code>trunc()</code></a></td>
<td>Truncate the fractional part off a floating point value.</td>
</tr>
</tbody>
</table>
<p>It’s your favorite subject: Mathematics! Hello, I’m Doctor Math, and
I’ll be making math FUN and EASY!</p>
<p><em>[vomiting sounds]</em></p>
<p>Ok, I know math isn’t the grandest thing for some of you out there,
but these are merely functions that quickly and easily do math you
either know, want, or just don’t care about. That pretty much covers
it.</p>
<h2 data-number="52.1" id="func-idioms"><span class="header-section-number">52.1</span> Math Function Idioms</h2>
<p>Many of these math functions exist in three forms, each corresponding
to the argument and/or return types the function uses,
<code>float</code>, <code>double</code>, or
<code>long double</code>.</p>
<p>The alternate form for <code>float</code> is made by appending
<code>f</code> to the end of the function name.</p>
<p>The alternate form for <code>long double</code> is made by appending
<code>l</code> to the end of the function name.</p>
<p>For example, the <code>pow()</code> function, which computes <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>x</mi><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span>, exists in these forms:</p>
<div class="sourceCode" id="cb969"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb969-1"><a href="math.html#cb969-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span>      pow<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span>             <span class="co">// double</span></span>
<span id="cb969-2"><a href="math.html#cb969-2" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span>       powf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span>              <span class="co">// float</span></span>
<span id="cb969-3"><a href="math.html#cb969-3" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> powl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span>  <span class="co">// long double</span></span></code></pre></div>
<p>Remember that parameters are given values as if you assigned into
them. So if you pass a <code>double</code> to <code>powf()</code>, it’ll
choose the closest <code>float</code> it can to hold the double. If the
<code>double</code> doesn’t fit, undefined behavior happens.</p>
<h2 data-number="52.2" id="math-types"><span class="header-section-number">52.2</span> Math Types</h2>
<p>We have two exciting new types in <code>&lt;math.h&gt;</code>:</p>
<ul>
<li><code>float_t</code></li>
<li><code>double_t</code></li>
</ul>
<p>The <code>float_t</code> type is at least as accurate as a
<code>float</code>, and the <code>double_t</code> type is at least as
accurate as a <code>double</code>.</p>
<p>The idea with these types is they can represent the most efficient
way of storing numbers for maximum speed.</p>
<p>Their actual types vary by implementation, but can be determined by
the value of the <code>FLT_EVAL_METHOD</code> macro.</p>
<table>
<thead>
<tr class="header">
<th><code>FLT_EVAL_METHOD</code></th>
<th><code>float_t</code> type</th>
<th><code>double_t</code> type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>0</code></td>
<td><code>float</code></td>
<td><code>double</code></td>
</tr>
<tr class="even">
<td><code>1</code></td>
<td><code>double</code></td>
<td><code>double</code></td>
</tr>
<tr class="odd">
<td><code>2</code></td>
<td><code>long double</code></td>
<td><code>long double</code></td>
</tr>
<tr class="even">
<td>Other</td>
<td>Implementation-defined</td>
<td>Implementation-defined</td>
</tr>
</tbody>
</table>
<p>For all defined values of <code>FLT_EVAL_METHOD</code>,
<code>float_t</code> is the least-precise type used for all floating
calculations.</p>
<h2 data-number="52.3" id="math-macros"><span class="header-section-number">52.3</span> Math Macros</h2>
<p>There are actually a number of these defined, but we’ll cover most of
them in their relevant reference sections, below.</p>
<p>But here are a couple:</p>
<p><code>NAN</code> represents Not-A-Number.</p>
<p>Defined in <code>&lt;float.h&gt;</code> is <code>FLT_RADIX</code>:
the number base used by floating point numbers. This is commonly
<code>2</code>, but could be anything.</p>
<h2 data-number="52.4" id="math-errors"><span class="header-section-number">52.4</span> Math Errors</h2>
<p>As we know, nothing can ever go wrong with math… except
<em>everything</em>!</p>
<p>So there are just a couple errors that might occur when using some of
these functions.</p>
<ul>
<li><p><strong>Range errors</strong> mean that some result is beyond
what can be stored in the result type.</p></li>
<li><p><strong>Domain errors</strong> mean that you’ve passed in an
argument that doesn’t have a defined result for this function.</p></li>
<li><p><strong>Pole errors</strong> mean that the limit of the function
as <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> approaches the given argument
is infinite.</p></li>
<li><p><strong>Overflow errors</strong> are when the result is really
large, but can’t be stored without incurring large roundoff
error.</p></li>
<li><p><strong>Underflow errors</strong> are like overflow errors,
except with very small numbers.</p></li>
</ul>
<p>Now, the C math library can do a couple things when these errors
occur:</p>
<ul>
<li>Set <code>errno</code> to some value, or…</li>
<li>Raise a floating point exception.</li>
</ul>
<p>Your system might vary on what happens. You can check it by looking
at the value of the variable <code>math_errhandling</code>. It will be
equivalent to one of the following<a href="footnotes.html#fn229" class="footnote-ref" id="fnref229" role="doc-noteref"><sup>229</sup></a>:</p>
<table>
<colgroup>
<col style="width: 50%">
<col style="width: 50%">
</colgroup>
<thead>
<tr class="header">
<th><code>math_errhandling</code></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>MATH_ERRNO</code></td>
<td>The system uses <code>errno</code> for math errors.</td>
</tr>
<tr class="even">
<td><code>MATH_ERREXCEPT</code></td>
<td>The system uses exceptions for math errors.</td>
</tr>
<tr class="odd">
<td><code>MATH_ERRNO | MATH_ERREXCEPT</code></td>
<td>The system does both! (That’s a bitwise-OR!)</td>
</tr>
</tbody>
</table>
<p>You are not allowed to change <code>math_errhandling</code>.</p>
<p>For a fuller description on how exceptions work and their meanings,
see the <a href="fenv.html"><code>&lt;fenv.h&gt;</code></a> section.</p>
<h2 data-number="52.5" id="math-pragmas"><span class="header-section-number">52.5</span> Math Pragmas</h2>
<p>In case you don’t remember, you can brush up on <a href="#pragma">pragmas back in the C Preprocessor section</a>.</p>
<p>But in a nutshell, they offer various ways to control the compiler’s
behavior.</p>
<p>In this case, we have a pragma <code>FP_CONTRACT</code> that can be
turned off and on.</p>
<p>What does it mean?</p>
<p>First of all, keep in mind that any operation in an expression can
cause rounding error. So each step of the expression can introduce more
rounding error.</p>
<p>But what if the compiler knows a <em>double secret</em> way of taking
the expression you wrote and converting it to a single instruction that
reduced the number of steps such that the intermediate rounding error
didn’t occur?</p>
<p>Could it use it? I mean, the results would be different than if you
let the rounding error settle each step of the way…</p>
<p>Because the results would be different, you can tell the compiler if
you want to allow it to do this or not.</p>
<p>If you want to allow it:</p>
<div class="sourceCode" id="cb970"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb970-1"><a href="math.html#cb970-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#pragma STDC FP_CONTRACT ON</span></span></code></pre></div>
<p>and to disallow it:</p>
<div class="sourceCode" id="cb971"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb971-1"><a href="math.html#cb971-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#pragma STDC FP_CONTRACT OFF</span></span></code></pre></div>
<p>If you do this at global scope, it stays at whatever state you set it
to until you change it.</p>
<p>If you do it at block scope, it reverts to the value outside the
block when the block ends.</p>
<p>The initial value of the <code>FP_CONTRACT</code> pragma varies from
system to system.</p>
<hr>
<h2 data-number="52.6" id="man-fpclassify"><span class="header-section-number">52.6</span> <code>fpclassify()</code></h2>
<p>Return the classification of a given floating point number.</p>
<h3 class="unnumbered unlisted" id="synopsis-54">Synopsis</h3>
<div class="sourceCode" id="cb972"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb972-1"><a href="math.html#cb972-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb972-2"><a href="math.html#cb972-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb972-3"><a href="math.html#cb972-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> fpclassify<span class="op">(</span>any_floating_type x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-54">Description</h3>
<p>What kind of entity does this floating point number represent? What
are the options?</p>
<p>We’re used to floating point numbers being regular old things like
<code>3.14</code> or <code>3490.0001</code>.</p>
<p>But floating point numbers can also represent things like infinity.
Or Not-A-Number (NAN). This function will let you know which type of
floating point number the argument is.</p>
<p>This is a macro, so you can use it with <code>float</code>,
<code>double</code>, <code>long double</code> or anything similar.</p>
<h3 class="unnumbered unlisted" id="return-value-53">Return Value</h3>
<p>Returns one of these macros depending on the argument’s
classification:</p>
<table>
<thead>
<tr class="header">
<th>Classification</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>FP_INFINITE</code></td>
<td>Number is infinite.</td>
</tr>
<tr class="even">
<td><code>FP_NAN</code></td>
<td>Number is Not-A-Number (NAN).</td>
</tr>
<tr class="odd">
<td><code>FP_NORMAL</code></td>
<td>Just a regular number.</td>
</tr>
<tr class="even">
<td><code>FP_SUBNORMAL</code></td>
<td>Number is a sub-normal number.</td>
</tr>
<tr class="odd">
<td><code>FP_ZERO</code></td>
<td>Number is zero.</td>
</tr>
</tbody>
</table>
<p>A discussion of subnormal numbers is beyond the scope of the guide,
and is something that most devs go their whole lives without dealing
with. In a nutshell, it’s a way to represent really small numbers that
might normally round down to zero. If you want to know more, see the
Wikipedia page on <a href="https://en.wikipedia.org/wiki/Denormal_number">denormal
numbers</a><a href="footnotes.html#fn230" class="footnote-ref" id="fnref230" role="doc-noteref"><sup>230</sup></a>.</p>
<h3 class="unnumbered unlisted" id="example-54">Example</h3>
<p>Print various number classifications.</p>
<div class="sourceCode" id="cb973"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb973-1"><a href="math.html#cb973-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb973-2"><a href="math.html#cb973-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb973-3"><a href="math.html#cb973-3"></a></span>
<span id="cb973-4"><a href="math.html#cb973-4"></a><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>get_classification<span class="op">(</span><span class="dt">double</span> n<span class="op">)</span></span>
<span id="cb973-5"><a href="math.html#cb973-5"></a><span class="op">{</span></span>
<span id="cb973-6"><a href="math.html#cb973-6"></a>    <span class="cf">switch</span> <span class="op">(</span>fpclassify<span class="op">(</span>n<span class="op">))</span> <span class="op">{</span></span>
<span id="cb973-7"><a href="math.html#cb973-7"></a>        <span class="cf">case</span> FP_INFINITE<span class="op">:</span> <span class="cf">return</span> <span class="st">"infinity"</span><span class="op">;</span></span>
<span id="cb973-8"><a href="math.html#cb973-8"></a>        <span class="cf">case</span> FP_NAN<span class="op">:</span> <span class="cf">return</span> <span class="st">"not a number"</span><span class="op">;</span></span>
<span id="cb973-9"><a href="math.html#cb973-9"></a>        <span class="cf">case</span> FP_NORMAL<span class="op">:</span> <span class="cf">return</span> <span class="st">"normal"</span><span class="op">;</span></span>
<span id="cb973-10"><a href="math.html#cb973-10"></a>        <span class="cf">case</span> FP_SUBNORMAL<span class="op">:</span> <span class="cf">return</span> <span class="st">"subnormal"</span><span class="op">;</span></span>
<span id="cb973-11"><a href="math.html#cb973-11"></a>        <span class="cf">case</span> FP_ZERO<span class="op">:</span> <span class="cf">return</span> <span class="st">"zero"</span><span class="op">;</span></span>
<span id="cb973-12"><a href="math.html#cb973-12"></a>    <span class="op">}</span></span>
<span id="cb973-13"><a href="math.html#cb973-13"></a></span>
<span id="cb973-14"><a href="math.html#cb973-14"></a>    <span class="cf">return</span> <span class="st">"unknown"</span><span class="op">;</span></span>
<span id="cb973-15"><a href="math.html#cb973-15"></a><span class="op">}</span></span>
<span id="cb973-16"><a href="math.html#cb973-16"></a> </span>
<span id="cb973-17"><a href="math.html#cb973-17"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb973-18"><a href="math.html#cb973-18"></a><span class="op">{</span></span>
<span id="cb973-19"><a href="math.html#cb973-19"></a>    printf<span class="op">(</span><span class="st">"    1.23: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> get_classification<span class="op">(</span><span class="fl">1.23</span><span class="op">));</span></span>
<span id="cb973-20"><a href="math.html#cb973-20"></a>    printf<span class="op">(</span><span class="st">"     0.0: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> get_classification<span class="op">(</span><span class="fl">0.0</span><span class="op">));</span></span>
<span id="cb973-21"><a href="math.html#cb973-21"></a>    printf<span class="op">(</span><span class="st">"sqrt(-1): %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> get_classification<span class="op">(</span>sqrt<span class="op">(-</span><span class="dv">1</span><span class="op">)));</span></span>
<span id="cb973-22"><a href="math.html#cb973-22"></a>    printf<span class="op">(</span><span class="st">"1/tan(0): %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> get_classification<span class="op">(</span><span class="dv">1</span><span class="op">/</span>tan<span class="op">(</span><span class="dv">0</span><span class="op">)));</span></span>
<span id="cb973-23"><a href="math.html#cb973-23"></a>    printf<span class="op">(</span><span class="st">"  1e-310: %s</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> get_classification<span class="op">(</span><span class="fl">1e-310</span><span class="op">));</span>  <span class="co">// very small!</span></span>
<span id="cb973-24"><a href="math.html#cb973-24"></a><span class="op">}</span></span></code></pre></div>
<p>Output<a href="footnotes.html#fn231" class="footnote-ref" id="fnref231" role="doc-noteref"><sup>231</sup></a>:</p>
<div class="sourceCode" id="cb974"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb974-1"><a href="math.html#cb974-1" aria-hidden="true" tabindex="-1"></a>    1.23: normal</span>
<span id="cb974-2"><a href="math.html#cb974-2" aria-hidden="true" tabindex="-1"></a>     0.0: zero</span>
<span id="cb974-3"><a href="math.html#cb974-3" aria-hidden="true" tabindex="-1"></a>sqrt(-1): not a number</span>
<span id="cb974-4"><a href="math.html#cb974-4" aria-hidden="true" tabindex="-1"></a>1/tan(0): infinity</span>
<span id="cb974-5"><a href="math.html#cb974-5" aria-hidden="true" tabindex="-1"></a>  1e-310: subnormal</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-50">See Also</h3>
<p><a href="math.html#man-isnan"><code>isfinite()</code></a>, <a href="#man-isnan"><code>isinf()</code></a>, <a href="#man-isnan"><code>isnan()</code></a>, <a href="#man-isnan"><code>isnormal()</code></a>, <a href="#man-signbit"><code>signbit()</code></a></p>
<hr>
<h2 data-number="52.7" id="man-isnan"><span class="header-section-number">52.7</span> <code>isfinite()</code>,
<code>isinf()</code>, <code>isnan()</code>, <code>isnormal()</code></h2>
<p>Return true if a number matches a classification.</p>
<h3 class="unnumbered unlisted" id="synopsis-55">Synopsis</h3>
<div class="sourceCode" id="cb975"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb975-1"><a href="math.html#cb975-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb975-2"><a href="math.html#cb975-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb975-3"><a href="math.html#cb975-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isfinite<span class="op">(</span>any_floating_type x<span class="op">);</span></span>
<span id="cb975-4"><a href="math.html#cb975-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb975-5"><a href="math.html#cb975-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isinf<span class="op">(</span>any_floating_type x<span class="op">);</span></span>
<span id="cb975-6"><a href="math.html#cb975-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb975-7"><a href="math.html#cb975-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isnan<span class="op">(</span>any_floating_type x<span class="op">);</span></span>
<span id="cb975-8"><a href="math.html#cb975-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb975-9"><a href="math.html#cb975-9" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isnormal<span class="op">(</span>any_floating_type x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-55">Description</h3>
<p>These are helper macros to <code>fpclassify()</code>. Bring macros,
they work on any floating point type.</p>
<table>
<thead>
<tr class="header">
<th>Macro</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>isfinite()</code></td>
<td>True if the number is not infinite or NaN.</td>
</tr>
<tr class="even">
<td><code>isinf()</code></td>
<td>True if the number is infinite.</td>
</tr>
<tr class="odd">
<td><code>isnan()</code></td>
<td>True if the number is Not-a-Number.</td>
</tr>
<tr class="even">
<td><code>isnormal()</code></td>
<td>True if the number is normal.</td>
</tr>
</tbody>
</table>
<p>For more superficial discussion on normal and subnormal numbers, see
<a href="math.html#man-fpclassify"><code>fpclassify()</code></a>.</p>
<h3 class="unnumbered unlisted" id="return-value-54">Return Value</h3>
<p>Returns non-zero for true, and zero for false.</p>
<h3 class="unnumbered unlisted" id="example-55">Example</h3>
<div class="sourceCode" id="cb976"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb976-1"><a href="math.html#cb976-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb976-2"><a href="math.html#cb976-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb976-3"><a href="math.html#cb976-3"></a></span>
<span id="cb976-4"><a href="math.html#cb976-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb976-5"><a href="math.html#cb976-5"></a><span class="op">{</span></span>
<span id="cb976-6"><a href="math.html#cb976-6"></a>    printf<span class="op">(</span><span class="st">"  isfinite(1.23): %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isfinite<span class="op">(</span><span class="fl">1.23</span><span class="op">));</span>    <span class="co">// 1</span></span>
<span id="cb976-7"><a href="math.html#cb976-7"></a>    printf<span class="op">(</span><span class="st">" isinf(1/tan(0)): %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isinf<span class="op">(</span><span class="dv">1</span><span class="op">/</span>tan<span class="op">(</span><span class="dv">0</span><span class="op">)));</span>   <span class="co">// 1</span></span>
<span id="cb976-8"><a href="math.html#cb976-8"></a>    printf<span class="op">(</span><span class="st">" isnan(sqrt(-1)): %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isnan<span class="op">(</span>sqrt<span class="op">(-</span><span class="dv">1</span><span class="op">)));</span>   <span class="co">// 1</span></span>
<span id="cb976-9"><a href="math.html#cb976-9"></a>    printf<span class="op">(</span><span class="st">"isnormal(1e-310): %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isnormal<span class="op">(</span><span class="fl">1e-310</span><span class="op">));</span>  <span class="co">// 0</span></span>
<span id="cb976-10"><a href="math.html#cb976-10"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-51">See Also</h3>
<p><a href="math.html#man-fpclassify"><code>fpclassify()</code></a>, <a href="#man-signbit"><code>signbit()</code></a>,</p>
<hr>
<h2 data-number="52.8" id="man-signbit"><span class="header-section-number">52.8</span> <code>signbit()</code></h2>
<p>Return the sign of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-56">Synopsis</h3>
<div class="sourceCode" id="cb977"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb977-1"><a href="math.html#cb977-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb977-2"><a href="math.html#cb977-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb977-3"><a href="math.html#cb977-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> signbit<span class="op">(</span>any_floating_type x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-56">Description</h3>
<p>This macro takes any floating point number and returns a value
indicating the sign of the number, positive or negative.</p>
<h3 class="unnumbered unlisted" id="return-value-55">Return Value</h3>
<p>Returns <code>1</code> if the sign is negative, otherwise
<code>0</code>.</p>
<h3 class="unnumbered unlisted" id="example-56">Example</h3>
<div class="sourceCode" id="cb978"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb978-1"><a href="math.html#cb978-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb978-2"><a href="math.html#cb978-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb978-3"><a href="math.html#cb978-3"></a></span>
<span id="cb978-4"><a href="math.html#cb978-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb978-5"><a href="math.html#cb978-5"></a><span class="op">{</span></span>
<span id="cb978-6"><a href="math.html#cb978-6"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> signbit<span class="op">(</span><span class="fl">3490.0</span><span class="op">));</span>  <span class="co">// 0</span></span>
<span id="cb978-7"><a href="math.html#cb978-7"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> signbit<span class="op">(-</span><span class="fl">37.0</span><span class="op">));</span>   <span class="co">// 1</span></span>
<span id="cb978-8"><a href="math.html#cb978-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-52">See Also</h3>
<p><a href="math.html#man-fpclassify"><code>fpclassify()</code></a>, <a href="#man-isnan"><code>isfinite()</code></a>, <a href="#man-isnan"><code>isinf()</code></a>, <a href="#man-isnan"><code>isnan()</code></a>, <a href="#man-isnan"><code>isnormal()</code></a>, <a href="#man-copysign"><code>copysign()</code></a></p>
<hr>
<h2 data-number="52.9" id="man-acos"><span class="header-section-number">52.9</span> <code>acos()</code>,
<code>acosf()</code>, <code>acosl()</code></h2>
<p>Calculate the arc cosine of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-57">Synopsis</h3>
<div class="sourceCode" id="cb979"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb979-1"><a href="math.html#cb979-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb979-2"><a href="math.html#cb979-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb979-3"><a href="math.html#cb979-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> acos<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb979-4"><a href="math.html#cb979-4" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> acosf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb979-5"><a href="math.html#cb979-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> acosl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-57">Description</h3>
<p>Calculates the arc cosine of a number in radians. (That is, the value
whose cosine is <code>x</code>.) The number must be in the range -1.0 to
1.0.</p>
<p>For those of you who don’t remember, radians are another way of
measuring an angle, just like degrees. To convert from degrees to
radians or the other way around, use the following code:</p>
<div class="sourceCode" id="cb980"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb980-1"><a href="math.html#cb980-1" aria-hidden="true" tabindex="-1"></a>pi <span class="op">=</span> <span class="fl">3.14159265358979</span><span class="op">;</span></span>
<span id="cb980-2"><a href="math.html#cb980-2" aria-hidden="true" tabindex="-1"></a>degrees <span class="op">=</span> radians <span class="op">*</span> <span class="dv">180</span> <span class="op">/</span> pi<span class="op">;</span></span>
<span id="cb980-3"><a href="math.html#cb980-3" aria-hidden="true" tabindex="-1"></a>radians <span class="op">=</span> degrees <span class="op">*</span> pi <span class="op">/</span> <span class="dv">180</span><span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-56">Return Value</h3>
<p>Returns the arc cosine of <code>x</code>, unless <code>x</code> is
out of range. In that case, <code>errno</code> will be set to EDOM and
the return value will be NaN. The variants return different types.</p>
<h3 class="unnumbered unlisted" id="example-57">Example</h3>
<div class="sourceCode" id="cb981"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb981-1"><a href="math.html#cb981-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb981-2"><a href="math.html#cb981-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb981-3"><a href="math.html#cb981-3"></a></span>
<span id="cb981-4"><a href="math.html#cb981-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb981-5"><a href="math.html#cb981-5"></a><span class="op">{</span></span>
<span id="cb981-6"><a href="math.html#cb981-6"></a>    <span class="dt">double</span> acosx<span class="op">;</span></span>
<span id="cb981-7"><a href="math.html#cb981-7"></a>    <span class="dt">long</span> <span class="dt">double</span> ldacosx<span class="op">;</span></span>
<span id="cb981-8"><a href="math.html#cb981-8"></a></span>
<span id="cb981-9"><a href="math.html#cb981-9"></a>    acosx <span class="op">=</span> acos<span class="op">(</span><span class="fl">0.2</span><span class="op">);</span></span>
<span id="cb981-10"><a href="math.html#cb981-10"></a>    ldacosx <span class="op">=</span> acosl<span class="op">(</span><span class="fl">0.3</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb981-11"><a href="math.html#cb981-11"></a></span>
<span id="cb981-12"><a href="math.html#cb981-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> acosx<span class="op">);</span></span>
<span id="cb981-13"><a href="math.html#cb981-13"></a>    printf<span class="op">(</span><span class="st">"%Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldacosx<span class="op">);</span></span>
<span id="cb981-14"><a href="math.html#cb981-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-53">See Also</h3>
<p><a href="math.html#man-asin"><code>asin()</code></a>, <a href="#man-atan"><code>atan()</code></a>, <a href="#man-atan"><code>atan2()</code></a>, <a href="#man-cos"><code>cos()</code></a></p>
<hr>
<h2 data-number="52.10" id="man-asin"><span class="header-section-number">52.10</span> <code>asin()</code>,
<code>asinf()</code>, <code>asinl()</code></h2>
<p>Calculate the arc sine of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-58">Synopsis</h3>
<div class="sourceCode" id="cb982"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb982-1"><a href="math.html#cb982-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb982-2"><a href="math.html#cb982-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb982-3"><a href="math.html#cb982-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> asin<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb982-4"><a href="math.html#cb982-4" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> asinf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb982-5"><a href="math.html#cb982-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> asinl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-58">Description</h3>
<p>Calculates the arc sine of a number in radians. (That is, the value
whose sine is <code>x</code>.) The number must be in the range -1.0 to
1.0.</p>
<p>For those of you who don’t remember, radians are another way of
measuring an angle, just like degrees. To convert from degrees to
radians or the other way around, use the following code:</p>
<div class="sourceCode" id="cb983"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb983-1"><a href="math.html#cb983-1" aria-hidden="true" tabindex="-1"></a>pi <span class="op">=</span> <span class="fl">3.14159265358979</span><span class="op">;</span></span>
<span id="cb983-2"><a href="math.html#cb983-2" aria-hidden="true" tabindex="-1"></a>degrees <span class="op">=</span> radians <span class="op">*</span> <span class="dv">180</span> <span class="op">/</span> pi<span class="op">;</span></span>
<span id="cb983-3"><a href="math.html#cb983-3" aria-hidden="true" tabindex="-1"></a>radians <span class="op">=</span> degrees <span class="op">*</span> pi <span class="op">/</span> <span class="dv">180</span><span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-57">Return Value</h3>
<p>Returns the arc sine of <code>x</code>, unless <code>x</code> is out
of range. In that case, <code>errno</code> will be set to EDOM and the
return value will be NaN. The variants return different types.</p>
<h3 class="unnumbered unlisted" id="example-58">Example</h3>
<div class="sourceCode" id="cb984"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb984-1"><a href="math.html#cb984-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb984-2"><a href="math.html#cb984-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb984-3"><a href="math.html#cb984-3"></a></span>
<span id="cb984-4"><a href="math.html#cb984-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb984-5"><a href="math.html#cb984-5"></a><span class="op">{</span></span>
<span id="cb984-6"><a href="math.html#cb984-6"></a>    <span class="dt">double</span> asinx<span class="op">;</span></span>
<span id="cb984-7"><a href="math.html#cb984-7"></a>    <span class="dt">long</span> <span class="dt">double</span> ldasinx<span class="op">;</span></span>
<span id="cb984-8"><a href="math.html#cb984-8"></a></span>
<span id="cb984-9"><a href="math.html#cb984-9"></a>    asinx <span class="op">=</span> asin<span class="op">(</span><span class="fl">0.2</span><span class="op">);</span></span>
<span id="cb984-10"><a href="math.html#cb984-10"></a>    ldasinx <span class="op">=</span> asinl<span class="op">(</span><span class="fl">0.3</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb984-11"><a href="math.html#cb984-11"></a></span>
<span id="cb984-12"><a href="math.html#cb984-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> asinx<span class="op">);</span></span>
<span id="cb984-13"><a href="math.html#cb984-13"></a>    printf<span class="op">(</span><span class="st">"%Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldasinx<span class="op">);</span></span>
<span id="cb984-14"><a href="math.html#cb984-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-54">See Also</h3>
<p><a href="math.html#man-acos"><code>acos()</code></a>, <a href="#man-atan"><code>atan()</code></a>, <a href="#man-atan"><code>atan2()</code></a>, <a href="#man-sin"><code>sin()</code></a></p>
<hr>
<h2 data-number="52.11" id="man-atan"><span class="header-section-number">52.11</span> <code>atan()</code>,
<code>atanf()</code>, <code>atanl()</code>, <code>atan2()</code>,
<code>atan2f()</code>, <code>atan2l()</code></h2>
<p>Calculate the arc tangent of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-59">Synopsis</h3>
<div class="sourceCode" id="cb985"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb985-1"><a href="math.html#cb985-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb985-2"><a href="math.html#cb985-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb985-3"><a href="math.html#cb985-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> atan<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb985-4"><a href="math.html#cb985-4" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> atanf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb985-5"><a href="math.html#cb985-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> atanl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb985-6"><a href="math.html#cb985-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb985-7"><a href="math.html#cb985-7" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> atan2<span class="op">(</span><span class="dt">double</span> y<span class="op">,</span> <span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb985-8"><a href="math.html#cb985-8" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> atan2f<span class="op">(</span><span class="dt">float</span> y<span class="op">,</span> <span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb985-9"><a href="math.html#cb985-9" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> atan2l<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> y<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-59">Description</h3>
<p>Calculates the arc tangent of a number in radians. (That is, the
value whose tangent is <code>x</code>.)</p>
<p>The <code>atan2()</code> variants are pretty much the same as using
<code>atan()</code> with <code>y</code>/<code>x</code> as the
argument…except that <code>atan2()</code> will use those values to
determine the correct quadrant of the result.</p>
<p>For those of you who don’t remember, radians are another way of
measuring an angle, just like degrees. To convert from degrees to
radians or the other way around, use the following code:</p>
<div class="sourceCode" id="cb986"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb986-1"><a href="math.html#cb986-1" aria-hidden="true" tabindex="-1"></a>pi <span class="op">=</span> <span class="fl">3.14159265358979</span><span class="op">;</span></span>
<span id="cb986-2"><a href="math.html#cb986-2" aria-hidden="true" tabindex="-1"></a>degrees <span class="op">=</span> radians <span class="op">*</span> <span class="dv">180</span> <span class="op">/</span> pi<span class="op">;</span></span>
<span id="cb986-3"><a href="math.html#cb986-3" aria-hidden="true" tabindex="-1"></a>radians <span class="op">=</span> degrees <span class="op">*</span> pi <span class="op">/</span> <span class="dv">180</span><span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-58">Return Value</h3>
<p>The <code>atan()</code> functions return the arc tangent of
<code>x</code>, which will be between PI/2 and -PI/2. The
<code>atan2()</code> functions return an angle between PI and -PI.</p>
<h3 class="unnumbered unlisted" id="example-59">Example</h3>
<div class="sourceCode" id="cb987"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb987-1"><a href="math.html#cb987-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb987-2"><a href="math.html#cb987-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb987-3"><a href="math.html#cb987-3"></a></span>
<span id="cb987-4"><a href="math.html#cb987-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb987-5"><a href="math.html#cb987-5"></a><span class="op">{</span></span>
<span id="cb987-6"><a href="math.html#cb987-6"></a>    <span class="dt">double</span> atanx<span class="op">;</span></span>
<span id="cb987-7"><a href="math.html#cb987-7"></a>    <span class="dt">long</span> <span class="dt">double</span> ldatanx<span class="op">;</span></span>
<span id="cb987-8"><a href="math.html#cb987-8"></a></span>
<span id="cb987-9"><a href="math.html#cb987-9"></a>    atanx <span class="op">=</span> atan<span class="op">(</span><span class="fl">0.7</span><span class="op">);</span></span>
<span id="cb987-10"><a href="math.html#cb987-10"></a>    ldatanx <span class="op">=</span> atanl<span class="op">(</span><span class="fl">0.3</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb987-11"><a href="math.html#cb987-11"></a></span>
<span id="cb987-12"><a href="math.html#cb987-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> atanx<span class="op">);</span></span>
<span id="cb987-13"><a href="math.html#cb987-13"></a>    printf<span class="op">(</span><span class="st">"%Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldatanx<span class="op">);</span></span>
<span id="cb987-14"><a href="math.html#cb987-14"></a></span>
<span id="cb987-15"><a href="math.html#cb987-15"></a>    atanx <span class="op">=</span> atan2<span class="op">(</span><span class="dv">7</span><span class="op">,</span> <span class="dv">10</span><span class="op">);</span></span>
<span id="cb987-16"><a href="math.html#cb987-16"></a>    ldatanx <span class="op">=</span> atan2l<span class="op">(</span><span class="dv">3</span><span class="bu">L</span><span class="op">,</span> <span class="dv">10</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb987-17"><a href="math.html#cb987-17"></a></span>
<span id="cb987-18"><a href="math.html#cb987-18"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> atanx<span class="op">);</span></span>
<span id="cb987-19"><a href="math.html#cb987-19"></a>    printf<span class="op">(</span><span class="st">"%Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldatanx<span class="op">);</span></span>
<span id="cb987-20"><a href="math.html#cb987-20"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-55">See Also</h3>
<p><a href="math.html#man-tan"><code>tan()</code></a>, <a href="#man-asin"><code>asin()</code></a>, <a href="#man-acos"><code>atan()</code></a></p>
<hr>
<h2 data-number="52.12" id="man-cos"><span class="header-section-number">52.12</span> <code>cos()</code>,
<code>cosf()</code>, <code>cosl()</code></h2>
<p>Calculate the cosine of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-60">Synopsis</h3>
<div class="sourceCode" id="cb988"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb988-1"><a href="math.html#cb988-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb988-2"><a href="math.html#cb988-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb988-3"><a href="math.html#cb988-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> cos<span class="op">(</span><span class="dt">double</span> x<span class="op">)</span></span>
<span id="cb988-4"><a href="math.html#cb988-4" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> cosf<span class="op">(</span><span class="dt">float</span> x<span class="op">)</span></span>
<span id="cb988-5"><a href="math.html#cb988-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> cosl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-60">Description</h3>
<p>Calculates the cosine of the value <code>x</code>, where
<code>x</code> is in radians.</p>
<p>For those of you who don’t remember, radians are another way of
measuring an angle, just like degrees. To convert from degrees to
radians or the other way around, use the following code:</p>
<div class="sourceCode" id="cb989"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb989-1"><a href="math.html#cb989-1" aria-hidden="true" tabindex="-1"></a>pi <span class="op">=</span> <span class="fl">3.14159265358979</span><span class="op">;</span></span>
<span id="cb989-2"><a href="math.html#cb989-2" aria-hidden="true" tabindex="-1"></a>degrees <span class="op">=</span> radians <span class="op">*</span> <span class="dv">180</span> <span class="op">/</span> pi<span class="op">;</span></span>
<span id="cb989-3"><a href="math.html#cb989-3" aria-hidden="true" tabindex="-1"></a>radians <span class="op">=</span> degrees <span class="op">*</span> pi <span class="op">/</span> <span class="dv">180</span><span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-59">Return Value</h3>
<p>Returns the cosine of <code>x</code>. The variants return different
types.</p>
<h3 class="unnumbered unlisted" id="example-60">Example</h3>
<div class="sourceCode" id="cb990"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb990-1"><a href="math.html#cb990-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb990-2"><a href="math.html#cb990-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb990-3"><a href="math.html#cb990-3"></a></span>
<span id="cb990-4"><a href="math.html#cb990-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb990-5"><a href="math.html#cb990-5"></a><span class="op">{</span></span>
<span id="cb990-6"><a href="math.html#cb990-6"></a>    <span class="dt">double</span> cosx<span class="op">;</span></span>
<span id="cb990-7"><a href="math.html#cb990-7"></a>    <span class="dt">long</span> <span class="dt">double</span> ldcosx<span class="op">;</span></span>
<span id="cb990-8"><a href="math.html#cb990-8"></a></span>
<span id="cb990-9"><a href="math.html#cb990-9"></a>    cosx <span class="op">=</span> cos<span class="op">(</span><span class="fl">3490.0</span><span class="op">);</span> <span class="co">// round and round we go!</span></span>
<span id="cb990-10"><a href="math.html#cb990-10"></a>    ldcosx <span class="op">=</span> cosl<span class="op">(</span><span class="fl">3.490</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb990-11"><a href="math.html#cb990-11"></a></span>
<span id="cb990-12"><a href="math.html#cb990-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> cosx<span class="op">);</span></span>
<span id="cb990-13"><a href="math.html#cb990-13"></a>    printf<span class="op">(</span><span class="st">"%Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldcosx<span class="op">);</span></span>
<span id="cb990-14"><a href="math.html#cb990-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-56">See Also</h3>
<p><a href="math.html#man-sin"><code>sin()</code></a>, <a href="#man-tan"><code>tan()</code></a>, <a href="#man-acos"><code>acos()</code></a></p>
<hr>
<h2 data-number="52.13" id="man-sin"><span class="header-section-number">52.13</span> <code>sin()</code>,
<code>sinf()</code>, <code>sinl()</code></h2>
<p>Calculate the sine of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-61">Synopsis</h3>
<div class="sourceCode" id="cb991"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb991-1"><a href="math.html#cb991-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb991-2"><a href="math.html#cb991-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb991-3"><a href="math.html#cb991-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> sin<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb991-4"><a href="math.html#cb991-4" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> sinf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb991-5"><a href="math.html#cb991-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> sinl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-61">Description</h3>
<p>Calculates the sine of the value <code>x</code>, where <code>x</code>
is in radians.</p>
<p>For those of you who don’t remember, radians are another way of
measuring an angle, just like degrees. To convert from degrees to
radians or the other way around, use the following code:</p>
<div class="sourceCode" id="cb992"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb992-1"><a href="math.html#cb992-1" aria-hidden="true" tabindex="-1"></a>pi <span class="op">=</span> <span class="fl">3.14159265358979</span><span class="op">;</span></span>
<span id="cb992-2"><a href="math.html#cb992-2" aria-hidden="true" tabindex="-1"></a>degrees <span class="op">=</span> radians <span class="op">*</span> <span class="dv">180</span> <span class="op">/</span> pi<span class="op">;</span></span>
<span id="cb992-3"><a href="math.html#cb992-3" aria-hidden="true" tabindex="-1"></a>radians <span class="op">=</span> degrees <span class="op">*</span> pi <span class="op">/</span> <span class="dv">180</span><span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-60">Return Value</h3>
<p>Returns the sine of <code>x</code>. The variants return different
types.</p>
<h3 class="unnumbered unlisted" id="example-61">Example</h3>
<div class="sourceCode" id="cb993"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb993-1"><a href="math.html#cb993-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb993-2"><a href="math.html#cb993-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb993-3"><a href="math.html#cb993-3"></a></span>
<span id="cb993-4"><a href="math.html#cb993-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb993-5"><a href="math.html#cb993-5"></a><span class="op">{</span></span>
<span id="cb993-6"><a href="math.html#cb993-6"></a>    <span class="dt">double</span> sinx<span class="op">;</span></span>
<span id="cb993-7"><a href="math.html#cb993-7"></a>    <span class="dt">long</span> <span class="dt">double</span> ldsinx<span class="op">;</span></span>
<span id="cb993-8"><a href="math.html#cb993-8"></a></span>
<span id="cb993-9"><a href="math.html#cb993-9"></a>    sinx <span class="op">=</span> sin<span class="op">(</span><span class="fl">3490.0</span><span class="op">);</span> <span class="co">// round and round we go!</span></span>
<span id="cb993-10"><a href="math.html#cb993-10"></a>    ldsinx <span class="op">=</span> sinl<span class="op">(</span><span class="fl">3.490</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb993-11"><a href="math.html#cb993-11"></a></span>
<span id="cb993-12"><a href="math.html#cb993-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> sinx<span class="op">);</span></span>
<span id="cb993-13"><a href="math.html#cb993-13"></a>    printf<span class="op">(</span><span class="st">"%Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldsinx<span class="op">);</span></span>
<span id="cb993-14"><a href="math.html#cb993-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-57">See Also</h3>
<p><a href="math.html#man-cos"><code>cos()</code></a>, <a href="#man-tan"><code>tan()</code></a>, <a href="#man-asin"><code>asin()</code></a></p>
<hr>
<h2 data-number="52.14" id="man-tan"><span class="header-section-number">52.14</span> <code>tan()</code>,
<code>tanf()</code>, <code>tanl()</code></h2>
<p>Calculate the tangent of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-62">Synopsis</h3>
<div class="sourceCode" id="cb994"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb994-1"><a href="math.html#cb994-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb994-2"><a href="math.html#cb994-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb994-3"><a href="math.html#cb994-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> tan<span class="op">(</span><span class="dt">double</span> x<span class="op">)</span></span>
<span id="cb994-4"><a href="math.html#cb994-4" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> tanf<span class="op">(</span><span class="dt">float</span> x<span class="op">)</span></span>
<span id="cb994-5"><a href="math.html#cb994-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> tanl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">)</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-62">Description</h3>
<p>Calculates the tangent of the value <code>x</code>, where
<code>x</code> is in radians.</p>
<p>For those of you who don’t remember, radians are another way of
measuring an angle, just like degrees. To convert from degrees to
radians or the other way around, use the following code:</p>
<div class="sourceCode" id="cb995"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb995-1"><a href="math.html#cb995-1" aria-hidden="true" tabindex="-1"></a>pi <span class="op">=</span> <span class="fl">3.14159265358979</span><span class="op">;</span></span>
<span id="cb995-2"><a href="math.html#cb995-2" aria-hidden="true" tabindex="-1"></a>degrees <span class="op">=</span> radians <span class="op">*</span> <span class="dv">180</span> <span class="op">/</span> pi<span class="op">;</span></span>
<span id="cb995-3"><a href="math.html#cb995-3" aria-hidden="true" tabindex="-1"></a>radians <span class="op">=</span> degrees <span class="op">*</span> pi <span class="op">/</span> <span class="dv">180</span><span class="op">;</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="return-value-61">Return Value</h3>
<p>Returns the tangent of <code>x</code>. The variants return different
types.</p>
<h3 class="unnumbered unlisted" id="example-62">Example</h3>
<div class="sourceCode" id="cb996"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb996-1"><a href="math.html#cb996-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb996-2"><a href="math.html#cb996-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb996-3"><a href="math.html#cb996-3"></a></span>
<span id="cb996-4"><a href="math.html#cb996-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb996-5"><a href="math.html#cb996-5"></a><span class="op">{</span></span>
<span id="cb996-6"><a href="math.html#cb996-6"></a>    <span class="dt">double</span> tanx<span class="op">;</span></span>
<span id="cb996-7"><a href="math.html#cb996-7"></a>    <span class="dt">long</span> <span class="dt">double</span> ldtanx<span class="op">;</span></span>
<span id="cb996-8"><a href="math.html#cb996-8"></a></span>
<span id="cb996-9"><a href="math.html#cb996-9"></a>    tanx <span class="op">=</span> tan<span class="op">(</span><span class="fl">3490.0</span><span class="op">);</span> <span class="co">// round and round we go!</span></span>
<span id="cb996-10"><a href="math.html#cb996-10"></a>    ldtanx <span class="op">=</span> tanl<span class="op">(</span><span class="fl">3.490</span><span class="bu">L</span><span class="op">);</span></span>
<span id="cb996-11"><a href="math.html#cb996-11"></a></span>
<span id="cb996-12"><a href="math.html#cb996-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tanx<span class="op">);</span></span>
<span id="cb996-13"><a href="math.html#cb996-13"></a>    printf<span class="op">(</span><span class="st">"%Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldtanx<span class="op">);</span></span>
<span id="cb996-14"><a href="math.html#cb996-14"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-58">See Also</h3>
<p><a href="math.html#man-sin"><code>sin()</code></a>, <a href="#man-cos"><code>cos()</code></a>, <a href="#man-atan"><code>atan()</code></a>, <a href="#man-atan"><code>atan2()</code></a></p>
<hr>
<h2 data-number="52.15" id="man-acosh"><span class="header-section-number">52.15</span> <code>acosh()</code>,
<code>acoshf()</code>, <code>acoshl()</code></h2>
<p>Compute arc hyperbolic cosine.</p>
<h3 class="unnumbered unlisted" id="synopsis-63">Synopsis</h3>
<div class="sourceCode" id="cb997"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb997-1"><a href="math.html#cb997-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb997-2"><a href="math.html#cb997-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb997-3"><a href="math.html#cb997-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> acosh<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb997-4"><a href="math.html#cb997-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb997-5"><a href="math.html#cb997-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> acoshf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb997-6"><a href="math.html#cb997-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb997-7"><a href="math.html#cb997-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> acoshl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-63">Description</h3>
<p>Trig lovers can rejoice! C has arc hyperbolic cosine!</p>
<p>These functions return the nonnegative acosh of <code>x</code>, which
must be greater than or equal to <code>1</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-62">Return Value</h3>
<p>Returns the arc hyperbolic cosince in the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-n"><mjx-c class="mjx-c221E"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>0</mn><mo>,</mo><mo>+</mo><mi mathvariant="normal">∞</mi><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-63">Example</h3>
<div class="sourceCode" id="cb998"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb998-1"><a href="math.html#cb998-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb998-2"><a href="math.html#cb998-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb998-3"><a href="math.html#cb998-3"></a></span>
<span id="cb998-4"><a href="math.html#cb998-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb998-5"><a href="math.html#cb998-5"></a><span class="op">{</span></span>
<span id="cb998-6"><a href="math.html#cb998-6"></a>    printf<span class="op">(</span><span class="st">"acosh 1.8 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> acosh<span class="op">(</span><span class="fl">1.8</span><span class="op">));</span>  <span class="co">// 1.192911</span></span>
<span id="cb998-7"><a href="math.html#cb998-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-59">See Also</h3>
<p><a href="math.html#man-asinh"><code>asinh()</code></a></p>
<hr>
<h2 data-number="52.16" id="man-asinh"><span class="header-section-number">52.16</span> <code>asinh()</code>,
<code>asinhf()</code>, <code>asinhl()</code></h2>
<p>Compute arc hyperbolic sine.</p>
<h3 class="unnumbered unlisted" id="synopsis-64">Synopsis</h3>
<div class="sourceCode" id="cb999"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb999-1"><a href="math.html#cb999-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb999-2"><a href="math.html#cb999-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb999-3"><a href="math.html#cb999-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> asinh<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb999-4"><a href="math.html#cb999-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb999-5"><a href="math.html#cb999-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> asinhf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb999-6"><a href="math.html#cb999-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb999-7"><a href="math.html#cb999-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> asinhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-64">Description</h3>
<p>Trig lovers can rejoice! C has arc hyperbolic sine!</p>
<p>These functions return the asinh of <code>x</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-63">Return Value</h3>
<p>Returns the arc hyperbolic sine.</p>
<h3 class="unnumbered unlisted" id="example-64">Example</h3>
<div class="sourceCode" id="cb1000"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1000-1"><a href="math.html#cb1000-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1000-2"><a href="math.html#cb1000-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1000-3"><a href="math.html#cb1000-3"></a></span>
<span id="cb1000-4"><a href="math.html#cb1000-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1000-5"><a href="math.html#cb1000-5"></a><span class="op">{</span></span>
<span id="cb1000-6"><a href="math.html#cb1000-6"></a>    printf<span class="op">(</span><span class="st">"asinh 1.8 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> asinh<span class="op">(</span><span class="fl">1.8</span><span class="op">));</span>  <span class="co">// 1.350441</span></span>
<span id="cb1000-7"><a href="math.html#cb1000-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-60">See Also</h3>
<p><a href="math.html#man-acosh"><code>acosh()</code></a></p>
<hr>
<h2 data-number="52.17" id="man-atanh"><span class="header-section-number">52.17</span> <code>atanh()</code>,
<code>atanhf()</code>, <code>atanhl()</code></h2>
<p>Compute the arc hyperbolic tangent.</p>
<h3 class="unnumbered unlisted" id="synopsis-65">Synopsis</h3>
<div class="sourceCode" id="cb1001"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1001-1"><a href="math.html#cb1001-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1001-2"><a href="math.html#cb1001-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1001-3"><a href="math.html#cb1001-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> atanh<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1001-4"><a href="math.html#cb1001-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1001-5"><a href="math.html#cb1001-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> atanhf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1001-6"><a href="math.html#cb1001-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1001-7"><a href="math.html#cb1001-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> atanhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-65">Description</h3>
<p>These functions compute the arc hyperbolic tangent of <code>x</code>,
which must be in the range <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c5B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c5D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mo>−</mo><mn>1</mn><mo>,</mo><mo>+</mo><mn>1</mn><mo stretchy="false">]</mo></math></mjx-assistive-mml></mjx-container></span>.
Passing exactly <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> or <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>+</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> might result in a pole error.</p>
<h3 class="unnumbered unlisted" id="return-value-64">Return Value</h3>
<p>Returns the arc hyperbolic tangent of <code>x</code>.</p>
<h3 class="unnumbered unlisted" id="example-65">Example</h3>
<div class="sourceCode" id="cb1002"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1002-1"><a href="math.html#cb1002-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1002-2"><a href="math.html#cb1002-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1002-3"><a href="math.html#cb1002-3"></a></span>
<span id="cb1002-4"><a href="math.html#cb1002-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1002-5"><a href="math.html#cb1002-5"></a><span class="op">{</span></span>
<span id="cb1002-6"><a href="math.html#cb1002-6"></a>    printf<span class="op">(</span><span class="st">"atanh 0.5 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> atanh<span class="op">(</span><span class="fl">0.5</span><span class="op">));</span>  <span class="co">// 0.549306</span></span>
<span id="cb1002-7"><a href="math.html#cb1002-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-61">See Also</h3>
<p><a href="math.html#man-acosh"><code>acosh()</code></a>, <a href="#man-asinh"><code>asinh()</code></a></p>
<hr>
<h2 data-number="52.18" id="man-cosh"><span class="header-section-number">52.18</span> <code>cosh()</code>,
<code>coshf()</code>, <code>coshl()</code></h2>
<p>Compute the hyperbolic cosine.</p>
<h3 class="unnumbered unlisted" id="synopsis-66">Synopsis</h3>
<div class="sourceCode" id="cb1003"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1003-1"><a href="math.html#cb1003-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1003-2"><a href="math.html#cb1003-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1003-3"><a href="math.html#cb1003-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> cosh<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1003-4"><a href="math.html#cb1003-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1003-5"><a href="math.html#cb1003-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> coshf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1003-6"><a href="math.html#cb1003-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1003-7"><a href="math.html#cb1003-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> coshl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-66">Description</h3>
<p>These functions predictably compute the hyperbolic cosine of
<code>x</code>. A range error might occur if <code>x</code> is too
large.</p>
<h3 class="unnumbered unlisted" id="return-value-65">Return Value</h3>
<p>Returns the hyperbolic cosine of <code>x</code>.</p>
<h3 class="unnumbered unlisted" id="example-66">Example</h3>
<div class="sourceCode" id="cb1004"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1004-1"><a href="math.html#cb1004-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1004-2"><a href="math.html#cb1004-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1004-3"><a href="math.html#cb1004-3"></a></span>
<span id="cb1004-4"><a href="math.html#cb1004-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1004-5"><a href="math.html#cb1004-5"></a><span class="op">{</span></span>
<span id="cb1004-6"><a href="math.html#cb1004-6"></a>    printf<span class="op">(</span><span class="st">"cosh 0.5 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> cosh<span class="op">(</span><span class="fl">0.5</span><span class="op">));</span>  <span class="co">// 1.127626</span></span>
<span id="cb1004-7"><a href="math.html#cb1004-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-62">See Also</h3>
<p><a href="math.html#man-sinh"><code>sinh()</code></a>, <a href="#man-tanh"><code>tanh()</code></a></p>
<hr>
<h2 data-number="52.19" id="man-sinh"><span class="header-section-number">52.19</span> <code>sinh()</code>,
<code>sinhf()</code>, <code>sinhl()</code></h2>
<p>Compute the hyperbolic sine.</p>
<h3 class="unnumbered unlisted" id="synopsis-67">Synopsis</h3>
<div class="sourceCode" id="cb1005"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1005-1"><a href="math.html#cb1005-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1005-2"><a href="math.html#cb1005-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1005-3"><a href="math.html#cb1005-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> sinh<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1005-4"><a href="math.html#cb1005-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1005-5"><a href="math.html#cb1005-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> sinhf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1005-6"><a href="math.html#cb1005-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1005-7"><a href="math.html#cb1005-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> sinhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-67">Description</h3>
<p>These functions predictably compute the hyperbolic sine of
<code>x</code>. A range error might occur if <code>x</code> is too
large.</p>
<h3 class="unnumbered unlisted" id="return-value-66">Return Value</h3>
<p>Returns the hyperbolic sine of <code>x</code>.</p>
<h3 class="unnumbered unlisted" id="example-67">Example</h3>
<div class="sourceCode" id="cb1006"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1006-1"><a href="math.html#cb1006-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1006-2"><a href="math.html#cb1006-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1006-3"><a href="math.html#cb1006-3"></a></span>
<span id="cb1006-4"><a href="math.html#cb1006-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1006-5"><a href="math.html#cb1006-5"></a><span class="op">{</span></span>
<span id="cb1006-6"><a href="math.html#cb1006-6"></a>    printf<span class="op">(</span><span class="st">"sinh 0.5 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> sinh<span class="op">(</span><span class="fl">0.5</span><span class="op">));</span>  <span class="co">// 0.521095</span></span>
<span id="cb1006-7"><a href="math.html#cb1006-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-63">See Also</h3>
<p><a href="math.html#man-cosh"><code>sinh()</code></a>, <a href="#man-tanh"><code>tanh()</code></a></p>
<hr>
<h2 data-number="52.20" id="man-tanh"><span class="header-section-number">52.20</span> <code>tanh()</code>,
<code>tanhf()</code>, <code>tanhl()</code></h2>
<p>Compute the hyperbolic tangent.</p>
<h3 class="unnumbered unlisted" id="synopsis-68">Synopsis</h3>
<div class="sourceCode" id="cb1007"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1007-1"><a href="math.html#cb1007-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1007-2"><a href="math.html#cb1007-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1007-3"><a href="math.html#cb1007-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> tanh<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1007-4"><a href="math.html#cb1007-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1007-5"><a href="math.html#cb1007-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> tanhf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1007-6"><a href="math.html#cb1007-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1007-7"><a href="math.html#cb1007-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> tanhl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-68">Description</h3>
<p>These functions predictably compute the hyperbolic tangent of
<code>x</code>.</p>
<p>Mercifully, this is the last trig-related man page I’m going to
write.</p>
<h3 class="unnumbered unlisted" id="return-value-67">Return Value</h3>
<p>Returns the hyperbolic tangent of <code>x</code>.</p>
<h3 class="unnumbered unlisted" id="example-68">Example</h3>
<div class="sourceCode" id="cb1008"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1008-1"><a href="math.html#cb1008-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1008-2"><a href="math.html#cb1008-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1008-3"><a href="math.html#cb1008-3"></a></span>
<span id="cb1008-4"><a href="math.html#cb1008-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1008-5"><a href="math.html#cb1008-5"></a><span class="op">{</span></span>
<span id="cb1008-6"><a href="math.html#cb1008-6"></a>    printf<span class="op">(</span><span class="st">"tanh 0.5 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> tanh<span class="op">(</span><span class="fl">0.5</span><span class="op">));</span>  <span class="co">// 0.462117</span></span>
<span id="cb1008-7"><a href="math.html#cb1008-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-64">See Also</h3>
<p><a href="math.html#man-cosh"><code>cosh()</code></a>, <a href="#man-sinh"><code>sinh()</code></a></p>
<hr>
<h2 data-number="52.21" id="man-exp"><span class="header-section-number">52.21</span> <code>exp()</code>,
<code>expf()</code>, <code>expl()</code></h2>
<p>Compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="12" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> raised to a power.</p>
<h3 class="unnumbered unlisted" id="synopsis-69">Synopsis</h3>
<div class="sourceCode" id="cb1009"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1009-1"><a href="math.html#cb1009-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1009-2"><a href="math.html#cb1009-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1009-3"><a href="math.html#cb1009-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> exp<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1009-4"><a href="math.html#cb1009-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1009-5"><a href="math.html#cb1009-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> expf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1009-6"><a href="math.html#cb1009-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1009-7"><a href="math.html#cb1009-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> expl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-69">Description</h3>
<p>Compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="13" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>e</mi><mi>x</mi></msup></math></mjx-assistive-mml></mjx-container></span> where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="14" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> is <a href="https://en.wikipedia.org/wiki/E_(mathematical_constant)">Euler’s
number</a><a href="footnotes.html#fn232" class="footnote-ref" id="fnref232" role="doc-noteref"><sup>232</sup></a>.</p>
<p>The number <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="15" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> is named after
Leonard Euler, born April 15, 1707, who is responsible, among other
things, for making this reference page longer than it needed to be.</p>
<h3 class="unnumbered unlisted" id="return-value-68">Return Value</h3>
<p>Returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="16" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>e</mi><mi>x</mi></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-69">Example</h3>
<div class="sourceCode" id="cb1010"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1010-1"><a href="math.html#cb1010-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1010-2"><a href="math.html#cb1010-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1010-3"><a href="math.html#cb1010-3"></a></span>
<span id="cb1010-4"><a href="math.html#cb1010-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1010-5"><a href="math.html#cb1010-5"></a><span class="op">{</span></span>
<span id="cb1010-6"><a href="math.html#cb1010-6"></a>    printf<span class="op">(</span><span class="st">"exp(1) = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> exp<span class="op">(</span><span class="dv">1</span><span class="op">));</span>  <span class="co">// 2.718282</span></span>
<span id="cb1010-7"><a href="math.html#cb1010-7"></a>    printf<span class="op">(</span><span class="st">"exp(2) = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> exp<span class="op">(</span><span class="dv">2</span><span class="op">));</span>  <span class="co">// 7.389056</span></span>
<span id="cb1010-8"><a href="math.html#cb1010-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-65">See Also</h3>
<p><a href="math.html#man-exp2"><code>exp2()</code></a>, <a href="#man-expm1"><code>expm1()</code></a>, <a href="#man-pow"><code>pow()</code></a>, <a href="#man-log"><code>log()</code></a></p>
<hr>
<h2 data-number="52.22" id="man-exp2"><span class="header-section-number">52.22</span> <code>exp2()</code>,
<code>exp2f()</code>, <code>exp2l()</code></h2>
<p>Compute 2 to a power.</p>
<h3 class="unnumbered unlisted" id="synopsis-70">Synopsis</h3>
<div class="sourceCode" id="cb1011"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1011-1"><a href="math.html#cb1011-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1011-2"><a href="math.html#cb1011-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1011-3"><a href="math.html#cb1011-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> exp2<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1011-4"><a href="math.html#cb1011-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1011-5"><a href="math.html#cb1011-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> exp2f<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1011-6"><a href="math.html#cb1011-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1011-7"><a href="math.html#cb1011-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> exp2l<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-70">Description</h3>
<p>These functions raise 2 to a power. Very exciting, since computers
are all about twos-to-powers!</p>
<p>These are likely to be faster than using <code>pow()</code> to do the
same thing.</p>
<p>They support fractional exponents, as well.</p>
<p>A range error occurs if <code>x</code> is too large.</p>
<h3 class="unnumbered unlisted" id="return-value-69">Return Value</h3>
<p><code>exp2()</code> returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="17" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mi>x</mi></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-70">Example</h3>
<div class="sourceCode" id="cb1012"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1012-1"><a href="math.html#cb1012-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1012-2"><a href="math.html#cb1012-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1012-3"><a href="math.html#cb1012-3"></a></span>
<span id="cb1012-4"><a href="math.html#cb1012-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1012-5"><a href="math.html#cb1012-5"></a><span class="op">{</span></span>
<span id="cb1012-6"><a href="math.html#cb1012-6"></a>    printf<span class="op">(</span><span class="st">"2^3 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> exp2<span class="op">(</span><span class="dv">3</span><span class="op">));</span>      <span class="co">// 2^3 = 8.000000</span></span>
<span id="cb1012-7"><a href="math.html#cb1012-7"></a>    printf<span class="op">(</span><span class="st">"2^8 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> exp2<span class="op">(</span><span class="dv">8</span><span class="op">));</span>      <span class="co">// 2^8 = 256.000000</span></span>
<span id="cb1012-8"><a href="math.html#cb1012-8"></a>    printf<span class="op">(</span><span class="st">"2^0.5 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> exp2<span class="op">(</span><span class="fl">0.5</span><span class="op">));</span>  <span class="co">// 2^0.5 = 1.414214    </span></span>
<span id="cb1012-9"><a href="math.html#cb1012-9"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-66">See Also</h3>
<p><a href="math.html#man-exp"><code>exp()</code></a>, <a href="#man-pow"><code>pow()</code></a></p>
<hr>
<h2 data-number="52.23" id="man-expm1"><span class="header-section-number">52.23</span> <code>expm1()</code>,
<code>expm1f()</code>, <code>expm1l()</code></h2>
<p>Compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="18" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>e</mi><mi>x</mi></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="synopsis-71">Synopsis</h3>
<div class="sourceCode" id="cb1013"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1013-1"><a href="math.html#cb1013-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1013-2"><a href="math.html#cb1013-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1013-3"><a href="math.html#cb1013-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> expm1<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1013-4"><a href="math.html#cb1013-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1013-5"><a href="math.html#cb1013-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> expm1f<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1013-6"><a href="math.html#cb1013-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1013-7"><a href="math.html#cb1013-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> expm1l<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-71">Description</h3>
<p>This is just like <code>exp()</code> except—<em>plot twist!</em>–it
computes that result minus one.</p>
<p>For more discussion about what <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="19" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span>
is, see <a href="math.html#man-exp">the <code>exp()</code> man page</a>.</p>
<p>If <code>x</code> is giant, a range error might occur.</p>
<p>For small values of <code>x</code> near zero, <code>expm1(x)</code>
might be more accurate than computing <code>exp(x)-1</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-70">Return Value</h3>
<p>Returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="20" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>e</mi><mi>x</mi></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-71">Example</h3>
<div class="sourceCode" id="cb1014"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1014-1"><a href="math.html#cb1014-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1014-2"><a href="math.html#cb1014-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1014-3"><a href="math.html#cb1014-3"></a></span>
<span id="cb1014-4"><a href="math.html#cb1014-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1014-5"><a href="math.html#cb1014-5"></a><span class="op">{</span></span>
<span id="cb1014-6"><a href="math.html#cb1014-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> expm1<span class="op">(</span><span class="fl">2.34</span><span class="op">));</span>  <span class="co">// 9.381237</span></span>
<span id="cb1014-7"><a href="math.html#cb1014-7"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-67">See Also</h3>
<p><a href="math.html#man-exp"><code>exp()</code></a></p>
<hr>
<h2 data-number="52.24" id="man-frexp"><span class="header-section-number">52.24</span> <code>frexp()</code>,
<code>frexpf()</code>, <code>frexpl()</code></h2>
<p>Break a number into its fraction part and exponent (as a power of
2).</p>
<h3 class="unnumbered unlisted" id="synopsis-72">Synopsis</h3>
<div class="sourceCode" id="cb1015"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1015-1"><a href="math.html#cb1015-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1015-2"><a href="math.html#cb1015-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1015-3"><a href="math.html#cb1015-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> frexp<span class="op">(</span><span class="dt">double</span> value<span class="op">,</span> <span class="dt">int</span> <span class="op">*</span>exp<span class="op">);</span></span>
<span id="cb1015-4"><a href="math.html#cb1015-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1015-5"><a href="math.html#cb1015-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> frexpf<span class="op">(</span><span class="dt">float</span> value<span class="op">,</span> <span class="dt">int</span> <span class="op">*</span>exp<span class="op">);</span></span>
<span id="cb1015-6"><a href="math.html#cb1015-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1015-7"><a href="math.html#cb1015-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> frexpl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> value<span class="op">,</span> <span class="dt">int</span> <span class="op">*</span>exp<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-72">Description</h3>
<p>If you have a floating point number, you can break it into its
fractional part and exponent part (as a power of 2).</p>
<p>For example, if you have the number <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="21" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c33"></mjx-c><mjx-c class="mjx-c34"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c35"></mjx-c><mjx-c class="mjx-c36"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1234.56</mn></math></mjx-assistive-mml></mjx-container></span>, this can be represented as a
multiple of a power of 2 like so:</p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="22" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c33"></mjx-c><mjx-c class="mjx-c34"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c35"></mjx-c><mjx-c class="mjx-c36"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c36"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c38"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1234.56</mn><mo>=</mo><mn>0.6028125</mn><mo>×</mo><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>11</mn></mrow></msup></math></mjx-assistive-mml></mjx-container></span></p>
<p>And you can use this function to get the <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="23" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c36"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c38"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0.6028125</mn></math></mjx-assistive-mml></mjx-container></span> and <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="24" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>11</mn></math></mjx-assistive-mml></mjx-container></span> parts of that equation.</p>
<p>As for why, I have a simple answer: I don’t know. I can’t find a use.
K&amp;R2 and everyone else I can find just says <em>how</em> to use it,
but not <em>why</em> you might want to.</p>
<p>The C99 Rationale document says:</p>
<blockquote>
<p>The functions <code>frexp</code>, <code>ldexp</code>, and
<code>modf</code> are primitives used by the remainder of the
library.</p>
<p>There was some sentiment for dropping them for the same reasons that
<code>ecvt</code>, <code>fcvt</code>, and <code>gcvt</code> were
dropped, but their adherents rescued them for general use. Their use is
problematic: on non-binary architectures, ldexp may lose precision and
frexp may be inefficient.</p>
</blockquote>
<p>So there you have it. If you need it.</p>
<h3 class="unnumbered unlisted" id="return-value-71">Return Value</h3>
<p><code>frexp()</code> returns the fractional part of
<code>value</code> in the range 0.5 (inclusive) to 1 (exclusive), or 0.
And it stores the exponent power-of-2 in the variable pointed to by
<code>exp</code>.</p>
<p>If you pass in zero, the return value and the variable
<code>exp</code> points to are both zero.</p>
<h3 class="unnumbered unlisted" id="example-72">Example</h3>
<div class="sourceCode" id="cb1016"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1016-1"><a href="math.html#cb1016-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1016-2"><a href="math.html#cb1016-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1016-3"><a href="math.html#cb1016-3"></a></span>
<span id="cb1016-4"><a href="math.html#cb1016-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1016-5"><a href="math.html#cb1016-5"></a><span class="op">{</span></span>
<span id="cb1016-6"><a href="math.html#cb1016-6"></a>    <span class="dt">double</span> frac<span class="op">;</span></span>
<span id="cb1016-7"><a href="math.html#cb1016-7"></a>    <span class="dt">int</span> expt<span class="op">;</span></span>
<span id="cb1016-8"><a href="math.html#cb1016-8"></a></span>
<span id="cb1016-9"><a href="math.html#cb1016-9"></a>    frac <span class="op">=</span> frexp<span class="op">(</span><span class="fl">1234.56</span><span class="op">,</span> <span class="op">&amp;</span>expt<span class="op">);</span></span>
<span id="cb1016-10"><a href="math.html#cb1016-10"></a>    printf<span class="op">(</span><span class="st">"1234.56 = %.7f x 2^%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> frac<span class="op">,</span> expt<span class="op">);</span>  </span>
<span id="cb1016-11"><a href="math.html#cb1016-11"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1017"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1017-1"><a href="math.html#cb1017-1" aria-hidden="true" tabindex="-1"></a>1234.56 = 0.6028125 x 2^11</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-68">See Also</h3>
<p><a href="math.html#man-ldexp"><code>ldexp()</code></a>, <a href="#man-ldexp"><code>ilogb()</code></a>, <a href="#man-modf"><code>modf()</code></a></p>
<hr>
<h2 data-number="52.25" id="man-ilogb"><span class="header-section-number">52.25</span> <code>ilogb()</code>,
<code>ilogbf()</code>, <code>ilogbl()</code></h2>
<p>Return the exponent of a floating point number.</p>
<h3 class="unnumbered unlisted" id="synopsis-73">Synopsis</h3>
<div class="sourceCode" id="cb1018"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1018-1"><a href="math.html#cb1018-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1018-2"><a href="math.html#cb1018-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1018-3"><a href="math.html#cb1018-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> ilogb<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1018-4"><a href="math.html#cb1018-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1018-5"><a href="math.html#cb1018-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> ilogbf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1018-6"><a href="math.html#cb1018-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1018-7"><a href="math.html#cb1018-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> ilogbl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-73">Description</h3>
<p>This gives you the exponent of the given number… it’s a little weird,
because the exponent depends on the value of <code>FLT_RADIX</code>.
Now, this is very often <code>2</code>—but no guarantees!</p>
<p>It actually returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="25" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>r</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>x</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span>
where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="26" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is
<code>FLT_RADIX</code>.</p>
<p>Domain or range errors might occur for invalid values of
<code>x</code>, or for return values that are outside the range of the
return type.</p>
<h3 class="unnumbered unlisted" id="return-value-72">Return Value</h3>
<p>The exponent of the absolute value of the given number, depending on
<code>FLT_RADIX</code>.</p>
<p>Specifically <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="27" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>r</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>x</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span> where
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="28" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is <code>FLT_RADIX</code>.</p>
<p>If you pass in <code>0</code>, it’ll return
<code>FP_ILOGB0</code>.</p>
<p>If you pass in infinity, it’ll return <code>INT_MAX</code>.</p>
<p>If you pass in NaN, it’ll return <code>FP_ILOGBNAN</code>.</p>
<p>The spec goes on to say that the value of <code>FP_ILOGB0</code> will
be either <code>INT_MIN</code> or <code>-INT_MAX</code>. And the value
of <code>FP_ILOGBNAN</code> shall be either <code>INT_MAX</code> or
<code>INT_MIN</code>, if that’s useful in any way.</p>
<h3 class="unnumbered unlisted" id="example-73">Example</h3>
<div class="sourceCode" id="cb1019"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1019-1"><a href="math.html#cb1019-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1019-2"><a href="math.html#cb1019-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1019-3"><a href="math.html#cb1019-3"></a></span>
<span id="cb1019-4"><a href="math.html#cb1019-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1019-5"><a href="math.html#cb1019-5"></a><span class="op">{</span></span>
<span id="cb1019-6"><a href="math.html#cb1019-6"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ilogb<span class="op">(</span><span class="dv">257</span><span class="op">));</span>  <span class="co">// 8</span></span>
<span id="cb1019-7"><a href="math.html#cb1019-7"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ilogb<span class="op">(</span><span class="dv">256</span><span class="op">));</span>  <span class="co">// 8</span></span>
<span id="cb1019-8"><a href="math.html#cb1019-8"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ilogb<span class="op">(</span><span class="dv">255</span><span class="op">));</span>  <span class="co">// 7</span></span>
<span id="cb1019-9"><a href="math.html#cb1019-9"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-69">See Also</h3>
<p><a href="math.html#man-frexp"><code>frexp()</code></a>, <a href="#man-logb"><code>logb()</code></a></p>
<hr>
<h2 data-number="52.26" id="man-ldexp"><span class="header-section-number">52.26</span> <code>ldexp()</code>,
<code>ldexpf()</code>, <code>ldexpl()</code></h2>
<p>Multiply a number by an integral power of 2.</p>
<h3 class="unnumbered unlisted" id="synopsis-74">Synopsis</h3>
<div class="sourceCode" id="cb1020"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1020-1"><a href="math.html#cb1020-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1020-2"><a href="math.html#cb1020-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1020-3"><a href="math.html#cb1020-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> ldexp<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">int</span> exp<span class="op">);</span></span>
<span id="cb1020-4"><a href="math.html#cb1020-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1020-5"><a href="math.html#cb1020-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> ldexpf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">int</span> exp<span class="op">);</span></span>
<span id="cb1020-6"><a href="math.html#cb1020-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1020-7"><a href="math.html#cb1020-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> ldexpl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">int</span> exp<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-74">Description</h3>
<p>These functions multiply the given number <code>x</code> by 2 raised
to the <code>exp</code> power.</p>
<h3 class="unnumbered unlisted" id="return-value-73">Return Value</h3>
<p>Returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="29" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45D TEX-I"></mjx-c></mjx-mi></mjx-texatom></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>×</mo><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mi>e</mi><mi>x</mi><mi>p</mi></mrow></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-74">Example</h3>
<div class="sourceCode" id="cb1021"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1021-1"><a href="math.html#cb1021-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1021-2"><a href="math.html#cb1021-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1021-3"><a href="math.html#cb1021-3"></a></span>
<span id="cb1021-4"><a href="math.html#cb1021-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1021-5"><a href="math.html#cb1021-5"></a><span class="op">{</span></span>
<span id="cb1021-6"><a href="math.html#cb1021-6"></a>    printf<span class="op">(</span><span class="st">"1 x 2^10 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldexp<span class="op">(</span><span class="dv">1</span><span class="op">,</span> <span class="dv">10</span><span class="op">));</span></span>
<span id="cb1021-7"><a href="math.html#cb1021-7"></a>    printf<span class="op">(</span><span class="st">"5.67 x 2^7 = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ldexp<span class="op">(</span><span class="fl">5.67</span><span class="op">,</span> <span class="dv">7</span><span class="op">));</span></span>
<span id="cb1021-8"><a href="math.html#cb1021-8"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1022"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1022-1"><a href="math.html#cb1022-1" aria-hidden="true" tabindex="-1"></a>1 x 2^10 = 1024.000000</span>
<span id="cb1022-2"><a href="math.html#cb1022-2" aria-hidden="true" tabindex="-1"></a>5.67 x 2^7 = 725.760000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-70">See Also</h3>
<p><a href="math.html#man-exp"><code>exp()</code></a></p>
<hr>
<h2 data-number="52.27" id="man-log"><span class="header-section-number">52.27</span> <code>log()</code>,
<code>logf()</code>, <code>logl()</code></h2>
<p>Compute the natural logarithm.</p>
<h3 class="unnumbered unlisted" id="synopsis-75">Synopsis</h3>
<div class="sourceCode" id="cb1023"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1023-1"><a href="math.html#cb1023-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1023-2"><a href="math.html#cb1023-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1023-3"><a href="math.html#cb1023-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> log<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1023-4"><a href="math.html#cb1023-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1023-5"><a href="math.html#cb1023-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> logf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1023-6"><a href="math.html#cb1023-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1023-7"><a href="math.html#cb1023-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> logl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-75">Description</h3>
<p>Natural logarithms! And there was much rejoycing.</p>
<p>These compute the base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="30" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span>
logarithm of a number, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="31" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>e</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>,
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="32" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6E"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>ln</mi><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>In other words, for a given <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="33" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>,
solves <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="34" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-msup space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>=</mo><msup><mi>e</mi><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span> for <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="35" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="return-value-74">Return Value</h3>
<p>The base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="36" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> logarithm of the
given value, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="37" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>e</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="38" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6E"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>ln</mi><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-75">Example</h3>
<div class="sourceCode" id="cb1024"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1024-1"><a href="math.html#cb1024-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1024-2"><a href="math.html#cb1024-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1024-3"><a href="math.html#cb1024-3"></a></span>
<span id="cb1024-4"><a href="math.html#cb1024-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1024-5"><a href="math.html#cb1024-5"></a><span class="op">{</span></span>
<span id="cb1024-6"><a href="math.html#cb1024-6"></a>    <span class="dt">const</span> <span class="dt">double</span> e <span class="op">=</span> <span class="fl">2.718281828459045</span><span class="op">;</span></span>
<span id="cb1024-7"><a href="math.html#cb1024-7"></a></span>
<span id="cb1024-8"><a href="math.html#cb1024-8"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> log<span class="op">(</span><span class="fl">3490.2</span><span class="op">));</span>  <span class="co">// 8.157714</span></span>
<span id="cb1024-9"><a href="math.html#cb1024-9"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> log<span class="op">(</span>e<span class="op">));</span>       <span class="co">// 1.000000</span></span>
<span id="cb1024-10"><a href="math.html#cb1024-10"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-71">See Also</h3>
<p><a href="math.html#man-exp"><code>exp()</code></a>, <a href="#man-log10"><code>log10()</code></a>, <a href="#man-log10"><code>log1p()</code></a></p>
<hr>
<h2 data-number="52.28" id="man-log10"><span class="header-section-number">52.28</span> <code>log10()</code>,
<code>log10f()</code>, <code>log10l()</code></h2>
<p>Compute the log-base-10 of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-76">Synopsis</h3>
<div class="sourceCode" id="cb1025"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1025-1"><a href="math.html#cb1025-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1025-2"><a href="math.html#cb1025-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1025-3"><a href="math.html#cb1025-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> log10<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1025-4"><a href="math.html#cb1025-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1025-5"><a href="math.html#cb1025-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> log10f<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1025-6"><a href="math.html#cb1025-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1025-7"><a href="math.html#cb1025-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> log10l<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-76">Description</h3>
<p>Just when you thought you might have to use Laws of Logarithms to
compute this, here’s a function coming out of the blue to save you.</p>
<p>These compute the base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="39" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>10</mn></math></mjx-assistive-mml></mjx-container></span>
logarithm of a number, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="40" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mrow data-mjx-texclass="ORD"><mn>10</mn></mrow></msub><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>In other words, for a given <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="41" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>,
solves <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="42" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-msup space="4"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.393em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>=</mo><msup><mn>10</mn><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span> for <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="43" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="return-value-75">Return Value</h3>
<p>Returns the log base-10 of <code>x</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="44" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mrow data-mjx-texclass="ORD"><mn>10</mn></mrow></msub><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-76">Example</h3>
<div class="sourceCode" id="cb1026"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1026-1"><a href="math.html#cb1026-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1026-2"><a href="math.html#cb1026-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1026-3"><a href="math.html#cb1026-3"></a></span>
<span id="cb1026-4"><a href="math.html#cb1026-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1026-5"><a href="math.html#cb1026-5"></a><span class="op">{</span></span>
<span id="cb1026-6"><a href="math.html#cb1026-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> log10<span class="op">(</span><span class="fl">3490.2</span><span class="op">));</span>   <span class="co">// 3.542850</span></span>
<span id="cb1026-7"><a href="math.html#cb1026-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> log10<span class="op">(</span><span class="dv">10</span><span class="op">));</span>       <span class="co">// 1.000000</span></span>
<span id="cb1026-8"><a href="math.html#cb1026-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-72">See Also</h3>
<p><a href="math.html#man-pow"><code>pow()</code></a>, <a href="#man-log"><code>log()</code></a></p>
<hr>
<h2 data-number="52.29" id="man-log1p"><span class="header-section-number">52.29</span> <code>log1p()</code>,
<code>log1pf()</code>, <code>log1pl()</code></h2>
<p>Compute the natural logarithm of a number plus 1.</p>
<h3 class="unnumbered unlisted" id="synopsis-77">Synopsis</h3>
<div class="sourceCode" id="cb1027"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1027-1"><a href="math.html#cb1027-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1027-2"><a href="math.html#cb1027-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1027-3"><a href="math.html#cb1027-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> log1p<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1027-4"><a href="math.html#cb1027-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1027-5"><a href="math.html#cb1027-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> log1pf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1027-6"><a href="math.html#cb1027-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1027-7"><a href="math.html#cb1027-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> log1pl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-77">Description</h3>
<p>This computes <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="45" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>e</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo stretchy="false">(</mo><mn>1</mn><mo>+</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>,
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="46" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6E"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>ln</mi><mo data-mjx-texclass="NONE">⁡</mo><mo stretchy="false">(</mo><mn>1</mn><mo>+</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>This works just like calling:</p>
<div class="sourceCode" id="cb1028"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1028-1"><a href="math.html#cb1028-1" aria-hidden="true" tabindex="-1"></a>log<span class="op">(</span><span class="dv">1</span> <span class="op">+</span> x<span class="op">)</span></span></code></pre></div>
<p>except it could be more accurate for small values of
<code>x</code>.</p>
<p>So if your <code>x</code> is small magnitude, use this.</p>
<h3 class="unnumbered unlisted" id="return-value-76">Return Value</h3>
<p>Returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="47" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>e</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo stretchy="false">(</mo><mn>1</mn><mo>+</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="48" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6E"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>ln</mi><mo data-mjx-texclass="NONE">⁡</mo><mo stretchy="false">(</mo><mn>1</mn><mo>+</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-77">Example</h3>
<p>Compute some big and small logarithm values to see the difference
between <code>log1p()</code> and <code>log()</code>:</p>
<div class="sourceCode" id="cb1029"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1029-1"><a href="math.html#cb1029-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1029-2"><a href="math.html#cb1029-2"></a><span class="pp">#include </span><span class="im">&lt;float.h&gt;</span><span class="pp"> </span><span class="co">// for LDBL_DECIMAL_DIG</span></span>
<span id="cb1029-3"><a href="math.html#cb1029-3"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1029-4"><a href="math.html#cb1029-4"></a></span>
<span id="cb1029-5"><a href="math.html#cb1029-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1029-6"><a href="math.html#cb1029-6"></a><span class="op">{</span></span>
<span id="cb1029-7"><a href="math.html#cb1029-7"></a>    printf<span class="op">(</span><span class="st">"Big log1p()  : %.*Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">-</span><span class="dv">1</span><span class="op">,</span> log1pl<span class="op">(</span><span class="dv">9</span><span class="op">));</span></span>
<span id="cb1029-8"><a href="math.html#cb1029-8"></a>    printf<span class="op">(</span><span class="st">"Big log()    : %.*Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">-</span><span class="dv">1</span><span class="op">,</span> logl<span class="op">(</span><span class="dv">1</span> <span class="op">+</span> <span class="dv">9</span><span class="op">));</span></span>
<span id="cb1029-9"><a href="math.html#cb1029-9"></a></span>
<span id="cb1029-10"><a href="math.html#cb1029-10"></a>    printf<span class="op">(</span><span class="st">"Small log1p(): %.*Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">-</span><span class="dv">1</span><span class="op">,</span> log1pl<span class="op">(</span><span class="fl">0.01</span><span class="op">));</span></span>
<span id="cb1029-11"><a href="math.html#cb1029-11"></a>    printf<span class="op">(</span><span class="st">"Small log()  : %.*Lf</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">-</span><span class="dv">1</span><span class="op">,</span> logl<span class="op">(</span><span class="dv">1</span> <span class="op">+</span> <span class="fl">0.01</span><span class="op">));</span></span>
<span id="cb1029-12"><a href="math.html#cb1029-12"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1030"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1030-1"><a href="math.html#cb1030-1" aria-hidden="true" tabindex="-1"></a>Big log1p()  : 2.30258509299404568403</span>
<span id="cb1030-2"><a href="math.html#cb1030-2" aria-hidden="true" tabindex="-1"></a>Big log()    : 2.30258509299404568403</span>
<span id="cb1030-3"><a href="math.html#cb1030-3" aria-hidden="true" tabindex="-1"></a>Small log1p(): 0.00995033085316808305</span>
<span id="cb1030-4"><a href="math.html#cb1030-4" aria-hidden="true" tabindex="-1"></a>Small log()  : 0.00995033085316809164</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-73">See Also</h3>
<p><a href="math.html#man-log"><code>log()</code></a></p>
<hr>
<h2 data-number="52.30" id="man-log2"><span class="header-section-number">52.30</span> <code>log2()</code>,
<code>log2f()</code>, <code>log2l()</code></h2>
<p>Compute the base-2 logarithm of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-78">Synopsis</h3>
<div class="sourceCode" id="cb1031"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1031-1"><a href="math.html#cb1031-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1031-2"><a href="math.html#cb1031-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1031-3"><a href="math.html#cb1031-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> log2<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1031-4"><a href="math.html#cb1031-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1031-5"><a href="math.html#cb1031-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> log2f<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1031-6"><a href="math.html#cb1031-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1031-7"><a href="math.html#cb1031-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> log2l<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-78">Description</h3>
<p>Wow! Were you thinking we were done with the logarithm functions?
We’re only getting started!</p>
<p>This one computes <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="49" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mn>2</mn></msub><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>. That
is, computes <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="50" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi></math></mjx-assistive-mml></mjx-container></span> that satisfies <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="51" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-msup space="4"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>=</mo><msup><mn>2</mn><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>Love me those powers of 2!</p>
<h3 class="unnumbered unlisted" id="return-value-77">Return Value</h3>
<p>Returns the base-2 logarithm of the given value, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="52" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mn>2</mn></msub><mo data-mjx-texclass="NONE">⁡</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-78">Example</h3>
<div class="sourceCode" id="cb1032"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1032-1"><a href="math.html#cb1032-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1032-2"><a href="math.html#cb1032-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1032-3"><a href="math.html#cb1032-3"></a></span>
<span id="cb1032-4"><a href="math.html#cb1032-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1032-5"><a href="math.html#cb1032-5"></a><span class="op">{</span></span>
<span id="cb1032-6"><a href="math.html#cb1032-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> log2<span class="op">(</span><span class="fl">3490.2</span><span class="op">));</span>  <span class="co">// 11.769094</span></span>
<span id="cb1032-7"><a href="math.html#cb1032-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> log2<span class="op">(</span><span class="dv">256</span><span class="op">));</span>     <span class="co">// 8.000000</span></span>
<span id="cb1032-8"><a href="math.html#cb1032-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-74">See Also</h3>
<p><a href="math.html#man-log"><code>log()</code></a></p>
<hr>
<h2 data-number="52.31" id="man-logb"><span class="header-section-number">52.31</span> <code>logb()</code>,
<code>logbf()</code>, <code>logbl()</code></h2>
<p>Extract the exponent of a number given <code>FLT_RADIX</code>.</p>
<h3 class="unnumbered unlisted" id="synopsis-79">Synopsis</h3>
<div class="sourceCode" id="cb1033"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1033-1"><a href="math.html#cb1033-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1033-2"><a href="math.html#cb1033-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1033-3"><a href="math.html#cb1033-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> logb<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1033-4"><a href="math.html#cb1033-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1033-5"><a href="math.html#cb1033-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> logbf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1033-6"><a href="math.html#cb1033-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1033-7"><a href="math.html#cb1033-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> logbl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-79">Description</h3>
<p>This function returns the whole number portion of the exponent of the
number with radix <code>FLT_RADIX</code>, namely the whole number
portion <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="53" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>r</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>x</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span> where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="54" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is <code>FLT_RADIX</code>. Fractional
numbers are truncated.</p>
<p>If the number is <a href="https://en.wikipedia.org/wiki/Denormal_number">subnormal</a><a href="#fn233" class="footnote-ref" id="fnref233" role="doc-noteref"><sup>233</sup></a>, <code>logb()</code> treats it as
if it were normalized.</p>
<p>If <code>x</code> is <code>0</code>, there could be a domain error or
pole error.</p>
<h3 class="unnumbered unlisted" id="return-value-78">Return Value</h3>
<p>This function returns the whole number portion of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="55" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>r</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>x</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span> where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="56" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is <code>FLT_RADIX</code>.</p>
<h3 class="unnumbered unlisted" id="example-79">Example</h3>
<div class="sourceCode" id="cb1034"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1034-1"><a href="math.html#cb1034-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1034-2"><a href="math.html#cb1034-2"></a><span class="pp">#include </span><span class="im">&lt;float.h&gt;</span><span class="pp">  </span><span class="co">// For FLT_RADIX</span></span>
<span id="cb1034-3"><a href="math.html#cb1034-3"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1034-4"><a href="math.html#cb1034-4"></a></span>
<span id="cb1034-5"><a href="math.html#cb1034-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1034-6"><a href="math.html#cb1034-6"></a><span class="op">{</span></span>
<span id="cb1034-7"><a href="math.html#cb1034-7"></a>    printf<span class="op">(</span><span class="st">"FLT_RADIX = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_RADIX<span class="op">);</span></span>
<span id="cb1034-8"><a href="math.html#cb1034-8"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> logb<span class="op">(</span><span class="fl">3490.2</span><span class="op">));</span></span>
<span id="cb1034-9"><a href="math.html#cb1034-9"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> logb<span class="op">(</span><span class="dv">256</span><span class="op">));</span></span>
<span id="cb1034-10"><a href="math.html#cb1034-10"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1035"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1035-1"><a href="math.html#cb1035-1" aria-hidden="true" tabindex="-1"></a>FLT_RADIX = 2</span>
<span id="cb1035-2"><a href="math.html#cb1035-2" aria-hidden="true" tabindex="-1"></a>11.000000</span>
<span id="cb1035-3"><a href="math.html#cb1035-3" aria-hidden="true" tabindex="-1"></a>8.000000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-75">See Also</h3>
<p><a href="math.html#man-ilogb"><code>ilogb()</code></a></p>
<hr>
<h2 data-number="52.32" id="man-modf"><span class="header-section-number">52.32</span> <code>modf()</code>,
<code>modff()</code>, <code>modfl()</code></h2>
<p>Extract the integral and fractional parts of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-80">Synopsis</h3>
<div class="sourceCode" id="cb1036"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1036-1"><a href="math.html#cb1036-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1036-2"><a href="math.html#cb1036-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1036-3"><a href="math.html#cb1036-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> modf<span class="op">(</span><span class="dt">double</span> value<span class="op">,</span> <span class="dt">double</span> <span class="op">*</span>iptr<span class="op">);</span></span>
<span id="cb1036-4"><a href="math.html#cb1036-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1036-5"><a href="math.html#cb1036-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> modff<span class="op">(</span><span class="dt">float</span> value<span class="op">,</span> <span class="dt">float</span> <span class="op">*</span>iptr<span class="op">);</span></span>
<span id="cb1036-6"><a href="math.html#cb1036-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1036-7"><a href="math.html#cb1036-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> modfl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> value<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> <span class="op">*</span>iptr<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-80">Description</h3>
<p>If you have a floating point number, like <code>123.456</code>, this
function will extract the integral part (<code>123.0</code>) and the
fractional part (<code>0.456</code>). It’s total coincidence that this
is exactly the plot for the latest Jason Statham action spectacular.</p>
<p>Both the integral part and fractional parts keep the sign of the
passed in <code>value</code>.</p>
<p>The integral part is stored in the address pointed to by
<code>iptr</code>.</p>
<p>See the note in <a href="math.html#man-frexp"><code>frexp()</code></a>
regarding why this is in the library.</p>
<h3 class="unnumbered unlisted" id="return-value-79">Return Value</h3>
<p>These functions return the fractional part of the number. The
integral part is stored in the address pointed to by <code>iptr</code>.
Both the integral and fractional parts preserve the sign of the
passed-in <code>value</code>.</p>
<h3 class="unnumbered unlisted" id="example-80">Example</h3>
<div class="sourceCode" id="cb1037"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1037-1"><a href="math.html#cb1037-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1037-2"><a href="math.html#cb1037-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1037-3"><a href="math.html#cb1037-3"></a></span>
<span id="cb1037-4"><a href="math.html#cb1037-4"></a><span class="dt">void</span> print_parts<span class="op">(</span><span class="dt">double</span> x<span class="op">)</span></span>
<span id="cb1037-5"><a href="math.html#cb1037-5"></a><span class="op">{</span></span>
<span id="cb1037-6"><a href="math.html#cb1037-6"></a>    <span class="dt">double</span> i<span class="op">,</span> f<span class="op">;</span></span>
<span id="cb1037-7"><a href="math.html#cb1037-7"></a></span>
<span id="cb1037-8"><a href="math.html#cb1037-8"></a>    f <span class="op">=</span> modf<span class="op">(</span>x<span class="op">,</span> <span class="op">&amp;</span>i<span class="op">);</span></span>
<span id="cb1037-9"><a href="math.html#cb1037-9"></a></span>
<span id="cb1037-10"><a href="math.html#cb1037-10"></a>    printf<span class="op">(</span><span class="st">"Entire number  : %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x<span class="op">);</span></span>
<span id="cb1037-11"><a href="math.html#cb1037-11"></a>    printf<span class="op">(</span><span class="st">"Integral part  : %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">);</span></span>
<span id="cb1037-12"><a href="math.html#cb1037-12"></a>    printf<span class="op">(</span><span class="st">"Fractional part: %f</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> f<span class="op">);</span></span>
<span id="cb1037-13"><a href="math.html#cb1037-13"></a><span class="op">}</span></span>
<span id="cb1037-14"><a href="math.html#cb1037-14"></a></span>
<span id="cb1037-15"><a href="math.html#cb1037-15"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1037-16"><a href="math.html#cb1037-16"></a><span class="op">{</span></span>
<span id="cb1037-17"><a href="math.html#cb1037-17"></a>    print_parts<span class="op">(</span><span class="fl">123.456</span><span class="op">);</span></span>
<span id="cb1037-18"><a href="math.html#cb1037-18"></a>    print_parts<span class="op">(-</span><span class="fl">123.456</span><span class="op">);</span></span>
<span id="cb1037-19"><a href="math.html#cb1037-19"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1038"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1038-1"><a href="math.html#cb1038-1" aria-hidden="true" tabindex="-1"></a>Entire number  : 123.456000</span>
<span id="cb1038-2"><a href="math.html#cb1038-2" aria-hidden="true" tabindex="-1"></a>Integral part  : 123.000000</span>
<span id="cb1038-3"><a href="math.html#cb1038-3" aria-hidden="true" tabindex="-1"></a>Fractional part: 0.456000</span>
<span id="cb1038-4"><a href="math.html#cb1038-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1038-5"><a href="math.html#cb1038-5" aria-hidden="true" tabindex="-1"></a>Entire number  : -123.456000</span>
<span id="cb1038-6"><a href="math.html#cb1038-6" aria-hidden="true" tabindex="-1"></a>Integral part  : -123.000000</span>
<span id="cb1038-7"><a href="math.html#cb1038-7" aria-hidden="true" tabindex="-1"></a>Fractional part: -0.456000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-76">See Also</h3>
<p><a href="math.html#man-frexp"><code>frexp()</code></a></p>
<hr>
<h2 data-number="52.33" id="man-scalb"><span class="header-section-number">52.33</span> <code>scalbn()</code>,
<code>scalbnf()</code>, <code>scalbnl()</code> <code>scalbln()</code>,
<code>scalblnf()</code>, <code>scalblnl()</code></h2>
<p>Efficiently compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="57" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>×</mo><msup><mi>r</mi><mi>n</mi></msup></math></mjx-assistive-mml></mjx-container></span>,
where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="58" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is
<code>FLT_RADIX</code>.</p>
<h3 class="unnumbered unlisted" id="synopsis-81">Synopsis</h3>
<div class="sourceCode" id="cb1039"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1039-1"><a href="math.html#cb1039-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1039-2"><a href="math.html#cb1039-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1039-3"><a href="math.html#cb1039-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> scalbn<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">int</span> n<span class="op">);</span></span>
<span id="cb1039-4"><a href="math.html#cb1039-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1039-5"><a href="math.html#cb1039-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> scalbnf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">int</span> n<span class="op">);</span></span>
<span id="cb1039-6"><a href="math.html#cb1039-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1039-7"><a href="math.html#cb1039-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> scalbnl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">int</span> n<span class="op">);</span></span>
<span id="cb1039-8"><a href="math.html#cb1039-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1039-9"><a href="math.html#cb1039-9" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> scalbln<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">int</span> n<span class="op">);</span></span>
<span id="cb1039-10"><a href="math.html#cb1039-10" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1039-11"><a href="math.html#cb1039-11" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> scalblnf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">int</span> n<span class="op">);</span></span>
<span id="cb1039-12"><a href="math.html#cb1039-12" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1039-13"><a href="math.html#cb1039-13" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> scalblnl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">int</span> n<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-81">Description</h3>
<p>These functions efficiently compute <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="59" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>×</mo><msup><mi>r</mi><mi>n</mi></msup></math></mjx-assistive-mml></mjx-container></span>, where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="60" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is <code>FLT_RADIX</code>.</p>
<p>If <code>FLT_RADIX</code> happens to be <code>2</code> (no
guarantees!), then this works like <a href="#man-exp2"><code>exp2()</code></a>.</p>
<p>The name of this function should have an obvious meaning to you.
Clearly they all start with the prefix “scalb” which means…</p>
<p>…OK, I confess! I have no idea what it means. My searches are
futile!</p>
<p>But let’s look at the suffixes:</p>
<table>
<thead>
<tr class="header">
<th>Suffix</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>n</code></td>
<td><code>scalbn()</code>—exponent <code>n</code> is an
<code>int</code></td>
</tr>
<tr class="even">
<td><code>nf</code></td>
<td><code>scalbnf()</code>—<code>float</code> version of
<code>scalbn()</code></td>
</tr>
<tr class="odd">
<td><code>nl</code></td>
<td><code>scalbnl()</code>—<code>long double</code> version of
<code>scalbn()</code></td>
</tr>
<tr class="even">
<td><code>ln</code></td>
<td><code>scalbln()</code>—exponent <code>n</code> is a
<code>long int</code></td>
</tr>
<tr class="odd">
<td><code>lnf</code></td>
<td><code>scalblnf()</code>—<code>float</code> version of
<code>scalbln()</code></td>
</tr>
<tr class="even">
<td><code>lnl</code></td>
<td><code>scalblnl()</code>—<code>long double</code> version of
<code>scalbln()</code></td>
</tr>
</tbody>
</table>
<p>So while I’m still in the dark about “scalb”, at least I have that
part down.</p>
<p>A range error might occur for large values.</p>
<h3 class="unnumbered unlisted" id="return-value-80">Return Value</h3>
<p>Returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="61" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>×</mo><msup><mi>r</mi><mi>n</mi></msup></math></mjx-assistive-mml></mjx-container></span>, where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="62" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></mjx-assistive-mml></mjx-container></span> is <code>FLT_RADIX</code>.</p>
<h3 class="unnumbered unlisted" id="example-81">Example</h3>
<div class="sourceCode" id="cb1040"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1040-1"><a href="math.html#cb1040-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1040-2"><a href="math.html#cb1040-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1040-3"><a href="math.html#cb1040-3"></a><span class="pp">#include </span><span class="im">&lt;float.h&gt;</span></span>
<span id="cb1040-4"><a href="math.html#cb1040-4"></a></span>
<span id="cb1040-5"><a href="math.html#cb1040-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1040-6"><a href="math.html#cb1040-6"></a><span class="op">{</span></span>
<span id="cb1040-7"><a href="math.html#cb1040-7"></a>    printf<span class="op">(</span><span class="st">"FLT_RADIX = %d</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> FLT_RADIX<span class="op">);</span></span>
<span id="cb1040-8"><a href="math.html#cb1040-8"></a>    printf<span class="op">(</span><span class="st">"scalbn(3, 8)      = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> scalbn<span class="op">(</span><span class="dv">2</span><span class="op">,</span> <span class="dv">8</span><span class="op">));</span></span>
<span id="cb1040-9"><a href="math.html#cb1040-9"></a>    printf<span class="op">(</span><span class="st">"scalbnf(10.2, 20) = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> scalbnf<span class="op">(</span><span class="fl">10.2</span><span class="op">,</span> <span class="dv">20</span><span class="op">));</span></span>
<span id="cb1040-10"><a href="math.html#cb1040-10"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1041"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1041-1"><a href="math.html#cb1041-1" aria-hidden="true" tabindex="-1"></a>FLT_RADIX = 2</span>
<span id="cb1041-2"><a href="math.html#cb1041-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1041-3"><a href="math.html#cb1041-3" aria-hidden="true" tabindex="-1"></a>scalbn(3, 8)       = 512.000000</span>
<span id="cb1041-4"><a href="math.html#cb1041-4" aria-hidden="true" tabindex="-1"></a>scalbn(10.2, 20.7) = 10695475.200000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-77">See Also</h3>
<p><a href="math.html#man-exp2"><code>exp2()</code></a>, <a href="#man-pow"><code>pow()</code></a></p>
<hr>
<h2 data-number="52.34" id="man-cbrt"><span class="header-section-number">52.34</span> <code>cbrt()</code>,
<code>cbrtf()</code>, <code>cbrtl()</code></h2>
<p>Compute the cube root.</p>
<h3 class="unnumbered unlisted" id="synopsis-82">Synopsis</h3>
<div class="sourceCode" id="cb1042"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1042-1"><a href="math.html#cb1042-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1042-2"><a href="math.html#cb1042-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1042-3"><a href="math.html#cb1042-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> cbrt<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1042-4"><a href="math.html#cb1042-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1042-5"><a href="math.html#cb1042-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> cbrtf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1042-6"><a href="math.html#cb1042-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1042-7"><a href="math.html#cb1042-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> cbrtl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-82">Description</h3>
<p>Computes the cube root of <code>x</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="63" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>x</mi><mrow data-mjx-texclass="ORD"><mn>1</mn><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>3</mn></mrow></msup></math></mjx-assistive-mml></mjx-container></span>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="64" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mroot><mjx-root style="vertical-align: 0.344em; width: 0px;"><mjx-mn class="mjx-n" size="ss" style="padding-left: 0.524em;"><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-root><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.281em;"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-box></mjx-sqrt></mjx-mroot></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mroot><mi>x</mi><mn>3</mn></mroot></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="return-value-81">Return Value</h3>
<p>Returns the cube root of <code>x</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="65" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>x</mi><mrow data-mjx-texclass="ORD"><mn>1</mn><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>3</mn></mrow></msup></math></mjx-assistive-mml></mjx-container></span>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="66" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mroot><mjx-root style="vertical-align: 0.344em; width: 0px;"><mjx-mn class="mjx-n" size="ss" style="padding-left: 0.524em;"><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-root><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.281em;"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-box></mjx-sqrt></mjx-mroot></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mroot><mi>x</mi><mn>3</mn></mroot></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-82">Example</h3>
<div class="sourceCode" id="cb1043"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1043-1"><a href="math.html#cb1043-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1043-2"><a href="math.html#cb1043-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1043-3"><a href="math.html#cb1043-3"></a></span>
<span id="cb1043-4"><a href="math.html#cb1043-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1043-5"><a href="math.html#cb1043-5"></a><span class="op">{</span></span>
<span id="cb1043-6"><a href="math.html#cb1043-6"></a>    printf<span class="op">(</span><span class="st">"cbrt(1729.03) = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> cbrt<span class="op">(</span><span class="fl">1729.03</span><span class="op">));</span></span>
<span id="cb1043-7"><a href="math.html#cb1043-7"></a><span class="op">}</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1044"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1044-1"><a href="math.html#cb1044-1" aria-hidden="true" tabindex="-1"></a>cbrt(1729.03) = 12.002384</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-78">See Also</h3>
<p><a href="math.html#man-sqrt"><code>sqrt()</code></a>, <a href="#man-pow"><code>pow()</code></a></p>
<hr>
<h2 data-number="52.35" id="man-fabs"><span class="header-section-number">52.35</span> <code>fabs()</code>,
<code>fabsf()</code>, <code>fabsl()</code></h2>
<p>Compute the absolute value.</p>
<h3 class="unnumbered unlisted" id="synopsis-83">Synopsis</h3>
<div class="sourceCode" id="cb1045"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1045-1"><a href="math.html#cb1045-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1045-2"><a href="math.html#cb1045-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1045-3"><a href="math.html#cb1045-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> fabs<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1045-4"><a href="math.html#cb1045-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1045-5"><a href="math.html#cb1045-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> fabsf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1045-6"><a href="math.html#cb1045-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1045-7"><a href="math.html#cb1045-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> fabsl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-83">Description</h3>
<p>These functions straightforwardly return the absolute value of
<code>x</code>, that is <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="67" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>x</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>If you’re rusty on your absolute values, all it means is that the
result will be positive, even if <code>x</code> is negative. It’s just
strips negative signs off.</p>
<h3 class="unnumbered unlisted" id="return-value-82">Return Value</h3>
<p>Returns the absolute value of <code>x</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="68" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>x</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-83">Example</h3>
<div class="sourceCode" id="cb1046"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1046-1"><a href="math.html#cb1046-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1046-2"><a href="math.html#cb1046-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1046-3"><a href="math.html#cb1046-3"></a></span>
<span id="cb1046-4"><a href="math.html#cb1046-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1046-5"><a href="math.html#cb1046-5"></a><span class="op">{</span></span>
<span id="cb1046-6"><a href="math.html#cb1046-6"></a>    printf<span class="op">(</span><span class="st">"fabs(3490.0)  = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fabs<span class="op">(</span><span class="fl">3490.0</span><span class="op">));</span>  <span class="co">// 3490.000000</span></span>
<span id="cb1046-7"><a href="math.html#cb1046-7"></a>    printf<span class="op">(</span><span class="st">"fabs(-3490.0) = %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fabs<span class="op">(</span><span class="fl">3490.0</span><span class="op">));</span>  <span class="co">// 3490.000000</span></span>
<span id="cb1046-8"><a href="math.html#cb1046-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-79">See Also</h3>
<p><a href="stdlib.html#man-abs"><code>abs()</code></a>, <a href="#man-copysign"><code>copysign()</code></a>, <a href="#man-imaxabs"><code>imaxabs()</code></a></p>
<hr>
<h2 data-number="52.36" id="man-hypot"><span class="header-section-number">52.36</span> <code>hypot()</code>,
<code>hypotf()</code>, <code>hypotl()</code></h2>
<p>Compute the length of the hypotenuse of a triangle.</p>
<h3 class="unnumbered unlisted" id="synopsis-84">Synopsis</h3>
<div class="sourceCode" id="cb1047"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1047-1"><a href="math.html#cb1047-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1047-2"><a href="math.html#cb1047-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1047-3"><a href="math.html#cb1047-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> hypot<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1047-4"><a href="math.html#cb1047-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1047-5"><a href="math.html#cb1047-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> hypotf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1047-6"><a href="math.html#cb1047-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1047-7"><a href="math.html#cb1047-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> hypotl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-84">Description</h3>
<p><a href="https://en.wikipedia.org/wiki/Pythagorean_theorem">Pythagorean
Theorem</a><a href="footnotes.html#fn234" class="footnote-ref" id="fnref234" role="doc-noteref"><sup>234</sup></a> fans rejoice! This is the function
you’ve been waiting for!</p>
<p>If you know the lengths of the two sides of a right triangle,
<code>x</code> and <code>y</code>, you can compute the length of the
hypotenuse (the longest, diagonal side) with this function.</p>
<p>In particular, it computes the square root of the sum of the squares
of the sides: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="69" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msqrt><mjx-sqrt><mjx-surd><mjx-mo class="mjx-sop"><mjx-c class="mjx-c221A TEX-S1"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.125em;"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.289em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.289em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup></mjx-box></mjx-sqrt></mjx-msqrt></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msqrt><msup><mi>x</mi><mn>2</mn></msup><mo>+</mo><msup><mi>y</mi><mn>2</mn></msup></msqrt></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="return-value-83">Return Value</h3>
<p>Returns the lenght of the hypotenuse of a right triangle with side
lengths <code>x</code> and <code>y</code>: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="70" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msqrt><mjx-sqrt><mjx-surd><mjx-mo class="mjx-sop"><mjx-c class="mjx-c221A TEX-S1"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.125em;"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.289em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.289em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup></mjx-box></mjx-sqrt></mjx-msqrt></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msqrt><msup><mi>x</mi><mn>2</mn></msup><mo>+</mo><msup><mi>y</mi><mn>2</mn></msup></msqrt></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-84">Example</h3>
<div class="sourceCode" id="cb1048"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1048-1"><a href="math.html#cb1048-1"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> hypot<span class="op">(</span><span class="dv">3</span><span class="op">,</span> <span class="dv">4</span><span class="op">));</span>  <span class="co">// 5.000000</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-80">See Also</h3>
<p><a href="math.html#man-sqrt"><code>sqrt()</code></a></p>
<hr>
<h2 data-number="52.37" id="man-pow"><span class="header-section-number">52.37</span> <code>pow()</code>,
<code>powf()</code>, <code>powl()</code></h2>
<p>Compute a value raised to a power.</p>
<h3 class="unnumbered unlisted" id="synopsis-85">Synopsis</h3>
<div class="sourceCode" id="cb1049"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1049-1"><a href="math.html#cb1049-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1049-2"><a href="math.html#cb1049-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1049-3"><a href="math.html#cb1049-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> pow<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1049-4"><a href="math.html#cb1049-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1049-5"><a href="math.html#cb1049-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> powf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1049-6"><a href="math.html#cb1049-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1049-7"><a href="math.html#cb1049-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> powl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-85">Description</h3>
<p>Computes <code>x</code> raised to the <code>y</code>th power: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="71" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>x</mi><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>These arguments can be fractional.</p>
<h3 class="unnumbered unlisted" id="return-value-84">Return Value</h3>
<p>Returns <code>x</code> raised to the <code>y</code>th power: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="72" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>x</mi><mi>y</mi></msup></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>A domain error can occur if:</p>
<ul>
<li><code>x</code> is a finite negative number and <code>y</code> is a
finite non-integer</li>
<li><code>x</code> is zero and <code>y</code> is zero.</li>
</ul>
<p>A domain error or pole error can occur if <code>x</code> is zero and
<code>y</code> is negative.</p>
<p>A range error can occur for large values.</p>
<h3 class="unnumbered unlisted" id="example-85">Example</h3>
<div class="sourceCode" id="cb1050"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1050-1"><a href="math.html#cb1050-1"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pow<span class="op">(</span><span class="dv">3</span><span class="op">,</span> <span class="dv">4</span><span class="op">));</span>    <span class="co">// 3^4    = 81.000000</span></span>
<span id="cb1050-2"><a href="math.html#cb1050-2"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> pow<span class="op">(</span><span class="dv">2</span><span class="op">,</span> <span class="fl">0.5</span><span class="op">));</span>  <span class="co">// sqrt 2 = 1.414214</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-81">See Also</h3>
<p><a href="math.html#man-exp"><code>exp()</code></a>, <a href="#man-exp2"><code>exp2()</code></a>, <a href="#man-sqrt"><code>sqrt()</code></a>, <a href="#man-cbrt"><code>cbrt()</code></a></p>
<hr>
<h2 data-number="52.38" id="man-sqrt"><span class="header-section-number">52.38</span> <code>sqrt()</code></h2>
<p>Calculate the square root of a number.</p>
<h3 class="unnumbered unlisted" id="synopsis-86">Synopsis</h3>
<div class="sourceCode" id="cb1051"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1051-1"><a href="math.html#cb1051-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1051-2"><a href="math.html#cb1051-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1051-3"><a href="math.html#cb1051-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> sqrt<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1051-4"><a href="math.html#cb1051-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1051-5"><a href="math.html#cb1051-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> sqrtf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1051-6"><a href="math.html#cb1051-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1051-7"><a href="math.html#cb1051-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> sqrtl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-86">Description</h3>
<p>Computes the square root of a number: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="73" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msqrt><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.281em;"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-box></mjx-sqrt></mjx-msqrt></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msqrt><mi>x</mi></msqrt></math></mjx-assistive-mml></mjx-container></span>. To those of you who don’t know
what a square root is, I’m not going to explain. Suffice it to say, the
square root of a number delivers a value that when squared (multiplied
by itself) results in the original number.</p>
<p>Ok, fine—I did explain it after all, but only because I wanted to
show off. It’s not like I’m giving you examples or anything, such as the
square root of nine is three, because when you multiply three by three
you get nine, or anything like that. No examples. I hate examples!</p>
<p>And I suppose you wanted some actual practical information here as
well. You can see the usual trio of functions here—they all compute
square root, but they take different types as arguments. Pretty
straightforward, really.</p>
<p>A domain error occurs if <code>x</code> is negative.</p>
<h3 class="unnumbered unlisted" id="return-value-85">Return Value</h3>
<p>Returns (and I know this must be something of a surprise to you) the
square root of <code>x</code>: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="74" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msqrt><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.281em;"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-box></mjx-sqrt></mjx-msqrt></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msqrt><mi>x</mi></msqrt></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-86">Example</h3>
<div class="sourceCode" id="cb1052"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1052-1"><a href="math.html#cb1052-1"></a><span class="co">// example usage of sqrt()</span></span>
<span id="cb1052-2"><a href="math.html#cb1052-2"></a></span>
<span id="cb1052-3"><a href="math.html#cb1052-3"></a><span class="dt">float</span> something <span class="op">=</span> <span class="dv">10</span><span class="op">;</span></span>
<span id="cb1052-4"><a href="math.html#cb1052-4"></a></span>
<span id="cb1052-5"><a href="math.html#cb1052-5"></a><span class="dt">double</span> x1 <span class="op">=</span> <span class="fl">8.2</span><span class="op">,</span> y1 <span class="op">=</span> <span class="op">-</span><span class="fl">5.4</span><span class="op">;</span></span>
<span id="cb1052-6"><a href="math.html#cb1052-6"></a><span class="dt">double</span> x2 <span class="op">=</span> <span class="fl">3.8</span><span class="op">,</span> y2 <span class="op">=</span> <span class="fl">34.9</span><span class="op">;</span></span>
<span id="cb1052-7"><a href="math.html#cb1052-7"></a><span class="dt">double</span> dx<span class="op">,</span> dy<span class="op">;</span></span>
<span id="cb1052-8"><a href="math.html#cb1052-8"></a></span>
<span id="cb1052-9"><a href="math.html#cb1052-9"></a>printf<span class="op">(</span><span class="st">"square root of 10 is %.2f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> sqrtf<span class="op">(</span>something<span class="op">));</span></span>
<span id="cb1052-10"><a href="math.html#cb1052-10"></a></span>
<span id="cb1052-11"><a href="math.html#cb1052-11"></a>dx <span class="op">=</span> x2 <span class="op">-</span> x1<span class="op">;</span></span>
<span id="cb1052-12"><a href="math.html#cb1052-12"></a>dy <span class="op">=</span> y2 <span class="op">-</span> y1<span class="op">;</span></span>
<span id="cb1052-13"><a href="math.html#cb1052-13"></a>printf<span class="op">(</span><span class="st">"distance between points (x1, y1) and (x2, y2): %.2f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span></span>
<span id="cb1052-14"><a href="math.html#cb1052-14"></a>    sqrt<span class="op">(</span>dx<span class="op">*</span>dx <span class="op">+</span> dy<span class="op">*</span>dy<span class="op">));</span></span></code></pre></div>
<p>And the output is:</p>
<div class="sourceCode" id="cb1053"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1053-1"><a href="math.html#cb1053-1" aria-hidden="true" tabindex="-1"></a>square root of 10 is 3.16</span>
<span id="cb1053-2"><a href="math.html#cb1053-2" aria-hidden="true" tabindex="-1"></a>distance between points (x1, y1) and (x2, y2): 40.54</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-82">See Also</h3>
<p><a href="math.html#man-hypot"><code>hypot()</code></a>, <a href="#man-pow"><code>pow()</code></a></p>
<hr>
<h2 data-number="52.39" id="man-erf"><span class="header-section-number">52.39</span> <code>erf()</code>,
<code>erff()</code>, <code>erfl()</code></h2>
<p>Compute the error function of the given value.</p>
<h3 class="unnumbered unlisted" id="synopsis-87">Synopsis</h3>
<div class="sourceCode" id="cb1054"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1054-1"><a href="math.html#cb1054-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1054-2"><a href="math.html#cb1054-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1054-3"><a href="math.html#cb1054-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> erfc<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1054-4"><a href="math.html#cb1054-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1054-5"><a href="math.html#cb1054-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> erfcf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1054-6"><a href="math.html#cb1054-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1054-7"><a href="math.html#cb1054-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> erfcl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-87">Description</h3>
<p>These functions compute the <a href="https://en.wikipedia.org/wiki/Error_function">error function</a><a href="#fn235" class="footnote-ref" id="fnref235" role="doc-noteref"><sup>235</sup></a> of a value.</p>
<h3 class="unnumbered unlisted" id="return-value-86">Return Value</h3>
<p>Returns the error function of <code>x</code>:</p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="75" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mstyle><mjx-mfrac><mjx-frac type="d"><mjx-num><mjx-nstrut type="d"></mjx-nstrut><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-num><mjx-dbox><mjx-dtable><mjx-line type="d"></mjx-line><mjx-row><mjx-den><mjx-dstrut type="d"></mjx-dstrut><mjx-msqrt><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.286em;"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi></mjx-box></mjx-sqrt></mjx-msqrt></mjx-den></mjx-row></mjx-dtable></mjx-dbox></mjx-frac></mjx-mfrac><mjx-msubsup space="2"><mjx-mo class="mjx-lop"><mjx-c class="mjx-c222B TEX-S2"></mjx-c></mjx-mo><mjx-script style="vertical-align: -0.896em; margin-left: -0.388em;"><mjx-mi class="mjx-i" size="s" style="margin-left: 0.647em;"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-spacer style="margin-top: 1.506em;"></mjx-spacer><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-script></mjx-msubsup><mjx-msup space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.413em;"><mjx-texatom size="s" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D461 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup></mjx-texatom></mjx-script></mjx-msup><mjx-mstyle><mjx-mspace style="width: 0.167em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D451 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D461 TEX-I"></mjx-c></mjx-mi></mjx-mstyle></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mstyle displaystyle="true" scriptlevel="0"><mfrac><mn>2</mn><msqrt><mi>π</mi></msqrt></mfrac><msubsup><mo data-mjx-texclass="OP">∫</mo><mn>0</mn><mi>x</mi></msubsup><msup><mi>e</mi><mrow data-mjx-texclass="ORD"><mo>−</mo><msup><mi>t</mi><mn>2</mn></msup></mrow></msup><mstyle scriptlevel="0"><mspace width="0.167em"></mspace></mstyle><mi>d</mi><mi>t</mi></mstyle></mrow></math></mjx-assistive-mml></mjx-container></span></p>
<h3 class="unnumbered unlisted" id="example-87">Example</h3>
<div class="sourceCode" id="cb1055"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1055-1"><a href="math.html#cb1055-1"></a><span class="cf">for</span> <span class="op">(</span><span class="dt">float</span> i <span class="op">=</span> <span class="op">-</span><span class="dv">2</span><span class="op">;</span> i <span class="op">&lt;=</span> <span class="dv">2</span><span class="op">;</span> i <span class="op">+=</span> <span class="fl">0.5</span><span class="op">)</span></span>
<span id="cb1055-2"><a href="math.html#cb1055-2"></a>    printf<span class="op">(</span><span class="st">"% .1f: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">,</span> erf<span class="op">(</span>i<span class="op">));</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1056"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1056-1"><a href="math.html#cb1056-1" aria-hidden="true" tabindex="-1"></a>-2.0: -0.995322</span>
<span id="cb1056-2"><a href="math.html#cb1056-2" aria-hidden="true" tabindex="-1"></a>-1.5: -0.966105</span>
<span id="cb1056-3"><a href="math.html#cb1056-3" aria-hidden="true" tabindex="-1"></a>-1.0: -0.842701</span>
<span id="cb1056-4"><a href="math.html#cb1056-4" aria-hidden="true" tabindex="-1"></a>-0.5: -0.520500</span>
<span id="cb1056-5"><a href="math.html#cb1056-5" aria-hidden="true" tabindex="-1"></a> 0.0: 0.000000</span>
<span id="cb1056-6"><a href="math.html#cb1056-6" aria-hidden="true" tabindex="-1"></a> 0.5: 0.520500</span>
<span id="cb1056-7"><a href="math.html#cb1056-7" aria-hidden="true" tabindex="-1"></a> 1.0: 0.842701</span>
<span id="cb1056-8"><a href="math.html#cb1056-8" aria-hidden="true" tabindex="-1"></a> 1.5: 0.966105</span>
<span id="cb1056-9"><a href="math.html#cb1056-9" aria-hidden="true" tabindex="-1"></a> 2.0: 0.995322</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-83">See Also</h3>
<p><a href="math.html#man-erfc"><code>erfc()</code></a></p>
<hr>
<h2 data-number="52.40" id="man-erfc"><span class="header-section-number">52.40</span> <code>erfc()</code>,
<code>erfcf()</code>, <code>erfcl()</code></h2>
<p>Compute the complementary error function of a value.</p>
<h3 class="unnumbered unlisted" id="synopsis-88">Synopsis</h3>
<div class="sourceCode" id="cb1057"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1057-1"><a href="math.html#cb1057-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1057-2"><a href="math.html#cb1057-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1057-3"><a href="math.html#cb1057-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> erfc<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1057-4"><a href="math.html#cb1057-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1057-5"><a href="math.html#cb1057-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> erfcf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1057-6"><a href="math.html#cb1057-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1057-7"><a href="math.html#cb1057-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> erfcl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-88">Description</h3>
<p>These functions compute the <a href="https://en.wikipedia.org/wiki/Error_function">complementary error
function</a><a href="footnotes.html#fn236" class="footnote-ref" id="fnref236" role="doc-noteref"><sup>236</sup></a> of a value.</p>
<p>This is the same as:</p>
<div class="sourceCode" id="cb1058"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1058-1"><a href="math.html#cb1058-1" aria-hidden="true" tabindex="-1"></a><span class="dv">1</span> <span class="op">-</span> erf<span class="op">(</span>x<span class="op">)</span></span></code></pre></div>
<p>A range error can occur if <code>x</code> is too large.</p>
<h3 class="unnumbered unlisted" id="return-value-87">Return Value</h3>
<p>Returns <code>1 - erf(x)</code>, namely:</p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="76" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mstyle><mjx-mfrac><mjx-frac type="d"><mjx-num><mjx-nstrut type="d"></mjx-nstrut><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-num><mjx-dbox><mjx-dtable><mjx-line type="d"></mjx-line><mjx-row><mjx-den><mjx-dstrut type="d"></mjx-dstrut><mjx-msqrt><mjx-sqrt><mjx-surd><mjx-mo class="mjx-n"><mjx-c class="mjx-c221A"></mjx-c></mjx-mo></mjx-surd><mjx-box style="padding-top: 0.286em;"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi></mjx-box></mjx-sqrt></mjx-msqrt></mjx-den></mjx-row></mjx-dtable></mjx-dbox></mjx-frac></mjx-mfrac><mjx-msubsup space="2"><mjx-mo class="mjx-lop"><mjx-c class="mjx-c222B TEX-S2"></mjx-c></mjx-mo><mjx-script style="vertical-align: -0.896em; margin-left: -0.388em;"><mjx-texatom size="s" texclass="ORD" style="margin-left: 0.647em;"><mjx-mi class="mjx-n"><mjx-c class="mjx-c221E"></mjx-c></mjx-mi></mjx-texatom><mjx-spacer style="margin-top: 1.664em;"></mjx-spacer><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msubsup><mjx-msup space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.413em;"><mjx-texatom size="s" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D461 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup></mjx-texatom></mjx-script></mjx-msup><mjx-mstyle><mjx-mspace style="width: 0.167em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D451 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D461 TEX-I"></mjx-c></mjx-mi></mjx-mstyle></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mstyle displaystyle="true" scriptlevel="0"><mfrac><mn>2</mn><msqrt><mi>π</mi></msqrt></mfrac><msubsup><mo data-mjx-texclass="OP">∫</mo><mi>x</mi><mrow data-mjx-texclass="ORD"><mi mathvariant="normal">∞</mi></mrow></msubsup><msup><mi>e</mi><mrow data-mjx-texclass="ORD"><mo>−</mo><msup><mi>t</mi><mn>2</mn></msup></mrow></msup><mstyle scriptlevel="0"><mspace width="0.167em"></mspace></mstyle><mi>d</mi><mi>t</mi></mstyle></mrow></math></mjx-assistive-mml></mjx-container></span></p>
<h3 class="unnumbered unlisted" id="example-88">Example</h3>
<div class="sourceCode" id="cb1059"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1059-1"><a href="math.html#cb1059-1"></a><span class="cf">for</span> <span class="op">(</span><span class="dt">float</span> i <span class="op">=</span> <span class="op">-</span><span class="dv">2</span><span class="op">;</span> i <span class="op">&lt;=</span> <span class="dv">2</span><span class="op">;</span> i <span class="op">+=</span> <span class="fl">0.5</span><span class="op">)</span></span>
<span id="cb1059-2"><a href="math.html#cb1059-2"></a>    printf<span class="op">(</span><span class="st">"% .1f: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">,</span> erfc<span class="op">(</span>i<span class="op">));</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1060"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1060-1"><a href="math.html#cb1060-1" aria-hidden="true" tabindex="-1"></a>-2.0: 1.995322</span>
<span id="cb1060-2"><a href="math.html#cb1060-2" aria-hidden="true" tabindex="-1"></a>-1.5: 1.966105</span>
<span id="cb1060-3"><a href="math.html#cb1060-3" aria-hidden="true" tabindex="-1"></a>-1.0: 1.842701</span>
<span id="cb1060-4"><a href="math.html#cb1060-4" aria-hidden="true" tabindex="-1"></a>-0.5: 1.520500</span>
<span id="cb1060-5"><a href="math.html#cb1060-5" aria-hidden="true" tabindex="-1"></a> 0.0: 1.000000</span>
<span id="cb1060-6"><a href="math.html#cb1060-6" aria-hidden="true" tabindex="-1"></a> 0.5: 0.479500</span>
<span id="cb1060-7"><a href="math.html#cb1060-7" aria-hidden="true" tabindex="-1"></a> 1.0: 0.157299</span>
<span id="cb1060-8"><a href="math.html#cb1060-8" aria-hidden="true" tabindex="-1"></a> 1.5: 0.033895</span>
<span id="cb1060-9"><a href="math.html#cb1060-9" aria-hidden="true" tabindex="-1"></a> 2.0: 0.004678</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-84">See Also</h3>
<p><a href="math.html#man-erf"><code>erf()</code></a></p>
<hr>
<h2 data-number="52.41" id="man-lgamma"><span class="header-section-number">52.41</span> <code>lgamma()</code>,
<code>lgammaf()</code>, <code>lgammal()</code></h2>
<p>Compute the natural logarithm of the absolute value of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="77" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="synopsis-89">Synopsis</h3>
<div class="sourceCode" id="cb1061"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1061-1"><a href="math.html#cb1061-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1061-2"><a href="math.html#cb1061-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1061-3"><a href="math.html#cb1061-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> lgamma<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1061-4"><a href="math.html#cb1061-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1061-5"><a href="math.html#cb1061-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> lgammaf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1061-6"><a href="math.html#cb1061-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1061-7"><a href="math.html#cb1061-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> lgammal<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-89">Description</h3>
<p>Compute the natural log of the absolute value of <a href="https://en.wikipedia.org/wiki/Gamma_function">gamma</a><a href="#fn237" class="footnote-ref" id="fnref237" role="doc-noteref"><sup>237</sup></a> <code>x</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="78" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>e</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>A range error can occur if <code>x</code> is too large.</p>
<p>A pole error can occur is <code>x</code> is non-positive.</p>
<h3 class="unnumbered unlisted" id="return-value-88">Return Value</h3>
<p>Returns <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="79" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-n"><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c67"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.241em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>log</mi><mi>e</mi></msub><mo data-mjx-texclass="NONE">⁡</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mo data-mjx-texclass="ORD" stretchy="false">|</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-89">Example</h3>
<div class="sourceCode" id="cb1062"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1062-1"><a href="math.html#cb1062-1"></a><span class="cf">for</span> <span class="op">(</span><span class="dt">float</span> i <span class="op">=</span> <span class="fl">0.5</span><span class="op">;</span> i <span class="op">&lt;=</span> <span class="dv">4</span><span class="op">;</span> i <span class="op">+=</span> <span class="fl">0.5</span><span class="op">)</span></span>
<span id="cb1062-2"><a href="math.html#cb1062-2"></a>    printf<span class="op">(</span><span class="st">"%.1f: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">,</span> lgamma<span class="op">(</span>i<span class="op">));</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1063"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1063-1"><a href="math.html#cb1063-1" aria-hidden="true" tabindex="-1"></a>0.5: 0.572365</span>
<span id="cb1063-2"><a href="math.html#cb1063-2" aria-hidden="true" tabindex="-1"></a>1.0: 0.000000</span>
<span id="cb1063-3"><a href="math.html#cb1063-3" aria-hidden="true" tabindex="-1"></a>1.5: -0.120782</span>
<span id="cb1063-4"><a href="math.html#cb1063-4" aria-hidden="true" tabindex="-1"></a>2.0: 0.000000</span>
<span id="cb1063-5"><a href="math.html#cb1063-5" aria-hidden="true" tabindex="-1"></a>2.5: 0.284683</span>
<span id="cb1063-6"><a href="math.html#cb1063-6" aria-hidden="true" tabindex="-1"></a>3.0: 0.693147</span>
<span id="cb1063-7"><a href="math.html#cb1063-7" aria-hidden="true" tabindex="-1"></a>3.5: 1.200974</span>
<span id="cb1063-8"><a href="math.html#cb1063-8" aria-hidden="true" tabindex="-1"></a>4.0: 1.791759</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-85">See Also</h3>
<p><a href="math.html#man-tgamma"><code>tgamma()</code></a></p>
<hr>
<h2 data-number="52.42" id="man-tgamma"><span class="header-section-number">52.42</span> <code>tgamma()</code>,
<code>tgammaf()</code>, <code>tgammal()</code></h2>
<p>Compute the gamma function, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="80" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="synopsis-90">Synopsis</h3>
<div class="sourceCode" id="cb1064"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1064-1"><a href="math.html#cb1064-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1064-2"><a href="math.html#cb1064-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1064-3"><a href="math.html#cb1064-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> tgamma<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1064-4"><a href="math.html#cb1064-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1064-5"><a href="math.html#cb1064-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> tgammaf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1064-6"><a href="math.html#cb1064-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1064-7"><a href="math.html#cb1064-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> tgammal<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-90">Description</h3>
<p>Computes the <a href="https://en.wikipedia.org/wiki/Gamma_function">gamma function</a><a href="#fn238" class="footnote-ref" id="fnref238" role="doc-noteref"><sup>238</sup></a> of <code>x</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="81" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>A domain or pole error might occur if <code>x</code> is
non-positive.</p>
<p>A range error might occur if <code>x</code> is too large or too
small.</p>
<h3 class="unnumbered unlisted" id="return-value-89">Return Value</h3>
<p>Returns the gamma function of <code>x</code>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="82" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c393"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">Γ</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-90">Example</h3>
<div class="sourceCode" id="cb1065"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1065-1"><a href="math.html#cb1065-1"></a><span class="cf">for</span> <span class="op">(</span><span class="dt">float</span> i <span class="op">=</span> <span class="fl">0.5</span><span class="op">;</span> i <span class="op">&lt;=</span> <span class="dv">4</span><span class="op">;</span> i <span class="op">+=</span> <span class="fl">0.5</span><span class="op">)</span></span>
<span id="cb1065-2"><a href="math.html#cb1065-2"></a>    printf<span class="op">(</span><span class="st">"%.1f: %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> i<span class="op">,</span> tgamma<span class="op">(</span>i<span class="op">));</span></span></code></pre></div>
<p>Output:</p>
<div class="sourceCode" id="cb1066"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1066-1"><a href="math.html#cb1066-1" aria-hidden="true" tabindex="-1"></a>0.5: 1.772454</span>
<span id="cb1066-2"><a href="math.html#cb1066-2" aria-hidden="true" tabindex="-1"></a>1.0: 1.000000</span>
<span id="cb1066-3"><a href="math.html#cb1066-3" aria-hidden="true" tabindex="-1"></a>1.5: 0.886227</span>
<span id="cb1066-4"><a href="math.html#cb1066-4" aria-hidden="true" tabindex="-1"></a>2.0: 1.000000</span>
<span id="cb1066-5"><a href="math.html#cb1066-5" aria-hidden="true" tabindex="-1"></a>2.5: 1.329340</span>
<span id="cb1066-6"><a href="math.html#cb1066-6" aria-hidden="true" tabindex="-1"></a>3.0: 2.000000</span>
<span id="cb1066-7"><a href="math.html#cb1066-7" aria-hidden="true" tabindex="-1"></a>3.5: 3.323351</span>
<span id="cb1066-8"><a href="math.html#cb1066-8" aria-hidden="true" tabindex="-1"></a>4.0: 6.000000</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-86">See Also</h3>
<p><a href="math.html#man-lgamma"><code>lgamma()</code></a></p>
<hr>
<h2 data-number="52.43" id="man-ceil"><span class="header-section-number">52.43</span> <code>ceil()</code>,
<code>ceilf()</code>, <code>ceill()</code></h2>
<p>Ceiling—return the next whole number not smaller than the given
number.</p>
<h3 class="unnumbered unlisted" id="synopsis-91">Synopsis</h3>
<div class="sourceCode" id="cb1067"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1067-1"><a href="math.html#cb1067-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1067-2"><a href="math.html#cb1067-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1067-3"><a href="math.html#cb1067-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> ceil<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1067-4"><a href="math.html#cb1067-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1067-5"><a href="math.html#cb1067-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> ceilf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1067-6"><a href="math.html#cb1067-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1067-7"><a href="math.html#cb1067-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> ceill<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-91">Description</h3>
<p>Returns the ceiling of the <code>x</code>: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="83" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2308"></mjx-c></mjx-mo><mjx-texatom texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c2309"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo fence="false" stretchy="false">⌈</mo><mrow data-mjx-texclass="ORD"><mi>x</mi></mrow><mo fence="false" stretchy="false">⌉</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>This is the next whole number not smaller than <code>x</code>.</p>
<p>Beware this minor dragon: it’s not just “rounding up”. Well, it is
for positive numbers, but negative numbers effectively round toward
zero. (Because the ceiling function is headed for the next largest whole
number and <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="84" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c34"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>4</mn></math></mjx-assistive-mml></mjx-container></span> is larger than <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="85" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>5</mn></math></mjx-assistive-mml></mjx-container></span>.)</p>
<h3 class="unnumbered unlisted" id="return-value-90">Return Value</h3>
<p>Returns the next largest whole number larger than <code>x</code>.</p>
<h3 class="unnumbered unlisted" id="example-91">Example</h3>
<p>Notice for the negative numbers it heads toward zero, i.e.&nbsp;toward the
next largest whole number—just like the positives head toward the next
largest whole number.</p>
<div class="sourceCode" id="cb1068"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1068-1"><a href="math.html#cb1068-1"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ceil<span class="op">(</span><span class="fl">4.0</span><span class="op">));</span>   <span class="co">//  4.000000</span></span>
<span id="cb1068-2"><a href="math.html#cb1068-2"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ceil<span class="op">(</span><span class="fl">4.1</span><span class="op">));</span>   <span class="co">//  5.000000</span></span>
<span id="cb1068-3"><a href="math.html#cb1068-3"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ceil<span class="op">(-</span><span class="fl">2.0</span><span class="op">));</span>  <span class="co">// -2.000000</span></span>
<span id="cb1068-4"><a href="math.html#cb1068-4"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ceil<span class="op">(-</span><span class="fl">2.1</span><span class="op">));</span>  <span class="co">// -2.000000</span></span>
<span id="cb1068-5"><a href="math.html#cb1068-5"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> ceil<span class="op">(-</span><span class="fl">3.1</span><span class="op">));</span>  <span class="co">// -3.000000</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-87">See Also</h3>
<p><a href="math.html#man-floor"><code>floor()</code></a>, <a href="#man-round"><code>round()</code></a></p>
<hr>
<h2 data-number="52.44" id="man-floor"><span class="header-section-number">52.44</span> <code>floor()</code>,
<code>floorf()</code>, <code>floorl()</code></h2>
<p>Compute the largest whole number not larger than the given value.</p>
<h3 class="unnumbered unlisted" id="synopsis-92">Synopsis</h3>
<div class="sourceCode" id="cb1069"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1069-1"><a href="math.html#cb1069-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1069-2"><a href="math.html#cb1069-2" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> floor<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1069-3"><a href="math.html#cb1069-3" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> floorf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1069-4"><a href="math.html#cb1069-4" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> floorl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-92">Description</h3>
<p>Returns the floor of the value: <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="86" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c230A"></mjx-c></mjx-mo><mjx-texatom texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c230B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo fence="false" stretchy="false">⌊</mo><mrow data-mjx-texclass="ORD"><mi>x</mi></mrow><mo fence="false" stretchy="false">⌋</mo></math></mjx-assistive-mml></mjx-container></span>. This is the opposite
of <code>ceil()</code>.</p>
<p>This is the largest whole number that is not greater than
<code>x</code>.</p>
<p>For positive numbers, this is like rounding down: <code>4.5</code>
becomes <code>4.0</code>.</p>
<p>For negative numbers, it’s like rounding up: <code>-3.6</code>
becomes <code>-4.0</code>.</p>
<p>In both cases, those results are the largest whole number not bigger
than the given number.</p>
<h3 class="unnumbered unlisted" id="return-value-91">Return Value</h3>
<p>Returns the largest whole number not greater than <code>x</code>:
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="87" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c230A"></mjx-c></mjx-mo><mjx-texatom texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c230B"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo fence="false" stretchy="false">⌊</mo><mrow data-mjx-texclass="ORD"><mi>x</mi></mrow><mo fence="false" stretchy="false">⌋</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<h3 class="unnumbered unlisted" id="example-92">Example</h3>
<p>Note how the negative numbers effectively round away from zero,
unlike the positives.</p>
<div class="sourceCode" id="cb1070"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1070-1"><a href="math.html#cb1070-1"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> floor<span class="op">(</span><span class="fl">4.0</span><span class="op">));</span>   <span class="co">//  4.000000</span></span>
<span id="cb1070-2"><a href="math.html#cb1070-2"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> floor<span class="op">(</span><span class="fl">4.1</span><span class="op">));</span>   <span class="co">//  4.000000</span></span>
<span id="cb1070-3"><a href="math.html#cb1070-3"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> floor<span class="op">(-</span><span class="fl">2.0</span><span class="op">));</span>  <span class="co">// -2.000000</span></span>
<span id="cb1070-4"><a href="math.html#cb1070-4"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> floor<span class="op">(-</span><span class="fl">2.1</span><span class="op">));</span>  <span class="co">// -3.000000</span></span>
<span id="cb1070-5"><a href="math.html#cb1070-5"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> floor<span class="op">(-</span><span class="fl">3.1</span><span class="op">));</span>  <span class="co">// -4.000000</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-88">See Also</h3>
<p><a href="math.html#man-ceil"><code>ceil()</code></a>, <a href="#man-round"><code>round()</code></a></p>
<hr>
<h2 data-number="52.45" id="man-nearbyint"><span class="header-section-number">52.45</span> <code>nearbyint()</code>,
<code>nearbyintf()</code>, <code>nearbyintl()</code></h2>
<p>Rounds a value in the current rounding direction.</p>
<h3 class="unnumbered unlisted" id="synopsis-93">Synopsis</h3>
<div class="sourceCode" id="cb1071"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1071-1"><a href="math.html#cb1071-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1071-2"><a href="math.html#cb1071-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1071-3"><a href="math.html#cb1071-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> nearbyint<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1071-4"><a href="math.html#cb1071-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1071-5"><a href="math.html#cb1071-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> nearbyintf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1071-6"><a href="math.html#cb1071-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1071-7"><a href="math.html#cb1071-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> nearbyintl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-93">Description</h3>
<p>This function rounds <code>x</code> to the nearest integer in the
current rounding direction.</p>
<p>The rounding direction can be set with <a href="#man-fegetround"><code>fesetround()</code></a> in
<code>&lt;fenv.h&gt;</code>.</p>
<p><code>nearbyint()</code> won’t raise the “inexact” floating point
exception.</p>
<h3 class="unnumbered unlisted" id="return-value-92">Return Value</h3>
<p>Returns <code>x</code> rounded in the current rounding direction.</p>
<h3 class="unnumbered unlisted" id="example-93">Example</h3>
<div class="sourceCode" id="cb1072"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1072-1"><a href="math.html#cb1072-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1072-2"><a href="math.html#cb1072-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1072-3"><a href="math.html#cb1072-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb1072-4"><a href="math.html#cb1072-4"></a></span>
<span id="cb1072-5"><a href="math.html#cb1072-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1072-6"><a href="math.html#cb1072-6"></a><span class="op">{</span></span>
<span id="cb1072-7"><a href="math.html#cb1072-7"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON        </span><span class="co">// If supported</span></span>
<span id="cb1072-8"><a href="math.html#cb1072-8"></a></span>
<span id="cb1072-9"><a href="math.html#cb1072-9"></a>    fesetround<span class="op">(</span>FE_TONEAREST<span class="op">);</span>          <span class="co">// round to nearest</span></span>
<span id="cb1072-10"><a href="math.html#cb1072-10"></a></span>
<span id="cb1072-11"><a href="math.html#cb1072-11"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> nearbyint<span class="op">(</span><span class="fl">3.14</span><span class="op">));</span>   <span class="co">// 3.000000</span></span>
<span id="cb1072-12"><a href="math.html#cb1072-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> nearbyint<span class="op">(</span><span class="fl">3.74</span><span class="op">));</span>   <span class="co">// 4.000000</span></span>
<span id="cb1072-13"><a href="math.html#cb1072-13"></a></span>
<span id="cb1072-14"><a href="math.html#cb1072-14"></a>    fesetround<span class="op">(</span>FE_TOWARDZERO<span class="op">);</span>         <span class="co">// round toward zero</span></span>
<span id="cb1072-15"><a href="math.html#cb1072-15"></a></span>
<span id="cb1072-16"><a href="math.html#cb1072-16"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> nearbyint<span class="op">(</span><span class="fl">1.99</span><span class="op">));</span>   <span class="co">// 1.000000</span></span>
<span id="cb1072-17"><a href="math.html#cb1072-17"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> nearbyint<span class="op">(-</span><span class="fl">1.99</span><span class="op">));</span>  <span class="co">// -1.000000</span></span>
<span id="cb1072-18"><a href="math.html#cb1072-18"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-89">See Also</h3>
<p><a href="math.html#man-rint"><code>rint()</code></a>, <a href="#man-lrint"><code>lrint()</code></a>, <a href="#man-round"><code>round()</code></a>, <a href="#man-fegetround"><code>fesetround()</code></a>, <a href="#man-fegetround"><code>fegetround()</code></a></p>
<hr>
<h2 data-number="52.46" id="man-rint"><span class="header-section-number">52.46</span> <code>rint()</code>,
<code>rintf()</code>, <code>rintl()</code></h2>
<p>Rounds a value in the current rounding direction.</p>
<h3 class="unnumbered unlisted" id="synopsis-94">Synopsis</h3>
<div class="sourceCode" id="cb1073"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1073-1"><a href="math.html#cb1073-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1073-2"><a href="math.html#cb1073-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1073-3"><a href="math.html#cb1073-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> rint<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1073-4"><a href="math.html#cb1073-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1073-5"><a href="math.html#cb1073-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> rintf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1073-6"><a href="math.html#cb1073-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1073-7"><a href="math.html#cb1073-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> rintl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-94">Description</h3>
<p>This works just like <a href="#man-nearbyint"><code>nearbyint()</code></a> except that is can
raise the “inexact” floating point exception.</p>
<h3 class="unnumbered unlisted" id="return-value-93">Return Value</h3>
<p>Returns <code>x</code> rounded in the current rounding direction.</p>
<h3 class="unnumbered unlisted" id="example-94">Example</h3>
<div class="sourceCode" id="cb1074"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1074-1"><a href="math.html#cb1074-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1074-2"><a href="math.html#cb1074-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1074-3"><a href="math.html#cb1074-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb1074-4"><a href="math.html#cb1074-4"></a></span>
<span id="cb1074-5"><a href="math.html#cb1074-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1074-6"><a href="math.html#cb1074-6"></a><span class="op">{</span></span>
<span id="cb1074-7"><a href="math.html#cb1074-7"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON</span></span>
<span id="cb1074-8"><a href="math.html#cb1074-8"></a></span>
<span id="cb1074-9"><a href="math.html#cb1074-9"></a>    fesetround<span class="op">(</span>FE_TONEAREST<span class="op">);</span></span>
<span id="cb1074-10"><a href="math.html#cb1074-10"></a></span>
<span id="cb1074-11"><a href="math.html#cb1074-11"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rint<span class="op">(</span><span class="fl">3.14</span><span class="op">));</span>   <span class="co">// 3.000000</span></span>
<span id="cb1074-12"><a href="math.html#cb1074-12"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rint<span class="op">(</span><span class="fl">3.74</span><span class="op">));</span>   <span class="co">// 4.000000</span></span>
<span id="cb1074-13"><a href="math.html#cb1074-13"></a></span>
<span id="cb1074-14"><a href="math.html#cb1074-14"></a>    fesetround<span class="op">(</span>FE_TOWARDZERO<span class="op">);</span></span>
<span id="cb1074-15"><a href="math.html#cb1074-15"></a></span>
<span id="cb1074-16"><a href="math.html#cb1074-16"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rint<span class="op">(</span><span class="fl">1.99</span><span class="op">));</span>   <span class="co">// 1.000000</span></span>
<span id="cb1074-17"><a href="math.html#cb1074-17"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> rint<span class="op">(-</span><span class="fl">1.99</span><span class="op">));</span>  <span class="co">// -1.000000</span></span>
<span id="cb1074-18"><a href="math.html#cb1074-18"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-90">See Also</h3>
<p><a href="math.html#man-nearbyint"><code>nearbyint()</code></a>, <a href="#man-lrint"><code>lrint()</code></a>, <a href="#man-round"><code>round()</code></a>, <a href="#man-fegetround"><code>fesetround()</code></a>, <a href="#man-fegetround"><code>fegetround()</code></a></p>
<hr>
<h2 data-number="52.47" id="man-lrint"><span class="header-section-number">52.47</span> <code>lrint()</code>,
<code>lrintf()</code>, <code>lrintl()</code>, <code>llrint()</code>,
<code>llrintf()</code>, <code>llrintl()</code></h2>
<p>Returns <code>x</code> rounded in the current rounding direction as
an integer.</p>
<h3 class="unnumbered unlisted" id="synopsis-95">Synopsis</h3>
<div class="sourceCode" id="cb1075"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1075-1"><a href="math.html#cb1075-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1075-2"><a href="math.html#cb1075-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1075-3"><a href="math.html#cb1075-3" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> lrint<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1075-4"><a href="math.html#cb1075-4" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> lrintf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1075-5"><a href="math.html#cb1075-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> lrintl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1075-6"><a href="math.html#cb1075-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1075-7"><a href="math.html#cb1075-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> llrint<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1075-8"><a href="math.html#cb1075-8" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> llrintf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1075-9"><a href="math.html#cb1075-9" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> llrintl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-95">Description</h3>
<p>Round a floating point number in the current rounding direction, but
this time return an integer intead of a float. You know, just to mix it
up.</p>
<p>These come in two variants:</p>
<ul>
<li><code>lrint()</code>—returns <code>long int</code></li>
<li><code>llrint()</code>—returns <code>long long int</code></li>
</ul>
<p>If the result doesn’t fit in the return type, a domain or range error
might occur.</p>
<h3 class="unnumbered unlisted" id="return-value-94">Return Value</h3>
<p>The value of <code>x</code> rounded to an integer in the current
rounding direction.</p>
<h3 class="unnumbered unlisted" id="example-95">Example</h3>
<div class="sourceCode" id="cb1076"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1076-1"><a href="math.html#cb1076-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1076-2"><a href="math.html#cb1076-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1076-3"><a href="math.html#cb1076-3"></a><span class="pp">#include </span><span class="im">&lt;fenv.h&gt;</span></span>
<span id="cb1076-4"><a href="math.html#cb1076-4"></a></span>
<span id="cb1076-5"><a href="math.html#cb1076-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1076-6"><a href="math.html#cb1076-6"></a><span class="op">{</span></span>
<span id="cb1076-7"><a href="math.html#cb1076-7"></a>    <span class="pp">#pragma STDC FENV_ACCESS ON</span></span>
<span id="cb1076-8"><a href="math.html#cb1076-8"></a></span>
<span id="cb1076-9"><a href="math.html#cb1076-9"></a>    fesetround<span class="op">(</span>FE_TONEAREST<span class="op">);</span></span>
<span id="cb1076-10"><a href="math.html#cb1076-10"></a></span>
<span id="cb1076-11"><a href="math.html#cb1076-11"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lrint<span class="op">(</span><span class="fl">3.14</span><span class="op">));</span>   <span class="co">// 3</span></span>
<span id="cb1076-12"><a href="math.html#cb1076-12"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lrint<span class="op">(</span><span class="fl">3.74</span><span class="op">));</span>   <span class="co">// 4</span></span>
<span id="cb1076-13"><a href="math.html#cb1076-13"></a></span>
<span id="cb1076-14"><a href="math.html#cb1076-14"></a>    fesetround<span class="op">(</span>FE_TOWARDZERO<span class="op">);</span></span>
<span id="cb1076-15"><a href="math.html#cb1076-15"></a></span>
<span id="cb1076-16"><a href="math.html#cb1076-16"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lrint<span class="op">(</span><span class="fl">1.99</span><span class="op">));</span>   <span class="co">// 1</span></span>
<span id="cb1076-17"><a href="math.html#cb1076-17"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lrint<span class="op">(-</span><span class="fl">1.99</span><span class="op">));</span>  <span class="co">// -1</span></span>
<span id="cb1076-18"><a href="math.html#cb1076-18"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-91">See Also</h3>
<p><a href="math.html#man-nearbyint"><code>nearbyint()</code></a>, <a href="#man-lrint"><code>rint()</code></a>, <a href="#man-round"><code>round()</code></a>, <a href="#man-fegetround"><code>fesetround()</code></a>, <a href="#man-fegetround"><code>fegetround()</code></a></p>
<hr>
<h2 data-number="52.48" id="man-round"><span class="header-section-number">52.48</span> <code>round()</code>,
<code>roundf()</code>, <code>roundl()</code></h2>
<p>Round a number in the good old-fashioned way.</p>
<h3 class="unnumbered unlisted" id="synopsis-96">Synopsis</h3>
<div class="sourceCode" id="cb1077"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1077-1"><a href="math.html#cb1077-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1077-2"><a href="math.html#cb1077-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1077-3"><a href="math.html#cb1077-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> round<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1077-4"><a href="math.html#cb1077-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1077-5"><a href="math.html#cb1077-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> roundf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1077-6"><a href="math.html#cb1077-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1077-7"><a href="math.html#cb1077-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> roundl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-96">Description</h3>
<p>Rounds a number to the nearest whole value.</p>
<p>In case of halfsies, rounds away from zero (i.e.&nbsp;“round up” in
magnitude).</p>
<p>The current rounding direction’s Jedi mind tricks don’t work on this
function.</p>
<h3 class="unnumbered unlisted" id="return-value-95">Return Value</h3>
<p>The rounded value of <code>x</code>.</p>
<h3 class="unnumbered unlisted" id="example-96">Example</h3>
<div class="sourceCode" id="cb1078"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1078-1"><a href="math.html#cb1078-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1078-2"><a href="math.html#cb1078-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1078-3"><a href="math.html#cb1078-3"></a></span>
<span id="cb1078-4"><a href="math.html#cb1078-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1078-5"><a href="math.html#cb1078-5"></a><span class="op">{</span></span>
<span id="cb1078-6"><a href="math.html#cb1078-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> round<span class="op">(</span><span class="fl">3.14</span><span class="op">));</span>   <span class="co">// 3.000000</span></span>
<span id="cb1078-7"><a href="math.html#cb1078-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> round<span class="op">(</span><span class="fl">3.5</span><span class="op">));</span>    <span class="co">// 4.000000</span></span>
<span id="cb1078-8"><a href="math.html#cb1078-8"></a></span>
<span id="cb1078-9"><a href="math.html#cb1078-9"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> round<span class="op">(-</span><span class="fl">1.5</span><span class="op">));</span>   <span class="co">// -2.000000</span></span>
<span id="cb1078-10"><a href="math.html#cb1078-10"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> round<span class="op">(-</span><span class="fl">1.14</span><span class="op">));</span>  <span class="co">// -1.000000</span></span>
<span id="cb1078-11"><a href="math.html#cb1078-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-92">See Also</h3>
<p><a href="math.html#man-lround"><code>lround()</code></a>, <a href="#man-nearbyint"><code>nearbyint()</code></a>, <a href="#man-lrint"><code>rint()</code></a>, <a href="#man-lrint"><code>lrint()</code></a>, <a href="#man-trunc"><code>trunc()</code></a></p>
<hr>
<h2 data-number="52.49" id="man-lround"><span class="header-section-number">52.49</span> <code>lround()</code>,
<code>lroundf()</code>, <code>lroundl()</code> <code>llround()</code>,
<code>llroundf()</code>, <code>llroundl()</code></h2>
<p>Round a number in the good old-fashioned way, returning an
integer.</p>
<h3 class="unnumbered unlisted" id="synopsis-97">Synopsis</h3>
<div class="sourceCode" id="cb1079"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1079-1"><a href="math.html#cb1079-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1079-2"><a href="math.html#cb1079-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1079-3"><a href="math.html#cb1079-3" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> lround<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1079-4"><a href="math.html#cb1079-4" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> lroundf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1079-5"><a href="math.html#cb1079-5" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">int</span> lroundl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1079-6"><a href="math.html#cb1079-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1079-7"><a href="math.html#cb1079-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> llround<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1079-8"><a href="math.html#cb1079-8" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> llroundf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1079-9"><a href="math.html#cb1079-9" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">long</span> <span class="dt">int</span> llroundl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-97">Description</h3>
<p>These are just like <a href="math.html#man-round"><code>round()</code></a>
except they return integers.</p>
<p>Halfway values round away from zero, e.g.&nbsp;<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="88" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1.5</mn></math></mjx-assistive-mml></mjx-container></span> rounds to <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="89" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></mjx-assistive-mml></mjx-container></span> and <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="90" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1.5</mn></math></mjx-assistive-mml></mjx-container></span> rounds to <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="91" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>2</mn></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>The functions are grouped by return type:</p>
<ul>
<li><code>lround()</code>—returns a <code>long int</code></li>
<li><code>llround()</code>—returns a <code>long long int</code></li>
</ul>
<p>If the rounded value can’t find in the return time, a domain or range
error can occur.</p>
<h3 class="unnumbered unlisted" id="return-value-96">Return Value</h3>
<p>Returns the rounded value of <code>x</code> as an integer.</p>
<h3 class="unnumbered unlisted" id="example-97">Example</h3>
<div class="sourceCode" id="cb1080"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1080-1"><a href="math.html#cb1080-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1080-2"><a href="math.html#cb1080-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1080-3"><a href="math.html#cb1080-3"></a></span>
<span id="cb1080-4"><a href="math.html#cb1080-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1080-5"><a href="math.html#cb1080-5"></a><span class="op">{</span></span>
<span id="cb1080-6"><a href="math.html#cb1080-6"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lround<span class="op">(</span><span class="fl">3.14</span><span class="op">));</span>   <span class="co">// 3</span></span>
<span id="cb1080-7"><a href="math.html#cb1080-7"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lround<span class="op">(</span><span class="fl">3.5</span><span class="op">));</span>    <span class="co">// 4</span></span>
<span id="cb1080-8"><a href="math.html#cb1080-8"></a></span>
<span id="cb1080-9"><a href="math.html#cb1080-9"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lround<span class="op">(-</span><span class="fl">1.5</span><span class="op">));</span>   <span class="co">// -2</span></span>
<span id="cb1080-10"><a href="math.html#cb1080-10"></a>    printf<span class="op">(</span><span class="st">"%ld</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> lround<span class="op">(-</span><span class="fl">1.14</span><span class="op">));</span>  <span class="co">// -1</span></span>
<span id="cb1080-11"><a href="math.html#cb1080-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-93">See Also</h3>
<p><a href="math.html#man-lround"><code>round()</code></a>, <a href="#man-nearbyint"><code>nearbyint()</code></a>, <a href="#man-lrint"><code>rint()</code></a>, <a href="#man-lrint"><code>lrint()</code></a>, <a href="#man-trunc"><code>trunc()</code></a></p>
<hr>
<h2 data-number="52.50" id="man-trunc"><span class="header-section-number">52.50</span> <code>trunc()</code>,
<code>truncf()</code>, <code>truncl()</code></h2>
<p>Truncate the fractional part off a floating point value.</p>
<h3 class="unnumbered unlisted" id="synopsis-98">Synopsis</h3>
<div class="sourceCode" id="cb1081"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1081-1"><a href="math.html#cb1081-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1081-2"><a href="math.html#cb1081-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1081-3"><a href="math.html#cb1081-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> trunc<span class="op">(</span><span class="dt">double</span> x<span class="op">);</span></span>
<span id="cb1081-4"><a href="math.html#cb1081-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1081-5"><a href="math.html#cb1081-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> truncf<span class="op">(</span><span class="dt">float</span> x<span class="op">);</span></span>
<span id="cb1081-6"><a href="math.html#cb1081-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1081-7"><a href="math.html#cb1081-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> truncl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-98">Description</h3>
<p>These functions just drop the fractional part of a floating point
number. Boom.</p>
<p>In other words, they always round toward zero.</p>
<h3 class="unnumbered unlisted" id="return-value-97">Return Value</h3>
<p>Returns the truncated floating point number.</p>
<h3 class="unnumbered unlisted" id="example-98">Example</h3>
<div class="sourceCode" id="cb1082"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1082-1"><a href="math.html#cb1082-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1082-2"><a href="math.html#cb1082-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1082-3"><a href="math.html#cb1082-3"></a></span>
<span id="cb1082-4"><a href="math.html#cb1082-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1082-5"><a href="math.html#cb1082-5"></a><span class="op">{</span></span>
<span id="cb1082-6"><a href="math.html#cb1082-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> trunc<span class="op">(</span><span class="fl">3.14</span><span class="op">));</span>   <span class="co">// 3.000000</span></span>
<span id="cb1082-7"><a href="math.html#cb1082-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> trunc<span class="op">(</span><span class="fl">3.8</span><span class="op">));</span>    <span class="co">// 3.000000</span></span>
<span id="cb1082-8"><a href="math.html#cb1082-8"></a></span>
<span id="cb1082-9"><a href="math.html#cb1082-9"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> trunc<span class="op">(-</span><span class="fl">1.5</span><span class="op">));</span>   <span class="co">// -1.000000</span></span>
<span id="cb1082-10"><a href="math.html#cb1082-10"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> trunc<span class="op">(-</span><span class="fl">1.14</span><span class="op">));</span>  <span class="co">// -1.000000</span></span>
<span id="cb1082-11"><a href="math.html#cb1082-11"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-94">See Also</h3>
<p><a href="math.html#man-lround"><code>round()</code></a>, <a href="#man-lround"><code>lround()</code></a>, <a href="#man-nearbyint"><code>nearbyint()</code></a>, <a href="#man-lrint"><code>rint()</code></a>, <a href="#man-lrint"><code>lrint()</code></a></p>
<hr>
<h2 data-number="52.51" id="man-fmod"><span class="header-section-number">52.51</span> <code>fmod()</code>,
<code>fmodf()</code>, <code>fmodl()</code></h2>
<p>Compute the floating point remainder.</p>
<h3 class="unnumbered unlisted" id="synopsis-99">Synopsis</h3>
<div class="sourceCode" id="cb1083"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1083-1"><a href="math.html#cb1083-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1083-2"><a href="math.html#cb1083-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1083-3"><a href="math.html#cb1083-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> fmod<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1083-4"><a href="math.html#cb1083-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1083-5"><a href="math.html#cb1083-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> fmodf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1083-6"><a href="math.html#cb1083-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1083-7"><a href="math.html#cb1083-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> fmodl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-99">Description</h3>
<p>Returns the remainder of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="92" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mfrac><mjx-frac><mjx-num><mjx-nstrut></mjx-nstrut><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-num><mjx-dbox><mjx-dtable><mjx-line></mjx-line><mjx-row><mjx-den><mjx-dstrut></mjx-dstrut><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-den></mjx-row></mjx-dtable></mjx-dbox></mjx-frac></mjx-mfrac></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mfrac><mi>x</mi><mi>y</mi></mfrac></math></mjx-assistive-mml></mjx-container></span>. The result will have the
same sign as <code>x</code>.</p>
<p>Under the hood, the computation performed is:</p>
<div class="sourceCode" id="cb1084"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1084-1"><a href="math.html#cb1084-1" aria-hidden="true" tabindex="-1"></a>x <span class="op">-</span> trunc<span class="op">(</span>x <span class="op">/</span> y<span class="op">)</span> <span class="op">*</span> y</span></code></pre></div>
<p>But it might be easier just to think of the remainder.</p>
<h3 class="unnumbered unlisted" id="return-value-98">Return Value</h3>
<p>Returns the remainder of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="93" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mfrac><mjx-frac><mjx-num><mjx-nstrut></mjx-nstrut><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-num><mjx-dbox><mjx-dtable><mjx-line></mjx-line><mjx-row><mjx-den><mjx-dstrut></mjx-dstrut><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-den></mjx-row></mjx-dtable></mjx-dbox></mjx-frac></mjx-mfrac></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mfrac><mi>x</mi><mi>y</mi></mfrac></math></mjx-assistive-mml></mjx-container></span> with the same sign as
<code>x</code>.</p>
<h3 class="unnumbered unlisted" id="example-99">Example</h3>
<div class="sourceCode" id="cb1085"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1085-1"><a href="math.html#cb1085-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1085-2"><a href="math.html#cb1085-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1085-3"><a href="math.html#cb1085-3"></a></span>
<span id="cb1085-4"><a href="math.html#cb1085-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1085-5"><a href="math.html#cb1085-5"></a><span class="op">{</span></span>
<span id="cb1085-6"><a href="math.html#cb1085-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fmod<span class="op">(-</span><span class="fl">9.2</span><span class="op">,</span> <span class="fl">5.1</span><span class="op">));</span>  <span class="co">// -4.100000</span></span>
<span id="cb1085-7"><a href="math.html#cb1085-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fmod<span class="op">(</span><span class="fl">9.2</span><span class="op">,</span> <span class="fl">5.1</span><span class="op">));</span>   <span class="co">//  4.100000</span></span>
<span id="cb1085-8"><a href="math.html#cb1085-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-95">See Also</h3>
<p><a href="math.html#man-remainder"><code>remainder()</code></a></p>
<hr>
<h2 data-number="52.52" id="man-remainder"><span class="header-section-number">52.52</span> <code>remainder()</code>,
<code>remainderf()</code>, <code>remainderl()</code></h2>
<p>Compute the remainder IEC 60559-style.</p>
<h3 class="unnumbered unlisted" id="synopsis-100">Synopsis</h3>
<div class="sourceCode" id="cb1086"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1086-1"><a href="math.html#cb1086-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1086-2"><a href="math.html#cb1086-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1086-3"><a href="math.html#cb1086-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> remainder<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1086-4"><a href="math.html#cb1086-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1086-5"><a href="math.html#cb1086-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> remainderf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1086-6"><a href="math.html#cb1086-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1086-7"><a href="math.html#cb1086-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> remainderl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-100">Description</h3>
<p>This is similar to <code>fmod()</code>, but not quite the same.
<code>fmod()</code> is probably what you’re after if you’re expecting
remainders to wrap around like an odometer.</p>
<p>The C spec quotes IEC 60559 on how this works:</p>
<blockquote>
<p>When <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="94" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2260"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi><mo>≠</mo><mn>0</mn></math></mjx-assistive-mml></mjx-container></span>, the remainder <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="95" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi><mo>=</mo><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> REM <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="96" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi></math></mjx-assistive-mml></mjx-container></span> is defined regardless of the rounding
mode by the mathematical relation <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="97" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi><mo>=</mo><mi>x</mi><mo>−</mo><mi>n</mi><mi>y</mi></math></mjx-assistive-mml></mjx-container></span>, where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="98" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is the integer nearest the exact value
of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="99" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mi>y</mi></math></mjx-assistive-mml></mjx-container></span>; whenever <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="100" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mi>n</mi><mo>−</mo><mi>x</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mi>y</mi><mo data-mjx-texclass="ORD" stretchy="false">|</mo><mo>=</mo><mn>1</mn><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn></math></mjx-assistive-mml></mjx-container></span>, then <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="101" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is even. If <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="102" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45F TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi><mo>=</mo><mn>0</mn></math></mjx-assistive-mml></mjx-container></span>, its sign shall be that of <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="103" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
</blockquote>
<p>Hope that clears it up!</p>
<p>OK, maybe not. Here’s the upshot:</p>
<p>You know how if you <code>fmod()</code> something by, say
<code>2.0</code> you get a result that is somewhere between
<code>0.0</code> and <code>2.0</code>? And how if you just increase the
number that you’re modding by <code>2.0</code>, you can see the result
climb up to <code>2.0</code> and then wrap around to <code>0.0</code>
like your car’s odometer?</p>
<p><code>remainder()</code> works just like that, except if
<code>y</code> is <code>2.0</code>, it wraps from <code>-1.0</code> to
<code>1.0</code> instead of from <code>0.0</code> to
<code>2.0</code>.</p>
<p>In other words, the range of the function runs from <code>-y/2</code>
to <code>y/2</code>. Contrasted to <code>fmod()</code> that runs from
<code>0.0</code> to <code>y</code>, <code>remainder()</code>’s output is
just shifted down half a <code>y</code>.</p>
<p>And zero-remainder-anything is <code>0</code>.</p>
<p>Except if <code>y</code> is zero, the function might return zero or a
domain error might occur.</p>
<h3 class="unnumbered unlisted" id="return-value-99">Return Value</h3>
<p>The IEC 60559 result of <code>x</code>-remainder-<code>y</code>.</p>
<h3 class="unnumbered unlisted" id="example-100">Example</h3>
<div class="sourceCode" id="cb1087"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1087-1"><a href="math.html#cb1087-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1087-2"><a href="math.html#cb1087-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1087-3"><a href="math.html#cb1087-3"></a></span>
<span id="cb1087-4"><a href="math.html#cb1087-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1087-5"><a href="math.html#cb1087-5"></a><span class="op">{</span></span>
<span id="cb1087-6"><a href="math.html#cb1087-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> remainder<span class="op">(</span><span class="fl">3.7</span><span class="op">,</span> <span class="dv">4</span><span class="op">));</span>  <span class="co">// -0.300000</span></span>
<span id="cb1087-7"><a href="math.html#cb1087-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> remainder<span class="op">(</span><span class="fl">4.3</span><span class="op">,</span> <span class="dv">4</span><span class="op">));</span>  <span class="co">//  0.300000</span></span>
<span id="cb1087-8"><a href="math.html#cb1087-8"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-96">See Also</h3>
<p><a href="math.html#man-fmod"><code>fmod()</code></a>, <a href="#man-remquo"><code>remquo()</code></a></p>
<hr>
<h2 data-number="52.53" id="man-remquo"><span class="header-section-number">52.53</span> <code>remquo()</code>,
<code>remquof()</code>, <code>remquol()</code></h2>
<p>Compute the remainder and (some of the) quotient.</p>
<h3 class="unnumbered unlisted" id="synopsis-101">Synopsis</h3>
<div class="sourceCode" id="cb1088"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1088-1"><a href="math.html#cb1088-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1088-2"><a href="math.html#cb1088-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1088-3"><a href="math.html#cb1088-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> remquo<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">,</span> <span class="dt">int</span> <span class="op">*</span>quo<span class="op">);</span></span>
<span id="cb1088-4"><a href="math.html#cb1088-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1088-5"><a href="math.html#cb1088-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> remquof<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">,</span> <span class="dt">int</span> <span class="op">*</span>quo<span class="op">);</span></span>
<span id="cb1088-6"><a href="math.html#cb1088-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1088-7"><a href="math.html#cb1088-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> remquol<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">,</span> <span class="dt">int</span> <span class="op">*</span>quo<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-101">Description</h3>
<p>This is a funky little thing.</p>
<p>First of all, the return value is the remainder, the same as the <a href="#man-remainder"><code>remainder()</code></a> function, so check
that out.</p>
<p>And the quotient comes back in the <code>quo</code> pointer.</p>
<p>Or at least <em>some of it</em> does. You’ll get at least 3 bits
worth of the quotient.</p>
<p>But <em>why</em>?</p>
<p>So a couple things.</p>
<p>One is that the quotient of some very large floating point numbers
can easily be far too gigantic to fit in even a
<code>long long unsigned int</code>. So some of it might very well need
to be lopped off, anyway.</p>
<p>But at 3 bits? How’s that even useful? That only gets you from 0 to
7!</p>
<p>The C99 Rationale document states:</p>
<blockquote>
<p>The <code>remquo</code> functions are intended for implementing
argument reductions which can exploit a few low-order bits of the
quotient. Note that <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="104" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> may be so
large in magnitude relative to <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="105" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi></math></mjx-assistive-mml></mjx-container></span>
that an exact representation of the quotient is not practical.</p>
</blockquote>
<p>So… implementing argument reductions… which can exploit a few
low-order bits… Ooookay.</p>
<p><a href="https://en.cppreference.com/w/c/numeric/math/remquo">CPPReference
has this to say</a><a href="footnotes.html#fn239" class="footnote-ref" id="fnref239" role="doc-noteref"><sup>239</sup></a> on the matter, which is spoken so
well, I will quote wholesale:</p>
<blockquote>
<p>This function is useful when implementing periodic functions with the
period exactly representable as a floating-point value: when calculating
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="106" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c73"></mjx-c><mjx-c class="mjx-c69"></mjx-c><mjx-c class="mjx-c6E"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2061"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D70B TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>sin</mi><mo data-mjx-texclass="NONE">⁡</mo><mo stretchy="false">(</mo><mi>π</mi><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> for a very large
<code>x</code>, calling <code>sin</code> directly may result in a large
error, but if the function argument is first reduced with
<code>remquo</code>, the low-order bits of the quotient may be used to
determine the sign and the octant of the result within the period, while
the remainder may be used to calculate the value with high
precision.</p>
</blockquote>
<p>And there you have it. If you have another example that works for
you… congratulations! :)</p>
<h3 class="unnumbered unlisted" id="return-value-100">Return Value</h3>
<p>Returns the same as <a href="#man-remainder"><code>remainder</code></a>: The IEC 60559 result
of <code>x</code>-remainder-<code>y</code>.</p>
<p>In addition, at least the lowest 3 bits of the quotient will be
stored in <code>quo</code> with the same sign as <code>x/y</code>.</p>
<h3 class="unnumbered unlisted" id="example-101">Example</h3>
<p>There’s a <a href="https://en.cppreference.com/w/c/numeric/math/remquo">great
<code>cos()</code> example at CPPReference</a><a href="footnotes.html#fn240" class="footnote-ref" id="fnref240" role="doc-noteref"><sup>240</sup></a>
that covers a genuine use case.</p>
<p>But instead of stealing it, I’ll just post a simple example here and
you can visit their site for a real one.</p>
<div class="sourceCode" id="cb1089"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1089-1"><a href="math.html#cb1089-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1089-2"><a href="math.html#cb1089-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1089-3"><a href="math.html#cb1089-3"></a></span>
<span id="cb1089-4"><a href="math.html#cb1089-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1089-5"><a href="math.html#cb1089-5"></a><span class="op">{</span></span>
<span id="cb1089-6"><a href="math.html#cb1089-6"></a>    <span class="dt">int</span> quo<span class="op">;</span></span>
<span id="cb1089-7"><a href="math.html#cb1089-7"></a>    <span class="dt">double</span> rem<span class="op">;</span></span>
<span id="cb1089-8"><a href="math.html#cb1089-8"></a></span>
<span id="cb1089-9"><a href="math.html#cb1089-9"></a>    rem <span class="op">=</span> remquo<span class="op">(</span><span class="fl">12.75</span><span class="op">,</span> <span class="fl">2.25</span><span class="op">,</span> <span class="op">&amp;</span>quo<span class="op">);</span></span>
<span id="cb1089-10"><a href="math.html#cb1089-10"></a></span>
<span id="cb1089-11"><a href="math.html#cb1089-11"></a>    printf<span class="op">(</span><span class="st">"%d remainder %f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> quo<span class="op">,</span> rem<span class="op">);</span>  <span class="co">// 6 remainder -0.750000</span></span>
<span id="cb1089-12"><a href="math.html#cb1089-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-97">See Also</h3>
<p><a href="math.html#man-remainder"><code>remainder()</code></a>, <a href="#man-imaxdiv"><code>imaxdiv()</code></a></p>
<hr>
<h2 data-number="52.54" id="man-copysign"><span class="header-section-number">52.54</span> <code>copysign()</code>,
<code>copysignf()</code>, <code>copysignl()</code></h2>
<p>Copy the sign of one value into another.</p>
<h3 class="unnumbered unlisted" id="synopsis-102">Synopsis</h3>
<div class="sourceCode" id="cb1090"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1090-1"><a href="math.html#cb1090-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1090-2"><a href="math.html#cb1090-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1090-3"><a href="math.html#cb1090-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> copysign<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1090-4"><a href="math.html#cb1090-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1090-5"><a href="math.html#cb1090-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> copysignf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1090-6"><a href="math.html#cb1090-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1090-7"><a href="math.html#cb1090-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> copysignl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-102">Description</h3>
<p>These functions return a number that has the magnitude of
<code>x</code> and the sign of <code>y</code>. You can use them to
coerce the sign to that of another value.</p>
<p>Neither <code>x</code> nor <code>y</code> are modified, of course.
The return value holds the result.</p>
<h3 class="unnumbered unlisted" id="return-value-101">Return Value</h3>
<p>Returns a value with the magnitude of <code>x</code> and the sign of
<code>y</code>.</p>
<h3 class="unnumbered unlisted" id="example-102">Example</h3>
<div class="sourceCode" id="cb1091"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1091-1"><a href="math.html#cb1091-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1091-2"><a href="math.html#cb1091-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1091-3"><a href="math.html#cb1091-3"></a></span>
<span id="cb1091-4"><a href="math.html#cb1091-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1091-5"><a href="math.html#cb1091-5"></a><span class="op">{</span></span>
<span id="cb1091-6"><a href="math.html#cb1091-6"></a>    <span class="dt">double</span> x <span class="op">=</span> <span class="fl">34.9</span><span class="op">;</span></span>
<span id="cb1091-7"><a href="math.html#cb1091-7"></a>    <span class="dt">double</span> y <span class="op">=</span> <span class="op">-</span><span class="fl">999.9</span><span class="op">;</span></span>
<span id="cb1091-8"><a href="math.html#cb1091-8"></a>    <span class="dt">double</span> z <span class="op">=</span> <span class="fl">123.4</span><span class="op">;</span></span>
<span id="cb1091-9"><a href="math.html#cb1091-9"></a></span>
<span id="cb1091-10"><a href="math.html#cb1091-10"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> copysign<span class="op">(</span>x<span class="op">,</span> y<span class="op">));</span> <span class="co">// -34.900000</span></span>
<span id="cb1091-11"><a href="math.html#cb1091-11"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> copysign<span class="op">(</span>x<span class="op">,</span> z<span class="op">));</span> <span class="co">//  34.900000</span></span>
<span id="cb1091-12"><a href="math.html#cb1091-12"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-98">See Also</h3>
<p><a href="math.html#man-signbit"><code>signbit()</code></a></p>
<hr>
<h2 data-number="52.55" id="man-nan"><span class="header-section-number">52.55</span> <code>nan()</code>,
<code>nanf()</code>, <code>nanl()</code></h2>
<p>Return <code>NAN</code>.</p>
<h3 class="unnumbered unlisted" id="synopsis-103">Synopsis</h3>
<div class="sourceCode" id="cb1092"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1092-1"><a href="math.html#cb1092-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1092-2"><a href="math.html#cb1092-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1092-3"><a href="math.html#cb1092-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> nan<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>tagp<span class="op">);</span></span>
<span id="cb1092-4"><a href="math.html#cb1092-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1092-5"><a href="math.html#cb1092-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> nanf<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>tagp<span class="op">);</span></span>
<span id="cb1092-6"><a href="math.html#cb1092-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1092-7"><a href="math.html#cb1092-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> nanl<span class="op">(</span><span class="dt">const</span> <span class="dt">char</span> <span class="op">*</span>tagp<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-103">Description</h3>
<p>These functions return a quiet NaN<a href="footnotes.html#fn241" class="footnote-ref" id="fnref241" role="doc-noteref"><sup>241</sup></a>. It is produced as if calling <a href="#man-strtod"><code>strtod()</code></a> with <code>"NAN"</code> (or
a variant thereof) as an argument.</p>
<p><code>tagp</code> points to a string which could be several things,
including empty. The contents of the string determine which variant of
NaN might get returned depending on the implementation.</p>
<p>Which <em>version</em> of NaN? Did you even know it was possible to
get this far into the weeds with something that wasn’t a number?</p>
<p>Case 1 in which you pass in an empty string, in which case these are
the same:</p>
<div class="sourceCode" id="cb1093"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1093-1"><a href="math.html#cb1093-1" aria-hidden="true" tabindex="-1"></a>nan<span class="op">(</span><span class="st">""</span><span class="op">);</span></span>
<span id="cb1093-2"><a href="math.html#cb1093-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1093-3"><a href="math.html#cb1093-3" aria-hidden="true" tabindex="-1"></a>strtod<span class="op">(</span><span class="st">"NAN()"</span><span class="op">,</span> NULL<span class="op">);</span></span></code></pre></div>
<p>Case 2 in which the string contains only digits 0-9, letters a-z,
letters A-Z, and/or underscore:</p>
<div class="sourceCode" id="cb1094"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1094-1"><a href="math.html#cb1094-1" aria-hidden="true" tabindex="-1"></a>nan<span class="op">(</span><span class="st">"goats"</span><span class="op">);</span></span>
<span id="cb1094-2"><a href="math.html#cb1094-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1094-3"><a href="math.html#cb1094-3" aria-hidden="true" tabindex="-1"></a>strtod<span class="op">(</span><span class="st">"NAN(goats)"</span><span class="op">,</span> NULL<span class="op">);</span></span></code></pre></div>
<p>And Case 3, in which the string contains anything else and is
ignored:</p>
<div class="sourceCode" id="cb1095"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1095-1"><a href="math.html#cb1095-1" aria-hidden="true" tabindex="-1"></a>nan<span class="op">(</span><span class="st">"!"</span><span class="op">);</span></span>
<span id="cb1095-2"><a href="math.html#cb1095-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1095-3"><a href="math.html#cb1095-3" aria-hidden="true" tabindex="-1"></a>strtod<span class="op">(</span><span class="st">"NAN"</span><span class="op">,</span> NULL<span class="op">);</span></span></code></pre></div>
<p>As for what <code>strtod()</code> does with those values in parens,
see the [<code>strtod()</code>] reference page. Spoiler: it’s
implementation-defined.</p>
<h3 class="unnumbered unlisted" id="return-value-102">Return Value</h3>
<p>Returns the requested quiet NaN, or 0 if such things aren’t supported
by your system.</p>
<h3 class="unnumbered unlisted" id="example-103">Example</h3>
<div class="sourceCode" id="cb1096"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1096-1"><a href="math.html#cb1096-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1096-2"><a href="math.html#cb1096-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1096-3"><a href="math.html#cb1096-3"></a></span>
<span id="cb1096-4"><a href="math.html#cb1096-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1096-5"><a href="math.html#cb1096-5"></a><span class="op">{</span></span>
<span id="cb1096-6"><a href="math.html#cb1096-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> nan<span class="op">(</span><span class="st">""</span><span class="op">));</span>       <span class="co">// nan</span></span>
<span id="cb1096-7"><a href="math.html#cb1096-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> nan<span class="op">(</span><span class="st">"goats"</span><span class="op">));</span>  <span class="co">// nan</span></span>
<span id="cb1096-8"><a href="math.html#cb1096-8"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> nan<span class="op">(</span><span class="st">"!"</span><span class="op">));</span>      <span class="co">// nan</span></span>
<span id="cb1096-9"><a href="math.html#cb1096-9"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-99">See Also</h3>
<p><a href="stdlib.html#man-strtod"><code>strtod()</code></a></p>
<hr>
<h2 data-number="52.56" id="man-nextafter"><span class="header-section-number">52.56</span> <code>nextafter()</code>,
<code>nextafterf()</code>, <code>nextafterl()</code></h2>
<p>Get the next (or previous) representable floating point value.</p>
<h3 class="unnumbered unlisted" id="synopsis-104">Synopsis</h3>
<div class="sourceCode" id="cb1097"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1097-1"><a href="math.html#cb1097-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1097-2"><a href="math.html#cb1097-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1097-3"><a href="math.html#cb1097-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> nextafter<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1097-4"><a href="math.html#cb1097-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1097-5"><a href="math.html#cb1097-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> nextafterf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1097-6"><a href="math.html#cb1097-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1097-7"><a href="math.html#cb1097-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> nextafterl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-104">Description</h3>
<p>As you probably know, floating point numbers can’t represent
<em>every</em> possible real number. There are limits.</p>
<p>And, as such, there exists a “next” and “previous” number after or
before any floating point number.</p>
<p>These functions return the next (or previous) representable number.
That is, no floating point numbers exist between the given number and
the next one.</p>
<p>The way it figures it out is it works from <code>x</code> in the
direction of <code>y</code>, answering the question of “what is the next
representable number from <code>x</code> as we head toward
<code>y</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-103">Return Value</h3>
<p>Returns the next representable floating point value from
<code>x</code> in the direction of <code>y</code>.</p>
<p>If <code>x</code> equals <code>y</code>, returns <code>y</code>. And
also <code>x</code>, I suppose.</p>
<h3 class="unnumbered unlisted" id="example-104">Example</h3>
<div class="sourceCode" id="cb1098"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1098-1"><a href="math.html#cb1098-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1098-2"><a href="math.html#cb1098-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1098-3"><a href="math.html#cb1098-3"></a></span>
<span id="cb1098-4"><a href="math.html#cb1098-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1098-5"><a href="math.html#cb1098-5"></a><span class="op">{</span></span>
<span id="cb1098-6"><a href="math.html#cb1098-6"></a>    printf<span class="op">(</span><span class="st">"%.*f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> nextafter<span class="op">(</span><span class="fl">0.5</span><span class="op">,</span> <span class="fl">1.0</span><span class="op">));</span></span>
<span id="cb1098-7"><a href="math.html#cb1098-7"></a>    printf<span class="op">(</span><span class="st">"%.*f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> nextafter<span class="op">(</span><span class="fl">0.349</span><span class="op">,</span> <span class="fl">0.0</span><span class="op">));</span></span>
<span id="cb1098-8"><a href="math.html#cb1098-8"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1099"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1099-1"><a href="math.html#cb1099-1" aria-hidden="true" tabindex="-1"></a>0.50000000000000011</span>
<span id="cb1099-2"><a href="math.html#cb1099-2" aria-hidden="true" tabindex="-1"></a>0.34899999999999992</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-100">See Also</h3>
<p><a href="math.html#man-nexttoward"><code>nexttoward()</code></a></p>
<hr>
<h2 data-number="52.57" id="man-nexttoward"><span class="header-section-number">52.57</span> <code>nexttoward()</code>,
<code>nexttowardf()</code>, <code>nexttowardl()</code></h2>
<p>Get the next (or previous) representable floating point value.</p>
<h3 class="unnumbered unlisted" id="synopsis-105">Synopsis</h3>
<div class="sourceCode" id="cb1100"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1100-1"><a href="math.html#cb1100-1" aria-hidden="true" tabindex="-1"></a>include <span class="op">&lt;</span>math<span class="op">.</span>h<span class="op">&gt;</span></span>
<span id="cb1100-2"><a href="math.html#cb1100-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1100-3"><a href="math.html#cb1100-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> nexttoward<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1100-4"><a href="math.html#cb1100-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1100-5"><a href="math.html#cb1100-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> nexttowardf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1100-6"><a href="math.html#cb1100-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1100-7"><a href="math.html#cb1100-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> nexttowardl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-105">Description</h3>
<p>These functions are the same as <a href="#man-nextafter"><code>nextafter()</code></a> except the second
parameter is always <code>long double</code>.</p>
<h3 class="unnumbered unlisted" id="return-value-104">Return Value</h3>
<p>Returns the same as <a href="#man-nextafter"><code>nextafter()</code></a> except if
<code>x</code> equals <code>y</code>, returns <code>y</code> cast to the
function’s return type.</p>
<h3 class="unnumbered unlisted" id="example-105">Example</h3>
<div class="sourceCode" id="cb1101"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1101-1"><a href="math.html#cb1101-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1101-2"><a href="math.html#cb1101-2"></a><span class="pp">#include </span><span class="im">&lt;float.h&gt;</span></span>
<span id="cb1101-3"><a href="math.html#cb1101-3"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1101-4"><a href="math.html#cb1101-4"></a></span>
<span id="cb1101-5"><a href="math.html#cb1101-5"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1101-6"><a href="math.html#cb1101-6"></a><span class="op">{</span></span>
<span id="cb1101-7"><a href="math.html#cb1101-7"></a>    printf<span class="op">(</span><span class="st">"%.*f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> nexttoward<span class="op">(</span><span class="fl">0.5</span><span class="op">,</span> <span class="fl">1.0</span><span class="op">));</span></span>
<span id="cb1101-8"><a href="math.html#cb1101-8"></a>    printf<span class="op">(</span><span class="st">"%.*f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> nexttoward<span class="op">(</span><span class="fl">0.349</span><span class="op">,</span> <span class="fl">0.0</span><span class="op">));</span></span>
<span id="cb1101-9"><a href="math.html#cb1101-9"></a><span class="op">}</span></span></code></pre></div>
<p>Output on my system:</p>
<div class="sourceCode" id="cb1102"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb1102-1"><a href="math.html#cb1102-1" aria-hidden="true" tabindex="-1"></a>0.50000000000000011</span>
<span id="cb1102-2"><a href="math.html#cb1102-2" aria-hidden="true" tabindex="-1"></a>0.34899999999999992</span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-101">See Also</h3>
<p><a href="math.html#man-nextafter"><code>nextafter()</code></a></p>
<hr>
<h2 data-number="52.58" id="man-fdim"><span class="header-section-number">52.58</span> <code>fdim()</code>,
<code>fdimf()</code>, <code>fdiml()</code></h2>
<p>Return the positive difference between two numbers clamped at 0.</p>
<h3 class="unnumbered unlisted" id="synopsis-106">Synopsis</h3>
<div class="sourceCode" id="cb1103"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1103-1"><a href="math.html#cb1103-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1103-2"><a href="math.html#cb1103-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1103-3"><a href="math.html#cb1103-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> fdim<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1103-4"><a href="math.html#cb1103-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1103-5"><a href="math.html#cb1103-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> fdimf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1103-6"><a href="math.html#cb1103-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1103-7"><a href="math.html#cb1103-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> fdiml<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-106">Description</h3>
<p>The positive difference between <code>x</code> and <code>y</code> is
the difference… except if the difference is less than <code>0</code>,
it’s clamped to <code>0</code>.</p>
<p>These functions might throw a range error.</p>
<h3 class="unnumbered unlisted" id="return-value-105">Return Value</h3>
<p>Returns the difference of <code>x-y</code> if the difference is
greater than <code>0</code>. Otherwise it returns <code>0</code>.</p>
<h3 class="unnumbered unlisted" id="example-106">Example</h3>
<div class="sourceCode" id="cb1104"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1104-1"><a href="math.html#cb1104-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1104-2"><a href="math.html#cb1104-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1104-3"><a href="math.html#cb1104-3"></a></span>
<span id="cb1104-4"><a href="math.html#cb1104-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1104-5"><a href="math.html#cb1104-5"></a><span class="op">{</span></span>
<span id="cb1104-6"><a href="math.html#cb1104-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fdim<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">3.0</span><span class="op">));</span>   <span class="co">// 7.000000</span></span>
<span id="cb1104-7"><a href="math.html#cb1104-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fdim<span class="op">(</span><span class="fl">3.0</span><span class="op">,</span> <span class="fl">10.0</span><span class="op">));</span>   <span class="co">// 0.000000, clamped</span></span>
<span id="cb1104-8"><a href="math.html#cb1104-8"></a><span class="op">}</span></span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="52.59" id="man-fmax"><span class="header-section-number">52.59</span> <code>fmax()</code>,
<code>fmaxf()</code>, <code>fmaxl()</code>, <code>fmin()</code>,
<code>fminf()</code>, <code>fminl()</code></h2>
<p>Return the maximum or minimum of two numbers.</p>
<h3 class="unnumbered unlisted" id="synopsis-107">Synopsis</h3>
<div class="sourceCode" id="cb1105"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1105-1"><a href="math.html#cb1105-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1105-2"><a href="math.html#cb1105-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1105-3"><a href="math.html#cb1105-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> fmax<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1105-4"><a href="math.html#cb1105-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1105-5"><a href="math.html#cb1105-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> fmaxf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1105-6"><a href="math.html#cb1105-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1105-7"><a href="math.html#cb1105-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> fmaxl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1105-8"><a href="math.html#cb1105-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1105-9"><a href="math.html#cb1105-9" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> fmin<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">);</span></span>
<span id="cb1105-10"><a href="math.html#cb1105-10" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1105-11"><a href="math.html#cb1105-11" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> fminf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">);</span></span>
<span id="cb1105-12"><a href="math.html#cb1105-12" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1105-13"><a href="math.html#cb1105-13" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> fminl<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-107">Description</h3>
<p>Straightforwardly, these functions return the minimum or maximum of
two given numbers.</p>
<p>If one of the numbers is NaN, the functions return the non-NaN
number. If both arguments are NaN, the functions return NaN.</p>
<h3 class="unnumbered unlisted" id="return-value-106">Return Value</h3>
<p>Returns the minimum or maximum values, with NaN handled as mentioned
above.</p>
<h3 class="unnumbered unlisted" id="example-107">Example</h3>
<div class="sourceCode" id="cb1106"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1106-1"><a href="math.html#cb1106-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1106-2"><a href="math.html#cb1106-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1106-3"><a href="math.html#cb1106-3"></a></span>
<span id="cb1106-4"><a href="math.html#cb1106-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1106-5"><a href="math.html#cb1106-5"></a><span class="op">{</span></span>
<span id="cb1106-6"><a href="math.html#cb1106-6"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fmin<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">3.0</span><span class="op">));</span>   <span class="co">//  3.000000</span></span>
<span id="cb1106-7"><a href="math.html#cb1106-7"></a>    printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fmax<span class="op">(</span><span class="fl">3.0</span><span class="op">,</span> <span class="fl">10.0</span><span class="op">));</span>   <span class="co">// 10.000000</span></span>
<span id="cb1106-8"><a href="math.html#cb1106-8"></a><span class="op">}</span></span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="52.60" id="man-fma"><span class="header-section-number">52.60</span> <code>fma()</code>,
<code>fmaf()</code>, <code>fmal()</code></h2>
<p>Floating (AKA “Fast”) multiply and add.</p>
<h3 class="unnumbered unlisted" id="synopsis-108">Synopsis</h3>
<div class="sourceCode" id="cb1107"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1107-1"><a href="math.html#cb1107-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1107-2"><a href="math.html#cb1107-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1107-3"><a href="math.html#cb1107-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> fma<span class="op">(</span><span class="dt">double</span> x<span class="op">,</span> <span class="dt">double</span> y<span class="op">,</span> <span class="dt">double</span> z<span class="op">);</span></span>
<span id="cb1107-4"><a href="math.html#cb1107-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1107-5"><a href="math.html#cb1107-5" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> fmaf<span class="op">(</span><span class="dt">float</span> x<span class="op">,</span> <span class="dt">float</span> y<span class="op">,</span> <span class="dt">float</span> z<span class="op">);</span></span>
<span id="cb1107-6"><a href="math.html#cb1107-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1107-7"><a href="math.html#cb1107-7" aria-hidden="true" tabindex="-1"></a><span class="dt">long</span> <span class="dt">double</span> fmal<span class="op">(</span><span class="dt">long</span> <span class="dt">double</span> x<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> y<span class="op">,</span> <span class="dt">long</span> <span class="dt">double</span> z<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-108">Description</h3>
<p>This performs the operation <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="107" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-texatom space="3" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D467 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">(</mo><mi>x</mi><mo>×</mo><mrow data-mjx-texclass="ORD"><mi>y</mi></mrow><mo stretchy="false">)</mo><mo>+</mo><mi>z</mi></math></mjx-assistive-mml></mjx-container></span>, but does so in a nifty
way. It does the computation as if it had infinite precision, and then
rounds the final result to the final data type according to the current
rounding mode.</p>
<p>Contrast to if you’d do the math yourself, where it would have
rounded each step of the way, potentially.</p>
<p>Also some architectures have a CPU instruction to do exactly this
calculation, so it can do it super quick. (If it doesn’t, it’s
considerably slower.)</p>
<p>You can tell if your CPU supports the fast version by checking that
the macro <code>FP_FAST_FMA</code> is set to <code>1</code>. (The
<code>float</code> and <code>long</code> variants of <code>fma()</code>
can be tested with <code>FP_FAST_FMAF</code> and
<code>FP_FAST_FMAL</code>, respectively.)</p>
<p>These functions might cause a range error to occur.</p>
<h3 class="unnumbered unlisted" id="return-value-107">Return Value</h3>
<p>Returns <code>(x * y) + z</code>.</p>
<h3 class="unnumbered unlisted" id="example-108">Example</h3>
<div class="sourceCode" id="cb1108"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1108-1"><a href="math.html#cb1108-1"></a>printf<span class="op">(</span><span class="st">"%f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> fma<span class="op">(</span><span class="fl">1.0</span><span class="op">,</span> <span class="fl">2.0</span><span class="op">,</span> <span class="fl">3.0</span><span class="op">));</span>  <span class="co">// 5.000000</span></span></code></pre></div>
<!--
### See Also {.unnumbered .unlisted}

[`example()`](#man-example),
-->
<hr>
<h2 data-number="52.61" id="man-isgreater"><span class="header-section-number">52.61</span> <code>isgreater()</code>,
<code>isgreaterequal()</code>, <code>isless()</code>,
<code>islessequal()</code></h2>
<p>Floating point comparison macros.</p>
<h3 class="unnumbered unlisted" id="synopsis-109">Synopsis</h3>
<div class="sourceCode" id="cb1109"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1109-1"><a href="math.html#cb1109-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1109-2"><a href="math.html#cb1109-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1109-3"><a href="math.html#cb1109-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isgreater<span class="op">(</span>any_floating_type x<span class="op">,</span> any_floating_type y<span class="op">);</span></span>
<span id="cb1109-4"><a href="math.html#cb1109-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1109-5"><a href="math.html#cb1109-5" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isgreaterequal<span class="op">(</span>any_floating_type x<span class="op">,</span> any_floating_type y<span class="op">);</span></span>
<span id="cb1109-6"><a href="math.html#cb1109-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1109-7"><a href="math.html#cb1109-7" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isless<span class="op">(</span>any_floating_type x<span class="op">,</span> any_floating_type y<span class="op">);</span></span>
<span id="cb1109-8"><a href="math.html#cb1109-8" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1109-9"><a href="math.html#cb1109-9" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> islessequal<span class="op">(</span>any_floating_type x<span class="op">,</span> any_floating_type y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-109">Description</h3>
<p>These macros compare floating point numbers. Being macros, we can
pass in any floating point type.</p>
<p>You might think you can already do that with just regular comparison
operators—and you’d be right!</p>
<p>One one exception: the comparison operators raise the “invalid”
floating exception if one or more of the operands is NaN. These macros
do not.</p>
<p>Note that you must only pass floating point types into these
functions. Passing an integer or any other type is undefined
behavior.</p>
<h3 class="unnumbered unlisted" id="return-value-108">Return Value</h3>
<p><code>isgreater()</code> returns the result of
<code>x &gt; y</code>.</p>
<p><code>isgreaterequal()</code> returns the result of
<code>x &gt;= y</code>.</p>
<p><code>isless()</code> returns the result of
<code>x &lt; y</code>.</p>
<p><code>islessequal()</code> returns the result of
<code>x &lt;= y</code>.</p>
<h3 class="unnumbered unlisted" id="example-109">Example</h3>
<div class="sourceCode" id="cb1110"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1110-1"><a href="math.html#cb1110-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1110-2"><a href="math.html#cb1110-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1110-3"><a href="math.html#cb1110-3"></a></span>
<span id="cb1110-4"><a href="math.html#cb1110-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1110-5"><a href="math.html#cb1110-5"></a><span class="op">{</span></span>
<span id="cb1110-6"><a href="math.html#cb1110-6"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgreater<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">3.0</span><span class="op">));</span>        <span class="co">// 1</span></span>
<span id="cb1110-7"><a href="math.html#cb1110-7"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isgreaterequal<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">10.0</span><span class="op">));</span>  <span class="co">// 1</span></span>
<span id="cb1110-8"><a href="math.html#cb1110-8"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isless<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">3.0</span><span class="op">));</span>           <span class="co">// 0</span></span>
<span id="cb1110-9"><a href="math.html#cb1110-9"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islessequal<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">3.0</span><span class="op">));</span>      <span class="co">// 0</span></span>
<span id="cb1110-10"><a href="math.html#cb1110-10"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-102">See Also</h3>
<p><a href="math.html#man-islessgreater"><code>islessgreater()</code></a>, <a href="#man-isunordered"><code>isunordered()</code></a></p>
<hr>
<h2 data-number="52.62" id="man-islessgreater"><span class="header-section-number">52.62</span>
<code>islessgreater()</code></h2>
<p>Test if a floating point number is less than or greater than
another.</p>
<h3 class="unnumbered unlisted" id="synopsis-110">Synopsis</h3>
<div class="sourceCode" id="cb1111"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1111-1"><a href="math.html#cb1111-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1111-2"><a href="math.html#cb1111-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1111-3"><a href="math.html#cb1111-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> islessgreater<span class="op">(</span>any_floating_type x<span class="op">,</span> any_floating_type y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-110">Description</h3>
<p>This macro is similar to <code>isgreater()</code> and all those,
except it made the section name too long if I included it up there. So
it gets its own spot.</p>
<p>This returns true if <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="108" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>&lt;</mo><mi>y</mi></math></mjx-assistive-mml></mjx-container></span> or
<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="109" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3E"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D466 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>&gt;</mo><mi>y</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>Even though it’s a macro, we can rest assured that <code>x</code> and
<code>y</code> are only evaluated once.</p>
<p>And even if <code>x</code> or <code>y</code> are NaN, this will not
throw an “invalid” exception, unlike the normal comparison
operators.</p>
<p>If you pass in a non-floating type, the behavior is undefined.</p>
<h3 class="unnumbered unlisted" id="return-value-109">Return Value</h3>
<p>Returns <code>(x &lt; y) || (x &gt; y)</code>.</p>
<h3 class="unnumbered unlisted" id="example-110">Example</h3>
<div class="sourceCode" id="cb1112"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1112-1"><a href="math.html#cb1112-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1112-2"><a href="math.html#cb1112-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1112-3"><a href="math.html#cb1112-3"></a></span>
<span id="cb1112-4"><a href="math.html#cb1112-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1112-5"><a href="math.html#cb1112-5"></a><span class="op">{</span></span>
<span id="cb1112-6"><a href="math.html#cb1112-6"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islessgreater<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">3.0</span><span class="op">));</span>   <span class="co">// 1</span></span>
<span id="cb1112-7"><a href="math.html#cb1112-7"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islessgreater<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">30.0</span><span class="op">));</span>  <span class="co">// 1</span></span>
<span id="cb1112-8"><a href="math.html#cb1112-8"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> islessgreater<span class="op">(</span><span class="fl">10.0</span><span class="op">,</span> <span class="fl">10.0</span><span class="op">));</span>  <span class="co">// 0</span></span>
<span id="cb1112-9"><a href="math.html#cb1112-9"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-103">See Also</h3>
<p><a href="math.html#man-isgreater"><code>isgreater()</code></a>, <a href="#man-isgreater"><code>isgreaterequal()</code></a>, <a href="#man-isgreater"><code>isless()</code></a>, <a href="#man-isgreater"><code>islessequal()</code></a>, <a href="#man-isunordered"><code>isunordered()</code></a></p>
<hr>
<h2 data-number="52.63" id="man-isunordered"><span class="header-section-number">52.63</span>
<code>isunordered()</code></h2>
<p>Macro returns true if either floating point argument is NaN.</p>
<h3 class="unnumbered unlisted" id="synopsis-111">Synopsis</h3>
<div class="sourceCode" id="cb1113"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb1113-1"><a href="math.html#cb1113-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1113-2"><a href="math.html#cb1113-2" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1113-3"><a href="math.html#cb1113-3" aria-hidden="true" tabindex="-1"></a><span class="dt">int</span> isunordered<span class="op">(</span>any_floating_type x<span class="op">,</span> any_floating_type y<span class="op">);</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="description-111">Description</h3>
<p>The spec writes:</p>
<blockquote>
<p>The isunordered macro determines whether its arguments are
unordered.</p>
</blockquote>
<p>See? Told you C was easy!</p>
<p>It does also elaborate that the arguments are unordered if one or
both of them are NaN.</p>
<h3 class="unnumbered unlisted" id="return-value-110">Return Value</h3>
<p>This macro returns true if one or both of the arguments are NaN.</p>
<h3 class="unnumbered unlisted" id="example-111">Example</h3>
<div class="sourceCode" id="cb1114"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb1114-1"><a href="math.html#cb1114-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb1114-2"><a href="math.html#cb1114-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb1114-3"><a href="math.html#cb1114-3"></a></span>
<span id="cb1114-4"><a href="math.html#cb1114-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb1114-5"><a href="math.html#cb1114-5"></a><span class="op">{</span></span>
<span id="cb1114-6"><a href="math.html#cb1114-6"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isunordered<span class="op">(</span><span class="fl">1.0</span><span class="op">,</span> <span class="fl">2.0</span><span class="op">));</span>       <span class="co">// 0</span></span>
<span id="cb1114-7"><a href="math.html#cb1114-7"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isunordered<span class="op">(</span><span class="fl">1.0</span><span class="op">,</span> sqrt<span class="op">(-</span><span class="dv">1</span><span class="op">)));</span>  <span class="co">// 1</span></span>
<span id="cb1114-8"><a href="math.html#cb1114-8"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isunordered<span class="op">(</span>NAN<span class="op">,</span> <span class="fl">30.0</span><span class="op">));</span>      <span class="co">// 1</span></span>
<span id="cb1114-9"><a href="math.html#cb1114-9"></a>    printf<span class="op">(</span><span class="st">"%d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> isunordered<span class="op">(</span>NAN<span class="op">,</span> NAN<span class="op">));</span>       <span class="co">// 1</span></span>
<span id="cb1114-10"><a href="math.html#cb1114-10"></a><span class="op">}</span></span></code></pre></div>
<h3 class="unnumbered unlisted" id="see-also-104">See Also</h3>
<p><a href="math.html#man-isgreater"><code>isgreater()</code></a>, <a href="#man-isgreater"><code>isgreaterequal()</code></a>, <a href="#man-isgreater"><code>isless()</code></a>, <a href="#man-isgreater"><code>islessequal()</code></a>, <a href="#man-islessgreater"><code>islessgreater()</code></a></p>

</body>