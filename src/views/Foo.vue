<template>
  <div class="foo">
    <h1>This is the Foo page</h1>
    {{count}}<br>{{word}}<br>
    <button v-on:click="counterPlus">Click to increment</button>
    <button v-on:click="counterMinus">Click to decrement</button>
    <br>
    <input v-on:keyup="updateWord" v-model="inputWord" />
  </div>
</template>


<script>
export default {
  name: 'Foo',
  data: function() {
    return {
      data: "data",
      store: this.$store,
      inputWord: ""
    }

  },
  methods: {
    counterPlus: function() {
      // console.log(event)
      this.$store.commit("increment")
    },
    counterMinus: function() {
      // console.log(event)
      this.$store.commit("decrement")
    },    
    updateWord: function(){
      this.$store.commit("changeWord", this.inputWord)
    }
  },
  computed: {
    count () {
      return this.$store.state.count
    },
    word () {
      return this.$store.state.word
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
