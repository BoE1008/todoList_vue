<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}

.finished {
  text-decoration: underline;
}
</style>

<template>
<div>
  <input type="text" v-model="newItem" v-on:keyup.enter="enter">
  <ul>
    <li v-for="item in todos" v-on:click="liClick(item)" v-bind:class="{finished:item.isFinished}">
      {{item.label}}
    </li>
  </ul>
  <div>
    {{sonmsg}}
  </div>
  <button type="button" @click='tofather'>子传父</button>
</div>
</template>

<script>
export default {
  data() {
    return {
      msg: '',
      newItem:'',
      todos: [],
    }
  },
  props:['sonmsg'],
  methods: {
    liClick(item) {
      item.isFinished = !item.isFinished;
    },
    enter(){
      this.todos.push({label:this.newItem,isFinished:false});
      this.newItem = '';
    },
    tofather(){
      this.$emit("childsend","this is from child")
    }
  }
}
</script>
