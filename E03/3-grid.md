( https://github.com/O-clock-FS-JS/oFig-home/tree/grid )




L'idée ici est de leur montrer les bases de Grid, il n'est donc pas nécessaire de rentrer dans les moindres détails (d'autant que Flex et le positionnement leur a déjà bien pris la tête)

L'intérêt principal d'utiliser Grid dans ce contexte est de pouvoir faire varier l'affichage des cartes pour présenter le contenu de manière moins monotone ou prévisible.

https://developer.mozilla.org/en-US/docs/Web/CSS/display#display_grid

aussi https://css-tricks.com/snippets/css/complete-guide-grid/ , très exhaustif !


https://grid.layoutit.com/ pour s'entrainer

Ou alors un jeu : [Grid garden](https://cssgridgarden.com/#fr) 

```css
/* .product-list à remplacer */
.product-list {
  /* permet de passer le conteneur en mode grid */
  display: grid;

  /* on utilise une grille de 12 colonnes pour 
  se laisser de la liberté de mise en page */
  grid-template-columns: repeat(12, 1fr);

  /* contrôle l'espacement entre les items */
  grid-gap: 10px;
}

.product-list__item {
  /* on déclare que chaque item doit prendre 4 colonnes
  pour se caler sur une base de 3 items par ligne, par défaut */
  grid-column: span 4;

  /* on peut continuer d'utiliser flex à l'intérieur
  grid et flex cohabitent très bien ensemble */
  .........
  /!\ enlever width: 30%
}

/* on cible les items au cas par cas pour la démo */
.product-list__item:nth-child(1) {
  /* l'item occupera l'espace de la colonne 1 jusqu'à la colonne 8 */
  grid-column: 1 / span 8;

  /* l'item occupera 2 lignes au lieu d'une seule, 
  cela permet aux éléments suivants de se positionner au même niveau */
  grid-row: span 2;
}

.product-list__item:nth-child(5),
.product-list__item:nth-child(8) {
  /* on demande à ces items de démarrer à la colonne 5 
  et d'occuper 4 colonnes */
  grid-column: 5 / span 4;
}

.product-list__item:nth-child(6) {
  /* on demande à cet item de démarrer à la colonne 9
  et d'occuper 4 colonnes */
  grid-column: 9 / span 4;

  /* On lui fait occuper 2 lignes pour que les 4 autres cartes
  se positionnent correctement à gauche */
  grid-row: span 2;
}

.product-list__item:nth-child(9) {
  /* cet item va occuper tout l'espace disponible */
  grid-column: 1 / span 12;
}





.product-list__item-img {
    ....

  /* pour que les images occupent plus d'espace dans
  les cartes les plus grandes */
  height: 100%;
  object-fit: contain;
}

```

------ NON -------

```css
/* Responsive de la partie Grid */
@media screen and (max-width: 768px) {
  .product-list {
    padding: 0 1em;
  }
  .product-list__item-img {
    height: auto;
    object-fit: unset;
  }
  .product-list__item,
  .product-list__item:nth-child(1),
  .product-list__item:nth-child(5),
  .product-list__item:nth-child(6),
  .product-list__item:nth-child(8) {
    /* ici "-1" représente la dernière colonne */
    grid-column: 1 / -1;
  }
}

```