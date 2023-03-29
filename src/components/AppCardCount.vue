<script>
    import {store} from "../store.js";

    export default {
        name:'AppCardCounter',
        data() {
            return {
                store
            }
        },
    }
</script>

<template>
    <div class="count_container centered">
        <div class="count">Cards Found: {{ this.store.cardCount }}</div>
    </div>
</template>

<style lang="scss" scoped>

@use "../scss/variables" as *;

    .count_container{
        padding-top: 1rem;

        .count{
        width: 200px;
        margin: 0 auto;
        
        text-align: center;

        font-size: 20px;
        color: $text-color;

        background-color: #7549B1;

        @include border();

        
    }

    }
    

</style>