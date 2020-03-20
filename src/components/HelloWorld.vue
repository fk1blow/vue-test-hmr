<template>

  <div class="hello">

    <test-container v-slot="{ visible }">

      the thing is that if i remove the `v-slot` fromt the `test-container`,
      it works fine, but if it put back the `v-slot` it stops hmr-ing it again.

      to test this, try to comment/uncomment the console.logs inside the testbudgets component,
      and see if that works. If the v-slot is present, it wont work, but if it's not,
      the test-budgets will remount(re initialized - see the console.log inside the `mounted`)
      and the update code will take its place

      <test-budgets :key="new Date().datetime"></test-budgets>

    </test-container>

  </div>

</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import TestBudgets from '@/components/TestBudgets.vue';
import TestContainer from '@/components/TestContainer.vue';

@Component({
  components: {
    TestBudgets, TestContainer
  }
})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
