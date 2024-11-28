Note : vraiment faire la version print ???? (classe CSS hide-when-printing)


# 1 - Slides

# 2 - Exemple

## 2.1 sauce-piquante.fr

=> les images de la page d'accueil

=> le "hamburger menu"

=> une sauce, le descriptif passe dessous


## 2.2 oFig


https://github.com/O-clock-FS-JS/oFig-cart/tree/responsive


- meta => il y est déjà

```html
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
```


un premier exemple de media query TODO

si l'écran fait moins de 500px de large, on veut que figurines et statuettes soit la ligne en-dessous

```css
@media screen and (max-width: 600px) {
    .header__title-container {
        /* nouvelle valeur ajoutée */
        flex-direction: column;
        /* remplacement d'une valeur : la valeur écrite le plus bas dans le fichier prend le dessus */
        align-items: flex-start;
    }

    .header__subtitle {
        margin-left: 0;
        margin-top: 15px;
        }
}
```


On va s'occuper de quelques autres éléments, cette fois en mobile-first.

mobile-first  de base on met ce qui est pour les plus petits écrans, et on "améliore" pour les écrans plus grand

```css
.cart-total {
  ......
  flex-direction: column;
}

.cart-actions {
    .......
    flex-direction: column;
  }

  .cart-delivery {
    .....
    flex-direction: column;
  }


@media screen and (min-width: 768px) {
  .cart-total, .cart-actions, .cart-delivery {
    flex-direction: row;
  }
}
```


=> montrer avec le dev tool responsive


