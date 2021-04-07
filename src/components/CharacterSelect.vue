<template>
  <option>{{character.name}}</option>
</template>

<script>
import{eventBus} from '../main.js'

export default {
    name: 'select-character',
    props: ['character'],
    methods: {
        
    }
}
</script>

<style>

</style>