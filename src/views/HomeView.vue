<script setup>
import { onMounted, reactive, ref } from 'vue';
import CardPersonagem from '../components/CardPersonagem.vue'

let personagens = reactive(ref());

onMounted(() => {

  fetch("https://rickandmortyapi.com/api/character")
    .then(response => response.json())
    .then(response => {
      personagens.value = response.results;
    })
})
</script>

<template>
  <CardPersonagem v-for="personagem in personagens" 
    :id_img="personagem.id"
    :name="personagem.name"
    :status="personagem.status"
    :species="personagem.species"
    :type="personagem.type"
    :location="personagem.location.name"
  />
</template>
