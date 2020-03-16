<template>
    <section class="stack">
        <div class="cards" v-for="(card, index) in allCards" v-bind:key="index">
            <card 
              class="card" 
              v-bind:card="card"
              @activateCard="activateCard"
            />
        </div>
    </section>
</template>

<script>
import card from "../components/Card";
export default {
  name: "CardStack",
  components: {
    card
  },
  props: {
    allCards: Array
  },
  methods: {
    activateCard(card) {
      this.$emit('activateCard', card)
      console.log(card)
    }
  }  
}
</script>

<style scoped>
  .stack {
    position: absolute;
    left: 5px;
    top: 320px;
  }

  .cards {
    height: 5rem;
    overflow: visible;
    margin-top: -2rem;
    position: relative;
  }

  .card {
    cursor: pointer;
  }
</style>