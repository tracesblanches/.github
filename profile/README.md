<picture>
  <source media="(prefers-color-scheme: dark)" srcset="banner-dark.svg">
  <img alt="Traces Blanches : carte, pistes, pentes et guidage vocal pour le ski nordique, sans réseau" src="banner-light.svg" width="100%">
</picture>

<p align="center">
  <a href="https://tracesblanches.github.io/fr/"><b>Site</b></a> ·
  <a href="https://tracesblanches.github.io/fr/fonctionnalites.html">Fonctionnalités</a> ·
  <a href="https://tracesblanches.github.io/fr/faq.html">FAQ</a> ·
  <a href="https://tracesblanches.github.io/fr/licences.html">Sources et crédits</a> ·
  <a href="https://github.com/tracesblanches/tracesblanches/issues">Issues</a> ·
  <a href="https://tracesblanches.github.io/">English</a>
</p>

<p align="center">
  <img alt="Noyau en Rust" src="https://img.shields.io/badge/noyau-Rust-1f4e79?style=flat-square&logo=rust">
  <img alt="App Android en Kotlin" src="https://img.shields.io/badge/app-Android_(Kotlin)-1f4e79?style=flat-square&logo=android">
  <img alt="Hors ligne" src="https://img.shields.io/badge/r%C3%A9seau-aucun_requis-1f4e79?style=flat-square">
  <img alt="Licence GPL-3.0-or-later" src="https://img.shields.io/badge/licence-GPL--3.0--or--later-1f4e79?style=flat-square">
</p>

En forêt du Haut-Doubs ou au fond d'une vallée du Queyras, le réseau tombe. Le plan des pistes est une image, le bulletin d'avalanche est sur un autre site, et vos doigts sont dans des gants.

Traces Blanches réunit sur le téléphone ce qu'il faut pour une journée de ski de fond ou de ski de randonnée nordique en France, et le garde disponible sans réseau. Vous préparez la journée la veille ou le matin. Ensuite, le téléphone reste dans la poche et une voix vous guide.

| | Dépôt | Contenu |
|---|---|---|
| 🎿 | [**tracesblanches**](https://github.com/tracesblanches/tracesblanches) | Le noyau en Rust (chaîne de données, routage, temps estimés, voix), le serveur de packs et l'app Android en Kotlin. |
| 🌐 | [**tracesblanches.github.io**](https://github.com/tracesblanches/tracesblanches.github.io) | Le site. |
| 📋 | [**.github**](https://github.com/tracesblanches/.github) | Ce profil, les règles de contribution et les modèles d'issues. |

#### Ce que contient un pack hors ligne

Un pack couvre un site. Un serveur construit les packs de 268 sites, toute la France (219 domaines nordiques du recensement, 41 zones de ski de randonnée nordique, les sections des grandes traversées), et les met à jour chaque jour ; le téléphone ne télécharge que ce qui a changé, puis lit le pack sans connexion.

- **Deux fonds de carte** : Plan IGN v2 et OpenStreetMap, en tuiles vectorielles, et un fond léger de toute la France pour le mode libre.
- **Les pistes de fond** d'OpenStreetMap : nom, difficulté, classique ou skating, sens.
- **Les pentes de plus de 30°**, calculées sur le relief LiDAR HD de l'IGN au pas de 5 m.
- **L'exposition aux avalanches**, modélisée sur le relief et la forêt (méthodes AutoATES v3.0 et Flow-Py, portées en Rust).
- **Les zones protégées** et leurs règles par période, les **refuges** (refuges.info, Camptocamp, OpenStreetMap), les **zones sans aucun réseau**, 112 compris (cartes ARCEP).
- **La neige estimée** à partir de la simulation nivologique de Météo-France, la **météo** heure par heure (AROME), le **bulletin d'avalanche** du massif avec sa date.

Chaque couche garde la licence de sa source. Les sources à usage personnel ne sont jamais dans un pack publié.

#### Ce que fait l'app Android

- La carte, en style fond, ski de randonnée nordique ou guidage, clair ou sombre ; le mode libre sur toute la France.
- La journée préparée la veille, en charge et sur le Wi-Fi ; le matin, une boucle à la mesure du temps, du groupe et de la technique, avec l'heure de demi-tour avant la nuit, dans tout domaine.
- Le suivi écran éteint, le guidage vocal en français ou en anglais, « Ramène-moi », le cap dans le brouillard, les alertes avant une pente de plus de 30°.
- Le hors piste de ski de randonnée nordique, avec sa difficulté et des conseils ; le groupe par Bluetooth, sans réseau.
- Le partage de la sortie en GPX ou FIT, et vers Health Connect.

#### Sortie hiver 2027

L'app sort à l'hiver 2027, à un prix modique, sans abonnement ni publicité. Le prix couvre l'hébergement du serveur qui construit et met à jour les packs chaque jour. D'ici là, tout le travail est consultable sur GitHub, et le code est libre.

#### Contribuer

Les contributions sont bienvenues, y compris celles écrites avec un outil d'IA. Chaque contribution arrive avec ses tests et ses preuves, et son auteur en répond. La CI tourne sur le poste du contributeur (`scripts/ci`). Lisez [CONTRIBUTING.md](https://github.com/tracesblanches/.github/blob/main/CONTRIBUTING.md) avant d'ouvrir une demande de fusion.

#### Sécurité en montagne

Traces Blanches ne présente jamais une pente comme hors de portée des avalanches. L'app montre l'âge et la source de chaque information. Elle ne remplace ni le bulletin d'avalanche, ni votre jugement sur le terrain.

<sub>Offline map, trails, slopes and voice guidance for cross-country and Nordic backcountry skiing across France: Rust core, pack server, Android app, coming winter 2027, at a modest price, with no subscription and no ads; the price covers the hosting. Code under GPL-3.0-or-later with an app store exception. <a href="https://tracesblanches.github.io/">English page</a>.</sub>
