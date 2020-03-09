<template>
  <div class="cards">
    <div class="top-card">
      <top 
        h1="E-WALLET" 
        h4="ACTIVE CARD"
      />
      <card 
        class="active-card" 
        v-bind:card="card"
      />
    </div>

    <div class="card-stack">
      <CardStack 
        v-bind:allCards="cards"
      />
    </div>

    <div>
      <button class="add-new-card-button" v-on:click="addnewcard">
        ADD A NEW CARD
      </button>
      <button class="remove-new-card-button" v-on:click="removenewcard">
        REMOVE CARD
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
  data: () => {
    return {
      card: {},
      cards: [],
      allCards: localStorage.getItem('allCards')
    };
  },
  methods: {
    addnewcard() {
      this.$router.push('/AddCard')
    }
  },
  watch: {
    allCards() {
      this.cards = JSON.parse(localStorage.getItem('cards'))
    }
  },
  mounted () {
    if (localStorage.getItem('allCards')) {
      this.cards = JSON.parse(localStorage.getItem('allCards'))
    } else {
      localStorage.setItem('allCards', JSON.stringify(this.cards))
    }
  }
}
</script>

<style>
  .add-new-card-button {
    position: absolute;
    width: 191px;
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
    cursor: pointer;
  }

  .remove-new-card-button {
    position: absolute;
    width: 192px;
    height: 80px;
    left: 210px;
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
    cursor: pointer;
  }
</style>