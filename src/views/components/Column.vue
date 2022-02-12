<template>
  <!-- <div class="column">{{ data }}</div> -->
  <div class="column">
    <div class="title">{{ data.title }}</div>
    <div class="contents">
      <div  v-for="(item, index) in itemData" :key="index" class="item"></div>
      <button class="item" @click="addTask">+</button>
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
  methods: {
    addTask() {
      
    }
  }
}
</script>

<style lang="scss" scoped>
.column{
  width: 25%;
  font-size: 1.5rem;
  position: relative;
  height: 140px;
  text-align: center;
  border: 1px solid #000;
  color: #000;
  background-color: #CFCFCF;
  $titleHeight: 30px;
  .title{
    position: absolute;
    top: 0;
    left: 0;
    height: $titleHeight;
    width: 100%;
    background-color: skyblue;
  }
  .contents{
    position: relative;
    top: $titleHeight;
    padding: 5px;
  }
  .item{
    display: block; 
    width: 100%; height: 20px;
    border: 1px solid #000;
    background-color: #FFF;
  }
}
</style>