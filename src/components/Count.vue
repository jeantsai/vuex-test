<template>
  <h2>Count: {{count}} </h2>
  <button @click="inc">Inc</button>
  <button @click="dec">Dec</button>
</template>

<script>
import Vuex from 'vuex'

const store = new Vuex.Store({
  state: {
    count: 0,
  },
  mutations: {
    inc: state => state.count++,
    dec: state => state.count--,
  },
})


export default {
  name: 'count',
  computed: {
    count() {
      return store.state.count
    }
  },
  methods: {
    inc() {
      store.commit('inc')
    },
    dec: () => store.commit('dec'),
  },
}
</script>