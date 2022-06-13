<body>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="incomplete-types.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="fixed-width-integer-types.html">Next»</a></div>
<hr>
<h1 data-number="36" id="complex-numbers"><span class="header-section-number">36</span> Complex Numbers</h1>
<p></p>
<p>A tiny primer on <a href="https://en.wikipedia.org/wiki/Complex_number">Complex
numbers</a><a href="footnotes.html#fn172" class="footnote-ref" id="fnref172" role="doc-noteref"><sup>172</sup></a> stolen directly from
Wikipedia:</p>
<blockquote>
<p>A <strong>complex number</strong> is a number that can be expressed
in the form <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>+</mo><mi>b</mi><mi>i</mi></math></mjx-assistive-mml></mjx-container></span>, where <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></mjx-assistive-mml></mjx-container></span> are real numbers [i.e.&nbsp;floating point
types in C], and <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></mjx-assistive-mml></mjx-container></span> represents the
imaginary unit, satisfying the equation <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>i</mi><mn>2</mn></msup><mo>=</mo><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>. Because no real number satisfies
this equation, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></mjx-assistive-mml></mjx-container></span> is called an
imaginary number. For the complex number <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>+</mo><mi>b</mi><mi>i</mi></math></mjx-assistive-mml></mjx-container></span>, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> is called the <strong>real
part</strong>, and <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></mjx-assistive-mml></mjx-container></span> is called the
<strong>imaginary part</strong>.</p>
</blockquote>
<p>But that’s as far as I’m going to go. We’ll assume that if you’re
reading this chapter, you know what a complex number is and what you
want to do with them.</p>
<p>And all we need to cover is C’s faculties for doing so.</p>
<p>Turns out, though, that complex number support in a compiler is an
<em>optional</em> feature. Not all compliant compilers can do it. And
the ones that do, might do it to various degrees of completeness.</p>
<p>You can test if your system supports complex numbers with:</p>
<p></p>
<div class="sourceCode" id="cb673"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb673-1"><a href="complex-numbers.html#cb673-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#ifdef __STDC_NO_COMPLEX__</span></span>
<span id="cb673-2"><a href="complex-numbers.html#cb673-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#error Complex numbers not supported!</span></span>
<span id="cb673-3"><a href="complex-numbers.html#cb673-3" aria-hidden="true" tabindex="-1"></a><span class="pp">#endif</span></span></code></pre></div>
<p></p>
<p></p>
<p>Furthermore, there is a macro that indicates adherence to the ISO
60559 (IEEE 754) standard for floating point math with complex numbers,
as well as the presence of the <code>_Imaginary</code> type.</p>
<div class="sourceCode" id="cb674"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb674-1"><a href="complex-numbers.html#cb674-1" aria-hidden="true" tabindex="-1"></a><span class="pp">#if __STDC_IEC_559_COMPLEX__ != 1</span></span>
<span id="cb674-2"><a href="complex-numbers.html#cb674-2" aria-hidden="true" tabindex="-1"></a><span class="pp">#error Need IEC 60559 complex support!</span></span>
<span id="cb674-3"><a href="complex-numbers.html#cb674-3" aria-hidden="true" tabindex="-1"></a><span class="pp">#endif</span></span></code></pre></div>
<p></p>
<p>More details on that are spelled out in Annex G in the C11 spec.</p>
<h2 data-number="36.1" id="complex-types"><span class="header-section-number">36.1</span> Complex Types</h2>
<p>To use complex numbers, <code>#include &lt;complex.h&gt;</code>.</p>
<p>With that, you get at least two types:</p>
<p> </p>
<div class="sourceCode" id="cb675"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb675-1"><a href="complex-numbers.html#cb675-1" aria-hidden="true" tabindex="-1"></a><span class="dt">_Complex</span></span>
<span id="cb675-2"><a href="complex-numbers.html#cb675-2" aria-hidden="true" tabindex="-1"></a><span class="dt">complex</span></span></code></pre></div>
<p>Those both mean the same thing, so you might as well use the prettier
<code>complex</code>.</p>
<p></p>
<p>You also get some types for imaginary numbers if you implementation
is IEC 60559-compliant:</p>
<p> </p>
<div class="sourceCode" id="cb676"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb676-1"><a href="complex-numbers.html#cb676-1" aria-hidden="true" tabindex="-1"></a><span class="dt">_Imaginary</span></span>
<span id="cb676-2"><a href="complex-numbers.html#cb676-2" aria-hidden="true" tabindex="-1"></a><span class="dt">imaginary</span></span></code></pre></div>
<p>These also both mean the same thing, so you might as well use the
prettier <code>imaginary</code>.</p>
<p></p>
<p>You also get values for the imaginary number <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></mjx-assistive-mml></mjx-container></span>, itself:</p>
<p> </p>
<div class="sourceCode" id="cb677"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb677-1"><a href="complex-numbers.html#cb677-1" aria-hidden="true" tabindex="-1"></a>I</span>
<span id="cb677-2"><a href="complex-numbers.html#cb677-2" aria-hidden="true" tabindex="-1"></a>_Complex_I</span>
<span id="cb677-3"><a href="complex-numbers.html#cb677-3" aria-hidden="true" tabindex="-1"></a>_Imaginary_I</span></code></pre></div>
<p>The macro <code>I</code> is set to <code>_Imaginary_I</code> (if
available), or <code>_Complex_I</code>. So just use <code>I</code> for
the imaginary number.</p>
<p> </p>
<p></p>
<p>One aside: I’ve said that if a compiler has
<code>__STDC_IEC_559_COMPLEX__</code> set to <code>1</code>, it must
support <code>_Imaginary</code> types to be compliant. That’s my read of
the spec. However, I don’t know of a single compiler that actually
supports <code>_Imaginary</code> even though they have
<code>__STDC_IEC_559_COMPLEX__</code> set. So I’m going to write some
code with that type in here I have no way of testing. Sorry!</p>
<p> </p>
<p>OK, so now we know there’s a <code>complex</code> type, how can we
use it?</p>
<h2 data-number="36.2" id="assigning-complex-numbers"><span class="header-section-number">36.2</span> Assigning Complex Numbers</h2>
<p></p>
<p>Since the complex number has a real and imaginary part, but both of
them rely on floating point numbers to store values, we need to also
tell C what precision to use for those parts of the complex number.</p>
<p> </p>
<p>We do that by just pinning a <code>float</code>, <code>double</code>,
or <code>long double</code> to the <code>complex</code>, either before
or after it.</p>
<p></p>
<p>Let’s define a complex number that uses <code>float</code> for its
components:</p>
<div class="sourceCode" id="cb678"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb678-1"><a href="complex-numbers.html#cb678-1" aria-hidden="true" tabindex="-1"></a><span class="dt">float</span> <span class="dt">complex</span> c<span class="op">;</span>   <span class="co">// Spec prefers this way</span></span>
<span id="cb678-2"><a href="complex-numbers.html#cb678-2" aria-hidden="true" tabindex="-1"></a><span class="dt">complex</span> <span class="dt">float</span> c<span class="op">;</span>   <span class="co">// Same thing--order doesn't matter</span></span></code></pre></div>
<p>So that’s great for declarations, but how do we initialize them or
assign to them?</p>
<p>Turns out we get to use some pretty natural notation. Example!</p>
<p></p>
<div class="sourceCode" id="cb679"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb679-1"><a href="complex-numbers.html#cb679-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">2</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb679-2"><a href="complex-numbers.html#cb679-2" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> <span class="dv">10</span> <span class="op">+</span> <span class="dv">3</span><span class="op">*</span>I<span class="op">;</span></span></code></pre></div>
<p></p>
<p>For <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c35"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>5</mn><mo>+</mo><mn>2</mn><mi>i</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>10</mn><mo>+</mo><mn>3</mn><mi>i</mi></math></mjx-assistive-mml></mjx-container></span>, respectively.</p>
<p> </p>
<h2 data-number="36.3" id="constructing-deconstructing-and-printing"><span class="header-section-number">36.3</span> Constructing, Deconstructing,
and Printing</h2>
<p>We’re getting there…</p>
<p>We’ve already seen one way to write a complex number:</p>
<div class="sourceCode" id="cb680"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb680-1"><a href="complex-numbers.html#cb680-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">2</span><span class="op">*</span>I<span class="op">;</span></span></code></pre></div>
<p>There’s also no problem using other floating point numbers to build
it:</p>
<div class="sourceCode" id="cb681"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb681-1"><a href="complex-numbers.html#cb681-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> a <span class="op">=</span> <span class="dv">5</span><span class="op">;</span></span>
<span id="cb681-2"><a href="complex-numbers.html#cb681-2" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> b <span class="op">=</span> <span class="dv">2</span><span class="op">;</span></span>
<span id="cb681-3"><a href="complex-numbers.html#cb681-3" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> a <span class="op">+</span> b<span class="op">*</span>I<span class="op">;</span></span></code></pre></div>
<p></p>
<p>There is also a set of macros to help build these. The above code
could be written using the <code>CMPLX()</code> macro, like so:</p>
<div class="sourceCode" id="cb682"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb682-1"><a href="complex-numbers.html#cb682-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> CMPLX<span class="op">(</span><span class="dv">5</span><span class="op">,</span> <span class="dv">2</span><span class="op">);</span></span></code></pre></div>
<p>As far as I can tell in my research, these are <em>almost</em>
equivalent:</p>
<div class="sourceCode" id="cb683"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb683-1"><a href="complex-numbers.html#cb683-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">2</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb683-2"><a href="complex-numbers.html#cb683-2" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> CMPLX<span class="op">(</span><span class="dv">5</span><span class="op">,</span> <span class="dv">2</span><span class="op">);</span></span></code></pre></div>
<p>But the <code>CMPLX()</code> macro will handle negative zeros in the
imaginary part correctly every time, whereas the other way might convert
them to positive zeros. I <em>think</em><a href="footnotes.html#fn173" class="footnote-ref" id="fnref173" role="doc-noteref"><sup>173</sup></a>
This seems to imply that if there’s a chance the imaginary part will be
zero, you should use the macro… but someone should correct me on this if
I’m mistaken!</p>
<p>The <code>CMPLX()</code> macro works on <code>double</code> types.
There are two other macros for <code>float</code> and
<code>long double</code>: <code>CMPLXF()</code> and
<code>CMPLXL()</code>. (These “f” and “l” suffixes appear in virtually
all the complex-number-related functions.)</p>
<p></p>
<p>Now let’s try the reverse: if we have a complex number, how do we
break it apart into its real and imaginary parts?</p>
<p> </p>
<p>Here we have a couple functions that will extract the real and
imaginary parts from the number: <code>creal()</code> and
<code>cimag()</code>:</p>
<div class="sourceCode" id="cb684"><pre class="sourceCode c"><code class="sourceCode c"><span id="cb684-1"><a href="complex-numbers.html#cb684-1" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">5</span> <span class="op">+</span> <span class="dv">2</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb684-2"><a href="complex-numbers.html#cb684-2" aria-hidden="true" tabindex="-1"></a><span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> <span class="dv">10</span> <span class="op">+</span> <span class="dv">3</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb684-3"><a href="complex-numbers.html#cb684-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb684-4"><a href="complex-numbers.html#cb684-4" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"x = %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>x<span class="op">),</span> cimag<span class="op">(</span>x<span class="op">));</span></span>
<span id="cb684-5"><a href="complex-numbers.html#cb684-5" aria-hidden="true" tabindex="-1"></a>printf<span class="op">(</span><span class="st">"y = %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>y<span class="op">),</span> cimag<span class="op">(</span>y<span class="op">));</span></span></code></pre></div>
<p>for the output:</p>
<div class="sourceCode" id="cb685"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb685-1"><a href="complex-numbers.html#cb685-1" aria-hidden="true" tabindex="-1"></a>x = 5.000000 + 2.000000i</span>
<span id="cb685-2"><a href="complex-numbers.html#cb685-2" aria-hidden="true" tabindex="-1"></a>y = 10.000000 + 3.000000i</span></code></pre></div>
<p>Note that the <code>i</code> I have in the <code>printf()</code>
format string is a literal <code>i</code> that gets printed—it’s not
part of the format specifier. Both return values from
<code>creal()</code> and <code>cimag()</code> are
<code>double</code>.</p>
<p>And as usual, there are <code>float</code> and
<code>long double</code> variants of these functions:
<code>crealf()</code>, <code>cimagf()</code>, <code>creall()</code>, and
<code>cimagl()</code>.</p>
<p> </p>
<h2 data-number="36.4" id="complex-arithmetic-and-comparisons"><span class="header-section-number">36.4</span> Complex Arithmetic and
Comparisons</h2>
<p></p>
<p>Arithmetic can be performed on complex numbers, though how this works
mathematically is beyond the scope of the guide.</p>
<div class="sourceCode" id="cb686"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb686-1"><a href="complex-numbers.html#cb686-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb686-2"><a href="complex-numbers.html#cb686-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb686-3"><a href="complex-numbers.html#cb686-3"></a></span>
<span id="cb686-4"><a href="complex-numbers.html#cb686-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb686-5"><a href="complex-numbers.html#cb686-5"></a><span class="op">{</span></span>
<span id="cb686-6"><a href="complex-numbers.html#cb686-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb686-7"><a href="complex-numbers.html#cb686-7"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> <span class="dv">3</span> <span class="op">+</span> <span class="dv">4</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb686-8"><a href="complex-numbers.html#cb686-8"></a>    <span class="dt">double</span> <span class="dt">complex</span> z<span class="op">;</span></span>
<span id="cb686-9"><a href="complex-numbers.html#cb686-9"></a></span>
<span id="cb686-10"><a href="complex-numbers.html#cb686-10"></a>    z <span class="op">=</span> x <span class="op">+</span> y<span class="op">;</span></span>
<span id="cb686-11"><a href="complex-numbers.html#cb686-11"></a>    printf<span class="op">(</span><span class="st">"x + y = %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>z<span class="op">),</span> cimag<span class="op">(</span>z<span class="op">));</span></span>
<span id="cb686-12"><a href="complex-numbers.html#cb686-12"></a></span>
<span id="cb686-13"><a href="complex-numbers.html#cb686-13"></a>    z <span class="op">=</span> x <span class="op">-</span> y<span class="op">;</span></span>
<span id="cb686-14"><a href="complex-numbers.html#cb686-14"></a>    printf<span class="op">(</span><span class="st">"x - y = %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>z<span class="op">),</span> cimag<span class="op">(</span>z<span class="op">));</span></span>
<span id="cb686-15"><a href="complex-numbers.html#cb686-15"></a></span>
<span id="cb686-16"><a href="complex-numbers.html#cb686-16"></a>    z <span class="op">=</span> x <span class="op">*</span> y<span class="op">;</span></span>
<span id="cb686-17"><a href="complex-numbers.html#cb686-17"></a>    printf<span class="op">(</span><span class="st">"x * y = %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>z<span class="op">),</span> cimag<span class="op">(</span>z<span class="op">));</span></span>
<span id="cb686-18"><a href="complex-numbers.html#cb686-18"></a></span>
<span id="cb686-19"><a href="complex-numbers.html#cb686-19"></a>    z <span class="op">=</span> x <span class="op">/</span> y<span class="op">;</span></span>
<span id="cb686-20"><a href="complex-numbers.html#cb686-20"></a>    printf<span class="op">(</span><span class="st">"x / y = %f + %fi</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> creal<span class="op">(</span>z<span class="op">),</span> cimag<span class="op">(</span>z<span class="op">));</span></span>
<span id="cb686-21"><a href="complex-numbers.html#cb686-21"></a><span class="op">}</span></span></code></pre></div>
<p>for a result of:</p>
<div class="sourceCode" id="cb687"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb687-1"><a href="complex-numbers.html#cb687-1" aria-hidden="true" tabindex="-1"></a>x + y = 4.000000 + 6.000000i</span>
<span id="cb687-2"><a href="complex-numbers.html#cb687-2" aria-hidden="true" tabindex="-1"></a>x - y = -2.000000 + -2.000000i</span>
<span id="cb687-3"><a href="complex-numbers.html#cb687-3" aria-hidden="true" tabindex="-1"></a>x * y = -5.000000 + 10.000000i</span>
<span id="cb687-4"><a href="complex-numbers.html#cb687-4" aria-hidden="true" tabindex="-1"></a>x / y = 0.440000 + 0.080000i</span></code></pre></div>
<p>You can also compare two complex numbers for equality (or
inequality):</p>
<div class="sourceCode" id="cb688"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb688-1"><a href="complex-numbers.html#cb688-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb688-2"><a href="complex-numbers.html#cb688-2"></a><span class="pp">#include </span><span class="im">&lt;complex.h&gt;</span></span>
<span id="cb688-3"><a href="complex-numbers.html#cb688-3"></a></span>
<span id="cb688-4"><a href="complex-numbers.html#cb688-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb688-5"><a href="complex-numbers.html#cb688-5"></a><span class="op">{</span></span>
<span id="cb688-6"><a href="complex-numbers.html#cb688-6"></a>    <span class="dt">double</span> <span class="dt">complex</span> x <span class="op">=</span> <span class="dv">1</span> <span class="op">+</span> <span class="dv">2</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb688-7"><a href="complex-numbers.html#cb688-7"></a>    <span class="dt">double</span> <span class="dt">complex</span> y <span class="op">=</span> <span class="dv">3</span> <span class="op">+</span> <span class="dv">4</span><span class="op">*</span>I<span class="op">;</span></span>
<span id="cb688-8"><a href="complex-numbers.html#cb688-8"></a></span>
<span id="cb688-9"><a href="complex-numbers.html#cb688-9"></a>    printf<span class="op">(</span><span class="st">"x == y = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x <span class="op">==</span> y<span class="op">);</span>  <span class="co">// 0</span></span>
<span id="cb688-10"><a href="complex-numbers.html#cb688-10"></a>    printf<span class="op">(</span><span class="st">"x != y = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> x <span class="op">!=</span> y<span class="op">);</span>  <span class="co">// 1</span></span>
<span id="cb688-11"><a href="complex-numbers.html#cb688-11"></a><span class="op">}</span></span></code></pre></div>
<p>with the output:</p>
<div class="sourceCode" id="cb689"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb689-1"><a href="complex-numbers.html#cb689-1" aria-hidden="true" tabindex="-1"></a>x == y = 0</span>
<span id="cb689-2"><a href="complex-numbers.html#cb689-2" aria-hidden="true" tabindex="-1"></a>x != y = 1</span></code></pre></div>
<p>They are equal if both components test equal. Note that as with all
floating point, they could be equal if they’re close enough due to
rounding error<a href="footnotes.html#fn174" class="footnote-ref" id="fnref174" role="doc-noteref"><sup>174</sup></a>.</p>
<p></p>
<h2 data-number="36.5" id="complex-math"><span class="header-section-number">36.5</span> Complex Math</h2>
<p>But wait! There’s more than just simple complex arithmetic!</p>
<p>Here’s a summary table of all the math functions available to you
with complex numbers.</p>
<p>I’m only going to list the <code>double</code> version of each
function, but for all of them there is a <code>float</code> version that
you can get by appending <code>f</code> to the function name, and a
<code>long double</code> version that you can get by appending
<code>l</code>.</p>
<p>For example, the <code>cabs()</code> function for computing the
absolute value of a complex number also has <code>cabsf()</code> and
<code>cabsl()</code> variants. I’m omitting them for brevity.</p>
<h3 data-number="36.5.1" id="trigonometry-functions"><span class="header-section-number">36.5.1</span> Trigonometry Functions</h3>
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
<td><code>ccos()</code></td>
<td>Cosine</td>
</tr>
<tr class="even">
<td><code>csin()</code></td>
<td>Sine</td>
</tr>
<tr class="odd">
<td><code>ctan()</code></td>
<td>Tangent</td>
</tr>
<tr class="even">
<td><code>cacos()</code></td>
<td>Arc cosine</td>
</tr>
<tr class="odd">
<td><code>casin()</code></td>
<td>Arc sine</td>
</tr>
<tr class="even">
<td><code>catan()</code></td>
<td>Play <em>Settlers of Catan</em></td>
</tr>
<tr class="odd">
<td><code>ccosh()</code></td>
<td>Hyperbolic cosine</td>
</tr>
<tr class="even">
<td><code>csinh()</code></td>
<td>Hyperbolic sine</td>
</tr>
<tr class="odd">
<td><code>ctanh()</code></td>
<td>Hyperbolic tangent</td>
</tr>
<tr class="even">
<td><code>cacosh()</code></td>
<td>Arc hyperbolic cosine</td>
</tr>
<tr class="odd">
<td><code>casinh()</code></td>
<td>Arc hyperbolic sine</td>
</tr>
<tr class="even">
<td><code>catanh()</code></td>
<td>Arc hyperbolic tangent</td>
</tr>
</tbody>
</table>
<h3 data-number="36.5.2" id="exponential-and-logarithmic-functions"><span class="header-section-number">36.5.2</span> Exponential and Logarithmic
Functions</h3>
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
<td><code>cexp()</code></td>
<td>Base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="12" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span> exponential</td>
</tr>
<tr class="even">
<td><code>clog()</code></td>
<td>Natural (base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="13" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span>) logarithm</td>
</tr>
</tbody>
</table>
<h3 data-number="36.5.3" id="power-and-absolute-value-functions"><span class="header-section-number">36.5.3</span> Power and Absolute Value
Functions</h3>
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
<td><code>cabs()</code></td>
<td>Absolute value</td>
</tr>
<tr class="even">
<td><code>cpow()</code></td>
<td>Power</td>
</tr>
<tr class="odd">
<td><code>csqrt()</code></td>
<td>Square root</td>
</tr>
</tbody>
</table>
<h3 data-number="36.5.4" id="manipulation-functions"><span class="header-section-number">36.5.4</span> Manipulation Functions</h3>
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
<td><code>creal()</code></td>
<td>Return real part</td>
</tr>
<tr class="even">
<td><code>cimag()</code></td>
<td>Return imaginary part</td>
</tr>
<tr class="odd">
<td><code>CMPLX()</code></td>
<td>Construct a complex number</td>
</tr>
<tr class="even">
<td><code>carg()</code></td>
<td>Argument/phase angle</td>
</tr>
<tr class="odd">
<td><code>conj()</code></td>
<td>Conjugate<a href="footnotes.html#fn175" class="footnote-ref" id="fnref175" role="doc-noteref"><sup>175</sup></a></td>
</tr>
<tr class="even">
<td><code>cproj()</code></td>
<td>Projection on Riemann sphere</td>
</tr>
</tbody>
</table>
<p></p>
<!-- Beej's guide to C

# vim: ts=4:sw=4:nosi:et:tw=72
-->
<hr>
<div class="bg-nav-outer"><a class="bg-nav-prev" href="incomplete-types.html">«Previous</a>&nbsp;|&nbsp;<a class="bg-nav-home" href="index.html">Contents</a>&nbsp;|&nbsp;<a class="bg-nav-next" href="fixed-width-integer-types.html">Next»</a></div>

</body>