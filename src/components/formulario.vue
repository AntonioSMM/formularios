<script>
import ProgresBar from './ProgresBar.vue';
import TotalProyectos from './TotalProyectos.vue';
  export default {
    data: () => ({
        proyecto: "",
        tipo: "",
        urgente: false,
        proyectos: [],
    }),
    methods: {
        registrarProyecto() {
            const proyecto = {
                proyecto: this.proyecto,
                tipo: this.tipo,
                urgente: this.urgente,
                completado: false,
            };
            this.proyectos.push(proyecto);
            this.proyecto = "",
                this.tipo = "",
                this.urgente = false;
        },
        cambiarEstado(proyecto, campo) {
            proyecto[campo] = !proyecto[campo];
        }
    },
    computed: {
        numeroProyectos() {
            return this.proyectos.length;
        },
        porcentaje() {
            let completados = 0;
            this.proyectos.map(proyecto => {
                if (proyecto.completado)
                    completados++;
            });
            return (completados * 100) / this.numeroProyectos || 0;
        }
    },
    components: { ProgresBar, TotalProyectos }
};
</script>



<template>

    <div class="row">
        <div class="col-12 mb-4">
            <progres-bar :porcentaje="porcentaje" />
          
        </div>

        <div class="col-12 col-md-4">
            <form @submit.prevent="registrarProyecto">
                <div class="mb-3">
                    <label  class="form-label">Proyecto</label>
                    <input v-model.trim="proyecto" type="text" class="form-control" required />
                </div>

      <div class="mb-3">2
        <label class="form-label"> Actividad </label>
        <select v-model="tipo" class="form-select" required>
          <option disabled selected value="">Selecciona un tipo..</option>
          <option >Aplicaciones Web con Vue.js</option>
          <option >Backend Services con Node.js</option>
          <option >App movil con React Native</option>
        </select>
      </div>

      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-check-label">Urgente</label>
        <input v-model="urgente" type="checkbox" class="form-check-input" />
      </div>

     
      <button type="submit" class="btn btn-primary"> Guardar </button>
    </form>
  </div>

  <div class="col-12 col-md-8">
    <total-proyectos :numeroProyectos = "numeroProyectos"  :proyectos = "proyectos" :cambiarEstado="cambiarEstado"/>



  </div>
</div>

 
</template>