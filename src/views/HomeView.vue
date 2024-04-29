<script setup>
import { onMounted, reactive, ref } from 'vue';
import CardPersonagem from '../components/CardPersonagem.vue'

let personagens = reactive(ref([]));

const getEpisodeCount = (episodes) => {
  return episodes.length;
};

onMounted(() => {

  fetch("https://rickandmortyapi.com/api/character")
    .then(response => response.json())
    .then(response => {
      personagens.value = response.results;
      console.log(response.results);
    })
})
</script>

<template>
  <main>
    <div class="container">
      <div class="card" style="width: 100%;">
        <div class="card-body row" style="background-color:  rgb(223, 222, 222);">
          <CardPersonagem v-for="personagem in personagens" 
          :id_img="personagem.id" 
          :name="personagem.name"
          :status="personagem.status" 
          :species="personagem.species" 
          :type="personagem.type"
          :location="personagem.location.name" 
          :episodeCount="personagem.episode.length" />
            />
        </div>
      </div>
    </div>
  </main>
</template>

<style>

</style>