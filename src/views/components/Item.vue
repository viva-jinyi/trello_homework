<template>
  <div>
    <button v-if="order>1" @click="moveTaskNext()"> &lt; </button>
    <div class="task">
      <span v-if="!isEditable" @click="editTask()">{{ task }}</span>
      <input v-else type="text" v-model="inputTask">
    </div>
    <button v-if="order<4" @click="moveTaskPrev()"> > </button>
  </div>
</template>

<script>
export default {
  props: ['data', 'columnOrder'],
  data() {
    return {
      isEditable: false,
      task: this.data,
      order: this.columnOrder,
      inputTask: this.data,
    };
  },
  methods: {
    editTask() {
      this.isEditable = true;
    }
  }
}
</script>

<style lang="scss" scoped>
button{
  outline: none;
  border: none;
  background-color: #FFF;
}
.task{
  display: inline-block;
  text-align: center;
}
</style>