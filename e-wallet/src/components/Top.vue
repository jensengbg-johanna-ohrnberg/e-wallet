<template>
    <header>
        <h1 class="title"> {{ h1 }} </h1>
        <h4 class="undertitle"> {{ h4 }} </h4>
    </header>
</template>

<script>
export default {
    name: "Top",
    props: {
        h1: String,
        h4: String
    }
}
</script>

<style scoped>
  .title {
    position: absolute;
    width: 250px;
    height: 98px;
    left: 82px;
    top: 9px;
    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: bold;
    font-size: 35px;
    line-height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    text-transform: uppercase;
    color: #222222;
  }
  
  .undertitle {
    position: absolute;
    width: 304px;
    height: 26px;
    left: 55px;
    top: 108px;
    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 15px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    text-transform: uppercase;
    color: rgba(34, 34, 34, 0.6);
  }
</style>