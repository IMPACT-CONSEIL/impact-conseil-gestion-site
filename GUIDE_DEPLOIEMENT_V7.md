# Site Impact Conseil v7 — Guide de déploiement

**Date** : 15 juillet 2026
**Objectif** : remplacer la v6.4 de impact-conseil-gestion.fr par la v7 (SEO multi-pages, auto-diagnostic, ressources réelles, outils Excel).

---

## Ce qui change par rapport à la v6.4

**Corrections**
- Compteurs affichés en dur dans le HTML (8+, 120+, +25%, 95%) — visibles par Google même sans JavaScript, l'animation fonctionne toujours.
- Logo GCL blanc hébergé en local (`images/gcl-blanc.png`). Les 2 autres logos ont un fallback automatique vers le site GCL (voir actions ci-dessous).
- Tous les liens morts de la section Ressources sont maintenant actifs.

**Nouvelles pages (18)**
- `offres/` : 5 pages détaillées, une par offre, avec FAQ et balisage schema.org (Service + FAQPage).
- `secteurs/` : 6 pages sectorielles (agroalimentaire, industrie, BTP, services, agriculture, santé).
- `faq.html` : 10 questions/réponses avec balisage FAQPage (visé : featured snippets Google).
- `diagnostic.html` : auto-diagnostic interactif 20 questions, score immédiat, priorités personnalisées, CTA Calendly. Aucune donnée transmise (tout est côté navigateur).
- `ressources/` : les 4 articles annoncés, réellement publiés.
- `outils/` : checklist imprimable + 2 fichiers Excel (tableau de bord 5 indicateurs, simulateur trésorerie 12 mois) — formules vérifiées, exemple janvier pré-rempli.
- `sitemap.xml` : 21 URLs (à re-soumettre dans Google Search Console après déploiement).

**Navigation**
- Lien FAQ dans le menu, bannière auto-diagnostic sur la page Ressources, lien diagnostic sous le CTA d'accueil, cartes d'offres cliquables vers les pages détaillées, footer enrichi (FAQ, diagnostic, mention Rennes · Cotonou).

---

## Déploiement

Identique à la v6 : remplacer le contenu du dépôt GitHub par ce dossier complet (y compris les nouveaux sous-dossiers `offres/`, `secteurs/`, `ressources/`, `outils/`).

GA4 (`G-RJ86Z3S9XD`) et Formspree (`maqzqyzl`) sont déjà configurés — rien à changer.

Après mise en ligne :
1. Google Search Console → Sitemaps → soumettre `https://impact-conseil-gestion.fr/sitemap.xml`
2. Tester : accueil, 1 page offre, le diagnostic (faire le quiz jusqu'au score), le téléchargement des 2 Excel.

---

## Actions côté Amos (par priorité)

1. **Bénin — enregistrer le domaine `impact-conseil-gestion.bj`** (registrar accrédité, liste sur nic.bj) et activer l'email `contact@impact-conseil-gestion.bj`. La landing (`LIVRABLES/SITE-BENIN-v1/`) est prête à déployer dès que le domaine existe — en attendant, elle utilise WhatsApp comme contact. Réserver aussi `impact-conseil-benin.com` (~12 €/an, vérifié disponible) en redirection.
2. **2 logos à déposer dans `images/`** (clic droit → enregistrer depuis le site GCL, puis renommer) :
   - `images/gcl-couleur.png` ← https://expertsgestion-gcl.fr/wp-content/uploads/2025/01/Logo_slogan.png
   - `images/label-figaro.png` ← https://expertsgestion-gcl.fr/wp-content/uploads/2024/08/Logo-label-remove-BG.png
   Tant qu'ils n'y sont pas, le site charge automatiquement les versions distantes (aucune casse visible).
3. **Chiffres des compteurs** : j'ai gardé ceux de la v6 (8 ans, 120 dirigeants, +25% trésorerie, 95% satisfaction). Confirme-les ou donne-moi les vrais.
4. **Témoignages nominatifs** : obtenir l'accord de 2-3 clients (nom complet + entreprise) pour remplacer les initiales.
5. **Photos réelles** : ta photo pour la section À propos + 1-2 photos terrain (formation, atelier) pour remplacer les images de banque restantes.

---

## Fichiers livrés

```
SITE-v7-PackComplet/          ← à déployer sur impact-conseil-gestion.fr
├── index.html                (corrigé)
├── faq.html · diagnostic.html
├── offres/ (5) · secteurs/ (6) · ressources/ (4) · outils/ (3)
├── sitemap.xml               (21 URLs)
└── … (mentions légales, 404, images, robots.txt inchangés)

SITE-BENIN-v1/                ← à déployer sur impact-conseil-gestion.bj (après enregistrement)
└── index.html                (landing complète : 5 pôles + transversal, bidirectionnel, WhatsApp)
```
