<template>
  <div class="column">
    <div class="title">{{ title }}</div>
    <div class="contents">
      <Item v-for="(item, index) in itemData" :key="index" class="item" :data="item" :columnOrder="columnOrder" />
      <button class="item" @click="addTask()">+</button>
    </div>
  </div>
</template>

<script>
import Item from './Item.vue'

export default {
  components: { Item },
  props: ['data', 'index'],
  data() {
    return {
      itemData: this.data.items,
      title: this.data.title,
      columnOrder: this.index,
    };
  },
  methods: {
    addTask() {
      let result = prompt(`Add a new item in [${this.title}]`);
      if (result != null) {
        this.itemData.push(result);
      }
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
    height: calc( 140px - #{$titleHeight} );
    overflow-y: auto;
  }
  .item{
    display: block; 
    width: 100%; height: 20px;
    border: 1px solid #000;
    background-color: #FFF;
    font-size: 1rem;
    line-height: 20px;
    margin-bottom: 5px;
    &:last-child{
      margin-bottom: 0;
    }
  }
}
</style>