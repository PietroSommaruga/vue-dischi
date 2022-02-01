<template>
  <div id="app">
    <header-content @filtro="filterGenre"/>
      <main-container :discs="filteredDiscs"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderContent from './components/HeaderContent.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderContent,
    MainContainer,
  },
  data() {
    return {
      discs : [],
      filteredDiscs: [],
    }
  },
  mounted() {
    axios.get(' https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
      this.discs = result.data.response
      this.filteredDiscs = result.data.response
      
      
    })
  },

  methods: {
    // ----- filtro per genere -----
    filterGenre(selectedValue) {
      if (selectedValue === 'All') {
        this.filteredDiscs = this.discs;
      } else {
        this.filteredDiscs = this.discs.filter((disk) => {
          return disk.genre.includes(selectedValue); 
        });
      }
    },
  }
}
   
</script>

<style lang="scss">
#app {
  @import '@/style/all.scss';
}
</style>
