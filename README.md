<h1 align="center">Clean Code Javascript ✨</h1>

Bienvenue sur cette Formation dans lequel vous allez decouvrir (ou re-decouvrir) des bonnes pratiques qui permettent d'améliorer la qualité d'un code Javascript !

## Informations
- **Objectifs** :dart: : Améliorer la qualité d'un code écrit en Javascript !
- **Public** :two_men_holding_hands: : Toutes les personnes qui codent ou qui seront amenés à coder en Javascript
- **Pré-requis** :heavy_check_mark: : Avoir les notions de base de Javascript
- **Méthode pédagogique** :game_die: : 50% théorique / 50% pratique + 1 exercice final
- **Description** :bookmark: : Aujourd'hui de plus en plus de développeurs sont formés et sont amenés à utiliser des frameworks comme Angular, React, Vue ou Node. Cependant, étant directement plongés dans les vagues sujets que peut amener un de ces frameworks, les notions même de javascript qui est à l'ogine de ces outils sont souvents oubliés ou vu trop rapidement !! Le principe de cette formation est donc de revoir ensemble quelques règles de base de ce langage.

## Formation
Pour chacun des points que nous allons aborder ensemble, il y aura une partie théorique et une partie pratique. Pour la partie pratique, il est nécessaire de cloner le projet sur votre ordinateur ``git clone git@github.com:landschootl/bonnes-pratiques-js.git``.

### Nommer correctement les variables et les méthodes
Il est important de bien nommer les variables et les noms des méthodes. Cela vous simplifiera la vie lorsque vous (ou un de vos collègues) devrez relire votre code suite à une évolution à effectuer ou un bug à corriger. Vous payez rarement aux nombres de caractères alors n'hésitez pas !

```
const list = ['Fred', 'Jacques'];                   ❌
const list2 = ['baleine', 'singe', 'loup'];         

function add(name) {                                
  list2.push(name);
}

const nameList = ['Fred', 'Jacques'];               ✅
const petList = ['baleine', 'singe', 'loup'];       

function addPet(name) {                             
  petList.push(name);
}
```

### Indenter correctement le code
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

### Ne pas oublier les accolades 
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

### Ne pas oublier les points-virgules
L’ASI contient certaines règles et exceptions parfois difficiles à retenir qui peuvent provoquer une mauvaise interprétation de notre code.
Il est plus simple de mettre les points-virgules tout le temps comme ça on n’a pas à se soucier des cas particuliers. Lorsqu’on utilise les points-virgules on ne risque aucune erreur. Si on ne les utilise pas on risque de tomber sur certaines erreurs.

```
const list2 = ['baleine', 'singe', 'loup']          ❌  

function add(name) {                                
  list2.push(name)
}

const petList = ['baleine', 'singe', 'loup'];       ✅

function addPet(name) {                             
  petList.push(name);
}
```

### Utiliser *let* à la place de *var*
**var** et **let** sont tous deux utilisés pour la déclaration de variables en javascript, mais la différence entre eux est que var a une portée de fonction et let est une portée de bloc.
On peut dire qu'une variable déclarée avec var est définie dans tout le programme par rapport à let.

```
for (var i = 0; i < 5; i++) {                         ❌
    console.log(i);
}
console.log(i); // 5

for (let i = 0; i < 5; i++) {                         ✅
    console.log(i);
}
console.log(i); // ReferenceError: i is not defined
```
:information_source:	Si vous avez des variables qui ne changeront jamais dans votre programme, il est préférable d'utilisez le mot clé **const**, comme pour définir la TVA ou la valeur de pi par exemple. A la différence de **let**, une fois la variable **const** définie, elle ne pourra plus être réaffecter, ce qui vous assure qu'elle ne changera jamais lors de l'execution du programme.

```
const TVA = 0.18;
console.log(TVA); // 0.18

TVA = 0.180; // TypeError: Assignement to constant variable
```

### Utiliser les conditions ternaire
Evitez les **if-else** quand ce n'est pas nécessaire. Utiliser des conditions ternaire rend le code plus lisible dans certains cas !
exemple :  

```
let location;                                                   ❌
if (env.development) {  
  location = 'localhost';
} else {
  location = 'www.api.com';
}

let location = env.development ? 'localhost' : 'www.api.com';   ✅
```

:warning: Attention, veuillez à respecter la bonne syntaxe :
```
let location = env.development ? 'localhost' : 'www.api.com';   👍

let location = env.development                                  👍
  ? 'localhost'
  : 'www.api.com';
  
let location = env.development ?                                👎
  'localhost' :
  'www.api.com';
```

### Utiliser les opérateurs logiques
Evitez les **if-else** quand ce n'est pas nécessaire. Utiliser des opérateurs logiques rend le code plus lisible dans certains cas !
exemple :  

```
let x;                        ❌
if (v) {                      
   x = v;
} else {
   x = 10;
}

let x = v || 10;              ✅
```

### Supprimer les consoles.log
Souvent utilisés pour le débogage en phase de développement et de test, ils ne sont pas supprimés par la suite. Pensez donc à supprimer les *"console.log"* une fois le développement terminé.

```
if (animal === undefined) {                         ❌
    console.log('je passe ici');
    // code
}

if (animal === undefined) {                         ✅
    // code
}

```

### Eviter les concatenations de chaine
Evitez les concatenations de chaine avec des opérateurs logiques car cela est lourd. Utilisez plutôt ` `` ` quand cela est possible.

```
const message = 'Hello' + name + '!';                 ❌

const message = `Hello ${name} !`;                    ✅
```

### Utiliser les fonctions fléchées
Une expression de fonction fléchée permet d’avoir une syntaxe plus courte que les expressions de fonction.

```
let total = values.reduce(function (a, b) {             ❌
  return a + b;
}, 0);

let total = values.reduce((a, b) => a + b, 0);          ✅
```

:warning: Les fonctions fléchées ne sont pas totalement identiques aux fonctions classiques.   
Elles ne gèrent pas les valeurs this, arguments et super (voir programmation Objet). Ces valeurs correspondent à celles de l'objet englobant (scope parent).   
Exemple :

```
let f1 = function(){ return this};
let f2 = () => this;

console.log(f1());    // affiche l'objet
console.log(f2());    // affiche window
```
   
Les fontions fléchées permettent donc d'éviter dans certaines conditions les créations de variables `let thas = this` inutiles.

### foreach avec index

### filter


  
### nommage des fichiers - 



### Ne pas laisser du code commenter



```
const lunch = new Array();
lunch[0]='Dosa';
lunch[1]='Roti';
lunch[2]='Rice';
lunch[3]='what the heck is this?';

const lunch = [
   'Dosa',
   'Roti',
   'Rice',
   'what the heck is this?'
];
```

