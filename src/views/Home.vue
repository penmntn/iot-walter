<template>
  <div class="home">
    <div>
        <test/>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import test from '../components/chart2.vue'

@Options({
  components: {
    test
  }
})
export default class Home extends Vue {}
</script>
