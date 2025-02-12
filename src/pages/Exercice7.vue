<template>
  <v-container max-width="700">
    <!-- Données de l'exercice -->
    <exercice-objectifs number="7"/>
    <!-- Zone de travail pour l'exercice -->
    <div class="exe-zone">
      <h2>Zone d'exercice</h2>
      <v-card
        class="mx-auto my-6 pa-2"
        max-width="500"
      >
        <v-card-title>
          Coucou
        </v-card-title>
        <v-card-text>
          <p>Je suis là !</p>
        </v-card-text>
      </v-card>

    </div>
  </v-container>
</template>

<script setup>
// Importation des données de l'exercice
import ExerciceObjectifs from "@/components/ExerciceObjectifs.vue";



</script>

<style scoped lang="sass">

</style>
