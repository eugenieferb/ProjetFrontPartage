<script lang="ts" setup>
import { Annonces } from "../entities";
import  AnnoncesItem  from '../components/Annonces-item.vue';

const route = useRoute();

const annonces = ref<Annonces>({
  name:'',
  description:'',
  status: '',
  type: '',
  owner:{
    name: '',
    address:''
  }
});

async function postAnnonces(annonces:Annonces) {
  await $fetch('http://localhost:8000/api/annonces', {
    method: "POST",
    body: annonces,
  });
};

</script>

<template>
  <div>
    <form @submit.prevent="postAnnonces(annonces)">
    <p><label for="name">Name :</label>
    <input type="text" id="name" v-model="annonces.name"></p>
    <p><label for="description">Description :</label>
    <input type="text" id="description" v-model="annonces.description"></p>
    <p><label for="type">Type :</label>
    <input type="text" id="type" v-model="annonces.type"></p>
    <p><label for="status">Status :</label>
    <input type="text" id="type" v-model="annonces.status"></p>
    <button type="submit">Submit</button>
  </form>
  </div>
</template>

<style scoped></style>
