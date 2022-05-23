---
title: Rodná čísla
demand: 2
---

Založte si projekt v čistém JavaScriptu bez Webpacku, stačí soubory `index.html` a `index.js`. Napište program, který zjistí, jestli je zadané rodné číslo platné.

1. Pomocí funkce `prompt` se zeptejte uživatele na rodné číslo. Rodné číslo zkontrolujte podle bodů popsaných níže.
1. Každé rodné číslo musí mít přesně 10 znaků. Zkontrolujte tedy, že zadaný řetězec je délky 10 a neprojdou nám například vstupy typu

   ```text
   nepovím
   ```

   Slovo „nepovím“ má totiž jen 7 znaků.

   ```text
   123456789123456789
   ```

   Řetězec „123456789123456789“ má totiž 18 znaků.

   Pokud uživatel zadal číslo špatné délky, **vypište do konzole text**:

   ```text
   ❌ Uživatel zadal rodné číslo neplatné délky.
   ```

   V opačném případě vypiště:

   ```text
   ✔️ Zadané rodné číslo má správně deset znaků.
   ```

1. Každé rodné číslo musí být celé číslo. Zde je nějaká hodnota celé číslo v JavaScriptu zkontrolujete pomocí funkce `Number.isInteger`. Musíte však vstup předtím převést na číslo pomocí funkce `Number`.

   ```text
   > Number.isInteger(Number('25'))
   true
   > Number.isInteger(Number('25.16'))
   false
   > Number.isInteger(Number('ahoj'))
   false
   ```

   Opět **vypište do konzole**, zda podmínka platí.

   ```text
   ❌ Rodné číslo obsahuje nepovolené znaky.
   ```

   ```text
   ✔️ Rodné číslo je celé číslo.
   ```

1. Každé rodné číslo musí být dělitelné 11. Zkontrolujte tedy, že zadané číslo je dělitelné jedenácti a výsledek opět **vypište do konzole**.

   ```text
   ❌ Rodné číslo není dělitelné číslem 11.
   ```

   ```text
   ✔️ Rodné číslo je dělitelné 11.
   ```

1. Pokud jsou všechny podmínky splněny, rodné číslo budeme považovat za platné. Informaci o platnosti **vypište do konzole**.

   ```text
   ❌ Uživatel zadal neplatné rodné číslo.
   ```

   ```text
   ✔️ Zadané rodné číslo je platné.
   ```

   Po zadání rodného čísla by se v konzoli měly objevit čtyři výpisy.

---solution

### `index.js`

```js
const rodneCislo = prompt('Jaké je tvé rodné číslo?');
let platne = true;

if (rodneCislo.length === 10) {
  console.log('✔️ Zadané rodné číslo má správně deset znaků.');
} else {
  console.log('❌ Uživatel zadal rodné číslo neplatné délky.');
  platne = false;
}

if (Number.isInteger(Number(rodneCislo))) {
  console.log('✔️ Rodné číslo je celé číslo.');
} else {
  console.log('❌ Rodné číslo obsahuje nepovolené znaky.');
  platne = false;
}

if (Number(rodneCislo) % 11 === 0) {
  console.log('✔️ Rodné číslo je dělitelné 11.');
} else {
  console.log('❌ Rodné číslo není dělitelné číslem 11.');
  platne = false;
}

if (platne) {
  console.log('✔️ Zadané rodné číslo je platné.');
} else {
  console.log('❌ Uživatel zadal neplatné rodné číslo.');
}
```
