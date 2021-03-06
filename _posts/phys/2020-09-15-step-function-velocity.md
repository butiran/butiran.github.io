---
layout: post
author: viridi
title: step function velocity
mathjax: true
ptext: false
x3dom: false
threejs: false
oo: true
category: physics
tags: ["topics"]
date: 2020-09-15 22:08:00 +07
permalink: /physics/step-function-velocity
---
There is a type of linear motion (LM) composed of some [uniform linear motions](uniform-linear-motion) (ULMs), which is different than the nonuniform linear motion (NULM). Velocity function $v(t)$ of this type of LM is simply a step function [[1](#ref1)]. Or it can said that each ULM is a boxcar function [[2](#ref2)].


## Boxcar function
A boxcar function has only non-zero value $A$ over a single interval, which can be described with

\begin{equation}
\label{eqn:vsf-boxcar-function}
{\rm boxcar}(x) =
\left\\{
\begin{array}{lc}
A, & a \le x < b, \newline
0, & x < a \cup b \le x,
\end{array}
\right.
\end{equation}

where the interval has lower boundary $a$ and upper boundary $b$.

<oo>
svg 400 200 #fafafa fig:vsf-boxchar|A boxchar function $f_{\rm BC}(x)$ with lower boundary $a$ and upper boundary $b$.

style lc:#000 ls:6-2 lw:0.3 lo:0.8
grid 20 20 380 180 40 40
style lc:#000 ls:0 lw:1 lo:1 fc:#000
arrow 20 180 380 180
arrow 20 180 20 20
style lc:#000 ls:0 lw:1 lo:1 fc:#000
circle 20 180 2
style lw:0 fc:#000 fo:1 ts:italic tw:normal tf:Times tz:16px
text 386 183 x
text 18 14 f
text 5 65 A
text 135 197 a
text 255 197 b
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:10px
text 24 16 BC

style lc:#f44 ls:6-4-2-4 lw:1 lo:1
line 20 60 380 60
line 140 180 140 60
line 260 180 260 60
style lc:#f00 ls:0 lw:2 lo:1
line 140 60 260 60
style lc:#f00 ls:0 lw:1 lo:1 fc:#f00
circle 140 60 4
style lc:#f00 ls:0 lw:1 lo:1 fc:#fff
circle 260 60 4
</oo>

Solid red circle in Fig. <a href="#fig:fig:vsf-boxchar">1</a> means that $f_{\rm BC}$ has value of $A$ at that position, while empty or white circle means that $f _{\rm BC}$ does not have value of $A$.

<oo>
svg 600 200 #fafafa fig:vsf-boxchar-example|Examples of boxchar funtion $f_{ {\rm BC}, 1}$, $f_{ {\rm BC}, 2}$, and $f_{ {\rm BC}, 3}$.

style lc:#000 ls:6-2 lw:0.3 lo:0.8
grid 20 20 180 180 40 40
style lc:#000 ls:0 lw:1 lo:1 fc:#000
arrow 20 180 180 180
arrow 20 180 20 20
style lc:#000 ls:0 lw:1 lo:1 fc:#000
circle 20 180 2
style lw:0 fc:#000 fo:1 ts:italic tw:normal tf:Times tz:16px
text 186 183 x
text 18 14 f
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:10px
text 24 16 BC,1
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:16px
text 15 197 0
text 55 197 1
text 95 197 2
text 135 197 3
text 5 185 0
text 5 145 1
text 5 105 2
text 5 65 3
style lc:#f00 ls:0 lw:2 lo:1
line 60 140 140 140
style lc:#f44 ls:6-4-2-4 lw:1 lo:1
line 60 140 60 180
line 140 140 140 180
style lc:#f00 ls:0 lw:1 lo:1 fc:#f00
circle 60 140 4
style lc:#f00 ls:0 lw:1 lo:1 fc:#fff
circle 140 140 4

style lc:#000 ls:6-2 lw:0.3 lo:0.8
grid 220 20 380 180 40 40
style lc:#000 ls:0 lw:1 lo:1 fc:#000
arrow 220 180 380 180
arrow 220 180 220 20
style lc:#000 ls:0 lw:1 lo:1 fc:#000
circle 220 180 2
style lw:0 fc:#000 fo:1 ts:italic tw:normal tf:Times tz:16px
text 386 183 x
text 218 14 f
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:10px
text 224 16 BC,2
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:16px
text 215 197 0
text 255 197 1
text 295 197 2
text 335 197 3
text 205 185 0
text 205 145 1
text 205 105 2
text 205 65 3
style lc:#f00 ls:0 lw:2 lo:1
line 220 60 340 60
style lc:#f44 ls:6-4-2-4 lw:1 lo:1
line 220 60 220 180
line 340 60 340 180
style lc:#f00 ls:0 lw:1 lo:1 fc:#f00
circle 220 60 4
style lc:#f00 ls:0 lw:1 lo:1 fc:#fff
circle 340 60 4

style lc:#000 ls:6-2 lw:0.3 lo:0.8
grid 420 20 580 180 40 40
style lc:#000 ls:0 lw:1 lo:1 fc:#000
arrow 420 180 580 180
arrow 420 180 420 20
style lc:#000 ls:0 lw:1 lo:1 fc:#000
circle 420 180 2
style lw:0 fc:#000 fo:1 ts:italic tw:normal tf:Times tz:16px
text 586 183 x
text 418 14 f
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:10px
text 424 16 BC,3
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:16px
text 415 197 0
text 455 197 1
text 495 197 2
text 535 197 3
text 405 185 0
text 405 145 1
text 405 105 2
text 405 65 3
style lc:#f00 ls:0 lw:2 lo:1
line 500 100 540 100
style lc:#f44 ls:6-4-2-4 lw:1 lo:1
line 500 100 500 180
line 540 100 540 180
style lc:#f00 ls:0 lw:1 lo:1 fc:#f00
circle 500 100 4
style lc:#f00 ls:0 lw:1 lo:1 fc:#fff
circle 540 100 4
</oo>


## Step function
Function composed of several functions boxcar $f_{\rm BC}(x)$ is a step function $f_{\rm S}(x)$. Or we can say that a step function $f_{\rm S}(x)$ is a finite linear combination of boxcar functions $f_{\rm BC}(x)$ of intervals, which is simply

\begin{equation}
\label{eqn:vsf-step-function}
{\rm step}(x) = \sum_{i = 1}^N f_{ {\rm BC}, i}(x),
\end{equation}

where each $f_{ {\rm BC}, i}(x)$ has its own values of $A_i$, $a_i$, and $b_i$.

<oo>
svg 400 200 #fafafa fig:vsf-step|A step function $f_{\rm S}(x)$ of four intervals.

style lc:#000 ls:6-2 lw:0.3 lo:0.8
grid 20 20 380 180 40 40
style lc:#000 ls:0 lw:1 lo:1 fc:#000
arrow 20 180 380 180
arrow 20 180 20 20
style lc:#000 ls:0 lw:1 lo:1 fc:#000
circle 20 180 2
style lw:0 fc:#000 fo:1 ts:italic tw:normal tf:Times tz:16px
text 386 183 x
text 18 14 f
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:10px
text 24 16 S
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:16px
text 5 185 0
text 5 145 1
text 5 105 2
text 5 65 3
text 15 197 0
text 55 197 1
text 95 197 2
text 135 197 3
text 175 197 4
text 215 197 5
text 255 197 6
text 295 197 7
text 335 197 8

style lc:#f44 ls:6-4-2-4 lw:1 lo:1
line 100 60 100 140
line 220 140 220 20
line 260 20 260 100
style lc:#f00 ls:0 lw:2 lo:1
line 20 60 100 60
line 100 140 220 140
line 220 20 260 20
line 260 100 340 100
style lc:#f00 ls:0 lw:1 lo:1 fc:#f00
circle 20 60 4
circle 100 140 4
circle 220 20 4
circle 260 100 4
style lc:#f00 ls:0 lw:1 lo:1 fc:#fff
circle 100 60 4
circle 220 140 4
circle 260 20 4
circle 340 100 4
</oo>

Step function $f_{\rm S}(x)$ in Fig. <a href="#fig:vsf-step">3</a> requires $A_1 = 3$, $a_1 = 0$, $b_1 = 2$; $A_2 = 1$, $a_2 = 2$, $b_2 = 5$; $A_3 = 4$, $a_3 = 5$, $b_3 = 6$; and $A_4 = 2$, $a_4 = 6$, $b_4 = 8$. Can $A$ have negative value? Yes, it can. See one of the exercise. Graph in Fig. <a href="#fig:vsf-step">3</a> can also be written in the following more well-known form

\begin{equation}
\label{eqn:vsf-step-function-4-intervals}
f_{\rm S}(x) =
\left\\{
\begin{array}{lr}
3, & 1 \le x \lt 2, \newline
1, & 2 \le x \lt 5, \newline
4, & 5 \le x \lt 6, \newline
2, & 6 \le x \lt 8,
\end{array}
\right. ,
\end{equation}

instead of Eqn. \eqref{eqn:vsf-step-function}. We will use notation similar to Eqn. \eqref{eqn:vsf-step-function} when discussing velocity step function, where in each interval there is simply a ULM.


## Uniform linear motion in each interval
We refer the type of motion discussed in this part as step function velocity or step function ULM (in some books this topic is a part of ULM without any additional name). An ULM $v_n(x)$ in an interval $t_n \le t \lt t_{n + 1}$ is simply

\begin{equation}
\label{eqn:vsf-ulm-v}
v_n(t) = v_{0n},
\end{equation}

where $v_{0n}$ is a constant value at $n$-th interval. And velocty function will be

\begin{equation}
\label{eqn:vsf-ulm-v-function}
v(t) = \sum_{i = 1}^N v_n(x),
\end{equation}

if there are $N$ intervals.

<oo>
svg 400 320 #fafafa fig:vsf-step-5-intv|A step function velocity of five intervals.

style lc:#000 ls:6-2 lw:0.3 lo:0.8
grid 20 20 380 300 40 40
style lc:#000 ls:0 lw:1 lo:1 fc:#000
arrow 20 180 380 180
arrow 20 180 20 20
line 20 205 20 300
style lc:#000 ls:0 lw:1 lo:1 fc:#000
circle 20 180 2
style lw:0 fc:#000 fo:1 ts:italic tw:normal tf:Times tz:16px
text 386 183 t
text 18 14 v
style lw:0 fc:#000 fo:1 ts:normal tw:normal tf:Times tz:16px
text 1 305 -3
text 1 265 -2
text 1 225 -1
text 5 185 0
text 5 145 1
text 5 105 2
text 5 65 3
text 15 197 0
text 55 197 1
text 95 197 2
text 135 197 3
text 175 197 4
text 215 197 5
text 255 197 6
text 295 197 7
text 335 197 8

style lc:#f44 ls:6-4-2-4 lw:1 lo:1
line 100 260 100 20
line 140 20 140 180
line 180 180 180 220
line 300 220 300 60
line 340 60 340 180
style lc:#f00 ls:0 lw:2 lo:1
line 20 260 100 260
line 100 20 140 20
line 140 180 180 180
line 180 220 300 220
line 300 60 340 60
style lc:#f00 ls:0 lw:1 lo:1 fc:#f00
circle 20 260 4
circle 100 20 4
circle 140 180 4
circle 180 220 4
circle 300 60 4
style lc:#f00 ls:0 lw:1 lo:1 fc:#fff
circle 100 260 4
circle 140 20 4
circle 180 180 4
circle 300 220 4
circle 340 60 4
</oo>

Example of step function velocity of five intervals is given in Fig. <a href="#fig:vsf-step-5-intv">4</a>.


## Exercises
1. Suppose that there are two boxcar function with $A_1 = 2$, $a_1 = 1$, $b_1 = 2$ and $A_2 = -2$, $a_2 = 2$, $b_2 = 3$, draw the functions, each in a separated graph.
2. Wite the equation of each boxchar funtion $f_{ {\rm BC}, 1}$, $f_{ {\rm BC}, 2}$, and $f_{ {\rm BC}, 3}$ in Fig. <a href="#fig:fig:vsf-boxchar-example">2</a>.
3. What are the values of $f(7)$,  $f(1)$, and  $f(4)$ from the step function in Fig. <a href="#fig:vsf-step">3</a>?
4. Please write the equation of step function velocity $v(t)$ from graph shown in Fig. <a href="#fig:vsf-step-5-intv">4</a>.
5. Could you also calculate the total displacement of object $\Delta x$ from $t = 0$ to $t = 8 \ \rm s$, whose velocity function is given in Fig. <a href="#fig:vsf-step-5-intv">4</a>? Calculate it if you are able to do that.


## References
1. <a name="ref1"></a>Wikipedia contributors, "Step function", Wikipedia, The Free Encyclopedia, 21 Apr 2020, 04:27 UTC, <https://en.wikipedia.org/w/index.php?oldid=952221804> [20200915].
2. <a name="ref2"></a>Wikipedia contributors, "Boxcar function", Wikipedia, The Free Encyclopedia, 1 Aug 2020, 03:12 UTC, <https://en.wikipedia.org/w/index.php?oldid=852898903> [20200915].

+ [Article history](https://github.com/butiran/butiran.github.io/commits/master/_posts/phys/2020-09-15-step-function-velocity.md)
