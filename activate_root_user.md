# ACTIVER L'UTILISATEUR ROOT

Pour des raisons de sécurité, dans la plupart des distributions Linux, l'utilisateur `root` est désactivé.

Ayant tous les droits sur la machine, il est vite fait de faire des erreurs et pour certaines, irreversibles, comme ce fût le cas pour moi, il y a quelques temps, où j'ai supprimé des dossiers et de fichiers système que je n'aurais pu supprimer avec mon compte utilisateur classique.

Ce qui m'a contraint à faire une réinstallation complète de la machine. Ben... c'est pas drôle du tout !

<br>

> [!CAUTION]
> Tous les utilisateurs expérimentés les disent:
>
> <br>SI VOUS NE SAVEZ PAS CE QUE VOUS FAITES, NE LE FAITES PAS !!

<br>Pour commencer, il faut créer un mot de passe pour `root`:

```bash
sudo passwd root
```

<br>Vous êtes invités à taper le nouveau mot de passe, puis, à le retaper:

<pre>
Nouveau mot de passe : &lt;votre_pass&gt;
Retapez le nouveau mot de passe : &lt;votre_pass&gt;
</pre>

<br>Bien évidemment, je ne saurais que trop conseiller de:
1. Ne jamais l'écrire nulle part
2. Trouver un mot de passe complexe (symboles, alphanumérique, assez long)
3. Essayer d'en trouver un facile à retenir tout de même pour vous
4. Ne jamais le donner à personne, on croit connaître les gens...

Pour se connecter à `root`, tapez simplement:

```bash
su -
```

<br>Il faut maintenant vérifier que `root` a bien tous les droits.
<br>Pour ce faire, il va falloir editer le fichier `visudo`, qui ne peut être éditer **QUE** par `root` ou tout autre utilisateur ayant tous les droits.

Editez le fichier `visudo`:

```bash
su -
```

Entrez votre mot de passe, puis tapez:

```bash
visudo
```

Cherchez la ligne:
<pre>
&#35 User privilege specification
</pre>

Puis ajoutez ectte ligne (si elle n'y est pas déjà):
```
root    ALL=(ALL:ALL) ALL
```

<br>

> [!TIP]
> Ne vous connectez a `root` <b>QUE</b> temporairement, le temps de votre action
> <br>Une fois terminée, sortez du mode `root` avec la commande `exit`
