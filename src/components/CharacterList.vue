<template>
  <section>
      <select @change="handleChange" v-model="selectedCharacter" name="characters" id="characters">
          <option v-for="(character, index) in characters" :value="character" :key="index">{{character.name}}</option>
      </select>
  </section>
</template>

<script>
import CharacterSelect from './CharacterSelect';
import{eventBus} from '../main.js'

export default {
name: 'characters-list',
props:['characters'],
data() {
    return {
        selectedCharacter: {}
    }
},

components: {
    "character-select": CharacterSelect
},
methods: {
    handleChange: function() {
       eventBus.$emit('character-selected', this.selectedCharacter)

    }
}
//  methods: {
//         onChange(event) {
//             console.log(event.target.value)

}
</script>

<style scoped>
ul {
    list-style: none;
}
</style>