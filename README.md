<h1 align="center">Formation sur les bonnes pratiques Javascript ✨</h1>

Bienvenue sur cette Formation Javascript dans lequel vous allez decouvrir (ou re-decouvrir) les bonnes pratiques du langage !

## Informations
- **Objectifs** :dart: : Améliorer la qualité d'un code écrit en Javascript
- **Public** :two_men_holding_hands: : Toutes les personnes qui codent ou qui seront amenés à coder en Javascript
- **Pré-requis** :heavy_check_mark: : Avoir les notions de base de Javascript
- **Méthode pédagogique** :game_die: : 50% théorique / 50% pratique + 1 exercice final
- **Description** :bookmark: : Aujourd'hui de plus en plus de développeurs sont formés et sont amenés à utiliser des frameworks comme Angular, React, Vue ou Node. Cependant, étant directement plongés dans les vagues sujets que peut amener un de ces frameworks, les notions même de javascript qui est à l'ogine de ces outils sont souvents oubliés ou vu trop rapidement !! Le principe de cette formation est donc de revoir ensemble quelques règles de base de ce langage.

## Formation

Pour chacun des points que nous allons aborder ensemble, il y aura une partie théorique et une partie pratique. Pour la partie pratique, il est nécessaire de cloner le projet sur votre ordinateur ``git clone git@github.com:landschootl/bonnes-pratiques-js.git``.

### Le nommage des variables et des méthodes
Il est important de bien nommer les variables et les noms des méthodes. Cela vous simplifiera la vie lorsque vous (ou un de vos collègues) devrez relire votre code suite à une évolution à effectuer ou un bug à corriger. Vous payez rarement aux nombres de caractères alors n'hésitez pas !

```
const list = ['Fred', 'Jacques'];                   ❌
const list2 = ['baleine', 'singe', 'loup'];         ❌

const add = function(name) => {                     ❌
  list2.push(name);
};

const nameList = ['Fred', 'Jacques'];               ✅
const petList = ['baleine', 'singe', 'loup'];       ✅

const addPet = function(name) => {                  ✅
  petList.push(name);
};
```
