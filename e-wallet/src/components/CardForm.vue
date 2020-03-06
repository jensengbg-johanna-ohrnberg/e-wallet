<template>
  <div class="form" v-on:input="update">

    <label class="vendor-title" for="vendor">
      Vendor
    </label>
    <select class="vendor-input" v-model="vendor" name="vendor" id="vendor">
      <option disabled>SELECT BANK...</option>
      <option value="bitcoin">Bitcoin</option>
      <option value="ninja">Ninja</option>
      <option value="blockchain">Block Chain</option>
      <option value="evil">Evil Corp</option>
    </select>

    <label class="cardnumber-title" for="cardnumber">
      Card Number
    </label>
    <input
      class="cardnumber-input"
      v-model="cardnumber"
      type="text"
      name="cardnumber"
      placeholder="XXXX XXXX XXXX XXXX"
    />

    <label class="cardholder-title" for="cardholder">
      Cardholder Name
    </label>
    <input
      class="cardholder-input"
      v-model="cardholder"
      type="text"
      name="cardholder"
      placeholder="FIRSTNAME LASTNAME"
    />

    <label class="validity-title" for="validity">
      Valid Thru
    </label>
    <input
      class="validity-input"
      v-model="validity"
      type="text"
      name="validity"
      placeholder="MM/YY"
    />
    
    <label class="ccv-title" for="ccv">
      CCV
    </label>
    <input 
      class="ccv-input" 
      v-model="ccv" 
      type="text" 
      name="ccv" 
      placeholder="xxx" 
    />

  </div>
</template>

<script>
export default {
  data: () => {
    return {
      vendor: "",
      cardnumber: "",
      cardholder: "",
      validity: "",
      ccv: ""
    }
  },
  methods: {
    update() {
      const input = {
        vendor: this.vendor,
        cardnumber: this.cardnumber,
        cardholder: this.cardholder,
        validity: this.validity,
        ccv: this.ccv
      }
      this.$emit("update", input);
    },

  }
};
</script>

<style scoped>
  .cardnumber-title {
    position: absolute;
    width: 251px;
    height: 22px;
    left: 16px;
    top: 507px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color: rgba(0, 0, 0, 0.8);
  }

  .cardnumber-input {
    position: absolute;
    width: 382px;
    height: 56px;
    left: 16px;
    top: 528px;
    border: 1px solid rgba(0, 0, 0, 0.8);
    box-sizing: border-box;
    border-radius: 8px;
  }

  .cardholder-title {
    position: absolute;
    width: 251px;
    height: 22px;
    left: 16px;
    top: 594px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color: rgba(0, 0, 0, 0.8);
  }

  .cardholder-input {
    position: absolute;
    width: 382px;
    height: 56px;
    left: 16px;
    top: 615px;
    border: 1px solid rgba(0, 0, 0, 0.8);
    box-sizing: border-box;
    border-radius: 8px;
  }

  .validity-title {
    position: absolute;
    width: 175px;
    height: 22px;
    left: 16px;
    top: 683px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color: rgba(0, 0, 0, 0.8);
  }

  .validity-input {
    position: absolute;
    width: 175px;
    height: 56px;
    left: 16px;
    top: 704px;
    border: 1px solid rgba(0, 0, 0, 0.8);
    box-sizing: border-box;
    border-radius: 8px;
  }

  .ccv-title {
    position: absolute;
    width: 175px;
    height: 22px;
    left: 223px;
    top: 683px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color: rgba(0, 0, 0, 0.8);
  }

  .ccv-input {
    position: absolute;
    width: 175px;
    height: 56px;
    left: 223px;
    top: 704px;
    border: 1px solid rgba(0, 0, 0, 0.8);
    box-sizing: border-box;
    border-radius: 8px;
  }

  .vendor-title {
    position: absolute;
    width: 382px;
    height: 22px;
    left: 16px;
    top: 419px;
    font-family: 'PT Mono';
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 13px;
    display: flex;
    align-items: center;
    text-transform: uppercase;
    color: rgba(0, 0, 0, 0.8);
  }

  .vendor-input {
    position: absolute;
    width: 382px;
    height: 56px;
    left: 16px;
    top: 440px;
    border: 1px solid rgba(0, 0, 0, 0.8);
    box-sizing: border-box;
    border-radius: 8px;
  }
</style>