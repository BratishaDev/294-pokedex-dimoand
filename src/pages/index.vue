<template>
  <!-- Conteneur principal pour structurer la disposition de la page -->
  <v-container>
    <!--
    Titre de la page
      * text-h3 applique le style titre de niveau 3
      * text-center permet de centrer le texte
      * my-6 ajoute une marge verticale de 6 unités
    -->
    <h1 class="text-h3 text-center my-6">
      Pokédex
    </h1>
    <!-- TODO: Afficher les Pokémon ici -->
  </v-container>
</template>

<script setup>
// Vos scripts ou imports ici
const pokemons = ref([]);

async function fetchPokemons() {
  try {
    // On envoie une requête GET à l’API locale
    const response = await fetch('http://localhost:3535/pokemons')
    // On convertit la réponse en objet JavaScript
    pokemons.value = await response.json()
    // On affiche le résultat dans la console
    console.log('Pokémns chargés : ', pokemons.value)
  } catch (error) {
    // En cas d’erreur, on affiche le message d’erreur
    console.error('Erreur lors de la récupération des Pokémon:', error)
  }
}

onMounted(() => {
  fetchPokemons()
})
</script>
