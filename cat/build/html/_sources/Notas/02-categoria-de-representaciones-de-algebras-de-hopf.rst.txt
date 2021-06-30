Categoría de Representaciones de Álgebras de Hopf
===================================================

Las representaciones de dimensión finita de un grupo finito :math:`G` dan un ejemplo sencillo de una categoría monoidal rígida con simetría. En esta sección generalizaremos este concepto al caso de las álgebras de Hopf.

.. _representacion-de-un-algebra:

Representación de un álgebra
----------------------------

Sea :math:`A` un álgebra sobre el cuerpo :math:`\mathbb{F}`. Una representación de :math:`A` es un :math:`\mathbb{F}`-espacio vectorial :math:`V` junto con un homomorfismo de álgebra :math:`\pi: A \to End (V)`.

.. _representaciones-equivalentes:

Representaciones Equivalentes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Dos representaciones :math:`\pi` en :math:`V` y :math:`\pi'` en :math:`W` se denominan equivalentes si existe un isomorfismo :math:`T: V \to W` tal que para todo :math:`a \in A` y :math:`v \in V`

.. math::

    T \pi(a) v = \pi'(a) Tv.


Un mapa :math:`\mathbb{F}`-lineal :math:`T: V \to W` que satisface (3) para todo :math:`a \in A` y :math:`v \in V` se llamará homomorfismo equivariante o entrelazado.

Representaciones de dimensión finita
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Sea :math:`(V, \pi)` una representación. Una representación :math:`V` se llama de dimensión finita, si :math:`dim (V) < \infty`.

.. _subespacios-invariantes:

Subespacios Invariantes
~~~~~~~~~~~~~~~~~~~~~~~~

Sea :math:`(V, \pi)` una representación. Un subespacio :math:`U \subset V` se llama invariante, si :math:`\pi (A) U \subset U`.

Representación Irreducible
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Una representación :math:`V` se llama irreducible, si :math:`0` y :math:`V` son sus únicos :ref:`subespacios-invariantes`.

La categoría Rep(A)
~~~~~~~~~~~~~~~~~~~

Denotamos :math:`Rep(A)` a la categoría con objetos las representaciones de dimensión finita de :math:`A` y con los entrelazados como morfismos. Las clases de equivalencia de representaciones corresponden a clases de isomorfismo de objetos en esta categoría.

.. note::

    La mayoría de las personas dirían :math:`A`-módulo (a izquierda) en lugar de representación. Nos atenemos a nuestra notación, debido a la estrecha conexión entre las álgebras de Hopf y la teoría de grupos.


En caso de que :math:`A` sea una :ref:`biálgebra`, la categoría :math:`Rep(A)` se puede dotar con un producto tensorial de la siguiente manera:
     
- Sea :math:`(V, \pi_{V}), (W, \pi_{W}) \in Obj(Rep(A))`, entonces el producto tensorial :math:`V \otimes W` sobre :math:`\mathbb{F}` es nuevamente una representación con la acción de :math:`A` dada por

    .. math::

        \pi_{V}\ast\pi_{W}:A\stackrel{\Delta}{\longrightarrow}A \otimes A\stackrel{\pi_{V}\otimes\pi_{W}}{\longrightarrow} End(V) \otimes End(W)\longrightarrow End(V \otimes W)


El cuerpo :math:`\mathbb{F}` también proporciona una representación vía la counidad :math:`\pi_{\mathbb{F}}= \epsilon: A \to \mathbb{F} = Hom (\mathbb{F}, \mathbb{F})`, es decir,

.. math::

    a \cdot \lambda = \epsilon (a) \cdot \lambda \text{ para } a \in A, \lambda \in \mathbb{F}.
    
Es fácil comprobar que :math:`(V\otimes \mathbb{F}, \pi_{V}\ast\pi_{\mathbb{F}})` y :math:`(\mathbb{F}\otimes V, \pi_{\mathbb{F}} \ast\pi_{V})` son naturalmente isomorfos a :math:`(V, \pi_{V})` a través del isomorfismo obvio. Esto resulta ser la unidad tensorial en la categoría monoidal.

Sea :math:`\tau_{V,W} : V \otimes W \to W \otimes V` el mapa twist canónico y sea :math:`\tau = \tau_{A,A}`. Observemos que

.. math::

    \tau_{V,W} \circ (\pi_{V} \ast \pi_{W})(a) \circ \tau_{V,W}^{-1} = (\pi_{W} \ast^{op} \pi_{V})(a),

donde :math:`\pi_{W}\ast^{op}\pi_{V}` está definido por

.. math::

    \pi_{W}\ast^{op}\pi_{V}:A \stackrel{\Delta}{\longrightarrow}A \otimes A\stackrel{\tau}{\longrightarrow}A \otimes A\stackrel{\pi_{W}\otimes\pi_{V}}{\longrightarrow} End(W \otimes V)

Dado que :math:`\tau \circ \Delta` puede no coincidir con :math:`\Delta`, los objetos :math:`(V \otimes W, \pi_{V} \ast \pi_{W})` y :math:`(W \otimes V, \pi_{W}\ast\pi_{V})` pueden ser no isomorfos en :math:`Rep(A)`. Para obtener una categoría monoidal trenzada, necesitamos más estructura en la :ref:`biálgebra` :math:`A`.

.. _matriz-universal:

R-matriz universal
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Sea :math:`A` una :ref:`biálgebra`. Un elemento :math:`R \in A\otimes A` se llama :math:`R`-matriz universal, si es invertible y satisface los siguientes axiomas:

    :math:`a)` :math:`(\tau \circ \Delta)(a) R = R \Delta(a)`,
    
    :math:`b)` :math:`(id_{A} \otimes \Delta) (R) = R_{13} R_{12}`,

    :math:`a)` :math:`(\Delta \otimes id_{A}) (R) = R_{13} R_{23}.`

Aquí usamos la siguiente notación: Si :math:`R = \sum_{i} a_{i} \otimes b_{i} \in A \otimes A`, entonces

.. math::

    \begin{align}
        R_{12} &= \sum_{i} a_{i} \otimes b_{i} \otimes 1.\\ 
        R_{13} &= \sum_{i} a_{i} \otimes 1 \otimes b_{i},\\
        R_{23} &= \sum_{i} 1 \otimes a_{i} \otimes b_{i}.
    \end{align}

.. _cuasi-triangular:

Biálgebra cuasi-triangular
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Una :ref:`biálgebra` :math:`A` junto con una :ref:`matriz-universal` se llama cuasi-triangular_.


.. _una-trenza-en-la-categoria-monoidal:

Lema
~~~~

Sea :math:`A` una biálgebra cuasi-triangular_ con :ref:`matriz-universal` :math:`R`. Entonces

.. math::

    \sigma_{V,W} : V \otimes W \stackrel{(\pi_{V}\otimes\pi_{W})(R)}{\longrightarrow}  V \otimes W \stackrel{\tau_{V,W}}{\longrightarrow} W \otimes V

es una trenza en la categoría monoidal :math:`Rep(A)`.

**Demostración:**

Primero tenemos que demostrar que :math:`\sigma_{V,W}` es equivariante con respecto a las acciones :math:`\pi_{V} ​​\ast \pi_{W}` y :math:`\pi_{W} ​​\ast \pi_{V}` sobre :math:`V \otimes W` y :math:`W \otimes V` respectivamente. Esto se sigue del pequeño cálculo

.. math::

    \begin{align}
        \sigma_{V,W}(\pi_{V}\otimes\pi_{W})(\Delta(a))&=\tau_{V,W}(\pi_{V} \otimes\pi_{W})(R)(\pi_{V}\otimes\pi_{W})(\Delta(a))\\
                                                &= \tau_{V,W}(\pi_{V} \otimes \pi_{W})(R \Delta(a))\\
                                                &= \tau_{V,W}(\pi_{V} \otimes \pi_{W})(\tau \Delta(a)) (\pi_{V} \otimes \pi_{W})(R)\\
                                                &= (\pi_{W} \otimes \pi_{V})(\Delta(a)) \tau_{V,W}(\pi_{V} \otimes \pi_{W})(R)\\
                                                &= (\pi_{W} \otimes \pi_{V})(\Delta(a)) \sigma_{V,W}
    \end{align}

donde usamos el punto :math:`a)` de la Definición de :ref:`matriz-universal`. Ahora sean :math:`V_{1}`, :math:`V_{2}` y :math:`V_{3}` tres representaciones de :math:`A` y denoten por :math:`\alpha_{ijk}` los asociados correspondientes del producto tensorial. La conmutatividad del diagrama de trenzado.

se desprende de la siguiente observación, en la que descuidamos a todos los asociados:

.. math::

    \begin{align}
        \sigma_{1,23} &= ​​\tau_{1,23} ​​\pi_1 ​​\otimes (​​\pi_2 \ast ​​\pi_3)(R)\\
                    &= ​​\tau_{1,23} (​​\pi_1 ​​\otimes ​​\pi_2 ​​\otimes ​​\pi_3)(id_{A} ​​\otimes \Delta)(R)\\
                    &= ​​\tau_{1,23} (​​\pi_1 ​​\otimes ​​\pi_2 ​​\otimes ​​\pi_3)(​​R_{13} ​​R_{12})\\
                    &= (​​id_{2}\otimes​​\tau_{1,3})(​​\tau_{1,2}​​\otimes ​​id_{3})(​​\pi_1​​\otimes​​\pi_2​\otimes​​\pi_3)(​​R_{13} ​​R_{12})\\
                    &= (​​id_{2}\otimes​​\tau_{1,3})(​​\tau_{1,2}​​\otimes ​​id_{3})(​​\pi_1​​\otimes​​\pi_2​​\otimes​​\pi_3)(​​R_{13})(​​\pi_1 \otimes ​​\pi_2 ​​\otimes ​​\pi_3)(​​R_{12})\\
                    &= (​​id_{2} ​​\otimes ​​\tau_{1,3}) ​​id_{2} ​​\otimes (​​\pi_1 ​​\otimes ​​\pi_3)(R) (​​\tau_{1,2} ​​\otimes ​​id_{3}) (​​\pi_1 ​​\otimes ​​\pi_2)(R) ​​\otimes ​​id_{3}\\
                    &= (​​id_{2} ​​\otimes \sigma_{1,3}) \circ (\sigma_{1,2} ​​\otimes ​​id_{3})
    \end{align}

Aquí usamos la propiedad :math:`b)` de la Definición de :ref:`matriz-universal`. El diagrama correspondiente para :math:`\sigma^{-1}` finalmente usa la propiedad :math:`c)`. :math:`\blacksquare`


.. note::
    
    Lo contrario de la declaración anterior también es cierto en el caso de que :math:`A` sea una :ref:`biálgebra` de dimensión finita, ya que entonces :math:`A \in Obj (Rep (A))`. Entonces tenemos: Si :math:`Rep (A)` es trenzada, entonces :math:`A` es cuasi-triangular_. La :ref:`matriz-universal` en este caso está dada por :math:`R = \tau (\sigma_{A, A} (1 \otimes 1)) \in A \otimes A`.

Álgebras de Hopf y Duales.
----------------------------

Como hemos visto en la última sección, la categoría de representación de una :ref:`biálgebra` :math:`A` es monoidal. Si :math:`A` es cuasi-triangular_, entonces :math:`Rep (A)`) incluso es trenzada.

Usando la categoría de representaciones de dimensión finita de un grupo finito como guía, la siguiente estructura a considerar es la de representaciones duales: si :math:`V` es una representación de :math:`G`, entonces :math:`G` también actúa sobre el espacio dual :math:`V^{\ast}` vía :math:`\xi \mapsto g \cdot \xi` con :math:`(g \cdot \xi) (v) = \xi (g^{-1} \cdot v)` para :math:`\xi \in V \ast`, :math:`v \in V` y :math:`g\in G`. Generalizaremos esto al caso de las álgebras de Hopf. Para lograr esto, necesitamos las siguientes propiedades de la antípoda:

Lema
~~~~

Sea :math:`A` un álgebra de Hopf con antípoda :math:`\mathcal{S}`, entonces tenemos

    :math:`a)` :math:`\mathcal{S}(ab) = \mathcal{S}(b) \mathcal{S}(a)` para todo :math:`a`, :math:`b \in A`,
    
    :math:`b)` :math:`\mathcal{S}(1) = 1`.

En resumen: :math:`\mathcal{S}` es un anti-homomorfismo de álgebras.

**Demostración:**

Consideremos el espacio :math:`Hom(A \otimes A, A)`. Esta es un álgebra con respecto a la siguiente operación:

- Sean :math:`f`, :math:`g \in Hom(A \otimes A, A)` y definimos

.. math::

    f \ast g : A \otimes A \stackrel{\Delta \otimes \Delta}{\longrightarrow} A \otimes A \otimes A \otimes A \stackrel{id_{A} \otimes \tau \otimes id_{A}}{\longrightarrow} A \otimes A \otimes A \otimes A \stackrel{f \otimes g}{\longrightarrow} A \otimes A \stackrel{\mu}{\longrightarrow} A .

- La asociatividad de esta operación se deriva de la asociatividad de :math:`\mu`.

- La coasociatividad de :math:`\Delta`.

- Una unidad para :math:`\ast` está dada por :math:`a \otimes b \mapsto u(\epsilon(a)\epsilon(b))`, lo que denotaremos por :math:`u(\epsilon \cdot \epsilon)`.

Define :math:`P : A \otimes A \to A` por :math:`P = \mathcal{S} \circ \mu`, i.e. :math:`P(a \otimes b) = \mathcal{S}(ab)` y observemos que

.. math::

    \begin{align}
        P \ast \mu &= (\mathcal{S} \circ \mu) \ast \mu\\
        &= \mu \circ ((\mathcal{S} \circ \mu) \otimes \mu) \circ (id_{A} \otimes \tau \otimes id_{A}) \circ (\Delta \otimes \Delta)\\
        &= \mu \circ (\mathcal{S} \otimes id_{A}) \circ (\mu \otimes \mu) \circ (id_{A} \otimes \tau \otimes id_{A}) \circ (\Delta \otimes \Delta)\\
        &= \mu \circ (\mathcal{S} \otimes id_{A}) \circ \Delta \circ \mu\\
        &= (\mathcal{S} \ast id_{A}) \circ \mu = u\epsilon \circ \mu\\
        &= u(\epsilon \cdot \epsilon)
    \end{align}

donde hemos usado los diagramas :math:`(1)` y :math:`(2)` de la definición de :ref:`biálgebra`. De la misma manera, sea :math:`N : A \otimes A \to A` dada por :math:`N(a \otimes b) = \mathcal{S}(b) \mathcal{S}(a)`. Sea :math:`a`, :math:`b \in A` y :math:`\Delta(a) = \sum_{i} a^{(1)}_{i} \otimes a^{(2)}_{i}` y :math:`\Delta(b) = \sum_{i} b^{(1)}_{i} \otimes b^{(2)}_{i}`. Notar que

.. math::

    \begin{align}
        (\mu \ast N)(a \otimes b) &= \sum_{i,j}a^{(1)}_{i} b^{(1)}_{j} \mathcal{S} \left(b^{(2)}_{j} \right) \mathcal{S} \left(a^{(2)}_{i} \right)\\
                                  &= \sum_{i}a^{(1)}_{i} (id_{A} \ast \mathcal{S})(b) \mathcal{S} \left(a^{(2)}_{i} \right)\\
                                  &= u\epsilon(b) \sum_{i}a^{(1)}_{i} \mathcal{S} \left(a^{(2)}_{i} \right)\\
                                  &= u\epsilon(b)(id_{A} \ast \mathcal{S})(a)\\
                                  &= u(\epsilon(b)\epsilon(a))\\
                                  &= u(\epsilon \cdot \epsilon)(a \otimes b).
    \end{align}

Ahora tenemos

.. math::
    
    \begin{align}
        P = P \ast u(\epsilon \cdot \epsilon) 
          = P \ast (\mu \ast N)               
          = (P \ast \mu) \ast N               
          = u(\epsilon \cdot \epsilon) \ast N 
          = N,
    \end{align}
      
i.e. :math:`\mathcal{S}(ab) = \mathcal{S}(b) \mathcal{S}(a)`. La segunda afirmación se deriva de

.. math::
    
    \mathcal{S}(1) = (\mathcal{S} \ast id_{A})(1) = (u\epsilon)(1) = 1.

:math:`\blacksquare`

Como vemos en este lema, la antípoda :math:`\mathcal{S}` de un álgebra de :ref:`Hopf` :math:`A` nos permite definir una acción de :math:`A` en el espacio dual :math:`V ^{\ast} = Hom (V, \mathbb{F})` de una representación :math:`V \in Obj (Rep (A))` a través de

.. math::
    
    (a \cdot \xi)(v) = \xi(\pi_{V}(\mathcal{S}(a))v)

para :math:`\xi \in V^{\ast}`, :math:`v \in V` y :math:`a \in A`. Más generalmente para dos representaciones :math:`V`, :math:`W \in Obj (Rep (A))`, los homomorfismos :math:`\mathbb{F}`-lineales :math:`Hom (V, W)` llevan una acción de :math:`A` de la siguiente manera: Sean :math:`a \in A` y :math:`\Delta(a) = \sum_{i} a^{(1)}_{i} \otimes a^{(2)}_{i}`. Entonces para :math:`f \in Hom(V, W)`

.. math::
    
    (a \cdot f)(v) = \sum_{i}\pi_{W}(a^{(1)}_{i}) f(\pi_{V}(\mathcal{S}(a^{(2)}_{i}))v)

define una acción de :math:`A`, donde usamos que :math:`\Delta` es un homomorfismo de álgebra. Esto es consistente con la definición anterior, ya que para :math:`a \in A` y :math:`f \in Hom (V, \mathbb{F})` tenemos

.. math::
    
    \begin{align}
        (a \cdot f)(v) &= \sum_{i}\epsilon(a^{(1)}_{i})f(\mathcal{S}(a^{(2)}_{i})v)                 \\
                       &= f\left(\sum_{i}u\epsilon(a^{(1)}_{i} )\mathcal{S}(a^{(2)}_{i})v\right)    \\
                       &= f((u\epsilon {\ast} \mathcal{S})(a)v)                                     \\
                       &= f(\mathcal{S}(a)v) .
    \end{align}


Lema
~~~~~~~~~~

Sean :math:`V`, :math:`W \in obj(Rep(A))`. El mapa canónico

.. math::
    
    \begin{align}
        \kappa : W \otimes V^{\ast} &\to Hom(V, W) ;\\
        w \otimes \xi &\mapsto (v \mapsto \xi(v) w)
    \end{align}

es una equivalencia de representaciones de :math:`A`.

**Demostración:**

Sea :math:`a \in A` con :math:`\Delta(a) = \sum_{i} a^{(1)}_{i} \otimes a^{(2)}_{i}` y :math:`w \otimes \xi \in W \otimes V^{\ast}`. entonces tenemos que para :math:`v \in V`

.. math::
    
    \begin{align}
        \kappa (a (w \otimes \xi))(v) &= \sum_{i} \kappa (a^{(1)}_{i} w \otimes a^{(2)}_{i} \xi)(v) \\
                                      &= \sum_{i} a^{(1)}_{i} w \xi (\mathcal{S}(a^{(2)}_{i} )v)    \\
                                      &= (a \kappa (w \otimes \xi))(v)
    \end{align}

donde hemos eliminado los endomorfismos :math:`\pi_{V}`, :math:`\pi_{W}`, etc. de nuestra notación. Esto prueba que :math:`\kappa` es un entrelazado en el sentido de la ecuación :math:`(3)`. El hecho de que :math:`\kappa` sea un isomorfismo es bien conocido por el álgebra lineal. :math:`\blacksquare`


Lema
~~~~~~~

Sea :math:`V \in obj(Rep(A))`. La unidad :math:`u : \mathbb{F} \to End(V)` dada por :math:`\lambda \mapsto \lambda id_{V}` es un entrelazamiento.

**Demostración:**

Sea :math:`a \in A` con :math:`\Delta(a) = \sum_{i} a^{(1)}_{i} \otimes a^{(2)}_{i}` y :math:`v \in V`. Entonces la acción de :math:`a` sobre :math:`id_{V}` está dada por

.. math::
    
    \begin{align}
        (a \cdot id_{V})(v) = \sum_{i}a^{(1)}_{i} \mathcal{S}(a^{(2)}_{i} ) v = (id_{A} \ast \mathcal{S})(a) v = \epsilon (a)v.
    \end{align}

La afirmación se deriva de esto. :math:`\blacksquare`

Lema
~~~~

Sea :math:`V \in obj(Rep(A))`. El pairing :math:`e_{V} : V^{\ast} \otimes V \to \mathbb{F}` es un entrelazamiento.

**Demostración:**

Sea :math:`a \in A` con :math:`\Delta(a) = \sum_{i} a^{(1)}_{i} \otimes a^{(2)}_{i}` y :math:`\xi \otimes v \in V^{\ast} \otimes V`. Tenemos

.. math::
    
    \begin{align}
        e_{V}(a \cdot (\xi \otimes v)) = \sum_{i} e_{V}(a^{(1)}_{i} \xi \otimes a^{(2)}_{i} v) = \sum_{i} \xi(\mathcal{S}(a^{(1)}_{i} )a^{(2)}_{i} v) = \xi((\mathcal{S} \ast id_{A})(a) v) = \epsilon(a) \xi(v) .
    \end{align}

Entonces, :math:`e_{V}` es equivariante con respecto a la acción de :math:`A`. :math:`\blacksquare`

Combinando los dos últimos lemas, tenemos que :math:`V^{\ast} \in obj(Rep(A))` junto con el entrelazamiento

.. math::
    
    \begin{align}
        &e_{V}: V^{\ast} \otimes V \to k &&\text{ y }& &i_{V} : k \stackrel{u}{\longrightarrow} End(V) \stackrel{\kappa^{-1}}{\longrightarrow} V \otimes V^{\ast}
    \end{align}

es un dual a derecha de :math:`V` en el sentido de categoría monoidal rígida. Para ver esto, sea :math:`e_{i} \in V` una base del espacio vectorial de dimensión finita :math:`V` y denote por :math:`e_{i} \in V^{\ast}` la base dual, entonces :math:`i_{V} (1) = \sum_{i} e_{i} \otimes e_{i}`. Por lo tanto, para :math:`v \in V`

.. math::
    
    (4) (id_{V} \otimes e_{V}) \circ (i_{V} \otimes id_{V})(v) = \sum_{i} e_{i} e_{i}(v) = v

y para :math:`\xi \in V^{\ast}`

.. math::
    
    (5) (e_{V} \otimes id_{V}\ast ) \circ (id_{V}\ast \otimes i_{V})(\xi) = \sum_{i}\xi(e_{i})e_{i} = \xi.

Por lo tanto, las relaciones de serpenteo se mantienen. Es tentador pensar que no debería haber diferencia entre los duales izquierdo y derecho en la categoría :math:`Rep (A)`, ya que :math:`(4)` y :math:`(5)` son solo una cuestión de álgebra lineal. Sin embargo, debido a la asimetría del producto tensorial, el lema 2.7 y el lema 2.9 no son válidos para estos duales izquierdos. Para obtener los duales derecho izquierdo 1, por lo tanto, necesitamos cambiar la acción de :math:`A` sobre :math:`Hom (V, k)`.

Sea :math:`A` un álgebra de :ref:`Hopf` sobre :math:`\mathbb{F}` con antípoda invertible :math:`\mathcal{S}` y defina :math:`{^{\ast}}V = Hom (V, k)` con la acción de :math:`A` dada por

.. math::
    
    (a \cdot \xi) (v) = \xi (\pi_{V} (\mathcal{S}^{-1} (a) )) v).


Lema
~~~~~~~

Sean :math:`V \in obj(Rep(A))`, :math:`e_{i}` una base de :math:`V` y denotamos por :math:`e^{i}` la base dual. El mapa

.. math::
    
    \begin{align}
        &i_{V} : k \to {^{\ast}}V \otimes V &&;& &\lambda \mapsto \lambda \sum_{i}e^{i} \otimes e_{i}\\
        &e_{V} : V \otimes {^{\ast}}V \to k &&;& &v \otimes \xi \mapsto \xi(v)
    \end{align}

son entrelazamientos.

**Demostración:**

Sea :math:`a \in A` y sea :math:`\Delta(a) = \sum_{i} a^{(1)}_{i} \otimes a^{(2)}_{i}`. Ya que :math:`\mathcal{S}^{-1}(1) = 1` tenemos que

.. math::
    
    \begin{align}
        e_{V}(a \cdot (v \otimes \xi)) &= \sum_{i}e_{V}(a^{(1)}_{i} v \otimes a^{(2)}_{i} \xi)                      \\
                                       &= \sum_{i}\xi(\mathcal{S}^{-1}(a^{(2)}_{i} ) a^{(1)}_{i} v)                 \\
                                       &= \sum_{i}\xi(\mathcal{S}^{-1}(\mathcal{S}(a^{(1)}_{i} ) a^{(2)}_{i} ) v)   \\
                                       &= \xi(\mathcal{S}^{-1}((\mathcal{S} \ast id_{A})(a)) v)                     \\
                                       &= \xi(\mathcal{S}^{-1}(\epsilon(a)1)v)                                      \\
                                       &= \epsilon(a) \xi(v)                                                        \\
                                       &= a \cdot e_{V}(v \otimes \xi).
    \end{align}

La equivariancia del mapa lineal :math:`i_{V}` solo necesita ser revisado en :math:`1 \in \mathbb{F}`, i.e. :math:`a\cdot i_{V}(1) = i_{V}(a\cdot 1)`. Esto se deduce de

.. math::
    
    \begin{align}
        a \cdot i_{V}(1) &= \sum_{i,j}a^{(1)}_{i} e^{j} \otimes a^{(2)}_{i} e_{j}                                   \\
                         &= \sum_{i,j,k} a^{(1)}_{i} e^{j}(e_{k})e^{k} \otimes a^{(2)}_{i} e_{j}                    \\
                         &= \sum_{i,j,k} e^{j}(\mathcal{S}^{-1}(a^{(1)}_{i} )e_{k}) e^{k} \otimes a^{(2)}_{i} e_{j} \\
                         &= \sum_{i,j,k} e^{k} \otimes a^{(2)}_{i} e_{j} e^{j}(\mathcal{S}^{-1}(a^{(1)}_{i} )e_{k}) \\
                         &= \sum_{i,k} e^{k} \otimes a^{(2)}_{i} \mathcal{S}^{-1}(a^{(1)}_{i} )e_{k}                \\
                         &= \sum_{i,k} e^{k} \otimes \mathcal{S}^{-1}(a^{(1)}_{i} \mathcal{S}(a^{(2)}_{i} )) e_{k}  \\
                         &= \sum_{k} e^{k} \otimes \mathcal{S}^{-1}(\epsilon(a) 1) e_{k}                            \\
                         &= \epsilon(a) \sum_{k} e^{k} \otimes e_{k}                                                \\
                         &= i_{V}(a \cdot 1).
    \end{align}


Las ecuaciones análogas de :math:`(4)` y :math:`(5)` son válidas para :math:`{^{\ast}}V` mostrando que proporciona un dual izquierdo a :math:`V`. Por lo tanto, hemos mostrado el 

Teorema
~~~~~~~~~~~~

Sea :math:`A` un álgebra de :ref:`Hopf` cuasi-triangular con antípoda invertible :math:`A`. Entonces :math:`Rep (A)` es una categoría monoidal trenzada rígida.

Ribbon Hopf algebras.
-----------------------

Una categoría de cinta posee una identificación natural :math:`\delta_{V} : V \to V^{\ast\ast}` que es compatible con el producto tensorial. Esto es equivalente a la siguiente definición

Categoría de cinta
~~~~~~~~~~~~~~~~~~~

Se dice que una categoría monoidal trenzada rígida :math:`(\mathcal{C}, \otimes, a, l, r, \mathbb{1})` es una categoría de cinta si viene equipada con una familia :math:`\theta_{V}: V \to V` de isomorfismos indexados por :math:`V \in obj (\mathcal{C})` que satisfacen

:math:`a)` :math:`\theta_{V\otimes W} = (\theta_{V} \otimes \theta_{W}) \sigma_{W,V} \circ \sigma_{V,W}`

:math:`b)` :math:`\theta_{{V}^{\ast}} = (\theta_{V})^{\ast}`

donde :math:`f^{\ast}` denota el morfismo adjunto a :math:`f` en :math:`\mathcal{C}`. Los morfismos :math:`\theta_{V}` se denominan *twists* de :math:`\mathcal{C}`.

Esta definición tiene una imagen especular en álgebras de Hopf cuasi-triangulares, lo que asegura que la categoría de representación correspondiente sea cinta.

.. _algebra-de-Hopf-de-cinta:

Álgebra de Hopf de cinta
~~~~~~~~~~~~~~~~~~~~~~~~~

Sea :math:`(A, \mu, u, \Delta,\epsilon, \mathcal{S}, R)` un álgebra de :ref:`Hopf` cuasi-triangular con antípoda invertible. Un elemento invertible :math:`\theta \in Z (A)` (donde :math:`Z (A)` denota el centro de :math:`A` como un álgebra) se llama un *twist*, si satisface

:math:`a)` :math:`\Delta(\theta) = (\tau(R)R)^{-1}(\theta \otimes \theta)`,

:math:`b)` :math:`\mathcal{S}(\theta) = \theta`.

Un álgebra de :ref:`Hopf` cuasi-triangular :math:`A` con antípoda invertible junto con un *twist* :math:`\theta` se llama álgebra de :ref:`Hopf` de cinta.

Esta definición está diseñada para hacer que funcione el siguiente teorema.

Teorema
~~~~~~~

Sea :math:`A` un :ref:`algebra-de-Hopf-de-cinta` con *twist* :math:`\theta \in Z(A)`. Luego :math:`Rep (A)` junto con el morfismo natural

.. math::

    \begin{align}
        &\theta_{V} : V \to V &&;& &v \mapsto \pi_{V}(\theta^{-1})(v)
    \end{align}
    
es una categoría de cinta.

**Demostración:**

Dado que :math:`\theta \in Z(A)`, la multiplicación por :math:`\theta^{-1}` conmuta con la multiplicación por cualquier otro elemento :math:`a \in A`. Por lo tanto, :math:`\theta_{V}` es de hecho equivariante y define un isomorfismo en :math:`Rep (A)`.

Para demostrar que :math:`\theta_{V}` define un twist, sea :math:`V`, :math:`W \in obj(Rep(A))`. Entonces tenemos para cada :math:`v\in V`, :math:`w\in W`

.. math::

    \begin{align}
        (\theta_{V} \otimes \theta_{W}) \sigma_{W,V} \circ \sigma_{V,W}(v \otimes w) &= (\pi_{V} \otimes \pi_{W})((\theta^{-1} \otimes \theta^{-1}) \tau(R) R)(v \otimes w)\\
        &= (\pi_{V} \otimes \pi_{W})(\Delta(\theta^{-1}))(v \otimes w)\\
        &= (\pi_{V} \ast \pi_{W})(\theta^{-1})(v \otimes w)\\
        &= \theta_{V}\otimes W(v \otimes w)\\
    \end{align}

por la condición :math:`a)` de la Definition de :ref:`algebra-de-Hopf-de-cinta`. Es más, para :math:`\xi \in V^{\ast}` y :math:`v \in V`

.. math::

    \begin{align}
        (\theta_{V}) \ast(\xi)(v) &= \xi(\theta_{V}(v))                 \\
                                  &= \xi(\pi_{V}(\theta^{-1})(v))       \\
                                  &= \xi(\pi_{V}(S(\theta^{-1}))(v))    \\
                                  &= (\pi_{V} \ast(\theta^{-1})(\xi))(v)\\
                                  &= \theta_{V} \ast(\xi)(v),
    \end{align}

donde hemos utilizado la propiedad :math:`b)`.

Observación
~~~~~~~~~~~~~

Para álgebras de Hopf cuasi-triangulares de dimensión finita, el inverso de la declaración anterior también es cierto, es decir, si :math:`Rep (A)` es una categoría de cinta, entonces :math:`A` es un :ref:`algebra-de-Hopf-de-cinta`. En este caso :math:`A \in obj (Rep (A))` y de manera similar a las consideraciones anteriores, se puede verificar que :math:`\theta = (\theta_{A} (1))^{-1}` proporciona un giro para :math:`A`.