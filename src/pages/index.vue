<template>
  <div id="container">
    <h2>Calculadora de interés simple</h2>
    <label for="capital">Capital:</label>
    <input v-model="capital" placeholder="Ingrese el capital" />

    <label for="interest">Interés:</label>
    <input v-model="interest" placeholder="Ingrese el interés" />

    <label for="returnX">Retorno neto (X):</label>
    <input :value="calculate_return_x" disabled />

    <label for="return">Retorno bruto (Y):</label>
    <input :value="calculate_return_y" disabled />

    <button @click="clear_inputs">Limpiar</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      capital: null,
      interest: null
    };
  },
  computed: {
    calculate_return_x() {
      if (this.capital && this.interest) {
        return parseFloat(this.capital) * (parseFloat(this.interest) / 100);
      }
      return null;
    },
    calculate_return_y() {
      if (this.capital && this.interest) {
        return parseFloat(this.capital) + parseFloat(this.calculate_return_x);
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

:root {
  --vue_green: #26a69a;
}

#container {
  display: grid;
  grid-template-columns: 1fr;
}

#container h2{
  padding: 5px 0px;
    text-transform: uppercase;
    text-decoration: underline #26a69a;
    font-weight: 300;
    font-size: 24px;
    color: #26a69a;
}

label {
  font-size: 16px;
  color: var(--vue_green);
}

input {
  font-size: 16px;
  padding: 10px;
  border: 1px solid #26a69a;
  border-radius: 4px;
  margin-bottom: 20px;
}

button {
  font-size: 16px;
  padding: 10px;
  background-color: #26a69a;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-bottom: 20px;
}

button:hover {
  background-color: #208c7d;
}

.result_field {
  margin-top: 20px;
}
</style>