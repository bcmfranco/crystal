<template>
  <div id="container">

    <div>
      <Brander />
      <Navbarr />
    </div>


    <form id="calculator_form" action="">
      <div id="form_head">
        <h2>Ciclos ahorrados</h2>
        <h3>Cuántos meses se puede vivir quemando el patrimonio</h3>
      </div>

      <label for="capital">Patrimonio:</label>
      <input type="number" v-model="patrimony" placeholder="Ingrese el patrimonio" />

      <label for="salary">Salario:</label>
      <input type="number" v-model="salary" placeholder="Ingrese el salario" />

      <label for="spent">Salario:</label>
      <input type="number" v-model="spent" placeholder="Ingrese el gasto mensual" />

      <label for="return_salary">Salarios ahorrados:</label>
      <input type="number" :value="calculate_patrimony_cycles_salary" disabled />

      <label for="return_spent">Meses que puede vivir sin trabajar:</label>
      <input type="number" :value="calculate_patrimony_cycles_spent" disabled />

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
      patrimony: null,
      salary: null,
      spent: null
    };
  },
  computed: {
    calculate_patrimony_cycles_salary() {
      if (this.patrimony && this.salary) {
        const result = parseFloat(this.patrimony) / parseFloat(this.salary);
        return result !== null ? result.toFixed(2) : null;
      }
      return null;
    },
    calculate_patrimony_cycles_spent() {
      if (this.patrimony && this.spent) {
        const result = parseFloat(this.patrimony) / parseFloat(this.spent);
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