# Jumeau Numérique d'Instance — Monument André Cools

**TFE 2026 · Master Ingénieur Industriel Géomètre · HEPL Liège**  
*Louis Frontain — supervisé par B. Jonlet*

🌐 **[Voir le site interactif](https://louisfrontain1-dot.github.io/jumeau-numerique-andre-cools/)**

---

## Présentation

Ce dépôt contient l'ensemble des livrables numériques du Travail de Fin d'Études portant sur la création d'un **jumeau numérique d'instance** du monument commémoratif André Cools (Flémalle-Haute, Liège, Belgique).

Le pipeline développé transforme un relevé TLS brut de 111 millions de points en un modèle numérique sémantisé, diffusé sur le web, capable de détecter et quantifier des évolutions structurelles entre deux états temporels.

---

## Pipeline en 5 phases

| Phase | Outil | Résultat |
|-------|-------|----------|
| 01 · Acquisition TLS | Trimble X7 · 6 stations | 111M points · RMSE 1.529mm |
| 02 · Traitement Python | Open3D · SOR + Voxel Grid 5mm | 6M points · réduction 99.7% |
| 03 · Modélisation BIM | Autodesk Revit 2024 | 7 paramètres DT · LOD 200-350 |
| 04 · Analyse T0→T1 | Python Open3D · CloudCompare | Fissure détectée · écart max 40.6mm |
| 05 · Diffusion web | HTML5 · Three.js · GitHub Pages | Site bilingue FR/EN · 4 viewers 3D |

---

## Contenu du dépôt

```
├── index.html                              # Site web principal (bilingue FR/EN)
├── viewer_ifc.html                         # Viewer IFC T0 interactif (Three.js)
├── viewer_ifc_fissure.html                 # Viewer IFC T1 — fissure simulée
├── viewer3d_standalone.html                # Viewer nuage de points T0
├── viewer3d_standalone_fissure.html        # Viewer nuage de points T1
├── TFE_Structure_JumeauNumerique_V1.ifc    # Modèle BIM IFC4 — état T0 (référence)
├── TFE_Structure_JumeauNumerique_V2.ifc    # Modèle BIM IFC4 — état T1 (fissure)
├── rapport_pipeline_TFE.pdf                # Rapport Python pipeline T0
├── rapport_comparaison_T0_T1.pdf           # Rapport comparaison multi-temporelle
├── data/
│   ├── nuage_cools.bin                     # Nuage de points T0 (367 996 pts · Three.js)
│   └── nuage_cools_fissure.bin             # Nuage de points T1 avec fissure orange
└── images/
    ├── photo1.jpg / photo2.jpg / photo3.jpg
    ├── logo_hepl.png
    └── logo_geotop.png
```

> **Fichiers volumineux** (.E57, .LAS, .PLY, .RVT) disponibles sur demande : louis.frontain@student.hepl.be

---

## Technologies utilisées

- **Acquisition** : Trimble X7, Trimble RealWorks
- **Traitement nuage de points** : Python 3.10, Open3D, pye57, CloudCompare
- **Modélisation BIM** : Autodesk Revit 2024, format IFC4
- **Visualisation web** : HTML5, CSS3, JavaScript, Three.js r128
- **Hébergement** : GitHub Pages

---

## Résultats clés

- ✅ RMSE recalage : **1.529 mm** (précision instrumentale Trimble X7 : 2.4 mm)
- ✅ Réduction données : **99.7%** (111M → 6M points)  
- ✅ Fissure simulée détectée : **écart max 40.6 mm**, validé CloudCompare (38.4 mm)
- ✅ Zone stable T0→T1 : **99.9%** des points < 3 mm
- ✅ Export **8 formats** : IFC4, RVT, E57, LAS, PLY, OBJ, DWG, PDF

---

## Note sur la fissure T1

> ⚠️ La fissure présentée dans les livrables T1 est **fictive et simulée algorithmiquement** à des fins de démonstration du pipeline de monitoring multi-temporel. **Aucune pathologie réelle** n'a été détectée sur le monument André Cools lors du relevé du 24/04/2026.

---

## Contexte académique

- **Établissement** : Haute École de la Province de Liège (HEPL), Quai Gloesener 6, 4020 Liège
- **Formation** : Master en Sciences de l'Ingénieur Industriel — orientation Géomètre
- **Promoteurs** : M. Benoît Jonlet
- **Stage** : Geotop SA, Liège
- **Année académique** : 2025–2026

---

*Développé avec Python, Open3D, Autodesk Revit et Three.js · Site généré avec l'assistance de Claude (Anthropic, 2025)*
