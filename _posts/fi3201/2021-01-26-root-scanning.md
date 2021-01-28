---
layout: post
author: viridi
title: root scanning
mathjax: true
ptext: false
x3dom: false
threejs: false
oo: false
category: physics
tags: ["fi3201", "root", "scanning"]
date: 2021-01-27 06:34:00 +07
permalink: /fi3201/root-scanning
---
We can use scanning method in finding a root, even it is not listed in the list of root-finding algorithms [[1](#ref1)]. This method is not efficient, not accurate, and very step dependent, but very simple and straightforward.


## sign function
A signum function or sign function can be deined as [[2](#ref2)]

\begin{equation}
\label{eqn:rs-sign-function}
{\rm sign}(x) = \left\\{
\begin{array}{lr}
-1, & x < 0, \newline
0, & x = 0, \newline
1, & x > 0,
\end{array}
\right.
\end{equation}

or for $x \ne 0$ it can be approximated with

\begin{equation}
\label{eqn:rs-sign-function-non-zero}
{\rm sign}(x) = \frac{x}{\|x\|} = \frac{\|x\|}{x}.
\end{equation}

We will use the Eqn. \eqref{eqn:rs-sign-function-non-zero} instead of \eqref{eqn:rs-sign-function} only for simplicity.


## algorithm
Assume that a function $f(x)$ already exists and we would like to find $x$ as a root of the function. 

Algorithm <a name="alg:rs-scanning-method-algorithm">1</a> Scanning method. \
`I`: $f(x)$, $x_{\rm beg}$, $x_{\rm end}$, $\Delta x$ \
`O`: $x_{\rm root}$
1. $x \leftarrow x_{\rm beg}$.
2. $\displaystyle S_0 \leftarrow \frac{f(x)}{\|f(x)\|}$.
3. $x \leftarrow x + \Delta x$.
4. $\displaystyle S \leftarrow \frac{f(x)}{\|f(x)\|}$.
5. $S_0 S < 0 \Rightarrow \rm step\ 8$
6. $x > x_{\rm end} \Rightarrow \rm step\ 10$
7. $\Rightarrow step\ 3$
8. $x_{\rm r} \leftarrow x - \frac12 \Delta x$.
9. $\Rightarrow step\ 11$
10. $x_{\rm r} \notin  [x_{\rm beg}, x_{\rm end}]$.
11. $x_{\rm root} \leftarrow x_r$

A function $f(x)$ will be solved using Alg. <a href="#alg:rs-scanning-method-algorithm">1</a> as discussed in following section.


## test function
Let us have a function

\begin{equation}
\label{eqn:rs-test-function}
f(x) = \frac{1}{20} (x + 1) (x - 3.45) (x - 8),
\end{equation}

a polynomial function with 3rd order. Illustration how Alg. <a href="#alg:rs-scanning-method-algorithm">1</a> works for Eqn. \eqref{eqn:rs-test-function} is given in Figs. <a href="#fig:rs-example-dx-1">1</a> and <a href="#fig:rs-example-dx-0.5">2</a>.

{:refdef: style="text-align: center;"}
![..](/assets/img/math/root/root-scanning-dx-1-2.png)
![..](/assets/img/math/root/root-scanning-dx-1-3.png)
![..](/assets/img/math/root/root-scanning-dx-1-4.png)
<br />
Figure <a name="fig:rs-example-dx-1">1</a> Scanning a root with $x_{\rm beg} = 2$ and $\Delta x = 1$, with result of $x_{\rm root} = 3.5$, while: $x = 2$ (top), $x = 3$ (middle), and $x = 4$ (bottom). 
{: refdef}

Three steps are required to get the result of $x_{\rm root} = 3.5$ for $\Delta x = 1$ as shown in Fig. <a name="fig:rs-example-dx-1">1</a>. In each sub-figure the point being examined is indicated with vertical blue line.

{:refdef: style="text-align: center;"}
![..](/assets/img/math/root/root-scanning-dx-0.5-2.0.png)
![..](/assets/img/math/root/root-scanning-dx-0.5-2.5.png)
![..](/assets/img/math/root/root-scanning-dx-0.5-3.0.png)
![..](/assets/img/math/root/root-scanning-dx-0.5-3.5.png)
<br />
Figure <a name="fig:rs-example-dx-0.5">2</a> Scanning a root with $x_{\rm beg} = 2$ and $\Delta x = 0.5$, with result of $x_{\rm root} = 3.25$, while: $x = 2$ (top), $x = 2.5$ )second top), $x = 3$ (second bottom), and $x = 3.5$ (bottom). 
{: refdef}

If we choose $\Delta x = 0.5$ then four steps are required to produce $x_{\rm root} = 3.25$. We can also try with $\Delta x = 0.25$ and we will have seven steps that produces $x_{\rm root} = 3.375$. Then $x = 3.5$ with 9 steps for $\Delta x = 0.2$. And finally $x = 3.45$ with 16 steps for $\Delta x = 0.1$, which is the right answer.

$\Delta x$ | 1 | 0.5 | 0.25 | 0.2 | 0.1
$N_{\rm step}$ | 3 | 4 | 7 |9 | 16
$x_{\rm root}$ | 3.5 | 3.25 | 3.375 | 3.5 | 3.45

Previous table summerized the discussed results, where all use the same initial value $x_{\rm beg} = 2$.


## implementation
We can design that the output is as follow

```batch
f(x)  0.05(x+1)(x-3.45)(x-8)
Δx    1
xbeg  2
xend  5
Nstep 3
xroot 3.5
```

Three examples are given in the next sub-sections.

### javascript
Following code `root-scanning.js` is tested using Node.js v10.1.0 on Windows 10 Home.

```javascript
// Define a test function
function test_function() {
	var x = arguments[0];
	var a = 0.05;
	var x1 = -1;
	var x2 = 3.45;
	var x3 = 8;
	var y = a*(x-x1)*(x-x2)*(x-x3);
	return y;
}


// Define main function
function main() {
	// Define input
	var f = test_function;
	var xbeg = 3;
	var xend = 5;
	var dx = 1;
	
	// Define default message
	var xroot = "not found";
	
	// Do iteration
	var S0, S;
	var Nstep = 0;
	var x = xbeg;
	while(x <= xend) {
		// Increase Nstep;
		Nstep++;
		
		// Calculate S0 and S
		if(x == xbeg) {
			S0 = Math.sign(f(x));
		} else {
			S = Math.sign(f(x));
		}
		
		// Check S0.S for root
		if(x > xbeg) {
			if(S0 * S < 0) {
				xroot = x - 0.5 * dx;
				break;
			}
		}
		x += dx;
	}
	
	// Display result
	console.log("f(x)  0.05(x+1)(x-3.45)(x-8)");
	console.log("Δx    " + dx);
	console.log("xbeg  " + xbeg);
	console.log("xend  " + xend);
	console.log("Nstep " + Nstep);
	console.log("xroot " + xroot);
}


// Call main function
main();
```

Full source code with comments can be accessed [here](https://github.com/butiran/butiran.github.io/blob/master/src/js/fi3201/root/root-scanning.js)

### c++
```c++
```

### python
```python
```


## exercises
1. Using previous C++ code compile the program to produce results for $\Delta x = 0.01$. What are the value of $N_{\rm step}$ and $x_{\rm root}$? Use the same $x_{\rm beg} = 2$.
2. Modify `root-scanning.js` to get following result
```batch
f(x)  0.05(x+1)(x-3.45)(x-8)
Δx    1
xbeg  0
xend  3
Nstep 4
xroot not found
```
Can you explain why such result is produced?


## references
1. <a name="ref1"></a>Wikipedia contributors, "Root-finding algorithms", Wikipedia, The Free Encyclopedia, 15 January 2021, 23:25 UTC, <https://en.wikipedia.org/w/index.php?oldid=1000624440> [20210126].
2. <a name="ref1"></a>Wikipedia contributors, "Root-finding algorithms", Wikipedia, The Free Encyclopedia, 15 January 2021, 23:25 UTC, <https://en.wikipedia.org/w/index.php?oldid=1000624440> [20210126].

+ [Article history](https://github.com/butiran/butiran.github.io/commits/master/_posts/fi3201/2021-01-26-root-scanning.md)