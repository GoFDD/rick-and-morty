<template>
  <div class="col-md-12 mb-12">
    <div class="card">
      <img :src="imageUrl" height="100%" alt="Imagem do personagem" class="card-img-top ">
      <div class="card-body">
        <h5 class="text-center">{{ character.name }}</h5>
        <p class="text-center">
          <strong>Status:</strong> {{ character.status }}<br>
          <strong>Espécie:</strong> {{ character.species }}<br>
          <strong>Gênero:</strong> {{ character.gender }}<br>
          <strong>Localização atual:</strong> {{ character.location.name }}<br>
          <strong>Episódios:</strong> {{ character.episode.length }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps(["character"]);
const imageUrl = `https://rickandmortyapi.com/api/character/avatar/${props.character.id}.jpeg`;
</script>

<style scoped>

</style>
