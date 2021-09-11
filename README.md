# JS Assignment 3: A Basic Pokedex using [PokeAPI](https://pokeapi.co/)

Deployed on Netlify: https://pokeapi-pokedex.netlify.com

A Pokedex app that displays a list of Pokemon on the homepage, and a details section when a Pokemon is clicked. This is all done on the same page by toggling the CSS display attribute on the main sections of the page.

The homepage displays the Kanto Pokedex by default. This can be changed in app.js by switching out the variable for the Pokedex region (not very user-friendly I know!!!).


## Known issues
- Pokemon list on the homepage isn't ordered properly, possibly because the `<div>` elements are being generated asynchronously inside a fetch() function. Tried to fix this with a sort function on `pokemonArray` before displaying the Pokemon, but couldn't get it to run consistently after the first fetch() call.
- Evolution chain (retrieved in a separate API call) won't display at all if it includes any Pokemon that wasn't fetched in the first API call (e.g. Jynx evolves from Smoochum, but Smoochum wasn't included in `pokemonArray` during the first API fetch (because it's not part of the Kanto Pokedex), so the code as it is won't work to display the evo chain.)
  - The evolution chain also doesn't display multiple evolutions (e.g. Eevee -> Jolteon/Vaporeon/Flareon/etc) properly. 
