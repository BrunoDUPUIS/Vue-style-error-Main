<script setup>
import Details from '../components/Details.vue'

// Déclaration de la props qui contient les informations d'un animal
const props = defineProps({
  animalInfos: Object
})
</script>

<template>
  <div
    class="card"
    :class="{
      opacity: animalInfos.alreadyAdopted === true
    }"
  >
    <div>
      <Details :animalInfos />
      <!-- <h2>{{ animalInfos.name }}</h2>
      <p><span>Espèce</span> : {{ animalInfos.species }}</p>
      <p><span>Age</span> : {{ animalInfos.age }}</p> -->
    </div>

    <p class="description">{{ animalInfos.description }}</p>
  </div>
</template>

<style scoped>
.opacity {
  opacity: 0.3;
  border: 1px solid red;
}
.card {
  background-color: var(--bgc);
  padding: 15px;
  border-radius: 5px;
  width: calc((100% - 15px) / 2);
  display: flex;
  justify-content: center;
  gap: 10px;
  box-shadow: 0px 0px 7px var(--shadow-color);
  /* border: 3px solid blue; */
}

.card div {
  width: 150px;
  display: flex;
  flex-direction: column;
  gap: 10px;

  /* border: 3px solid red; */
}
.description {
  flex: 1;
  /* border: 1px solid green; */
}
span {
  text-decoration: underline;
  color: gray;
  /* border: 1px solid purple; */
}
.card p {
  color: var(--text-color);
}
/* ======================== */
/* ==== MEDIA QUERRIES ==== */
/* ======================== */

@media (max-width: 900px) {
  .card {
    width: 100%;
    flex-wrap: wrap;
  }
}
</style>
