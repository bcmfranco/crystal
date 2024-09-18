<template>

  <div id="gumcom_brander" @click="goToHome">
    <div id="logotype">
      <div>IN</div>
    </div>
    <div id="isotype">
      <h1>Interceptor</h1>
      <h2>Online investment calculator</h2>
      <Navbarr />
    </div>
  </div>


</template>

<script>
  export default {
    methods: {
      goToHome() {
        this.$router.push('/');
      }
    }
  }
</script>


<style scoped>

  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

  #gumcom_brander{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-items: center;
    cursor: pointer;
  }

  #gumcom_brander #logotype{
    font-family: Roboto;
    font-size: 25px;
    color: #C4368C;
    width: 50px; /* Ajusta el ancho según tus necesidades */
    height: 50px; /* Ajusta la altura según tus necesidades */
    border: 2px solid #C4368C; /* Color del borde */
    border-radius: 8px; /* Ajusta el radio del borde según tus necesidades */
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.1); /* Añade una sombra */
    margin: 10px;
  }

  #gumcom_brander #isotype h1 {
    color: #C4368C;
    margin: 0px;
    padding: 0px;
  }
  
  #gumcom_brander #isotype h2 {
    font-size: 24px;
    color: #C4368C;
    margin-bottom: 20px;
    margin: 0px;
    padding: 0px;
  }


  @media (max-width: 480px) {

    #gumcom_brander{
      flex-direction: column;
      align-items: start;
      padding: 0px 20px;
    }


  }

</style>