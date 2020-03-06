<template>
    <section class="stack">
        <div class="cards" 
            v-for="(card, index) in cards" 
            v-bind:key="index" 
            v-on:click="activateCard(index)"
        >
            <card 
                class="card" 
                v-bind:card="card" 
                v-on:click="activate"
            />
        </div>
    </section>
</template>

<script>
import card from "../components/Card";

export default {
    name: "Card Stack",
    components: {
        card
    },
    props: {
        cards: Array
    },
    methods: {
        activateCard(index) {
            this.$emit("activateCard", index);
        }
    }
}
</script>

<style scoped>
  .stack {
    height: 24rem;
  }

  .cards:last-child {
    overflow: visible;
  }

  .card {
    cursor: pointer;
    height: 2.5rem;
  }  
</style>