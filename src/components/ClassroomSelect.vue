<template>
  <div class="text-lg font-bold ml-4 text-2xl text-gray-800"> Mes Cours Suivis: {{selection.length}}
    <span v-if="nbrClassroom"> Cours </span>
    <span v-else> Cours </span>
  </div>
</template>

<script>
export default {
  name: "classroom-select",
  props: ['selection'],
  computed: {
    nbrClassroom(){
      if(this.selection.length > 1){
        return true
      }
      return false
    }
  }
}
</script>

<style scoped>

</style>
