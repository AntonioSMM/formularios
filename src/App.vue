<template>


  <headerr></headerr>

  <div class="container mt-3">
   

    <formulario></formulario>






</div>
</template>


<script>
  import headerr from "./components/headerr.vue"
  import formulario from "./components/formulario.vue";

  export default{
    components: {
      headerr,
      formulario,
    }

  }

</script>


<style scoped>
  div{
    margin: 0px 2rem;
  }

</style>