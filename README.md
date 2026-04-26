# VIVA Clinique

Site vitrine statique de **VIVA Clinique**, clinique privée de référence de 2ème catégorie fondée en 1998 et basée à Douala-Logbessou, au Cameroun.

Projet réalisé dans le cadre d'un cours XHTML & CSS.
Ceci est mon 1er projet. ^^
---

## Pages

| Page | Fichier | Description |
|------|---------|-------------|
| Accueil | `Page d'Accueil.html` | Présentation de la clinique, carrousels, vaccinations, actualités, localisation |
| Notre Équipe | `nous.html` | Profils des 6 médecins de l'équipe médicale |
| Pharmacie | `Pharmacie.html` | Catalogue de 10 médicaments avec prix en XAF |
| Rendez-vous | `Consultation.html` | Formulaire de prise de RDV médical téléchargeable |

---

## Structure du projet

```
Projet Cours XHTML & CSS/
├── Page d'Accueil.html
├── nous.html
├── Pharmacie.html
├── Consultation.html
├── css/
│   ├── shared.css          ← styles communs (body, header, footer, navbar, arrow)
│   ├── acceuil.css         ← styles spécifiques à la page d'accueil
│   ├── consultation.css    ← styles spécifiques au formulaire
│   ├── pharmacie.css       ← styles spécifiques au catalogue
│   ├── nous.css            ← styles spécifiques à l'équipe
│   └── bootstrap/          ← Bootstrap 5 (local)
├── JS/
│   └── Go-up-arrow         ← bouton retour en haut de page
└── image/                  ← photos, icônes et logos
```

---

## Technologies

- HTML5 / CSS3
- [Bootstrap 5](https://getbootstrap.com/) — grille, navbar responsive, carrousels
- JavaScript vanilla — scroll-to-top, téléchargement du formulaire en `.txt`

---

## Lancer le projet

Ouvrir `Projet Cours XHTML & CSS/Page d'Accueil.html` directement dans un navigateur. Aucun serveur requis.

---

## Fonctionnalités

- Carrousels Bootstrap animés (entrée clinique, infrastructures, vaccinations, actualités)
- Formulaire de RDV médical avec export des données en fichier `.txt`
- Catalogue de 10 médicaments avec photos, descriptions et prix
- Carte Google Maps intégrée (section Localisation + footer)
- Bouton flottant de retour en haut de page (scroll smooth)
- Navigation responsive avec menu hamburger sur mobile
- Footer uniforme avec contacts, liens rapides, réseaux sociaux

---

## Corrections appliquées (audit)

### Bugs critiques
- **JS formulaire** : corrigé le code de téléchargement (était dans l'attribut `src` d'un `<script>`, donc jamais exécuté) et corrigé la référence à l'ID du formulaire
- **IDs dupliqués** : remplacé les `id="titre"` multiples par `class="titre"` (les IDs doivent être uniques par page)
- **`object-fit` invalide** : corrigé `object-fit: fit` → `object-fit: cover` dans `pharmacie.css`
- **Typo classe CSS** : corrigé `.incone` → `.icone` dans `shared.css`
- **Typo prix** : corrigé `1,,800 XAF` → `1 800 XAF`
- **Double slash** : corrigé `./image//infra-labo.png` → `./image/infra-labo.png`

### Architecture CSS
- **CSS partagé** : créé `shared.css` pour éliminer ~120 lignes dupliquées entre les 4 fichiers CSS
- **Media query abusive** : supprimé le bloc `min-width: 350px` qui forçait la navbar à toujours s'afficher, écrasant Bootstrap

### HTML & Accessibilité
- **`lang`** : corrigé `lang="fr"` sur toutes les pages (était `en` sur Consultation et Notre Équipe)
- **Viewport** : ajouté `<meta name="viewport">` manquant sur la page d'accueil
- **Meta description** : ajouté sur les 4 pages
- **Navbar mobile** : activé le toggler Bootstrap 5 sur toutes les pages (était commenté)
- **Réseaux sociaux** : corrigé les URLs (`wwww` → `www`) et ajouté `rel="noopener noreferrer"`
- **Carte localisation** : ajouté l'iframe Google Maps dans les sections Localisation (sections présentes mais vides)
- **`alt` images** : amélioré les attributs `alt` sur toutes les images
- **`aria-label`** : ajouté sur les boutons des carrousels et la navbar toggler
- **`loading="lazy"`** : ajouté sur toutes les images des carrousels
- **`autocomplete`** : ajouté sur les champs du formulaire

### Contenu
- **Notre Équipe** : page entièrement développée avec 6 profils de médecins (spécialités, descriptions, lien RDV)
