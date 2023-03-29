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

            axios.get(this.store.APIcall).then((res)=>{
            console.log(res.data.data);
            this.store.cards = res.data.data;

        });
        
    }
    }

</script>
  
<template>

    <div id="main_container">
        <div v-if="store.cards.length == 50" class="cards_container">
            <CardItem v-for="card in store.cards" :cards="card"></CardItem>
        </div>

        <div v-else class="loading">
            <em>Loading...</em>
        </div>
    </div>

</template>

<style lang="scss" scoped>

#main_container{
  background-color: #FCECAE;


    .cards_container{

        padding: 6rem 0;
        display: flex;

        max-width: 1200px;
        margin: 0 auto;

        flex-flow: row wrap;
        justify-content: center;
        gap: 20px;

        overflow-y: auto;


    }

    .loading{
        font-size: 3rem;

        text-align: center;

        padding: 3rem;
    }


}

</style>