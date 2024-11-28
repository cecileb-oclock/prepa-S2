On recopie html css et dossier images depuis oFig saison 1.

Regarder vite fait les tableaux avec les liens de l'énoncé ?


# 1 - Structure

créer fichier html/cart.html (Emmet html)

title => `oFig - Panier`

Et remettre le CSS + la Google Font

On remet dans la structure le header et le footer


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <link rel="stylesheet" href="./../css/reset.css" />
<link rel="stylesheet" href="./../css/styles.css" />  

    <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">

    <title>Panier</title>
</head>
<body>
        <header class="header">
        <div class="header__title-container">
          <h1 class="header__title">oFig</h1>
          <h2 class="header__subtitle">Figurines et statuettes</h2>
        </div>
        <div class="header__theme-container">
          <h2 class="header__theme-title">
            Figurines sur le thème <span class="header__theme-title-franchise">Final Fantasy</span>
          </h2>
        </div>
      </header>

    <footer class="footer">
        oFig - toutes les images sont sous copyright SquareEnix
      </footer>
</body>
</html>
```

Puis un main, avec un formulaire, 4 sections : produits, livraison, montant, boutons

```html
<main class="container">
    <form class="form">
      <section class="cart-section">
        <h2 class="cart-section__title">Votre panier</h2>
        </section>
      <section class="cart-section">
        <h2 class="cart-section__title">Préférences de livraison</h2>
    </section>
      <section class="cart-section">
        </section>
      <section class="cart-section">
        </section>
</main>
        
```


```css
.cart-section {
  border-bottom: 1px solid #ccc;
  padding-bottom: 15px;
  margin: 10px 0;
}

.cart-section__title {
  font-weight: bold;
  font-size: 1.5rem;
  margin-bottom: 20px;
}

```

# 2 - Produits dans le panier

un tableau, avec des titres de colonne, et "une ligne spéciale avec toutes les cellules fusionnées" => ou un footer tfoot

https://developer.mozilla.org/fr/docs/Web/HTML/Element/tfoot

Déjà, thead, tbody avec un élément, tfoot :

```html
<table class="cart-products">
    <thead class="cart-products__head">
    <tr class="cart-products__head-line">
        <th class="cart-products__head-item">Figurine</th>
        <th class="cart-products__head-item">Prix unitaire</th>
        <th class="cart-products__head-item">Quantité</th>
    </tr>
    </thead>
    <tbody class="cart-products__body">
    <tr class="cart-products__body-line">
        <td class="cart-products__body-item">Cloud Strife</td>
        <td class="cart-products__body-item">59 €</td>
        <td class="cart-products__body-item">
        <input type="text" class="cart-products__qty" value="1" />
        <a href="#" class="cart-products__remove-product" >supprimer</a>
        </td>
    </tr>
    </tbody>
    <tfoot class="cart-products__foot">
    <tr class="cart-products__foot-line">
        <td class="cart-products__foot-item" colspan="2">Total de la commande :</td>
        <td class="cart-products__foot-item cart-products__foot-item--price">197 €</td>
    </tr>
    </tfoot>
</table>
```


```css
.cart-products {
  text-align: center;
  width: 94%;
  margin: 0 auto;
  box-shadow: 1px 2px 4px rgb(0 0 0 / 10%)
}

.cart-products__head-line {
  border-bottom: 1px solid #ccc;
}

.cart-products__head-item {
  font-weight: bold;
  font-size: 1.4rem;
  padding: 6px;
}

.cart-products__body-item {
  padding: 6px;
}

.cart-products__qty {
  width: 30px;
}

.cart-products__remove-product {
  color: #c80000;
  text-decoration: underline;
  font-size: 0.9rem;
  margin-left: 2px;
}

.cart-products__foot-item {
  padding: 10px;
  font-weight: bold;
  font-size: 1.2rem;
}

.cart-products__foot-item--price {
  color: #c80000;
  font-size: 1.8rem;
}
```

Les autres lignes :


```html

            <tr class="cart-products__body-line">
              <td class="cart-products__body-item">Tifa Lockhart</td>
              <td class="cart-products__body-item">69 €</td>
              <td class="cart-products__body-item">
                <input type="text" class="cart-products__qty" value="1" />
                <a href="#" class="cart-products__remove-product" >supprimer</a>
              </td>
            </tr>
            <tr class="cart-products__body-line">
              <td class="cart-products__body-item">Barret Wallace</td>
              <td class="cart-products__body-item">69 €</td>
              <td class="cart-products__body-item">
                <input type="text" class="cart-products__qty" value="1" />
                <a href="#" class="cart-products__remove-product" >supprimer</a>
              </td>
            </tr>
```


# 3 - Préférences de livraison

2 colonnes, mais pas un tableau => display flex

un conteneur global, avec deux éléments dedans

```html
 <div class="cart-delivery">
    <div class="cart-delivery__part">
        <h3 class="cart-delivery__part-title">Où souhaitez-vous être livré ?</h3>
    </div>
    <div class="cart-delivery__part">
        <h3 class="cart-delivery__part-title">Options</h3>
    </div>
    <div class="cart-delivery__part">
        <h3 class="cart-delivery__part-title">Adresse</h3>
    </div>
    <div class="cart-delivery__part">
        <h3 class="cart-delivery__part-title">Informations complémentaires</h3>
    </div>
</div>
```

```css
.cart-delivery {
  display: flex;
  justify-content: space-between;
  margin: 0 3%;
}

.cart-delivery__part-title {
  color: #666;
  font-weight: bold;
  font-size: 1.2rem;
  margin: 20px 0;
}
```

=> ce n'est pas ça qu'on veut, il faut qu'on regroupe des éléments => ajout de div

```html
<div class="cart-delivery">
    <!-- première colonne -->
    <div>
        <div class="cart-delivery__part">
            <h3 class="cart-delivery__part-title">Où souhaitez-vous être livré ?</h3>
        </div>
        <div class="cart-delivery__part">
            <h3 class="cart-delivery__part-title">Options</h3>
        </div>
    </div>
    <!--  deuxième colonne -->
    <div>
        <div class="cart-delivery__part">
            <h3 class="cart-delivery__part-title">Adresse</h3>
        </div>
        <div class="cart-delivery__part">
              <h3 class="cart-delivery__part-title">Informations complémentaires</h3>
        </div>
    </div>
</div>
```

On remplit chaque partie

## Partie 1

Pour que chaque élément soit sur une ligne :
- une div container et display flex
- une div autour de chaque élément (car display block)

=> on choisit div autour de chaque élément

```html
<div>
    <input type="radio" value="current" name="adressSelection" id="currentAddress" class="form__radio">
    <label for="currentAddress" class="form__radio-label">Mon adresse courante</label>
</div>
<div>
    <input type="radio" value="other" name="adressSelection" id="otherAddress" class="form__radio" checked> 
    <label for="otherAddress" class="form__radio-label">Autre adresse</label>
</div>
```

```css
.form__radio-label {
  line-height: 1.5;
  font-size: 0.8rem;
}
```

## Partie 2

```html
<div>
                <input type="checkbox" id="followBySms" name="sms" checked>
                <label for="followBySms" class="form__checkbox-label">Suivi de livraison par sms (inclus)</label>
              </div>
              <div>
                <input type="checkbox" id="moneyBack" name="moneyBack" >
                <label for="moneyBack" class="form__checkbox-label">Satisfait ou remboursé (+ 2 euros)</label>
              </div>
              <div>
                <input type="checkbox" id="care" name="care" >
                <label for="care" class="form__checkbox-label">Garantie 2 ans (+ 10 euros)</label>
              </div>
            </div>
```

```css
.form__radio-label, .form__checkbox-label {
 ```

## Partie 3

```html
<div>
                <label for="address" class="form__label-input">Rue</label>
                <input type="text" class="form__input" id="address" name="address">
              </div>
              <div>
                <label for="zipCode" class="form__label-input">Code postal</label>
                <input type="text" class="form__input" id="zipCode" name="zipCode">
              </div>
              <div>
                <label for="city" class="form__label-input">Ville</label>
                <input type="text" class="form__input" id="city" name="city">
              </div>
            </div>
```

```css
.form__label-input {
  display: block;
  margin-top: 3px;
  padding-bottom: 3px;
  font-size: 0.8rem;
}

.form__input {
  border: none;
  border-bottom: 1px solid #ccc;
  background-color: #fafafa;
  width: 100%;
  line-height: 2;
}
```

## Partie 4

```html
    <textarea name="complement" id="complement" class="form__textarea"></textarea>
```


```css
.form__input, .form__textarea {
```


# 4 - 2 dernières sections

```html
<div class="cart-total">
    <span class="cart-total__label">Montant total à régler :</span>
    <span class="cart-total__price">197 €</span>
</div>
```

```css
.cart-total {
  margin: 20px 3% 10px 3%;
  padding: 30px;
  box-shadow: 1px 2px 4px rgb(0 0 0 / 10%);
  border-radius: 5px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.cart-total__label {
  font-weight: bold;
  font-size: 1.1rem;
}

.cart-total__price {
  font-weight: bold;
  color: #c80000;
  font-size: 1.8rem;
}

```


```html
<div class="cart-actions">
    <button class="button">Continuer vos achats</button>
    <button class="button button--red" type="submit">Valider et payer</button>
</div>
```

```css
.cart-actions {
  margin: 20px 3% 10px 3%;
  display: flex;
  justify-content: space-between;
}

.button {
  border: none;
  padding: 15px 30px;
  font-weight: bold;
  letter-spacing: 0.05rem;
  font-size: 1rem;
  cursor: pointer;
  transition: 0.5s;
}

.button:hover {
  background-color: #666;
  color: white;
}

.button--red {
  background-color: #c80000;
  color: #fff;
}

.button--red:hover {
  background-color: #8e0000;
}
```




# 5 - Bonus une ligne sur 2

```css
/* https://developer.mozilla.org/fr/docs/Web/CSS/:nth-child */
.cart-products__body-line:nth-child(odd) {
  background-color: #eee;
}
```

On peut aussi utiliser un calcul automatique pour les éléments à sélectionner


Ajouter des éléments dans le panier en c/c du dernier tr


```css

/* tous les "multiples de 3 + 1" => 1, 4, 7... */
.cart-products__body-line:nth-child(3n + 1) {
  background-color: lightblue;
}

/* tous les "multiples de 3 + 2" => 2, 5, 8... */
.cart-products__body-line:nth-child(3n + 2) {
  background-color: lightpink;
}
```

commiter ce bonus en le commentant (pour être prêt pour la suite)



