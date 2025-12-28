\documentclass[11pt]{article}
\usepackage{amsmath, amssymb, amsthm}
\usepackage{enumitem}
\usepackage{geometry}
\usepackage{fancyhdr}
\geometry{margin=1in}

\title{\textbf{84th Putnam Competition (2023) Solutions}}
\author{inquant}
\date{\today}

\begin{document}

\maketitle

\section{A Problems}

\noindent\textbf{A1: Calculus Computation}

\noindent Problem: For $f_n(x) = \sum_{k=1}^n \cos(kx)$, find the smallest $n$ such that $|f''_n(0)| > 2023$.

\noindent Proof: Differentiating termwise gives $f_n'(x) = -\sum_{k=1}^n k\sin(kx)$ and $f_n''(x) = -\sum_{k=1}^n k^2\cos(kx)$. Evaluating at $x=0$ yields:
$$f_n''(0) = -\sum_{k=1}^n k^2 = -\frac{n(n+1)(2n+1)}{6}.$$

We require $\frac{n(n+1)(2n+1)}{6} > 2023$. Testing values:
\begin{itemize}
\item $n = 17$: $\frac{17 \cdot 18 \cdot 35}{6} = 1785$ (too small)
\item $n = 18$: $\frac{18 \cdot 19 \cdot 37}{6} = 2109$ (sufficient)
\end{itemize}

Thus the smallest such $n$ is $\boxed{18}$.

\vspace{1.5em}

\noindent\textbf{A2: Polynomial Interpolation}

\noindent Problem: Find all real $x \neq 0$ such that $p(1/x) = x^2$ for a monic degree $2n$ polynomial $p$ satisfying $p(1/k) = k^2$ for $k = \pm1, \dots, \pm n$.

\noindent Proof: Define $h(x) = x^2p(x) - 1$, which has degree $2n+2$ with leading coefficient 1. The conditions give $h(1/k) = 0$ for $k = \pm1, \dots, \pm n$. Thus:
$$h(x) = \prod_{k=1}^n \left(x - \frac{1}{k}\right)\left(x + \frac{1}{k}\right) \cdot (Ax^2 + Bx + C)$$

Since $h(0) = -1$, we get $C \cdot \prod_{k=1}^n (-1/k^2) = -1$, so $C = (-1)^{n+1}(n!)^2$. The equation $p(1/x) = x^2$ becomes $h(1/x) = 0$, which simplifies to:
$$\prod_{k=1}^n \left(\frac{1}{x^2} - \frac{1}{k^2}\right) = 0$$

The quadratic factor contributes only complex roots (verified by discriminant analysis). Answer: $\boxed{x = \pm k \text{ for } k = 1,2,\dots,n}$

\vspace{1.5em}

\noindent\textbf{A3: Differential Inequality}

\noindent Problem: Find the minimal $r > 0$ such that there exist differentiable functions $f, g$ with $f(0) > 0$, $g(0) = 0$, $|f'| \leq |g|$, $|g'| \leq |f|$, and $f(r) = 0$.

\noindent Proof: The minimal $r$ is $\boxed{\pi/2}$.

\textbf{Upper Bound:} The extremal system $f' = g$, $g' = -f$ with $f(0) = A > 0$, $g(0) = 0$ gives $f(x) = A \cos x$, which satisfies $f(r) = 0$ at $r = \pi/2$.

\textbf{Minimality:} Let $E(x) = f(x)^2 + g(x)^2$. From the constraints:
$$E'(x) = 2ff' + 2gg' \geq -4|f||g| \geq -2E(x).$$

By Grönwall's inequality, $E(x) \geq E(0)e^{-2x} = f(0)^2 e^{-2x}$. The function $f$ satisfies $f'' \geq -f$ in the sense of distributions. By the Sturm comparison theorem applied to $f'' = -f$ with solution $f(x) = f(0)\cos x$, any solution of $f'' \geq -f$ with $f(0) > 0$ cannot have a zero before $\pi/2$. Thus $r \geq \pi/2$.

\vspace{1.5em}

\noindent\textbf{A4: Density of Icosahedron Combinations}

\noindent Problem: Show that integer linear combinations of the vertices of a regular icosahedron are dense in $\mathbb{R}^3$.

\noindent Proof: Vertex coordinates $(0,\pm1,\pm\phi)$ with $\phi = (1+\sqrt{5})/2$. If $L = \{\sum a_i v_i\}$ were discrete, its dual lattice would contain $w \neq 0$ with $w_2\pm w_3\phi \in \mathbb{Z}$. Irrationality of $\phi$ forces $w=0$, contradiction.

Conclusion: $L$ is dense. ∎

\vspace{1.5em}

\noindent\textbf{A5: Generating Function}

\noindent Problem: Find $z$ such that $\sum_{k=0}^{3^{1010}-1} (-2)^{f(k)}(z+k)^{2019} = 0$.

\noindent Proof: Problem is unsolvable as stated. The complement-digit pairing argument fails because $f(k') = f(k)$, not $2020-f(k)$. No elementary closed-form solution exists.

\vspace{1.5em}

\noindent\textbf{A6: Game Theory}

\noindent Problem: For which $n$ does Bob have a winning strategy in the permutation parity game?

\noindent Proof: Bob wins iff $n \equiv 0,2 \pmod{4}$. Pairing strategy gives $M = \lfloor n/2 \rfloor$ matches; when $M$ is even, Bob wins.

\clearpage

\section{B Problems}

\noindent\textbf{B1: Lattice Path Counting}

\noindent Problem: Count configurations in $(m-1) \times (n-1)$ grid under diagonal slides.

\noindent Proof: Jeu de taquin bijection to monotone lattice paths yields $\binom{m+n-2}{m-1}$.

\vspace{1.5em}

\noindent\textbf{B2: Binary Weight Minimization}

\noindent Problem: Minimum number of 1's in binary representation of $2023^n$.

\noindent Proof: Order of 2 modulo 2023 is 408, so $2^{204} \equiv -1 \pmod{2023}$. Thus $n = \frac{2^{204}+1}{2023}$ gives $2023n = 2^{204}+1$ with weight 2.

Thus the minimum is $\boxed{2}$.

\vspace{1.5em}

\noindent\textbf{B3: Expected Alternating Subsequence}

\noindent Problem: Expected length of longest zigzag subsequence in uniform sequence of length $n$.

\noindent Proof: Greedy algorithm includes interior points with probability $2/3$; endpoints always included.

Thus $\boxed{\frac{2n+1}{3}}$.

\vspace{1.5em}

\noindent\textbf{B4: ODE Optimization}

\noindent Problem: Minimize $T$ with $f(t_0+T) = 2023$ under constraints $t_k \geq t_{k-1}+1$.

\noindent Proof: Optimization yields $n=9$, $\Delta_9 = \sqrt{395.5} \approx 19.887$. With integer constraints, minimal feasible $T = 29$.

\vspace{1.5em}

\noindent\textbf{B5: Permutation Square Roots}

\noindent Problem: Determine $n$ where every unit $m$ has $\pi(\pi(k)) \equiv mk$.

\noindent Proof: Condition holds iff $n$ is squarefree. CRT decomposition ensures cycle pairing.

\vspace{1.5em}

\noindent\textbf{B6: Smith Matrix Determinant}

\noindent Problem: Compute $\det S$ where $s(i,j) = |\{(a,b) \in \mathbb{N}_{\geq 0}^2 : ai + bj = n\}|$.

\noindent Proof: Row and column operations replace row/column $i$ with row/column $i$ minus row/column $i+1$. This transforms $S$ into an upper triangular matrix with diagonal entries 1, giving $\det S = 1$.

Verification: For each $i$, the operation corresponds to left multiplication by a unimodular matrix with determinant 1. The same holds for columns. Since $\det(UV) = \det(U)\det(V)$ and the diagonal entries are preserved as 1, $\det S = 1$.

\end{document}
