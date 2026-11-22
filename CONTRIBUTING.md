# Contribuer à Traces Blanches

Les contributions sont bienvenues : correction, test, donnée, traduction, idée. Les contributions écrites avec un outil d'IA sont bienvenues aussi, aux conditions ci-dessous.

- Un bogue, une idée, une donnée fausse ou un site à ajouter : ouvrez une issue avec le modèle qui correspond.
- Une faille de sécurité : ne l'ouvrez pas en public, suivez [SECURITY.md](SECURITY.md).
- Le [code de conduite](CODE_OF_CONDUCT.md) s'applique partout dans le projet.

Pour un changement important, ouvrez d'abord une issue. Nous verrons ensemble s'il entre dans le projet avant que vous n'y passiez du temps.

## Tests et preuves

Chaque demande de fusion prouve ce qu'elle affirme.

- **Un test par comportement modifié.** Le test échoue sans votre changement et passe avec.
- **Références dorées obligatoires.** Les sorties de la chaîne de données et du noyau sont comparées à des références versionnées ([`fixtures/golden/`](https://github.com/tracesblanches/tracesblanches/tree/main/fixtures/golden), voir le [CONTRIBUTING du dépôt](https://github.com/tracesblanches/tracesblanches/blob/main/CONTRIBUTING.md#références-dorées)). Si votre changement déplace une référence, mettez-la à jour dans le même commit et expliquez l'écart dans la demande de fusion, chiffres avant et après.
- **Sorties collées.** Collez dans la demande de fusion la sortie des commandes que vous avez lancées. « Ça devrait marcher » n'est pas une preuve.
- **Performance mesurée sur le cas qui domine.** Une optimisation donne le temps total de la tâche avant et après, sur le cas qui pèse le plus (par exemple le `build-all` complet d'un site), pas sur une seule étape.
- **Python hors du chemin critique.** Python sert d'oracle de référence ou d'outil. Le code qui tourne en production est en Rust, et en Kotlin pour l'app Android.

La CI tourne sur votre poste, pas sur GitHub Actions. Avant d'ouvrir la demande de fusion, depuis la racine du dépôt :

```sh
git config core.hooksPath .githooks   # une fois par clone : le hook pre-push lance scripts/ci --quick
scripts/ci --quick                    # fmt, clippy -D warnings, cargo test --workspace
scripts/ci                            # tout : tests, scénarios, doc, cargo deny, données publiables, fuzz, bancs, Android
```

Le détail des étapes est dans `docs/ci-locale.md`.

La version de Rust est figée dans `rust-toolchain.toml`. Mettez à jour la documentation (`README.md`, `docs/`) dans le même commit quand un comportement, une option ou une valeur par défaut change.

## Contributions écrites avec un outil d'IA

Elles sont acceptées au même niveau d'exigence que les autres.

- **Relecture humaine.** Vous avez lu chaque ligne, vous la comprenez et vous savez l'expliquer en revue.
- **Preuves.** Tests, sorties de commandes et chiffres, comme pour toute contribution.
- **Responsabilité.** Vous signez la contribution et vous en répondez : exactitude, sécurité, droits sur le code. Vérifiez que l'outil n'a pas recopié du code sous une licence incompatible.
- **Taille raisonnable.** Une demande de fusion traite un sujet. Nous refusons les lots générés et non relus.

## Licence et accord de chaque contributeur

- Le code est sous **GPL-3.0-or-later**, avec une permission additionnelle (section 7 de la GPLv3) qui autorise la diffusion par les boutiques d'applications malgré leurs conditions d'usage. Le texte est dans `LICENSE-EXCEPTION`.
- `crates/avalanche` reste sous **EUPL-1.2** : c'est un portage de com4FlowPy (AvaFrame). Aucune crate embarquée sur le téléphone n'en dépend.
- L'exception ne couvre que le code dont les auteurs l'ont acceptée. Chaque contributeur l'accepte donc explicitement, de deux façons :
  1. **DCO.** Chaque commit porte une ligne `Signed-off-by` (`git commit -s`). Elle certifie le [Developer Certificate of Origin 1.1](https://developercertificate.org/).
  2. **Phrase d'accord.** Vous cochez dans le modèle de demande de fusion : « J'accepte que ma contribution soit diffusée sous GPL-3.0-or-later avec l'exception pour les boutiques d'applications de `LICENSE-EXCEPTION`, et sous EUPL-1.2 pour ce qui touche `crates/avalanche`. »
- Du code tiers n'entre que sous une licence compatible, avec son avis de copyright, et une ligne dans `THIRD-PARTY.md`.

## Règles des données

Les packs publiés n'emportent que des données que nous avons le droit de redistribuer.

- **Jamais de source d'usage personnel dans un pack publié.** Ces sources ne tournent qu'avec `SKIMAP_PERSONAL_SOURCES=1`, et leurs métadonnées portent `personal_use_only: true`. Exemples aujourd'hui : état des pistes publié sans licence (Espace Nordique Jurassien, Nordic France, pages de mairies), CLPA et EPA du site d'INRAE, API gratuite d'Open-Meteo, pages des émetteurs de titres nordiques.
- **Ne jamais redistribuer un plan des pistes de station.** Ni image, ni couche raster, ni plan déformé, dans un pack ou dans le dépôt. Le plan peut être lu en local pour reporter ses informations sur nos propres tracés. Dans une issue, un lien vers le plan suffit.
- **Une couche par type d'objet et par source.** Ne mélangez jamais OpenStreetMap (ODbL) et refuges.info ou Camptocamp (CC BY-SA) pour un même type d'objet : les deux licences sont incompatibles.
- **Une nouvelle source arrive avec sa licence lue.** Citez l'adresse, le passage exact et la date de lecture dans `docs/licences/`, et l'attribution dans les métadonnées de la couche.
- **Corrections d'OpenStreetMap** : faites-les dans OpenStreetMap, selon ses règles. L'app prépare au plus une note, que le skieur relit et envoie lui-même ; aucun envoi automatique.
- **Sécurité** : aucun texte ne présente une pente ou un itinéraire comme sans risque d'avalanche. Chaque information affiche sa date et sa source.

## Demandes de fusion

- Un sujet par demande de fusion. Le message de commit cite l'issue (`Refs #12`).
- Remplissez le modèle : ce qui change, les preuves, la phrase d'accord.
- Textes publics : voix active, phrases courtes, faits vérifiés, aucun superlatif.
