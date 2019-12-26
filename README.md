<h1 align="center">Formation sur les bonnes pratiques Javascript ✨</h1>

Bienvenue sur cette Formation Javascript dans lequel vous allez decouvrir (ou re-decouvrir) les bonnes pratiques du langage !

## Informations
- **Objectifs** :dart: : Améliorer la qualité d'un code écrit en Javascript !
- **Public** :two_men_holding_hands: : Toutes les personnes qui codent ou qui seront amenés à coder en Javascript
- **Pré-requis** :heavy_check_mark: : Avoir les notions de base de Javascript
- **Méthode pédagogique** :game_die: : 50% théorique / 50% pratique + 1 exercice final
- **Description** :bookmark: : Aujourd'hui de plus en plus de développeurs sont formés et sont amenés à utiliser des frameworks comme Angular, React, Vue ou Node. Cependant, étant directement plongés dans les vagues sujets que peut amener un de ces frameworks, les notions même de javascript qui est à l'ogine de ces outils sont souvents oubliés ou vu trop rapidement !! Le principe de cette formation est donc de revoir ensemble quelques règles de base de ce langage.

## Formation
Pour chacun des points que nous allons aborder ensemble, il y aura une partie théorique et une partie pratique. Pour la partie pratique, il est nécessaire de cloner le projet sur votre ordinateur ``git clone git@github.com:landschootl/bonnes-pratiques-js.git``.

### Nommer correctement les variables et des méthodes
Il est important de bien nommer les variables et les noms des méthodes. Cela vous simplifiera la vie lorsque vous (ou un de vos collègues) devrez relire votre code suite à une évolution à effectuer ou un bug à corriger. Vous payez rarement aux nombres de caractères alors n'hésitez pas !

```
const list = ['Fred', 'Jacques'];                   ❌
const list2 = ['baleine', 'singe', 'loup'];         

function add(name) {                                
  list2.push(name);
};

const nameList = ['Fred', 'Jacques'];               ✅
const petList = ['baleine', 'singe', 'loup'];       

function addPet(name) {                             
  petList.push(name);
};
```

### Indenter correctement son code
C'est pareil que pour le nommage des variables et méthodes, l’indentation permet de structurer son code pour le rendre plus lisible.

```
if (Platform.OS === 'ios') {                        ❌
if (typeof type !== 'undefined') { 
console.warn('Alert.alert() with a 5th "type" parameter is deprecated and will be removed. Use AlertIOS.prompt() instead.'); AlertIOS.alert(title, message, buttons, type);
return;
}
AlertIOS.alert(title, message, buttons);
} else if (Platform.OS === 'android') {
AlertAndroid.alert(title, message, buttons,options);


if (Platform.OS === 'ios') {                        ✅
  if (typeof type !== 'undefined') { 
    console.warn('Alert.alert() with a 5th "type" parameter is deprecated and will be removed. Use AlertIOS.prompt() instead.'); 
    AlertIOS.alert(title, message, buttons, type); 
    return; 
  } 
  AlertIOS.alert(title, message, buttons); 
} else if (Platform.OS === 'android') { 
  AlertAndroid.alert(title, message, buttons,options); 
}
```

/**todo : utiliser bien les espaces**/

### Utiliser le CamelCase et le PascalCase
Utilisez le camelCase lorsque vous nomez vos objets, fonctions et instances. Et utilisez la PascalCase lorsque vous nommez vos constructeurs ou vos classes.

```
const game_map = {};                            ❌
const alien-spacecraft = {};                    
function FireAMissile() {};                     
class player {                                  
  constructor(name) {
    this.name = name;
  }
}
const player--one = new player('Bob');          

const gameMap = {};                             ✅
const alienSpacecraft = {};                     
function fireAMissile() {};                     
class Player {                                  
  constructor(name) {
    this.name = name;
  }
}
const playerOne = new Player('Bob');            
```

### Utiliser la comparaison d'égalité stricte
Bien différencier le == (égalité faible) qui vérifie l’égalité **des valeurs** et le === (égalité stricte) qui vérifie l’égalité **des valeurs et des types**.
Il est donc préférable de toujours utiliser l'égalité stricte, cela vous obligera à être rigoureux et ça évitera les possibles effets de bord.

```
console.log(0 == 0);                                // true   ❌
console.log(new String("0") == new String("0"));    // true
console.log('0' == '0');                            // true
console.log(0 == new String("0"));                  // true
console.log(0 == '0');                              // true
console.log(new String("0") == '0');                // true

console.log(0 === 0);                               // true   ✅
console.log(new String("0") === new String("0"));   // true
console.log('0' === '0');                           // true
console.log(0 === new String("0"));                 // false
console.log(0 === '0');                             // false
console.log(new String("0") === '0');               // false
```

### N'omettez pas les accolades 
Même si il est possible de s’en passer dans certains cas il faut les utiliser. Les risques d’erreurs sont trop important pour passer à coté. Et qui sait ? Demain vous devrez peut-être rajouter une ligne dans votre condition et le terrain sera déjà prêt !

```
if (condition === true)                         ❌
  console.log('hello');

for (var i = 0; i < 9; i++)                     ❌
  console.log('hello', i);
  
if (condition === true) {                       ✅
  console.log('hello');
}

for (var i = 0; i < 9; i++) {                   ✅
  console.log('hello', i);
}
```

### N'omettez pas les points-virgules
Une caractéristique que de nombreux développeurs nouveaux et amateurs adorent sur JavaScript est le fait que, dans la plupart des cas, les points-virgules (;) sont facultatifs et que le code s'exécute sans eux. Cette fonctionnalité est connue sous le nom d'insertion automatique de point-virgule. Cependant, en utilisant cette fonction n'est pas recommandée et vous devrait inclure tous les points - virgules à cause que cela peut entraîner un comportement inattendu. Les points-virgules sont également essentiels pour une meilleure lisibilité.

### let / const / var


### () => {}

### foreach avec index

### filter

### if -> ? : condition ternaire
```
// ✓ ok
var location = env.development ? 'localhost' : 'www.api.com'
 
// ✓ ok
var location = env.development
  ? 'localhost'
  : 'www.api.com'
 
// ✗ avoid
var location = env.development ?
  'localhost' :
  'www.api.com'
```
  
### nommage des fichiers - 

### eviter les consoles.log

### Ne pas laisser du code commenter

```
if(v){
   var x = v;
} else {
   var x =10;
}

var x = v || 10;
```

```
var lunch = new Array();
lunch[0]='Dosa';
lunch[1]='Roti';
lunch[2]='Rice';
lunch[3]='what the heck is this?';

var lunch = [
   'Dosa',
   'Roti',
   'Rice',
   'what the heck is this?'
];
```

### Eviter les concatenations de chaine
```
const message = 'Hello' + name + '!';     // ✗ avoid
const message = `Hello ${name} !`;        // ✓ ok
```
