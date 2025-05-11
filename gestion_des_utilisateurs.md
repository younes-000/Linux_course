#  Gérer les utilisateurs sous Linux

##  Description du projet

Dans ce scénario, un nouvel employé (`researcher9`) a rejoint l’organisation. L’équipe de recherche m’a donc demandé de gérer les accès utilisateurs. Le système d’exploitation utilisé est Linux, ce qui implique une approche en ligne de commande via le terminal Bash.

##  Commandes utilisées

1. **Ajouter un utilisateur :**
   ```bash
   sudo useradd researcher9
   ```

2. **Affecter un groupe (principal et secondaire) :**
   ```bash
   sudo usermod -g research_team researcher9
   ```

3. **Supprimer un utilisateur :**
   ```bash
   sudo userdel researcher9
   ```

4. **Supprimer le groupe de l’utilisateur :**
   ```bash
   sudo groupdel researcher9
   ```

   > Lorsqu’un nouvel utilisateur est créé, un groupe portant le même nom est également créé. Il est recommandé de supprimer ces groupes vides après suppression de l’utilisateur.

5. **Changer le propriétaire d’un fichier :**
   ```bash
   sudo chown researcher9 /home/researcher2/projects/project_r.txt
   ```

> Toutes ces commandes nécessitent `sudo`. L’option `-g` permet d’assigner un groupe principal.

##  Ajout d’un utilisateur à un groupe

Pour ajouter `researcher9` au système et l’ajouter au groupe `research_team` :

```bash
sudo useradd researcher9
sudo usermod -g research_team researcher9
```

Ou en une seule commande :

```bash
sudo useradd researcher9 -g research_team
```

##  Attribution de propriété d’un fichier

Attribuer la propriété du fichier `project_r.txt` à `researcher9` :

```bash
sudo chown researcher9 /home/researcher2/projects/project_r.txt
```

##  Ajouter un groupe secondaire

Plus tard, `researcher9` travaille également pour le département des ventes (`sales_team`). Pour l’y ajouter sans le retirer de son groupe principal :

```bash
sudo usermod -a -G sales_team researcher9
```

##  Supprimer un utilisateur

Lorsque `researcher9` quitte l’entreprise :

```bash
sudo userdel researcher9
sudo groupdel researcher9
```

##  Résumé

Dans ce projet, j’ai démontré comment :

- Ajouter des utilisateurs
- Les affecter à un groupe principal et secondaire
- Attribuer la propriété des fichiers
- Supprimer des utilisateurs et nettoyer les groupes associés
