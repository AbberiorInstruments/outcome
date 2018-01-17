+++
title = "Success/Failure"
weight = 40
+++
# Header file `success_failure.hpp`

<a id="standardese-success_failure-hpp" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">namespace</span> <span class="typ dec var fun">outcome_v2_xxx</span>
<span class="pun">{</span>
    <span class="kwd">namespace</span> <span class="typ dec var fun">policy</span>
    <span class="pun">{</span>
        <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
        <span class="kwd">constexpr</span> <span class="kwd">auto</span> <a href="#standardese-outcome_v2_xxx__policy__error_code-T--T---"><span class="typ dec var fun">error_code</span></a><span class="pun">(</span><span class="typ dec var fun">T</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>

        <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
        <span class="kwd">constexpr</span> <span class="kwd">auto</span> <a href="#standardese-outcome_v2_xxx__policy__exception_ptr-T--T---"><span class="typ dec var fun">exception_ptr</span></a><span class="pun">(</span><span class="typ dec var fun">T</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>

        <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Error</span><span class="pun">&gt;</span>
        <span class="kwd">constexpr</span> <span class="kwd">void</span> <a href="#standardese-outcome_v2_xxx__policy__throw_as_system_error_with_payload-Error--Errorconst--"><span class="typ dec var fun">throw_as_system_error_with_payload</span></a><span class="pun">(</span><span class="typ dec var fun">Error</span> <span class="kwd">const</span><span class="pun">&amp;</span> <span class="typ dec var fun">error</span><span class="pun">)</span><span class="pun">;</span>
    <span class="pun">}</span>

    <span class="kwd">namespace</span> <span class="typ dec var fun">trait</span>
    <span class="pun">{</span>
        <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
        <span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__trait__has_error_code-T-"><span class="typ dec var fun">has_error_code</span></a><span class="pun">;</span>

        <span class="typ dec var fun">template</span> <span class="pun">&lt;</span><span class="typ dec var fun">class</span> <span class="kwd">T</span><span class="pun">&gt;</span><span class="typ dec var fun">constexpr</span> <span class="typ dec var fun">bool</span> <span class="kwd">has_error_code_v</span> <span class="pun">=</span> <span class="kwd">has_error_code</span><span class="pun">&lt;</span><span class="kwd">T</span><span class="pun">&gt;</span><span class="pun">::</span><span class="kwd">value</span><span class="pun">;</span>

        <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
        <span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__trait__has_exception_ptr-T-"><span class="typ dec var fun">has_exception_ptr</span></a><span class="pun">;</span>

        <span class="typ dec var fun">template</span> <span class="pun">&lt;</span><span class="typ dec var fun">class</span> <span class="kwd">T</span><span class="pun">&gt;</span><span class="typ dec var fun">constexpr</span> <span class="typ dec var fun">bool</span> <span class="kwd">has_exception_ptr_v</span> <span class="pun">=</span> <span class="kwd">has_exception_ptr</span><span class="pun">&lt;</span><span class="kwd">T</span><span class="pun">&gt;</span><span class="pun">::</span><span class="kwd">value</span><span class="pun">;</span>
    <span class="pun">}</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
    <span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__success_type-T-"><span class="typ dec var fun">success_type</span></a><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="pun">&gt;</span>
    <span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__success_type-T-"><span class="typ dec var fun">success_type</span></a><span class="pun">&lt;</span><span class="typ dec var fun">void</span><span class="pun">&gt;</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-"><span class="typ dec var fun">success_type</span></a><span class="pun">&lt;</span>void<span class="pun">&gt;</span> <a href="#standardese-outcome_v2_xxx__success-T--T---"><span class="typ dec var fun">success</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">noexcept</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-"><span class="typ dec var fun">success_type</span></a><span class="pun">&lt;</span>std::decay_t&lt;T&gt;<span class="pun">&gt;</span> <a href="#standardese-outcome_v2_xxx__success-T--T---"><span class="typ dec var fun">success</span></a><span class="pun">(</span><span class="typ dec var fun">T</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span> <span class="pun">=</span> std::error_code<span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">E</span> <span class="pun">=</span> void<span class="pun">&gt;</span>
    <span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">&gt;</span>
    <span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span><span class="kwd">EC</span><span class="pun">,</span> <span class="typ dec var fun">void</span><span class="pun">&gt;</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">E</span><span class="pun">&gt;</span>
    <span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span><span class="typ dec var fun">void</span><span class="pun">,</span> <span class="kwd">E</span><span class="pun">&gt;</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">&gt;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>std::decay_t&lt;EC&gt;<span class="pun">&gt;</span> <a href="#standardese-outcome_v2_xxx__failure-EC--EC---"><span class="typ dec var fun">failure</span></a><span class="pun">(</span><span class="typ dec var fun">EC</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">E</span><span class="pun">&gt;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>std::decay_t&lt;EC&gt;, std::decay_t&lt;E&gt;<span class="pun">&gt;</span> <a href="#standardese-outcome_v2_xxx__failure-EC-E--EC---E---"><span class="typ dec var fun">failure</span></a><span class="pun">(</span><span class="typ dec var fun">EC</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">,</span> <span class="typ dec var fun">E</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">w</span><span class="pun">)</span><span class="pun">;</span>
<span class="pun">}</span>
</code></pre>

<a id="standardese-outcome_v2_xxx" style="display: none"></a>

<a id="standardese-outcome_v2_xxx__policy" style="display: none"></a>

### Function `outcome_v2_xxx::policy::error_code`

<a id="standardese-outcome_v2_xxx__policy__error_code-T--T---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <span class="kwd">auto</span> <span class="typ dec var fun">error_code</span><span class="pun">(</span><span class="typ dec var fun">T</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Used by policies to extract a `std::error_code` from some input `T` via ADL discovery of some `make_error_code(T)` function.

-----

### Function `outcome_v2_xxx::policy::exception_ptr`

<a id="standardese-outcome_v2_xxx__policy__exception_ptr-T--T---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <span class="kwd">auto</span> <span class="typ dec var fun">exception_ptr</span><span class="pun">(</span><span class="typ dec var fun">T</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Used by policies to extract a `std::exception_ptr` from some input `T` via ADL discovery of some `make_exception_ptr(T)` function.

-----

### Function `outcome_v2_xxx::policy::throw_as_system_error_with_payload`

<a id="standardese-outcome_v2_xxx__policy__throw_as_system_error_with_payload-Error--Errorconst--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">Error</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <span class="kwd">void</span> <span class="typ dec var fun">throw_as_system_error_with_payload</span><span class="pun">(</span><span class="typ dec var fun">Error</span> <span class="kwd">const</span><span class="pun">&amp;</span> <span class="typ dec var fun">error</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Override to define what the policies which throw a system error with payload ought to do for some particular `result.error()`.

-----

<a id="standardese-outcome_v2_xxx__trait" style="display: none"></a>

### Struct `outcome_v2_xxx::trait::has_error_code`

<a id="standardese-outcome_v2_xxx__trait__has_error_code-T-" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
<span class="kwd">struct</span> <span class="typ dec var fun">has_error_code</span>
<span class="pun">{</span>
<span class="pun">};</span>
</code></pre>

Trait for whether a free function `make_error_code(T)` returning a `std::error_code` exists or not.

Also returns true if `std::error_code` is convertible from T.

-----

### Unexposed entity `outcome_v2_xxx::trait::has_error_code_v`

<a id="standardese-outcome_v2_xxx__trait__has_error_code_v" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="typ dec var fun">template</span> <span class="pun">&lt;</span><span class="typ dec var fun">class</span> <span class="kwd">T</span><span class="pun">&gt;</span><span class="typ dec var fun">constexpr</span> <span class="typ dec var fun">bool</span> <span class="kwd">has_error_code_v</span> <span class="pun">=</span> <span class="kwd">has_error_code</span><span class="pun">&lt;</span><span class="kwd">T</span><span class="pun">&gt;</span><span class="pun">::</span><span class="kwd">value</span><span class="pun">;</span>
</code></pre>

Trait for whether a free function `make_error_code(T)` returning a `std::error_code` exists or not.

Also returns true if `std::error_code` is convertible from T.

-----

### Struct `outcome_v2_xxx::trait::has_exception_ptr`

<a id="standardese-outcome_v2_xxx__trait__has_exception_ptr-T-" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
<span class="kwd">struct</span> <span class="typ dec var fun">has_exception_ptr</span>
<span class="pun">{</span>
<span class="pun">};</span>
</code></pre>

Trait for whether a free function `make_exception_ptr(T)` returning a `std::exception_ptr` exists or not.

Also returns true if `std::exception_ptr` is convertible from T.

-----

### Unexposed entity `outcome_v2_xxx::trait::has_exception_ptr_v`

<a id="standardese-outcome_v2_xxx__trait__has_exception_ptr_v" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="typ dec var fun">template</span> <span class="pun">&lt;</span><span class="typ dec var fun">class</span> <span class="kwd">T</span><span class="pun">&gt;</span><span class="typ dec var fun">constexpr</span> <span class="typ dec var fun">bool</span> <span class="kwd">has_exception_ptr_v</span> <span class="pun">=</span> <span class="kwd">has_exception_ptr</span><span class="pun">&lt;</span><span class="kwd">T</span><span class="pun">&gt;</span><span class="pun">::</span><span class="kwd">value</span><span class="pun">;</span>
</code></pre>

Trait for whether a free function `make_exception_ptr(T)` returning a `std::exception_ptr` exists or not.

Also returns true if `std::exception_ptr` is convertible from T.

-----

### Struct `outcome_v2_xxx::success_type`

<a id="standardese-outcome_v2_xxx__success_type-T-" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
<span class="kwd">struct</span> <span class="typ dec var fun">success_type</span>
<span class="pun">{</span>
    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a> <span class="pun">=</span> <span class="typ dec var fun">T</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__success_type--"><span class="typ dec var fun">success_type</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__success_type-constsuccess_type-T---"><span class="typ dec var fun">success_type</span></a><span class="pun">(</span>const success_type&lt;T&gt;<span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__success_type-success_type-T----"><span class="typ dec var fun">success_type</span></a><span class="pun">(</span>success_type&lt;T&gt;<span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">U</span><span class="pun">&gt;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__success_type-U--U---"><span class="typ dec var fun">success_type</span></a><span class="pun">(</span><span class="typ dec var fun">U</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>

    &#x2F;&#x2F;=== value ===&#x2F;&#x2F;
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value---"><span class="typ dec var fun">value</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value---"><span class="typ dec var fun">value</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value---"><span class="typ dec var fun">value</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value---"><span class="typ dec var fun">value</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
<span class="pun">};</span>
</code></pre>

Type sugar for implicitly constructing a `result<>` with a successful state.

### Type alias `outcome_v2_xxx::success_type::value_type`

<a id="standardese-outcome_v2_xxx__success_type-T-__value_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">value_type</span> <span class="pun">=</span> <span class="typ dec var fun">T</span><span class="pun">;</span>
</code></pre>

The type of the successful state.

-----

### Constructor `outcome_v2_xxx::success_type::success_type`

<a id="standardese-outcome_v2_xxx__success_type-T-__success_type--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">success_type</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Default constructor

-----

### Constructor `outcome_v2_xxx::success_type::success_type`

<a id="standardese-outcome_v2_xxx__success_type-T-__success_type-constsuccess_type-T---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">success_type</span><span class="pun">(</span>const success_type&lt;T&gt;<span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Copy constructor

-----

### Constructor `outcome_v2_xxx::success_type::success_type`

<a id="standardese-outcome_v2_xxx__success_type-T-__success_type-success_type-T----" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">success_type</span><span class="pun">(</span>success_type&lt;T&gt;<span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Move constructor

-----

### Constructor `outcome_v2_xxx::success_type::success_type`

<a id="standardese-outcome_v2_xxx__success_type-T-__success_type-U--U---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">U</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <span class="typ dec var fun">success_type</span><span class="pun">(</span><span class="typ dec var fun">U</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Initialising constructor

-----

### Function `outcome_v2_xxx::success_type::value`

<a id="standardese-outcome_v2_xxx__success_type-T-__value---" style="display: none"></a>

<pre><code class="standardese-language-cpp">(1) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">value</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>

(2) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">value</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>

(3) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">value</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>

(4) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-__value_type"><span class="typ dec var fun">value_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">value</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
</code></pre>

Access value.

*Returns:* Reference to the held `value_type` according to overload.

-----

-----

### Struct `outcome_v2_xxx::success_type`

<a id="standardese-outcome_v2_xxx__success_type-" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="pun">&gt;</span>
<span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__success_type-T-"><span class="typ dec var fun">success_type</span></a><span class="pun">&lt;</span><span class="typ dec var fun">void</span><span class="pun">&gt;</span>
<span class="pun">{</span>
    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__success_type-__value_type"><span class="typ dec var fun">value_type</span></a> <span class="pun">=</span> <span class="kwd">void</span><span class="pun">;</span>
<span class="pun">};</span>
</code></pre>

Type sugar for implicitly constructing a `result<>` with a successful state.

### Type alias `outcome_v2_xxx::success_type::value_type`

<a id="standardese-outcome_v2_xxx__success_type-__value_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">value_type</span> <span class="pun">=</span> <span class="kwd">void</span><span class="pun">;</span>
</code></pre>

The type of the successful state.

-----

-----

### Function `outcome_v2_xxx::success`

<a id="standardese-outcome_v2_xxx__success--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-"><span class="typ dec var fun">success_type</span></a><span class="pun">&lt;</span>void<span class="pun">&gt;</span> <span class="typ dec var fun">success</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">noexcept</span><span class="pun">;</span>
</code></pre>

Returns type sugar for implicitly constructing a `result<T>` with a successful state, default constructing `T` if necessary.

-----

### Function `outcome_v2_xxx::success`

<a id="standardese-outcome_v2_xxx__success-T--T---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">T</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__success_type-T-"><span class="typ dec var fun">success_type</span></a><span class="pun">&lt;</span>std::decay_t&lt;T&gt;<span class="pun">&gt;</span> <span class="typ dec var fun">success</span><span class="pun">(</span><span class="typ dec var fun">T</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Returns type sugar for implicitly constructing a `result<T>` with a successful state.

*Effects:* Copies or moves the successful state supplied into the returned type sugar.

-----

### Struct `outcome_v2_xxx::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span> <span class="pun">=</span> std::error_code<span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">E</span> <span class="pun">=</span> void<span class="pun">&gt;</span>
<span class="kwd">struct</span> <span class="typ dec var fun">failure_type</span>
<span class="pun">{</span>
    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a> <span class="pun">=</span> <span class="typ dec var fun">EC</span><span class="pun">;</span>

    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a> <span class="pun">=</span> <span class="typ dec var fun">E</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type--"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type-constfailure_type-EC-E---"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span>const failure_type&lt;EC, E&gt;<span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type-failure_type-EC-E----"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span>failure_type&lt;EC, E&gt;<span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">U</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">V</span><span class="pun">&gt;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type-U-V--U---V---"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><span class="typ dec var fun">U</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">u</span><span class="pun">,</span> <span class="typ dec var fun">V</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>

    &#x2F;&#x2F;=== error ===&#x2F;&#x2F;
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>

    &#x2F;&#x2F;=== exception ===&#x2F;&#x2F;
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
<span class="pun">};</span>
</code></pre>

Type sugar for implicitly constructing a `result<>` with a failure state of error code and exception.

### Type alias `outcome_v2_xxx::failure_type::error_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__error_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">error_type</span> <span class="pun">=</span> <span class="typ dec var fun">EC</span><span class="pun">;</span>
</code></pre>

The type of the error code

-----

### Type alias `outcome_v2_xxx::failure_type::exception_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">exception_type</span> <span class="pun">=</span> <span class="typ dec var fun">E</span><span class="pun">;</span>
</code></pre>

The type of the exception

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Default constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type-constfailure_type-EC-E---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span>const failure_type&lt;EC, E&gt;<span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Copy constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type-failure_type-EC-E----" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span>failure_type&lt;EC, E&gt;<span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Move constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__failure_type-U-V--U---V---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">U</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">V</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><span class="typ dec var fun">U</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">u</span><span class="pun">,</span> <span class="typ dec var fun">V</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Initialising constructor

-----

### Function `outcome_v2_xxx::failure_type::error`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__error---" style="display: none"></a>

<pre><code class="standardese-language-cpp">(1) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>

(2) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>

(3) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>

(4) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
</code></pre>

Access error.

*Returns:* Reference to the held `error_type` according to overload.

-----

### Function `outcome_v2_xxx::failure_type::exception`

<a id="standardese-outcome_v2_xxx__failure_type-EC-E-__exception---" style="display: none"></a>

<pre><code class="standardese-language-cpp">(1) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>

(2) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>

(3) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>

(4) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
</code></pre>

Access exception.

*Returns:* Reference to the held `exception_type` according to overload.

-----

-----

### Struct `outcome_v2_xxx::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">&gt;</span>
<span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span><span class="kwd">EC</span><span class="pun">,</span> <span class="typ dec var fun">void</span><span class="pun">&gt;</span>
<span class="pun">{</span>
    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a> <span class="pun">=</span> <span class="typ dec var fun">EC</span><span class="pun">;</span>

    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__exception_type"><span class="typ dec var fun">exception_type</span></a> <span class="pun">=</span> <span class="kwd">void</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__failure_type--"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__failure_type-failure_type-type-parameter-0-0-void-const--"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>type-parameter-0-0, void<span class="pun">&gt;</span> <span class="kwd">const</span><span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__failure_type-failure_type-type-parameter-0-0-void----"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>type-parameter-0-0, void<span class="pun">&gt;</span><span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">U</span><span class="pun">&gt;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__failure_type-U--U---"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><span class="typ dec var fun">U</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">u</span><span class="pun">)</span><span class="pun">;</span>

    &#x2F;&#x2F;=== error2 ===&#x2F;&#x2F;
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error---"><span class="typ dec var fun">error</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
<span class="pun">};</span>
</code></pre>

Type sugar for implicitly constructing a `result<>` with a failure state of error code.

### Type alias `outcome_v2_xxx::failure_type::error_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-__error_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">error_type</span> <span class="pun">=</span> <span class="typ dec var fun">EC</span><span class="pun">;</span>
</code></pre>

The type of the error code

-----

### Type alias `outcome_v2_xxx::failure_type::exception_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-__exception_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">exception_type</span> <span class="pun">=</span> <span class="kwd">void</span><span class="pun">;</span>
</code></pre>

The type of the exception

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-__failure_type--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Default constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-__failure_type-failure_type-type-parameter-0-0-void-const--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>type-parameter-0-0, void<span class="pun">&gt;</span> <span class="kwd">const</span><span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Copy constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-__failure_type-failure_type-type-parameter-0-0-void----" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>type-parameter-0-0, void<span class="pun">&gt;</span><span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Move constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-EC-__failure_type-U--U---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">U</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><span class="typ dec var fun">U</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">u</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Initialising constructor

-----

### Function `outcome_v2_xxx::failure_type::error`

<a id="standardese-outcome_v2_xxx__failure_type-EC-__error---" style="display: none"></a>

<pre><code class="standardese-language-cpp">(1) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>

(2) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>

(3) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>

(4) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-__error_type"><span class="typ dec var fun">error_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">error</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
</code></pre>

Access error.

*Returns:* Reference to the held `error_type` according to overload.

-----

-----

### Struct `outcome_v2_xxx::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-E-" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">E</span><span class="pun">&gt;</span>
<span class="kwd">struct</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span><span class="typ dec var fun">void</span><span class="pun">,</span> <span class="kwd">E</span><span class="pun">&gt;</span>
<span class="pun">{</span>
    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__error_type"><span class="typ dec var fun">error_type</span></a> <span class="pun">=</span> <span class="kwd">void</span><span class="pun">;</span>

    <span class="kwd">using</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a> <span class="pun">=</span> <span class="typ dec var fun">E</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__failure_type--"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__failure_type-failure_type-void-type-parameter-0-0-const--"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>void, type-parameter-0-0<span class="pun">&gt;</span> <span class="kwd">const</span><span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__failure_type-failure_type-void-type-parameter-0-0----"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>void, type-parameter-0-0<span class="pun">&gt;</span><span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>

    <span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">V</span><span class="pun">&gt;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__failure_type-V--V---"><span class="typ dec var fun">failure_type</span></a><span class="pun">(</span><span class="typ dec var fun">V</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>

    &#x2F;&#x2F;=== exception2 ===&#x2F;&#x2F;
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
    <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception---"><span class="typ dec var fun">exception</span></a><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
<span class="pun">};</span>
</code></pre>

Type sugar for implicitly constructing a `result<>` with a failure state of exception.

### Type alias `outcome_v2_xxx::failure_type::error_type`

<a id="standardese-outcome_v2_xxx__failure_type-E-__error_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">error_type</span> <span class="pun">=</span> <span class="kwd">void</span><span class="pun">;</span>
</code></pre>

The type of the error code

-----

### Type alias `outcome_v2_xxx::failure_type::exception_type`

<a id="standardese-outcome_v2_xxx__failure_type-E-__exception_type" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">using</span> <span class="typ dec var fun">exception_type</span> <span class="pun">=</span> <span class="typ dec var fun">E</span><span class="pun">;</span>
</code></pre>

The type of the exception

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-E-__failure_type--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Default constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-E-__failure_type-failure_type-void-type-parameter-0-0-const--" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>void, type-parameter-0-0<span class="pun">&gt;</span> <span class="kwd">const</span><span class="pun">&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Copy constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-E-__failure_type-failure_type-void-type-parameter-0-0----" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>void, type-parameter-0-0<span class="pun">&gt;</span><span class="pun">&amp;&amp;</span><span class="pun">)</span> <span class="pun">=</span> <span class="kwd">default</span><span class="pun">;</span>
</code></pre>

Move constructor

-----

### Constructor `outcome_v2_xxx::failure_type::failure_type`

<a id="standardese-outcome_v2_xxx__failure_type-E-__failure_type-V--V---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">V</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <span class="typ dec var fun">failure_type</span><span class="pun">(</span><span class="typ dec var fun">V</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Initialising constructor

-----

### Function `outcome_v2_xxx::failure_type::exception`

<a id="standardese-outcome_v2_xxx__failure_type-E-__exception---" style="display: none"></a>

<pre><code class="standardese-language-cpp">(1) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;</span><span class="pun">;</span>

(2) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;</span><span class="pun">;</span>

(3) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>

(4) <span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-E-__exception_type"><span class="typ dec var fun">exception_type</span></a><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">exception</span><span class="pun">(</span><span class="pun">)</span> <span class="kwd">const</span> <span class="pun">&amp;&amp;</span><span class="pun">;</span>
</code></pre>

Access exception.

*Returns:* Reference to the held `exception_type` according to overload.

-----

-----

### Function `outcome_v2_xxx::failure`

<a id="standardese-outcome_v2_xxx__failure-EC--EC---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>std::decay_t&lt;EC&gt;<span class="pun">&gt;</span> <span class="typ dec var fun">failure</span><span class="pun">(</span><span class="typ dec var fun">EC</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Returns type sugar for implicitly constructing a `result<T>` with a failure state.

*Effects:* Copies or moves the failure state supplied into the returned type sugar.

-----

### Function `outcome_v2_xxx::failure`

<a id="standardese-outcome_v2_xxx__failure-EC-E--EC---E---" style="display: none"></a>

<pre><code class="standardese-language-cpp"><span class="kwd">template</span> <span class="pun">&lt;</span><span class="kwd">class</span> <span class="typ dec var fun">EC</span><span class="pun">,</span> <span class="kwd">class</span> <span class="typ dec var fun">E</span><span class="pun">&gt;</span>
<span class="kwd">constexpr</span> <a href="#standardese-outcome_v2_xxx__failure_type-EC-E-"><span class="typ dec var fun">failure_type</span></a><span class="pun">&lt;</span>std::decay_t&lt;EC&gt;, std::decay_t&lt;E&gt;<span class="pun">&gt;</span> <span class="typ dec var fun">failure</span><span class="pun">(</span><span class="typ dec var fun">EC</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">v</span><span class="pun">,</span> <span class="typ dec var fun">E</span><span class="pun">&amp;&amp;</span> <span class="typ dec var fun">w</span><span class="pun">)</span><span class="pun">;</span>
</code></pre>

Returns type sugar for implicitly constructing a `result<T>` with a failure state.

*Effects:* Copies or moves the failure state supplied into the returned type sugar.

-----