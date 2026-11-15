# Politique de sécurité

Traces Blanches sert en montagne, parfois loin de tout réseau. Une faille peut toucher la carte, le guidage ou les données d'un skieur. Merci de nous la signaler.

## Signaler une faille

Signalez-la en privé, par le signalement privé de GitHub : onglet **Security** du dépôt concerné, puis **Report a vulnerability**. N'ouvrez pas d'issue publique pour une faille.

Indiquez ce que vous avez trouvé, comment le reproduire, et la version ou le commit concerné. Nous répondons dès que le signalement a été lu. Le correctif sort avant la publication des détails.

## Versions suivies

Les correctifs vont dans le dernier commit de `main`. Il n'existe pas d'ancienne branche maintenue.

## Ce qui est concerné

Notamment :

- la lecture des packs et des fichiers téléchargés (formats GeoJSON, PMTiles, rasters, clips audio) ;
- le téléchargeur de la chaîne de données (cache, quotas, clés d'API qui ne doivent apparaître dans aucun journal) ;
- l'app Android, quand elle existera : position, trace, plan de sortie ;
- les services prévus : téléchargement des packs, alerte en cas de non-retour, échange de jetons Strava.

## Ce qui ne l'est pas

- Une donnée fausse dans une source (piste mal tracée dans OpenStreetMap, refuge fermé) : ouvrez une issue avec le modèle « Données ».
- Un appareil déjà compromis, une clé d'API divulguée par son propriétaire.

## Sécurité en montagne

Une erreur de pente, d'exposition aux avalanches ou de zone protégée n'est pas une faille informatique, mais elle compte autant. Signalez-la en public avec le modèle « Données », en précisant le site et la position.
