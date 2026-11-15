## Ce qui change

<!-- Le problème, puis ce que la demande de fusion change. Citez l'issue : Refs #… -->

## Preuves

<!-- Collez la sortie des commandes lancées et les chiffres avant et après. -->

- [ ] `cargo fmt --all --check`, `cargo clippy --workspace --all-targets -- -D warnings` et `cargo test --workspace` passent (sortie collée ci-dessus).
- [ ] Un test couvre chaque comportement modifié.
- [ ] Les références dorées touchées sont mises à jour dans le même commit, avec l'écart expliqué.
- [ ] La documentation est à jour (`README.md`, `docs/`).
- [ ] J'ai relu et je comprends chaque ligne, qu'un outil d'IA l'ait écrite ou non.

## Données

- [ ] Aucune source d'usage personnel n'entre dans un pack publié.
- [ ] Aucun plan des pistes de station n'est redistribué.
- [ ] Toute nouvelle source a sa licence citée dans `docs/licences/` et son attribution dans les métadonnées.

## Accord du contributeur

- [ ] Chaque commit porte une ligne `Signed-off-by` (`git commit -s`), selon le [Developer Certificate of Origin 1.1](https://developercertificate.org/).
- [ ] J'accepte que ma contribution soit diffusée sous GPL-3.0-or-later avec l'exception pour les boutiques d'applications de `LICENSE-EXCEPTION`, et sous EUPL-1.2 pour ce qui touche `crates/avalanche`.
