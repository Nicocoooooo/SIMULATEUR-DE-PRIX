# Simulateur de Prix - Dashboard IProspect

## 📋 Description

Simulateur de prix interactif développé par Hanalytics pour IProspect, permettant d'estimer automatiquement le coût des dashboards analytics en fonction des besoins clients.

## 🎨 Design & Identité Visuelle

- **Charte graphique IProspect** :
  - Noir : `#0F0F0F`
  - Blanc : `#FFFFFF`
  - Vert : `#3EC780`
- **Typographies** : Montserrat (titres) et Inter (corps de texte)
- **Interface moderne** avec thème clair/sombre
- **Responsive design** pour tous les écrans

## ⚡ Fonctionnalités

### Interface Utilisateur
- **Thème adaptatif** : Commutateur clair/sombre avec sauvegarde locale
- **Interface intuitive** : Sliders interactifs et checkbox personnalisée
- **Animations fluides** : Transitions et effets visuels modernes
- **Responsive** : Adaptation automatique mobile/desktop

### Paramètres de Configuration
1. **Sources de données** : 1 à 10 sources
2. **Comptes clients** : 1 à 10 comptes
3. **Leviers marketing** : 1 à 10 leviers
4. **Nomenclature standard** : Oui/Non (checkbox)

### Calculs Automatiques
- **Flexpoints** : `50 × sources × comptes × leviers`
- **Coût flexpoints/an** : `flexpoints × 1.6 × 12`
- **Main d'œuvre** : `850 × 5 = 4 250 €`
- **Stockage** : `1 000 €`
- **Surcoût nomenclature** : `850 €` (si nomenclature non-standard)
- **Coût total** : Somme de tous les éléments

## 🚀 Installation & Utilisation

### Prérequis
- Navigateur web moderne (Chrome, Firefox, Safari, Edge)
- Connexion internet (pour les polices et icônes)

### Lancement
1. Télécharger le fichier `index.html`
2. Ouvrir le fichier dans un navigateur web
3. Le simulateur est immédiatement fonctionnel

### Utilisation
1. **Ajuster les paramètres** via les sliders et la checkbox
2. **Visualiser les résultats** en temps réel dans la section "Estimation des Coûts"
3. **Changer de thème** via le bouton en haut à droite
4. **Consulter le coût total** mis en évidence en bas

## 🛠️ Architecture Technique

### Technologies Utilisées
- **HTML5** : Structure sémantique
- **CSS3** : 
  - Variables CSS pour le theming
  - Flexbox et Grid pour la mise en page
  - Animations et transitions
  - Media queries pour le responsive
- **JavaScript Vanilla** :
  - Gestion des événements
  - Calculs dynamiques
  - LocalStorage pour la persistance du thème
  - Manipulation du DOM

### Librairies Externes
- **Font Awesome 6.4.0** : Icônes
- **Google Fonts** : Montserrat & Inter

### Structure des Fichiers
```
projet/
└── index.html (fichier unique autonome)
```

## 🎯 Logique Métier

### Formules de Calcul
```javascript
// Calcul des flexpoints
flexpoints = 50 * sources * comptes * leviers;

// Coût annual des flexpoints
coutFlexpointsAn = flexpoints * 1.6 * 12;

// Coûts fixes
coutMainOeuvre = 850 * 5; // 4 250 €
coutStockage = 1000; // 1 000 €

// Surcoût conditionnel
surtaxeNomenclature = nomenclatureStandard ? 0 : 850;

// Total
coutTotal = coutFlexpointsAn + coutMainOeuvre + coutStockage + surtaxeNomenclature;
```

### Règles de Gestion
- **Nomenclature standard** = coût réduit
- **Nomenclature personnalisée** = surcoût de 850€
- **Calculs en temps réel** lors des modifications
- **Affichage conditionnel** du surcoût nomenclature

## 🎨 Caractéristiques UX/UI

### Design System
- **Cartes flottantes** avec ombres et animations
- **Sliders personnalisés** avec indicateurs visuels
- **Badges de valeurs** pour un feedback immédiat
- **Animations de transition** pour une expérience fluide
- **Effets de hover** interactifs

### Accessibilité
- **Contraste respecté** pour la lisibilité
- **Tailles tactiles optimisées** pour mobile
- **Navigation au clavier** possible
- **Feedback visuel** sur toutes les interactions

## 📱 Responsive Design

### Points de Rupture
- **Desktop** : > 768px (layout 2 colonnes)
- **Mobile** : ≤ 768px (layout 1 colonne)

### Adaptations Mobile
- Navigation en colonne unique
- Taille des cartes adaptée
- Espacement optimisé
- Textes redimensionnés

## 🔧 Personnalisation

### Modification des Tarifs
Les tarifs peuvent être ajustés dans la fonction `calculerPrix()` :
```javascript
const flexpoints = 50 * sources * comptes * leviers; // Modifier le coefficient 50
const coutFlexpointsAn = flexpoints * 1.6 * 12; // Modifier 1.6 (coût unitaire)
const coutMainOeuvre = 850 * 5; // Modifier 850 (tarif horaire) ou 5 (heures)
```

### Modification des Limites
Ajuster les attributs `min` et `max` des sliders dans le HTML :
```html
<input type="range" id="sources" min="1" max="10" value="1">
```

## 📊 Exemple de Calcul

**Configuration** :
- Sources : 3
- Comptes : 2  
- Leviers : 4
- Nomenclature : Standard

**Résultat** :
- Flexpoints : 50 × 3 × 2 × 4 = 1 200
- Coût flexpoints/an : 1 200 × 1.6 × 12 = 23 040 €
- Main d'œuvre : 4 250 €
- Stockage : 1 000 €
- **Total : 28 290 €**

## 🚀 Déploiement

### Hébergement Simple
Le fichier `index.html` peut être :
- Hébergé sur n'importe quel serveur web
- Ouvert directement depuis le système de fichiers
- Déployé sur des plateformes comme Netlify, Vercel, GitHub Pages

### Intégration
Peut être intégré dans :
- Site web existant (iframe ou intégration directe)
- Application web plus large
- CRM ou outils internes

## 📝 Notes Techniques

- **Compatibilité** : Tous navigateurs modernes
- **Performance** : Optimisé pour une exécution fluide
- **Maintenance** : Code modulaire et commenté
- **Évolutivité** : Structure extensible pour nouvelles fonctionnalités

## 🔄 Évolutions Possibles

- Export PDF des devis
- Sauvegarde des configurations
- Historique des simulations
- Intégration API pour tarifs dynamiques
- Multi-langue
- Authentification utilisateur