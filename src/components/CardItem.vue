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

   
  </div>
</template>

<style lang="scss" scoped>



  .card{
    width: calc(100% / 5 - 20px / 5 * 4);

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
  }


</style>