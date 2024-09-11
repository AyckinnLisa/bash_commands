# SAVOIR QUELS DOSSIERS SONT INSCRIPTIBLES

Dans certains cas, notamment de piratage de machine, il peut être nécessaire de savoir quels dossiers sont inscriptibles, c'est à dire, dans quels dossiers il est possible d'écrire ou non.

Dans cette même perspective, le dossier `/tmp`, par exemple, est l'un des dossiers les plus importants.

En effet, dans la mesure où tout son contenu est supprimé à chaque redémarrage, il est très facile d'y cacheer des `payloads` ou des scripts le temps de notre action.

Ainsi, même si par mégarde vous oubliez de supprimer vos traces, elles le seront au prochain démarrage.

<br>

> [!WARNING]
> CE N'EST PAS LE REMÈDE À TOUT !!
> <br>Il vaut quand même mieux controler vos actions et supprimer vos traces vous même !

<br>Pour savoir si `/tmp`, entre autres, est inscriptible, il suffit de taper:

```bash
find / -type d -writable
```

<br>

> [!NOTE]
> Trouve (`find`) à la racine (`/`) tous les éléménts de type "dossier" (`-type d`) inscriptibles (`-writable`)

<br>

Cela sortira le listing de **TOUS** les dossiers inscriptibles. Y compris ceux avec les permissions non accordées.

Ces dossiers n'étant pas utiles, il est possible de n'afficher que les dossiers auxquels nous avons accès:

```bash
find / -type d -writable 2>/dev/null
```

En effet, `2>/dev/null` est une commande qui permet de ne pas afficher les erreurs en sortie, comme par exemple, les permissions non accordées.
