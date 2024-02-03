<template>
  <div id="container">

    <div id="brand">
      brand
    </div>

    <form id="calculator_form" action="">
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
    </form>
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
  --vuegreen: #26a69a;
}

@import url("https://fonts.googleapis.com/css?family=Montserrat");
@font-face {
  font-family: 'Nunito';
  src: url('../../public/assets/Nunito_Sans/static/NunitoSans_7pt_Condensed-Regular.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}


#container{
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 1fr;
  align-items: center;
  justify-items: center;
  height: 100vh;
  font-family: Nunito;
}

#calculator_form {
  display: flex;
  flex-direction: column;
  max-width: 400px;
  margin: 0 auto;
}

h2 {
  font-size: 24px;
  color: #26a69a;
  margin-bottom: 20px;
}

label {
  font-size: 16px;
  color: #26a69a;
  margin-bottom: 8px;
}

input {
  font-size: 16px;
  padding: 10px;
  border: 1px solid #26a69a;
  border-radius: 4px;
  margin-bottom: 20px;
  width: 100%;
  box-sizing: border-box;
}

input[disabled] {
  background-color: #f5f5f5;
}

button {
  font-size: 16px;
  padding: 10px 20px;
  background-color: #26a69a;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #00796b;
}

@media (max-width: 480px) {
  #container {
    grid-template-columns: 1fr;
    grid-template-rows: 10% 80%;
  }
}


</style>