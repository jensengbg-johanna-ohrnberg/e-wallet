<template>
  <div>
    <router-view @card="addCards" :cards="cards" class="e-wallet"/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: []
    }
  },
  methods: {
    addCards(card) {
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