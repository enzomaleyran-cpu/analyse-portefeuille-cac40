# Analyse d'un portefeuille de trois actions du CAC 40

Projet personnel en Python : mesurer le rendement et le risque d'**Airbus (AIR.PA)**, **LVMH (MC.PA)** et **L'Oréal (OR.PA)**, puis étudier l'effet de la diversification dans un portefeuille à poids égaux.

## Méthodologie

- Cours de clôture ajustés (dividendes et divisions d'actions inclus), récupérés avec `yfinance`, du 2 janvier 2024 au 9 octobre 2026 (709 jours de bourse)
- Rendements journaliers (`pct_change`), puis rendement annualisé (moyenne × 252) et volatilité annualisée (écart-type × √252)
- Matrice de corrélation des rendements
- Portefeuille à poids égaux (un tiers par action), rééquilibré chaque jour
- Visualisation en base 100 avec `matplotlib`

## Résultats principaux

| Actif | Rendement annualisé | Volatilité annualisée | Rendement / risque |
|---|---|---|---|
| Airbus | +15,9 % | 27,2 % | 0,59 |
| LVMH | -16,3 % | 30,2 % | -0,54 |
| L'Oréal | -0,6 % | 24,3 % | -0,02 |
| **Portefeuille** | **-0,3 %** | **20,9 %** | |

- La volatilité du portefeuille (20,9 %) est inférieure à celle de chacune des trois actions (24,3 % à 30,2 %) et de 6,3 points à leur moyenne (27,2 %).
- LVMH et L'Oréal sont les plus corrélés (0,56) ; Airbus est faiblement corrélé aux deux autres (0,31 et 0,28) et diversifie donc le plus.

## Limites

- Seulement trois actions, issues de deux grands secteurs, sur une période courte
- Rééquilibrage quotidien supposé, sans frais de transaction
- La diversification protège moins lors des fortes baisses de marché (avril 2025 : les trois actions reculent ensemble)
- Taux sans risque supposé nul dans le ratio rendement/risque
- Les performances passées ne préjugent pas des performances futures

## Contenu du dépôt

- `analyse_portefeuille_cac40.ipynb` : notebook complet (code, graphiques, conclusion)
- `prix.csv` : données figées pour que les résultats soient reproductibles

## Reproduire l'analyse

```bash
pip install numpy pandas matplotlib yfinance jupyter
jupyter notebook
```

Ouvrir le notebook et exécuter toutes les cellules (**Kernel > Restart & Run All**).

## Auteur

Enzo Maleyran, étudiant en MSc Financial Analysis and Investment Management, Audencia Business School.
