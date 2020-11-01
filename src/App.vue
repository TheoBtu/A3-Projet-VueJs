<template>
  <nav-bar
      @change-component="updateSelectedComponent"
  >
  </nav-bar>

  <keep-alive>
    <component
        :is="selectedComponent"
        v-bind="currentProps"
        @update-selection="updateSelection"
    >
    </component>
  </keep-alive>
</template>


<script>
import ClassroomList from './components/ClassroomList.vue';
import SelectionList from "./components/SelectionList";
import NavBar from "./components/navigation/NavBar";

export default {
  name: 'App',
  components: {
    NavBar,
    ClassroomList,
    SelectionList
  },
  data(){
    return{
      selectedComponent: 'classroom-list',
      classroomArray: [],
    }
  },
  computed:{
    currentProps(){
      if(this.selectedComponent == "selection-list"){
        return { selection: this.classroomArray}
      }
      return false
    }
  },
  methods:{
    updateSelectedComponent(comp){
      this.selectedComponent = comp
    },
    updateSelection(classroom){
      this.classroomArray.push(classroom);
    }
  }
}
</script>


