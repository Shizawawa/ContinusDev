Projet DevOps
========================

Consignes:
```bash
https://gitlab.esgi.io/garygitton/cours-iw1/blob/master/CONSIGNE.md
```

L'équipe
------------

  * Elodie Flores
  * Kunborribo Hing
  * Alexandre Morcrette
  * Classe 5IW1

Le projet
------------

Il s'agit d'un projet qui contient des tests unitaires et le but ici est de montrer un circuit d'intégration continu en passant par une pipeline de déploiement pour au final atterrir sur un serveur.

Les technologies
------------

Notre projet est en Symfony 4, nous utilisons Travis CI pour faire une pipeline de déploiement vers un serveur Heroku. Nous avons des tests unitaires dans le projet pour démontrer l'efficacité de la pipeline.

Fonctionnement
------------
<p>L'ensemble des tâches effectuées par Travis sont décrites et ordonnées dans le fichier travis.yml qui est d'ailleurs commenté pour en expliquer les compléxités.</p>
<p>Lorsque nous réalisons un push sur notre git (branche master ou dev), le commit va être intercepté par Travis CI qui va ensuite réaliser une batterie de tests. Tout d'abord Travis CI va exécuter nos tests unitaires écrits en PHP à l'aide de PHPunit. Nous testons le projet sous plusieurs version de PHP, nous vérifions les synthaxes, puis en dernier nous vérifions la validité de la base de données.</p>
<p>Une fois l'ensemble des tests exécutés, si ils sont réussi par l'application, alors Travis va déployer la nouvelle version du projet que nous avons commit vers notre serveur heroku.</p>
