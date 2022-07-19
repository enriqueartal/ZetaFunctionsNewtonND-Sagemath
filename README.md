# ZetaFunctionsNewtonND-Sagemath

_A `Sagemath` class for computing (local) Igusa and topological zeta functions for Newton-non-degenerated polynomials_

The file `ZetaFunctionsNewtonND.py` provides a class (the `ZetaFunctions` class) in Sagemath together with methods in order to study and compute local and global Igusa and topological zeta functions for Newton-non-degenerated polynomials.

This class is initialized with a multivariate polynomial and creates an object with several functions for computing the previous zeta functions whenever the associated polynomial is Newton-non-degenerated. Also, several methods to study the associated Newton polyhedron, its faces, dual cones, and possible candidate poles are provided.

This implementation is based in the formulas given in **[DH01]**, **[DL92]** and **[Var76]** and an initial `Maple` program by K. Hoornaert and D. Loots in **[HL00]**. I would like to thank [Frédéric Chapoton](https://irma-web1.math.unistra.fr/~chapoton/) (Univ. Strasbourg), who improved outputs, handling errors and symbolic variables in a middle-stage version of this computer program.

## Prerequisites

- `Sagemath>=v9.4`.

## A minimal example

First, you should download `ZetaFunctionsNewtonND.py` and locate it in your working folder.

A minimal example could be:

```python
sage: load('ZetaFunctionsNewtonND.py')
sage: R.<x,y,z,t> = QQ[]
sage: zex = ZetaFunctions(x^4 + y^3*z^3+y^3*t^3+z^3*t^3)
sage: zex.topological_zeta(local = True)
(1/4) * (s + 3/4)^-1 * (s + 11/12)^-1 * (s + 1)^-1 * (s^2 + 23/12*s + 11/4)
sage: zex.monodromy_zeta()
(t - 1)^-8 * (t + 1)^-8 * (t^2 + 1)^-17 * (t^2 - t + 1)^-9 * (t^2 + t + 1)^-9 * (t^4 - t^2 + 1)^-18
```

You can find much more examples and explanations in the Jupyter notebook [`Examples_ZetaFunctions.ipynb`](https://github.com/jviusos/ZetaFunctionsNewtonND-Sagemath/blob/main/Examples_ZetaFunctions.ipynb).

## Methods in `ZetaFunctions`

- `cones_plot(self, **kwargs)`

- `dict_info_poles(self, d=1, weights=None, local=False)`

- `get_newton_polyhedron(self)`

- `get_polyfaces_dictionary(self, keys = 'polynomials', compact = False)`

- `give_expected_pole_info(self, d=1, local=False, weights=None)`

- `give_info_facets(self, compact = False)`

- `give_info_newton(self, faces=False, cones=False, compact = False)`

- `is_newton_degenerated(self, p=None, local=False, method='default', info = False)`

- `newton_plot(self, point_size = 30, **kwargs)`

- `igusa_zeta(self, p=None, dict_Ntau={}, local=False, weights=None, info=False, check='ideals')`

- `topological_zeta(self, d=1, local=False, weights=None, info=False, check='ideals')`

- `monodromy_zeta(self, char=False, info=False, check='ideals')`

## References

**[DH01]** Denef, J. and Hoornaert, K., *Newton Polyhedra and Igusa's Local Zeta Function*, 2001. [*J. Number Theory*](https://mathscinet.ams.org/mathscinet/search/journaldoc.html?id=3003) [89](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=193003) [(2001),](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=193003) [no. 1,](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=193003) 31–64.

**[DL92]** Denef, J. and Loeser, F., *Caracteristiques d'Euler-Poincare, fonctions zeta locales et modifications analytiques*, [*J. Amer. Math. Soc.*](https://mathscinet.ams.org/mathscinet/search/journaldoc.html?id=3464) [5](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=118748) [(1992),](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=118748) [no. 4,](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=118748) 705–720.

**[HL00]** Hoornaert, K. and Loots, D., [*Computer program written in Maple for the calculation of Igusa's local zeta function*](http://www.wis.kuleuven.ac.be/algebra/kathleen.htm), (2000).

**[Var76]** Varchenko, A. N., *Zeta-function of monodromy and Newton's diagram*.  [*Invent. Math.*](https://mathscinet.ams.org/mathscinet/search/journaldoc.html?id=449) [37](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=392830) [(1976),](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=392830) [no. 3,](https://mathscinet.ams.org/mathscinet/search/publications.html?pg1=ISSI&s1=392830) 253–262.

**[Viu12]** Viu-Sos, J., [*Funciones zeta y poliedros de Newton: Aspectos teoricos y computacionales*](https://zaguan.unizar.es/record/8916/files/TAZ-TFM-2012-749.pdf), Master Thesis, (2012). 

## Authors

- Kathleen Hoornaert (2000): initial version for Maple

- Juan Viu-Sos (2012): initial version for Sage

- Frédéric Chapoton (2017): improved outputs, handling errors and symbolic variables 

- Juan Viu-Sos (2022): improved methods and new functions in the class to visualize Newton polyhedra

## Contact

For any question or comment, please email me: [juan.viu.sos@upm.es](mailto:juan.viu.sos@upm.es)
