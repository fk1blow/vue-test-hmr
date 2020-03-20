<template>

  <div>

    <button @click="onClick">click me</button>
    xxx

  </div>

</template>

<script>

import Vue from 'vue';

export default {

  mounted() {
    console.log(this)
  },

  methods: {
    onClick(budget) {
      console.log(new Date())
      console.log(new Date())
    }
  }

}


</script>

<style lang="scss" scoped>

</style>
