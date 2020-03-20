<template>
  <div>
    <slot :visible="visible"></slot>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class extends Vue {
  get visible() {
    return 'xxxxx visible xxxx'
  }

  afterUpdate() {
    console.log('afterUpdate')
  }
}

</script>

<style lang="scss" scoped>

</style>
