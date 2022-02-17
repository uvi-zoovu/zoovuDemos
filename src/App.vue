<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.svg">
    <br/>
    <FilterBar @filterRequest="filter"></FilterBar>
    <div id="carousel">{{this.$data.activeFilters}}</div>

  </div>
</template>

<script>
import FilterBar from "@/components/FilterBar";

export default {
  name: 'App',
  components: {FilterBar},
  data(){
  return {activeFilters : []}
  },
  methods: {
    filter(params) {
      if(params.status) {
        this.$data.activeFilters.push(params.demoType)
      }
      else{
        this.$data.activeFilters.splice(this.$data.activeFilters.indexOf(params.demoType),1)
      }
    }
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
