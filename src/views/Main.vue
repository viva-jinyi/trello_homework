<template>
  <div class="main">
    <Column v-for="task in taskData" :key="task.index" :data="task" />
  </div>
</template>

<script>
import Column from './components/Column.vue'

export default {
  components: { Column },
  data() {
    return {
      taskData: [
        {
          index: 1,
          title: "A",
          items: []
        },
        {
          index: 2,
          title: "B",
          items: []
        },
        {
          index: 3,
          title: "C",
          items: []
        },
        {
          index: 4,
          title: "D",
          items: []
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.main{
  width: 1280px;
  max-width: 90vw;
  min-height: 100vh;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 40px;
}
</style>