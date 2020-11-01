<template>
  <div class="border border-gray-700 m-2 p-2 rounded flex justify-between"
       :class="isTimeClass"
  >
    <div>
      <h3 class="text-lg font-bold text-gray-900"> Cours : {{ classroomName }}  ᠌᠌ ᠌ ᠌ ᠌ ᠌᠌ ᠌᠌ ᠌ ᠌ ᠌ ᠌᠌ ᠌᠌ ᠌᠌ ᠌ ᠌ ᠌ ᠌᠌
        Temps: {{classroom.time}} ᠌᠌ ᠌ ᠌ ᠌ ᠌᠌ ᠌᠌ ᠌ ᠌ ᠌ ᠌᠌ ᠌᠌ ᠌᠌ ᠌ ᠌ ᠌ ᠌᠌
        Langues Disponibles: {{classroom.language}}

      </h3>
      <p class="text-gray-100"> {{ classroom.category }} </p>
      <p class="text-gray-100"> {{ classroom.onlineDate }} </p>
    </div>

    <base-button
        text="Sélectionner"
        @click="addToSelection"
    >
    </base-button>

  </div>
</template>

<script>
import BaseButton from "./global/BaseButton";
export default {
  name: "classroom-card",
  components:{
    BaseButton
  },
  props: ['classroom'],
  computed: {
    classroomName() {
      if (this.classroom.name.split(':').length > 1) {
        return this.classroom.name.split(':')[1]
      }
      return this.classroom.name;
    },
    classroomTime() {
      if (this.classroom.time == "Long") {
        return true
      }
      return false
    },
    isTimeClass() {
      return {
        'bg-blue-700': this.classroomTime,
        'bg-blue-500': !this.classroomTime
      }
    }
  },
  methods: {
    addToSelection() {
      this.$emit('add-classroom', this.classroom)
    }
  }
}
</script>

<style scoped>

</style>
