<template>
    <div id="container">
  
      <div>
        <Brander />
        <Navbarr />
      </div>
  
  
      <form id="calculator_form" action="">
        <div id="form_head">
          <h2>Calculadora de libertad financiera</h2>
          <h3>Cuánto dinero necesito para dejar de trabajar</h3>
        </div>

        <label for="interest">Gasto mensual:</label>
        <input type="number" v-model="monthly_spent" placeholder="Gasto bruto mensual" />

        <label for="interest">Retorno anual esperado:</label>
        <input type="number" v-model="expected_profit" placeholder="Rendimiento esperado" />

        <label for="capital">Capital actual:</label>
        <input type="number" v-model="saving" placeholder="Ahorros con los que se parte" />
  
        <label for="return_a">Capital necesario:</label>
        <input type="number" :value="calculate_freedom_a" disabled />

        <label for="return_ab">Capital faltante:</label>
        <input type="number" :value="calculate_freedom_ab" disabled />
  
        <button @click="clear_inputs">Limpiar</button>
      </form>
  
      <div>
        <Footer />
      </div>
  
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
        monthly_spent: null,
        expected_profit: null,
        saving: null,
      };
    },
    computed: {
      calculate_freedom_a() {

        var annual_required = this.monthly_spent * 12;
        this.necessary_capital = annual_required / this.expected_profit * 100;

        return this.necessary_capital.toFixed(0);
      },
      calculate_freedom_ab(){

        var annual_required = this.monthly_spent * 12;
        this.remaining_capital = (annual_required / this.expected_profit * 100) - this.saving;
        
        return this.remaining_capital.toFixed(0);
      },
      clear_inputs() {
        this.capital = null;
        this.interest = null;
      }
    }
  };
  </script>
  
  <style scoped>
    @import "../../public/assets/interceptor.css";
  </style>