# 🛸 MISSION WARP 2026 — Document complet (scellé 2026-09-23)

**Objectif** : mettre une bulle d'Alcubierre dans l'univers-jouet RATISS et y
faire voyager un vaisseau (10 t, 2026) — 11 vols, **22 examens** (état,
intrication, résidus, déformation, relativité). Tout le déclaré dans
`warp/engine.py`, tout le mesuré dans `warp/resultats/w22.json`.

## 1. Le moteur (déclaré, honnête)
- **Espace** = milieu élasto-plastique 656 pts (ressorts k=0.5 + amortissement
  0.2 + seuil plastique 1.0 : l'espace a une MÉMOIRE).
- **Bulle** = VRAI profil Alcubierre tanh (R=3, σ=1, intérieur plat R_in=1.5) :
  contraction AVANT + expansion ARRIÈRE (puissance E_b=1) + maintenance mur.
- **Vaisseau** (m=10) : vol LIBRE (réaction Newton ×ksurf=0.2, zéro frottement :
  le vide !) ou IMPOSÉ (v = bouton). Contrôle classique : poussée 0.5, bulle OFF.
- **Messagers Λ** (option) : émis à l'arrière (taux 1.5, vie 250, marche 0.3),
  poussent le milieu (kap=0.03) — version ISOTROPE (R6) ou DIRECTIVE (R6b).
- **Diagnostics** : horloges Kuramoto (K=0.5), 64 bits bord (flips au mur),
  H1 ripser (sous-échantillon /4). Échelles SI : 1u=1m, 10t, 1t=1s.

## 2. Les 11 vols
| Vol | Réglage | t_arr | W (coût) | Note |
|---|---|---|---|---|
| R1 libre | bulle, réaction | 26.3 | 83.0 (830 kJ) | vol de référence |
| R2 class | poussée 0.5, pas de bulle | 40.0 | 20.0 (200 kJ) | contrôle |
| R3/R4/R5 | imposé v=1/2/4 | 40/20/10 | 122/59/22 | courbe coût |
| R10 | imposé v=8 | 5.0 | 6.8 (68 kJ !) | seuil rentabilité |
| R6/R6b | libre + msg iso/dir | 26.4/18.3 | 82/62 | anti-exotique |
| R7 panne | bulle coupée à x=0 | 27.9 | 67.2 | dérive gratuite ! |
| R8 lourd | m×4 | 59.6 | 185 | loi √m |
| R9 retour | +2 puis -2 | — (x=-30) | 145.5 | aller-retour |

## 3. Les 22 examens (résultats)
**ÉTAT** : W01 vol libre v_max=3.29 ; **W02 coût ∝ v^-1.4** (122→6.8 !) ;
W02-exo : R1 32.5 (100% exotique), R6 -1.9% (traînée !), **R6b 159% (bulle
PROPRE, exotique -19.3 !)** ; W03 facteur libre **0.42** (lent = cher) ;
W04 accélération variable (std quad 0.85, pas de croisière) ; **W05 panne :
+6% temps, -19% coût** (on dérive, l'espace ne freine pas !) ; W06 t×2.27
(√4=2 à 13% près).
**INTRICATION** : W07 **+0.237 cycles bord** (offset soustrait) ; W08 R
0.23→0.70 mais **R1=R2 au millième = sync spontanée** (nul honnête) ;
W09 bits 0.56→0.70 monotone exposition (σ=0.06) ; W10 avant 0.73/arrière
0.68 (+7%, marginal).
**RÉSIDUS** : W11 sillage 0.071 (R1), **0.029 (v4 : vite = propre !)**,
0.091 (retour, max 2.05) ; W12 E_résid 6.4/1.2/10.5 ; **W13 H1 0.76→0.85
(+12% : le sillage cicatrise en rides !)** ; W14 359 msg restants, 24 leaked.
**DÉFORMATION** : W15 corr tanh **0.24 (mur ÉTALÉ par élasticité)** ; W16
avant dep 0.055 (transitoire) ; W17 arrière dep 0.52 (sillage creusé) ;
W18 dedans dep 0.44 (t...[truncated 2242 chars]