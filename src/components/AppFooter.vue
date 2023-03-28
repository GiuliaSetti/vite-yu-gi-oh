<script>
import {store} from "../store.js";
export default {
  name: "AppFooter",
  data() {
    return {
      store,      
    }
  },
}
</script>
  
<template>

  <footer>
    <div>Made with &hearts; by Giulia</div>
  </footer>
  
</template>

<style lang="scss" scoped>

@use "../scss/variables" as *;

  footer{
    width: 100vw;
    background-color: $background;
    color: $text-color;
    text-align: center;
    padding: 0.5rem;

    position: fixed;
    bottom: 0;
  }


</style>