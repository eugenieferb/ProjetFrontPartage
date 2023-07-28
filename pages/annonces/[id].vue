<script lang="ts" setup>
import { Annonces } from 'entities';

const route = useRoute();

const { data } = useFetch<Annonces>('http://localhost:8000/api/annonces/id/' + route.params.id);

</script>

<template>
<div v-if="data">{{data.name}}
    </div>
    </template>


