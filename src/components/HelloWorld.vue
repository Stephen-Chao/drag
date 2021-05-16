<template>
  <vuedraggable class="wrapper" v-model="list" :sort= "true" animation=500 chosenClass="chosen">
    <transition-group>
      <div v-for="item in list" :key="item" class="item">
        <p>{{list.indexOf(item)+1+','+item}}</p>
      </div>
    </transition-group>
  </vuedraggable>
</template>

<script>
import vuedraggable from 'vuedraggable';

export default {
  name: 'HelloWorld',
  components: {vuedraggable},
  props: {
  },
  data() {
    return {
      list: ['选项1','选项2','选项3','选项4']
    }
  },
  updated() {
    console.log(this.list)
  },
  methods: {
  }
}
</script>
<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
  width: 100%;
}
.item{
  width: 300px;
  height: 50px;
  background-color: #fff;
  color: #000;
  border-top: 1px solid #999;
}
.chosen{
  background: #2378ff;
  color: #fff;
}
</style>
