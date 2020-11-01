<template>
  <h1> Ma sélection </h1>
  <span v-if="selection.length == 0">
    <p>Vous n'avez pas de cours suivis</p>
  </span>

  <div v-else>
    <selection-classroom
        v-for="(classroom, index) in selection"
        :classroomIndex="index"
        :key="index"
        :classroom="classroom"
    >
      {{ classroom.name }}
    </selection-classroom>
  </div>

</template>

<script>
import SelectionClassroom from "./SelectionClassroom";
export default {
  name: "selection-list",
  components:{
    SelectionClassroom
  },
  props: ['selection']
}
</script>

<style scoped>

</style>
