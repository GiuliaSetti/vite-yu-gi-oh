<script>
export default {
  name: 'CardItem',
  data() {
    return {

      
      index: 0,

    }
  },
  props: {
    cards: Object,
  }
}
</script>
<template>
  <div class="card">

    <div class="card_image">
      <img :src="cards.card_images[index].image_url" alt="">
    </div>

    <div class="card_price">
      <h6>Amazon Price</h6>
      <div>€ {{ cards.card_prices[index].amazon_price }}</div>
    </div>

    <div class="card_name">
      <div class=" name">{{ cards.name }}</div>
      <div class="type">{{ 'Type: ' + cards.type }}</div>
    </div>
  

   
  </div>
</template>

<style lang="scss" scoped>

@use "../scss/variables" as *;



  .card{
    width: calc(100% / 5 - 20px / 5 * 4);

    position: relative;

    .card_image{
      width: 100%;

      border-radius: 10px;

      box-shadow: 5px 4px 6px black;

      img{
        width: 100%;

        border-radius: 10px;

        display: block;

        
      }
    }

    &:hover .card_price{
      display: block;
    }

    &:hover .card_image{
      filter: brightness(0.3);
    }


    .card_price{
      position: absolute;

      background-color:#7549B1;
      padding: 1rem;

      border-radius: 20px;

      font-size: 20px;
      font-weight: bold;

      color: $text-color;

      top: 20px;
      right: 20px;



      display: none;

    
    }

    .card_name{
      text-align: center;
      margin-top: 10px;
      padding: 10px;
      color: purple;
      font-weight: bold;
      font-size: 13px;

      border: 1px solid purple;
      border-radius: 20px;
      background-color: $background;
      box-shadow: 1px 1px 3px black;
    }


    
  }


</style>