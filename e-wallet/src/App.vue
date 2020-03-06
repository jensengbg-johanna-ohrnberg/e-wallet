<template>
  <div id="app">
    <div id="nav">
      <router-link to="/"></router-link>
      <router-link to="/addcard"></router-link>
    </div>
    <router-view v-bind:card="cards" v-on:update="update" class="e-wallet"/>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      cards: []
    }
  },
  methods: {
    update(card) {
      this.cards.push(card);
    }
  }
}
</script>

<style>
  .e-wallet {
    background: #FFFFFF;
  }
</style>