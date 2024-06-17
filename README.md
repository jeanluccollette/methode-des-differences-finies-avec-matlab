# Méthode des différences finies avec Matlab

## Introduction

### Problèmes traités

#### Domaine $\Omega$ et maillage

Pour tous les problèmes traités, le domaine  $\Omega$ sera un carré de dimension $D \times D$, avec un maillage carré dont les sommets sont au nombre de $N \times N$. Le pas élémentaire du maillage sera donc $h=\dfrac{D}{N-1}$

#### Conditions aux limites

Pour tous les problèmes traités, des conditions aux limites de Dirichlet et de Neumann seront imposées sur chaque côté du carré. Dans les programmes proposés, les côtés où ces conditions sont imposées, sont arbitrairement fixés et seules les valeurs imposées sont paramètrables.

#### Problèmes stationnaires

On résoudra numériquement l'équation $-\Delta u + au = f$, avec différentes conditions aux limites. 

#### Problèmes d'évolution

On résoudra numériquement l'équation de la chaleur $\dfrac{\partial u}{\partial t} = \gamma \Delta u$ ainsi que l'équation des ondes $\dfrac{\partial^2 u}{\partial t^2} = \gamma \Delta u$.

## Quelques exemples

[![](Data/df2d_dirichlet.mp4)

[![](Data/df2d_dirichlet_neumann.mp4)

[![](Data/df2d_neumann.mp4)

[![](Data/df2d_propag_dirichlet_rk45.mp4)

[![](Data/df2d_propag_neumann_rk45.mp4)

