<script>

    // store
    import { store } from "../store.js";
    // axios
    import axios from 'axios';
    // card
    import CardItem from "./CardItem.vue";
    // barra di ricerca
    import AppSearchBar from './AppSearchBar.vue'
    // totale delle carte trovate
    import AppCardCount from './AppCardCount.vue'

    export default {
    name: 'AppMain',
    data() {
            return {

                store,
            }
        },
        components: {
            CardItem,
            AppSearchBar,
            AppCardCount,
        },

        created() {

                axios.get(this.store.APIcall).then((res)=>{
                console.log(res.data.data);
                this.store.cards = res.data.data;

            });
            
        },
        
        methods: {
                search() {
                 
                    let APInewString = `${this.store.APIcall}`;

                    if (this.store.cardName != '') {

                        APInewString += `&fname=${this.store.cardName}`;

                    }

                    if (this.store.cardType != '') {

                        APInewString += `&type=${this.store.cardType}`;

                    }

                    axios.get(APInewString).then((res) => {
                        console.log(res.data.data);
                        this.store.cards = res.data.data;

                        this.store.cardCount= this.store.cards.length;
                    });
              
               
                        
                
            }
        }
    }

</script>
  
<template>

    

    <div id="main_container">

        <!-- searchbar -->
        <AppSearchBar  @searchCard="search()"></AppSearchBar>

        <AppCardCount></AppCardCount>

        <!-- container carte -->
        <div v-if="store.cards.length > 0" class="cards_container">
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
  
    padding-top: 90px;


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