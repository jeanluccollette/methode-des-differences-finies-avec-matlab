# Méthode des différences finies avec Matlab

## Introduction

### Problèmes traités

#### Domaine $\Omega$ et maillage

Pour tous les problèmes traités, le domaine  $\Omega$ sera un carré de dimension $D \times D$, avec un maillage carré dont les sommets sont au nombre de $N \times N$. Le pas spatial élémentaire du maillage sera donc $h_x=\dfrac{D}{N-1}$.

#### Conditions aux limites

Pour tous les problèmes traités, des conditions aux limites de Dirichlet ou de Neumann seront imposées sur chaque côté du carré. Dans les programmes proposés, les côtés où ces conditions sont imposées, sont arbitrairement fixés et seules les valeurs imposées sont paramétrables.

#### Problèmes stationnaires

On résoudra numériquement l'équation $-\Delta u + au = f$, avec différentes conditions aux limites. 

#### Problèmes d'évolution

On résoudra numériquement l'équation de la chaleur $\dfrac{\partial u}{\partial t} = \gamma \Delta u$ ainsi que l'équation des ondes $\dfrac{\partial^2 u}{\partial t^2} = \gamma \Delta u$.

Pour l'équation de la chaleur, on pourra tester les méthodes d'Euler implicites et explicites.

Pour l'équation des ondes, on pourra tester la méthode de Runge-Kutta d'ordre 4.

### Schémas numériques et stabilté

Pour l'équation de la chaleur, on pourra calculer numériquement le rayon spectral de la matrice intervenant dans la méthode d'Euler, dans le cas implicite et explicite. 

Pour chaque instant $t_n=nh_t$ avec un pas temporel $h_t$, on approxime le laplacien sous la forme $\Delta u \approx AU_n+B$, où $U_n$ est un vecteur rassemblant les valeurs de la fonction $u(t_n)$ dans le domaine $\Omega$ carré, $A$ est une matrice et $B$ est un vecteur.

Pour l'équation de la chaleur, les équations d'Euler explicites et implicites sont respectivement $U_{n+1} = U_n + h_t \gamma \left(AU_n+B\right)$ et $U_{n+1} = U_n + h_t \gamma \left(AU_{n+1}+B\right)$.

On obtient finalement pour le schéma explicite :
$$U_{n+1} = \left(I+h_t\gamma A\right)U_n+h_t\gamma B$$
et pour le schéma implicite :
$$U_{n+1} = \left(I-h_t\gamma A\right)^{-1}\left(U_n+h_t \gamma B\right)$$

Pour l'équation des ondes, on se ramène à la résolution numérique d'une équation différentielle ordinaire $\dfrac{dX(t)}{dt}=F(X(t))$, avec un vecteur d'état $X(t)$ défini ci-dessous.

```math
X(t) = \begin{pmatrix}U(t)\\\dfrac{dU(t)}{dt}\end{pmatrix}
```
```math
\dfrac{dX(t)}{dt} = \begin{pmatrix}\dfrac{dU(t)}{dt}\\  \gamma \left(AU(t)+B\right) \end{pmatrix} = F(X(t))
```

## Quelques exemples

### Problèmes stationnaires

Les programmes sont dans l'archive **df2d_stat.zip**, dossier **CODE**.

```
>> N=501;D=10;ul=1;gl=0;a=0;f=1;
>> df2d_statique(N,D,ul,gl,a,f)
```

![](Data/stat_D.png)
![](Data/stat_DN.png)

### Problèmes d'évolution

#### Equation de la chaleur

Les programmes sont dans l'archive **df2d_cha.zip**, dossier **CODE**.

```
>> resolexpl=0;ht=0.05;N=51;f=10;D=1;T=10;gamm=0.01;
>> df2d_simu_dirichlet(resolexpl,ht,N,f,D,T,gamm)
ht=0.05  hx=0.02
gamma*ht/hx^2=1.25
   10.1461
```

[![](Data/df2d_dirichlet.mp4)

```
>> resolexpl=0;ht=0.05;N=51;f=10;g=0;D=1;T=10;gamm=0.01;
>> df2d_simu_dirichlet_neumann(resolexpl,ht,N,f,g,D,T,gamm)
ht=0.05  hx=0.02
gamma*ht/hx^2=1.25
   10.2163
```

[![](Data/df2d_dirichlet_neumann.mp4)

[![](Data/df2d_neumann.mp4)

[![](Data/df2d_propag_dirichlet_rk45.mp4)

[![](Data/df2d_propag_neumann_rk45.mp4)

