# Modèle, mesures et montage — Santé communautaire

## Import

`Obtenir les données → Classeur Excel` → `data/Programme_Sante_Communautaire_Senegal_DEMO.xlsx` → tables **Suivi_Indicateurs** et **Districts**. L'onglet **Sources** n'entre pas dans le modèle.

Types Power Query : `Cible_Pourcentage`, `Population_Cible`, `Nombre_Atteint`, `Annee` en nombre entier.

## Relation

`Suivi_Indicateurs[District_Sanitaire]` → `Districts[District_Sanitaire]` (plusieurs-à-un).

Pour un tri chronologique correct : colonne `Ordre_Trimestre` (`Annee * 10 + numéro du trimestre`), puis **Trier par colonne** sur `Trimestre`.

## Mesures

Voir le README racine. Formater `Taux de Réalisation`, `Cible Moyenne` et `Écart à la Cible` en pourcentage. Mise en forme conditionnelle rouge / vert sur l'écart.

## Mise en page (indicateurs)

- Ligne 1 — cartes : taux de réalisation, population couverte, indicateurs sous la cible, pire écart
- Ligne 2 — combiné barres (réalisé) + ligne (cible) par indicateur
- Ligne 3 — courbe trimestrielle ; matrice district × écart à la cible
