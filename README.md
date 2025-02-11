# From Fermat's Little Theorem to the group theory

## $a^{p - 1} \equiv 1 \mod p$ and $a^{k(p - 1)} \equiv 1 \mod p$ proofs background

### Cancellation law

<p>
  
  If $u, x, y$ are integers and $u$ is coprime with a prime $p$, then if

  $ux \equiv uy \mod p$<br>
  $->$<br>
  $x \equiv y \mod p$

  because if

   $ux \equiv uy \mod p$<br>
   $->$<br>
   $p | ux - uy$<br>
   $->$<br>
   $p | u(x - y)$

   and since $u$ is coprime with $p$

   $p | (x - y)$<br>
   $->$<br>
   $x \equiv y \mod p$
   
</p>

### Rearrangement property

<p>
  
$a$ and $p$ are coprimes, $p$ is prime, then
  
  $a, 2a, 3a, \dots, (p - 1)a (\mod p)$

  becomes a 'rearrangement' of
  
  $1, 2, 3, \dots, (p - 1)$

  This one could look exactly like the former but it's not. This property does not care at all about congruences equalities; it just states that the first formula will be 'mapped' into that sequence of values. 'rearrangement' means that we don't care about which congruence will be mapped into which value, we just want to prove that all those values will be mapped. Nonetheless we will use the **cancellation law** to prove it (:'D). The fact that no congruence will 'produce' $0$ is trivial. Why all those values will be distinct is the real question. We take the sequence of congruences

$a, 2a, 3a, \dots, (p - 1)a (\mod p)$

and represent each pair as

$ka \equiv ma \mod p$

From the **cancellation law** we know that since $a$ is coprime with $p$

$ka \equiv ma \mod p$<br>
$->$<br>
$k \equiv m \mod p$<br>

but this is true only if $k = m$, and since this is not true then every $ka \equiv ma \mod p$ pair must produce a different remainder, and since the result set is $\\{1, 2, 3 \dots, (p - 1)\\}$ then the property is proved.

</p>

### Multiplication property

<p>
  
  $ab \mod p = (a \mod p)(b \mod p )(\mod p)$
  
  $a \equiv x \mod p$<br>
  $->$<br> 
  $a = zp + x$<br>
  
  $b \equiv y \mod p$<br>
  $->$<br>
  $b = kp + y$<br>
  
  with $z, k \geq 0$

  $(a \mod p)(b \mod p )(\mod p)$<br>
  $->$<br>
  $(zp + x)(kp + y)(\mod p)$<br>
  $zpkp + zpy + xkp + xy (\mod p)$<br>
  $xy \mod p$ _

  hence $ab \mod p = (a \mod p)(b \mod p )(\mod p)$.
  
</p>

## $a^{p - 1} \equiv 1 \mod p$ proof

<p>
  
  This proof has been discovered by James Ivory and Dirichlet.

  Recalling the **rearrangement property** and the **multiplication property** we can write

  $a \cdot 2a \cdot 3a \cdot \dots \cdot (p - 1)a \equiv 1 \cdot 2 \cdot 3 \cdot \dots \cdot (p - 1) \mod p$

  Now we can collect every term.

  $a^{p - 1}(p - 1)! \equiv (p - 1)! \mod p$

  We can think at this formula as

  $a^{p - 1}(Z) \equiv 1(Z) \mod p$

  where $Z$ is coprime with $p$, then, applying the **cancellation law**

  $a^{p - 1} \equiv 1 \mod p$

  which proves $a^{p - 1} \equiv 1 \mod p$.
  
  </p>

## $a^{k(p - 1)} \equiv 1 \mod p$ proof

<p>
  
  Now we can prove the corollary, which is really important.

  $a^{k(p - 1)} \equiv 1 \mod p$

  The **rearrangement** holds since if $a$ is coprime with $p$ then $a^{k}$ will be coprime too for any $k \in N > 0$.

  $a^{k} \cdot 2a^{k} \cdot 3a^{k} \cdot \dots \cdot (p - 1)a^{k} \equiv 1 \cdot 2 \cdot 3 \cdot \dots \cdot (p - 1) \mod p$

  Collecting and applying the **cancellation law** produces

  $a^{k(p - 1)} \equiv 1 \mod p$
  
</p>

## Using the same reasoning to prove Euler's Theorem: $a^{\phi(n)} \equiv 1 \mod n$

<p>
  
  We call $z_{1} \dots z_{\phi(n)}$ the integers which are coprime with $n$, then using the **rearrangement property** (which holds because $a$ and $n$ are coprimes and because $z_{1} \dots z_{\phi(n)}$ are pairwise $\neq$) and the **multiplication property** we can write

  $z_{1}a \cdot z_{2}a \cdot z_{3}a \cdot \dots \cdot z_{\phi(n)}a \equiv z_{1} \cdot z_{2} \cdot z_{3} \cdot \dots \cdot z_{\phi(n)} \mod n$

  Collecting the terms produces
  
  $a^{\phi(n)} Z \equiv (1)Z \mod n$

  and using the **cancellation law** (holds since $z_{1} \dots z_{\phi(n)}$ are coprimes with $n$) we get

  $a^{\phi(n)} \equiv 1 \mod n$
  
</p>

## $a^{k(\phi(n))} \equiv 1 \mod n$ corollary proof

<p>
  
  Same reasoning made for the former. We can write

  $z_{1}a^{k} \cdot z_{2}a^{k} \cdot z_{3}a^{k} \cdot \dots \cdot z_{\phi(n)}a^{k} \equiv z_{1} \cdot z_{2} \cdot z_{3} \cdot \dots \cdot z_{\phi(n)} \mod n$

  Collecting and applying the **cancellation law** we obtain

  $a^{k(\phi(n))} \equiv 1 \mod n$
  
</p>

## $a^{k(\phi(n)) + 1} \equiv a \mod n$ corollary proof

<p>
  
  We can rewrite the formula above as

  $a^{k(\phi(n))}a \equiv a \mod n$

  Since we proved $a^{k(\phi(n))} \equiv 1 \mod n$ this one follows.
  
</p>

### Proof of existence and uniqueness of inverses in $Z_{p}^{*}$ and $Z_{\phi(n)}^{\ast}$ 

<p>
  
  $Z_{p} = \\{1, 2, \dots, p - 1\\}$

  with the operation of multiplication

  $\\{Z_{p}, \cdot\\} = \\{x \cdot y \mod p\\}$

  where $x, y$ are positive integers $> 0$; forms a multiplicative group, that is, a set with a binary operation which produces from $2$ elements of the set, $1$ element of the same set; where exists an identity element ($1$) and where each element has an inverse (etc.). Since all these requirements are quite obvious, the only one which (for the moment) needs a more detailed analysis is the inverse existence and uniqueness for every element. Calling $z$ any element of $Z_{p}^{*}$, since $z$ is coprime with $p$, the Bezout's Identity ensures that

  $zk + (-x)p = 1$

  always exists, and we can rewrite this as

  $zk \equiv 1 \mod p$

  proving that every element of $Z_{p}^{*}$ has an inverse. Now the real question is about uniqueness. We can reuse the almighty 'cancellation law' and state that if

  $z_{1}k_{1} \equiv z_{2}k_{1} \mod p$
  
  is true, then $z_{1}, z_{2}$ should be the same number since $z_{1}, z_{2} < p$ and $k_{1} < p$ (this means it's coprime, otherwise we couldn't use the law). Since the hypothesis is that they are not the same number $k_{1_{1}}, 
  k_{1_{2}}$ are forced to be different. This proves the uniqueness of the inverses and one part of the Wilson's Theorem since this proof was requested to complete the proof.

  This whole reasoning is easily iterable for $Z_{\phi(n)}^{\ast}$, proving that every element of $Z_{\phi(n)}^{\ast}$ also has an inverse which is unique.
  
</p>
