<script setup>

const personagem = defineProps(["id_img", "name", "status", "species", "type", "location"]);
const image_url = "https://rickandmortyapi.com/api/character/avatar/" + personagem.id_img + ".jpeg"
console.log(personagem);
</script>
<template>

    <div class="card m-3" style="width: 18rem;">
        <img :src="image_url" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ personagem.name }}</h5>
            <div class="d-flex">
                <span>Status: </span>
                <p class="card-text">{{ personagem.status }}</p>
            </div>
            <div class="d-flex">
                <span>Especie: </span>
                <p class="card-text">{{ personagem.species }}</p>
            </div>
            <div class="d-flex">
                <span>Genero: </span>
                <p class="card-text">{{ personagem.type }}</p>
            </div>
            <div class="d-flex">
                <span>Localização: </span>
                <p class="card-text">{{ personagem.location }}</p>
            </div>
        </div>
    </div>

</template>