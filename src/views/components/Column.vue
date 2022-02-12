<template>
  <!-- <div class="column">{{ data }}</div> -->
  <div class="column">
    <div class="title">{{ data.title }}</div>
    <div class="contents">
      <div v-if="!itemData.length>0"><button>+</button></div>
      <div v-else v-for="(item, index) in itemData" :key="index"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['data'],
  data() {
    return {
      itemData: this.data.items,
    };
  },
}
</script>

<style lang="scss" scoped>
.column{
  .title{
    
  }
}
</style>