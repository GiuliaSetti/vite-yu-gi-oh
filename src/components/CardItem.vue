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

      box-shadow: 1px 1px 5px black;

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


    
  }


</style>