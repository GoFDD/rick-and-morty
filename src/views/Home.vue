<template>
  <link rel="stylesheet" href="@/../src/assets/css/style.css">
  <div class="container">
    <main>
      <section class="chars">
        <img src="@/assets/logo.svg" alt="">

        
        <div class="filters">
          <input type="text" id="name" placeholder="Filtrar por nome..." class="filter">
          <select name="species" id="species" class="filter">
            <option value="">Espécie</option>
            <option value="animal">Animal</option>
            <option value="alien">Alien</option>
            <option value="human">Humano</option>
            <option value="humanoid">Humanoide</option>
            <option value="mythological">Mitológico</option>
            <option value="poopybutthole">Poopybutthole</option>
            <option value="robot">Robô</option>
          </select>
          <select name="gender" id="gender" class="filter">
            <option value="">Gênero</option>
            <option value="female">Feminino</option>
            <option value="male">Masculino</option>
          </select>
          <select name="status" id="status" class="filter">
            <option value="">Status</option>
            <option value="alive">Vivo</option>
            <option value="dead">Morto</option>
          </select>
        </div>

        <!-- Cards de personagens -->
        <div class="chars-container">
          <CharacterCard
            v-for="(character, index) in characters"
            :key="index"
            :character="character"
          />
        </div>

        <button class="margem" id="load-more" @click="loadMore">
            Carregar mais
        </button>

      </section>
    </main>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import CharacterCard from '../components/CharacterCard.vue';

const characters = ref([]);

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character/")
    .then(response => response.json())
    .then(data => {
      characters.value = data.results;
    })
    .catch(error => {
      console.error('Erro ao carregar dados dos personagens:', error);
    });
})
</script>


