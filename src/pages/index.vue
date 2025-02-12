<template>
  <v-container max-width="700">
    <!-- Donnée de l'exercice -->
    <exercice1-donnee />
    <!-- Zone de travail pour l'exercice -->
    <div class="exe-zone">
      <h2>Zone d'exercice</h2>

      <!-- Carte statique à transformer -->
      <v-card class="mx-auto my-6 pa-2" max-width="400">
        <!-- Remplacez *** TITRE *** par un contenu dynamique -->
        <v-card-title> {{ title }}</v-card-title>

        <!-- Remplacez *** DESCRIPTION *** par un contenu dynamique avec une liaison de style -->
        <v-card-subtitle :style="{ color:  textColor }">
          {{ description }}
        </v-card-subtitle>

        <!-- Rendez ce bouton fonctionnel pour changer la couleur -->
        <v-card-actions>
          <v-btn color="primary" @click="changeColor">
            <p v-if="isHighlighted">Réinitialiser la couleur</p>
            <p v-else>Mettre en surbrillance</p>
          </v-btn>
        </v-card-actions>
      </v-card>
    </div>
  </v-container>
</template>

<script setup>
// Importation du composant contenant la donnée de l'exercice
import Exercice1Donnee from "@/components/donnees/Exercice1Donnee.vue";
import { ref } from 'vue'
import { sassFalse } from "sass";
// Données préparées pour l'exercice
// SUGGESTION : Pensez à rendre ces données réactives pour qu'elles puissent être mises à jour dynamiquement.

const title = "Bienvenue à l'exercice 1";
const description = "Cet exercice teste le rendu déclaratif et les liaisons d'attributs.";
const isHighlighted = ref(false);
const textColor = ref('black');


// Change la valeur de isHiglithed apèrs le click
const changeColor = () => {
  isHighlighted.value = !isHighlighted.value
  textColor.value = isHighlighted.value ? 'blue' : 'black';
  console.log(isHighlighted.value)
  console.log(textColor.value)
}
</script>

<style scoped lang="sass">

</style>
