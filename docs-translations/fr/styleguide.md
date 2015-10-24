# À prpos de la documentation d'Electron

Trouvez la section appropriée : [lire la documentation d'Electron](#reading-electron-documentation)
ou [rédiger la documentation d'Electron](#writing-electron-documentation).

## Rédiger la documentation d'Electron

Voilà les règles que nous avons utilisé pour écrire la documentation d'Electron.

- Utiliser un titre `h1` par page au maximum.
- Utiliser `bash` au lieu de `cmd` dans les blocs de code (pour la colorisation
  syntaxique).
- Les titres `h1` doivent correspondre à un objet (i.e. `browser-window` →
  `BrowserWindow`).
  - Les noms de fichiers séparés par des tirets sont tout de même valides.
- Pas de titres suivis directement par un autre titre, utiliser une phrase de séparation au minimum.
- Les noms de méthodes sont entourés de "`".
- Les noms d'évènements sont entourés de "'".
- Pas de liste à puces de plus de 2 niveaux d'imbriquation (à cause du moteur
  de rendu de markdown).
- Ajouter des titres de section : Évènements, méthodes de classe et méthodes
  d'instances.
- Utiliser le futur plutôt que le conditionnel pour les sorties.
- Les évènements et les méthodes sont des titres `h3`.
- Les arguments optionnels s'écrivent `function (requis[, optionnel])`.
- Les arguments optionels sont suivi de points de suspension quant ils peuvent
  être utilisés plusieurs fois.
- Les lignes ne doivent pas dépasser 80 colonnes.
- Les méthodes spécifiques à une plateforme sont précisés en italique.
  - ```### `method(foo, bar)` _OS X_```
- Utiliser 'in the ___ process' plutôt que 'on'

### Traduction de la documentation

Les traductions de la doc d'Electron sont situés dans le dossier `docs-translations`.

Pour en ajouter une nouvelle (ou une partie) :

- Créer un nouveau sous-dossier nommé par l'abbrévation de la langue
- Dupliquer le dossier `docs` dans ce sous-dossier, conserver les noms de
  fichiers et dossiers.
- Traduisez les fichiers.
- Mettre à jour les liens du `README.md` de votre traduction.
- Ajouter un lien vers votre dossier de traduction au [README](https://github.com/atom/electron#documentation-translations) principal
  d'Electron.

## Lire la documentation d'Electron

Voilà quelques astuces pour comprendre la syntaxe de la documentation
d'Electron.

### Méthodes

Voici un exemple de documentation de [méthode](https://developer.mozilla.org/en-US/docs/Glossary/Method) :

---

`methodName(required[, optional]))`

* `required` String, **requis**
* `optional` Integer

---

Le nom de la méthode est suivi par les arguments qu'elle prend. On peut repérer
les arguments optionels car le nom de l'argument et la virgule le précédant
(si il suit un autre argument) sont entourés de crochets.

En dessous de la méthode, il y a des informations supplémentaires sur les
arguments. Le type de l'argument est noté par un de ces types communs :
[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String),
[`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number),
[`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object),
[`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
ou un type particulier comme [`webContent`](api/web-content.md) d'Electron.

### Évènements

Un exemple de documentation d'[évènement](https://developer.mozilla.org/en-US/docs/Web/API/Event) : 

---

Évènement: 'wake-up'

Retourne:

* `time` String

---

L'évènement est une chaine de caractère qui est utilisé après la méthode
d'écoute `.on`. Si il renvoie une valeur alors elle est notée en dessous ainsi
que le type de cette valeur. Voilà à quoi ressemble l'écoute d'un évènement :

```javascript
Alarm.on('wake-up', function(time) {
  console.log(time)
})
```
