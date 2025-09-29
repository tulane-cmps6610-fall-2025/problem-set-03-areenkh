# CMPS 6610 Problem Set 03
## Answers

**Name:**_________________________


Place all written answers from `problemset-03.md` here for easier grading.




- **1b.**

Both the span and work are $O(n)$



- **1d.**


Work is $O(n)$ and span is $O(log n)$


- **1e.**

Work is $W(n)= W(n/3)+W(2n/3)+O(1)$ Therefore, it's $O(n)$

Span is $S(n)= S(2n/3)+O(1)$ Therefore, it's $O(\log n)$

- **2a.**
OR takes two booleans a and b and returns their logical OR

OR(a, b) = a ∨ b

member(S, y) =
  reduce(OR,false, ⟨ S[i] = y: 0 ≤ i < |S| ⟩)

dedup(A) =
  iterate(F,⟨ ⟩, A)
  where F(out, y) =
      if member(out, y) then 
        out
      else 
        out ++ ⟨y⟩

- **2b.**
combine(L, R) =
  L ++ ⟨ R[j] : 0 ≤ j < |R| ,not member(L, R[j]) ⟩

multi_dedup(A) =
  let 
    B = ⟨dedup(A[i]):0 ≤ i < |A|⟩
  in  
    reduce(combine,⟨ ⟩, B)
  end


Work of member(out,y) is O(|out|).

Span of member(out,y) is O(log|out|)

In the worst case (all distinct), any order-preserving dedup built from iterate + member does

$sum_{k=1}^{N} O(k) = O(n^2)$ work and 

$sum_{k=1}^{N} O(\log k) = O(n \log n)$ span

The worst-case asymptotics remain the same as Part 2a applied to a length N list:
Work: $O(n^2)$
Span: $O(n\log n)$

- **2c.**
Yes, we used iterate to process left-to-right and preserve first-appearance order. We also used reduce(OR) to implement member(out, y) in parallel.

- **3b.**
Work: $W(n)=W(n-1)+1 -> O(n)$
Span: $S(n)=S(n-1)+1 -> O(n)$

- **3d.**

$W_map(n) = O(n)$
$S_map(n) = O(n)$

$W_scan(n) = W_(scan)(n/2)+O(n) -> O(n)$
$S_scan(n) = S_scan(n/2)+O(1) -> O(\log n)$

$W_reduce(n) = 2W_reduce(n/2)+O(1) -> O(n)$
$S_reduce(n) = S_reduce(n/2)+O(1) -> O(\log n)$

Whole algorith: 
$W(n)=O(n)$
$S(\log n)$


- **3f.**

Work: $W(n) = 2W(n/2)+O(1) -> O(n)$
Span: $S(n) = S(n)+O(1) -> O(\log n)$



