<script lang="ts" setup>
import  AnnoncesItem  from '../components/Annonces-item.vue';
import { Annonces } from '../entities';

const { data, refresh} = await useFetch<Annonces[]>('http://localhost:8000/api/annonces')

async function addAnnonces(annonces:Annonces) {
  await $fetch('http://localhost:8000/api/annonces',{
    method: 'POST',
    body: annonces
  });
refresh();
}

</script>

<template>
  <AnnoncesItem v-for="item of data" :annonces="item" />
</template>