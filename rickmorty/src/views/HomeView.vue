<script setup>
// props - onMounted, reactive, ref
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';
let personagens = reactive(ref())
// fetch - axios
onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results
    console.log(personagens)
  });
})
</script>
<template>
  <section>
  <main>
    <div class="container">
      <div class="row mt-6">
        <div class="col-sm-12 col-md-6">
          <div class="cardy center" style="width: 90%" text-align: center>
            <h3 class="card-text text-center">Personagens Rick and Morty</h3>
          </div>
        </div>
      </div>
    </div>    
        <div class="col-sm-12 col-md-6" style="width: 50%">
          <div class="card">
            <div class="card-body row">
              <ListPersonagens 
            v-for="personagem in personagens"
            :key="personagem.name"
            :name="personagem.name"
            :url="personagem.url"
            :image="personagem.image"
            :status="personagem.status"
            :species="personagem.species"
            :gender="personagem.gender"
            :location="personagem.location"
            :episode="personagem.episode"
            />
              </div>            
            </div>
          </div>  
    </main>
    </section>
</template>
