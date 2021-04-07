<template>
  <div id="app">
    <h1>The Creatures of Imaginary Universes</h1>
    <div class="main">
      <characters-list :characters='characters' :selectedCharacter='selectedCharacter'/>
      <character-detail v-if='selectedCharacter' :character='selectedCharacter'/>
    </div>
  </div>
</template>

<script>
import{eventBus} from './main.js';
import CharacterDetail from './components/CharacterDetail';
import CharacterList from './components/CharacterList';



export default {
  name: 'App',
  data(){
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characters = characters.results)
    
    eventBus.$on('character-selected', (character) => {
    this.selectedCharacter = character;
    })
  },

  components: {
    "character-detail": CharacterDetail,
    "characters-list": CharacterList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
