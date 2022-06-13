# 24 Bitwise Operations

These numeric operations effectively allow you to manipulate individual bits in variables, fitting since C is such a low-level langauge[139](https://beej.us/guide/bgc/html/split/footnotes.html#fn139).

If you’re not familiar with bitwise operations, [Wikipedia has a good bitwise article](https://en.wikipedia.org/wiki/Bitwise_operation)[140](https://beej.us/guide/bgc/html/split/footnotes.html#fn140).

## 24.1 Bitwise AND, OR, XOR, and NOT

For each of these, the [usual arithmetic conversions](https://beej.us/guide/bgc/html/split/types-iii-conversions.html#usual-arithmetic-conversions) take place on the operands (which in this case must be an integer type), and then the appropriate bitwise operation is performed.

  

<table style="">
<colgroup>
<col style="width: 20%">
<col style="width: 60%">
<col style="width: 20%">
</colgroup>
<thead>
<tr class="header">
<th>Operation</th>
<th style="text-align: center;">Operator</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>AND</td>
<td style="text-align: center;"><code>&amp;</code></td>
<td><code>a = b &amp; c</code></td>
</tr>
<tr class="even">
<td>OR</td>
<td style="text-align: center;"><code>|</code></td>
<td><code>a = b | c</code></td>
</tr>
<tr class="odd">
<td>XOR</td>
<td style="text-align: center;"><code>^</code></td>
<td><code>a = b ^ c</code></td>
</tr>
<tr class="even">
<td>NOT</td>
<td style="text-align: center;"><code>~</code></td>
<td style=""><code style="">a = ~c</code></td>
</tr>
</tbody>
</table>

<table style="">
<colgroup>
<col style="width: 33%">
<col style="width: 33%">
<col style="width: 33%">
</colgroup>
<thead>
<tr class="header">
<th>Operator</th>
<th style="">Example</th>
<th style="">Longhand equivalent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>&amp;=</code></td>
<td><code>a &amp;= c</code></td>
<td style=""><code>a = a &amp; c</code></td>
</tr>
<tr class="even">
<td><code>|=</code></td>
<td><code>a |= c</code></td>
<td style=""><code>a = a | c</code></td>
</tr>
<tr class="odd">
<td><code>^=</code></td>
<td><code>a ^= c</code></td>
<td><code>a = a ^ c</code></td>
</tr>
</tbody>
</table>
## 24.2 Bitwise Shift

For these, the [integer promotions](https://beej.us/guide/bgc/html/split/types-iii-conversions.html#integer-promotions) are performed on each operand (which must be an integer type) and then a bitwise shift is executed. The type of the result is the type of the promoted left operand.

New bits are filled with zeros, with a possible exception noted in the implementation-defined behavior, below.

  
<table style="">
<colgroup>
<col style="width: 20%">
<col style="width: 60%">
<col style="width: 20%">
</colgroup>
<thead>
<tr class="header">
<th style="">Operation</th>
<th style="text-align: center;">Operator</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="">Shift left</td>
<td style="text-align: center;"><code>&lt;&lt;</code></td>
<td><code>a = b &lt;&lt; c</code></td>
</tr>
<tr class="even">
<td>Shift right</td>
<td style="text-align: center;"><code>&gt;&gt;</code></td>
<td><code>a = b &gt;&gt; c</code></td>
</tr>
</tbody>
</table>

<table style="">
<colgroup>
<col style="width: 33%">
<col style="width: 33%">
<col style="width: 33%">
</colgroup>
<thead>
<tr class="header">
<th style="">Operator</th>
<th style="">Example</th>
<th>Longhand equivalent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style=""><code>&gt;&gt;=</code></td>
<td style=""><code>a &gt;&gt;= c</code></td>
<td style=""><code style="">a = a &gt;&gt; c</code></td>
</tr>
<tr class="even">
<td><code>&lt;&lt;=</code></td>
<td><code>a &lt;&lt;= c</code></td>
<td style=""><code style="">a = a &lt;&lt; c</code></td>
</tr>
</tbody>
</table>


Watch for undefined behavior: no negative shifts, and no shifts that are larger than the size of the promoted left operand.

Also watch for implementation-defined behavior: if you right-shift a negative number, the results are implementation-defined. (It’s perfectly fine to right-shift a signed `int`, just make sure it’s positive.)