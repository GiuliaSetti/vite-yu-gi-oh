<script>

import {store} from "../store.js";
export default {
  name: "AppNav",
  data() {
    return {

        title: "Yu Gi Oh",

        store,

    }
  },
 
}
</script>
  
<template>

    <header>

        <h1>{{title}}</h1>

    </header>


</template>

<style lang="scss" scoped>

    @use "../scss/variables" as *;

    header{
        width: 100vw;
        background-color: $background;

        padding: 0.7rem;
        color: $text-color;

        text-align: center;

        position: fixed;
        top: 0;

    }

</style>