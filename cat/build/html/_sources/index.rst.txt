Categorías Tensoriales Modulares y Grupos Finitos
=================================================


Fundamentos
-----------


Una clase particularmente importante de categorías, es la de las categorías tensoriales finitas sobre un cuerpo :math:`\mathbb{F}` algebraicamente cerrado y de característica cero. Recordemos que una categoría monoidal es una categoría munida de un producto tensorial y de un objeto unidad sujetos a ciertos axiomas de asociatividad y unidad. 

A través de este concepto, se engloba a la teoría de representaciones de grupos, de álgebras de Lie y, más generalmente, de álgebras de Hopf, a través de sus categorías de representaciones, que resultan naturalmente equipadas con un producto tensorial. A su vez, una categoría tensorial finita es una categoría monoidal Abeliana :math:`\mathbb{F}`-lineal, con ciertas propiedades.

En el caso en el que la categoría es semisimple, se dice que es una categoría de fusión (bajo ciertos axiomas); y se dice finita en el caso en que exista una cantidad finita de objetos simples :math:`\mathcal{S}=\{S_{1},\dots,S_{n}\}`. En este caso, la categoría posee una descripción combinatoria, a través de las reglas de multiplicación (o "fusión") de los objetos simples:

.. math::
   
   S_{i}\otimes S_{j}=\bigoplus_{S_{k}\in \mathcal{S}} S_{k}^{\oplus N_{ij}^{j}}.

Asociada a estas constantes de estructura :math:`(N_{ij}^{j})_{i,j,k}`, se definen matrices :math:`S` y :math:`T` asociadas a la estructura monoidal de la categoría. Cuando la matriz :math:`S` es invertible, se dice que la categoría es modular. Estas matrices dan una representación proyectiva del grupo :math:`\operatorname{SL}(2,\mathbb{Z})`.


Objetivos
-----------


El objetivo principal es familiarizarse con los conceptos básicos de la teoría de categorías, y más aún con el área de las categorías tensoriales y modulares. Se desarollarán ejemplos, como el de la categoría de representaciones de un grupo finito.

Un ejemplo esencial y no inmediato de categoría modular es la de representaciones del doble de Drinfeld o doble cuántico de :math:`G`, denotado :math:`D(G)`. Este álgebra tiene una estructura de álgebra de Hopf, lo que dota a la categoría de la estructura tensorial. Puede verse que la misma es semisimple y que la :math:`S`-matriz asociada es invertible. Se buscará desarrollar estos resultados en detalle y dar ejemplos concretos de :math:`S`-matrices asociados a algunos grupos finitos (:math:`\mathbb{Z}/n\mathbb{Z}`, :math:`\mathbb{Z}/p\mathbb{Z}\rtimes \mathbb{Z}/q\mathbb{Z}`, :math:`\mathbb{S}_n`, entre otros).


.. toctree::
   :maxdepth: 3
   :numbered:
   :caption: Contenidos:

   Notas/00-nociones-preliminares
   Notas/01-teoria-de-representaciones
   Notas/02-categoria-de-representaciones-de-algebras-de-hopf
   Notas/03-el-doble-cuantico-de-un-grupo-finito
