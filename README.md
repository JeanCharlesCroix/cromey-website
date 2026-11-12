# crome.fr — site vitrine

Site vitrine de **cromey**, entreprise d'accompagnement d'entreprise.
Site statique (HTML/CSS/JS, sans build), responsive, hébergé chez OVHcloud.

## Structure

```
index.html              Accueil
services.html           Services
a-propos.html           À propos
contact.html            Contact (formulaire factice en mailto:)
mentions-legales.html   Mentions légales
404.html                Page d'erreur
assets/css/style.css    Styles (couleurs et polices dans :root)
assets/js/main.js       Menu mobile
assets/img/             Images et favicon
.htaccess               HTTPS, redirection www, cache, en-têtes (Apache OVH)
```

Les textes entre crochets `[...]` sont à remplacer.

## Identité visuelle

| Rôle      | Couleur   |
|-----------|-----------|
| Encre     | `#0f2a36` |
| Cuivre    | `#c26a34` |
| Papier    | `#f7f4ee` |

Titres en serif, texte en sans-serif — polices système uniquement (pas de Google Fonts, donc pas de transfert de données à un tiers).

## Voir le site en local

```bash
python3 -m http.server 8000
```

Puis ouvrir http://localhost:8000.

## Déploiement sur OVH

Le workflow `.github/workflows/deploy-ovh.yml` envoie le site en FTPS dans le dossier `www/` de l'hébergement à chaque push sur `main`.
Il faut d'abord créer trois secrets dans le dépôt GitHub : `OVH_FTP_SERVER`, `OVH_FTP_USERNAME`, `OVH_FTP_PASSWORD` (disponibles dans l'espace client OVH, rubrique Hébergements > FTP-SSH).
Sans ces secrets, le workflow ne fait rien.
