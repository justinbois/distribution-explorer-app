.. _negative_binomial:

Negative Binomial distribution
==============================

----


Story
-----

We perform a series of Bernoulli trials with probability :math:`\beta/(1+\beta)` of success. The number of failures, :math:`y`, before we get :math:`\alpha` successes is Negative Binomially distributed. 

An equivalent story is that the sum of :math:`\alpha` independent and identically Gamma distributed variables is Negative Binomially distributed. For this reason, the Negative Binomial distribution is sometimes called the Gamma-Poisson distribution.


----


Example
-------

Bursty gene expression can give mRNA count distributions that are Negative Binomially distributed. Here, "success" is that a burst in gene expression stops. In this case, the parameter :math:`1/\beta` is the mean number of transcripts in a burst of expression. The parameter :math:`\alpha` is related to the frequency of the bursts.  If multiple bursts are possible within the lifetime of mRNA, then :math:`\alpha > 1`. Then, the number of "failures" is the number of mRNA transcripts that are made in the characteristic lifetime of mRNA.


----

Parameters
----------

There are two parameters: :math:`\alpha`, the desired number of successes, and :math:`\beta`, which is the mean of the :math:`\alpha` identical Gamma distributions that give the Negative Binomial. The probability of success of each Bernoulli trial is given by :math:`\beta/(1+\beta)`.




----


Support
-------

The Negative-Binomial distribution is supported on the set of nonnegative integers.


----


Probability mass function
-------------------------

.. math::

    \begin{align}
    f(y;\alpha,\beta) = \begin{pmatrix}
    y+\alpha-1 \\
    \alpha-1
    \end{pmatrix}
    \left(\frac{\beta}{1+\beta}\right)^\alpha \left(\frac{1}{1+\beta}\right)^y.
    \end{align}

Generally speaking, :math:`\alpha` need not be an integer, so we may write the PMF as

.. math::

    \begin{align}
    f(y;\alpha,\beta) = \frac{\Gamma(y+\alpha)}{\Gamma(\alpha) \, y!}\,\left(\frac{\beta}{1+\beta}\right)^\alpha \left(\frac{1}{1+\beta}\right)^y.
    \end{align}

See the notes below for other parametrizations.


----


Usage
-----

+---------------------------------------+-------------------------------------------------------+
| Package                               | Syntax                                                |
+=======================================+=======================================================+
| **NumPy**                             | ``rg.negative_binomial(alpha, beta/(1+beta))``        |
+---------------------------------------+-------------------------------------------------------+
| **SciPy**                             | ``scipy.stats.nbinom(alpha, beta/(1+beta))``          |
+---------------------------------------+-------------------------------------------------------+
| **Stan**                              | ``neg_binomial(alpha, beta)``                         |
+---------------------------------------+-------------------------------------------------------+
| **Stan with (µ, φ) parametrization**  | ``neg_binomial_2(mu, phi)``                           |
+---------------------------------------+-------------------------------------------------------+

----

Related distributions
---------------------

- The :ref:`geometric` is a special case of the Negative Binomial distribution in which :math:`\alpha=1` and :math:`\theta = \beta/(1+\beta)`.
- The continuous analog of the Negative Binomial distribution is the :ref:`gamma`. 
- In a certain limit, which is easier considered using the :math:`(\mu,\phi)` parametrization below, the Negative Binomial distribution becomes a :ref:`poisson`. See the note below for this limit.


----

Notes
-----

- The Negative Binomial distribution may be parametrized such that the probability mass function is

.. math::

    \begin{align}
       f(y;\mu,\phi) = \frac{\Gamma(y+\phi)}{\Gamma(\phi) \, y!}\,\left(\frac{\phi}{\mu+\phi}\right)^\phi\left(\frac{\mu}{\mu+\phi}\right)^y. 
    \end{align}

These parameters are related to the parametrization above by :math:`\phi = \alpha` and :math:`\mu = \alpha/\beta`. In the limit of :math:`\phi\to\infty`, which can be taken for the PMF, the Negative Binomial distribution becomes Poisson with parameter :math:`\mu`. This also gives meaning to the parameters :math:`\mu` and :math:`\phi; :math:`\mu` is the mean of the Negative Binomial, and :math:`\phi` controls extra width of the distribution beyond Poisson. The smaller :math:`\phi` is, the broader the distribution.

- In Stan, the Negative Binomial distribution using the :math:`(\mu,\phi)` parametrization is called ``neg_binomial_2``.
- SciPy and NumPy use yet another parametrization. The PMF for SciPy is

.. math::

    \begin{align}
       f(y;n, p) = \frac{\Gamma(y+n)}{\Gamma(n) \, y!}\,p^n \left(1-p\right)^y. 
    \end{align}

The parameter :math:`p` is the probability of success of a Bernoulli trial. The parameters are related to the others we have defined by :math:`n=\alpha=\phi` and :math:`p=\beta/(1+\beta) = \phi/(\mu+\phi)`.

----


PMF and CDF plots
-----------------

In the α-β formulation:

.. bokeh-plot::
    :source-position: none

    import bokeh.io
    import distribution_explorer

    bokeh.io.show(distribution_explorer.explore('negative_binomial'))


|


In the µ-φ formulation:

.. bokeh-plot::
    :source-position: none

    import bokeh.io
    import distribution_explorer

    bokeh.io.show(distribution_explorer.explore('negative_binomial_mu_phi'))

----

Links
-----

- `Wikipedia <https://en.wikipedia.org/wiki/Negative_binomial_distribution>`_
- `Numpy <https://docs.scipy.org/doc/numpy/reference/random/generated/numpy.random.Generator.negative_binomial.html>`_
- `Scipy <https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.nbinom.html>`_
- `Stan α-β formulation <https://mc-stan.org/docs/2_21/functions-reference/negative-binomial-distribution.html>`_
- `Stan µ-φ formulation formulation <https://mc-stan.org/docs/2_21/functions-reference/nbalt.html>`_
