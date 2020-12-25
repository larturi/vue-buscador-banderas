<template>
  <div class="card mb-2">

      <div class="card-header">
         {{pais.name}}
      </div>

      <div class="card-body">

          <div class="row">
              <div class="col">
                  <p class="text-center">
                     <img :src="pais.flag" :alt="`bandera-${pais.name}`" class="img-fluid w-100">
                  </p>
              </div>

              <div class="col">
                <p class="card-text">
                    <span class="badge badge-info p-3 d-block mb-1">Población: {{numeroFormato(pais.population)}}</span>
                    <span class="badge badge-dark p-3 d-block mb-1">Capital: {{pais.capital}}</span>
                    <span class="badge badge-dark p-3 d-block mb-1">Continente: {{pais.region}}</span>
                </p>
              </div>
          </div>
          
      </div>
  </div>
</template>

<script>
export default {
    props: ['pais'],
    setup(){
        const numeroFormato = (num) => {
            return new Intl.NumberFormat("de-DE").format(num);
        }

        return {numeroFormato};
    }

}
</script>