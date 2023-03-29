<script>
    // store
    import {store} from "../store.js";

    export default {
        name:'AppSearchBar',
        data() {
            return {
                store
            }
        },
    }
</script>


<template> 
    <div class="searchbar_container centered">

        <input @keyup.enter="$emit('searchCard')" type="text" placeholder="Search a card by name" v-model="store.cardName">
        <button @click="$emit('searchCard')">Search</button>

    </div>
</template>


<style lang="scss" scoped>

@use "../scss/variables" as *;
    .searchbar_container{
        background-color: purple;
       @include border();


        input{
            width: 300px;
            
            border: none;
            @include border();

        }

        button{
            margin: 0 1rem;
            @include border();

            background-color: $background;
            border: none;
            color: $text-color;
            font-weight: bold;

            cursor: pointer;

        }
    }


</style>