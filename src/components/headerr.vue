<script>
  export default {
    data: () => ({
    url:"https://cdn.svgporn.com/logos/vue.svg",
    alt: "vue.js",
    
    }),
  };
  
</script>




<template>
  <div class = "container mt-3">
      <div class="row">
        <div class="col-12 col-md-3">
          <h1>Formulario</h1>
        </div>
        <div class="col-12 col-md-6"> </div>
            <img :src = "url" :alt="alt" width="100" height="100">
      </div>
    </div>
    
    <hr />

</template>

