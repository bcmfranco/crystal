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

      <label for="cycles">Ciclos:</label>
      <input type="number" v-model="cycles" placeholder="Durante los cuales se va reinvertir" />

      <label for="return_simple">Retorno por interés simple:</label>
      <input type="number" :value="calculate_return_simple" disabled />

      <label for="return_compounded">Retorno por interés compuesto:</label>
      <input type="number" :value="calculate_return_compounded" disabled />

      <label for="return_difference">Diferencia obtenida:</label>
      <input type="number" :value="calculate_return_difference_sc" disabled />

      <button @click="clear_inputs">Limpiar</button>
    </form>
  </div>
</template>

<script>
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
      interest: null,
      cycles: null,
      return_simple: null,
      return_compounded: null,
      return_difference: null,
    };
  },
  computed: {
    calculate_return_simple() {
      if (this.capital && this.interest && this.cycles) {
        const result = (parseFloat(this.capital) * (parseFloat(this.interest) / 100) * parseInt(this.cycles)) + parseFloat(this.capital);
        this.return_simple = result.toFixed(2);
        return this.return_simple;
      }
    },
    calculate_return_compounded() {
      if (this.capital && this.interest && this.cycles) {
        const result = parseFloat(this.capital) * Math.pow(1 + (parseFloat(this.interest) / 100), parseInt(this.cycles));
        this.return_compounded = result.toFixed(2);
        return this.return_compounded;
      }
    },
    calculate_return_difference_sc() {
      if (this.return_simple && this.return_compounded) {
        const result = parseFloat(this.return_compounded) - parseFloat(this.return_simple);
        this.return_difference = result.toFixed(2);
        return this.return_difference;
      }
    }
  },
  methods: {
    clear_inputs() {
      this.capital = null;
      this.interest = null;
      this.cycles = null;
      this.return_simple = null;
      this.return_compounded = null;
      this.return_difference = null;
    }
  }
};
</script>
  
  <style scoped>
    @import "../../public/assets/interceptor.css";
  </style>