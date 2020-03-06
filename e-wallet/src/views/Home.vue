<template>
  <div class="cards">

    <div class="top-card">
      <top h1="E-WALLET" h4="ACTIVE CARD"/>
      <card 
        class="active-card" 
        v-bind:input="input"
      />
    </div>

    <div class="card-stack">
      <CardStack 
        v-bind:cards="cards" 
        v-on:activateCard="activateCard"
      />
    </div>

    <div>
      <button 
        class="add-new-card-button" 
        v-on:click="addnewcard"
      >
        ADD A NEW CARD
      </button>
    </div>

  </div>
</template>

<script>
import top from "../components/Top";
import card from "../components/Card";
import CardStack from "../components/CardStack";

export default {
  name: "Cards",
  components: {
    top,
    card,
    CardStack,
  },
  props: {
    card: Array
  },
  data: () => {
    return {
      cards: [],
      activeCard: {},
    };
  },
  methods: {
    addnewcard() {
      this.$router.push('/AddCard')
    },
    activateCard(index) {
      this.input = this.cards[index];
    }
  }
};
</script>

<style scoped>
  .cards {
    position: relative;
    width: 414px;
    height: 896px;
    background: #FFFFFF;
    border: 2px solid black;
    margin-left: 38%;
  }

  .top-card {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .active-card {
    position: absolute;
    width: 382px;
    height: 241px;
    left: 16px;
    top: 138px;
  }

  .card-stack {
    display: flex;
    flex-direction: column;
    margin-top: 25rem;
  }

  .add-new-card-button {
    position: absolute;
    width: 382px;
    height: 80px;
    left: 16px;
    top: 799px;
    border: 1px solid #000000;
    box-sizing: border-box;
    border-radius: 8px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: bold;
    font-size: 22px;
    line-height: 25px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    text-transform: uppercase;
    color: #000000;
  }
</style>