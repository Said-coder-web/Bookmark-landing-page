<template>
  <div class="title-section max-w-[450px] mx-auto px-[10px] text-center">
    <h2 class="text-[2rem] font-medium mb-[10px]">{{ headSection }}</h2>
    <p class="opacity-75">{{ parSection }}</p>
  </div>
</template>

<script>
export default {
  inject: ["headSection", "parSection"],
};
</script>

<style lang="scss">
// .title-section {
//   text-align: ;
// }
</style>
