<h1 align="center">Skeletons</h1>

The morphological skeleton S(A) represents the shape of a binary foreground set A through its centerlines and branches. It can be described geometrically using disks or computed using erosion and opening.

**1. Geometric Interpretation & Maximum Disks**

For a point z inside A, let (D)<sub>z</sub> be the largest disk centered at z that fits inside A. The disk is *maximal* (called a *maximum disk* in the textbook) if no other disk inside A strictly contains it, even when the other disk has a different center. The centers of these disks form the geometric skeleton.

*Y-Shaped Example (Figure 9.25)*

In the textbook's Y-shaped region, disks along each arm touch its opposite sides, and their centers trace the arm's centerline. Near the ends, smaller maximal disks touch two adjacent edges. Their centers form the short branches toward the corners shown in the complete skeleton.

<img width="493" height="369" alt="skeletons-figure-9-25" src="https://github.com/user-attachments/assets/ce027ce2-5024-4002-972e-4730a0d08a37" />


*Figure 9.25. Maximal disks and the resulting skeleton of a Y-shaped region. Source: Gonzalez and Woods, Digital Image Processing, Section 9.5.*

**2. Mathematical Formulation Using Erosion & Opening**

Let B be the structuring element. The notation A ⊖ kB means applying erosion by B a total of k times, starting with A. For k=0, the result is A itself.

*Skeleton Subsets*

At each erosion level k, open the eroded region with B. The skeleton subset S<sub>k</sub>(A) consists of the pixels present before opening and removed by it.

```text
Sₖ(A) = (A ⊖ kB) ∖ ((A ⊖ kB) ∘ B)
```

Here, ⊖ denotes erosion, ∘ denotes opening, and ∖ denotes set difference.

*Complete Skeleton*

Let K be the last erosion level at which the eroded set is still nonempty. Taking the union of all skeleton subsets gives S(A).

```text
K = max { k ≥ 0 | A ⊖ kB ≠ ∅ }
```

```text
S(A) = ⋃ Sₖ(A),  k = 0, …, K
```

**3. Reconstruction Using Dilation**

The original set A can be recovered if each skeleton subset is kept with its erosion level k. Dilate S<sub>k</sub>(A) by B exactly k times, then take the union of the results.

```text
A = ⋃ (Sₖ(A) ⊕ kB),  k = 0, …, K
```

Here, ⊕ denotes dilation. The level k determines how far each subset expands during reconstruction.

*Reference* — Gonzalez and Woods, *Digital Image Processing*, Section 9.5, Figure 9.25 and Equations (9-28)–(9-33).
