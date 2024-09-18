<template>
  <div id="container">
    <div>
      <Brander />
      <Navbarr />
    </div>
    <form id="calculator_form" action="">
      <div id="form_head">
        <h2>Calculadora de tope de reintegro</h2>
        <h3>Cuánto puedo gastar según el tope de reintegro que tengo</h3>
      </div>

      <label for="capital">Descuento:</label>
      <input type="number" v-model="discount" placeholder="Porcentaje de descuento" />

      <label for="capital">Tope de reintegro:</label>
      <input type="number" v-model="refund" placeholder="Tope de reintegro" />

      <label for="spent_possible">Podés gastar hasta:</label>
      <input type="number" :value="calculate_spent_possible" disabled />

      <button type="button" @click="clear_inputs">Limpiar</button>
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
      discount: null,
      refund: null,
    };
  },
  computed: {
    calculate_spent_possible() {
      if (this.refund && this.discount) {
        const maxSpend = this.refund / (this.discount / 100);
        return maxSpend.toFixed(0);
      }
      return 0;
    }
  },
  methods: {
    clear_inputs() {
      this.discount = null;
      this.refund = null;
    }
  }
};
</script>

<style scoped>
  @import "../../public/assets/interceptor.css";
</style>
