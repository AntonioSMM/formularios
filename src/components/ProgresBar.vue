<template>

<h3 class="text-center" > Proceso: {{porcentaje}}%  </h3>
      <div class="progress">
      <div class="progress-bar progress-bar-striped progress-bar-animated bg-success" 
            role="progressbar" 
            v-bind:aria-valuenow="porcentaje" 
            aria-valuemin="0" 
            aria-valuemax="100"
            :style="`width:${porcentaje}%`" 
            /> 
      </div>

</template>

<script>
      export default {
            props: {
                  porcentaje: Number,
            },
      }
</script>