# Functions and Relations

This document covers the fundamental concepts of **Functions and Relations** in discrete mathematics, including definitions, properties, examples, and solutions to common problems.

---

## Table of Contents

1. [Relations](#relations)
   - [Definition](#definition-of-relation)
   - [Types of Relations](#types-of-relations)
2. [Functions](#functions)
   - [Definition](#definition-of-function)
   - [Types of Functions](#types-of-functions)
3. [Problems with Solutions](#problems-with-solutions)

---

## Relations

### Definition of Relation

A **relation** R from a set A to a set B is a subset of the Cartesian product A × B. In other words, a relation is a set of ordered pairs (a, b) where a ∈ A and b ∈ B.

**Notation:** If (a, b) ∈ R, we write aRb (read as "a is related to b").

**Example:**
Let A = {1, 2, 3} and B = {a, b}

The Cartesian product A × B = {(1, a), (1, b), (2, a), (2, b), (3, a), (3, b)}

A possible relation R from A to B could be: R = {(1, a), (2, b), (3, a)}

### Types of Relations

For a relation R on a set A (i.e., R ⊆ A × A):

#### 1. Reflexive Relation
A relation R on a set A is **reflexive** if every element is related to itself.

∀ a ∈ A: (a, a) ∈ R

**Example:** On set A = {1, 2, 3}, the relation R = {(1, 1), (2, 2), (3, 3), (1, 2)} is reflexive.

#### 2. Symmetric Relation
A relation R on a set A is **symmetric** if whenever a is related to b, then b is also related to a.

∀ a, b ∈ A: (a, b) ∈ R ⟹ (b, a) ∈ R

**Example:** R = {(1, 2), (2, 1), (3, 3)} is symmetric.

#### 3. Transitive Relation
A relation R on a set A is **transitive** if whenever a is related to b and b is related to c, then a is also related to c.

∀ a, b, c ∈ A: [(a, b) ∈ R ∧ (b, c) ∈ R] ⟹ (a, c) ∈ R

**Example:** R = {(1, 2), (2, 3), (1, 3)} is transitive.

#### 4. Equivalence Relation
A relation is an **equivalence relation** if it is reflexive, symmetric, AND transitive.

**Example:** Equality (=) on any set is an equivalence relation.

#### 5. Anti-symmetric Relation
A relation R on a set A is **anti-symmetric** if:

∀ a, b ∈ A: [(a, b) ∈ R ∧ (b, a) ∈ R] ⟹ a = b

**Example:** The "less than or equal to" (≤) relation on integers is anti-symmetric.

---

## Functions

### Definition of Function

A **function** f from a set A to a set B (written f: A → B) is a special type of relation where every element in A is related to exactly one element in B.

- **Domain:** The set A (the set of all inputs)
- **Codomain:** The set B (the set of all possible outputs)
- **Range:** The set of all actual outputs {f(a) | a ∈ A} ⊆ B

**Key Difference from Relations:**
- A relation can map one element to multiple elements
- A function must map each element to exactly ONE element

**Example:**
f: {1, 2, 3} → {a, b, c} defined by f(1) = a, f(2) = b, f(3) = c is a function.

### Types of Functions

#### 1. Injective (One-to-One) Function
A function f: A → B is **injective** if different inputs always produce different outputs.

∀ a₁, a₂ ∈ A: f(a₁) = f(a₂) ⟹ a₁ = a₂

**Example:** f(x) = 2x is injective because if 2x₁ = 2x₂, then x₁ = x₂.

#### 2. Surjective (Onto) Function
A function f: A → B is **surjective** if every element in B is mapped to by at least one element in A.

∀ b ∈ B, ∃ a ∈ A: f(a) = b

**Example:** f: ℝ → ℝ defined by f(x) = x³ is surjective.

#### 3. Bijective (One-to-One and Onto) Function
A function is **bijective** if it is both injective AND surjective. Bijective functions have an inverse function.

**Example:** f(x) = x + 1 is bijective from ℝ to ℝ.

---

## Problems with Solutions

### Problem 1: Identifying Relation Properties

**Question:** Determine whether the relation R = {(1, 1), (2, 2), (3, 3), (1, 2), (2, 1)} on set A = {1, 2, 3} is:
- a) Reflexive
- b) Symmetric
- c) Transitive
- d) An equivalence relation

**Solution:**

a) **Reflexive?** ✅ YES
   - Check: (1, 1) ∈ R ✓, (2, 2) ∈ R ✓, (3, 3) ∈ R ✓
   - All elements are related to themselves.

b) **Symmetric?** ✅ YES
   - Check all pairs: 
   - (1, 2) ∈ R and (2, 1) ∈ R ✓
   - (1, 1), (2, 2), (3, 3) are symmetric by default ✓

c) **Transitive?** ✅ YES
   - Check: (1, 2) ∈ R and (2, 1) ∈ R ⟹ need (1, 1) ∈ R ✓
   - Check: (2, 1) ∈ R and (1, 2) ∈ R ⟹ need (2, 2) ∈ R ✓
   - All transitive conditions are satisfied.

d) **Equivalence Relation?** ✅ YES
   - Since R is reflexive, symmetric, and transitive, it is an equivalence relation.

---

### Problem 2: Function Classification

**Question:** Let f: ℤ → ℤ be defined by f(x) = x². Determine if f is:
- a) Injective
- b) Surjective
- c) Bijective

**Solution:**

a) **Injective?** ❌ NO
   - Counter-example: f(2) = 4 and f(-2) = 4
   - Two different inputs (2 and -2) give the same output (4)
   - Therefore, f is NOT injective.

b) **Surjective?** ❌ NO
   - Counter-example: There is no integer x such that x² = -1
   - Negative numbers in the codomain are never reached.
   - Therefore, f is NOT surjective.

c) **Bijective?** ❌ NO
   - Since f is neither injective nor surjective, it cannot be bijective.

---

### Problem 3: Composition of Functions

**Question:** Given f(x) = 2x + 1 and g(x) = x², find:
- a) (f ∘ g)(x)
- b) (g ∘ f)(x)
- c) (f ∘ g)(3)

**Solution:**

a) **(f ∘ g)(x) = f(g(x))**
   - g(x) = x²
   - f(g(x)) = f(x²) = 2(x²) + 1 = 2x² + 1
   - **Answer: (f ∘ g)(x) = 2x² + 1**

b) **(g ∘ f)(x) = g(f(x))**
   - f(x) = 2x + 1
   - g(f(x)) = g(2x + 1) = (2x + 1)² = 4x² + 4x + 1
   - **Answer: (g ∘ f)(x) = 4x² + 4x + 1**

c) **(f ∘ g)(3)**
   - Using (f ∘ g)(x) = 2x² + 1
   - (f ∘ g)(3) = 2(3)² + 1 = 2(9) + 1 = 18 + 1 = 19
   - **Answer: (f ∘ g)(3) = 19**

---

### Problem 4: Inverse Function

**Question:** Find the inverse of f(x) = 3x - 5, if it exists.

**Solution:**

Step 1: Verify that f is bijective (so the inverse exists)
- f is injective: If 3x₁ - 5 = 3x₂ - 5, then x₁ = x₂ ✓
- f is surjective: For any y ∈ ℝ, we can find x = (y + 5)/3 ✓
- Therefore, f is bijective and has an inverse.

Step 2: Find the inverse
- Let y = f(x) = 3x - 5
- Solve for x: y + 5 = 3x → x = (y + 5)/3
- Replace y with x: f⁻¹(x) = (x + 5)/3

**Answer: f⁻¹(x) = (x + 5)/3**

Verification: f(f⁻¹(x)) = f((x + 5)/3) = 3((x + 5)/3) - 5 = x + 5 - 5 = x ✓

---

### Problem 5: Determining if a Relation is a Function

**Question:** Which of the following relations from A = {1, 2, 3} to B = {a, b, c} are functions?

- R₁ = {(1, a), (2, b), (3, c)}
- R₂ = {(1, a), (1, b), (2, c)}
- R₃ = {(1, a), (2, a)}

**Solution:**

**R₁ = {(1, a), (2, b), (3, c)}**
- ✅ IS a function
- Each element in A (1, 2, 3) maps to exactly one element in B.

**R₂ = {(1, a), (1, b), (2, c)}**
- ❌ NOT a function
- Element 1 maps to both 'a' and 'b' (violates the uniqueness condition).

**R₃ = {(1, a), (2, a)}**
- ❌ NOT a function
- Element 3 from set A has no mapping (every element in the domain must have a mapping).

---

## Summary Table

| Concept | Definition | Example |
|---------|------------|---------|
| Relation | Subset of A × B | R = {(1, a), (2, b)} |
| Reflexive | ∀a: (a,a) ∈ R | R = {(1,1), (2,2)} |
| Symmetric | (a,b) ∈ R ⟹ (b,a) ∈ R | R = {(1,2), (2,1)} |
| Transitive | (a,b), (b,c) ∈ R ⟹ (a,c) ∈ R | R = {(1,2), (2,3), (1,3)} |
| Function | Each input → exactly one output | f(x) = x + 1 |
| Injective | Different inputs → different outputs | f(x) = 2x |
| Surjective | All outputs are reached | f: ℝ → ℝ, f(x) = x³ |
| Bijective | Both injective and surjective | f(x) = x + 1 |

---

## Practice Problems

Try these on your own:

1. Is the relation R = {(a, a), (b, b), (a, b), (b, a)} on A = {a, b, c} reflexive?

2. Given f: ℝ → ℝ where f(x) = |x|, is this function injective?

3. Find the composition (g ∘ f)(x) where f(x) = x + 2 and g(x) = 3x.

4. Determine if f: ℕ → ℕ defined by f(n) = n + 1 is surjective.

---

*This document was created as part of a Computer Science study resource for discrete mathematics.*
