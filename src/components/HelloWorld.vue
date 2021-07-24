<script lang="ts">
import { ref, defineComponent } from 'vue';

export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      required: true,
    },
  },
  setup: () => {
    const count = ref(0);
    return { count };
  },
});
</script>
<template>
  <div class="">
    <h1 class="">{{ msg }}</h1>
  </div>
</template>

<style scoped lang="scss"></style>
