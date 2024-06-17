# Méthode des différences finies avec Matlab

## Introduction

### Problèmes traités

#### Domaine $\Omega$ et maillage

Pour tous les problèmes traités, le domaine  $\Omega$ sera un carré de dimension $D \times D$, avec un maillage carré dont les sommets sont au nombre de $N \times N$. Le pas spatial élémentaire du maillage sera donc $h_x=\dfrac{D}{N-1}$.

#### Conditions aux limites

Pour tous les problèmes traités, des conditions aux limites de Dirichlet et de Neumann seront imposées sur chaque côté du carré. Dans les programmes proposés, les côtés où ces conditions sont imposées, sont arbitrairement fixés et seules les valeurs imposées sont paramétrables.

#### Problèmes stationnaires

On résoudra numériquement l'équation $-\Delta u + au = f$, avec différentes conditions aux limites. 

#### Problèmes d'évolution

On résoudra numériquement l'équation de la chaleur $\dfrac{\partial u}{\partial t} = \gamma \Delta u$ ainsi que l'équation des ondes $\dfrac{\partial^2 u}{\partial t^2} = \gamma \Delta u$.

Pour l'équation de la chaleur, on pourra tester les méthodes d'Euler implicites et explicites.

Pour l'équation des ondes, on pourra tester la méthode de Runge-Kutta d'ordre 4.

### Schémas numériques et stabilté

Pour l'équation de la chaleur, on pourra calculer numériquement le rayon spectral de la matrice intervenant dans la méthode d'Euler, dans le cas implicite et explicite. 

Pour chaque instant $t=nh_t$ avec un pas temporel $h_t$, on approxime le laplacien sous la forme $\Delta u \approx AU_n+B$, où $U_n$ est un vecteur rassemblant les valeurs de la fonction $u$ dans le domaine $\Omega$ carré, $A$ est une matrice et $B$ est un vecteur.

Pour l'équation de la chaleur, les équations d'Euler explicites et implicites sont respectivement $U_{n+1} = U_n + h_t \gamma \left(AU_n+B\right)$ et $U_{n+1} = U_n + h_t \gamma \left(AU_{n+1}+B\right)$.

On obtient finalement pour le schéma explicite :
$$U_{n+1} = \left(I+h_t\gamma A\right)U_n+h_t\gamma B$$
et pour le schéma implicite :
$$U_{n+1} = \left(I-h_t\gamma A\right)^{-1}\left(U_n+h_t\gamma B\right)$$

Pour l'équation des ondes, $X(t)=\begin{pmatrix} U & V\begin{pmatrix}$

## Quelques exemples

[![](Data/df2d_dirichlet.mp4)

[![](Data/df2d_dirichlet_neumann.mp4)

[![](Data/df2d_neumann.mp4)

[![](Data/df2d_propag_dirichlet_rk45.mp4)

[![](Data/df2d_propag_neumann_rk45.mp4)

