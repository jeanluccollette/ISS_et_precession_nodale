# Simulation numérique de la précession nodale de l'ISS

## Calcul du potentiel gravitationnel

Dans le référentiel géocentrique, le satellite a une position repérée par ses coordonnées $X$, $Y$ et $Z$, le plan de référence (coordonnées  $X$ et $Y$) étant le plan équatorial. Dans ce référentiel, $\lambda$ est la latitude ou la déclinaison. On note par ailleurs $R=\sqrt{X^2+Y^2+Z^2}$ et $\mu_T$ le paramètre gravitationnel standard de la Terre. Pour une Terre sphérique, le potentiel gravitationnel est :

$$V(R,\lambda)=-\dfrac{\mu_T}{R}$$

Il en résulte une accélération qui détermine un mouvement classique sur une orbite de Kepler.

$$-\dfrac{\mu_T}{R^3}
\begin{pmatrix}
X\\
Y\\
Z
\end{pmatrix}$$

Pour une Terre ellipsoïdale avec un rayon moyen $R_T=6371 \text{ km}$, on modélise approximativement le potentiel gravitationnel avec un terme complémentaire au précédent ($J_2 = 1,082625\times10^{−3}$).

$$V(R,\lambda)=-\dfrac{\mu_T}{R}\left(1 - \dfrac{J_2}{2}\left(\dfrac{R_T}{R}\right)^2(3\sin^2(\lambda)-1)\right)$$

Un terme complémentaire apparaît alors pour l'accélération, dont la direction ne passe plus par le centre de la Terre.

$$\dfrac{3}{2}J_2\mu_T\left(\dfrac{R_T}{R}\right)^2
\begin{pmatrix}
\left(\dfrac{X}{R^3}\right)\left(5\left(\dfrac{Z}{R}\right)^2-1\right)\\
\left(\dfrac{Y}{R^3}\right)\left(5\left(\dfrac{Z}{R}\right)^2-1\right)\\
\left(\dfrac{Z}{R^3}\right)\left(5\left(\dfrac{Z}{R}\right)^2-3\right)
\end{pmatrix}$$

Une conséquence bien visible de cette perturbation apparaît, avec la ligne des noeuds associée à l'orbite du satellite qui tourne dans le sens rétrograde. Il s'agit de la **précession nodale**.

L'objet du programme proposé est de simuler numériquement cet effet pour l'ISS, et de confronter les résultats aux données fournies par le JPL.
