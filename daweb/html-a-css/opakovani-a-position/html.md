Vítejte na Digitální akademii! Na začátek si zopakujeme informace o HTML a CSS, které bychom měli znát z prerekvizit. Pokud nebyl čas si kurz HTML a CSS projít, [tady je na něj odkaz](https://www.czechitas.cz/blog/online-kurz-uvod-do-html-css-1-lekce). Správné základy nám umožní postupovat akademií bez panikaření a osvojovat si znalosti v přiměřeném tempu.

## HTML

**HTML** (HyperText Markup Language), je značkovací jazyk, který nám umožňuje tvořit webové stránky. Můžeme vytvořit strukturu stránky, která obsahuje nadpisy, seznamy, odstavce, odkazy, a to pomocí **značek (tags), prvků (elements) a atributů (attributes).**

### Struktura HTML souboru

HTML soubory jsou ty, které končí koncovkou **.html**. Základní struktura HTML souboru je značka `html`, která obaluje prvky `head` a `body`.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>A simple HTML document</title>
  </head>
  <body>
    <p>Hello World!</p>
    <p></p>
  </body>
</html>
```

V prvku `head` se nachází

- informace o dokumentu, jako je například název,
- metaznačky (metatags), které mimo jiné pomáhají vyhledávačům,
- nebo linky na CSS a JS soubory.

Do obsahu prvku `body` potom píšeme samotný obsah naší webové stránky.

### HTML element

::fig[HTML tag]{src=assets/htmltag.jpg}

Většina elementů má otevírací a zavírací značku, jako například `body`. Existují ale také tzv. self-closing tags, které mají pouze atributy a nemají obsah. To jsou například značky `img` nebo `hr`.
Obsahem prvku může být i jiný prvek. V tom případě se obalový prvek stává jeho rodičem a prvek uvnitř dítětem.

Pojďme si společne projít základní HTML značky.

### Nadpisy

- `h1` - `h6`

### Text

- `p`

### Seznamy

- `ul`
- `ol`
- `li`

### Odkazy

- `a`

### Obrázky

- `img`

### Členění obsahu

- `div`
- `span`

### Sémantické HTML

- `main`
- `header`
- `footer`
- `section`
- `article`
- `nav`
