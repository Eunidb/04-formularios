<template>
    
      <div class="row">
        <div class="col-6 my-2">
            <h3>
                Total Proyectos : {{numeroProyectos}}
              </h3>
        </div>
        <div class="col-6 text-end">
            <button @click="limpiarData" class="btn btn-warning">Limpiar proyecto</button>
        </div>
      </div>

    <div class="table-responsive">
        <table class="table table-dark table-hover">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Proyecto</th>
                    <th>Tipo</th>
                    <th>Urgente</th>
                    <th>Completado</th>
                    <th>Borrar</th>
                </tr>
            </thead>
            <tbody v-for="(proyecto,index) in proyectos" :key="index">
                <tr >
                    <td>{{index + 1}}</td>
                    <td>{{proyecto.proyecto}}</td>
                    <td>{{proyecto.tipo}}</td>
                    <td @click="cambiarEstado(proyecto,'urgente')" :class="proyecto.urgente ?
                     'bg-success' : 'bg-danger'">{{proyecto.urgente ? "Si" : "No"}}</td>

                  <td @click="cambiarEstado(proyecto,'completado')" :class="proyecto.completado ?
                     'bg-success' : 'bg-danger'">{{proyecto.completado ? "Completado" : "Incompleto"}}</td>

                    <td @click="borrar(index)" > 
                       <p>Borrar</p>
                       <svg> 
                            <path d="m2.5 1A1 1 0 0 0-1 1V1a1 1 0 0 0 1 1H3v9a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V4h.5a1"></path></svg> 
                    </td>
                </tr>
            </tbody>
     
        </table>
      </div>
</template>

        <script>
        export default {
            props: [ 'numeroProyectos', 'proyectos', 'cambiarEstado', 'limpiarData', 'borrar'],
           
        }
        </script>