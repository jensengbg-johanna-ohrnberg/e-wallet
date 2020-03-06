<template>
  <div class="addCards">
    <Top h1="ADD A NEW BANK CARD" h4="NEW CARD"/>
    <Card 
      v-bind:card="card"
    />
    <CardForm 
      v-on:addcard="addcard" 
      v-on:update="update"
    />

    <div>
      <button 
        class="add-card-button" 
        v-on:click="addcard"
      >
        Add Card
      </button>
      <button 
        class="view-cards-button" 
        v-on:click="viewcards"
      >
        VIEW CARDS
      </button>
    </div>
  </div>
</template>

<script>
import Top from "../components/Top";
import Card from "../components/Card";
import CardForm from "../components/CardForm";

export default {
  name: "Add Cards",
  components: {
    Top,
    Card,
    CardForm
  },
  data: () => {
    return {
      card: {},
      cards: []
    };
  },
  methods: {
    viewcards() {
      this.$router.push('/')
    },
    update(input) {
      this.card = input;
    },
    addcard() {
      this.$emit('update', this.card);
        this.$router.push(this.input)
    }
  }
}
</script>

<style scoped>
  .addCards {
    position: relative;
    width: 414px;
    height: 896px;
    background: #FFFFFF;
    border: 1px solid black;
    margin-left: 38%;
  }

  .add-card-button {
    position: absolute;
    width: 191px;
    height: 72px;
    left: 16px;
    top: 808px;
    background: #000000;
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
    color: #FFFFFF;
  }

  .view-cards-button {
    position: absolute;
    width: 191px;
    height: 72px;
    left: 210px;
    top: 808px;
    background: #000000;
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
    color: #FFFFFF;
  }
</style>