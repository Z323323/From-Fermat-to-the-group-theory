# Fermat's Little Theorem proof using multinomial theorem

Ahhh these mathematicians...<br>
We need to prove $a^{p} \equiv a \mod p$ with $p$ prime and $p > a$.

## Multinomial theorem
<p>
  Since this is quite difficult to understand I'm simplifying as much as possible (it's almost the same as Wiki by the way).
  For any positive integer $m$ and non-negative integer $n$ this theorem describes how a sum of $m$ terms expands when raised to the nth power:

  $(x_{1} + x_{2} + \dots + x_{m})^{n} = \sum_{k_{1} + \dots + k_{m} = n} (\frac{n!}{k_{1}! \dots k_{m}!}) x_{1}^{k_{1}} x_{2}^{k_{2}} \dots x_{m}^{k_{m}}$

  This is a strange summation because of: $k_{1} + \dots + k_{m} = n$. There's no need to explain the meaning but it's somehow strange because it builds a combination of $k_{1} \dots k_{m}$ implicitly, see below.<br>

</p>

## Lightning fast example

<p>
  $(a + b + c)^{3} = a^{3} + b^{3} + c^{3} + 3a^{2}b + 3a^{2}c + 3b^{2}a + 3b^{2}c + 3c^{2}a + 3c^{2}b + 6abc$

The implicit combination is:<br>

  1. $(3, 0, 0)$
  2. $(0, 3, 0)$
  3. $(0, 0, 3)$
  4. $(2, 1, 0)$
  5. $(2, 0, 1)$
  6. $(1, 2, 0)$
  7. $(0, 2, 1)$
  8. $(1, 0, 2)$
  9. $(0, 1, 2)$
  10. $(1, 1, 1)$

Combinations are not an easy topic, here the quest. is: how many sets of $3$ elements can we build with 4 elements ($0, 1, 2, 3$) without breaking $k_{1} + \dots + k_{m} = n$ ? Not so easy. Since $3$ is enough to saturate it we'll have $n$ sets with it, and $1$ set with $1s$. Then $(2, 1, 0)$ form: <br>

$3! = 6$ combinations of 3 elements and <br>
$6 + n + 1 = 10$ solutions.

But there's another better formed solution for sure.

Now what's actually crazy about this theorem is that it correlates these combinations with powers and coeffs of every term of any power (ahhh these mathematicians...).<br>

$(\frac{n!}{k_{1}! \dots k_{m}!})$ 

This is the coeff. of every term, if you try to calculate it you will find that is correct. Now for this example is quite fast to check, but it actually works for every power and any number of $xs \dots$

</p>

## Back to Fermat

<p>
  We can represent $a^{p}$ as $(1 + 1 + \dots + 1)^{p}$ and apply the multinomial theorem, this will build some sets with $a$ $k_{1} \dots k_{a}$.<br>
  We can immediately notice $a$ sets of $(p_{1}, 0_{2}, 0_{3}, \dots, 0_{a})$ like terms (for which the coeff. will be $1$).<br>
  All other terms will need to 'produce' $p$ too as sum of $k_{1} \dots k_{a}$, then:
  $(\frac{n!}{k_{1}! \dots k_{m}!})$ will have $k_{1}! \dots k_{m}!$ composed only by factors which are coprime with $p$ since it's prime and $p > k_{1 \dots m}!$. This means: <br>
  $(\frac{n!}{k_{1}! \dots k_{m}!}) \equiv 0 \mod p$

  and:

  $(\frac{n!}{k_{1}! \dots k_{m}!}) \equiv 1 \mod p$ 

  in every other case.

  Since 'every other case' are the cases mentioned initially and there are $a$ of those. We will end up having something like:<br>

  calling $C_{1 \dots nCombs}$ the coeffs of the multinomial theorem, and $z_{1 \dots nCombs}$ the products of $x_{1 \dots a}^{k_1 \dots a} = 1$:

  $a^{p} = C_{1}z_{1} + C_{2}z_{2} + \dots + C_{nCombs}z_{nCombs}$

  will have $a$ $C_{?}z_{?} \equiv 1 \mod p$ and $nCombs - a$ $C_{?}z_{?} \equiv 0 \mod p$ then:<br>

  $a^{p} = (C_{1}z_{1} + C_{2}z_{2} + \dots + C_{nCombs}z_{nCombs}) \equiv a \mod p$
  
  which proves the theorem.

</p>

## $a^{p - 1} \equiv 1 \mod p$ case proof background

### Cancellation law
<p>
  If $u, x, y$ are integers and $u$ is coprime with a prime $p$ then if:<br>

  $ux \equiv uy \mod p$
  
  -> $x \equiv y \mod p$

  because if:

   $ux \equiv uy \mod p$ -> $p | u(x - y)$

   and since $u$ is coprime with $p$:

   $p | (x - y)$ -> $x \equiv y \mod p$

   Note the first 'if' statement: $ux \equiv uy \mod p$ is the starting point; the viceversa is not true. Infact this congruence forces $u$ to be big enough to restart the 'cycle' of $p$ otherwise it clearly wouldn't make sense. Also I guess that there's some rule on how many 'cycles', because even here is quite clear that if $x > y$, $u$ will make $x$ to restart the 'cycle' more often. There must be some 'overlapping' rule which I guess it coincides with the Fermat's Little Theorem but for the moment we are good with this result.

</p>

### Rearrangement property

<p>
  $a, 2a, 3a, \dots, (p - 1)a \mod p$

  becomes a 'rearrangement' of:
  
  $1, 2, 3, \dots, (p - 1)$

  This one could look exactly like the former but it's not. This property does not care at all about congruences equalities; it just states that the first formula will be 'mapped' into that sequence of values. 'rearrangement' means that we don't care about which congruence will be mapped into which value, we just want to prove that all those values will be mapped. Nonetheless we will use the 'cancellation law' to prove it (:'D).
The fact that no congruence will 'produce' $0$ is trivial. Why all those values will be distinct is the real question.
<br>
We take the sequence of congruences:

$a, 2a, 3a, \dots, (p - 1)a \mod p$

and represent each pair as:

$ka \equiv ma \mod p$

From the 'cancellation law' we know that since $a$ is coprime with $p$:

$ka \equiv ma \mod p$

-> $k \equiv m \mod p$

but this is true only if $k = m$, and since this is not true then every $ka \equiv ma \mod p$ pair must produce a different remainder, and since the result set is: $\\{1, 2, 3 \dots, (p - 1)\\}$ then the property is proved.
  
</p>
