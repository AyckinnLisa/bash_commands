# AJOUTER UN UTILISATEUR POUR SUDO

Pour qu'un utilisateur puisse utiliser la commande `sudo`, il faut l'ajouter au groupe, dans la plupart des cas, cela se fait automatiquement au moment de la création du compte, si, biensûr, les droits administrateur lui sont donnés.

Dans d'autre cas comme pour Debian par exemple, il faut le faire à la main.

Evidemment, il faut que `root` soit activé sur votre machine, puisqu'il vous faut les droits super-utilisateur mais que vous ne pouvez pas utiliser `sudo` avec votre compte.

Si ce n'est pas le cas, voici comment l'[activer](https://github.com/AyckinnLisa/bash_commands/blob/main/activate_root_user.md).

Connectez-vous à `root`:

```bash
su -
```

Entrez le mot de passe, puis tapez:

```bash
adduser <user> root
```

Remplacez `<user>` par le nom de l'utilisateur en question.