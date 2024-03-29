.. _gamma:

Gamma distribution
========================


----


Story
-----

The amount of time we have to wait for :math:`\alpha` arrivals of a Poisson process. More concretely, if we have events, :math:`X_1, X_2, \ldots X_\alpha` that are Exponentially distributed, :math:`X_1 + X_2 + \cdots X_\alpha` is Gamma distributed. While this is the story for an integer number of arrivals, the Gamma distribution is defined for noninteger :math:`\alpha` as well.

----


Example
-------

Any multistep process where each step happens at the same rate. This is common in molecular rearrangements. For example, the time it takes for three phosphorylation events have to happen, assuming all phosphorylation events happen at the same rate, is Gamma distributed.


----

Parameters
----------

The Gamma distribution has two parameter, both strictly positive. The shape parameter, corresponding to the number of arrivals of a Poisson process is :math:`\alpha`. The inverse scale parameter, corresponding to the rate of arrivals, is :math:`\beta`.

----


Support
-------

The Gamma distribution is supported on the set of positive real numbers.



----


Probability density function
----------------------------

.. math::

	\begin{align}
	f(y;\alpha, \beta) = \frac{1}{\Gamma(\alpha)}\,\frac{(\beta y)^\alpha}{y} \,\mathrm{e}^{-\beta y},
	\end{align}

where :math:`\Gamma(\alpha)` is the :ref:`gamma function <Gamma function>`.

----


Cumulative distribution function
--------------------------------

.. math::

    \begin{align}
    F(y;\alpha, \beta) = P(\alpha, \beta y),
    \end{align}

a :ref:`regularized lower incomplete gamma function <Regularized lower incomplete gamma function>`.

----


Moments
-------

Mean: :math:`\displaystyle{\frac{\alpha}{\beta}}`


Variance: :math:`\displaystyle{\frac{\alpha}{\beta^2}}`


----


Usage
-----

+----------------------+----------------------------------------------------+
| Package              | Syntax                                             |
+======================+====================================================+
| **NumPy**            | ``rng.gamma(alpha, 1/beta)``                       |
+----------------------+----------------------------------------------------+
| **SciPy**            | ``scipy.stats.gamma(alpha, loc=0, scale=1/beta)``  |
+----------------------+----------------------------------------------------+
| **Distributions.jl** | ``Gamma(alpha, 1/beta)``                           |
+----------------------+----------------------------------------------------+
| **Stan**             | ``gamma(alpha, beta)``                             |
+----------------------+----------------------------------------------------+

----


Related distributions
---------------------

- The Gamma distribution is the continuous analog of the :ref:`negative_binomial`.
- The special case where :math:`\alpha = 1` is an :ref:`exponential`.
- The special case where :math:`\alpha = \nu/2` and :math:`\beta = 1/2` is a :ref:`chi_square` parametrized by :math:`\nu`.

----


Notes
-----

- The Gamma distribution is useful as a prior for positive parameters. It imparts a heavier tail than the :ref:`half_normal` (but not too heavy; it keeps parameters from growing too large), and allows the parameter value to come close to zero.
- The SciPy implementation has a location parameter, which should be set to zero, with :math:`1/\beta` being the scale parameter.

----


PDF and CDF plots
-----------------

.. bokeh-plot::
    :source-position: none

    import bokeh.io
    import distribution_explorer

    bokeh.io.show(distribution_explorer.explore('gamma', background_fill_alpha=0, border_fill_alpha=0))

----

Links
-----

- `Wikipedia <https://en.wikipedia.org/wiki/Gamma_distribution>`_
- `Numpy <https://docs.scipy.org/doc/numpy/reference/random/generated/numpy.random.Generator.gamma.html>`_
- `Scipy <https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.gamma.html>`_
- `Distributions.jl <https://juliastats.org/Distributions.jl/stable/univariate/#Distributions.Gamma>`_
- `Stan <https://mc-stan.org/docs/2_21/functions-reference/gamma-distribution.html>`_
