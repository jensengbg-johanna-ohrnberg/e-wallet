<template>
  <article class="card" v-on:click="activateCard()" v-bind:class="['card', vendor, chip]">
    <div>
      <img class="chip-img" v-bind:src="require(`../assets/chip-${chip}.svg`)">
      <img class="vendor-img" v-bind:src="require(`../assets/vendor-${vendor}.svg`)">
    </div>

    <div>
      <p class="cardnumber"> {{ cardnumber }} </p>
    </div>

    <div>
      <p class="cardholder-label">Cardholder Name</p>
      <p class="cardholder"> {{ cardholder }} </p>
    </div>

    <div>
      <p class="validity-label">Valid Thru</p>
      <p class="validity"> {{ validity }} </p>
    </div>
  </article>
</template>

<script>
export default {
  name: "Card",
  props: {
    card: Object
  },
  data: () => {
    return {
      defaultImg: "",
      defaultNumber: "xxxx xxxx xxxx xxxx",
      defaultHolder: "Firstname Lastname",
      defaultValidity: "MM/YY"
    };
  },
  computed: {
    cardnumber() {
      if (!this.card.cardnumber) {
        return this.defaultNumber;
      } else {
        let number = this.card.cardnumber
        number = number.match(/.{1,4}/g)   
        return number.join(' ');
      }
    },
    cardholder() {
      if (!this.card.cardholder) {
        return this.defaultHolder;
      } else {
        return this.card.cardholder;
      }
    },
    validity() {
      if (!this.card.validity) {
        return this.defaultValidity;
      } else {
        return this.card.validity;
      }
    },
    vendor() {
      if (!this.card.vendor) {
        return this.defaultImg;
      } else {
        return this.card.vendor;
      }
    },
    chip() {
      let chip = "dark";
      if (!this.card.vendor) {
        return chip;
      } else if (this.card.vendor === "bitcoin") {
        return chip;
      } else {
        chip = "light";
        return chip;
      }
    }
  },
  methods: {
    activateCard() {
      this.$emit("activateCard", this.card)
      console.log(this.card)
    }
  }
}
</script>

<style scoped>
  .card {
    position: absolute;
    width: 382px;
    height: 241px;
    left: 16px;
    top: 150px;
  }
  
  .chip-img {
    position: absolute;
    width: 70px;
    height: 60px;
    left: 20px;
    top: 20px;
  }

  .vendor-img {
    position: absolute;
    left: 80%;
    right: 10%;
    top: 14%;
  }

  .bitcoin {
    background: linear-gradient(237.41deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 99.07%), #FFAE34;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    border-radius: 8px;
    color: #000000;
  }

  .ninja {
    background: linear-gradient(237.75deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 100%), #222222;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.2);
    border-radius: 8px;
    color: #FFFFFF;
  }

  .blockchain {
    background: linear-gradient(238.04deg, rgba(0, 0, 0, 0.15) 1.49%, rgba(0, 0, 0, 0) 100%), #8B58F9;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.2);
    border-radius: 8px;
    color: #000000;
  }

  .evil {
    background: linear-gradient(237.75deg, rgba(0, 0, 0, 0.16) 0%, rgba(0, 0, 0, 0) 100%), #F33355;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.2);
    border-radius: 8px;
    color: #FFFFFF;
  }

  .dark {
    color: #222222;;
    text-shadow: -0.5px 0.5px 0px #3a3a3a;
  }

  .light {
    color: #FFFFFF;
    text-shadow: 0.5px 0.5px 0px #868686, -0.5px -0.5px 0px #868686;
  }

  .cardnumber {
    position: absolute;
    width: 350px;
    height: 42px;
    left: 55px;
    top: 80px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 29px;
    line-height: 32px;
    letter-spacing: 0.03em;
  }

  .cardholder-label {
    position: absolute;
    width: 251px;
    height: 16px;
    left: 32px;
    top: 155px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
  }

  .cardholder {
    position: absolute;
    width: 251px;
    height: 32px;
    left: 32px;
    top: 170px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 20px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
  }

  .validity-label {
    position: absolute;
    width: 89px;
    height: 16px;
    left: 280px;
    top: 155px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-align: right;
    text-transform: uppercase;
  }

  .validity {
    position: absolute;
    width: 89px;
    height: 32px;
    left: 280px;
    top: 170px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 20px;
    display: flex;
    align-items: center;
    text-align: right;
    text-transform: uppercase;
  }
</style>