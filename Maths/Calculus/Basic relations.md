
### Sets of numbers :

- $\mathbb{N}$ : Natural
- $\mathbb{D}$ : Decimal
- $\mathbb{Z}$ : Integers
- $\mathbb{Q}$ : Rationals
- $\mathbb{R}$ : Reals
- $\mathbb{C}$ : Complex


### Natural Logarithm

- $ln(x * y) = ln(x) + ln(y)$
- $ln (\frac 1 x) = -ln(x)$
- $ln(\frac x y) = ln(x) - ln(y)$
- $ln(\sqrt{x}) = \frac 1 2 \space ln(x)$
- $ln(x^n) = n \cdot ln(x)$

### e
//TODO

### Summations
$$ \sum_{i=1}^n i = \frac {n(n+1)} {2} $$

$$ \sum_{i=1}^n i^2 = \frac{n(n+1)(2n+1)}{6} $$

$$ \sum_{i=1}^n i^3 = \left(\sum_{i=1}^n i\right)^2 = \left(\frac{n(n+1)}{2}\right)^2 $$

### Logic

Let P and Q be two propositions:

The negation on a proposition $P$ is denoted ($\neg P$)

- $A \land (B \lor C) = (A \land B) \lor (A \land C)$
- $A \lor (B \land C) = (A \lor B) \land (A \lor C)$

#### Morgan Law:

- $\neg (P \lor Q) = (\neg P) \land (\neg Q)$
- $\neg (P \land Q) = (\neg P) \lor (\neg Q)$

#### Implication / Negation of implication:

- $P \implies Q = (\neg P) \lor Q$
- $\neg(P \implies Q) = P \land (\neg Q)$

#### Contrapositive of implication :

- $(P \implies Q) = (\neg Q) \implies (\neg P)$

#### If and only If:

- $(A \iff B) = (A \implies B) \land (B \implies A)$
- $\neg (A \iff B) = (A \land \neg B) \lor (B \land \neg A)$


### Relations

- Reflexive
    
    $aRb$
    
- Symmetric
    
    $aRb \iff bRa$
    
- Transitive
    
    $(aRb)\land(bRc) \implies (aRc)$
    
- Anti-symmetric
    
    $(aRb)\land(bRa) \implies a = b$
    
- Asymmetric
    
    $aRb \implies \neg (bRa)$
    
- Equivalence
    
    Reflexive + symmetric + Transitive
    
- Partial order
    
    Reflexive + anti-symmetric + transitive
    
- Total order
    
    Reflexive + anti-symmetric + transitive AND $aRb \lor bRa$