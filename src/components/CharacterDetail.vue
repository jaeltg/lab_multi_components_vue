<template>
  <section>
      <h3>{{character.name}}</h3>
      <p>{{character.status}}</p>
      <p>{{character.species}}</p>
      <p>{{character.origin.name}}</p>
      <img :src="character.image" alt="">
      <!-- gogo Jael ! <your personal cheerleader> i was missing this!! -->
  </section>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}

</script>

<style>

</style>