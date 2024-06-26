Special functions
=================

Some PDFs and PMFs and many CDFs are expressed in terms of `special functions <https://en.wikipedia.org/wiki/Special_functions>`_. Here, for reference, are special functions featured in various distributions in the Distribution Explorer. In general, these functions are functions of complex variables, but for our purposes we will only consider real numbers.


Factorial
---------

The `factorial <https://en.wikipedia.org/wiki/Factorial>`_ of a positive real number :math:`n` is denoted as :math:`n!` and is defined as

.. math::

	\begin{align}
	n! = n \cdot (n-1) \cdot (n-2) \cdots 1,
	\end{align}

with the convention that :math:`0! = 1`.

----

Binomial coefficient
--------------------

A Binomial coefficient of two nonnegative real numbers :math:`N` and :math:`n`, with :math:`n \le N`, is denoted as :math:`\displaystyle \begin{pmatrix}N \\n\end{pmatrix}`, and is defined as

.. math::

	\begin{align}
	\begin{pmatrix}N \\n\end{pmatrix} = \frac{N!}{n!(N-n)!}.
	\end{align}

----

Gamma function
--------------

The `gamma function <https://en.wikipedia.org/wiki/Gamma_function>`_, :math:`\Gamma(x)`, may be thought of as a continuous generalization of the factorial. For positive integer :math:`n`, :math:`\Gamma(n) = (n-1)!`. The Gamma function for positive real :math:`x` is

.. math::

	\begin{align}
	\Gamma(x) = \int_0^\infty\mathrm{d}t\,t^{x-1}\mathrm{e}^{-t}.
	\end{align}

----

Lower incomplete gamma function
-------------------------------

Notice that the integral in the gamma function runs from zero to infinity. If we instead truncate the integration at :math:`y`, we get the `lower incomplete gamma function <https://en.wikipedia.org/wiki/Incomplete_gamma_function>`_,

.. math::

	\begin{align}
	\gamma(x, y) = \int_0^y \mathrm{d}t \, t^{x-1}\mathrm{e}^{-t}.
	\end{align}

Note that the function is denoted with a lowercase :math:`\gamma`.

----

Upper incomplete gamma function
-------------------------------

Similarly, the `upper incomplete gamma function <https://en.wikipedia.org/wiki/Incomplete_gamma_function>`_ results from beginning the integral in the gamma function at :math:`x`.

.. math::

	\begin{align}
	\Gamma(x, y) = \int_y^\infty \mathrm{d}t \, t^{x-1}\mathrm{e}^{-t}.
	\end{align}

Note that am uppercase :math:`\Gamma` is used, but the presence of two arguments distinguishes this function notationally from the gamma function.

----

Regularized lower incomplete gamma function
-------------------------------------------

When we divide the lower incomplete gamma function by the corresponding complete gamma function, we get a regularized lower incomplete gamma function, often denoted :math:`P(x, y)`.

.. math::

	\begin{align}
	P(x, y) = \frac{\gamma(x, y)}{\Gamma(x)}.
	\end{align}

Regularized upper incomplete gamma function
-------------------------------------------

Similarly, the upper incomplete gamma function may also be regularized, and is often denoted :math:`Q(x, y)`.

.. math::

	\begin{align}
	Q(x, y) = \frac{\Gamma(x, y)}{\Gamma(x)}.
	\end{align}




Beta function
-------------

The `beta function <https://en.wikipedia.org/wiki/Beta_function>`_ is

.. math::

	\begin{align}
	B(x, y) = \frac{\Gamma(x)\Gamma(y)}{\Gamma(x + y)}.
	\end{align}

The beta function may be expressed as an integral,

.. math::

	\begin{align}
	B(x, y) = \int_0^1\mathrm{d}t\,t^{x-1} (1-t)^{y-1}.
	\end{align}

When :math:`x` and :math:`y` are integers, say :math:`m` and :math:`n`, the beta function is related to the binomial coefficient as

.. math::

	\begin{align}
	B(m, n) = \frac{(m+n)/mn}{\displaystyle \begin{pmatrix}N \\n\end{pmatrix}}.
	\end{align}

----

Multivariate beta function
--------------------------

The beta function may be generalized to a multivariate case, called the `multivariate Beta function <https://en.wikipedia.org/wiki/Beta_function#Multivariate_beta_function>`_.

.. math::

    \begin{align}
    B(\boldsymbol{\alpha}) = \frac{\prod_{i=1}^K\Gamma(\alpha_i)}{\Gamma\left(\sum_{i=1}^K \alpha_i\right)}
    \end{align}

----

Incomplete beta function
------------------------

Looking at the integral form of the beta function, above, we can define an `incomplete beta function <https://en.wikipedia.org/wiki/Beta_function#Incomplete_beta_function>`_ by truncating the integral. The incomplete beta function is denoted :math:`B(x; a, b)`.

.. math::

	\begin{align}
	B(x; a, b) = \int_0^x\mathrm{d}t\,t^{a-1} (1-t)^{b-1}.
	\end{align}

Note that :math:`x` must be between zero and one.

----

Regularized incomplete beta function
------------------------------------

The `regularized incomplete beta function <https://en.wikipedia.org/wiki/Beta_function#Incomplete_beta_function>`_. :math:`I_x(a,b)` is computed by dividing the incomplete beta function by the corresponding beta function.

.. math::

	\begin{align}
	I_x(a, b) = \frac{B(x; a, b)}{B(a, b)} = \frac{\int_0^x\mathrm{d}t\,t^{a-1} (1-t)^{b-1}}{\int_0^1\mathrm{d}t\,t^{x-1} (1-t)^{y-1}}.
	\end{align}

----

Error function
--------------

The `error function <https://en.wikipedia.org/wiki/Error_function>`_, :math:`\text{erf}(x)` is defined by

.. math::

	\begin{align}
	\text{erf}(x) = \frac{2}{\sqrt{\pi}}\int_0^x \mathrm{d}t\,\mathrm{e}^{-t^2}.
	\end{align}

----

Modified Bessel function of the first kind
------------------------------------------

`Bessel functions <https://en.wikipedia.org/wiki/Bessel_function>`_ are solutions to Bessel's differential equation, which appears in solutions to diffusion problems in cylindrical coordinates. Modified Bessel functions of the first kind appear in the analysis of the Von Mises distribution. For integer :math:`\alpha`, these are given by

.. math::

	\begin{align}
	I_\alpha(x) = \frac{1}{\pi}\int_0^\pi\,\mathrm{d}\theta\,\cos(\alpha\theta)\,\mathrm{e}^{x\cos\theta},
	\end{align}

and can also be expressed as a series

.. math::

	\begin{align}
	I_\alpha(x) = \left(\frac{x}{2}\right)^n\sum_{k=0}^\infty\frac{(x/2)^{2k}}{k!\,\Gamma(\alpha + k + 1)},
	\end{align}

where :math:`\Gamma(x)` denotes the `gamma function <Gamma function>`_.

