<body>

<hr>
<h1 data-number="47" id="float"><span class="header-section-number">47</span> <code>&lt;float.h&gt;</code>
Floating Point Limits</h1>
<table>
<colgroup>
<col style="width: 14%">
<col style="width: 28%">
<col style="width: 57%">
</colgroup>
<thead>
<tr class="header">
<th>Macro</th>
<th style="text-align: center;">Minimum Magnitude</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>FLT_ROUNDS</code></td>
<td style="text-align: center;"></td>
<td>Current rounding mode</td>
</tr>
<tr class="even">
<td><code>FLT_EVAL_METHOD</code></td>
<td style="text-align: center;"></td>
<td>Types used for evaluation</td>
</tr>
<tr class="odd">
<td><code>FLT_HAS_SUBNORM</code></td>
<td style="text-align: center;"></td>
<td>Subnormal support for <code>float</code></td>
</tr>
<tr class="even">
<td><code>DBL_HAS_SUBNORM</code></td>
<td style="text-align: center;"></td>
<td>Subnormal support for <code>double</code></td>
</tr>
<tr class="odd">
<td><code>LDBL_HAS_SUBNORM</code></td>
<td style="text-align: center;"></td>
<td>Subnormal support for <code>long double</code></td>
</tr>
<tr class="even">
<td><code>FLT_RADIX</code></td>
<td style="text-align: center;"><code>2</code></td>
<td>Floating point radix (base)</td>
</tr>
<tr class="odd">
<td><code>FLT_MANT_DIG</code></td>
<td style="text-align: center;"></td>
<td>Number of base <code>FLT_RADIX</code> digits in a
<code>float</code></td>
</tr>
<tr class="even">
<td><code>DBL_MANT_DIG</code></td>
<td style="text-align: center;"></td>
<td>Number of base <code>FLT_RADIX</code> digits in a
<code>double</code></td>
</tr>
<tr class="odd">
<td><code>LDBL_MANT_DIG</code></td>
<td style="text-align: center;"></td>
<td>Number of base <code>FLT_RADIX</code> digits in a
<code>long double</code></td>
</tr>
<tr class="even">
<td><code>FLT_DECIMAL_DIG</code></td>
<td style="text-align: center;"><code>6</code></td>
<td>Number of decimal digits required to encode a
<code>float</code></td>
</tr>
<tr class="odd">
<td><code>DBL_DECIMAL_DIG</code></td>
<td style="text-align: center;"><code>10</code></td>
<td>Number of decimal digits required to encode a
<code>double</code></td>
</tr>
<tr class="even">
<td><code>LDBL_DECIMAL_DIG</code></td>
<td style="text-align: center;"><code>10</code></td>
<td>Number of decimal digits required to encode a
<code>long double</code></td>
</tr>
<tr class="odd">
<td><code>DECIMAL_DIG</code></td>
<td style="text-align: center;"><code>10</code></td>
<td>Number of decimal digits required to encode the the widest floating
point number supported</td>
</tr>
<tr class="even">
<td><code>FLT_DIG</code></td>
<td style="text-align: center;"><code>6</code></td>
<td>Number of decimal digits that can be safely stored in a
<code>float</code></td>
</tr>
<tr class="odd">
<td><code>DBL_DIG</code></td>
<td style="text-align: center;"><code>10</code></td>
<td>Number of decimal digits that can be safely stored in a
<code>double</code></td>
</tr>
<tr class="even">
<td><code>LDBL_DIG</code></td>
<td style="text-align: center;"><code>10</code></td>
<td>Number of decimal digits that can be safely stored in a
<code>long double</code></td>
</tr>
<tr class="odd">
<td><code>FLT_MIN_EXP</code></td>
<td style="text-align: center;"></td>
<td><code>FLT_RADIX</code> to the <code>FLT_MIN_EXP-1</code> power is
the smallest normalized <code>float</code></td>
</tr>
<tr class="even">
<td><code>DBL_MIN_EXP</code></td>
<td style="text-align: center;"></td>
<td><code>FLT_RADIX</code> to the <code>DBL_MIN_EXP-1</code> power is
the smallest normalized <code>double</code></td>
</tr>
<tr class="odd">
<td><code>LDBL_MIN_EXP</code></td>
<td style="text-align: center;"></td>
<td><code>FLT_RADIX</code> to the <code>LDBL_MIN_EXP-1</code> power is
the smallest normalized <code>long double</code></td>
</tr>
<tr class="even">
<td><code>FLT_MIN_10_EXP</code></td>
<td style="text-align: center;"><code>-37</code></td>
<td>Minimum exponent such that <code>10</code> to this number is a
normalized <code>float</code></td>
</tr>
<tr class="odd">
<td><code>DBL_MIN_10_EXP</code></td>
<td style="text-align: center;"><code>-37</code></td>
<td>Minimum exponent such that <code>10</code> to this number is a
normalized <code>double</code></td>
</tr>
<tr class="even">
<td><code>LDBL_MIN_10_EXP</code></td>
<td style="text-align: center;"><code>-37</code></td>
<td>Minimum exponent such that <code>10</code> to this number is a
normalized <code>long_double</code></td>
</tr>
<tr class="odd">
<td><code>FLT_MAX_EXP</code></td>
<td style="text-align: center;"></td>
<td><code>FLT_RADIX</code> to the <code>FLT_MAX_EXP-1</code> power is
the largest finite <code>float</code></td>
</tr>
<tr class="even">
<td><code>DBL_MAX_EXP</code></td>
<td style="text-align: center;"></td>
<td><code>FLT_RADIX</code> to the <code>DBL_MAX_EXP-1</code> power is
the largest finite <code>double</code></td>
</tr>
<tr class="odd">
<td><code>LDBL_MAX_EXP</code></td>
<td style="text-align: center;"></td>
<td><code>FLT_RADIX</code> to the <code>LDBL_MAX_EXP-1</code> power is
the largest finite <code>long double</code></td>
</tr>
<tr class="even">
<td><code>FLT_MAX_10_EXP</code></td>
<td style="text-align: center;"><code>-37</code></td>
<td>Minimum exponent such that <code>10</code> to this number is a
finite <code>float</code></td>
</tr>
<tr class="odd">
<td><code>DBL_MAX_10_EXP</code></td>
<td style="text-align: center;"><code>-37</code></td>
<td>Minimum exponent such that <code>10</code> to this number is a
finite <code>double</code></td>
</tr>
<tr class="even">
<td><code>LDBL_MAX_10_EXP</code></td>
<td style="text-align: center;"><code>-37</code></td>
<td>Minimum exponent such that <code>10</code> to this number is a
finite <code>long_double</code></td>
</tr>
<tr class="odd">
<td><code>FLT_MAX</code></td>
<td style="text-align: center;"><code>1E+37</code></td>
<td>Largest finite <code>float</code></td>
</tr>
<tr class="even">
<td><code>DBL_MAX</code></td>
<td style="text-align: center;"><code>1E+37</code></td>
<td>Largest finite <code>double</code></td>
</tr>
<tr class="odd">
<td><code>LDBL_MAX</code></td>
<td style="text-align: center;"><code>1E+37</code></td>
<td>Largest finite <code>long double</code></td>
</tr>
</tbody>
</table>
<table>
<colgroup>
<col style="width: 14%">
<col style="width: 28%">
<col style="width: 57%">
</colgroup>
<thead>
<tr class="header">
<th>Macro</th>
<th style="text-align: center;">Maximum Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>FLT_EPSILON</code></td>
<td style="text-align: center;"><code>1E-5</code></td>
<td>Difference between 1 and the next biggest representable
<code>float</code></td>
</tr>
<tr class="even">
<td><code>DBL_EPSILON</code></td>
<td style="text-align: center;"><code>1E-9</code></td>
<td>Difference between 1 and the next biggest representable
<code>double</code></td>
</tr>
<tr class="odd">
<td><code>LDBL_EPSILON</code></td>
<td style="text-align: center;"><code>1E-9</code></td>
<td>Difference between 1 and the next biggest representable
<code>long double</code></td>
</tr>
<tr class="even">
<td><code>FLT_MIN</code></td>
<td style="text-align: center;"><code>1E-37</code></td>
<td>Minimum positive normalized <code>float</code></td>
</tr>
<tr class="odd">
<td><code>DBL_MIN</code></td>
<td style="text-align: center;"><code>1E-37</code></td>
<td>Minimum positive normalized <code>double</code></td>
</tr>
<tr class="even">
<td><code>LDBL_MIN</code></td>
<td style="text-align: center;"><code>1E-37</code></td>
<td>Minimum positive normalized <code>long double</code></td>
</tr>
<tr class="odd">
<td><code>FLT_TRUE_MIN</code></td>
<td style="text-align: center;"><code>1E-37</code></td>
<td>Minimum positive <code>float</code></td>
</tr>
<tr class="even">
<td><code>DBL_TRUE_MIN</code></td>
<td style="text-align: center;"><code>1E-37</code></td>
<td>Minimum positive <code>double</code></td>
</tr>
<tr class="odd">
<td><code>LDBL_TRUE_MIN</code></td>
<td style="text-align: center;"><code>1E-37</code></td>
<td>Minimum positive <code>long double</code></td>
</tr>
</tbody>
</table>
<p>The minimum and maximum values here are from the spec—they should
what you can at least expect across all platforms. Your super dooper
machine might do better, still!</p>
<h2 data-number="47.1" id="background-1"><span class="header-section-number">47.1</span> Background</h2>
<p>The spec allows a lot of leeway when it comes to how C represents
floating point numbers. This header file spells out the limits on those
numbers.</p>
<p>It gives a model that can describe any floating point number that I
<em>know</em> you’re going to absolutely love. It looks like this:</p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mstyle><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D460 TEX-I"></mjx-c></mjx-mi><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.413em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup><mjx-munderover space="2"><mjx-over style="padding-bottom: 0.111em; padding-left: 0.544em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45D TEX-I"></mjx-c></mjx-mi></mjx-over><mjx-box><mjx-munder><mjx-row><mjx-base><mjx-mo class="mjx-lop"><mjx-c class="mjx-c2211 TEX-S2"></mjx-c></mjx-mo></mjx-base></mjx-row><mjx-row><mjx-under style="padding-top: 0.167em; padding-left: 0.086em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-texatom></mjx-under></mjx-row></mjx-munder></mjx-box></mjx-munderover><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.06em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.413em;"><mjx-texatom size="s" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-texatom></mjx-script></mjx-msub><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2264"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2264"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-texatom></mjx-script></mjx-msub></mjx-mstyle></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mstyle displaystyle="true" scriptlevel="0"><mi>x</mi><mo>=</mo><mi>s</mi><msup><mi>b</mi><mi>e</mi></msup><munderover><mo data-mjx-texclass="OP">∑</mo><mrow data-mjx-texclass="ORD"><mi>k</mi><mo>=</mo><mn>1</mn></mrow><mi>p</mi></munderover><msub><mi>f</mi><mi>k</mi></msub><msup><mi>b</mi><mrow data-mjx-texclass="ORD"><mo>−</mo><mi>k</mi></mrow></msup><mo>,</mo><msub><mi>e</mi><mrow data-mjx-texclass="ORD"><mi>m</mi><mi>i</mi><mi>n</mi></mrow></msub><mo>≤</mo><mi>e</mi><mo>≤</mo><msub><mi>e</mi><mrow data-mjx-texclass="ORD"><mi>m</mi><mi>a</mi><mi>x</mi></mrow></msub></mstyle></math></mjx-assistive-mml></mjx-container></span></p>
<p>where:</p>
<table>
<thead>
<tr class="header">
<th style="text-align: center;">Variable</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D460 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>s</mi></math></mjx-assistive-mml></mjx-container></span></td>
<td>Sign, <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> or <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></mjx-assistive-mml></mjx-container></span></td>
</tr>
<tr class="even">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></mjx-assistive-mml></mjx-container></span></td>
<td>Base (radix), probably <span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></mjx-assistive-mml></mjx-container></span> on
your system</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D452 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>e</mi></math></mjx-assistive-mml></mjx-container></span></td>
<td>Exponent</td>
</tr>
<tr class="even">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45D TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></mjx-assistive-mml></mjx-container></span></td>
<td>Precision: how many base-<span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></mjx-assistive-mml></mjx-container></span>
digits in the number</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.06em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>f</mi><mi>k</mi></msub></math></mjx-assistive-mml></mjx-container></span></td>
<td>The individual digits of the number, the significand</td>
</tr>
</tbody>
</table>
<p>But let’s blissfully ignore all that for a second.</p>
<p>Let’s assume your computer uses base 2 for it’s floating point (it
probably does). And that in the example below the 1s-and-0s numbers are
in binary, and the rest are in decimal.</p>
<p>The short of it is you could have floating point numbers like shown
in this example:</p>
<p><span class="math inline"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 103.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-cD7"></mjx-c></mjx-mo><mjx-msup space="3"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c31"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c30"></mjx-c><mjx-c class="mjx-c2E"></mjx-c><mjx-c class="mjx-c36"></mjx-c><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c35"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>0.10100101</mn><mo>×</mo><msup><mn>2</mn><mn>5</mn></msup><mo>=</mo><mo>−</mo><mn>10100.101</mn><mo>=</mo><mo>−</mo><mn>20.625</mn></math></mjx-assistive-mml></mjx-container></span></p>
<p>That’s your fractional part multiplied by the base to the exponent’s
power. The exponent controls where the decimal point is. It “floats”
around!</p>
<!--
Or, more specifically, that example uses:

$s=-1$ \
$b=2$ \
$e=5$ \
$p=8$ \
$f_n=10100101$ 
-->
<h2 data-number="47.2" id="flt_rounds-details"><span class="header-section-number">47.2</span> <code>FLT_ROUNDS</code>
Details</h2>
<p>This tells you the rounding mode. It can be changed with a call to <a href="#man-fegetround"><code>fesetround()</code></a>.</p>
<table>
<thead>
<tr class="header">
<th style="text-align: center;">Mode</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>-1</code></td>
<td>Indeterminable</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>0</code></td>
<td>Toward zero</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>1</code></td>
<td>To nearest</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>2</code></td>
<td>Toward positive infinity</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>3</code></td>
<td>Toward negative infinity… and beyond!</td>
</tr>
</tbody>
</table>
<p>Unlike every other macro in this here header, <code>FLT_ROUNDS</code>
might not be a constant expression.</p>
<h2 data-number="47.3" id="flt_eval_method-details"><span class="header-section-number">47.3</span> <code>FLT_EVAL_METHOD</code>
Details</h2>
<p>This basically tells you how floating point values are promoted to
different types in expressions.</p>
<table>
<colgroup>
<col style="width: 14%">
<col style="width: 85%">
</colgroup>
<thead>
<tr class="header">
<th style="text-align: center;">Method</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>-1</code></td>
<td>Indeterminable</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>0</code></td>
<td>Evaluate all operations and constants to the precision of their
respective types</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>1</code></td>
<td>Evaluate <code>float</code> and <code>double</code> operations as
<code>double</code> and <code>long double</code> ops as
<code>long double</code></td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>2</code></td>
<td>Evaluate all operations and constants as
<code>long double</code></td>
</tr>
</tbody>
</table>
<h2 data-number="47.4" id="subnormal-numbers"><span class="header-section-number">47.4</span> Subnormal Numbers</h2>
<p>The macros <code>FLT_HAS_SUBNORM</code>,
<code>DBL_HAS_SUBNORM</code>, and <code>LDBL_HAS_SUBNORM</code> all let
you know if those types support <a href="https://en.wikipedia.org/wiki/Subnormal_number">subnormal
numbers</a><a href="footnotes.html#fn225" class="footnote-ref" id="fnref225" role="doc-noteref"><sup>225</sup></a>.</p>
<table>
<thead>
<tr class="header">
<th style="text-align: center;">Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>-1</code></td>
<td>Indeterminable</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>0</code></td>
<td>Subnormals not supported for this type</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>1</code></td>
<td>Subnormals supported for this type</td>
</tr>
</tbody>
</table>
<h2 data-number="47.5" id="how-many-decimal-places-can-i-use"><span class="header-section-number">47.5</span> How Many Decimal Places Can I
Use?</h2>
<p>It depends on what you want to do.</p>
<p>The safe thing is if you never use more than <code>FLT_DIG</code>
base-10 digits in your <code>float</code>, you’re good. (Same for
<code>DBL_DIG</code> and <code>LDBL_DIG</code> for their types.)</p>
<p>And by “use” I mean print out, have in code, read from the keyboard,
etc.</p>
<p>You can print out that many decimal places with <code>printf()</code>
and the <code>%g</code> format specifier:</p>
<div class="sourceCode" id="cb937"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb937-1"><a href="float.html#cb937-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb937-2"><a href="float.html#cb937-2"></a><span class="pp">#include </span><span class="im">&lt;float.h&gt;</span></span>
<span id="cb937-3"><a href="float.html#cb937-3"></a></span>
<span id="cb937-4"><a href="float.html#cb937-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb937-5"><a href="float.html#cb937-5"></a><span class="op">{</span></span>
<span id="cb937-6"><a href="float.html#cb937-6"></a>    <span class="dt">float</span> pi <span class="op">=</span> <span class="fl">3.1415926535897932384626433832795028841971</span><span class="op">;</span></span>
<span id="cb937-7"><a href="float.html#cb937-7"></a></span>
<span id="cb937-8"><a href="float.html#cb937-8"></a>    <span class="co">// With %g or %G, the precision refers to the number of significant</span></span>
<span id="cb937-9"><a href="float.html#cb937-9"></a>    <span class="co">// digits:</span></span>
<span id="cb937-10"><a href="float.html#cb937-10"></a></span>
<span id="cb937-11"><a href="float.html#cb937-11"></a>    printf<span class="op">(</span><span class="st">"%.*g</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DIG<span class="op">,</span> pi<span class="op">);</span>  <span class="co">// For me: 3.14159</span></span>
<span id="cb937-12"><a href="float.html#cb937-12"></a></span>
<span id="cb937-13"><a href="float.html#cb937-13"></a>    <span class="co">// But %f prints too many, since the precision is the number of</span></span>
<span id="cb937-14"><a href="float.html#cb937-14"></a>    <span class="co">// digits to the right of the decimal--it doesn't count the digits</span></span>
<span id="cb937-15"><a href="float.html#cb937-15"></a>    <span class="co">// to the left of it:</span></span>
<span id="cb937-16"><a href="float.html#cb937-16"></a></span>
<span id="cb937-17"><a href="float.html#cb937-17"></a>    printf<span class="op">(</span><span class="st">"%.*f</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DIG<span class="op">,</span> pi<span class="op">);</span>  <span class="co">// For me: 3.14159... 3 ???</span></span>
<span id="cb937-18"><a href="float.html#cb937-18"></a><span class="op">}</span></span></code></pre></div>
<p>That’s the end, but stay tuned for the exciting conclusion of “How
Many Decimal Places Can I Use?”</p>
<p>Because base 10 and base 2 (your typical <code>FLT_RADIX</code>)
don’t mix very well, you can actually have more than
<code>FLT_DIG</code> in your <code>float</code>; the bits of storage go
out a little farther. But these might round in a way you don’t
expect.</p>
<p>But if you want to convert a floating point number to base 10 and
then be able to convert it back again to the exact same floating point
number, you’ll need <code>FLT_DECIMAL_DIG</code> digits from your
<code>float</code> to make sure you get those extra bits of storage
represented.</p>
<p>Here’s some example output that shows how the value stored might have
some extra decimal places at the end.</p>
<div class="sourceCode" id="cb938"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb938-1"><a href="float.html#cb938-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb938-2"><a href="float.html#cb938-2"></a><span class="pp">#include </span><span class="im">&lt;math.h&gt;</span></span>
<span id="cb938-3"><a href="float.html#cb938-3"></a><span class="pp">#include </span><span class="im">&lt;assert.h&gt;</span></span>
<span id="cb938-4"><a href="float.html#cb938-4"></a><span class="pp">#include </span><span class="im">&lt;float.h&gt;</span></span>
<span id="cb938-5"><a href="float.html#cb938-5"></a></span>
<span id="cb938-6"><a href="float.html#cb938-6"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb938-7"><a href="float.html#cb938-7"></a><span class="op">{</span></span>
<span id="cb938-8"><a href="float.html#cb938-8"></a>    printf<span class="op">(</span><span class="st">"FLT_DIG = %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DIG<span class="op">);</span></span>
<span id="cb938-9"><a href="float.html#cb938-9"></a>    printf<span class="op">(</span><span class="st">"FLT_DECIMAL_DIG = %d</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> FLT_DECIMAL_DIG<span class="op">);</span></span>
<span id="cb938-10"><a href="float.html#cb938-10"></a></span>
<span id="cb938-11"><a href="float.html#cb938-11"></a>    assert<span class="op">(</span>FLT_DIG <span class="op">==</span> <span class="dv">6</span><span class="op">);</span>  <span class="co">// Code below assumes this</span></span>
<span id="cb938-12"><a href="float.html#cb938-12"></a></span>
<span id="cb938-13"><a href="float.html#cb938-13"></a>    <span class="cf">for</span> <span class="op">(</span><span class="dt">float</span> x <span class="op">=</span> <span class="fl">0.123456</span><span class="op">;</span> x <span class="op">&lt;</span> <span class="fl">0.12346</span><span class="op">;</span> x <span class="op">+=</span> <span class="fl">0.000001</span><span class="op">)</span> <span class="op">{</span></span>
<span id="cb938-14"><a href="float.html#cb938-14"></a>        printf<span class="op">(</span><span class="st">"As written: %.*g</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DIG<span class="op">,</span> x<span class="op">);</span></span>
<span id="cb938-15"><a href="float.html#cb938-15"></a>        printf<span class="op">(</span><span class="st">"As stored:  %.*g</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> FLT_DECIMAL_DIG<span class="op">,</span> x<span class="op">);</span></span>
<span id="cb938-16"><a href="float.html#cb938-16"></a>    <span class="op">}</span></span>
<span id="cb938-17"><a href="float.html#cb938-17"></a><span class="op">}</span></span></code></pre></div>
<p>And the output on my machine, starting at <code>0.123456</code> and
incrementing by <code>0.000001</code> each time:</p>
<div class="sourceCode" id="cb939"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb939-1"><a href="float.html#cb939-1" aria-hidden="true" tabindex="-1"></a>FLT_DIG = 6</span>
<span id="cb939-2"><a href="float.html#cb939-2" aria-hidden="true" tabindex="-1"></a>FLT_DECIMAL_DIG = 9</span>
<span id="cb939-3"><a href="float.html#cb939-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb939-4"><a href="float.html#cb939-4" aria-hidden="true" tabindex="-1"></a>As written: 0.123456</span>
<span id="cb939-5"><a href="float.html#cb939-5" aria-hidden="true" tabindex="-1"></a>As stored:  0.123456001</span>
<span id="cb939-6"><a href="float.html#cb939-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb939-7"><a href="float.html#cb939-7" aria-hidden="true" tabindex="-1"></a>As written: 0.123457</span>
<span id="cb939-8"><a href="float.html#cb939-8" aria-hidden="true" tabindex="-1"></a>As stored:  0.123457</span>
<span id="cb939-9"><a href="float.html#cb939-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb939-10"><a href="float.html#cb939-10" aria-hidden="true" tabindex="-1"></a>As written: 0.123458</span>
<span id="cb939-11"><a href="float.html#cb939-11" aria-hidden="true" tabindex="-1"></a>As stored:  0.123457998</span>
<span id="cb939-12"><a href="float.html#cb939-12" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb939-13"><a href="float.html#cb939-13" aria-hidden="true" tabindex="-1"></a>As written: 0.123459</span>
<span id="cb939-14"><a href="float.html#cb939-14" aria-hidden="true" tabindex="-1"></a>As stored:  0.123458996</span>
<span id="cb939-15"><a href="float.html#cb939-15" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb939-16"><a href="float.html#cb939-16" aria-hidden="true" tabindex="-1"></a>As written: 0.12346</span>
<span id="cb939-17"><a href="float.html#cb939-17" aria-hidden="true" tabindex="-1"></a>As stored:  0.123459995</span></code></pre></div>
<p>You can see that the value stored isn’t always the value we’re
expecting since base-2 can’t represent all base-10 fractions exactly.
The best it can do is store more places and then round.</p>
<p>Also notice that even though we tried to stop the <code>for</code>
loop <em>before</em> <code>0.123460</code>, it actually ran including
that value since the stored version of that number was
<code>0.123459995</code>, which is still less than
<code>0.123460</code>.</p>
<p>Aren’t floating point numbers fun?</p>
<h2 data-number="47.6" id="comprehensive-example"><span class="header-section-number">47.6</span> Comprehensive Example</h2>
<p>Here’s a program that prints out the details for a particular
machine:</p>
<div class="sourceCode" id="cb940"><pre class="sourceCode numberSource c numberLines"><code class="sourceCode c"><span id="cb940-1"><a href="float.html#cb940-1"></a><span class="pp">#include </span><span class="im">&lt;stdio.h&gt;</span></span>
<span id="cb940-2"><a href="float.html#cb940-2"></a><span class="pp">#include </span><span class="im">&lt;float.h&gt;</span></span>
<span id="cb940-3"><a href="float.html#cb940-3"></a></span>
<span id="cb940-4"><a href="float.html#cb940-4"></a><span class="dt">int</span> main<span class="op">(</span><span class="dt">void</span><span class="op">)</span></span>
<span id="cb940-5"><a href="float.html#cb940-5"></a><span class="op">{</span></span>
<span id="cb940-6"><a href="float.html#cb940-6"></a>    printf<span class="op">(</span><span class="st">"FLT_RADIX: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_RADIX<span class="op">);</span></span>
<span id="cb940-7"><a href="float.html#cb940-7"></a>    printf<span class="op">(</span><span class="st">"FLT_ROUNDS: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_ROUNDS<span class="op">);</span></span>
<span id="cb940-8"><a href="float.html#cb940-8"></a>    printf<span class="op">(</span><span class="st">"FLT_EVAL_METHOD: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_EVAL_METHOD<span class="op">);</span></span>
<span id="cb940-9"><a href="float.html#cb940-9"></a>    printf<span class="op">(</span><span class="st">"DECIMAL_DIG: %d</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> DECIMAL_DIG<span class="op">);</span></span>
<span id="cb940-10"><a href="float.html#cb940-10"></a></span>
<span id="cb940-11"><a href="float.html#cb940-11"></a>    printf<span class="op">(</span><span class="st">"FLT_HAS_SUBNORM: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_HAS_SUBNORM<span class="op">);</span></span>
<span id="cb940-12"><a href="float.html#cb940-12"></a>    printf<span class="op">(</span><span class="st">"FLT_MANT_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_MANT_DIG<span class="op">);</span></span>
<span id="cb940-13"><a href="float.html#cb940-13"></a>    printf<span class="op">(</span><span class="st">"FLT_DECIMAL_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DECIMAL_DIG<span class="op">);</span></span>
<span id="cb940-14"><a href="float.html#cb940-14"></a>    printf<span class="op">(</span><span class="st">"FLT_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DIG<span class="op">);</span></span>
<span id="cb940-15"><a href="float.html#cb940-15"></a>    printf<span class="op">(</span><span class="st">"FLT_MIN_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_MIN_EXP<span class="op">);</span></span>
<span id="cb940-16"><a href="float.html#cb940-16"></a>    printf<span class="op">(</span><span class="st">"FLT_MIN_10_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_MIN_10_EXP<span class="op">);</span></span>
<span id="cb940-17"><a href="float.html#cb940-17"></a>    printf<span class="op">(</span><span class="st">"FLT_MAX_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_MAX_EXP<span class="op">);</span></span>
<span id="cb940-18"><a href="float.html#cb940-18"></a>    printf<span class="op">(</span><span class="st">"FLT_MAX_10_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_MAX_10_EXP<span class="op">);</span></span>
<span id="cb940-19"><a href="float.html#cb940-19"></a>    printf<span class="op">(</span><span class="st">"FLT_MIN: %.*e</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DECIMAL_DIG<span class="op">,</span> FLT_MIN<span class="op">);</span></span>
<span id="cb940-20"><a href="float.html#cb940-20"></a>    printf<span class="op">(</span><span class="st">"FLT_MAX: %.*e</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DECIMAL_DIG<span class="op">,</span> FLT_MAX<span class="op">);</span></span>
<span id="cb940-21"><a href="float.html#cb940-21"></a>    printf<span class="op">(</span><span class="st">"FLT_EPSILON: %.*e</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> FLT_DECIMAL_DIG<span class="op">,</span> FLT_EPSILON<span class="op">);</span></span>
<span id="cb940-22"><a href="float.html#cb940-22"></a>    printf<span class="op">(</span><span class="st">"FLT_TRUE_MIN: %.*e</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> FLT_DECIMAL_DIG<span class="op">,</span> FLT_TRUE_MIN<span class="op">);</span></span>
<span id="cb940-23"><a href="float.html#cb940-23"></a></span>
<span id="cb940-24"><a href="float.html#cb940-24"></a>    printf<span class="op">(</span><span class="st">"DBL_HAS_SUBNORM: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_HAS_SUBNORM<span class="op">);</span></span>
<span id="cb940-25"><a href="float.html#cb940-25"></a>    printf<span class="op">(</span><span class="st">"DBL_MANT_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_MANT_DIG<span class="op">);</span></span>
<span id="cb940-26"><a href="float.html#cb940-26"></a>    printf<span class="op">(</span><span class="st">"DBL_DECIMAL_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">);</span></span>
<span id="cb940-27"><a href="float.html#cb940-27"></a>    printf<span class="op">(</span><span class="st">"DBL_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DIG<span class="op">);</span></span>
<span id="cb940-28"><a href="float.html#cb940-28"></a>    printf<span class="op">(</span><span class="st">"DBL_MIN_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_MIN_EXP<span class="op">);</span></span>
<span id="cb940-29"><a href="float.html#cb940-29"></a>    printf<span class="op">(</span><span class="st">"DBL_MIN_10_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_MIN_10_EXP<span class="op">);</span></span>
<span id="cb940-30"><a href="float.html#cb940-30"></a>    printf<span class="op">(</span><span class="st">"DBL_MAX_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_MAX_EXP<span class="op">);</span></span>
<span id="cb940-31"><a href="float.html#cb940-31"></a>    printf<span class="op">(</span><span class="st">"DBL_MAX_10_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_MAX_10_EXP<span class="op">);</span></span>
<span id="cb940-32"><a href="float.html#cb940-32"></a>    printf<span class="op">(</span><span class="st">"DBL_MIN: %.*e</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> DBL_MIN<span class="op">);</span></span>
<span id="cb940-33"><a href="float.html#cb940-33"></a>    printf<span class="op">(</span><span class="st">"DBL_MAX: %.*e</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> DBL_MAX<span class="op">);</span></span>
<span id="cb940-34"><a href="float.html#cb940-34"></a>    printf<span class="op">(</span><span class="st">"DBL_EPSILON: %.*e</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> DBL_EPSILON<span class="op">);</span></span>
<span id="cb940-35"><a href="float.html#cb940-35"></a>    printf<span class="op">(</span><span class="st">"DBL_TRUE_MIN: %.*e</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> DBL_DECIMAL_DIG<span class="op">,</span> DBL_TRUE_MIN<span class="op">);</span></span>
<span id="cb940-36"><a href="float.html#cb940-36"></a></span>
<span id="cb940-37"><a href="float.html#cb940-37"></a>    printf<span class="op">(</span><span class="st">"LDBL_HAS_SUBNORM: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_HAS_SUBNORM<span class="op">);</span></span>
<span id="cb940-38"><a href="float.html#cb940-38"></a>    printf<span class="op">(</span><span class="st">"LDBL_MANT_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_MANT_DIG<span class="op">);</span></span>
<span id="cb940-39"><a href="float.html#cb940-39"></a>    printf<span class="op">(</span><span class="st">"LDBL_DECIMAL_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">);</span></span>
<span id="cb940-40"><a href="float.html#cb940-40"></a>    printf<span class="op">(</span><span class="st">"LDBL_DIG: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DIG<span class="op">);</span></span>
<span id="cb940-41"><a href="float.html#cb940-41"></a>    printf<span class="op">(</span><span class="st">"LDBL_MIN_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_MIN_EXP<span class="op">);</span></span>
<span id="cb940-42"><a href="float.html#cb940-42"></a>    printf<span class="op">(</span><span class="st">"LDBL_MIN_10_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_MIN_10_EXP<span class="op">);</span></span>
<span id="cb940-43"><a href="float.html#cb940-43"></a>    printf<span class="op">(</span><span class="st">"LDBL_MAX_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_MAX_EXP<span class="op">);</span></span>
<span id="cb940-44"><a href="float.html#cb940-44"></a>    printf<span class="op">(</span><span class="st">"LDBL_MAX_10_EXP: %d</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_MAX_10_EXP<span class="op">);</span></span>
<span id="cb940-45"><a href="float.html#cb940-45"></a>    printf<span class="op">(</span><span class="st">"LDBL_MIN: %.*Le</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">,</span> LDBL_MIN<span class="op">);</span></span>
<span id="cb940-46"><a href="float.html#cb940-46"></a>    printf<span class="op">(</span><span class="st">"LDBL_MAX: %.*Le</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">,</span> LDBL_MAX<span class="op">);</span></span>
<span id="cb940-47"><a href="float.html#cb940-47"></a>    printf<span class="op">(</span><span class="st">"LDBL_EPSILON: %.*Le</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">,</span> LDBL_EPSILON<span class="op">);</span></span>
<span id="cb940-48"><a href="float.html#cb940-48"></a>    printf<span class="op">(</span><span class="st">"LDBL_TRUE_MIN: %.*Le</span><span class="sc">\n\n</span><span class="st">"</span><span class="op">,</span> LDBL_DECIMAL_DIG<span class="op">,</span> LDBL_TRUE_MIN<span class="op">);</span></span>
<span id="cb940-49"><a href="float.html#cb940-49"></a>    </span>
<span id="cb940-50"><a href="float.html#cb940-50"></a>    printf<span class="op">(</span><span class="st">"sizeof(float): %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">float</span><span class="op">));</span></span>
<span id="cb940-51"><a href="float.html#cb940-51"></a>    printf<span class="op">(</span><span class="st">"sizeof(double): %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">double</span><span class="op">));</span></span>
<span id="cb940-52"><a href="float.html#cb940-52"></a>    printf<span class="op">(</span><span class="st">"sizeof(long double): %zu</span><span class="sc">\n</span><span class="st">"</span><span class="op">,</span> <span class="kw">sizeof</span><span class="op">(</span><span class="dt">long</span> <span class="dt">double</span><span class="op">));</span></span>
<span id="cb940-53"><a href="float.html#cb940-53"></a><span class="op">}</span></span></code></pre></div>
<p>And here’s the output on my machine:</p>
<div class="sourceCode" id="cb941"><pre class="sourceCode default"><code class="sourceCode default"><span id="cb941-1"><a href="float.html#cb941-1" aria-hidden="true" tabindex="-1"></a>FLT_RADIX: 2</span>
<span id="cb941-2"><a href="float.html#cb941-2" aria-hidden="true" tabindex="-1"></a>FLT_ROUNDS: 1</span>
<span id="cb941-3"><a href="float.html#cb941-3" aria-hidden="true" tabindex="-1"></a>FLT_EVAL_METHOD: 0</span>
<span id="cb941-4"><a href="float.html#cb941-4" aria-hidden="true" tabindex="-1"></a>DECIMAL_DIG: 21</span>
<span id="cb941-5"><a href="float.html#cb941-5" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb941-6"><a href="float.html#cb941-6" aria-hidden="true" tabindex="-1"></a>FLT_HAS_SUBNORM: 1</span>
<span id="cb941-7"><a href="float.html#cb941-7" aria-hidden="true" tabindex="-1"></a>FLT_MANT_DIG: 24</span>
<span id="cb941-8"><a href="float.html#cb941-8" aria-hidden="true" tabindex="-1"></a>FLT_DECIMAL_DIG: 9</span>
<span id="cb941-9"><a href="float.html#cb941-9" aria-hidden="true" tabindex="-1"></a>FLT_DIG: 6</span>
<span id="cb941-10"><a href="float.html#cb941-10" aria-hidden="true" tabindex="-1"></a>FLT_MIN_EXP: -125</span>
<span id="cb941-11"><a href="float.html#cb941-11" aria-hidden="true" tabindex="-1"></a>FLT_MIN_10_EXP: -37</span>
<span id="cb941-12"><a href="float.html#cb941-12" aria-hidden="true" tabindex="-1"></a>FLT_MAX_EXP: 128</span>
<span id="cb941-13"><a href="float.html#cb941-13" aria-hidden="true" tabindex="-1"></a>FLT_MAX_10_EXP: 38</span>
<span id="cb941-14"><a href="float.html#cb941-14" aria-hidden="true" tabindex="-1"></a>FLT_MIN: 1.175494351e-38</span>
<span id="cb941-15"><a href="float.html#cb941-15" aria-hidden="true" tabindex="-1"></a>FLT_MAX: 3.402823466e+38</span>
<span id="cb941-16"><a href="float.html#cb941-16" aria-hidden="true" tabindex="-1"></a>FLT_EPSILON: 1.192092896e-07</span>
<span id="cb941-17"><a href="float.html#cb941-17" aria-hidden="true" tabindex="-1"></a>FLT_TRUE_MIN: 1.401298464e-45</span>
<span id="cb941-18"><a href="float.html#cb941-18" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb941-19"><a href="float.html#cb941-19" aria-hidden="true" tabindex="-1"></a>DBL_HAS_SUBNORM: 1</span>
<span id="cb941-20"><a href="float.html#cb941-20" aria-hidden="true" tabindex="-1"></a>DBL_MANT_DIG: 53</span>
<span id="cb941-21"><a href="float.html#cb941-21" aria-hidden="true" tabindex="-1"></a>DBL_DECIMAL_DIG: 17</span>
<span id="cb941-22"><a href="float.html#cb941-22" aria-hidden="true" tabindex="-1"></a>DBL_DIG: 15</span>
<span id="cb941-23"><a href="float.html#cb941-23" aria-hidden="true" tabindex="-1"></a>DBL_MIN_EXP: -1021</span>
<span id="cb941-24"><a href="float.html#cb941-24" aria-hidden="true" tabindex="-1"></a>DBL_MIN_10_EXP: -307</span>
<span id="cb941-25"><a href="float.html#cb941-25" aria-hidden="true" tabindex="-1"></a>DBL_MAX_EXP: 1024</span>
<span id="cb941-26"><a href="float.html#cb941-26" aria-hidden="true" tabindex="-1"></a>DBL_MAX_10_EXP: 308</span>
<span id="cb941-27"><a href="float.html#cb941-27" aria-hidden="true" tabindex="-1"></a>DBL_MIN: 2.22507385850720138e-308</span>
<span id="cb941-28"><a href="float.html#cb941-28" aria-hidden="true" tabindex="-1"></a>DBL_MAX: 1.79769313486231571e+308</span>
<span id="cb941-29"><a href="float.html#cb941-29" aria-hidden="true" tabindex="-1"></a>DBL_EPSILON: 2.22044604925031308e-16</span>
<span id="cb941-30"><a href="float.html#cb941-30" aria-hidden="true" tabindex="-1"></a>DBL_TRUE_MIN: 4.94065645841246544e-324</span>
<span id="cb941-31"><a href="float.html#cb941-31" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb941-32"><a href="float.html#cb941-32" aria-hidden="true" tabindex="-1"></a>LDBL_HAS_SUBNORM: 1</span>
<span id="cb941-33"><a href="float.html#cb941-33" aria-hidden="true" tabindex="-1"></a>LDBL_MANT_DIG: 64</span>
<span id="cb941-34"><a href="float.html#cb941-34" aria-hidden="true" tabindex="-1"></a>LDBL_DECIMAL_DIG: 21</span>
<span id="cb941-35"><a href="float.html#cb941-35" aria-hidden="true" tabindex="-1"></a>LDBL_DIG: 18</span>
<span id="cb941-36"><a href="float.html#cb941-36" aria-hidden="true" tabindex="-1"></a>LDBL_MIN_EXP: -16381</span>
<span id="cb941-37"><a href="float.html#cb941-37" aria-hidden="true" tabindex="-1"></a>LDBL_MIN_10_EXP: -4931</span>
<span id="cb941-38"><a href="float.html#cb941-38" aria-hidden="true" tabindex="-1"></a>LDBL_MAX_EXP: 16384</span>
<span id="cb941-39"><a href="float.html#cb941-39" aria-hidden="true" tabindex="-1"></a>LDBL_MAX_10_EXP: 4932</span>
<span id="cb941-40"><a href="float.html#cb941-40" aria-hidden="true" tabindex="-1"></a>LDBL_MIN: 3.362103143112093506263e-4932</span>
<span id="cb941-41"><a href="float.html#cb941-41" aria-hidden="true" tabindex="-1"></a>LDBL_MAX: 1.189731495357231765021e+4932</span>
<span id="cb941-42"><a href="float.html#cb941-42" aria-hidden="true" tabindex="-1"></a>LDBL_EPSILON: 1.084202172485504434007e-19</span>
<span id="cb941-43"><a href="float.html#cb941-43" aria-hidden="true" tabindex="-1"></a>LDBL_TRUE_MIN: 3.645199531882474602528e-4951</span>
<span id="cb941-44"><a href="float.html#cb941-44" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb941-45"><a href="float.html#cb941-45" aria-hidden="true" tabindex="-1"></a>sizeof(float): 4</span>
<span id="cb941-46"><a href="float.html#cb941-46" aria-hidden="true" tabindex="-1"></a>sizeof(double): 8</span>
<span id="cb941-47"><a href="float.html#cb941-47" aria-hidden="true" tabindex="-1"></a>sizeof(long double): 16</span></code></pre></div>

</body>