Preliminares acerca de Álgebras de Hopf
========================================

Álgebras de Hopf
-----------------

Como hemos visto en el ejemplo de las teorías de cuerpos cuánticos topológicos bidimensionales, la anillo de grupo complejo :math:`A = \mathbb{C}G` de un grupo finito :math:`G` tiene mucha estructura algebraica. En primer lugar, es un álgebra sobre :math:`\mathbb{C}` con respecto a la multiplicación

.. math::

    \begin{align}
        \mu : A &\otimes A \to A ;&&&
        \left(\sum_{g\in G} \lambda_{g}g\right) &\otimes \left(\sum_{g\in G}\rho_{h} h\right)\mapsto \sum_{g,h\in G} \lambda_{g} \rho_{h} gh
    \end{align}

con unidad :math:`e \in G \subset \mathbb{C}G`. Dual a esta noción :math:`\mathbb{C}G` también lleva una estructura de coalgebra, que la convierte en una biálgebra_ en el sentido de la siguiente definición [5].

.. _biálgebra:

Biálgebra
~~~~~~~~~

Una bialgebra :math:`A` sobre un cuerpo :math:`\mathbb{F}` es una tupla :math:`(A, \mu, u, \Delta, \epsilon)`, tal que :math:`(A, \mu, u)` es un álgebra sobre :math:`\mathbb{F}` con multiplicación :math:`\mu: A \otimes A \to A` y unidad :math:`u: \mathbb{F} \to A` junto con una comultiplicación :math:`\Delta: A \to A\otimes A` y un couinidad :math:`\epsilon :A \to \mathbb{F}`, tal que :math:`\Delta` y :math:`\epsilon` son homomorfismos de álgebra. Los axiomas del álgebra (asociatividad y unidad) están codificados en la conmutatividad de los siguientes diagramas

en el que las flechas sin etiquetar marcan los isomorfismos canónicos. Los axiomas de una coálgebra producen la conmutatividad de

y la compatibilidad de ambas estructuras obliga a los siguientes diagramas a conmutar


donde las flechas sin marcar son nuevamente canónicas y :math:`\tau: A^{\otimes 4} \to A^{\otimes 4}` viene dado por :math:`\tau (a \otimes b \otimes c \otimes d) = a \otimes c \otimes b \otimes d`.

Ejemplo
~~~~~~~~

El álgebra de grupo complejo :math:`A = \mathbb{C}G` con la multiplicación y unidad anteriores junto con la multiplicación

.. math::
    
    \begin{align}
        \Delta: A &\to A \otimes A &&;& \sum_{g\in G}\lambda_{g} g &\mapsto \sum_{g\in G}\lambda g (g \otimes g)
    \end{align}

y counidad

.. math::
    
    \begin{align}
        \epsilon :A &\to \mathbb{C} &&;&\sum_{g\in G} \lambda_{g} g &\mapsto \sum_{g\in G} \lambda_{g}
    \end{align}

es una biálgebra_. (ejercicio)


.. warning::
    
    Hemos visto que :math:`A = \mathbb{C}G` también lleva una traza
    
    .. math::

        \begin{align}
            tr: A &\to \mathbb{C} &&;& \sum_{g\in G} \lambda_{g} g \mapsto \lambda_{e},
        \end{align}
        
        
    
    lo que le confiere la estructura de un álgebra de Frobenius. La estructura de coalgebra obtenida a partir de esto se diferencia de la de la definición anterior en que las condiciones (1) y (2) no se satisfacen para ella. La comultiplicación :math:`\delta: A \to A \otimes A` de un álgebra de Frobenius solo tiene que ser un homomorfismo de :math:`A`-módulo, mientras que para una bialgebra exigimos que :math:`\Delta: A \to A \otimes A` sea un homomorfismo de álgebra con respecto a la estructura del álgebra en :math:`A`. Por lo tanto, las álgebras y bialgebras de Frobenius deben considerarse como dos tipos diferentes de estructuras.
    

El álgebra de grupo :math:`A = \mathbb{C}G` tiene otra característica no codificada en la estructura de bialgebra: cada elemento de grupo tiene una inversa. Esto lleva a la siguiente definición

.. _antípoda:

Antípoda
~~~~~~~~

Sea :math:`A` una biálgebra_. Un homomorfismo :math:`\mathbb{F}`-lineal :math:`\mathcal{S}: A \to A` se llama antípoda si encaja en el siguiente diagrama conmutativo

.. _Hopf:

Álgebra de Hopf
~~~~~~~~~~~~~~~

Una biálgebra_ :math:`A` junto con una antípoda_ :math:`\mathcal{S}: A \to A` se llama álgebra de Hopf.

Ejemplo
~~~~~~~

El álgebra de grupo :math:`A = \mathbb{C}G` es un álgebra de Hopf_ con la antípoda_

.. math::
    
    \mathcal{S} \left(\sum_{g\in G} \lambda_{g}g\right) = \sum_{g\in G} \lambda_{g}g^{-1}.

.. note::
    
    Usando :math:`\Delta` y :math:`\mu` podemos dotar a :math:`Hom (A, A)` de una estructura de álgebra:
    
    - Sea :math:`f`, :math:`g \in Hom (A, A)`. Entonces definimos
    
    .. math::
        
        f \ast g : A \stackrel{\Delta}{\longrightarrow} A \otimes A \stackrel{f\otimes g}{\longrightarrow} A \otimes A \stackrel{\mu}{\longrightarrow} A
        
    Esta multiplicación, que es diferente de la canónica dada por composición, convierte a :math:`Hom (A, A)` en un álgebra.
    
    - La unidad con respecto a :math:`\ast` viene dada por
    
    .. math::
        
        u \circ \epsilon : A \to k \to A.
        
    Por lo tanto, la condición de que :math:`\mathcal{S}: A \to A` sea una antípoda_ significa que es una inversa de :math:`id_{A}` con respecto a :math:`\ast`, es decir, :math:`id_{A}\ast S = S \ast id_{A} = u \circ \epsilon`. Desentrañar la definición de :math:`\ast` produce el diagrama conmutativo en la definición de antípoda_.


Lema
~~~~

*Sea* :math:`A` *un álgebra de Hopf sobre un cuerpo* :math:`\mathbb{F}`, *que es de dimensión finita como un* :math:`\mathbb{F}`-*espacio vectorial. Entonces su espacio dual* :math:`A^{\ast} = Hom (A, \mathbb{F})` *se describe de manera canónica en la prueba nuevamente como un álgebra de Hopf.*

**Demostración:**

Dado que :math:`(A \otimes A)^{\ast} = A^{\ast} \otimes A^{\ast}` en el caso de dimensión finita, el espacio :math:`A^{\ast}` es una bialgebra con multiplicación :math:`\mu ' = \Delta^{\ast}: A^{\ast} \otimes A^{\ast} \to A^{\ast}`, unidad :math:`u ' =\epsilon^{\ast}: \mathbb{F} \to A^{\ast}`, comultiplicación :math:`\Delta ' = \mu^{\ast}: A^{\ast} \to A^{\ast} \otimes A^{\ast}` y counidad :math:`\epsilon' = u^{\ast}: A^{\ast} \to \mathbb{F}`. Dado que el funtor dualizante es contravariante, convierte los dos primeros diagramas de la definición 1.1 en los dos segundos diagramas y viceversa. La condición de compatibilidad de la comultiplicación :math:`\Delta` y la counidad :math:`\epsilon` fue que son homomorfismos de álgebra. Al girar 90 grados los diagramas (1) y (2), vemos que esta condición es equivalente al hecho de que :math:`\mu` y :math:`u` son homomorfismos de coalgebra.

Por lo tanto, los diagramas correspondientes para :math:`\Delta '`, :math:`\mu '`, :math:`\epsilon '` y :math:`u '` siguen conmutando.

Si aplicamos el funtor dualizante al diagrama de definición de la antípoda dado en la definición 1.3, se deduce de la simetría de ese diagrama que :math:`\mathcal{S}^{\ast}: A^{\ast} \to A^{\ast}` es una antípoda de la bialgebra :math:`A^{\ast}`.

