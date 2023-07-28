<script lang="ts" setup>
import { Annonces } from "../entities";
defineProps<{
  annonces:Annonces}>()
</script>

<template>
  <div>
    <h3>{{ annonces.name }}</h3>
    <p>{{ annonces.description }}</p>
    <p>status :{{ annonces.status }}</p>
    <p>{{ annonces.type }}</p>
    <p>Appartient à :{{  annonces.owner.name }}</p>
    <p>A proximité :{{  annonces.owner.address }}</p>
  </div>
</template>

<style scoped></style>
