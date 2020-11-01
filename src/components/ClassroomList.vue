<template>
  <h1 class="text-lg font-bold ml-4 text-3xl text-gray-900"> Liste des {{classroomsData.name}} </h1>

  <classroom-select
      :selection="selection"
  >
  </classroom-select>

  <classroom-card v-for="(classroom, index) in classroomsData.classroom"
                  :key="index"
                  :classroom="classroom"
                  @add-classroom="addClassroomToSelection"
  >
  </classroom-card>
</template>

<script>
import classroomsData from '../assets/data/classrooms.json'
import ClassroomCard from "./ClassroomCard";
import ClassroomSelect from "./ClassroomSelect";

export default {
  name: "classroom-list",
  components: {
    ClassroomCard,
    ClassroomSelect
  },
  data(){
    return{
      classroomsData : classroomsData,
      selection: []
    }
  },
  methods: {
    addClassroomToSelection(classroom){
      this.selection.push(classroom)
      this.$emit("update-selection", classroom);
    }
  }
}
</script>

<style scoped>

</style>
