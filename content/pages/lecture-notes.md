---
content_type: page
description: This page includes lecture notes and readings for each lecture.
draft: false
title: Lecture Notes and Readings
uid: dc60f1da-e984-4045-b07c-af4129d934e0
---
Lecture notes were prepared by Paige Bright under the guidance of Professors Edelman and Johnson. {{% resource_link "b67b8d11-1918-467a-bb76-1cfdb8289174" "Full Course Notes (PDF)" %}}   
The notes are also available on {{% resource_link "cd0eaa5b-2cd6-430a-b68c-d08e1402f97b" "arXiv.org" %}}, along with any updates and citing information.

## Lecture 1

### Outline

**Part 1:** Overview, applications, and motivation.

**Part 2:** Rethinking derivatives as linear operators: f(x + dx) - f(x) = df = f′(x)\[dx\] — f′ is the {{% resource_link "5ce3ac77-ea9b-496d-9958-c91b5a05cc54" "linear operator" %}} that gives the change df in the output from a "tiny" change dx in the inputs, to first order in dx (i.e. dropping higher-order terms). When we have a scalar function f(x) ∈ ℝ of vector inputs x ∈ ℝⁿ, then this gives us a "row vector" f′(x) since f′(x)dx is a scalar, which we interpret as the transpose of the gradient ∇f (which we call a "column" vector), i.e. df = (∇f) ⋅ dx = (∇f)ᵀdx. When we have a vector function f(x) ∈ ℝᵐ of vector inputs x ∈ ℝⁿ, then f'(x) is a linear operator that takes n inputs to m outputs, which we can think of as an m × n matrix called the {{% resource_link "d84b32c3-1c98-4933-9bca-22202f3ca52f" "Jacobian matrix" %}} (typically covered only superficially in {{% resource_link "eef52057-2378-49ea-a937-e47025160784" "*18.02 Multivariable Calculus*" %}}.)

### Lecture Notes and Slides

- *Course notes: Chapter 1, and Chapter 2, Sections 2.1–2.3*
- Chapter 1: {{% resource_link "532b0906-f056-4c35-8800-db8207fd5011" "Lecture 1, Part 1 Notes: Overview and Motivation (PDF)" %}}  
- Part 1 Slides: {{% resource_link "db5aaa4c-5321-46b2-8ef2-55b2a072adeb" "Introduction (PDF)" %}}
- Chapter 2: {{% resource_link "d80e29bd-e7c8-4feb-836e-6afa2914ccde" "Lecture 1, Part 2 Notes: Derivatives as Linear Operators (PDF)" %}} 

### Further Readings

- {{% resource_link "1abb3073-ef45-4896-98d4-0c29e91f4607" "matrixcalculus.org" %}} is a fun site to play with derivatives of matrix and vector functions. 
- {{% resource_link "deb0c335-0454-47b6-b2c1-066e09a3d7a1" "*The Matrix Cookbook* (PDF)" %}} has a lot of formulas for these derivatives, but no derivations.
- Notes on {{% resource_link "f3fca745-e6c8-4a4d-918a-5417bbd5fd97" "Vector and Matrix Differentiation (PDF)" %}} from *6.S087 Special Subject in Electrical Engineering and Computer Science* (IAP 2021) are helpful.
- **Fancier math:** The perspective of derivatives as linear operators is sometimes called a {{% resource_link "1bc43bbb-3584-4045-aa07-75c6d15b5cc8" "Fréchet derivative" %}} and you can find lots of very abstract (what I'm calling "fancy") presentations of this online, chock full of weird terminology whose purpose is basically to generalize the concept to weird types of vector spaces. The "little-o notation" o(δx) we're using here for "infinitesimal asymptotics" is closely related to the {{% resource_link "8e1e7d21-1fa9-4a86-b1bb-ffa97c822fc8" "Big *O* notation" %}} used in computer science, but in computer science people are typically taking the limit as the argument (often called "n") becomes very large instead of very small. A fancy name for a row vector is a "covector" or {{% resource_link "6c1bc4a3-c800-4867-b852-a4b624de55a3" "linear form" %}}, and the fancy version of the relationship between row and column vectors is the {{% resource_link "2c11ab17-c14c-46be-9a48-e5c9323d1db4" "Riesz representation theorem" %}}, but until you get to non-Euclidean geometry you may be happier thinking of a row vector as the transpose of a column vector.

## Lecture 2

### Outline

**Part 1:** Continued discussing derivatives as linear operators, starting with Jacobian matrices. Reviewed the sum rule d(f + g) = df + dg, the product rule d(fg) = (df)g + f(dg), and the chain rule for f(g(x)) (f'(x) = g'(h(x))h'(x), where this is a composition of two linear operations, performing h' then g' — g'h' ≠ h'g'!). For functions from vectors to vectors, the chain rule is simply the product of Jacobians. Moreover, as soon as you compose 3 or more functions, it can make a huge difference whether you multiply the Jacobians from left to right ("reverse-mode", or "backpropagation", or "adjoint differentiation") or right to left ("forward-mode"). Showed, for example, that if you have many inputs but a single output (as is common in machine learning and other types of optimization problems), that it is vastly more efficient to multiply left-to-right than right-to-left, and such "backpropagation algorithms" are a key factor in the practicality of large-scale optimization. Finally, began talking about functions in more general vector spaces, such as functions with **matrix inputs and/or outputs**. For example, considered f(A) = A³, giving d(A³) = f′(A)\[dA\] = A²(dA) + A(dA)A + (dA)A² (≠3A²dA!), and f(A) = A⁻¹, giving d(A⁻¹) = -A⁻¹(dA)A⁻¹.

**Part 2:** Began going into more detail on matrix-valued functions, and their relationship to the "Jacobian matrix" picture. Converting f′(A) to a conventional "Jacobian matrix" in such cases requires converting matrices A into column vectors vec(A), a process called "vectorization" of the matrix (by a common convention: simply stacking the matrix by columns). Linear operators like f′(A)\[dA\] = AdA + dAA can then be expressed as "ordinary" matrices via {{% resource_link "4f386402-9ea3-4d21-9808-0d53e7a170e2" "Kronecker products" %}}.

### Lecture Notes and Other Resources

- *Course notes: Chapter 2, Sections 2.4–2.6, and Chapter 3*
- Part 0: {{% resource_link "76b7dc6b-b6f6-4b18-8c13-83392b4ae954" "Examples of Linear and Nonlinear Transformations of ℝ² via Images (try it online)" %}}
- Part 1: Derivatives as Linear Operators (continued) 
    - Chapter 2: {{% resource_link "d80e29bd-e7c8-4feb-836e-6afa2914ccde" "Lecture 1, Part 2 Notes: Derivatives as Linear Operators (PDF)" %}} 
- Chapter 3: {{% resource_link "98865698-8f4e-4766-9e15-a2d0d1d8f14d" "Lecture 2, Part 2 Notes: Jacobians of Matrix Functions (PDF)" %}} 
- Part 2 (Matrix Jacobians via {{% resource_link "ff20b32a-356f-4551-94ee-40b3d35547bf" "Vectorization" %}}): {{% resource_link "5674fdfe-1b21-4527-acbd-d156d4fd6078" "Two by Two Matrix Jacobians (HTML)" %}} {{% resource_link "d6549c38-24d1-4cad-85ba-b7be4bf7f9e1" "(Pluto notebook source code)" %}}

### Further Readings

- The terms "forward-mode" and "reverse-mode" differentiation are most prevalent in {{% resource_link "85066e63-8f42-4ad0-8088-9fd413dbab10" "automatic differentiation" %}} (AD), which we will cover later in this course. 
- You can find many, many articles online about {{% resource_link "c9f81497-e332-420d-b478-b98c911345fd" "backpropagation" %}} in neural networks. 
- There are many other versions of this, e.g. in differential geometry the derivative linear operator (multiplying Jacobians and perturbations dx right-to-left) is called a {{% resource_link "d6f78235-53dc-4220-8463-c52d1ab1c7ec" "pushforward" %}}, whereas multiplying a gradient row vector (covector) by a Jacobian left-to-right is called a {{% resource_link "80a05176-45c9-4df5-991b-b148d98541eb" "pullback" %}}. 
- The video on {{% resource_link "813aa7dd-f8be-4493-b636-831c66808e2d" "Understanding Automatic Differentiation (in Julia) (YouTube)" %}} by {{% resource_link "d74c961b-23fe-4542-a6a0-0fc9ece05d21" "Dr. Mohamed Tarek" %}} also starts with a similar left-to-right (reverse) vs right-to-left (forward) viewpoint and goes into how it translates to Julia code, and how you define custom chain-rule steps for Julia AD.

## Lecture 3

### Outline

**Part 1:** Continued from Lecture 2: matrix functions, Jacobians, vectorizations, and Kronecker products. More examples of matrix functions, including LU factorization and 2 × 2 eigenproblems.

**Part 2:** Finite-difference methods: viewing f(x + δx) – f(x) as an approximation for f'(x)δx on a computer. This is extremely useful as a quick check of a hand-derived derivative (which is very error-prone for complicated functions), and can also be used as a replacement for analytical derivatives in a pinch. Analyzed two sources of error: truncation error (from the non-infinitesimal δx) and roundoff error (from the finite precision of computer arithmetic).

### Lecture Notes and Other Resources

- *Course notes: Chapter 3 and Chapter 4* 
- Part 1 (Lecture 2 Part 2 continued)
    - Chapter 3: {{% resource_link "98865698-8f4e-4766-9e15-a2d0d1d8f14d" "Lecture 2, Part 2 Notes: Jacobians of Matrix Functions (PDF)" %}} 
-  {{% resource_link "5674fdfe-1b21-4527-acbd-d156d4fd6078" "Two by Two Matrix Jacobians (HTML)" %}} {{% resource_link "d6549c38-24d1-4cad-85ba-b7be4bf7f9e1" "(Pluto notebook source code)" %}}
- Chapter 4: {{% resource_link "6ba1e5b8-0fb9-454e-9a1c-372bfcbaae9a" "Lecture 3, Part 2 Notes: Finite-Difference Approximations (PDF)" %}} 
- Part 2: {{% resource_link "16570e1f-d628-4ecc-ae7b-f65fb08e5e1a" "Finite Difference (Jupyter notebook)" %}}

### Further Readings

- Wikipedia has a useful list of {{% resource_link "d18d0d11-b4ea-427c-9cdd-5c11e35e7ba9" "properties of the matrix trace" %}}. 
- The "matrix dot product" introduced today is also called the {{% resource_link "ed9fc255-41f8-42fd-bef9-a12dba6fc752" "Frobenius inner product" %}}, and the corresponding norm ("length" of the matrix viewed as a vector) is the {{% resource_link "04a433ec-18d8-434e-a935-bea119499964" "Frobenius norm" %}}. 
- When you "flatten" a matrix A by stacking its columns into a single vector, the result is called {{% resource_link "ff20b32a-356f-4551-94ee-40b3d35547bf" "vec(A)" %}}, and many important linear operations on matrices can be expressed as {{% resource_link "4f386402-9ea3-4d21-9808-0d53e7a170e2" "Kronecker products" %}}. 
- {{% resource_link "deb0c335-0454-47b6-b2c1-066e09a3d7a1" "*The Matrix Cookbook* (PDF)" %}} has lots of formulas for derivatives of matrix functions. 
- There is a lot of information online on {{% resource_link "f0f52df3-dd15-4f5d-a797-07ad16cd78dc" "finite difference" %}}, {{% resource_link "c8b8b0ed-6070-415c-851e-1455127cb8b3" "18.303 Notes on Finite Differences (PDF)" %}}, or {{% resource_link "d0e4a8ab-96b1-40be-b36f-1127a68b0688" "Section 5.7 of Numerical Derivatives (PDF)" %}}. 
- The Julia {{% resource_link "e9bb5ae3-c823-4b27-a398-bea9783f75c1" "FiniteDifferences.jl" %}} package provides lots of algorithms to compute finite-difference approximations; a particularly robust and powerful way to obtain high accuracy is to employ {{% resource_link "c6f1a071-32ea-4144-91e9-08785f2613ca" "Richardson extrapolation" %}} to smaller and smaller δx. If you make δx too small, the finite precision (#digits) of {{% resource_link "27f7d3e1-6094-46f8-9d8d-fbf98adc5270" "floating-point arithmetic" %}} leads to {{% resource_link "4510368f-f574-44b8-9c31-5de9b7544cbb" "catastrophic cancellation" %}} errors.

## Lecture 4

### Outline

**Part 0:** To begin with, spent a few minutes talking about the last few sections of the {{% resource_link "16570e1f-d628-4ecc-ae7b-f65fb08e5e1a" "Finite Difference (Jupyter notebook)" %}} from last lecture: higher-order finite-difference rules and finite differences in higher dimensions (e.g. for gradients).

**Part 1:** Generalizing **gradients** to scalar functions f(x) for x in arbitrary vector spaces x ∈ V. The key thing is that we need not just a vector space, but an **inner product** x ⋅ y (a "dot product", also denoted ⟨x,y⟩ or ⟨x|y⟩); V is then formally called a {{% resource_link "c0cd6832-8dc6-4236-a780-07ba42d639ba" "Hilbert space" %}}. Then, for any scalar function, since df = f'(x)\[dx\] is a linear operator mapping dx ∈ V to scalars df ∈ ℝ (a "{{% resource_link "6c1bc4a3-c800-4867-b852-a4b624de55a3" "linear form" %}}"), it turns out that it {{% resource_link "2c11ab17-c14c-46be-9a48-e5c9323d1db4" "*must* be a dot product" %}} of dx with "something", and we call that "something" the gradient! That is, once we define a dot product, then for any scalar function f(x) we can define ∇f by f'(x)\[dx\] = ∇f ⋅ dx. So ∇f is always something with the same "shape" as x (the {{% resource_link "0f377ba5-4520-44bb-a66a-a173e2cb3947" "steepest-ascent" %}} direction).

Defined the most obvious inner product of m × n matrices: the {{% resource_link "ed9fc255-41f8-42fd-bef9-a12dba6fc752" "Frobenius inner product" %}} A\\(\cdot\\)B = sum(A\\(\cdot\ast\\)B) = trace(AᵀB) = vec(A)ᵀvec(B), the sum of the products of the matrix entries. This also gives us the "Frobenius norm" ‖A‖² = A ⋅ A = trace(AᵀA) = ‖vec(A)‖², the square root of the sum of the squares of the entries. Using this, we can now take the derivatives of various scalar functions of matrices, e.g. we considered

- f(A) = ‖A‖ ⥰ ∇f = A/‖A‖
- f(A) = xᵀAy ⥰ ∇f = xyᵀ (for constant x, y)
- f(A) = det(A) ⥰ ∇f = det(A)(A⁻¹)ᵀ = {{% resource_link "f28a60e3-5d7b-45a4-8f75-01875476c36d" "adjugate" %}}(A)ᵀ: we will prove this later

**Part 2:** Applications of derivatives to multivariate root-finding and optimization. A key fact enabling large-scale optimization, i.e. min f(x) where f is a scalar function of *many* parameters x, is that computing ∇f has about the same cost as f, using what is variously called "reverse-mode" or "adjoint" or "backpropagation" differentiation algorithms, which essentially boil down to evaluating the chain rule **left to right**. Went through a few examples of this, oriented more at engineering/physics optimization (and "topology optimization").

### Lecture Notes and Slides

- *Course notes: Section 5.1, and Chapter 6*
- Chapter 5: {{% resource_link "7af616b9-bb47-4b92-88fb-f01a4faed704" "Lecture 4, Part 1 Notes: Derivatives in General Vector Spaces (PDF)" %}} 
- Chapter 6: {{% resource_link "6d55b3ea-f560-4129-9386-11f2f0f329e6" "Lecture 4, Part 2 Notes: Nonlinear Root-Finding, Optimization, and Adjoint Differentiation (PDF)" %}} 
- Part 2 Slides: {{% resource_link "f46d4277-f227-44f7-a6dd-7176e7d45df4" "Nonlinear Root-Finding, Optimization, and Adjoint-Method Differentiation (PDF)" %}}

### Further Readings (Part 2)

- Prof. Steven Johnson gave another {{% resource_link "f1257774-d535-401d-83aa-641ebfa13e40" "overview of optimization problems (PDF)" %}} in *18.335 Introduction to Numerical Methods*. 
- There are many textbooks on nonlinear programming, including {{% resource_link "ee4d00f8-5acb-48c8-b8d4-55a7c88fe543" "*Nonlinear Programming*" %}} (by Bertsekas) and specialized books on {{% resource_link "fc6bf517-ba60-4d00-9a0c-87a7a87e6ebc" "*Convex Optimization*" %}} (by Boyd and Vandenberghe), {{% resource_link "90680d52-551c-4335-9b9b-b05f771da271" "*Introduction to Derivative-Free Optimization*" %}} (by Conn, Scheinberg, and Vicente), etc. 
- A useful review of topology-optimization methods can be found in {{% resource_link "8f2e0375-81be-4a70-a60d-56121ca49dae" "Topology Optimization Approaches" %}} (by Sigmund and Maute). 
- See the {{% resource_link "ae210e12-ddc3-48ad-b4b0-4b159e8e1d5f" "Notes on Adjoint Methods (PDF)" %}} and {{% resource_link "0f73b6c7-1c38-4393-bc1e-51b402de6a7a" "The Adjoint Method for Differentiating Complex Computations (PDF)" %}} from *18.335 Introduction to Numerical Methods*. 

## Lecture 5

### Lecture Notes and Other Resources

- *Course notes: Section 5.2, Chapter 7, and Sections 8.1–8.2*
- Part 0: Norms and Derivatives: Why a Norm of the Input and Output Are Needed to Define a Derivative
- Chapter 7:{{% resource_link "0bf49c20-75d0-4e15-a605-390ec1f204e1" "Lecture 5, Part 1 Notes: Derivative of Matrix Determinant and Inverse (PDF)" %}}  
- Part 1: {{% resource_link "dcc1d232-206a-4ec7-8474-aec9ae8da39a" "Derivative of Matrix Determinant and Inverse (HTML)" %}} {{% resource_link "58261f48-bbeb-4a98-b042-4ce2be056a03" "(Julia source code)" %}}
- Part 2: {{% resource_link "6ec95617-bc03-46bd-894a-427aa82c253c" "Forward-Mode Automatic Differentiation via Dual Numbers (Jupyter notebook)" %}}
- Chapter 8: {{% resource_link "dd866538-0b2b-491b-85f9-005b8cbc7673" "Lecture 5, Part 3 Notes: Forward and Reverse-Mode Automatic Differentiation (PDF)" %}} 

### Further Readings (Part 1)

- There are lots of discussions of the {{% resource_link "27aa6b30-a410-42af-9a4d-229a95ed9107" "derivative of a determinant" %}} online, involving the {{% resource_link "f28a60e3-5d7b-45a4-8f75-01875476c36d" "\"adjugate\" matrix" %}} det(A)A⁻¹. Not as well documented is that the gradient of the determinant is the cofactor matrix widely used for the {{% resource_link "02349b71-61bb-46ca-9182-2da8899e9c34" "Laplace expansion" %}} of a determinant. The formula for the {{% resource_link "cf657bca-9bce-4534-b2af-0e406bfbbfd8" "derivative of log(det A)" %}} is also nice, and logs of determinants appear in surprisingly many applications (from statistics to quantum field theory). 
- {{% resource_link "deb0c335-0454-47b6-b2c1-066e09a3d7a1" "*The Matrix Cookbook* (PDF)" %}} contains many of these formulas, but no derivations. 
- A nice application of d(det(A)) is solving for eigenvalues λ by applying Newton's method to det(A - λI) = 0, and more generally one can solve det(M(λ)) = 0 for any function Μ(λ) — the resulting roots λ are called {{% resource_link "9236dc84-587e-4563-831f-68449d8b3bac" "nonlinear eigenvalues" %}} (if M is nonlinear in λ), and one can apply Newton's method using the determinant-derivative formula here.

### Further Readings (Part 2)

- Googling "automatic differentiation" will turn up many, many resources—this is a huge practical field these days. {{% resource_link "901fc722-12f9-49ae-bc78-4b45fcf97f3f" "ForwardDiff.jl" %}} (described in detail by "{{% resource_link "4cd1564e-84de-4f92-8cfe-681f324e6a4a" "Forward-Mode Automatic Differentiation in Julia" %}}") uses {{% resource_link "60520353-2e75-48e5-a65f-d0e032140aa4" "dual number" %}} arithmetic similar to lecture to compute derivatives.
- See also the article "{{% resource_link "823d23e0-9570-46e7-95d2-736b9a3683c6" "How to Differentiate with a Computer" %}}," or google "dual number automatic differentiation" for many other reviews. 

### Further Readings (Part 3)

- See {{% resource_link "7ec407de-8fee-4754-8991-d1be96b2a771" "Backpropagation through Back Substitution with a Backslash (PDF)" %}} about backpropagation on graphs, this blog post on {{% resource_link "036a94e4-4e9c-4c97-a293-49022d76b806" "calculus on computational graphs" %}} for a gentle review, and Columbia University’s {{% resource_link "29352b5b-cad3-4432-92e7-deda1f51a2a7" "Course Notes on Computational Graphs, and Backpropagation (PDF)" %}} for a more formal approach. 
- Implementing automatic reverse-mode AD is much more complicated than defining a new number type, unfortunately, and involves a lot more intricacies of compiler technology. See also Chris Rackauckas's blog post on {{% resource_link "0deb2b2f-6b2b-4ed5-a228-42d46e27b82b" "Engineering Trade-Offs in Automatic Differentiation: from TensorFlow and PyTorch to Jax and Julia" %}}, and Chris's discussion post on {{% resource_link "20e870df-2a78-47bd-a401-e741ae4d2ffe" "AD limitations" %}}.

## Lecture 6

### Lecture Notes and Slides

- *Course notes: Chapter 9 and Chapter 10*
- Chapter 9: {{% resource_link "1fb6c24e-c6b5-41f7-9405-56f9ff7bb689" "Lecture 6, Part 1a Notes: Differentiating ODE Solutions (PDF)" %}} 
- Part 1 Slides: {{% resource_link "1a34cc63-b920-4b86-80da-3c0f7566b9d5" "An Introduction to (Local) Sensitivity Analysis for (Ordinary) Differential Equations (PDF)" %}} (Courtesy of Frank Schäfer. Used with permission.)
- Chapter 10: {{% resource_link "4eca7e53-5fc8-49db-b808-e09685ee385e" "Lecture 6, Part 1b Notes: Calculus of Variations (PDF)" %}} 

### Further Readings (Part 1)

- A classic reference on adjoint-method (reverse-mode/backpropagation) differentiation of ODEs (and generalizations thereof), using notation similar to that used today, is {{% resource_link "5004cca8-207c-4292-b27b-d73e88929bf4" "Adjoint Sensitivity Analysis for Differential-Algebraic Equations: The Adjoint DAE System and Its Numerical Solution" %}} ({{% resource_link "9aceaa4d-4f5c-45bb-9513-74e29394e062" "PDF" %}}). 
- See also the {{% resource_link "5cbd9683-4d46-4155-ad9d-e53e48bb0b1b" "SciMLSensitivity.jl package" %}} for sensitivity analysis with Chris Rackauckas's amazing {{% resource_link "49d7c9ac-8fb2-4dc8-83d4-3a26846c8888" "DifferentialEquations.jl software suite" %}} for numerical solution of ODEs in Julia, along with his notes {{% resource_link "6b381f7e-ee15-45b5-a109-40184c362041" "Differentiable Programming and Neural Differential Equations" %}}. 
- There is a nice YouTube lecture on {{% resource_link "7d93aef9-5b61-4ba3-9a20-f856dbdc08b3" "Adjoint State Method for an ODE" %}}, again using a similar notation. 
- A *discrete* version of this process is {{% resource_link "4f30c3db-b0f7-4e82-9829-819e6707d02d" "adjoint methods and sensitivity analysis for recurrence relations (PDF)" %}} (MIT course notes), in which case one obtains a reverse-order "adjoint" recurrence relation.

### Further Readings (Part 2)

- There are many resources on the {{% resource_link "48eda133-9909-4774-a68e-9d783ddc3c60" "\"calculus of variations\"" %}}, which refers to derivatives of f(u) = ∫F(u,u′,…)dx for functions u(x), but we saw that it is essentially just a special case of our general rule df = f(u + du) - f(u) = f′(u)\[du\] = ∇f ⋅ du when du lies in a vector space of functions. Setting ∇f to find an extremum of f(u) yields an {{% resource_link "38a5e123-dbd0-4560-ba84-87be31bf5b92" "Euler–Lagrange equation" %}}, the most famous examples of which are probably {{% resource_link "d4803d41-2d08-47d5-92d7-989748311f47" "Lagrangian mechanics" %}} and also the {{% resource_link "80a0c611-5696-418a-8fa8-9a5db7d51d6b" "Brachistochrone problem" %}}, but it also shows up in many other contexts such as {{% resource_link "95149365-3edb-4e3b-9af8-25cd27d95dd9" "optimal control" %}}. 
- A very readable textbook on the subject is {{% resource_link "54023f2a-cb4a-4fed-99d6-c856582a3ab3" "*Calculus of Variations* by Gelfand and Fomin" %}}.

## Lecture 7

### Lecture Notes

- *Course notes: Chapter 11 and Chapter 12*
- Chapter 11: {{% resource_link "ffdcd720-dc4b-467a-861a-a6ff79ab6ff4" "Lecture 7, Part 1 Notes: Derivative of Random Functions (PDF)" %}} 
- Lecture 7, Part 1 Guest Lecture Notes: {{% resource_link "c66c314f-efc2-4a08-9982-e966fb2400c6" "Derivatives of Random Functions (PDF)" %}} (Courtesy of Gaurav Arya. Used with permission.)
- Chapter 12: {{% resource_link "7724967d-1b72-4498-b202-440d7437d3eb" "Lecture 7, Part 2 Notes: Second Derivatives, Bilinear Forms, and Hessian Matrices (PDF)" %}} 

### Further Readings (Part 1)

- The idea of computing gradients of programs with a sampleable random output is called {{% resource_link "5b52c02c-b255-4fda-abbb-0017c9e6063f" "Monte-Carlo Gradient Estimation" %}}; the link leads to a nice survey.
- This {{% resource_link "70590a23-36f6-41a9-b25a-46da7c08503e" "Stack Exchange answer" %}} gives a concise, worked-out example of the reparameterization trick applied to a toy program.
- {{% resource_link "0b755872-a95f-40bf-b2ac-1114aa73482d" "The frontier of simulation-based inference" %}} gives an overview of stochastic simulations across many domains of science, and discusses attempts to deal with the fact that it is much easier to sample them than to exactly compute a "likelihood."
- {{% resource_link "917e59fc-f84c-4a63-8c39-cfb1ca91c2ff" "Auto-Encoding Variational Bayes" %}} introduces the variational autoencoder, and introduces the reparameterization trick for use in training it.
- {{% resource_link "009b0bea-4e3a-4151-abb3-f5883415c70e" "Automatic differentiation of programs with discrete randomness" %}} describes an approach for generalizing derivatives of continuous random functions based on the "reparameterization trick" to discrete random functions. {{% resource_link "ba05f1c3-b7ac-487e-83ca-45176b36bcd8" "StochasticAD.jl" %}} is an associated code package that implements the stochastic triples we played with at the end of class.

### Further Readings (Part 2)

- {{% resource_link "ef69d82c-4821-4a5a-9b34-0dcb79d591bf" "Bilinear forms" %}} are an important generalization of quadratic operations to arbitrary vector spaces, and we saw that the second derivative can be viewed as a {{% resource_link "50b5685b-a868-4156-8c41-28dfdbce6481" "symmetric bilinear forms" %}}. This is closely related to a {{% resource_link "03077dea-90d6-4022-9dbe-2fd7b7029f0f" "quadratic form" %}}, which is just what we get by plugging in the same vector twice, e.g. the f''(x)\[δx,δx\]/2 that appears in quadratic approximations for f(x + δx) is a quadratic form. The most familiar multivariate version of f''(x) is the {{% resource_link "29bbee00-822c-402e-ad2a-f03258c18eb4" "Hessian matrix" %}}; Khan Academy has an elementary {{% resource_link "17e48aa4-d99f-4207-9858-1687c67e18f6" "quadratic approximation" %}}.
- {{% resource_link "ce525897-60be-43c5-b7ba-9c7ad359bb97" "Positive-definite" %}} Hessian matrices, or more generally {{% resource_link "5ecca9e2-30d2-436b-aa75-95693f312433" "definite quadratic forms" %}} f″, appear at extrema (f′ = 0) of scalar-valued functions f(x) that are local minima; there a lot {{% resource_link "54d02a64-82f5-4553-9956-fc4487f60aa0" "more formal treatments (PDF)" %}} of the same idea, and conversely Khan Academy has the {{% resource_link "2b5f930c-ef8b-4b93-8e9c-14b0d4532bd7" "simple 2-variable version" %}} where you can check the sign of the 2 × 2 eigenvalues just by looking at the determinant and a single entry (or the trace). There's a nice {{% resource_link "91d38d08-e753-4b33-adad-a18fa43fdc35" "Stack Exchange discussion" %}} on why an {{% resource_link "4064f24d-2934-4370-ad9c-ea06b7d9c642" "ill-conditioned" %}} Hessian tends to make steepest descent converge slowly; some Toronto {{% resource_link "7353adb9-08b2-47b5-a151-f5cd6b61ef1b" "Optimization (PDF)" %}} may also be helpful.
- See e.g. these Stanford notes on {{% resource_link "61dc296d-9d5c-4ca7-b8af-0c277f5ca002" "Sequential Convex Programming (PDF)" %}} using trust regions (sec. 2.2). See 18.335 notes on {{% resource_link "a4a190c3-6696-41c7-9f3e-7854e964671a" "Quasi-Newton Optimization: Origin of the BFGS Update (PDF)" %}}. The fact that a quadratic optimization problem in a sphere has {{% resource_link "35df739e-42d3-4549-bf3e-960cd0c60bc0" "strong duality" %}} and hence is efficiently solvable is discussed in section 5.2.4 of the {{% resource_link "7e2e402d-5b25-4da8-bfa8-de6b24939a46" "*Convex Optimization*" %}}. There has been a lot of work on {{% resource_link "7b78f49e-8245-4ea1-946a-c60b23077284" "automatic Hessian computation" %}}, but for large-scale problems you can ultimately only compute Hessian–vector products efficiently in general, which are equivalent to a directional derivative of the gradient, and can be used e.g. for {{% resource_link "2e775300-eb2d-4026-bf08-06a63e2133f7" "Newton–Krylov methods" %}}.

## Lecture 8

### Lecture Notes and Other Resources

- *Course notes: Chapter 13, and Chapter 8, Sections 8.3-8.4, and Chapter 14*
- Chapter 13: {{% resource_link "c135bd06-d239-432f-9f85-c1a607636ad3" "Lecture 8, Part 1 Notes: Derivatives of Eigenproblems (PDF)" %}} 
- Part 1: {{% resource_link "3f60d894-848b-49c0-9e88-1b30db4b8eb9" "Derivatives of Eigenproblems (HTML)" %}} {{% resource_link "4753711e-3fce-40a0-9a52-4a7fdf51a06f" "(Julia source code)" %}}
- Part 2: Forward and Reverse-Mode Automatic Differentiation on Computational Graphs (continued from Lecture 5) and {{% resource_link "ee69f58f-18ae-4e7a-aeb5-7afeb54fa12e" "interactive notebook (HTML)" %}}
- Chapter 14: {{% resource_link "e46f9d46-cd58-4cca-91d5-2ec64ff054c9" "Lecture 8, Part 3 Notes: Where We Go From Here (PDF)" %}} 

### Further Readings (Part 1)

- Computing derivatives on curved surfaces ("manifolds") is closely related to {{% resource_link "65b16b81-d5d7-4805-a2ef-e0c0e43c58d5" "tangent spaces" %}} in differential geometry. The effect of constraints can also be expressed in terms of {{% resource_link "26b0acfc-fc1d-4f40-954c-729475c53cae" "Lagrange multipliers" %}}, which are useful in expressing optimization problems with constraints (see also chapter 5 of {{% resource_link "7e2e402d-5b25-4da8-bfa8-de6b24939a46" "*Convex Optimization*" %}} by Boyd and Vandenberghe). In physics, first and second derivatives of eigenvalues and first derivatives of eigenvectors are often presented as part of {{% resource_link "ed03b7a6-a3e2-4bdf-91a3-d37eacb752ad" "\"time-independent\" perturbation theory" %}} in quantum mechanics, or as the {{% resource_link "f799181c-fb25-44d7-8716-ef50d4c5bf6a" "Hellmann–Feynmann theorem" %}} for the case of dλ. The derivative of an eigenvector involves *all* of the other eigenvectors, but a much simpler "vector–Jacobian product" (involving only a single eigenvector and eigenvalue) can be obtained from left-to-right differentiation of a *scalar function* of an eigenvector, as reviewed in the {{% resource_link "ae210e12-ddc3-48ad-b4b0-4b159e8e1d5f" "Notes on Adjoint Methods for 18.335 (PDF)" %}}.

### Further Readings (Part 2)

- See Lecture 5, above.

### Further Readings (Part 3)

There are many topics that we did not have time to cover, even in 16 hours of lectures. If you came into this class thinking that taking derivatives is easy and you already learned everything there is to know about it in first-year calculus, hopefully we've convinced you that it is an enormously rich subject that is impossible to exhaust in a single course. Some of the things it might have been nice to include are:

- When AD hits something it can't handle, you may have to write a custom Jacobian–vector product (a "Jvp", "frule", or "pushforward") in forward mode, and/or a custom rowvector–Jacobian product (a "vJp", "rrule", "pullback", or Jacobianᵀ–vector product) in reverse mode. In Julia with Zygote AD, this is done using {{% resource_link "e5203ba7-01a3-4b97-b9ad-2e98bbbdf505" "the ChainRules packages" %}}. In Python with JAX, this is done with {{% resource_link "3152a640-c188-4ae2-9be9-f8937cee67fc" "`jax.custom_jvp`" %}} and/or {{% resource_link "ff130692-e4d4-4b6e-88f9-58b6fc57ce29" "`jax.custom_vjp`" %}}, respectively. In principle this is straightforward, but the APIs can take some getting used to because of the generality that they support.
- For functions f(z) of complex arguments z (complex vector spaces), you cannot take "ordinary" complex derivatives whenever the function involves the conjugate z̄ (e.g. for |z|, Re z, or Im z); this *must* occur if f(z) is purely real-valued (and not constant). One option is to write z = x + iy and treat f(z) as a two-argument function f(x,y) with real derivatives, but this can be awkward if your problem is "naturally" expressed in terms of complex variables (e.g. in the {{% resource_link "6e19ecb5-195d-47be-a996-4810cc4f5934" "Fourier frequency domain" %}}). A common alternative is "CR calculus" (or "Wirtinger calculus"), in which you write df = (∂f/∂z)dz + (∂f/∂z̄)dz̄ as if z and z̄ were independent variables. This can be extended to gradients, Jacobians, steepest-descent, and Newton iterations, for example. A nice review can be found in {{% resource_link "3aade76d-173a-4080-bfe7-1d10bf7e46f2" "The Complex Gradient Operator and the CR-Calculus" %}} by Ken Kreuz-Delgado.
- Many, many more derivative results for matrix functions and factorizations can be found in the literature, some of them quite tricky to derive. For example, a number of references are listed in this GitHub issue for the {{% resource_link "b1acaa86-112d-45d2-a253-f59cdcb12262" "ChainRules package" %}}.
- Another important generalization of differential calculus is to derivatives on curved manifolds and differential geometry, leading to the {{% resource_link "43ebc870-0b75-48e6-9f1e-3f5e1390219f" "exterior derivative" %}}.
- When differentiating eigenvalues λ of matrices A(x), a complication arises at eigenvalue crossings (multiplicity k > 1), where in general the eigenvalues (and eigenvectors) cease to be differentiable. (More generally, this problem arises for any {{% resource_link "e0a416d6-1324-41c6-87e1-66c6bce8e4ed" "implicit function" %}} with a repeated root.) In this case, one option is to use an expanded definition of sensitivity analysis called a **generalized gradient** (a k × k matrix-valued linear operator G(x)\[dx\] whose eigenvalues are the perturbations dλ); see e.g. {{% resource_link "c71f4e79-2bb7-4713-8321-9d307c6b2eee" "Cox (1995)" %}}, {{% resource_link "49900645-8e06-4085-964c-f8cc33ef99cc" "Seyranian et al. (1994)" %}}, and {{% resource_link "ef964062-b578-4c24-955d-f467999ec471" "Stechlinski (2022)" %}}. (Physicists call this idea {{% resource_link "f2e70e87-4ea2-453f-9426-3f7f5723d486" "degenerate perturbation theory (PDF)" %}}.) A recent formulation of similar ideas is called a **lexicographic directional derivative**; see {{% resource_link "78f1ca28-55df-4e82-9442-1464ff781ef3" "Nesterov (2005)" %}} and {{% resource_link "0751148c-c797-4412-a608-911233bffdf1" "Barton et al. (2017)" %}}. Sometimes, optimization problems involving eigenvalues can be reformulated to avoid this difficulty by using {{% resource_link "41539e78-3d70-4088-9b8a-2cf94e11d9db" "SDP" %}} constraints {{% resource_link "b76258ac-1137-435c-980e-61b687df8fd9" "(Men et al. 2014)" %}}. For a {{% resource_link "33bf144d-3cf9-46ec-999e-29f09822d40b" "defective matrix" %}} the situation is worse: even the generalized derivatives blow up, because dλ is proportional to the *square root* of the perturbation ‖dA‖.
- Famous generalizations of differentiation are the {{% resource_link "2d190de1-8e87-4ad7-9cd5-5420142f475f" "\"distributional\"" %}} and {{% resource_link "914e90b5-2d42-4d4a-86b3-ce8d4ea1a7e8" "\"weak\"" %}} derivatives, for example to obtain {{% resource_link "9aed575d-2dbd-4be2-99c8-25cc1e21dbfa" "Dirac delta \"functions\"" %}} by differentiating discontinuities. This requires changing not only the definition of "derivative" but also *changing the definition of "function,"* as reviewed in {{% resource_link "39a3eb8e-a8f3-4d8e-b6a0-912fee14d3b3" "When Functions Have No Value(s): Delta Functions and Distributions (PDF)" %}}.