<template>
  <div id="gumcom_navbarr">
    <router-link to="/">Simple</router-link>
    <router-link to="/montly">Mensualizado</router-link>
    <router-link to="/cycle">Ciclos</router-link>
    <router-link to="/compound">Compuesto</router-link>
    <router-link to="/papers">Activos</router-link>
    <router-link to="/freedom">Libertad</router-link>

  </div>
</template>

<style scoped>

#gumcom_navbarr {
    display: flex;
    justify-content: space-around;
    padding: 20px;
  }

  #gumcom_navbarr a {
    text-decoration: none;
    color: inherit;
    cursor: pointer;
    font-size: 16px;
    padding: 2px;
    border-radius: 4px;
    transition: background-color 0.3s ease;
    color: #C4368C; /* Cambia el color según tu paleta de colores */
  }

  #gumcom_navbarr a:hover {
    border-bottom: 2px solid #C4368C; /* Cambia el color de fondo al pasar el ratón */
  }

  @media (max-width: 480px) {
    a {
      font-size: 14px; /* Ajusta el tamaño de fuente para dispositivos móviles */
      padding: 8px; /* Ajusta el espaciado interno para dispositivos móviles */
    }
  }

</style>
