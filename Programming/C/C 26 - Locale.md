# 26 Locale and Internationalization

_Localization_ is the process of making your app ready to work well in different locales (or countries).

As you might know, not everyone uses the same character for decimal points or for thousands separators… or for currency.

These locales have names, and you can select one to use. For example, a US locale might write a number like:

100,000.00

Whereas in Brazil, the same might be written with the commas and decimal points swapped:

100.000,00

Makes it easier to write your code so it ports to other nationalities with ease!

Well, sort of. Turns out C only has one built-in locale, and it’s limited. The spec really leaves a lot of ambiguity here; it’s hard to be completely portable.

But we’ll do our best!

## 26.1 Setting the Localization, Quick and Dirty

For these calls, include `<locale.h>`.

There is basically one thing you can portably do here in terms of declaring a specific locale. This is likely what you want to do if you’re going to do locale anything:

```
setlocale(LC_ALL, "");  // Use this environment's locale for everything
```

You’ll want to call that so that the program gets initialized with your current locale.

Getting into more details, there is one more thing you can do and stay portable:

```
setlocale(LC_ALL, "C");  // Use the default C locale
```

but that’s called by default every time your program starts, so there’s not much need to do it yourself.

In that second string, you can specify any locale supported by your system. This is completely system-dependent, so it will vary. On my system, I can specify this:

```
setlocale(LC_ALL, "en_US.UTF-8");  // Non-portable!
```

And that’ll work. But it’s only portable to systems which have that exact same name for that exact same locale, and you can’t guarantee it.

By passing in an empty string (`""`) for the second argument, you’re telling C, “Hey, figure out what the current locale on this system is so I don’t have to tell you.”

## 26.2 Getting the Monetary Locale Settings

Because moving green pieces of paper around promises to be the key to happiness[143](https://beej.us/guide/bgc/html/split/footnotes.html#fn143), let’s talk about monetary locale. When you’re writing portable code, you have to know what to type for cash, right? Whether that’s “$”, “€”, “¥”, or “£”.

How can you write that code without going insane? Luckily, once you call `setlocale(LC_ALL, "")`, you can just look these up with a call to `localeconv()`:

```
struct lconv *x = localeconv();
```

This function returns a pointer to a statically-allocated `struct lconv` that has all that juicy information you’re looking for.

Here are the fields of `struct lconv` and their meanings.

First, some conventions. An `_p_` means “positive”, and `_n_` means “negative”, and `int_` means “international”. Though a lot of these are type `char` or `char*`, most (or the strings they point to) are actually treated as integers[144](https://beej.us/guide/bgc/html/split/footnotes.html#fn144).

Before we go further, know that `CHAR_MAX` (from `<limits.h>`) is the maximum value that can be held in a `char`. And that many of the following `char` values use that to indicate the value isn’t available in the given locale.

  

<table style="">
<colgroup>
<col style="width: 31%">
<col style="width: 68%">
</colgroup>
<thead>
<tr class="header">
<th style="">Field</th>
<th style="">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style=""><code style="">char *mon_decimal_point</code></td>
<td style="">Decimal pointer character for money, e.g.&nbsp;<code>"."</code>.</td>
</tr>
<tr class="even">
<td style=""><code style="">char *mon_thousands_sep</code></td>
<td style="">Thousands separator character for money, e.g.&nbsp;<code>","</code>.</td>
</tr>
<tr class="odd">
<td style=""><code style="">char *mon_grouping</code></td>
<td style="">Grouping description for money (see below).</td>
</tr>
<tr class="even">
<td style=""><code style="">char *positive_sign</code></td>
<td style="">Positive sign for money, e.g.&nbsp;<code>"+"</code> or
<code>""</code>.</td>
</tr>
<tr class="odd">
<td style=""><code style="">char *negative_sign</code></td>
<td style="">Negative sign for money, e.g.&nbsp;<code>"-"</code>.</td>
</tr>
<tr class="even">
<td style=""><code>char *currency_symbol</code></td>
<td style="">Currency symbol, e.g.&nbsp;<code>"$"</code>.</td>
</tr>
<tr class="odd">
<td><code>char frac_digits</code></td>
<td style="">When printing monetary amounts, how many digits to print past the
decimal point, e.g.&nbsp;<code>2</code>.</td>
</tr>
<tr class="even">
<td><code>char p_cs_precedes</code></td>
<td style=""><code>1</code> if the <code>currency_symbol</code> comes before the
value for a non-negative monetary amount, <code>0</code> if after.</td>
</tr>
<tr class="odd">
<td><code>char n_cs_precedes</code></td>
<td style=""><code>1</code> if the <code>currency_symbol</code> comes before the
value for a negative monetary amount, <code>0</code> if after.</td>
</tr>
<tr class="even">
<td><code>char p_sep_by_space</code></td>
<td style="">Determines the separation of the <code>currency symbol</code> from
the value for non-negative amounts (see below).</td>
</tr>
<tr class="odd">
<td><code>char n_sep_by_space</code></td>
<td>Determines the separation of the <code>currency symbol</code> from
the value for negative amounts (see below).</td>
</tr>
<tr class="even">
<td><code>char p_sign_posn</code></td>
<td>Determines the <code>positive_sign</code> position for non-negative
values.</td>
</tr>
<tr class="odd">
<td><code>char p_sign_posn</code></td>
<td>Determines the <code>positive_sign</code> position for negative
values.</td>
</tr>
<tr class="even">
<td><code>char *int_curr_symbol</code></td>
<td>International currency symbol, e.g.&nbsp;<code>"USD "</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_frac_digits</code></td>
<td style="">International value for <code>frac_digits</code>.</td>
</tr>
<tr class="even">
<td><code>char int_p_cs_precedes</code></td>
<td style="">International value for <code>p_cs_precedes</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_n_cs_precedes</code></td>
<td style="">International value for <code>n_cs_precedes</code>.</td>
</tr>
<tr class="even">
<td><code>char int_p_sep_by_space</code></td>
<td style="">International value for <code>p_sep_by_space</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_n_sep_by_space</code></td>
<td style="">International value for <code>n_sep_by_space</code>.</td>
</tr>
<tr class="even">
<td><code>char int_p_sign_posn</code></td>
<td style="">International value for <code>p_sign_posn</code>.</td>
</tr>
<tr class="odd">
<td><code>char int_n_sign_posn</code></td>
<td style="">International value for <code>n_sign_posn</code>.</td>
</tr>
</tbody>
</table>
### 26.2.1 Monetary Digit Grouping

OK, this is a trippy one. `mon_grouping` is a `char*`, so you might be thinking it’s a string. But in this case, no, it’s really an array of `char`s. It should always end either with a `0` or `CHAR_MAX`.

These values describe how to group sets of numbers in currency to the _left_ of the decimal (the whole number part).

For example, we might have:

```
  2   1   0
 --- --- ---
$100,000,000.00
```

These are groups of three. Group 0 (just left of the decimal) has 3 digits. Group 1 (next group to the left) has 3 digits, and the last one also has 3.

So we could describe these groups, from the right (the decimal) to the left with a bunch of integer values representing the group sizes:

```
3 3 3
```

And that would work for values up to $100,000,000.

But what if we had more? We could keep adding `3`s…

```
3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
```

but that’s crazy. Luckily, we can specify `0` to indicate that the previous group size repeats:

```
3 0
```

Which means to repeat every 3. That would handle $100, $1,000, $10,000, $10,000,000, $100,000,000,000, and so on.

You can go legitimately crazy with these to indicate some weird groupings.

For example:

```
4 3 2 1 0
```

would indicate:

```
$1,0,0,0,0,00,000,0000.00
```

One more value that can occur is `CHAR_MAX`. This indicates that no more grouping should occur, and can appear anywhere in the array, including the first value.

```
3 2 CHAR_MAX
```

would indicate:

```
100000000,00,000.00
```

for example.

And simply having `CHAR_MAX` in the first array position would tell you there was to be no grouping at all.

### 26.2.2 Separators and Sign Position

All the `sep_by_space` variants deal with spacing around the currency sign. Valid values are:

  

<table style="">
<colgroup>
<col style="width: 25%">
<col style="width: 75%">
</colgroup>
<thead>
<tr class="header">
<th style="text-align: center;">Value</th>
<th style="">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>0</code></td>
<td style="">No space between currency symbol and value.</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>1</code></td>
<td style="">Separate the currency symbol (and sign, if any) from the value with
a space.</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>2</code></td>
<td style="">Separate the sign symbol from the currency symbol (if adjacent) with
a space, otherwise separate the sign symbol from the value with a
space.</td>
</tr>
</tbody>
</table>
<p style="">The <code style="">sign_posn</code> variants are determined by the following
values:</p>

<table style="">
<thead>
<tr class="header">
<th style="text-align: center;">Value</th>
<th style="">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;"><code>0</code></td>
<td style="">Put parens around the value and the currency symbol.</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>1</code></td>
<td style="">Put the sign string in front of the currency symbol and value.</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>2</code></td>
<td style="">Put the sign string after the currency symbol and value.</td>
</tr>
<tr class="even">
<td style="text-align: center;"><code>3</code></td>
<td style="">Put the sign string directly in front of the currency symbol.</td>
</tr>
<tr class="odd">
<td style="text-align: center;"><code>4</code></td>
<td>Put the sign string directly behind the currency symbol.</td>
</tr>
</tbody>
</table>
### 26.2.3 Example Values

When I get the values on my system, this is what I see (grouping string displayed as individual byte values):

```
mon_decimal_point  = "."
mon_thousands_sep  = ","
mon_grouping       = 3 3 0
positive_sign      = ""
negative_sign      = "-"
currency_symbol    = "$"
frac_digits        = 2
p_cs_precedes      = 1
n_cs_precedes      = 1
p_sep_by_space     = 0
n_sep_by_space     = 0
p_sign_posn        = 1
n_sign_posn        = 1
int_curr_symbol    = "USD "
int_frac_digits    = 2
int_p_cs_precedes  = 1
int_n_cs_precedes  = 1
int_p_sep_by_space = 1
int_n_sep_by_space = 1
int_p_sign_posn    = 1
int_n_sign_posn    = 1
```

## 26.3 Localization Specifics

Notice how we passed the macro `LC_ALL` to `setlocale()` earlier… this hints that there might be some variant that allows you to be more precise about which _parts_ of the locale you’re setting.

Let’s take a look at the values you can see for these:

  
<table>
<colgroup>
<col style="width: 22%">
<col style="width: 77%">
</colgroup>
<thead>
<tr class="header">
<th style="">Macro</th>
<th style="">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style=""><code style="">LC_ALL</code></td>
<td style="">Set all of the following to the given locale.</td>
</tr>
<tr class="even">
<td style=""><code style="">LC_COLLATE</code></td>
<td style="">Controls the behavior of the <code style="">strcoll()</code> and
<code style="">strxfrm()</code> functions.</td>
</tr>
<tr class="odd">
<td style=""><code style="">LC_CTYPE</code></td>
<td style="">Controls the behavior of the character-handling functions<a href="#fn145" class="footnote-ref" id="fnref145" role="doc-noteref"><sup>145</sup></a>.</td>
</tr>
<tr class="even">
<td style=""><code style="">LC_MONETARY</code></td>
<td style="">Controls the values returned by <code style="">localeconv()</code>.</td>
</tr>
<tr class="odd">
<td style=""><code style="">LC_NUMERIC</code></td>
<td style="">Controls the decimal point for the <code style="">printf()</code> family of
functions.</td>
</tr>
<tr class="even">
<td style=""><code style="">LC_TIME</code></td>
<td style="">Controls time formatting of the <code style="">strftime()</code> and
<code>wcsftime()</code> time and date printing functions.</td>
</tr>
</tbody>
</table>

It’s pretty common to see `LC_ALL` being set, but, hey, at least you have options.

Also I should point out that `LC_CTYPE` is one of the biggies because it ties into wide characters, a significant can of worms that we’ll talk about later.