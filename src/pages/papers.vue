<template>
    <div id="container">
      <div>
        <Brander />
        <Navbarr />
      </div>
      <form id="calculator_form" action="">
        <div id="form_head">
          <h2>Evolución de activos en dólares</h2>
          <h3>Devuelve el rendimiento intervenido por el dolar</h3>
        </div>
  
        <label for="paper_start">Especie precio inicial:</label>
        <input type="number" v-model="paper_start" placeholder="Valor incial del activo" />
  
        <label for="usd_srtar">Dolar precio inicial:</label>
        <input type="number" v-model="usd_srtar" placeholder="Dólar al momento de comprar el activo" />
  
        <label for="paper_current">Especie precio actual:</label>
        <input type="number" v-model="paper_current" placeholder="Valor actual del activo" />

        <label for="usd_current">Dolar precio actual:</label>
        <input type="number" v-model="usd_current" placeholder="Dólar al precio actual" />

        <label for="return_difference_usd">Rendimiento obtenido en dólares:</label>
        <input type="number" :value="calculate_return_papers_usd" disabled />

        <label for="return_difference_ars">Rendimiento obtenido en pesos:</label>
        <input type="number" :value="calculate_return_papers_ars" disabled />
  
        <button @click="clear_inputs">Limpiar</button>
      </form>
    </div>

    <div>
        <Footer />
    </div>

  </template>
  
  <script>
  import Brander from '../../public/components/brander.vue';
  import Navbarr from '../../public/components/navbarr.vue';
  import Footer from '../../public/components/footer.vue';

  
  export default {
    components: {
      Brander,
      Navbarr,
      Footer
    },
    data() {
      return {
        capital: null,
        interest: null,
        cycles: null,
        return_simple: null,
        return_compounded: null,
        return_difference: null,
      };
    },
    computed: {
        calculate_return_papers_ars() {
        if (this.paper_start && this.usd_srtar && this.paper_current && this.usd_current) {
          const result = ( parseFloat(this.paper_current) - (parseFloat(this.paper_star) / parseFloat(this.usd_srtar)))
          this.return_difference_usd = result.toFixed(2);
          return this.return_difference_usd;
        }
      },
      calculate_return_papers_usd() {
        if (this.return_simple && this.return_compounded) {
            const result = ( parseFloat(this.paper_current) - (parseFloat(this.paper_star) / parseFloat(this.usd_srtar)) / parseFloat(this.usd_current))
          this.return_difference = result.toFixed(2);
          return this.return_difference;
        }
      }
    },
    methods: {
      clear_inputs() {
        this.paper_start = null;
        this.usd_start = null;
        this.paper_current = null;
        this.usd_current = null;
        this.return_difference_usd = null;
        this.return_difference_ars = null;
      }
    }
  };
  </script>
    
    <style scoped>
      @import "../../public/assets/interceptor.css";
    </style>