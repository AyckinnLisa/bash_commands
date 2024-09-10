# FAIRE APPARAITRE UN TERMINAL SUR UNE MACHINE DISTANTE

Dans le cas d'une élévation de privilèges par exemple, ou encore, de la prise de contrôle à distance d'une machine, par `Telnet` ou `NetCat`, il peut s'avérer très utile de travailler avec un Terminal Unix, par habitude par exemple.

Il existe une commande qui permet de faire apparaître un Terminal en utilisant un mini script `Python`.

Pour ce faire, il y a deux pré-requis:
- Etre `root` sur la machine distante
- Il faut que python soit installé sur la machine distante

<br>Pour savoir si vous êtes `root`, il suffit de taper la commande: `id`. 
<br>Pour l'exemple, je vais utiliser la machine `Metasploitable2`

```bash
id
```
<pre>
uid=0(root) gid=0(root)
</pre>

Vous pouvez voir que nous sommes bien `root`.

Nous allons pouvoir envoyer notre script pour faire apparaître le Terminal

```python
python -c "import pty; pty.spawn('/bin/bash')"
```

<br>

> [!NOTE]
> - `python`: Appelle Python. Dans notre cas, c'est Python2 qui est installé sur la machine. Adaptez la commande à la version de Python utilisée par la machine.
> - `-c`: Indique que nous allons lui passer une commande sous forme de chaîne de caractères (notre script)
> - `import pty`: Bibliothèque en charge de l'émulation des Terminaux Unix
> - `pty.spawn()`: Initialise l'instance du Terminal et prend le chemin de celui-ci en paramètre
> - `/bin/bash`: Terminal que nous utilisons sur la `Metasploitable2`.
> <br>A Adapter si vous souhaitez utiliser `zsh` ou un autre Terminal, dans la mesure où il est présent sur la machine

<br>

<pre>
root@metasploitable:/#
</pre>

Voilà, vous avez accès au Terminal et à toutes ses fonctionnalités.

<br>Lien vers les différents [scripts Python pour le spawn de Terminal](https://gtfobins.github.io/gtfobins/python/#suid)
