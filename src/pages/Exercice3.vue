<template>
  <v-container max-width="700">
    <!-- Donnée de l'exercice -->
    <exercice3-donnee />
    <!-- Zone de travail pour l'exercice -->
    <div class="exe-zone">
      <h2>Zone d'exercice</h2>
      <v-card
        class="mx-auto my-6 pa-2"
        max-width="300"
      >
        <v-card-title>Liste de Pokémons</v-card-title>
        <v-card-subtitle v-show="pokemons.length === 0" class="text-center">
          La liste est vide.
        </v-card-subtitle>

        <v-list>
          <v-list-item>
            <v-list-item-title v-for="(pokemon, index) in pokemons"
                               :key="index">
              {{ index + 1 }}. {{ pokemon }}               <v-btn
              @click="removePokemon(index)"
              icon="mdi-delete"
              variant="text"
            ></v-btn>
            </v-list-item-title>

            <template v-slot:append>

            </template>
          </v-list-item>
        </v-list>
      </v-card>
    </div>
  </v-container>
</template>

<script setup>
// Importation du composant contenant la donnée de l'exercice
import Exercice3Donnee from "@/components/donnees/Exercice3Donnee.vue";
// Importation de la fonction réactive ref
import {ref} from 'vue';

// Tableau réactif de noms de Pokémons
const pokemons = ref([
  "Pikachu",
  "Bulbizarre",
  "Salamèche",
  "Carapuce",
  "Rondoudou"
]);

/**
 * Fonction qui supprime le Pokémon à l'index donné.
 * @param {number} index - Index, position, du Pokémon à supprimer.
 */
function removePokemon(index) {
  pokemons.value.splice(index, 1);
}
</script>

<style scoped lang="sass">
ul
  list-style: none
</style>
