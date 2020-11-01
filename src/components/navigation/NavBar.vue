<template>
  <div class="bg-blue-200 p-2">

    <!-- Avec un tableau dans la data -->
    <a v-for="(link, index) in navigation"
       :key="index"
       href="#"
       @click="selectComponent(link.component)"
    >
      {{ link.name }}
      | </a>

    <!-- <a href="#" @click="selectComponent('player-list')"> Tous les joueurs </a> |   Avec une function
         <a href="#" @click="selectComponent('selection-list')"> Ma sélection </a>
         <a href="#" @click="selectedComponent = 'selection-list'"> Ma sélection </a>    Sans function
    -->
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  data(){
    return{
      navigation: [
        {name: "Tous les cours disponible", component: "classroom-list"},
        {name: "Les cours suivis", component: "selection-list"}
      ]
    }
  },
  methods:{
    selectComponent(comp){
      this.$emit('change-component', comp)
    }
  }
}
</script>

<style scoped>

</style>
