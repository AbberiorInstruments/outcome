+++
title = "exception_ptr rethrow (Outcome)"
slug = "doc_outcome_exception_ptr_rethrow.md"
weight = 30
+++

# Header file `outcome_exception_ptr_rethrow.hpp`

<a id="standardese-outcome_exception_ptr_rethrow.hpp"/>

<pre><code class="standardese-language-cpp"><span class="pre">#include</span> <span class="pre">&quot;</span><span class="typ dec var fun">result_exception_ptr_rethrow.hpp</span><span class="pre">&quot;</span>

<span class="kwd">namespace</span> <span class="typ dec var fun">outcome_v2_xxx</span>
<span class="pun">{</span>
    <span class="kwd">namespace</span> <span class="typ dec var fun">policy</span>
    <span class="pun">{</span>
        <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">E</span><span class="pun">&gt;</span>
        <span class="kwd">struct</span> <a href="doc_outcome_exception_ptr_rethrow.md#standardese-outcome_v2_xxx::policy::exception_ptr_rethrow%3CT,EC,E%3E"><span class="typ dec var fun">exception_ptr_rethrow</span></a><span class="pun">;</span>
    <span class="pun">}</span>
<span class="pun">}</span>
</code></pre>

<a id="standardese-outcome_v2_xxx"/>

<a id="standardese-outcome_v2_xxx::policy"/>

### Struct `exception_ptr_rethrow`

<a id="standardese-outcome_v2_xxx::policy::exception_ptr_rethrow<T,EC,E>"/>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">E</span><span class="pun">&gt;</span>
<span class="kwd">struct</span> <span class="typ dec var fun">exception_ptr_rethrow</span>
<span class="pun">:</span> <span class="typ dec var fun">detail::base</span>
<span class="pun">{</span>
    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Impl</span><span class="pun">&gt;</span>
    <span class="kwd">static</span> <span class="kwd">constexpr</span> <span class="kwd">void</span> <a href="doc_outcome_exception_ptr_rethrow.md#standardese-outcome_v2_xxx::policy::exception_ptr_rethrow%3CT,EC,E%3E::wide_value_check%3CImpl%3E(Impl&amp;&amp;)"><span class="typ dec var fun">wide_value_check</span></a><span class="pun">(</span><span class="typ dec var fun">Impl</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">self</span><span class="pun">)</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Impl</span><span class="pun">&gt;</span>
    <span class="kwd">static</span> <span class="kwd">constexpr</span> <span class="kwd">void</span> <a href="doc_outcome_exception_ptr_rethrow.md#standardese-outcome_v2_xxx::policy::exception_ptr_rethrow%3CT,EC,E%3E::wide_error_check%3CImpl%3E(Impl&amp;&amp;)"><span class="typ dec var fun">wide_error_check</span></a><span class="pun">(</span><span class="typ dec var fun">Impl</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">self</span><span class="pun">)</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Impl</span><span class="pun">&gt;</span>
    <span class="kwd">static</span> <span class="kwd">constexpr</span> <span class="kwd">void</span> <a href="doc_outcome_exception_ptr_rethrow.md#standardese-outcome_v2_xxx::policy::exception_ptr_rethrow%3CT,EC,E%3E::wide_exception_check%3CImpl%3E(Impl&amp;&amp;)"><span class="typ dec var fun">wide_exception_check</span></a><span class="pun">(</span><span class="typ dec var fun">Impl</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">self</span><span class="pun">)</span><span class="pun">;</span>
<span class="pun">};</span>
</code></pre>

Policy interpreting `EC` or `E` as a type for which `trait::has_exception_ptr_v<EC|E>` is true.

Any wide attempt to access the successful state where there is none causes: `std::rethrow_exception(policy::exception_ptr(.error()|.exception()))` appropriately.

### Function `wide_value_check`

<a id="standardese-outcome_v2_xxx::policy::exception_ptr_rethrow<T,EC,E>::wide_value_check<Impl>(Impl&&)"/>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Impl</span><span class="pun">&gt;</span>
<span class="kwd">static</span> <span class="kwd">constexpr</span> <span class="kwd">void</span> <span class="typ dec var fun">wide_value_check</span><span class="pun">(</span><span class="typ dec var fun">Impl</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">self</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Performs a wide check of state, used in the value() functions

*Effects:* If outcome does not have a value, if it has an exception it rethrows that exception via `std::rethrow_exception()`, if it has an error it rethrows that error via `std::rethrow_exception()`, else it throws `bad_outcome_access`.

-----

### Function `wide_error_check`

<a id="standardese-outcome_v2_xxx::policy::exception_ptr_rethrow<T,EC,E>::wide_error_check<Impl>(Impl&&)"/>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Impl</span><span class="pun">&gt;</span>
<span class="kwd">static</span> <span class="kwd">constexpr</span> <span class="kwd">void</span> <span class="typ dec var fun">wide_error_check</span><span class="pun">(</span><span class="typ dec var fun">Impl</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">self</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Performs a wide check of state, used in the error() functions

*Effects:* If outcome does not have an error, it throws `bad_outcome_access`.

-----

### Function `wide_exception_check`

<a id="standardese-outcome_v2_xxx::policy::exception_ptr_rethrow<T,EC,E>::wide_exception_check<Impl>(Impl&&)"/>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Impl</span><span class="pun">&gt;</span>
<span class="kwd">static</span> <span class="kwd">constexpr</span> <span class="kwd">void</span> <span class="typ dec var fun">wide_exception_check</span><span class="pun">(</span><span class="typ dec var fun">Impl</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">self</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Performs a wide check of state, used in the exception() functions

*Effects:* If result does not have an exception, it throws `bad_outcome_access`.

-----

-----