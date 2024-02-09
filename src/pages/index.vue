<template>
  <div id="container">

    <div>
      <Brander />
      <Navbarr />
    </div>


    <form id="calculator_form" action="">
      <div id="form_head">
        <h2>Calculadora de interés simple</h2>
      </div>
      <label for="capital">Capital:</label>
      <input type="number" v-model="capital" placeholder="Ingrese el capital" />

      <label for="interest">Interés:</label>
      <input type="number" v-model="interest" placeholder="Ingrese el interés" />

      <label for="returnX">Retorno neto (X):</label>
      <input type="number" :value="calculate_return_x" disabled />

      <label for="return">Retorno bruto (Y):</label>
      <input type="number" :value="calculate_return_y" disabled />

      <button @click="clear_inputs">Limpiar</button>
    </form>
  </div>
</template>

<script>

// Poner todo el header dentro de un componente, y la navbarr adentro

import Brander from '../../public/components/brander.vue';
import Navbarr from '../../public/components/navbarr.vue';

export default {
  components: {
    Brander,
    Navbarr,
  },
  data() {
    return {
      capital: null,
      interest: null
    };
  },
  computed: {
    calculate_return_x() {
      if (this.capital && this.interest) {
        const result = parseFloat(this.capital) * (parseFloat(this.interest) / 100);
        return result !== null ? result.toFixed(2) : null;
      }
      return null;
    },
    calculate_return_y() {
      if (this.capital && this.interest) {
          const result = parseFloat(this.capital) + parseFloat(this.calculate_return_x);
          return result !== null ? result.toFixed(2) : null;
      }
      return null;
    },
    calculate_return_12() {
      if (this.capital && this.interest) {
          const result = parseFloat(this.calculate_return_x) / 12;
          return result !== null ? result.toFixed(2) : null;
      }
      return null;
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