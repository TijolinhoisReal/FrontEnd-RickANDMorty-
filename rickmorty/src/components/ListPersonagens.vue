<script setup> 
    const personagem = defineProps(["name", "url", "image", "status","species", "gender", "location", "episode"])
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3 p-2">
            <!-- <p class="text-center">{{ personagem.name }}</p>  -->
            <img :src="personagem.image" class="card-img-top" height="60%" alt="..."> 
            <div class="card-body">
                <p class="card-title text-center">Nome: {{ personagem.name }}</p>
                <p class="card-title text-center">Status: {{ personagem.status }}</p>
                <p class="card-title text-center">Espécies: {{ personagem.species }}</p>
                <p class="card-title text-center">Gênero: {{ personagem.gender }}</p>
                <p class="card-title text-center">Localização: {{ personagem.location.name }}</p>
                <p class="card-title text-center">Episódios: {{ personagem.episode.length }}</p>
            </div>
        </div>
    </div>
</template>

<style>

</style>