Čím budou naše webové aplikace pokročilejší a schopnější, tím více budou obsahovat komponent, ale také různých knihoven. Brzy již přestane být únosné mít všechen kód v jednom obřím `index.js`, protože by se v něm za chvíli už nikdo nikdy nevyznal. Od samého začátku se tedy budeme snažit rozdělovat naše komponenty do jednotlivých souborů.

## Oddělování komponent

Ve výsledku se chceme ke každé komponentě chovat jako k jakémusi samostatnému uzlíku či balíčku. Každá komponenta má nějaký JavaScriptový kód, styly a také třeba soubory s obrázky. Toto všechno chceme mít pohromadě, aby bylo jasné, co všechno patří k jaké komponentě.

Pro každou komponentu si tedy vytvoříme spociální složku a domluvíme se na společné struktuře, kterou budeme dodržovat. Každá složka bude obsahovat

- soubor `index.js` s JavaScriptovým kódem komponenty,
- soubor `style.css` s CSS styly pro komponentu,
- případně složku `img` s obrázky.

Kromě složek s komponentami budeme v každém projektu také mít hlavní soubor `index.html`, hlavní `index.js` a hlavní `style.css`, jak jsme byli doposud zvyklí.

Uvažme například náš projekt dříve v této lekci používající komponenty `ListItem` a `ShopList`,

::fig{src=assets/struktura-projektu.png size=40}

V souboru `ListItem/index.js` bude JavaScriptový kód komponenty:

```js
const ListItem = (props) => {
  const { done, product, amount } = props;

  let tickClass = '';
  if (done) {
    tickClass = ' item__done--tick';
  }

  return `
    <li class="item">
      <div class="item__product">${product}</div>
      <div class="item__amount">${amount}</div>
      <div class="item__done${tickClass}"></div>
    </li>
  `;
};
```

Podobně bude vypadat soubor `ShopList/index.js`:

```js
const ShopList = (props) => {
  const { day, items } = props;
  return `
    <div class="shoplist">
      <h2>${day}</h2>  
      <div class="shopping-list__items">
        ${items.map((item) => ListItem(item)).join('')}
      </div>
    </div>
  `;
};
```

Komponenty lehce nastylujeme v souboru `ListItem/style.css`:

```css
.item {
  display: flex;
  align-items: center;
  list-style: none;
  background-color: #e4e4e4;
  padding: 1rem 1.5rem;
  margin-bottom: 0.5rem;
}

.item__product {
  flex: 1;
}

.item__amount {
  margin: 0 1rem;
}

.item__done {
  width: 1.5rem;
  height: 1.5rem;
  background-size: contain;
  background-repeat: no-repeat;
}

.item__done--tick {
  background-image: url(./img/tick.svg);
}
```

a `ShopList/style.css`:

```css
ul.shoplist {
  padding: 0;
}
```

Do složky `ListItem` také přidáme složku `img` s obrázekm [tick.svg](assets/tick.svg).

Hlavní soubor `index.html` bude vypadat takto:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <link rel="stylesheet" href="style.css" />
    <link rel="stylesheet" href="ListItem/style.css" />
    <link rel="stylesheet" href="ShopList/style.css" />

    <script type="module" src="index.js"></script>

    <title>První komponenta</title>
  </head>

  <body>
    <div class="container">
      <h1>Nákupní seznam</h1>
    </div>
    <div id="lists" class="container"></div>
  </body>
</html>
```

Všimněte si hlavičky, kam musíme vložit všechny soubory stylů. Co se JavaScriptu týče, stačí nám do stránky vložit pouze hlavní `index.js` s tímto obsahem:

```js
const listsElement = document.querySelector('#lists');

fetch('https://apps.kodim.cz/daweb/trening-api/apis/shopping/mon')
  .then((response) => response.json())
  .then((data) => {
    listsElement.innerHTML += ShopList({ day: 'Pondělí', items: data });
  });

fetch('https://apps.kodim.cz/daweb/trening-api/apis/shopping/tue')
  .then((response) => response.json())
  .then((data) => {
    listsElement.innerHTML += ShopList({ day: 'Úterý', items: data });
  });
```

Ještě nám zbývá hlavní soubor `style.css` s tímto obsahem:

```
html {
  font-family: sans-serif;
}

.container {
  max-width: 30rem;
  margin: 3rem auto;
}
```

Nyní máme veškerý kód projektu hezky rozdělený na logické části. Všimněte si však, že jsme do hlavičky HTML vložili pouze hlavní `index.js`, ale nevložili jsme tam JavaScript naší komponenty. Ten se do naší stránky dostane jiným způsbem, který uvidíme v následující sekci.
