TODO regarder juste le README (car code fourni html/css)

# 1 structure de la page HTML puis CSS

(partir sur un c/c de la page d'accueil, pour le CSS ? )

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="../css/reset.css">
    <link rel="stylesheet" href="../css/style.css">
    <title>Contact</title>
</head>
<body id="contact-page">
    <div class="wrapper">
        <div id="welcome">
            <div id="logo">
                <a href="index.html">O'Clock Students News</a>
            </div>
            <div id="welcome-message">
                <h1>Say a word <span>contact us</span></h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque scelerisque suscipit nibh quis porttitor. Integer iaculis mi urna, a pulvinar quam adipiscing ut. Vivamus vel vestibulum mauris. </p>
            </div>
            <nav id="menu">
                <a href="#">Plan du site</a>
                <a href="#">Mentions légales</a>
                <a href="">Contact</a>
            </nav>
        </div>
        <div id="content">
            <header id="content-header">
                <h1>Contact</h1>
            </header>
            <section id="contact">
              
            </section>
        </div>
    </div>
</body>
</html>

```


# 2 ajouts éléments formulaire

- form
- fieldset + legend
- input (text) et label (d'abord le prénom ?)
- input radio
- select
- textarea
- input checkbox
- 

TODO : vraiment besoin de action sur le form ?

TODO prévoir des commentaires

```html
              <form id="form" action="">
                <fieldset>
                  <legend>Identité</legend>
                  <div class="form-row">
                    <p class="label">Je suis</p>
                    <div class="input-group">
                      <input type="radio" id="civilite-2" name="civilite" value="2" checked>
                      <label for="civilite-2">une femme</label>
                      <span>/</span>
                      <input type="radio" id="civilite-1" name="civilite" value="1">
                      <label  for="civilite-1">un homme</label>
                    </div>
                  </div>
                  <div class="form-row">
                    <label class="label" for="prenom">Mon prénom est </label>
                    <input type="text" id="prenom" placeholder="Prenom">
                  </div>
                  <div class="form-row">
                    <label class="label" for="nom">Et mon nom, </label>
                    <input type="text" id="nom" placeholder="Nom">
                  </div>
                  <div class="form-row">
                    <label class="label" for="source">J'ai connu ce site grâce à </label>
                    <select id="source" name="source">
                      <option value="">choisir</option>
                      <option value="fb">Facebook</option>
                      <option value="twitter">Twitter</option>
                      <option value="google">Google</option>
                      <option value="bouche-a-oreilles">Bouche à oreilles</option>
                      <option value="jpp">JT de 13h de TF1</option>
                      <option value="autre">Autre</option>
                    </select>
                  </div>
                </fieldset>
                <fieldset>
                  <legend>Message</legend>
                  <div class="form-row">
                    <label class="label" for="email">Répondez-moi via</label>
                    <input type="email" id="email" placeholder="Adresse e-mail">
                  </div>
                  <div class="form-row">
                    <label class="label" for="message">Je voulais vous dire que</label>
                    <textarea id="message" placeholder="Votre message"></textarea>
                  </div>
                  <div class="form-row">
                    <label class="label" for="file">Et vous montrer ça aussi</label>
                    <input type="file" id="file">
                  </div>
                </fieldset>
                <fieldset>
                  <div class="form-row">
                    <label class="label" for="info">Je certifie la véracité de ces informations.</label>
                    <input id="info" type="checkbox" name="info" value="1">
                  </div>
                </fieldset>
                <button id="submit-form" type="submit">Envoyer</button>
              </form>
```


```css
#form {
  width: 100%;
}

#form fieldset {
  border-left: 1px solid #4cced3;
  padding: .5em 1em 0;
  margin-bottom: 2em;
}
#form legend {
  margin-left: -.3em;
  font-size: 1.1em;
}

.form-row {
  display: flex;
  margin-bottom: .4em;
}

.form-row .label {
  flex-basis: 30%;
  margin: 0;
  padding-right: 3%;
}

.form-row > * {
  flex-basis: 70%;
}

.input-group {
  display: flex;
  align-items: center;
}

.input-group > * {
  margin: 0 .5em 0 0;
}

/* moche mais bon */
#info {
  flex-basis: 1em;
}

#contact input[type=text],
#contact input[type=email],
#contact textarea,
#contact select
{
   background-color: #f9f9f9;
  border: none;
  border-bottom: 1px solid #4cced3;
}
#contact input[type=email] {
  width: 100%;
}
#contact textarea {
  padding: .2em;
  width: 100%;
}
#contact button {
  background-color: #4cced3;
  color: white;
  font-weight: 700;
  border: none;
  border-radius: 5px;
  font-size: 1.3em;
  padding: 5px 10px;
}
```