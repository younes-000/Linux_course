#  Guide des permissions de fichiers sous Linux

##  Description du projet

Dans cette mission, j'ai dû ajuster les permissions des fichiers et dossiers situés dans un répertoire spécifique en utilisant l'interface en ligne de commande sous Linux (shell Bash).

##  Vérification des fichiers et dossiers

Pour commencer, j'ai utilisé la commande `ls` afin de lister les répertoires existants. Le répertoire ciblé nommé `data_project` est apparu dans la liste. Ensuite, en utilisant `ls -la`, j'ai pu afficher tous les fichiers visibles et cachés dans ce répertoire.

Les éléments découverts :

- Un fichier caché : `.config_secret`
- Trois fichiers standards :
  - `report.txt`
  - `summary.log`
  - `analysis.csv`
- Un dossier : `backup`

##  Compréhension des permissions

Chaque fichier ou dossier possède une chaîne de 10 caractères définissant ses permissions :

**Exemple :**

```
-rwxrw-r--
```

- Le **1er caractère** indique le type (`-` pour fichier, `d` pour dossier).
- Les **caractères 2 à 4** définissent les permissions de l’utilisateur propriétaire (`rwx`).
- Les **caractères 5 à 7** définissent les permissions du groupe (`rw-`).
- Les **caractères 8 à 10** définissent les permissions des autres utilisateurs (`r--`).

##  Modifier les permissions

La commande `chmod` permet de modifier les permissions :

- `chmod u+(r/w/x) fichier` : Ajoute une permission à l’utilisateur.
- `chmod u-(r/w/x) fichier` : Retire une permission à l’utilisateur.
- `chmod g+(r/w/x) fichier` : Ajoute une permission au groupe.
- `chmod g-(r/w/x) fichier` : Retire une permission au groupe.
- `chmod o+(r/w/x) fichier` : Ajoute une permission aux autres.
- `chmod o-(r/w/x) fichier` : Retire une permission aux autres.

##  Modifications effectuées

- Retirer les droits d'exécution aux autres utilisateurs sur `report.txt` :
  ```bash
  chmod o-x report.txt
  ```

- Ajouter les droits d’écriture au groupe sur `analysis.csv` :
  ```bash
  chmod g+w analysis.csv
  ```

###  Modification des permissions sur un fichier caché

Pour le fichier `.config_secret`, j'ai retiré les droits d'écriture pour l’utilisateur et le groupe, en conservant la permission de lecture pour le groupe :

```bash
chmod u-w,g-w,g+r .config_secret
```

###  Modification des permissions sur un dossier

J'ai limité l'accès au dossier `backup` en retirant les droits d'exécution aux autres utilisateurs :

```bash
chmod o-x backup
```

##  Résumé

Cette tâche m'a permis de démontrer ma capacité à ajuster précisément les permissions en adéquation avec les directives de sécurité de mon organisation, en utilisant efficacement les commandes Linux appropriées.
