---
title: Responzivní layout 03
demand: 3
context: nadoma
solutionAccess: protected
---

Naklonujte si repozitář na základě šablony [cviceni-layout-03](https://github.com/Czechitas-podklady-WEB/cviceni-layout-03).
V repositor máte soubor `index.html`, `style.css` a obrázek se zadáním úkolu.

Nakódujte stránku podle obrázku `zadani-ukolu.jpg`.

::fig[responsive layout result]{src=assets/zadani-ukolu.jpg}

<br/>

Rozložení stránky se mění v breakpointech: 640px a 1000px.
Prohlédněte si pečlivě HTML strukturu, všímejte si jak jsou prvky do sebe zanořené.

Výsledek bude vypadat takto.  
::fig[responsive layout result]{src=assets/layout-03-result.gif}

Pro mezery mezi reklamami je možné použít vlastnost [gap](https://coryrylan.com/blog/css-gap-space-with-flexbox). Ale jde to i bez ní 😀

:::solution

```css
.reklamy {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

@media (min-width: 640px) {
  .obsah {
    display: flex;
  }
  .clanek {
    width: 60%;
  }
  .reklamy {
    width: 40%;
  }
}

@media (min-width: 1000px) {
  .kontejner {
    display: flex;
  }

  .obsah {
    flex-direction: column;
    width: 75%;
  }

  .reklamy {
    flex-direction: row;
    width: 100%;
  }

  .menu {
    width: 25%;
  }

  .reklama1,
  .reklama2 {
    width: 50%;
  }
}
```

:::
