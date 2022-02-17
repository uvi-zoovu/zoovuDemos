<template>
  <div>
    <form class='filterBar'>
      <h1 class='filterHeader'>Demo Type</h1>
      <fieldset v-for='demoType in demoTypes' v-bind:key='demoType'>
        <input
            type='checkbox'
            :id=demoType
            :value=demoType
            @change='$emit("filterRequest", {demoType: demoType, status: $event.target.checked})'
        >
        <input
            v-if='index != demoTypes.length - 1'
            type='button'
            id=demoTypesAll
            @click='$emit("filterRequest", {demoType: demoType, status: $event.target.checked})'
        >
        <label :for=demoType>{{ demoType.toUpperCase() }}</label>
      </fieldset>


        <h1 class='filterHeader'>Demo Industry</h1>
        <fieldset v-for='demoType in demoTypes' v-bind:key='demoType'>
          <input
              type='checkbox'
              :id=demoType
              :value=demoType
              @change='$emit("filterRequest", {demoType: demoType, status: $event.target.checked})'
          >
          <label :for=demoType>{{ demoType.toUpperCase() }}</label>
        </fieldset>

    </form>
  </div>
</template>

<script>
export default {
  name: 'FilterBar',
  emits:['filterRequest'],
  data() {
    return {
      demoTypes: ['assistant', 'configurator', 'others'],
      demoIndustries: []
    }
  },
  methods: {
    
  }
}
</script>

<style scoped>
.filterBar{
  width: 10vw;
  background: aliceblue;
}
</style>