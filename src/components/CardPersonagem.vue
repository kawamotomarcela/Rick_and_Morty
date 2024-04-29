<script setup>

const personagem = defineProps(["id_img", "name", "status", "species", "type", "location", "episodeCount" ]);

const image_url = "https://rickandmortyapi.com/api/character/avatar/" + personagem.id_img + ".jpeg"
console.log(personagem);

</script>

<template>

    <div class="col-md-3" >
        <div class="card mb-4 mt-2 d-flex"  >
            <img :src="image_url" class="card-img-top" alt="...">
            <div class="card-body" style="height: 200px">
                <h5 class="card-title">{{ personagem.name }}</h5>
                <div class="d-flex" >
                    <span>Status:  </span>
                    <p class="card-text">{{ personagem.status }}</p>
                </div>
                <div class="d-flex">
                    <span>Espécie: </span>
                    <p class="card-text">{{ personagem.species }}</p>
                </div>
                <div class="d-flex">
                    <span>Gênero: </span>
                    <p class="card-text">{{ personagem.type }}</p>
                </div>
                <div class="d-flex">
                    <span>Localização: </span>
                    <p class="card-text">{{ personagem.location }}</p>
                </div>
                <div class="d-flex">
                    <span>Episodios: </span>
                    <p class="card-text">{{ episodeCount }}</p>
                </div>
            </div>
        </div>
    </div>

</template>

<style>
span {
    margin-right: 5px;
}
</style>