<script>
    import { store } from "../store.js";
    import axios from 'axios';
    import CardItem from "./CardItem.vue";
    export default {
    name: 'AppMain',
    data() {
        return {
        store,
        }
    },
    components: {
        CardItem,
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
        console.log(res.data.data)
        });
    }
    }

</script>
  
<template>

    <div id="cards_container">
        <CardItem></CardItem>
    </div>

</template>

<style lang="scss" scoped>




 
</style>